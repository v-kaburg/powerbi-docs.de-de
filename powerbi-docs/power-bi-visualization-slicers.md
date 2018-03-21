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
ms.date: 03/05/2018
ms.author: v-thepet
LocalizationGroup: Visualizations
ms.openlocfilehash: cfa4c0f17c67a036b7d01744da1b5247345c493a
ms.sourcegitcommit: 4217430c3419046c3a90819c34f133ec7905b6e7
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2018
---
# <a name="slicers-in-power-bi-tutorial"></a>Slicer in Power BI (Tutorial)
Eine Vertriebsleiterin möchte mehrere Metriken betrachten können, und zwar für die gesamte Abteilung und für jeden einzelnen Bezirksleiter. Sie könnte für jeden Bezirksleiter einen einzelnen Bericht erstellen oder einen Slicer verwenden. Ein Slicer beschränkt den Teil des Datasets, das in anderen Visualisierungen in einem Bericht angezeigt wird. Slicer stellen eine zusätzliche Möglichkeit zum Filtern dar.

In diesem Tutorial wird anhand des [Analysebeispiels für den Einzelhandel](sample-retail-analysis.md) die Erstellung und Formatierung eines Slicers sowie die Verwendung des Slicers zum Filtern eines Berichts erläutert. Viel Vergnügen beim Entdecken der Möglichkeiten zum Formatieren und Verwenden von Slicern! 

![Datenschnitt](media/power-bi-visualization-slicers/slicer2.gif)

## <a name="when-to-use-a-slicer"></a>Verwenden von Slicern
Slicer sind für folgende Zwecke gut geeignet:

* Anzeigen häufig verwendeter oder wichtiger Filter für den einfacheren Zugriff im Zeichenbereich des Berichts.
* Einfacheres Anzeigen des aktuellen gefilterten Zustands, ohne dass das Öffnen einer Dropdownliste erforderlich ist. 
* Filtern nach Spalten, die nicht benötigt und in den Datentabellen ausgeblendet werden.
* Erstellen fokussierterer Berichte durch das Einfügen von Slicern neben wichtigen visuellen Elementen.

Power BI-Slicer weisen die folgenden Einschränkungen auf:

- Slicer unterstützen keine Eingabefelder.
- Slicer können nicht an ein Dashboard angeheftet werden.
- Drilldown wird für Slicer nicht unterstützt.
- Slicer unterstützen keine Filter auf visueller Ebene.

## <a name="create-a-slicer"></a>Erstellen von Slicern

In diesem Tutorial wird ein Slicer für Listen verwendet. Numerische Datentypen und Datentypen für Datum/Uhrzeit können über Slicer für Bereiche verfügen. Weitere Informationen zum Erstellen und Verwenden von Slicern für Bereiche finden Sie unter [Verwenden der Funktion „Slicer für numerischen Bereich“ in Power BI Desktop](desktop-slicer-numeric-range.md) oder im folgenden Video.
<iframe width="560" height="315" src="https://www.youtube.com/embed/zIZPA0UrJyA" frameborder="0" allowfullscreen></iframe>

1. Öffnen Sie in Power BI Desktop oder im Power BI-Dienst das [Analysebeispiel für Einzelhandel](sample-retail-analysis.md) in der [Bearbeitungsansicht](service-interact-with-a-report-in-editing-view.md) und [fügen Sie eine neue Berichtsseite hinzu](power-bi-report-add-page.md).
2. Wählen Sie aus dem Bereich „Felder“ unter „Bezirk“ die Option **Bezirksleiter** aus, um eine neue Visualisierung zu erstellen.
    
    ![Neues Diagramm](media/power-bi-visualization-slicers/1-new-vis.png)
    
3. Wählen Sie das Symbol **Slicer** ![Symbol „Slicer“](media/power-bi-visualization-slicers/slicer-icon.png) im Bereich „Visualisierungen“ aus, um die neue Visualisierung für einen Slicer zu erstellen. 
    
    ![Konvertieren in einen Slicer](media/power-bi-visualization-slicers/2-slicer.png)

Sie können das Symbol „Slicer“ auch für die Erstellung eines neuen Slicers auswählen und anschließend ein Datenfeld für das Feld auswählen bzw. es in das Feld ziehen, um dieses zu füllen.

>[!TIP]
>Sie können Slicerelemente für Listen nach Datenwerten sortieren. Wenn Sie Slicerelemente in umgekehrter alphabetischer Reihenfolge sortieren möchten, wählen Sie die Ellipsen (...) in der rechten oberen Ecke des Slicers und anschließend **Sort by District Manager** (Nach Bezirksleiter sortieren) aus. Standardmäßig ist die aufsteigende alphabetische Reihenfolge festgelegt, die Einstellung wechselt jedoch zwischen der aufsteigenden und der absteigenden Reihenfolge. 

## <a name="format-the-slicer"></a>Formatieren von Slicern
Wenden Sie visuelle Formatierung auf den Slicer für den Bezirksmanager an.
1. Wählen Sie bei ausgewähltem Slicer im Bereich „Visualisierungen“ das Formatierungssymbol ![](media/power-bi-visualization-slicers/power-bi-paintroller.png) aus, um die Formatierungssteuerungen anzuzeigen. 
    
    ![Formatierung](media/power-bi-visualization-slicers/3-format.png)
    
2. Klicken Sie neben den einzelnen anzuzeigenden Kategorien auf die Dropdown-Pfeile und bearbeiten Sie die Optionen. 

### <a name="general-options"></a>Allgemeine Optionen
1. Wählen Sie unter **Konturfarbe** die Farbe Rot aus, und ändern Sie **Konturstärke** in „2“. Wenn diese Option aktiviert ist, werden die Farbe und Stärke von Konturen und Unterstreichungen dadurch festgelegt. 
2. Bei der Option „Ausrichtung“ ist „Vertikal“ die Standardeinstellung. Sie erstellt einen Slicer für eine vertikale Liste mit Auswahlfeldern vor den Elementen. Wählen Sie **Horizontal** aus, um einen Slicer mit horizontal angeordneten Elementen zu erstellen. Durch eine horizontale Ausrichtung können je nach Größe und Form des Slicers sowie je nach Elementformatierung verschiedene Anordnungen von Text, Schaltflächen oder Kacheln erzeugt werden. 
    
    ![Horizontal](media/power-bi-visualization-slicers/4-horizontal.png)
    
3. Aktivieren Sie das Layout **Dynamisch**. Dadurch werden Größe und Anordnung der horizontalen Slicerelemente geändert und an die Größe und Form des Slicers angepasst. Bei einer sehr kleinen Größe wird der Slicer ein Filtersymbol. 
    
    ![Dynamisch](media/power-bi-visualization-slicers/5-responsive.png)
    
    >[!NOTE]
    >Durch dynamische Layoutänderungen können bestimmte, von Ihnen festgelegte Formatierungen von Überschriften und Elementen überschrieben werden. 
    
4. Legen Sie die Position und Größe des Slicers unter **X-Position**, **Y-Position**, **Breite** und **Höhe** mit numerischer Genauigkeit fest, oder verschieben Sie den Slicer direkt im Zeichenbereich und ändern die Größe, um unterschiedliche Größen und Anordnungen wie z.B. eine horizontale Zeile mit Schaltflächen zu erzeugen. 

    ![Horizontale Schaltflächen](media/power-bi-visualization-slicers/6-buttons.png)

Weitere Informationen zur horizontalen Ausrichtung und dynamischen Formatierung finden Sie unter [Erstellen eines dynamischen Slicers mit anpassbarer Größe in Power BI](power-bi-slicer-filter-responsive.md).

### <a name="selection-controls-options"></a>Optionen für Auswahlsteuerelemente
1. Die Anzeige von „Alles auswählen“ ist standardmäßig deaktiviert. Sie können sie aktivieren (**On**), um das Element „Alles auswählen“ zum Slicer hinzuzufügen, über das beim Umschalten alle Elemente ausgewählt oder abgewählt werden können. Wenn alle Elemente ausgewählt sind, werden sie durch das Klicken auf ein Element wieder abgewählt, wodurch ein Filter vom Typ „is-not“ (Ist nicht) zugelassen wird. 
    
    ![Alles auswählen](media/power-bi-visualization-slicers/7-select-all.png)
    
2. Die Einfachauswahl ist standardmäßig eingeschaltet („On“). Durch Klicken auf die einzelnen Elemente werden diese ausgewählt. Wenn Sie die STRG-Taste während des Klickens gedrückt halten, werden mehrere Elemente ausgewählt. Schalten Sie die Einfachauswahl aus (**Off**), damit mehrere Elemente ausgewählt werden können, ohne dass die STRG-Taste gedrückt werden muss. Durch erneutes Klicken auf die einzelnen Elemente werden diese wieder abgewählt. 

### <a name="header-options"></a>Headeroptionen
Der Header ist standardmäßig eingeschaltet („On“). Darin wird im oberen Bereich des Slicers der Datenfeldname angezeigt. 
1. Formatieren Sie den Headertext so, dass die **Schriftfarbe** Rot, die **Textgröße** 14 Pt. und die **Schriftfamilie** Arial Black ist. 
2. Wählen Sie unter „Kontur“ **Nur unten** aus, um einen Unterstrich in der unter „Allgemeine Optionen“ festgelegten Größe und Farbe zu erzeugen. 

### <a name="item-options"></a>Elementoptionen
1. Formatieren Sie Elementtext und den Hintergrund so, dass die **Schriftfarbe** Schwarz, der **Hintergrund** Hellrot, die **Textgröße** 10 Pt. und die **Schriftfamilie** Arial ist. 
2. Wählen Sie unter „Kontur“ die Option **Rahmen** aus, um eine Umrandung für die einzelnen Elemente in der unter „Allgemeine Optionen“ festgelegten Größe und Farbe zu zeichnen. 
    
    ![formatiert](media/power-bi-visualization-slicers/8-formatted.png)
    
    >[!TIP]
    >- Bei „Horizontale Ausrichtung“ zeigen abgewählte Elemente die ausgewählten Text- und Hintergrundfarben an, während ausgewählte Elemente den Systemstandard verwenden (in der Regel schwarze Hintergründe mit weißem Text). 
    >- Bei „Vertikale Ausrichtung“ zeigen Elemente immer die festgelegten Farben an, während Auswahlfelder immer schwarz sind, wenn sie ausgewählt werden. 

### <a name="other-formatting-options"></a>Weitere Formatierungsoptionen
Die weiteren Formatierungsoptionen sind standardmäßig ausgeschaltet. Wenn sie eingeschaltet (**On**) sind: 
- **Titel**: Fügt im oberen Bereich des Slicers einen Titel hinzu und formatiert diesen (zusätzlich zu und unabhängig vom Header). 
- **Hintergrund**: Fügt eine Hintergrundfarbe zum gesamten Slicer hinzu und legt die Transparenz fest.
- **Seitenverhältnis**: Behält bei einer Größenänderung die Form des Slicers bei.
- **Rahmen**: Fügt einen 1-Pixel-Rahmen um den Slicer hinzu und legt die Farbe fest. (Dieser Slicerrahmen ist separat von den allgemeinen Einstellungen für Konturen; diese haben keinen Einfluss auf ihn.) 

## <a name="sync-and-use-the-slicer-on-other-pages"></a>Synchronisieren und Verwenden des Slicers auf anderen Seiten
Ab dem Power BI-Update von Februar 2018 können Sie einen Slicer synchronisieren und auf einer beliebigen Seite oder allen Seiten in einem Bericht verwenden. 
1. Wählen Sie in Power BI Desktop bei ausgewähltem District Manager-Slicer im Menü „Ansicht“ die Option **Slicer synchronisieren** aus, oder schalten Sie den Bereich **Slicer synchronisieren** im Power BI-Dienst ein. Der Bereich „Slicer synchronisieren“ wird angezeigt. 
    
    ![Slicer synchronisieren](media/power-bi-visualization-slicers/9-sync-slicers.png)
    
2. Wählen Sie in der ersten Spalte den Eintrag **Übersicht** und alle weiteren Seiten aus, auf denen der Slicer synchronisiert werden soll. Alternativ können Sie auf **Add to all** (Zu allen hinzufügen) klicken, damit der Slicer auf allen Berichtsseiten synchronisiert wird.  
3. Wählen Sie in der nächsten Spalte **Übersicht** aus sowie alle weiteren Seiten, auf denen der Slicer sichtbar sein soll. 
4. Wechseln Sie zur Seite **Übersicht**, und achten Sie auf den Slicer und seine Auswirkungen auf die anderen visuellen Elemente auf der Seite. 
    - Wählen Sie verschiedene Elemente aus, und entfernen Sie Elemente. Achten Sie dabei darauf, wie sich die anderen visuellen Elemente auf der Seite entsprechend verändern. Die Elementauswahl auf einer Seite wird seitenübergreifend widergespiegelt.
    - Ändern Sie die Größe, Form, Position und/oder Formatierung des Slicers auf der Seite „Übersicht“. Die Formatierung des Slicers ändert sich nicht auf anderen synchronisierten Seiten. 

### <a name="control-which-page-visuals-are-affected-by-the-slicer"></a>Steuern der vom Slicer betroffenen visuellen Elemente auf der Seite
Ein Slicer auf einer Berichtsseite hat standardmäßig Auswirkungen auf alle anderen Visualisierungen auf dieser Seite. Mit der Option **Interaktionen mit visuellen Elementen** können Sie dies bei einigen Seiten verhindern.

1. Gehen Sie auf der Seite **Übersicht** bei ausgewähltem Slicer wie folgt vor:
    - Klicken Sie in Power BI Desktop unter „Visual Tools“ auf das Menü „Format“, und wählen Sie **Interaktionen bearbeiten** aus.
    - Öffnen Sie im Power BI-Dienst in der Menüleiste das Dropdownfeld **Interaktionen mit visuellen Elementen**, und aktivieren Sie **Interaktionen bearbeiten**. 
    
    Über allen anderen visuellen Elementen auf der Seite werden Filtersteuerelemente angezeigt. ![Filtersteuerelemente](media/power-bi-visualization-slicers/filter-controls.png)
    
2. Wählen Sie das Symbol **Keine** über einem visuellen Element aus, um das Element aus der Filterung durch den Slicer auszuschließen. Wählen Sie das Symbol **Filter** aus, damit der Slicer erneut mit der Filterung des visuellen Elements beginnt. 

Weitere Informationen zur Bearbeitung von Interaktionen finden Sie unter [Interaktionen mit visuellen Elementen in einem Power BI-Bericht](service-reports-visual-interactions.md).

## <a name="next-steps"></a>Nächste Schritte
[Jetzt kostenlos testen](https://powerbi.com/)

Haben Sie Verbesserungsvorschläge für Power BI? [Vorschlag einreichen](https://ideas.powerbi.com/forums/265200-power-bi-ideas)

Weitere Fragen? [Wenden Sie sich an die Power BI-Community](http://community.powerbi.com/)

[Hinzufügen einer Visualisierung zu einem Bericht](power-bi-report-add-visualizations-i.md)

[Visualisierungstypen in Power BI](power-bi-visualization-types-for-reports-and-q-and-a.md)

[Power BI – Grundkonzepte](service-basic-concepts.md)

