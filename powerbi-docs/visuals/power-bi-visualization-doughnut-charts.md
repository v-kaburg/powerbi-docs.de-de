---
title: Ringdiagramme in Power BI
description: Ringdiagramme in Power BI
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 06/11/2019
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: cd78fc1411f1eb4e9148bb12ddf6d9805954cfd7
ms.sourcegitcommit: 797bb40f691384cb1b23dd08c1634f672b4a82bb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/12/2019
ms.locfileid: "66839710"
---
# <a name="doughnut-charts-in-power-bi"></a>Ringdiagramme in Power BI
Ein Ringdiagramm ähnelt einem Kreisdiagramm insofern, als dass es die Beziehung von Teilen zu einem Ganzen zeigt. Der einzige Unterschied ist, dass die Mitte leer und Platz für eine Beschriftung oder ein Symbol bleibt.

## <a name="create-a-doughnut-chart"></a>Erstellen eines Ringdiagramms
Mit dieser Anleitung erstellen Sie anhand des Analysebeispiels für den Einzelhandel ein Ringdiagramm, das den Absatz des laufenden Jahres nach Kategorie anzeigt. Wenn Sie diese Schritte selbst ausführen möchten, [laden Sie das Beispiel](../sample-datasets.md) für den Power BI-Dienst oder Power BI Desktop herunter.

1. Beginnen Sie auf einer leeren Berichtsseite. Wenn Sie den Power BI-Dienst verwenden, achten Sie darauf, den Bericht in der [Bearbeitungsansicht](../service-interact-with-a-report-in-editing-view.md) zu öffnen.

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


