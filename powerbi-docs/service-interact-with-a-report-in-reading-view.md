---
title: Interagieren mit einem Bericht in der Leseansicht von Power BI
description: Interagieren mit einem Bericht in der Leseansicht von Power BI
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: monitoring
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 08/15/2017
ms.author: mihart
ms.openlocfilehash: 54de712e0743801b3e8c565ca997bbc56e254c69
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2017
---
# <a name="interact-with-a-report-in-reading-view-in-power-bi"></a>Interagieren mit einem Bericht in der Leseansicht von Power BI
## <a name="reading-view"></a>Leseansicht
Interaktivität ist in der Leseansicht weniger ausgeprägt als in der [Bearbeitungsansicht](service-interact-with-a-report-in-editing-view.md), aber die Leseansicht bietet Ihnen dennoch viele Optionen zum Untersuchen der Daten. Dies ist beim Anzeigen von Berichten, die [für Sie freigegeben wurden](service-share-dashboards.md) und nur in der Leseansicht geöffnet werden können, von Nutzen.

In der Leseansicht können Sie auf ansprechende und sichere Weise mit den Daten experimentieren und diese erkunden. In der Leseansicht können Sie auf visuelle Elemente auf einer Seite Kreuzhervorhebung und Kreuzfilterung anwenden.  Heben Sie einfach einen Wert in einem Visual hervor, oder wählen Sie ihn aus, um seine Auswirkung auf die anderen Visuals sofort anzuzeigen. Verwenden Sie den Bereich „Filter“, um Filter auf einer Berichtsseite hinzuzufügen und zu ändern, und ändern Sie die Sortierung der Werte in einer Visualisierung. Alle vorgenommenen Filterungen und Hervorhebungen werden nicht mit dem Bericht gespeichert.

## <a name="cross-highlight-the-related-visualizations-on-a-page"></a>Kreuzhervorhebung bei verknüpften Visualisierungen auf einer Seite
Visualisierungen auf einer Berichtsseite sind alle miteinander „verknüpft“.  Wenn Sie also einen oder mehrere Werte in einer Visualisierung auswählen, werden andere Visualisierungen, die den gleichen Wert verwenden, auf Grundlage dieser Auswahl geändert.

![](media/service-interact-with-a-report-in-reading-view/pagefilter3b.gif)

> [!NOTE]
> Wenn Sie mehr als ein Element in einer Visualisierung auswählen möchten, halten Sie die STRG-TASTE gedrückt.
> 
> 

## <a name="hover-over-visual-elements-to-see-the-details"></a>Zeigen Sie auf ein visuelles Element, um die Details anzuzeigen.
![](media/service-interact-with-a-report-in-reading-view/amarillachart.png)

## <a name="sort-the-data-in-a-visualization"></a>Die Daten in einer Visualisierung sortieren
Wählen Sie die Auslassungspunkte (...) aus, um **Sortieren nach** zu öffnen. Wählen Sie den Dropdownpfeil und danach das Feld aus, nach dem sortiert werden soll. Durch Klicken auf das „AZ“-Symbol ändern Sie die Sortierreihenfolge (aufsteigend oder absteigend). 

![](media/service-interact-with-a-report-in-reading-view/pbi_changechartsort.gif) 

## <a name="interact-with-filters"></a>Interagieren mit Filtern
Wenn der Autor des Berichts einer Berichtsseite Filter hinzugefügt hat, können Sie in der Leseansicht mit diesen interagieren. Vorgenommene Änderungen werden nicht mit dem Bericht gespeichert.

1. Wählen Sie oben rechts das Filtersymbol aus.
   
   ![](media/service-interact-with-a-report-in-reading-view/filters.png)  
2. Ihnen werden alle Filter angezeigt, die auf die ausgewählte Visualisierung (Filter auf visueller Ebene), auf die gesamte Berichtsseite (Filter auf Seitenebene) und auf den gesamten Bericht (Filter auf Berichtsebene) angewandt werden.
   
   ![](media/service-interact-with-a-report-in-reading-view/power-bi-reading-filters.png)
3. Zeigen Sie auf einen Filter, und erweitern Sie ihn, indem Sie den Pfeil nach unten auswählen.
   
   ![](media/service-interact-with-a-report-in-reading-view/power-bi-expan-filter.png)
4. Ändern Sie die Filter, und beobachten Sie die Auswirkungen auf die visuellen Elemente.  
   
   * In diesem Beispiel haben wir einen Filter auf Seitenebene für **Kette**. Ändern Sie ihn von **Lindseys** in **Fashions Direct**, indem Sie die entsprechenden Kontrollkästchen aktivieren bzw. deaktivieren.
     
     ![](media/service-interact-with-a-report-in-reading-view/power-bi-filter-chain.png)
   * Oder heben Sie die Filterung nach **Kette** vollständig auf, indem Sie das Radierersymbol ![](media/service-interact-with-a-report-in-reading-view/power-bi-eraser-icon.png) oder beide Läden der Kette auswählen.
   * Wählen Sie den Filter auf Seitenebene **Region** aus und wechseln Sie zu **Erweiterte Filterung**. Bearbeiten Sie den Filter so, dass nur Regionen angezeigt werden, die mit **FD** beginnen und die Zahl 4 nicht enthalten.
     
     ![](media/service-interact-with-a-report-in-reading-view/power-bi-advanced-filter.png)

Weitere Informationen finden Sie unter [Hinzufügen eines Filters zu einem Bericht](power-bi-report-add-filter.md) und [Informationen zu Filtern und Hervorhebungen in Berichten](power-bi-reports-filters-and-highlighting.md).

## <a name="zoom-in-on-individual-visuals"></a>Einzelne visuelle Elemente vergrößern
Zeigen Sie auf eine Visualisierung, und wählen Sie das Symbol für den **Fokusmodus** aus: ![](media/service-interact-with-a-report-in-reading-view/pbi_popouticon.jpg). Wenn Sie eine Visualisierung im Fokusmodus anzeigen, wird diese erweitert, sodass sie den gesamten Berichtszeichenbereich ausfüllt, wie unten dargestellt.

![](media/service-interact-with-a-report-in-reading-view/powerbi-focus-mode.png)

Wählen Sie zum Anzeigen dieser Visualisierung ohne störende Menüleisten, ohne den Filterbereich und andere Chromelemente das Symbol **Vollbild**![](media/service-interact-with-a-report-in-reading-view/power-bi-focus-icon.png) auf der oberen Menüleiste aus.

![](media/service-interact-with-a-report-in-reading-view/power-bi-full-screen.png)

Weitere Informationen finden Sie unter [Fokusmodus für Berichte](service-focus-mode.md) und [Vollbildmodus für Berichte](service-fullscreen-mode.md).

## <a name="adjust-the-display-dimensions"></a>Anpassen der Anzeigegröße
Berichte werden auf vielen verschiedenen Geräten mit unterschiedlichen Bildschirmgrößen und Seitenverhältnissen angezeigt.  Die Standardanzeige entspricht unter Umständen nicht dem, was Sie auf Ihrem Gerät anzeigen möchten.  Wählen Sie zum Anpassen **Ansicht** aus, und wählen Sie:

* An Seite anpassen: Inhalte werden skaliert und an die Seite angepasst.
* An Breite anpassen: Inhalte werden skaliert und an die Seitenbreite angepasst.
* Tatsächliche Größe: Der Inhalt wird in voller Größe angezeigt.  

![](media/service-interact-with-a-report-in-reading-view/power-bi-view.png)

  In der Leseansicht ist die gewählte Anzeigeoption temporär, d. h. sie wird beim Schließen des Berichts nicht gespeichert.

  Weitere Informationen erhalten Sie im [Tutorial zum Ändern der Anzeigeeinstellungen für einen Bericht](power-bi-change-report-display-settings.md).

## <a name="next-steps"></a>Nächste Schritte
[Berichte in Power BI](service-reports.md)

[Öffnen der Bearbeitungsansicht](service-reading-view-and-editing-view.md)

Weitere Fragen? [Wenden Sie sich an die Power BI-Community](http://community.powerbi.com/)

