---
title: "Daten und Datensätze in Power BI Desktop-Visualisierungen genauer betrachten"
description: "Verwenden der Power BI Desktop-Funktionen „Daten anzeigen“ und „Datensätze anzeigen“ für Drilldowns"
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
ms.date: 10/09/2017
ms.author: davidi
ms.openlocfilehash: c43ec48d1bd34a5df2578c6cc117dd3e3bbdb64f
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2017
---
# <a name="use-see-data-and-see-records-in-power-bi-desktop"></a>Verwenden von „Daten anzeigen“ und „Datensätze anzeigen“ in Power BI Desktop
In **Power BI Desktop** können Sie beliebige Visualisierungen genauer betrachten (Drilldown ins Detail) und die Textdarstellung der Daten oder einzelner Datenelemente einer bestimmten Visualisierung anzeigen. Diese Features werden auch als *Durchklick*, *Drillthrough* oder *Drillthrough zu den Details* bezeichnet.

Mit **Datensätze anzeigen** können Sie die zugrunde liegenden Zeilen eines bestimmten Datenelements in einer Visualisierung anzeigen, mit **Daten anzeigen** die Textdarstellung der Werte einer Visualisierung. Bei der Verwendung von **Daten anzeigen** und **Datensätze anzeigen** gelten einige Einschränkungen, die am Ende dieses Artikels genannt werden.

![](media/desktop-see-data-see-records/see-data-see-records_1.png)

## <a name="using-see-data-in-power-bi-desktop"></a>Verwenden von „Daten anzeigen“ in Power BI Desktop
Die Schaltfläche **Daten anzeigen** befindet sich auf der Registerkarte **Daten/Drillvorgang** im Abschnitt **Visuelle Tools** des Menübands.

![](media/desktop-see-data-see-records/see-data-see-records_2.png)

Sie können auch **Daten anzeigen**, indem Sie auf eine Visualisierung klicken und im nun angezeigten Menü **Daten anzeigen** wählen.

![](media/desktop-see-data-see-records/see-data-see-records_3.png)

> [!NOTE]
> Sie müssen auf einen Datenpunkt im Visual zeigen, damit das Kontextmenü verfügbar ist.
> 
> 

Bei der Option **Daten anzeigen** werden in **Power BI Desktop** die Visualisierung und die Daten, die Sie ausgewählt haben, in den Fokus genommen: Die Visualisierung und die Textdarstellung der Daten nehmen den gesamten Zeichenbereich ein. Die Visualisierung wird in der oberen Hälfte, die Daten werden in der unteren Hälfte des Zeichenbereichs angezeigt (siehe die folgende Abbildung). *Horizontale* Ansicht:

![](media/desktop-see-data-see-records/see-data-see-records_4.png)

Mit dem Symbol in der oberen rechten Ecke können Sie auch zu einer *vertikalen Ansicht* (und zurück zur *horizontalen Ansicht*) wechseln.

![](media/desktop-see-data-see-records/see-data-see-records_5.png)

Um zum Bericht zurückzukehren, wählen Sie in der oberen linken Ecke des Zeichenbereichs **< Zurück zum Bericht**.

![](media/desktop-see-data-see-records/see-data-see-records_6.png)

## <a name="using-see-records-in-power-bi-desktop"></a>Verwenden von „Datensätze anzeigen“ in Power BI Desktop
Sie können den Fokus auch auf ein Datenelement einer Visualisierung legen und die zugrunde liegenden Daten genauer betrachten. Bei ausgewählter Visualisierung bestehen zwei Möglichkeiten, die Option **Datensätze anzeigen** zu verwenden: Entweder können Sie den Schalter **Datensätze anzeigen** im Menüband **Daten/Drillvorgang** aktivieren und dann auf ein Datenelement klicken, oder Sie können mit der rechten Maustaste auf ein Datenelement klicken und **Datensätze anzeigen** im Kontextmenü wählen.

![](media/desktop-see-data-see-records/see-data-see-records_7.png)

> [!NOTE]
> Wenn das ausgewählte Visual die Option **Datensätze anzeigen** nicht unterstützt, ist die Schaltfläche auf dem Menüband abgeblendet.
> 
> 

Sobald die Option **Datensätze anzeigen** aktiviert ist, wird der Bildschirm in **Power BI Desktop** auf das ausgewählte Datenelement fokussiert, und im Zeichenbereich werden die Daten für dieses Element angezeigt (siehe die folgende Abbildung).

![](media/desktop-see-data-see-records/see-data-see-records_8.png)

Mit der Schaltfläche **Zurück zum Bericht** in der oberen linken Ecke des Zeichenbereichs können Sie zum Bericht zurückkehren.

## <a name="limitations"></a>Einschränkungen
Bei der Verwendung der Optionen **Daten anzeigen** und **Datensätze anzeigen** sind einige Einschränkungen zu beachten:

* Die folgenden Visualisierungstypen werden unterstützt:
  * **Balken**
  * **Spalte**
  * **Zuordnung**
  * **Treemap-Diagramme**
  * **Flächenkartogramm**
  * **Kreisdiagramm**
  * **Ringdiagramm**
  * **Trichterdiagramm**
* Wenn die Visualisierung ein berechnetes Measure beinhaltet, können Sie **Datensätze anzeigen** nicht verwenden.
* Sie können **Datensätze anzeigen** nicht verwenden, wenn Sie mit einem aktiven mehrdimensionalen Modell (MD-Modell) verbunden sind.

## <a name="next-steps"></a>Nächste Schritte
In **Power BI Desktop** stehen verschiedene Features für das Formatieren von Berichten und die Datenverwaltung zur Verfügung. Die folgenden Ressourcen enthalten einige Beispiele:

* [Verwenden von Gruppierung und Diskretisierung in Power BI Desktop](desktop-grouping-and-binning.md)
* [Verwenden von Gitternetzlinien, der Option „Am Raster ausrichten“, der Z-Reihenfolge, Ausrichtung und Verteilung in Power BI Desktop-Berichten](desktop-gridlines-snap-to-grid.md)

