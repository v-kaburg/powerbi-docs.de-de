---
title: Ringdiagramme in Power BI (Tutorial)
description: 'Lernprogramm: Ringdiagramme in Power BI'
services: powerbi
documentationcenter: 
author: mihart
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
ms.date: 09/27/2017
ms.author: mihart
ms.openlocfilehash: 2f428095eb57c5358770f1d6d8572316d2b84c37
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2017
---
# <a name="doughnut-charts-in-power-bi-tutorial"></a>Ringdiagramme in Power BI (Tutorial)
Ein Ringdiagramm ähnelt einem Kreisdiagramm insofern, als dass es die Beziehung von Teilen zu einem Ganzen zeigt. Der einzige Unterschied ist, dass die Mitte leer und Platz für eine Beschriftung oder ein Symbol bleibt.

## <a name="create-a-doughnut-chart"></a>Erstellen eines Ringdiagramms
Melden Sie sich bei Power BI an, und wählen Sie **Daten abrufen** \> **Beispiele** \> **Analysebeispiel für Einzelhandel** \> **Verbinden** aus. 

1. Wählen Sie im Dashboard die Kachel **Läden gesamt** aus, um den Bericht „Analysebeispiel für Einzelhandel“ zu öffnen.
2. Wählen Sie **Bericht bearbeiten** , um den Bericht in der Bearbeitungsansicht zu öffnen.
3. [Fügen Sie eine neue Seite zu Ihrem Bericht hinzu](power-bi-report-add-page.md).
4. Erstellen Sie ein Ringdiagramm, das den Absatz des laufenden Jahres nach Kategorie anzeigt.
   
   * Wählen Sie im Bereich **Felder** die Option **Verkäufe**\>**Verkäufe im letzten Jahr** aus.
   * Konvertieren Sie das Diagramm in ein Ringdiagramm. Wenn sich die Kategorie „Verkäufe im letzten Jahr“ nicht im Bereich **Werte** befindet, ziehen Sie diese dorthin.
     
       ![](media/power-bi-visualization-doughnut-charts/convertdonut.png)
   * Wählen Sie **Element** \> **Kategorie** aus, um die Kategorie dem Bereich **Legende** hinzuzufügen. 
     
       ![](media/power-bi-visualization-doughnut-charts/doughnuttutorial.png)

## <a name="considerations-and-troubleshooting"></a>Zu beachtende Aspekte und Problembehandlung
* Die Summe der Ringdiagrammwerte muss insgesamt 100 % betragen.
* Zu viele Kategorien erschweren das Lesen und Interpretieren der Werte.
* Ringdiagramme werden am besten zum Vergleichen eines bestimmten Bereichs gegenüber dem Ganzen verwendet, anstatt einzelne Abschnitte miteinander zu vergleichen. 

## <a name="next-steps"></a>Nächste Schritte
[Berichte in Power BI](service-reports.md)

[Visualisierungstypen in Power BI](power-bi-visualization-types-for-reports-and-q-and-a.md)

[Visualisierungen in Power BI-Berichten](power-bi-report-visualizations.md)

[Power BI – Grundkonzepte](service-basic-concepts.md)

Weitere Fragen? [Wenden Sie sich an die Power BI-Community](http://community.powerbi.com/)

