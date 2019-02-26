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
ms.date: 12/06/2018
ms.author: mihart
LocalizationGroup: Reports
ms.openlocfilehash: 43046a5fab33f384a6d9f573a992843fa84a0713
ms.sourcegitcommit: a054782370dec56d49bb205ee10b7e2018f22693
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/22/2019
ms.locfileid: "56662225"
---
# <a name="how-visuals-cross-filter-each-other-in-a-power-bi-report"></a>Gegenseitige Kreuzfilterung von Visuals in einem Power BI-Bericht
Eines der herausragenden Features von Power BI ist die Art, auf die alle visuellen Elemente auf einer Berichtsseite miteinander verbunden sind. Wenn Sie in einem der visuellen Elemente einen Datenpunkt auswählen, ändern sich alle anderen visuellen Elemente auf der Seite, die diese Daten enthalten, auf Grundlage dieser Auswahl. 

![Video von interagierenden visuellen Elementen](media/end-user-interactions/interactions.gif)

Standardmäßig können Visualisierungen auf einer Berichtsseite für die Kreuzfilterung und -hervorhebung sowie Drillvorgänge der anderen Visualisierungen auf der Seite verwendet werden. Beim Auswählen eines Status in einer Kartenvisualisierung werden beispielsweise das Säulendiagramm hervorgehoben und das Liniendiagramm gefiltert, um nur Daten anzuzeigen, die für diesen einen Status gelten.

Siehe [Informationen zum Filtern und Hervorheben](../power-bi-reports-filters-and-highlighting.md). Wenn Sie über eine Visualisierung verfügen, die [Drilling](../power-bi-visualization-drill-down.md) unterstützt, hat das Drilling einer Visualisierung standardmäßig keinen Einfluss auf andere Visualisierungen auf der Berichtsseite. 

Wie visuelle Elemente auf einer Seite genau miteinander interagieren, wird vom *Designer* des Berichts festgelegt. Designer können visuelle Interaktionen aktivieren und deaktivieren sowie das Standardverhalten von Kreuzfilterung und -hervorhebung sowie Drillvorgängen ändern.
  
> [!NOTE]
> Die Begriffe *Kreuzfilterung* und *Kreuzhervorhebung* werden verwendet, um das hier beschriebene Verhalten davon zu unterscheiden, was geschieht, wenn Sie den Bereich **Filter** zum Filtern und Hervorheben von Visualisierungen verwenden.  

### <a name="next-steps"></a>Nächste Schritte
[Verwenden von Berichtsfiltern](../power-bi-how-to-report-filter.md)
