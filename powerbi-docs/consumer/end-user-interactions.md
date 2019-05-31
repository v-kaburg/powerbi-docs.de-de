---
title: Interaktionen zwischen Visuals in einem Bericht
description: Dokumentation für Power BI-Endbenutzer, die erklärt, wie visuelle Elemente auf einer Berichtsseite interagieren.
author: mihart
manager: kvivek
ms.custom: seodec18
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-consumer
ms.topic: conceptual
ms.date: 05/29/2019
ms.author: mihart
LocalizationGroup: Reports
ms.openlocfilehash: 7148a52d7c7475fbe685f83b1e1cc325521460db
ms.sourcegitcommit: d88cc6a87d4ba82ad2c4d496a3634f927e4ac529
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/30/2019
ms.locfileid: "66413173"
---
# <a name="how-visuals-cross-filter-each-other-in-a-power-bi-report"></a>Gegenseitige Kreuzfilterung von Visuals in einem Power BI-Bericht
Eines der herausragenden Features von Power BI ist die Art, auf die alle visuellen Elemente auf einer Berichtsseite miteinander verbunden sind. Wenn Sie in einem der visuellen Elemente einen Datenpunkt auswählen, ändern sich alle anderen visuellen Elemente auf der Seite, die diese Daten enthalten, auf Grundlage dieser Auswahl. 

![Video von interagierenden visuellen Elementen](media/end-user-interactions/interactions.gif)

Standard, wählen einen Datenpunkt in einer Visualisierung auf einer Berichtsseite wird kreuzfiltern, hervorheben, und zeigen Sie die anderen Visualisierungen auf der Seite. 

Dies kann nützlich sein, wie ein Wert in den Daten identifizieren trägt zu einem anderen. Z. B. das Moderation Segment im Ringdiagramm auswählen die einzelnen Spalten in die Gesamtzahl der Einheiten nach Monat Diagramm die Beteiligung dieses Segment hervorgehoben, und es wurde gefiltert, dass das Liniendiagramm auf der rechten Seite.

![Bild von visuellen Elementen interagieren](media/end-user-interactions/power-bi-interactions.png)

Siehe [Informationen zum Filtern und Hervorheben](../power-bi-reports-filters-and-highlighting.md). 

Wie visuelle Elemente auf einer Seite genau miteinander interagieren, wird vom *Designer* des Berichts festgelegt. Designer können visuelle Interaktionen aktivieren und deaktivieren sowie das Standardverhalten von Kreuzfilterung und -hervorhebung sowie Drillvorgängen ändern. 
  
> [!NOTE]
> Die Begriffe *Kreuzfilterung* und *Kreuzhervorhebung* werden verwendet, um das hier beschriebene Verhalten davon zu unterscheiden, was geschieht, wenn Sie den Bereich **Filter** zum Filtern und Hervorheben von Visualisierungen verwenden.  

## <a name="considerations-and-troubleshooting"></a>Zu beachtende Aspekte und Problembehandlung
- Wenn Ihr Bericht eine Visualisierung verfügt, unterstützt [Drilldown](../power-bi-visualization-drill-down.md), in der Standardeinstellung drilling einer Visualisierung hat keine Auswirkungen auf die anderen Visualisierungen auf der Berichtsseite.     
- Wenn Sie VisualA für die Interaktion mit VisualB verwenden, werden Filter auf visueller Ebene, von VisualA auf VisualB angewendet werden.

## <a name="next-steps"></a>Nächste Schritte
[Verwenden von Berichtsfiltern](../power-bi-how-to-report-filter.md)
