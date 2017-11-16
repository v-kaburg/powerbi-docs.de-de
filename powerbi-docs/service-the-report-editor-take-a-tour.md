---
title: "Berichts-Editor – Verschaffen Sie sich einen Überblick"
description: "Berichts-Editor – Verschaffen Sie sich einen Überblick"
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
featuredvideoid: IkJda4O7oGs
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/30/2017
ms.author: mihart
ms.openlocfilehash: e5ee6db22fe0fa7fd1e61ebbfb7dbee9d3458159
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2017
---
# <a name="the-report-editortake-a-tour"></a>Berichts-Editor – Verschaffen Sie sich einen Überblick
Der Berichts-Editor im Power BI-Dienst und der Berichts-Editor in Power BI Desktop sind sich sehr ähnlich. Im Video wird der Berichts-Editor in Power BI Desktop gezeigt, und in diesem Artikel wird der Berichts-Editor im Power BI-Dienst gezeigt. 

<iframe width="560" height="315" src="https://www.youtube.com/embed/IkJda4O7oGs" frameborder="0" allowfullscreen></iframe>

Im Power BI-Dienst ist der *Berichts-Editor* nur in der [Bearbeitungsansicht](service-reading-view-and-editing-view.md) verfügbar. Wenn Sie einen Bericht in der Bearbeitungsansicht öffnen möchten, müssen Sie Besitzer des Berichts sein.

Der Power BI-Berichts-Editor besteht aus drei Abschnitten:  

1. den Bereichen **Felder**, **Visualisierungen** und **Filter**
2. den oberen Navigationsleisten    
3. dem Zeichenbereich für den Bericht     

![](media/service-the-report-editor-take-a-tour/power-bi-report-canvas.png)

## <a name="1-the-report-editor-panes"></a>1. Die Bereiche des Berichts-Editors
![](media/service-the-report-editor-take-a-tour/power-bi-report-panes.png)

Wenn Sie einen Bericht öffnen, sehen Sie drei Bereiche: Visualisierungen, Filter und Felder. Die Bereiche auf der linken Seite (Visualisierungen und Filter) steuern das Aussehen Ihrer Visualisierungen: Typ, Farben, Filter, Format.  Im Bereich auf der rechten Seite (Felder) werden die zugrunde liegenden Daten verwaltet, die in den Visualisierungen verwendet werden. 

Der im Berichts-Editor angezeigte Inhalt variiert je nach ausgewählten Optionen, die Sie im Berichtszeichenbereich vornehmen.  Wenn Sie z. B. ein einzelnes visuelles Element auswählen, 

|  |  |
| --- | --- |
| ![](media/service-the-report-editor-take-a-tour/power-bi-panes.png) |<ul><li>wird am Anfang des Bereichs „Visualisierung“ der Typ des verwendeten visuellen Elements angegeben; in diesem Beispiel ein gruppiertes Säulendiagramm.<br><br></li> <li>werden am Ende des Bereichs „Visualisierung“ (möglicherweise müssen Sie nach unten scrollen) die vom visuellen Element verwendeten Felder angezeigt. In diesem Diagramm werden „FiscalMonth“, „DistrictManager“ und „Total Sales Variance“ verwendet. <br><br></li><li>werden im Bereich „Filter“ (möglicherweise müssen Sie nach unten scrollen) alle Filter angezeigt, die angewendet wurden. <br><br></li><li>werden im Bereich „Felder“ die verfügbaren Tabellen und, wenn Sie den Namen einer Tabelle erweitern, die Felder aufgelistet, die diese Tabelle bilden. An gelber Schrift können Sie erkennen, dass mindestens ein Feld aus dieser Tabelle in der Visualisierung verwendet wird.<br><br></li><li>![](media/service-the-report-editor-take-a-tour/power-bi-paint-roller-icon.png) Um den Formatierungsbereich für die ausgewählte Visualisierung anzuzeigen, wählen Sie das Farbrollensymbol aus.<br><br></li><li>![](media/service-the-report-editor-take-a-tour/power-bi-magnifying-icon.png) Um den Analysebereich anzuzeigen, wählen Sie das Lupensymbol aus.</ul> |
|  | |

## <a name="the-visualizations-pane-from-top-to-bottom"></a>Bereich „Visualisierungen“ (von oben nach unten)
![](media/service-the-report-editor-take-a-tour/selectviz.png)

Hier wählen Sie den Typ der Visualisierung aus. Die kleinen Bilder werden als *Vorlagen* bezeichnet. In der Abbildung oben wurde ein gestapeltes Balkendiagramm ausgewählt. Wenn Sie am Anfang keinen Visualisierungstyp auswählen, sondern eine Visualisierung durch Auswählen von Feldern erstellen, wählt Power BI den Visualisierungstyp aus. Sie können die Auswahl von Power BI übernehmen oder den Typ ändern, indem Sie eine andere Vorlage auswählen. Wechseln Sie den Visualisierungstyp beliebig oft, bis Sie den Typ gefunden haben, mit dem Ihre Daten am besten dargestellt werden.

### <a name="manage-the-fields-used-in-your-visual"></a>Steuern der im Visual verwendeten Felder
![](media/service-the-report-editor-take-a-tour/power-bi-field-list.png)

Die in diesem Bereich angezeigten Buckets (auch als *Bereiche* bezeichnet) variieren je nach Typ der ausgewählten Visualisierung.  Wenn Sie z. B. ein Balkendiagramm ausgewählt haben, werden Buckets für Folgendes angezeigt: Werte, Achse und Legende. Wenn Sie ein Feld auswählen oder in den Zeichenbereich ziehen, fügt Power BI dieses Feld zu einem der Buckets hinzu.  Sie können die Felder aus der Liste „Felder“ auch direkt in die Buckets ziehen.  Einige Buckets sind auf bestimmte Datentypen beschränkt.  **Werte** akzeptiert beispielsweise keine nicht numerischen Felder. Wenn Sie also das Feld **Mitarbeitername** in das Bucket **Werte** ziehen, ändert sich das Feld für Power BI in **Anzahl von Mitarbeitername**.

### <a name="remove-a-field"></a>Entfernen von Feldern
Um ein Feld aus der Visualisierung zu entfernen, klicken Sie auf das **X** rechts neben dem Feldnamen.

![](media/service-the-report-editor-take-a-tour/deletefield.png)

Weitere Informationen finden Sie unter [Hinzufügen von Visualisierungen zu einem Power BI-Bericht](power-bi-report-add-visualizations-i.md).

### <a name="format-your-visuals"></a>Formatieren von visuellen Elementen
Wählen Sie das Farbrollen-Symbol aus, um den Formatierungsbereich anzuzeigen. Die verfügbare Option hängt vom ausgewählten Visualisierungstyp ab.

![](media/service-the-report-editor-take-a-tour/power-bi-formatting.png)

Ihnen stehen nahezu unbegrenzt viele Formatierungsmöglichkeiten zur Verfügung.  Wenn Sie mehr Informationen benötigen, untersuchen Sie den Bereich selbst weiter oder lesen Sie die folgenden Artikel:

* [Anpassen von Visualisierungstitel, Hintergrund und Legende](power-bi-visualization-customize-title-background-and-legend.md)
* [Farbformatierung](service-getting-started-with-color-formatting-and-axis-properties.md)
* [Anpassen der Eigenschaften der X- und Y-Achse](power-bi-visualization-customize-x-axis-and-y-axis.md)

### <a name="add-analytics-to-your-visualizations"></a>Hinzufügen von Analysen in Visualisierungen
Wählen Sie das Lupensymbol aus, um den Analysebereich anzuzeigen. Die verfügbare Option hängt vom ausgewählten Visualisierungstyp ab.

![](media/service-the-report-editor-take-a-tour/power-bi-analytics.png)    
Mit dem Bereich „Analyse“ im Power BI-Dienst können Sie Visualisierungen dynamische Bezugslinien hinzufügen und wichtige Trends und Erkenntnisse identifizieren. Weitere Informationen finden Sie unter [Analysebereich im Power BI-Dienst](service-analytics-pane.md) oder [Analysebereich in Power BI Desktop](desktop-analytics-pane.md).

- - -
## <a name="the-filters-pane"></a>Bereich „Filter“
Sie können Filter auf Seiten-, Berichts-, Drillthrough- und Visualsebene anzeigen, festlegen und ändern.

![](media/service-the-report-editor-take-a-tour/power-bi-formatting-pane.png)

Weitere Informationen finden Sie unter [Hinzufügen von Filtern zu Berichten](power-bi-report-add-filter.md).

- - -
## <a name="the-fields-pane"></a>Bereich „Felder“
Im Bereich „Felder“ werden die Tabellen und Felder angezeigt, die in den Daten vorhanden sind und zum Erstellen von Visualisierungen verwendet werden können.

|  |  |
| --- | --- |
| ![](media/service-the-report-editor-take-a-tour/reportfields.png) |<ul><li>Ziehen Sie ein Feld auf die Seite, um eine neue Visualisierung zu starten.  Sie können auch ein Feld auf eine vorhandene Visualisierung ziehen, um das Feld zu dieser Visualisierung hinzuzufügen.<br><br></li> <li>Wenn Sie das Kontrollkästchen neben einem Feld aktivieren, fügt Power BI dieses Feld zur aktiven (oder neuen) Visualisierung hinzu. Außerdem legt Power BI fest, in welchem Bucket dieses Feld platziert werden soll.  Soll das Feld beispielsweise als Legende, Achse oder Wert verwendet werden? Power BI trifft eine bestmögliche Annahme, und Sie können das Feld ggf. aus diesem Bucket in einen anderen verschieben. <br><br></li><li>In beiden Fällen wird das jeweils ausgewählte Feld im Berichts-Editor zum Bereich „Visualisierungen“ hinzugefügt.</li></ul> |

**HINWEIS:** Wenn Sie Power BI Desktop verwenden, finden Sie auch Optionen zum Ein- und Ausblenden von Feldern, Hinzufügen von Berechnungen usw.

### <a name="what-do-the-field-icons-mean"></a>Bedeutung der Feldsymbole
* **∑ Aggregate** Ein Aggregat ist ein numerischer Wert, mit dem z.B. eine Summe oder ein Mittelwert gebildet wird. Aggregate werden mit den Daten importiert (definiert im Datenmodell, auf dem der Bericht basiert).
  Weitere Informationen finden Sie unter [Aggregate in Power BI-Berichten](service-aggregates.md).
* ![](media/service-the-report-editor-take-a-tour/pbi_calculated_icon.png) **Berechnete Measures (auch berechnete Felder genannt)**  
   Jedes berechnete Feld verfügt über eine eigene hartcodierte Formel. Die Berechnung kann nicht geändert werden, d. h. eine Summe bleibt eine Summe. Weitere Informationen finden Sie unter [Grundlegendes zu Measures](desktop-measures.md).
* ![](media/service-the-report-editor-take-a-tour/icon.png) **Eindeutige Felder**  
   Felder mit diesem Symbol wurden aus Excel importiert und sind so eingestellt, dass sie alle Werte anzeigen, auch wenn sie Duplikate aufweisen. Ihre Daten können z. B. zwei Datensätze für Personen namens „Johan Hofman“ enthalten, die jeweils eindeutig behandelt werden, d. h. es wird keine Summe gebildet.  
* **![](media/service-the-report-editor-take-a-tour/pbi_geo_icon.png) Geografische Felder**  
   Mithilfe der Felder für Ortsangaben können Kartenvisualisierungen erstellt werden. 
* **![](media/service-the-report-editor-take-a-tour/power-bi-hierarchy-icon.png) Hierarchie**  
   Wählen Sie den Pfeil aus, um die Felder anzuzeigen, die die Hierarchie bilden. 

- - -
## <a name="2-the-top-navigation-bar"></a>2. Die obere Navigationsleiste
Die in der oberen Navigationsleiste verfügbaren Aktionen sind zahlreich, und es werden kontinuierlich neue Aktionen hinzugefügt. Informationen zu einer bestimmten Aktion finden Sie im Inhaltsverzeichnis oder im Suchfeld der Power BI-Dokumentation.

## <a name="3-the-report-canvas"></a>3. Der Zeichenbereich des Berichts
Im Zeichenbereich des Berichts wird Ihre Arbeit angezeigt. Wenn Sie in den Bereichen „Felder“, „Filter“ und „Visualisierungen“ Visuals erstellen, werden diese im Zeichenbereich des Berichts erstellt und angezeigt. Jede Registerkarte am unteren Rand des Zeichenbereichs entspricht einer Seite im Bericht. Wählen Sie eine Registerkarte aus, um die entsprechende Seite zu öffnen. 

## <a name="next-steps"></a>Nächste Schritte:
[Erstellen eines Berichts](service-report-create-new.md)

[Bearbeiten eines Berichts](service-interact-with-a-report-in-editing-view.md)

Erfahren Sie mehr über [Berichte in Power BI](service-reports.md).

[Erste Schritte mit Power BI](service-get-started.md)

[Power BI – Grundkonzepte](service-basic-concepts.md)

Weitere Fragen? [Wenden Sie sich an die Power BI-Community](http://community.powerbi.com/)

