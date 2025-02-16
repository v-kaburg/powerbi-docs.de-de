---
title: Wasserfalldiagramme in Power BI
description: Wasserfalldiagramme in Power BI
author: mihart
manager: kvivek
ms.reviewer: ''
featuredvideoid: maTzOJSRB3g
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 09/27/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 3835bedc1b4ab2df87abf4704ef338ff7f4abc5d
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2019
ms.locfileid: "61393000"
---
# <a name="waterfall-charts-in-power-bi"></a>Wasserfalldiagramme in Power BI
Wasserfalldiagramme zeigen eine laufende Summe an, während Werte hinzugefügt oder entfernt werden. Sie zeigen, wie ein anfänglicher Wert (z. B. das Nettoeinkommen) durch eine Reihe von positiven und negativen Änderungen beeinflusst wird.

Die Säulen sind farbkodiert, damit Sie Zu- und Abnahmen der Werte schnell erkennen können. Die Säulen für den Anfangs- und den Endwert [gehen häufig von der horizontalen Achse aus](https://support.office.com/article/Create-a-waterfall-chart-in-Office-2016-for-Windows-8de1ece4-ff21-4d37-acd7-546f5527f185#BKMK_Float "gehen häufig von der horizontalen Achse aus"), während die Zwischenwerte unverankerte Säulen sind. Aufgrund dieses Aussehens werden Wasserfalldiagramme auch als „Brückendiagramme“ bezeichnet.

<iframe width="560" height="315" src="https://www.youtube.com/embed/qKRZPBnaUXM" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>

## <a name="when-to-use-a-waterfall-chart"></a>Einsatz von Wasserfalldiagrammen
Wasserfalldiagramme sind gut für folgende Zwecke geeignet:

* Bei Änderungen der Zahlen im Laufe der Zeit oder über andere Kategorien hinweg
* Zum Überwachen der wichtigsten Änderungen am Gesamtwert
* Zum Anzeigen des jährlichen Gewinns Ihres Unternehmens mithilfe einer Darstellung verschiedener Umsatzquellen und letztendlich des Gesamtgewinns (oder -verlusts)
* Zum Illustrieren der Mitarbeiterzahl Ihres Unternehmens zu Jahresbeginn und -ende
* Zum Visualisieren Ihrer Einnahmen und Ausgaben pro Monat und des laufenden Kontostands für Ihr Konto 

## <a name="create-a-waterfall-chart"></a>Erstellen eines Wasserfalldiagramms
Sie erstellen ein Wasserfalldiagramm, mit dem Abweichungen beim Umsatz (geschätzter Umsatz im Vergleich zu tatsächlichen Verkaufszahlen) nach Monat dargestellt werden. Melden Sie sich bei Power BI an, und wählen Sie **Daten abrufen \> Beispiele \>Analysebeispiel für Einzelhandel**. 

1. Wählen Sie die Registerkarte **Datasets** aus, und scrollen Sie zum neuen Dataset „Analysebeispiel für Einzelhandel“.  Wählen Sie das Symbol **Bericht erstellen** aus, um das Dataset in der Berichtsbearbeitungsansicht zu öffnen. 
   
    ![Hervorgehobene Registerkarte „Datasets“](media/power-bi-visualization-waterfall-charts/power-bi-waterfall-report.png)
2. Wählen Sie im Bereich **Felder** die Option **Verkäufe \> Gesamtabweichung Verkäufe**. 
3. Wandeln Sie das Diagramm in ein **Wasserfalldiagramm**um. Wenn sich **Gesamtabweichung Verkäufe** nicht im Bereich der **Y-Achse** befindet, ziehen Sie es dorthin.
   
    ![Visualisierungsvorlagen](media/power-bi-visualization-waterfall-charts/convertwaterfall.png)
4. Wählen Sie **Zeit** \> **Geschäftsmonat** aus, um den Wert dem Bereich **Kategorie** hinzuzufügen. 
   
    ![Wasserfalldiagramm](media/power-bi-visualization-waterfall-charts/power-bi-waterfall.png)
5. Sortieren Sie das Wasserfalldiagramm chronologisch. Wählen Sie rechts oben im Diagramm die Auslassungspunkte (...) und dann **FiscalMonth** aus.
   
    ![Auswählen von Sortieren nach > FiscalMonth](media/power-bi-visualization-waterfall-charts/power-bi-sort-by.png)
   
    ![Ergebnis der neuen aufsteigenden Sortierung](media/power-bi-visualization-waterfall-charts/power-bi-waterfall-sorted.png)
6. Analysieren Sie die Informationen genauer, um zu ermitteln, was von Monat zu Monat am stärksten zu den Änderungen beiträgt. Ziehen Sie **Store** > **Gebiet** in den Bucket **Aufschlüsselung**.
   
    ![Zeigt Store im Bucket „Aufschlüsselung“ an](media/power-bi-visualization-waterfall-charts/power-bi-waterfall-breakdown.png)
7. Standardmäßig fügt Power BI die wichtigsten fünf Faktoren für die Steigerungen oder Verringerungen pro Monat hinzu. Hier sind aber nur die ersten beiden Faktoren von Interesse.  Wählen Sie im Formatierungsbereich **Aufschlüsselung** aus, und legen Sie **Maximum** auf 2 fest.
   
    ![Formatierung > Aufschlüsselung](media/power-bi-visualization-waterfall-charts/power-bi-waterfall-breakdown-maximum.png)
   
    Ein kurzer Blick zeigt, dass die Gebiete „Ohio“ und „Pennsylvania“ im Wasserfalldiagramm den größten Anteil an positiven und negativen Änderungen haben. 
   
    ![Wasserfalldiagramm](media/power-bi-visualization-waterfall-charts/power-bi-waterfall-axis.png)
8. Dies ist ein bemerkenswertes Ergebnis. Haben Ohio und Pennsylvania so starken Einfluss, weil der Umsatz in diesen beiden Gebieten sehr viel höher als in den anderen Gebieten ist?  Das können wir nachprüfen. Erstellen Sie eine Karte, mit der der Umsatz dieses Jahres nach Umsatzwert und der des letzten Jahres nach Gebiet analysiert wird.  
   
    ![Kartenausschnitt für Pennsylvania und Ohio](media/power-bi-visualization-waterfall-charts/power-bi-map.png)
   
    Diese Karte unterstützt unsere Theorie.  Sie zeigt, dass diese beiden Gebiete im letzten Jahr (Blasengröße) und in diesem Jahr (Blasenschattierung) die höchsten Umsätze erzielt haben.

## <a name="highlighting-and-cross-filtering"></a>Hervorheben und Kreuzfiltern
Informationen zur Verwendung des Filterbereichs finden Sie unter [Hinzufügen eines Filters zu einem Bericht in Power BI](../power-bi-report-add-filter.md).

Das Markieren einer Säule in einem Wasserfalldiagramm ermöglicht ein Kreuzfiltern anderer Visualisierungen auf der Berichtsseite und umgekehrt. Die Säule mit dem Gesamtwert löst jedoch keine Markierung aus und reagiert nicht auf Kreuzfiltern.

## <a name="next-steps"></a>Nächste Schritte

[Visualinteraktionen](../service-reports-visual-interactions.md)

[Visualisierungstypen in Power BI](power-bi-visualization-types-for-reports-and-q-and-a.md)