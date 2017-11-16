---
title: "Ändern der Interaktion von Visualisierungen in einem Bericht"
description: Dokumentation zum Festlegen von Interaktionen mit Visualisierungen in einem Microsoft Power BI-Bericht.
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: N_xYsCbyHPw
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 09/25/2017
ms.author: mihart
ms.openlocfilehash: 126bd40e98a88138a2732155f9792d65666e52c7
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2017
---
# <a name="visualization-interactions-in-a-power-bi-report"></a>Interaktionen mit Visualisierungen in einem Power BI-Bericht
Standardmäßig können Visualisierungen auf einer Berichtsseite für die Kreuzfilterung und -hervorhebung der anderen Visualisierungen auf der Seite verwendet werden.
Beim Auswählen eines Status in einer Kartenvisualisierung wird beispielsweise das Säulendiagramm hervorgehoben und das Liniendiagramm gefiltert, um nur Daten anzuzeigen, die für diesen einen Status gelten.
Siehe [Informationen zum Filtern und Hervorheben](power-bi-reports-filters-and-highlighting.md).

Um dieses Standardverhalten zu ändern, verwenden Sie das Steuerelement **Visualinteraktionen**. „Visualinteraktionen“ ist nur in der [Bearbeitungsansicht](service-interact-with-a-report-in-editing-view.md) verfügbar. Wenn ein Bericht für Sie freigegeben wurde, müssen Sie nicht auf „Visualinteraktionen“ zugreifen.

> [!NOTE]
> Die Begriffe *Kreuzfilterung* und *Kreuzhervorhebung* werden verwendet, um das hier beschriebene Verhalten davon zu unterscheiden, was geschieht, wenn Sie den Bereich **Filter** zum Filtern und Hervorheben von Visualisierungen verwenden.  
> 
> 

<iframe width="560" height="315" src="https://www.youtube.com/embed/N_xYsCbyHPw?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>

1. Wählen Sie eine Visualisierung aus, um sie zu aktivieren.  
2. Aktivieren Sie **Interaktionen mit Visualisierungen** , indem Sie diese Option auf der oberen Menüleiste auswählen. Beachten Sie die Filter- und Hervorhebungssymbole, die über den anderen Visualisierungen auf der Berichtsseite angezeigt werden, wenn Sie auf sie zeigen.
   
    ![](media/service-reports-visual-interactions/pbi-visual-interaction-icon.png)
3. Bestimmen Sie, welche Auswirkung die ausgewählte Visualisierung auf die anderen haben soll.  
   
   * Wenn sie eine Kreuzfilterbeziehung mit der anderen Visualisierung haben soll, wählen Sie das Symbol **Filter** ![](media/service-reports-visual-interactions/pbi-filter-icon-outlined.png) aus.
   * Wenn sie eine Kreuzhervorhebung bei dieser Visualisierung bewirken soll, wählen Sie das Symbol **Hervorhebung** ![](media/service-reports-visual-interactions/pbi-highlight-icon-outlined.png) aus.
   * Wenn sie keine Auswirkung haben soll, wählen Sie das Symbol **Keine Auswirkung** ![](media/service-reports-visual-interactions/pbi-noimpact-icon-outlined.png) aus.
4. Optional können Sie diesen Schritt für alle anderen Visualisierungen auf der Berichtsseite wiederholen.

### <a name="next-steps"></a>Nächste Schritte
[Verwenden von Berichtsfiltern](power-bi-how-to-report-filter.md)

[Filter und Hervorhebungen in Berichten](power-bi-reports-filters-and-highlighting.md)

[Power BI – Grundkonzepte](service-basic-concepts.md)

Weitere Fragen? [Wenden Sie sich an die Power BI-Community](http://community.powerbi.com/)

