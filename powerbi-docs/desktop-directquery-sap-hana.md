---
title: "DirectQuery für SAP HANA in Power BI"
description: "Überlegungen zur Verwendung von DirectQuery mit SAP HANA"
services: powerbi
documentationcenter: 
author: davidiseminger
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/12/2017
ms.author: davidi
ms.openlocfilehash: d6f863df59d7374c792f1e1ac16db3a04ad99d87
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2017
---
# <a name="directquery-and-sap-hana"></a>DirectQuery und SAP HANA
Sie können sich mit **SAP HANA**-Datenquellen direkt über **DirectQuery** verbinden.

Bei der Verwendung von **SAP HANA** ist es wichtig, einige Aspekte der Behandlung der Verbindungsherstellung zu verstehen, um sicherzustellen, dass:

* Die Ergebnisse wie erwartet sind, wenn die SAP HANA-Ansicht nicht additive Measures (z.B. unterscheidbare Grafen oder Mittelwerte, statt einfache Summen) enthält
* Die resultierenden Abfragen besonders effizient sind

Es ist sinnvoll, sich beim Start einen Moment Zeit zu nehmen, um sich das Verhalten von einer relationalen Quelle wie z.B. **SQL Server** klar zu machen, wenn die Abfrage, die in **Daten abrufen** oder im **Abfrage-Editor** festgelegt ist, eine Aggregation ausführt. Im folgenden Beispiel gibt eine im **Abfrage-Editor** definierte Abfrage den Durchschnittspreis anhand der **ProductID** zurück.

![](media/desktop-directquery-sap-hana/directquery-sap-hana_01.png)

Wenn die Daten in Power BI importiert werden (im Vergleich zur Verwendung von DirectQuery), würde sich das Folgende ergeben:

* Die Daten werden auf der Ebene der Aggregation importiert, die von der im **Abfrage-Editor** erstellten Abfrage definiert ist. Beispielsweise der Durchschnittspreis nach Produkt. Dies führt zu einer Tabelle mit den beiden Spalten *ProductID* und *AveragePrice*, die in visuellen Elementen verwendet werden können.
* In einem visuellen Element erfolgt jede nachträgliche Aggregation (z.B. *Summe*, *Durchschnitt*, *Min*, oder andere) über die importierten Daten.  Wenn Sie beispielsweise den *AveragePrice* in einem visuellen Element einbeziehen, wird das Aggregat *Sum* standardmäßig verwendet. So würde die Summe über den *Averageprice* jeder *ProductID* zurückgegeben werden – in diesem Fall würde diese 13,67 betragen. Das gleiche gilt für andere Aggregatfunktionen (z.B. *Min*, *Average*, usw.), die in dem visuellen Element verwendet werden. *Average* von *AveragePrice* gibt z.B. den Durchschnitt von 6,66, 4 und 3 zurück, was 4,56 ergibt, und *nicht* den Durchschnitt von *Price* in den sechs Datensätzen in der zugrunde liegenden Tabelle, was 5,17 ergibt.

Wenn **DirectQuery** anstelle des Importierens verwendet wird, ist die gleiche Semantik anzuwenden und die Ergebnisse wären absolut identisch:

* Bei der gleichen Abfrage werden logisch genau die gleichen Daten der Berichtsebene angezeigt – obwohl die Daten tatsächlich nicht importiert werden.
* In einem visuellen Element werden alle nachfolgenden Aggregationen (*Summe*, *Durchschnitt*, *Min*, andere) erneut über diese logische Tabelle aus der Abfrage ausgeführt. Und wieder gibt ein visuelles Element, das *Average* von *AveragePrice* enthält, das gleiche Ergebnis zurück, nämlich 4,56.

Jetzt betrachten wir **SAP HANA**. Power BI funktioniert mit *analytischen Ansichten* und *Berechnungsansichten* in SAP HANA, die beide Measures enthalten können. Aber heute folgt der Ansatz für SAP HANA denselben Prinzipien, wie sie zuvor beschrieben wurden: Die Abfrage, die in **Daten abrufen** oder im **Abfrage-Editor** definiert ist, bestimmt die Daten, die verfügbar sind, und dann erfolgen alle nachfolgenden Aggregationen in einem visuellen Element über diese Daten. Das gleiche gilt sowohl für Import als auch für DirectQuery.

Angesichts der Beschaffenheit von HANA ist die im ersten Dialogfeld **Daten abrufen** oder im **Abfrage-Editor** definierte Abfrage immer eine Aggregatabfrage und enthält in der Regel Measures, bei denen die tatsächliche Aggregation, die verwendet wird, durch die HANA-Ansicht definiert ist.

Die Entsprechung des SQL-Servers im oben angeführten Beispiel ist, dass eine HANA-Sicht vorhanden ist, die **ID**, **ProductID**, **DepotID**, und Measures, einschließlich **Durchschnittspreis** enthält, was in der Ansicht als **Durchschnittspreis** definiert ist.

![](media/desktop-directquery-sap-hana/directquery-sap-hana_02.png)

Wenn unter **Get Data** die Auswahl für die Measures **ProductID** und **AveragePrice** getroffen wurde, wird dadurch eine Abfrage über die Ansicht definiert, die die Aggregatdaten anfordert (im oben stehenden Beispiel wird der Einfachheit halber Pseudo-SQL verwendet, die nicht genau der Syntax von HANA SQL entspricht). Dann aggregieren alle weiteren Aggregationen, die in einem visuellen Element definiert sind, die Ergebnisse für eine solche Abfrage weiter. Wie oben bereits für **SQL Server** beschrieben, gilt dies sowohl für den Import als auch für den DirectQuery-Fall. Beachten Sie, dass im DirectQuery-Fall die Abfrage von **Daten abrufen** oder vom **Abfrage-Editor** in einer untergeordneten SELECT-Anweisung innerhalb einer einzelnen Abfrage verwendet wird, die an HANA gesendet wird. Daher handelt es sich nicht tatsächlich um den Fall, in dem alle Daten vor dem weiteren Aggregieren gelesen werden.

Dies führt zu folgenden wichtigen Überlegungen bei der Verwendung von DirectQuery über HANA:

* Berücksichtigt werden müssen alle weiteren Aggregationen, die in Visuals ausgeführt werden, wenn das Measure in HANA nicht additiv ist (z.B. keine einfache *Summe*, *Min*, oder *Max*).
* In **Daten abrufen** oder im **Abfrage-Editor** werden nur die erforderlichen Spalten einbezogen, um die erforderlichen Daten abzurufen, was widerspiegelt, dass das Ergebnis eine Abfrage sein wird, die eine sinnvolle Abfrage sein muss, die an HANA gesendet werden kann. Wenn z.B. Dutzende von Spalten ausgewählt wurden, um herauszufinden, ob sie möglicherweise in nachfolgenden visuellen Elementen benötigt werden, dann bedeutet ein einfaches visuelles Element selbst für DirectQuery, dass die Aggregatabfrage, die in der Unterauswahl verwendet wurde, diese Dutzenden Spalten enthält, was allgemein zu keiner guten Leistung führt.

Betrachten wir dazu ein Beispiel. Wenn Sie im folgenden Beispiel fünf Spalten („CalendarQuarter“, „Color, „LastName“, „ProductLine“, „SalesOrderNumber“) im Dialogfeld **Daten abrufen** zusammen mit dem Measure „OrderQuantity“ auswählen, bedeutet dies, dass später die Erstellung eines einfachen visuellen Elements, das die Mindest-OrderQuantity enthält, zu der folgenden SQL-Abfrage an HANA führen wird. Der schattierte Bereich ist die untergeordnete SELECT-Anweisung, die die Abfrage von **Daten abrufen** / **Abfrage-Editor** enthält. Wenn diese untergeordnete SELECT-Anweisung ein sehr hohes Kardinalitäts-Ergebnis ergibt, ist es wahrscheinlich, dass die resultierende HANA-Leistung schlechter sein wird.

![](media/desktop-directquery-sap-hana/directquery-sap-hana_03.png)

Aus diesem Grund wird empfohlen, dass die Elemente, die in **Daten abrufen** oder im **Abfrage-Editor** ausgewählt werden, auf die Elemente beschränkt sind, die erforderlich sind, während Sie weiterhin in einer sinnvollen Abfrage für HANA resultieren.

### <a name="next-steps"></a>Nächste Schritte
Weitere Informationen zu DirectQuery finden Sie in den folgenden Ressourcen:

* [DirectQuery in Power BI](desktop-directquery-about.md)
* [Von DirectQuery unterstützte Datenquellen](desktop-directquery-data-sources.md)
* [DirectQuery und SAP BW](desktop-directquery-sap-bw.md)
* [Lokales Datengateway](service-gateway-onprem.md)

