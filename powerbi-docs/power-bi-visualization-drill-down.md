---
title: Drilldown in einer Visualisierung in Power BI
description: "Dieses Dokument veranschaulicht, wie Sie im Microsoft Power BI-Dienst und in Power BI Desktop einen Drilldown in eine Visualisierung durchführen können."
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: MNAaHw4PxzE
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 01/08/2018
ms.author: mihart
ms.openlocfilehash: 22dc1c9b703b500625a5aed23b6187fd3f616dde
ms.sourcegitcommit: 804ee18b4c892b7dcbd7d7d5d987b16ef16fc2bb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2018
---
# <a name="drill-down-in-a-visualization-in-power-bi"></a>Drilldown in einer Visualisierung in Power BI
## <a name="drill-down-requires-a-hierarchy"></a>Ein Drilldown setzt eine Hierarchie voraus
Wenn eine Visualisierung eine Hierarchie aufweist, können Sie einen Drilldown ausführen, um weitere Details einzublenden. Sie verfügen beispielsweise über eine Visualisierung eines Olympia-Medaillenspiegels, hierarchisch geordnet nach Sportart, Disziplin und Ereignis. Standardmäßig würde die Visualisierung die Anzahl der Medaillen nach Sportart anzeigen – Gymnastik, Skisport, Wassersport usw. Da jedoch eine Hierarchie vorhanden ist, wird durch die Auswahl eines Visualisierungselements (etwa eines Balkens, einer Linie oder einer Blase) ein zunehmend detaillierteres Bild angezeigt werden. Sie würden beispielsweise das Element **Wassersport** auswählen, um Daten für Schwimmsport, Kunstspringen und Wasserball anzuzeigen.  Sie wählen das Element **Kunstspringen** aus, um Details zu Sprungbrett, Sprungturm und Synchronsprung-Veranstaltungen anzuzeigen.

Sie können Hierarchien Berichten hinzufügen, deren Eigentümer Sie sind, jedoch nicht Berichten, die für Sie freigegeben wurden.
Sie sind nicht sicher, welche Power BI-Visualisierungen eine Hierarchie enthalten?  Zeigen Sie mit dem Mauszeiger auf eine Visualisierung. Wenn diese Drilldown-Steuerelemente in den oberen Ecken sichtbar sind, weist die Visualisierung eine Hierarchie auf.

![](media/power-bi-visualization-drill-down/power-bi-drill-icon4.png)  ![](media/power-bi-visualization-drill-down/power-bi-drill-icon2.png)  ![](media/power-bi-visualization-drill-down/power-bi-drill-icon3.png)
![](media/power-bi-visualization-drill-down/power-bi-drill-icon5.png) ![](media/power-bi-visualization-drill-down/power-bi-drill-icon6.png)  

Datumsangaben stellen einen eindeutigen Hierarchietyp dar. Wenn Sie einer Visualisierung ein Datumsfeld hinzufügen, wird in Power BI automatisch eine Zeithierarchie hinzugefügt, die Jahr, Quartal, Monat und Tag enthält. Weitere Informationen finden Sie unter [Visuelle Hierarchien und Drilldownverhalten](guided-learning/visualizations.yml#step-18), oder sehen Sie sich das Video unten an.

  <iframe width="560" height="315" src="https://www.youtube.com/embed/MNAaHw4PxzE?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>

> [!NOTE]
> Informationen zum Erstellen von Hierarchien mit Power BI Desktop erhalten Sie im Video zum [Erstellen und Hinzufügen von Hierarchien](https://youtu.be/q8WDUAiTGeU).
> 
> 

## <a name="two-methods-to-drill-down"></a>Zwei Drilldown-Methoden
Es gibt zwei Methoden, um in Ihrer Visualisierung einen Drilldown (und Drillup) durchzuführen.  Beide werden in diesem Artikel beschrieben. Sie erreichen mit beiden Methoden dasselbe Ziel und können daher beliebig wählen.

> [!NOTE]
> [Öffnen Sie hierfür das Analysebeispiel für Einzelhandel](sample-datasets.md) im Power BI-Dienst, und erstellen Sie eine TreeMap, in der **Total Units This Year** (Summe der Einheiten, dieses Jahr) (Werte) nach **Territory** (Gebiet), **City** (Stadt), **PostalCode** (Postleitzahl) und **Name** (Gruppe) betrachtet werden.  
> 
> 

## <a name="method-1-for-drill-down"></a>Methode 1 für Drilldowns
Bei dieser Methode werden die Drilldownsymbole verwendet, die sich in den oberen Ecken der Visualisierung selbst befinden.

1. Öffnen Sie in Power BI einen Bericht in der [Leseansicht oder der Bearbeitungsansicht](service-reading-view-and-editing-view.md). Der Drilldown erfordert eine Visualisierung mit einer Hierarchie. 
   
   Eine Hierarchie wird in der Animation unten veranschaulicht.  Die Visualisierung weist eine Hierarchie aus Gebiet, Stadt, Postleitzahl und Ortsname auf. Jedes Gebiet umfasst eine oder mehrere Städte, jede Stadt weist eine oder mehrere Postleitzahlen auf usw. In der Standardeinstellung werden in der Visualisierung nur die Gebietsdaten angezeigt, da *Territory* (Gebiet) in der Liste als erster Eintrag aufgeführt wird.
   
   ![](media/power-bi-visualization-drill-down/power-bi-hierarcy-list.png)
2. Um einen Drilldown zu aktivieren, wählen Sie das Pfeilsymbol in der oberen rechten Ecke der Visualisierung aus. Ist das Symbol dunkel, ist der Drilldown aktiviert. Wenn Sie den Drilldown nicht aktivieren und ein visuelles Element (wie einen Balken oder eine Blase) auswählen, wird ein übergreifender Filtervorgang für die übrigen Diagramme auf der Berichtsseite ausgeführt.    
   
   ![](media/power-bi-visualization-drill-down/power-bi-drill-icon.png)
3. Um einen Drilldown für ***jeweils ein Feld*** auszuführen, klicken Sie auf eines der Elemente in der Visualisierung; klicken Sie z.B. in einem Balkendiagramm auf einen Balken, während Sie in einer Treemap auf eines der *Blätter* klicken. Beachten Sie, dass sich der Titel ändert, wenn Sie einen Drilldown und anschließend einen Drillup ausführen. In dieser Animation wird er von „Total Units This Year by Territory“ (Summe der Einheiten, dieses Jahr nach Gebiet) über „Total Units This Year by Territory and City“ (Summe der Einheiten, dieses Jahr nach Gebiet und Stadt) in „Total Units This Year by Territory, City and PostalCode“ (Summe der Einheiten, dieses Jahr nach Gebiet, Stadt und Postleitzahl) und schließlich in „Total Units This Year by Territory, City, PostalCode, and Name“ (Summe der Einheiten, dieses Jahr nach Gebiet, Stadt, Postleitzahl und Name) geändert. Um anschließend einen Drillup auszuführen, wählen Sie das Symbol **Drillup** ![](media/power-bi-visualization-drill-down/power-bi-drill-icon5.png) in der linken oberen Ecke der Visualisierung aus (siehe unten).
   
   ![](media/power-bi-visualization-drill-down/drill.gif)
4. Um für ***alle Felder gleichzeitig*** einen Drilldown durchzuführen, wählen Sie den doppelten Pfeil in der linken oberen Ecke der Visualisierung aus.
   
   ![](media/power-bi-visualization-drill-down/pbi_drillall.png)
5. Um einen Drilldown bei der Sicherung durchzuführen, wählen Sie den Pfeil nach oben in der oberen linken Ecke der Visualisierung aus.
   
   ![](media/power-bi-visualization-drill-down/pbi_drillup2.png)

## <a name="method-2-for-drill-down"></a>Methode 2 für Drilldowns
Bei dieser Methode wird das Dropdownmenü **Durchsuchen** in der oberen Power BI-Menüleiste verwendet.

1. Öffnen Sie in Power BI einen Bericht in der [Leseansicht oder der Bearbeitungsansicht](service-reading-view-and-editing-view.md). Der Drilldown erfordert eine Visualisierung mit einer Hierarchie. 
   
   Eine Hierarchie wird in der Abbildung unten veranschaulicht.  Die Visualisierung weist eine Hierarchie aus Gebiet, Stadt, Postleitzahl und Ortsname auf. Jedes Gebiet umfasst eine oder mehrere Städte, jede Stadt weist eine oder mehrere Postleitzahlen auf usw. In der Standardeinstellung werden in der Visualisierung nur die Gebietsdaten angezeigt, da *Territory* (Gebiet) in der Liste als erster Eintrag aufgeführt wird.
   
   ![](media/power-bi-visualization-drill-down/power-bi-hierarcy-list.png)
2. Um einen Drilldown zu aktivieren, wählen Sie eine Visualisierung aus, um diese zu aktivieren, und wählen Sie in der oberen Menüleiste von Power BI **Durchsuchen** > **Drilldown** aus. Das Drilldownsymbol in der rechten oberen Ecke der Visualisierung erhält einen schwarzen Hintergrund. ![](media/power-bi-visualization-drill-down/power-bi-drill-icon2.png)  
   
   ![](media/power-bi-visualization-drill-down/power-bi-explore2.png)
3. Sobald die Option aktiviert ist, führen Sie einen Drilldown jeweils für ein Feld aus, indem Sie eines der Treemap-Blätter auswählen. In diesem Beispiel wurde das Gebiet **NC** ausgewählt, um die Gesamtzahl der in diesem Jahr in North Carolina verkauften Einheiten nach Stadt anzuzeigen.
   
   ![](media/power-bi-visualization-drill-down/power-bi-drilldown-1.png)
4. Um einen Drilldown für alle Felder gleichzeitig durchzuführen, wählen Sie **Durchsuchen** > **Nächste Ebene anzeigen** aus.
   
   ![](media/power-bi-visualization-drill-down/power-bi-show-next-level.png)
5. Wählen Sie für einen anschließenden Drillup **Durchsuchen** > **Drillup** aus.
   
   ![](media/power-bi-visualization-drill-down/power-bi-drill-up2.png)
6. Um die zum Erstellen der Visualisierung verwendeten Daten anzuzeigen, wählen Sie **Daten anzeigen**. Die Daten werden in einem Bereich unterhalb der Visualisierung angezeigt. Dieser Bereich bleibt während des Drilldowns in der Visualisierung erhalten. Weitere Informationen finden Sie unter [Anzeigen der zum Erstellen der Visualisierung verwendeten Daten](service-reports-show-data.md).

## <a name="considerations-and-limitations"></a>Überlegungen und Einschränkungen
* Wenn Sie einer Visualisierung ein Datumsfeld hinzufügen, wird dadurch keine Hierarchie erstellt. Möglicherweise wird das Feld „Datum“ nicht tatsächlich als Datum gespeichert. Wenn Sie Eigentümer des Datasets sind, öffnen Sie es in der *Datensicht* in Power BI Desktop, wählen Sie die Spalte mit dem Datum aus, und ändern Sie auf der Registerkarte „Modellierung“ den **Datentyp** in **Datum** oder **Datum/Uhrzeit**. Wenn der Bericht für Sie freigegeben wurde, wenden Sie sich an den Eigentümer, um die Änderung anzufordern.  
  
  ![](media/power-bi-visualization-drill-down/power-bi-change-data-type2.png)

## <a name="next-steps"></a>Nächste Schritte
[Visualisierungen in Power BI-Berichten](power-bi-report-visualizations.md)

[Power BI-Berichte](service-reports.md)

[Power BI – Grundkonzepte](service-basic-concepts.md)

Weitere Fragen? [Wenden Sie sich an die Power BI-Community](http://community.powerbi.com/)

