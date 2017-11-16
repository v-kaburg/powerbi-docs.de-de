---
title: Slicer in Power BI (Tutorial)
description: 'Lernprogramm: Slicer in Power BI'
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: zIZPA0UrJyA
qualityfocus: monitoring
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 05/30/2017
ms.author: mihart
ms.openlocfilehash: b6ce0c396f4a189489b97fe5cd86ab5cd8dbcc35
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2017
---
# <a name="slicers-in-power-bi-service-tutorial"></a>Slicer im Power BI-Dienst (Tutorial)
Die Vertriebsleiterin möchte eine Reihe von Metriken, und zwar für die gesamte Abteilung und für jeden einzelnen Bezirksleiter, betrachten können. Sie kann für jeden Bezirksleiter eine einzelne Berichtsseite erstellen oder einen Slicer verwenden. Ein Slicer beschränkt den Teil der Datasets, die in den anderen Visualisierungen auf der Seite angezeigt werden.  Slicer stellen eine zusätzliche Möglichkeit zum Filtern dar.

![](media/power-bi-visualization-slicers/slicer2.gif)

## <a name="when-to-use-a-slicer"></a>Verwenden von Slicern
Slicer sind in den folgenden Situationen eine gute Wahl:

* Anzeigen häufig verwendeter oder wichtiger Filter für den einfacheren Zugriff im Zeichenbereich des Berichts.
* Einfacheres Anzeigen des aktuellen Filterzustands, ohne eine Dropdownliste zum Ermitteln der Filterdetails öffnen zu müssen.
* Wenn Sie nicht benötigte Spalten ausblenden möchten, die Sie jedoch weiterhin zum Filtern verwenden müssen, können Sie so schlankere und klarere Tabellen erzeugen.
* Zum Erstellen prägnanterer Berichte – da Slicer bewegliche Objekte sind, können Sie sie neben dem interessanten Teil des Berichts platzieren, um den Blick darauf zu lenken.

## <a name="create-a-slicer"></a>Erstellen von Slicern
<iframe width="560" height="315" src="https://www.youtube.com/embed/zIZPA0UrJyA" frameborder="0" allowfullscreen></iframe>


1. Öffnen Sie das [Analysebeispiel für Einzelhandel](sample-retail-analysis.md) in der [Bearbeitungsansicht](service-interact-with-a-report-in-editing-view.md), und [fügen Sie eine neue Berichtsseite hinzu](power-bi-report-add-page.md).
2. Wählen Sie im Bereich „Felder“ die Option **Region > Regionalmanager** aus.
   
    ![](media/power-bi-visualization-slicers/pbi_slicer_chartfirst.png)
3. Konvertieren Sie die Visualisierung in einen Slicer. Wählen Sie im Bereich „Visualisierungen“ das Slicersymbol aus.
   
    ![](media/power-bi-visualization-slicers/pbi_slicer_select.png)

## <a name="format-the-slicer"></a>Formatieren von Slicern
1. Wählen Sie bei ausgewähltem Slicer im Bereich „Visualisierungen“ das Farbrollersymbol ![](media/power-bi-visualization-slicers/power-bi-paintroller.png) aus, um die Formatierungsoptionen anzuzeigen.
2. Wählen Sie **Allgemein > Konturfarbe** und dann „Dunkelblau“ aus, und ändern Sie die **Stärke** auf **6**.
   
    ![](media/power-bi-visualization-slicers/pbi_slicer_outline2.png)
3. Unter **Auswahlsteuerelemente**ist standardmäßig **Alles auswählen** auf **Aus** und **Einfachauswahl** auf **Ein**eingestellt. Dies bedeutet, dass Sie die STRG-Taste verwenden müssen, um mehr als einen Namen gleichzeitig auszuwählen. Ändern Sie **Alles auswählen** in **Ein** und **Einfachauswahl** in **Aus**.
   
    ![](media/power-bi-visualization-slicers/pbi_slicer_selectioncontrols2.png)
   
   * Beachten Sie, dass der Slicer nun am Anfang der Liste die Option **Alles auswählen** bereitstellt. Sie können **Alles auswählen** umschalten, um alle Namen oder keinen der Namen auszuwählen.
   * Sie können nun auch mehr als einen Namen auswählen, ohne die STRG-Taste zu verwenden.
4. Erhöhen Sie unter **Elemente**die Textgröße auf 14 Punkte.  Wir möchten sicherstellen, dass unsere Kollegen diesen Slicer auch beachten.
5. Legen Sie zum Schluss die **Schriftfarbe** auf Dunkelrot fest.  Damit können die markierten Namen in unserem Slicer besser von den nicht markierten Namen unterschieden werden.
   
    ![](media/power-bi-visualization-slicers/pbi_slicer_font2.png)
6. Untersuchen Sie die anderen für Slicer verfügbaren Optionen.

## <a name="use-the-slicer-in-a-report"></a>Verwenden des Slicers in einem Bericht
1. Fügen Sie der Berichtsseite weitere Visualisierungen hinzu, oder öffnen Sie den [Bericht mit dem Analysebeispiel für den Einzelhandel](sample-retail-analysis.md), und wählen Sie die Registerkarte **District Monthly Sales** aus.
   
    ![](media/power-bi-visualization-slicers/power-bi-retail-sample.png)
2. Unterteilen Sie die Berichtsseite für Carlos. Beachten Sie, wie die anderen Visualisierungen gemäß dieser Auswahl aktualisiert werden.
   
    ![](media/power-bi-visualization-slicers/slicer2.gif)
3. Sortieren Sie den Slicer alphabetisch nach dem Nachnamen des Regionalmanagers.  Wählen Sie die Auslassungspunkte (...) in der oberen rechten Ecke des Slicers, und wählen Sie **Regionalmanager**aus.
   
    ![](media/power-bi-visualization-slicers/pbi_slicer_sort2.png)
   
    ![](media/power-bi-visualization-slicers/pbi_slicer_sorted.png)

## <a name="control-what-effect-the-slicer-has-on-other-visuals-on-the-page"></a>Steuern der Auswirkungen des Slicers auf andere Visualisierungen auf der Seite
Soll der Slicer nur einige der Visualisierungen auf der Berichtsseite filtern?  Dies können Sie mit dem Steuerelement **Visuelle Interaktionen** einrichten.

**HINWEIS**: Wenn **Visuelle Interaktionen** nicht angezeigt wird, suchen Sie stattdessen nach dem entsprechenden Symbol ![](media/power-bi-visualization-slicers/power-bi-slicer-visual-interactions.png). Wenn beides nicht angezeigt wird, stellen Sie sicher, dass die [Bearbeitungsansicht](service-reading-view-and-editing-view.md) für Berichte geöffnet ist.

1. Wählen Sie den Slicer aus, um ihn zu aktivieren, und wählen Sie auf der Menüleiste **Visuelle Interaktionen**.
   
    ![](media/power-bi-visualization-slicers/pbi-slicer-interactions.png)
2. Über allen anderen Visualisierungen auf der Seite werden Filtersteuerelemente angezeigt. Wenn der Slicer eine Visualisierung filtern soll, wählen Sie das Symbol **Filter** aus.  Wenn der Slicer keine Auswirkungen auf die Visualisierung haben soll, wählen Sie das Symbol **Keine** aus.
   
    ![](media/power-bi-visualization-slicers/filter-controls.png)

Weitere Informationen finden Sie unter [Interaktionen mit Visualisierungen in einem Power BI-Bericht](service-reports-visual-interactions.md).

## <a name="considerations-and-troubleshooting-slicers-in-power-bi"></a>Zu beachtende Aspekte und Problembehandlung für Slicer in Power BI
Für die Verwendung von Slicern in Power BI gelten die folgenden Einschränkungen:

1. Slicer unterstützen keine Eingabefelder.
2. Ein einzelner Slicer kann nicht für einen gesamten Bericht verwendet werden. Ein Slicer wirkt sich nur auf die aktuelle Seite aus.
3. Slicer können nicht an ein Dashboard angeheftet werden.
4. Drilldown wird für Slicer nicht unterstützt.    
5. Slicer unterstützen keine Filter auf Visualisierungsebene.

Haben Sie Verbesserungsvorschläge für Power BI? [Vorschlag einreichen](https://ideas.powerbi.com/forums/265200-power-bi-ideas)

## <a name="next-steps"></a>Nächste Schritte
 [Hinzufügen einer Visualisierung zu einem Bericht](power-bi-report-add-visualizations-i.md)

 [Visualisierungstypen in Power BI](power-bi-visualization-types-for-reports-and-q-and-a.md)

 [Power BI – Grundkonzepte](service-basic-concepts.md)

[Jetzt kostenlos testen](https://powerbi.com/)

Weitere Fragen? [Wenden Sie sich an die Power BI-Community](http://community.powerbi.com/)

