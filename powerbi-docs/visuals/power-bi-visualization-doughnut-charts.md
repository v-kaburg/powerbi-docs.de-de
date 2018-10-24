---
title: Ringdiagramme in Power BI
description: Ringdiagramme in Power BI
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 09/24/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: ab292964bb1b6b1f4218d41c46eb2c28c82a034c
ms.sourcegitcommit: ce8332a71d4d205a1f005b703da4a390d79c98b6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/27/2018
ms.locfileid: "47416749"
---
# <a name="doughnut-charts-in-power-bi"></a>Ringdiagramme in Power BI
Ein Ringdiagramm ähnelt einem Kreisdiagramm insofern, als dass es die Beziehung von Teilen zu einem Ganzen zeigt. Der einzige Unterschied ist, dass die Mitte leer und Platz für eine Beschriftung oder ein Symbol bleibt.

## <a name="create-a-doughnut-chart"></a>Erstellen eines Ringdiagramms
Mit dieser Anleitung erstellen Sie anhand des Analysebeispiels für den Einzelhandel ein Ringdiagramm, das den Absatz des laufenden Jahres nach Kategorie anzeigt. Wenn Sie diese Schritte selbst ausführen möchten, [laden Sie das Beispiel](../sample-datasets.md) für den Power BI-Dienst oder Power BI Desktop herunter.

1. Beginnen Sie auf einer [leeren Berichtsseite](../power-bi-report-add-page.md). Wenn Sie den Power BI-Dienst verwenden, achten Sie darauf, den Bericht in der [Bearbeitungsansicht](../service-interact-with-a-report-in-editing-view.md) zu öffnen.

2. Wählen Sie im Bereich „Felder“ die Option **Verkäufe** \> **Verkäufe im letzten Jahr** aus.  
   
3. Wählen Sie im Bereich „Visualisierungen“ das Symbol für ein Ringdiagramm ![Symbol für Ringdiagramm](media/power-bi-visualization-doughnut-charts/power-bi-icon.png) aus, um das Balkendiagramm in ein Ringdiagramm zu konvertieren. Wenn sich die Kategorie **Verkäufe im letzten Jahr** nicht im Bereich **Werte** befindet, ziehen Sie diese dorthin.
     
   ![Bereich „Visualisierung“ mit ausgewähltem Ringdiagramm](media/power-bi-visualization-doughnut-charts/power-bi-doughnut-chart.png)

4. Wählen Sie **Element** \> **Kategorie** aus, um die Kategorie dem Bereich **Legende** hinzuzufügen. 
     
    ![Ringdiagramm neben Bereich „Felder“](media/power-bi-visualization-doughnut-charts/power-bi-doughnut-done.png)

5. Optional können Sie [die Textgröße und -farbe des Diagramms anpassen](power-bi-visualization-customize-title-background-and-legend.md). 

## <a name="considerations-and-troubleshooting"></a>Zu beachtende Aspekte und Problembehandlung
* Die Summe der Ringdiagrammwerte muss insgesamt 100 % betragen.
* Zu viele Kategorien erschweren das Lesen und Interpretieren der Werte.
* Ringdiagramme werden am besten zum Vergleichen eines bestimmten Bereichs gegenüber dem Ganzen verwendet, anstatt einzelne Abschnitte miteinander zu vergleichen. 

## <a name="next-steps"></a>Nächste Schritte
[Trichterdiagramme in Power BI](power-bi-visualization-funnel-charts.md)

[Visualisierungstypen in Power BI](power-bi-visualization-types-for-reports-and-q-and-a.md)


