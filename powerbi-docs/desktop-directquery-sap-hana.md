---
title: DirectQuery für SAP HANA in Power BI
description: Überlegungen zur Verwendung von DirectQuery mit SAP HANA
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 04/10/2019
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 9d7c5415d084ea7ca9b6a6dd4da3e84662fc6349
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2019
ms.locfileid: "61303799"
---
# <a name="directquery-and-sap-hana"></a>DirectQuery und SAP HANA
Sie können sich mit **SAP HANA**-Datenquellen direkt über **DirectQuery** verbinden. Beim Verbinden mit SAP HANA stehen zwei Optionen zur Verfügung:

* **SAP HANA als mehrdimensionale Quelle behandeln (Standard):**  Bei Auswahl dieser Option ist das Verhalten mit dem vergleichbar, das bei einer Verbindung von Power BI mit anderen mehrdimensionalen Quellen wie SAP Business Warehouse oder Analysis Services besteht. Beim Herstellen einer Verbindung mit SAP HANA, die mit dieser Einstellung, eine einzelne analytische oder Berechnung, die Ansicht ausgewählt ist und alle Measures, stehen Hierarchien und Attribute dieser Ansicht in der Feldliste. Beim Erstellen von Visuals werden die Aggregatdaten immer von SAP HANA abgerufen. Dies ist die empfohlene Vorgehensweise und stellt auch die Standardeinstellung für neue DirectQuery-Berichte über SAP HANA dar.

* **SAP HANA als relationale Quelle behandeln:** Mit dieser Option behandelt Power BI SAP HANA als relationale Quelle. Dies bietet mehr Flexibilität. Muss darauf geachtet werden bei diesem Ansatz um sicherzustellen, dass Measures wie erwartet aggregiert und Leistungsprobleme zu vermeiden.

Der Ansatz für die Verbindung wird durch eine globale Tooloption festlegen bestimmt **Datei > Optionen und Einstellungen** und dann **Optionen > DirectQuery**, und klicken Sie dann das Kontrollkästchen neben  **SAP HANA als relationale Quelle behandeln**, wie in der folgenden Abbildung dargestellt. 

![](media/desktop-directquery-sap-hana/directquery-sap-hana_01a.png)

Nachdem Sie angegeben haben, dass SAP HANA als relationale Quelle behandelt werden soll, wird diese Option auf alle *neu erstellten* Berichte angewendet, die DirectQuery über SAP HANA verwenden. Sie hat weder Auswirkungen auf vorhandene SAP HANA-Verbindungen im aktuellen Bericht noch auf Verbindungen in anderen Berichten, die geöffnet werden. Wenn die Option nicht aktiviert ist, wird beim Herstellen einer neuen Verbindung mit SAP HANA über **Daten abrufen** SAP HANA als mehrdimensionale Datenquelle für die Verbindung verwendet. Jedoch, wenn ein anderer Bericht geöffnet ist, die eine Verbindung mit SAP HANA und dieser Bericht ist weiterhin der Option orientieren, die festgelegt wurde *die zum Zeitpunkt der Erstellung*, was bedeutet, dass alle Berichte, die eine Verbindung mit SAP HANA ist und wurden erstellt vor Februar 2018 weiterhin SAP HANA als relationale Quelle behandelt werden soll. 

Die beiden Ansätze bilden anderes Verhalten, und es ist nicht möglich, einen vorhandenen Bericht ein Ansatz zum anderen wechseln. 

Die beiden Ansätze werden im Folgenden genauer beschrieben.

## <a name="treat-sap-hana-as-a-multi-dimensional-source-default"></a>SAP HANA als mehrdimensionale Quelle behandeln (Standard)

Beim Herstellen einer neuen Verbindung mit SAP HANA wird standardmäßig diese Verbindungsmethode verwendet, bei der SAP HANA als mehrdimensionale Datenquelle behandelt wird. Wenn SAP HANA als relationale Datenquelle behandelt werden soll, sind folgende Schritte notwendig: Rufen Sie zuerst **Datei > Optionen und Einstellungen > Optionen** auf, und aktivieren Sie anschließend unter **DirectQuery** das Kontrollkästchen neben „SAP HANA als relationale Quelle behandeln“. Obwohl dieses Feature in der **Vorschauversion** verfügbar ist, können Berichte, die mit dem mehrdimensionalen Ansatz erstellt wurden, *nicht* im Power BI-Dienst veröffentlicht werden. Wenn das Feature dennoch verwendet wird, führt dies beim Öffnen des Berichts im Power BI-Dienst zu Fehlern.  

Bei der Verbindung mit SAP HANA als mehrdimensionale Quelle gelten die folgenden Überlegungen:

* Im Navigator **Daten abrufen** kann eine einzelne SAP HANA-Ansicht ausgewählt werden. Individuelle Measures oder Attribute lassen sich nicht auswählen. Bei der Verbindungsherstellung wird im Gegensatz zum Datenimport keine Abfrage definiert. Dasselbe gilt, wenn DirectQuery zum Behandeln von SAP HANA als relationale Datenquelle verwendet wird. Dies bedeutet auch, dass es nicht möglich, eine SAP HANA SQL-Abfrage direkt zu verwenden, bei Auswahl dieser Verbindungsmethode.

* Alle Measures, Hierarchien und Attribute der ausgewählten Ansicht werden in der Feldliste angezeigt. 

* Wenn ein Measure in einem Visual verwendet wird, wird SAP HANA abgefragt und dabei der Measurewert auf der Ebene der Aggregation abgerufen, die für das Visual erforderlich ist. Daher werden bei nicht additiven Measures (Zählern, Verhältnissen usw.) alle Aggregationen von SAP HANA ausgeführt, während Power BI keine weitere Aggregation vornimmt. 

* Damit von SAP HANA immer die richtigen Aggregatwerte abgerufen werden, müssen bestimmte Einschränkungen festgelegt werden. Beispielsweise ist es nicht möglich, berechnete Spalten hinzuzufügen oder Daten aus mehreren SAP HANA-Ansichten innerhalb desselben Berichts zu kombinieren. 

Der Ansatz, SAP HANA als mehrdimensionale Quelle zu behandeln, ist im Gegensatz zur *relationalen* Methode weniger flexibel. Er ist jedoch einfacher, garantiert bei komplexeren SAP HANA-Measures korrekte Aggregatwerte und führt allgemein zu einer höheren Leistung. 

Die Liste **Felder** umfasst alle Measures, Attribute und Hierarchien der SAP HANA-Ansicht. Beachten Sie, dass bei dieser Verbindungsmethode folgende Verhalten auftreten:

* Alle Attribute, die in mindestens einer Hierarchie enthalten sind, werden standardmäßig ausgeblendet. Sie können sie sich allerdings bei Bedarf anzeigen lassen, indem Sie aus dem Kontextmenü der Feldliste den Eintrag **Ausgeblendete anzeigen** auswählen. Über dasselbe Kontextmenü lässt sich ggf. der Sichtbarkeitsstatus ändern.

* In SAP HANA kann ein Attribut so definiert werden, dass ein anderes Attribut als dessen Bezeichnung verwendet wird. Z. B. **Produkt** (mit Werten 1,2,3, und So weiter) können **ProductName** (mit Werten, Fahrrad, "Shirt", Handschuhe und So weiter) als dessen Bezeichnung. In diesem Fall wird das Feld **Produkt** in der Feldliste angezeigt, deren Werte die Bezeichnungen „Fahrrad“, „Shirt“, „Handschuhe“ usw. sind. Die Bezeichnungen werden allerdings über die eindeutigen Schlüsselwerte 1, 2 und 3 identifiziert und nach diesen sortiert. Außerdem wird die ausgeblendete Spalte **Produkt.Schlüssel** erstellt, über die bei Bedarf auf die entsprechenden Schlüsselwerte zugegriffen werden kann. 

Alle in der zugrunde liegenden SAP HANA-Ansicht definierten Variablen werden zum Verbindungszeitpunkt angezeigt. Dabei können die erforderlichen Werte eingegeben werden. Diese Werte können später ändern, indem Sie auswählen **Abfragen bearbeiten** aus dem Menüband, und klicken Sie dann **Parameter verwalten** im Dropdown-Menü angezeigt. 

Die zulässigen Modellierungsvorgänge sind restriktiver als bei der Verwendung von DirectQuery, da sichergestellt werden muss, dass die richtigen Aggregatdaten immer von SAP HANA abgerufen werden können. Allerdings ist es weiterhin möglich, viele Ergänzungen und Änderungen vorzunehmen und beispielsweise Measures zu definieren, Felder umzubenennen und auszublenden sowie Anzeigeformate zu definieren. Alle Änderungen werden bei einer Aktualisierung beibehalten. Außerdem werden alle an der SAP HANA-Ansicht vorgenommenen Änderungen übernommen, die zu keinen Konflikten führen. 

### <a name="additional-modeling-restrictions"></a>Zusätzliche modellierungseinschränkungen

Wenn über DirectQuery eine Verbindung mit SAP HANA hergestellt und SAP HANA als mehrdimensionale Quelle verwendet wird, sind v.a. die folgenden zusätzlichen Modellierungseinschränkungen zu berücksichtigen: 

* **Keine Unterstützung für berechnete Spalten:** Das Erstellen berechneter Spalten ist deaktiviert. Dies bedeutet zudem, dass Gruppierung und Clustering, mit denen berechnete Spalten erstellt werden, nicht zur Verfügung stehen.
* **Zusätzliche Einschränkungen für Measures:** Es gibt zusätzliche Einschränkungen von DAX-Ausdrücken, die in Measures verwendet werden können, damit die von SAP HANA bereitgestellte Unterstützung übernommen wird.
* **Keine Unterstützung für das Definieren von Beziehungen:** Innerhalb eines Berichts können nur einzelne Ansichten abgefragt werden. Daher können auch keine Beziehungen definiert werden.
* **Keine Datenansicht:** Die **Datenansicht** zeigt in der Tabelle normalerweise Daten auf Detailebene an. Aufgrund der Eigenschaften von OLAP-Quellen wie SAP HANA ist diese Ansicht in SAP HANA nicht verfügbar.
* **Details von Spalten und Measures sind unveränderlich:** Die in der Feldliste anzeigte Listen von Spalten und Measures sind in der zugrunde liegenden Quelle festgelegt und können nicht verändert werden. Es ist z.B. nicht möglich, eine Spalte oder deren Datentyp zu löschen. Sie können sie allerdings umbenennen.
* **Zusätzliche Einschränkungen in DAX:** Es gibt zusätzliche Einschränkungen für die DAX-Bibliothek, die in Measuredefinitionen verwendet werden kann, damit die Einschränkungen in der Quelle übernommen werden. Es ist z.B. nicht möglich, eine Aggregatfunktion für eine Tabelle zu verwenden.

### <a name="additional-visualization-restrictions"></a>Zusätzliche visualisierungseinschränkungen

Wenn über DirectQuery eine Verbindung mit SAP HANA hergestellt und SAP HANA als mehrdimensionale Quelle verwendet wird, sind Einschränkungen bei Visuals zu beachten: 
* **Keine Spaltenaggregation:** Es ist nicht möglich, die Aggregation einer Spalte für ein Visual zu ändern. Die Einstellung lautet immer *Nicht zusammenfassen*.

## <a name="treat-sap-hana-as-a-relational-source"></a>SAP HANA als relationale Quelle behandeln 

Wenn eine Verbindung mit SAP HANA als relationale Datenquelle hergestellt wird, lassen sich erweiterte Funktionen nutzen. Sie können z.B. berechnete Spalten erstellen, Daten aus mehreren SAP HANA-Ansichten einbeziehen und Beziehungen zwischen Tabellen erstellen. Wenn Sie SAP HANA auf diese Weise nutzen möchten, sollten Sie jedoch bestimmte Verbindungsaspekte berücksichtigen, um sicherzustellen, dass 

* die Ergebnisse richtig sind, wenn die SAP HANA-Ansicht nicht additive Measures (z.B. Distinct Count Measures oder Mittelwerte statt einfache Summen) enthält und
* Die resultierenden Abfragen besonders effizient sind

Es ist zunächst sinnvoll, sich mit dem Verhalten einer relationalen Quelle wie SQL Server zu befassen, wenn die Abfrage, die in **Daten abrufen** oder im **Abfrage-Editor** festgelegt ist, eine Aggregation ausführt. Im folgenden Beispiel gibt eine im **Abfrage-Editor** definierte Abfrage den Durchschnittspreis anhand der *ProductID* zurück.  

![](media/desktop-directquery-sap-hana/directquery-sap-hana_01.png)

Wenn die Daten in Power BI importiert werden (im Vergleich zur Verwendung von DirectQuery), würde sich das Folgende ergeben:

* Die Daten werden auf der Ebene der Aggregation importiert, die von der im **Abfrage-Editor** erstellten Abfrage definiert ist. Beispielsweise der Durchschnittspreis nach Produkt. Dies führt zu einer Tabelle mit den beiden Spalten *ProductID* und *AveragePrice*, die in visuellen Elementen verwendet werden können.
* In einem visuellen Element erfolgt jede nachträgliche Aggregation (z.B. *Summe*, *Durchschnitt*, *Min*, oder andere) über die importierten Daten. Wenn Sie beispielsweise *AveragePrice* aus einem Visual einbeziehen, wird das Aggregat *Sum* standardmäßig verwendet. So würde die Summe über den *AveragePrice*-Wert jeder *ProductID* zurückgegeben werden. In diesem Beispiel würde sie 13,67 betragen. Das gleiche gilt für andere Aggregatfunktionen (z.B. *Min*, *Average*, usw.), die in dem visuellen Element verwendet werden. Z. B. *durchschnittliche* von *AveragePrice* gibt den Durchschnitt von 6,66, 4 und 3, was 4,56 ergibt, und nicht den Durchschnitt von *Preis* in den sechs Datensätzen in der zugrunde liegenden Tabelle handelt es sich 5,17 ergibt.
  
Wenn für dieselbe relationale Quelle **DirectQuery** anstelle der Option „Import“ (Importieren) verwendet wird, ist die gleiche Semantik anzuwenden, und die Ergebnisse wären identisch:  

* Bei der gleichen Abfrage werden logisch genau die gleichen Daten der Berichtsebene angezeigt – obwohl die Daten tatsächlich nicht importiert werden.

* In einem visuellen Element werden alle nachfolgenden Aggregationen (*Summe*, *Durchschnitt*, *Min*, andere) erneut über diese logische Tabelle aus der Abfrage ausgeführt. Und wieder gibt ein visuelles Element, das *Average* von *AveragePrice* enthält, das gleiche Ergebnis zurück, nämlich 4,56.
  
Nun wird SAP HANA vor dem Hintergrund einer relationalen Verbindungsquelle betrachtet. Power BI funktioniert mit *analytischen Ansichten* und *Berechnungsansichten* in SAP HANA, die beide Measures enthalten können. Mittlerweile folgt der Ansatz für SAP HANA aber denselben Prinzipien, die weiter oben beschrieben wurden: Die Abfrage, die in **Daten abrufen** oder im **Abfrage-Editor** definiert wird, legt fest, welche Daten verfügbar sind, und anschließend werden alle nachfolgenden Aggregationen in einem Visual für diese Daten ausgeführt. Das Gleiche gilt sowohl für die Option „Import“ (Importieren) als auch für DirectQuery.  
Angesichts der Beschaffenheit von SAP HANA ist die im ersten Dialogfeld **Daten abrufen** oder im **Abfrage-Editor** definierte Abfrage immer eine Aggregatabfrage und enthält in der Regel Measures, bei denen die tatsächliche Aggregation, die verwendet wird, durch die SAP HANA-Ansicht definiert ist.

Die Entsprechung des SQL Servers im oben angeführten Beispiel ist, dass eine SAP HANA-Sicht vorhanden ist, die *ID*, *ProductID*, *DepotID* und Measures, einschließlich *AveragePrice* enthält, was in der Ansicht als *Durchschnittspreis* definiert ist.  
    
Sofern es sich um die **Get Data** Erfahrung, die Auswahl vorgenommen wurden, für **"ProductID"** und **AveragePrice** Measures, die eine Abfrage über die Ansicht angefordert wird, der definiert wird Aggregieren von Daten (im vorherigen Beispiel, aus Gründen der Einfachheit Pseudo-SQL wird verwendet, die nicht die genaue Syntax für SAP HANA SQL entspricht). Dann aggregieren alle weiteren Aggregationen, die in einem visuellen Element definiert sind, die Ergebnisse für eine solche Abfrage weiter. Wie oben bereits für SQL Server beschrieben, gilt dies sowohl für die Option „Import“ (Importieren) als auch für DirectQuery. In den DirectQuery-Fall die Abfrage von **Datenabruf** oder **Abfrage-Editor** wird in einer untergeordneten SELECT-Anweisung innerhalb einer einzelnen Abfrage an SAP HANA gesendet wird, und daher nicht tatsächlich der Fall, in dem alle Daten vor der gelesen werden sollen Um weiteren aggregieren.  

Wenn DirectQuery für SAP HANA verwendet wird, müssen daher die folgenden Überlegungen und Verhalten unbedingt beachtet werden:  

* Berücksichtigt werden müssen alle weiteren Aggregationen, die in Visuals ausgeführt werden, wenn das Measure in SAP HANA nicht additiv ist (z.B. keine einfache *Summe*, *Min* oder *Max*).

* In **Daten abrufen** oder im **Abfrage-Editor** werden nur die zum Abrufen der Daten erforderlichen Spalten einbezogen. Dies zeigt, dass das Ergebnis eine sinnvolle Abfrage sein muss, die an SAP HANA gesendet werden kann. Z. B. wenn Dutzende von Spalten, mit der Gedanke ausgewählt wurden, dass sie möglicherweise auf nachfolgende Visualisierungen benötigt werden bedeutet dann selbst für DirectQuery ein einfaches visuelles, dass die Aggregatabfrage, die in der Unterauswahl verwendet diese Dutzenden Spalten enthält, was die in der Regel wird Führen Sie schlecht.
  
Betrachten wir dazu ein Beispiel. Wenn Sie im folgenden Beispiel fünf Spalten (**CalendarQuarter**, **Color**, **LastName**, **ProductLine** und **SalesOrderNumber**) im Dialogfeld **Daten abrufen** zusammen mit dem Measure *OrderQuantity* auswählen, bedeutet dies, dass das Erstellen eines einfachen Visuals, das die Mindestbestellmenge (OrderQuantity) enthält, später zu der folgenden SQL-Abfrage an SAP HANA führt. Der schattierte Bereich ist die untergeordnete SELECT-Anweisung, die die Abfrage von **Daten abrufen** / **Abfrage-Editor** enthält. Wenn diese untergeordnete SELECT-Anweisung bietet ein hohes kardinalitätsergebnis ergibt, wird die resultierende SAP HANA-Leistung wahrscheinlich schlechter sein.  

![](media/desktop-directquery-sap-hana/directquery-sap-hana_03.png)

   
Aufgrund dieses Verhaltens wird empfohlen, dass die Elemente, die in **Daten abrufen** oder im **Abfrage-Editor** ausgewählt werden, auf die erforderlichen Elemente beschränkt werden, solange sie weiterhin in einer sinnvollen Abfrage für SAP HANA resultieren.  

## <a name="best-practices"></a>Bewährte Methoden 

Die Nutzungsempfehlungen für DirectQuery gelten auch für beide Ansätze zum Herstellen einer Verbindung mit SAP HANA. Dies ist insbesondere für die Best Practices der Fall, die eine zufriedenstellende Leistung garantieren sollen. Diese Empfehlungen werden ausführlich im Artikel [Verwenden von DirectQuery mit Power BI](desktop-directquery-about.md) beschrieben.
   
## <a name="limitations"></a>Einschränkungen

In der folgenden Liste werden alle Features von SAP HANA aufgelistet, die nicht vollständig unterstützt werden oder sich mit Power BI anders verhalten. 

* **Über-/untergeordnete Hierarchien**: Diese werden in Power BI nicht angezeigt.
Dies liegt daran, dass Power BI über die SQL-Schnittstelle auf SAP HANA zugreift. Mit SQL ist ein vollständiger Zugriff auf über-/untergeordnete Hierarchien jedoch nicht möglich.
* **Andere Hierarchiemetadaten**: Die grundlegende Struktur von Hierarchien wird in Power BI angezeigt. Einige Hierarchiemetadaten (z.B. die Steuerung des Verhaltens unregelmäßiger Hierarchien) haben jedoch keine Auswirkung.
Auch dies ist auf die Einschränkungen zurückzuführen, die die SQL-Schnittstelle mit sich bringt.
* **Verbindung über SSL** – Sie können eine Verbindung mit den Import herstellen und mehrdimensional, mit SSL verwendet wird, kaufen kann keine Verbindung mit SAP HANA-Instanzen, die für die Verwendung von SSL für den relationalen-Connector konfiguriert.
* **Unterstützung für Attributansichten:** Power BI kann eine Verbindung mit den Ansichten „Analyse“ und „Berechnung“ herstellen. Eine direkte Verbindung mit Ansicht „Attribut“ ist hingegen nicht möglich.
* **Unterstützung für Katalogobjekte**: Power BI kann keine Verbindung mit Katalogobjekten herstellen.
* **Änderungen an Variablen nach der Veröffentlichung**: Nachdem der Bericht veröffentlicht wurde, können Sie die Werte der SAP HANA-Variablen nicht mehr direkt im Power BI-Dienst ändern. 
 
## <a name="known-issues"></a>Bekannte Probleme 
In der folgenden Liste werden alle bekannten Probleme beschrieben, die beim Herstellen einer Verbindung mit SAP HANA (DirectQuery) über Power BI auftreten. 

* **Problem mit SAP HANA bei Abfragen für Zähler und andere Measures**: Falsche Daten werden von SAP HANA zurückgegeben, wenn eine Verbindung mit einer analytischen Ansicht hergestellt wird und ein Zählermeasure sowie ein weiteres Verhältnismeasure in demselben Visual enthalten sind. Dieses Problem wird im SAP-Hinweis 2128928 „Unexpected results when query a Calculated Column and a Counter“ (Unerwartete Ergebnisse beim Abfragen einer berechneten Spalte und eines Zählers) beschrieben. In diesem Fall ist das Verhältnismeasure falsch. 

* **Erstellung mehrerer Power BI-Spalten aus einer SAP HANA-Spalte**: Bei einigen Berechnungsansichten, in denen eine SAP HANA-Spalte in mehreren Hierarchien verwendet wird, stellt SAP HANA zwei eigenständige Attribute bereit. Dies führt dazu, dass zwei Spalten in Power BI erstellt werden.  Diese werden allerdings standardmäßig ausgeblendet, und alle Abfragen im Zusammenhang mit Hierarchien oder Spalten verhalten sich korrekt. 
 
## <a name="next-steps"></a>Nächste Schritte

Weitere Informationen zu DirectQuery finden Sie in den folgenden Ressourcen:

* [DirectQuery in Power BI](desktop-directquery-about.md)
* [Von DirectQuery unterstützte Datenquellen](desktop-directquery-data-sources.md)
* [DirectQuery und SAP BW](desktop-directquery-sap-bw.md)
* [Lokales Datengateway](service-gateway-onprem.md)

