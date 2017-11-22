---
title: "Verwenden von Was-wäre-wenn-Parametern zum Visualisieren von Variablen in Power BI Desktop"
description: "Erstellen Sie eine eigene Was-wäre-wenn-Variable, um Variablen in Power BI-Berichten zu imaginieren und visualisieren"
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
ms.openlocfilehash: 5b02f55a14592020e73005e44f8692cdb01693c7
ms.sourcegitcommit: f2b38777ca74c28f81b25e2f739e4835a0ffa75d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2017
---
# <a name="create-and-use-a-what-if-parameter-to-visualize-variables-in-power-bi-desktop"></a>Erstellen und Verwenden eines Was-wäre-wenn-Parameters zum Visualisieren von Variablen in Power BI Desktop
Ab der **Power BI Desktop**-Version von August 2017 können Sie **Was-wäre-wenn**-Variables für Ihre Berichte erstellen, mit der Variablen als Slicer interagieren und auf diese Weise unterschiedliche wichtige Werte in den Berichten visualisieren und quantifizieren.

![](media/desktop-what-if/what-if_01.png)

Der Parameter **Was-wäre-wenn** befindet sich auf der Registerkarte **Modellierung** von **Power BI Desktop**. Wenn Sie diese Option auswählen, wird ein Dialogfeld angezeigt, in dem Sie den Parameter konfigurieren können.

## <a name="creating-a-what-if-parameter"></a>Erstellen eines Was-wäre-wenn-Parameters
Wählen Sie zum Erstellen eines **Was-wäre-wenn**-Parameters die Schaltfläche **Was-wäre-wenn** auf der Registerkarte **Modellierung** in **Power BI Desktop**. In der folgenden Abbildung wurde ein Parameter mit dem Namen *Discount percentage* (Rabattprozentsatz) erstellt und sein Datentyp auf *Dezimalzahl* festgelegt. Der Wert von *Minimum* ist 0, und der Wert von *Maximum* ist 0,50 (fünfzig Prozent). Außerdem wurde *Inkrement* auf 0,05 bzw. fünf Prozent festgelegt. Um diesen Betrag wird der Parameter angepasst, wenn in einem Bericht eine Interaktion mit ihm erfolgt.

![](media/desktop-what-if/what-if_02.png)

> [!NOTE]
> Stellen Sie Dezimalzahlen eine 0 voran, also in diesem Feld 0,50 und nicht ,50. Andernfalls wird die Zahl nicht ausgewertet, und die Schaltfläche **OK** kann nicht ausgewählt werden.
> 
> 

Durch Aktivieren des Kontrollkästchens **Slicer zu dieser Seite hinzufügen** wird mit dem **Was-wäre-wenn**-Parameter automatisch ein Slicer auf der aktuellen Berichtsseite hinzugefügt.

![](media/desktop-what-if/what-if_03.png)

Durch das Erstellen eines **Was-wäre-wenn**-Parameters wird auch ein Measure erstellt, mit dem Sie den aktuellen Wert des **Was-wäre-wenn**-Parameters visualisieren können.

![](media/desktop-what-if/what-if_04.png)

Beachten Sie, dass nach dem Erstellen eines **Was-wäre-wenn**-Parameters sowohl der Parameter als auch das Measure Teil des Modells werden. Sie sind somit im gesamten Bericht verfügbar und können auf anderen Berichtsseiten verwendet werden. Und da sie Teil des Modells sind, können Sie den Slicer von der Berichtsseite löschen. Wenn er wieder auf ihr enthalten sein soll, ziehen Sie einfach den Parameter **Was-wäre-wenn** aus der Liste **Felder** in den Zeichenbereich (ändern Sie dann das Visual in einen Slicer), um den **Was-wäre-wenn**-Parameter einfach wieder dem Bericht hinzuzufügen.

## <a name="using-a-what-if-parameter"></a>Verwenden eines Was-wäre-wenn-Parameters
Lassen Sie uns ein einfaches Beispiel für die Verwendung eines **Was-wäre-wenn**-Parameters erstellen. Im vorherigen Abschnitt haben wir den **Was-wäre-wenn**-Parameter erstellt. Jetzt werden wir ihn auch verwenden, indem wir ein neues Measure erstellen, dessen Wert mit dem Schieberegler angepasst wird. Zu diesem Zweck erstellen wir ein neues Measure.

![](media/desktop-what-if/what-if_05.png)

Das neue Measure ist einfach der Gesamtumsatz, auf den der Rabatt angewendet wird. Sie können selbstverständlich komplexe und interessante Measures erstellen, mit denen die Benutzer Ihrer Berichte die Variable des **Was-wäre-wenn**-Parameters visualisieren können. Sie können z.B. einen Bericht erstellen, mit dem Vertriebsmitarbeiter die Vergütung, die sie beim Erreichen bestimmter Umsatzziele oder -prozentwerte erhalten, oder die Erhöhung von Rabatten aufgrund höherer Umsätze anzeigen können.

Sobald wir die Measureformel in der Bearbeitungsleiste eingegeben und sie mit **Sales after Discount** (Auftragsrabatt) benannt haben, wird das Ergebnis angezeigt:

![](media/desktop-what-if/what-if_06.png)

Anschließend erstellen wir ein Säulendiagramm-Visual mit *OrderDate* auf der Achse und mit *SalesAmount* und dem gerade erstellten Measure *Sales after Discount* (Auftragsrabatt) als Werte.

![](media/desktop-what-if/what-if_07.png)

Wenn wir dann den Schieberegler bewegen, stellen wir fest, dass die Spalte *Sales after Discount* (Auftragsrabatt) den ermäßigten Umsatzbetrag wiedergibt.

![](media/desktop-what-if/what-if_08.png)

Das war schon alles. Sie können den **Was-wäre-wenn**-Parameter in allen möglichen Situationen verwenden, damit die Benutzer von Berichten mit unterschiedlichen Szenarien interagieren können, die Sie in Ihren Berichten erstellen.

