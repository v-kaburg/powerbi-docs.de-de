---
title: Informationen zu Filtern und Hervorhebungen in Power BI-Berichten
description: Informationen zu Filtern und Hervorhebungen in Power BI-Berichten
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 09/28/2018
ms.author: maggies
LocalizationGroup: Reports
ms.openlocfilehash: e364d2ceac3d1a30b0742ceac2bd56e2bc66d9ba
ms.sourcegitcommit: d20f74d5300197a0930eeb7db586c6a90403aabc
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2018
ms.locfileid: "50973233"
---
# <a name="about-filters-and-highlighting-in-power-bi-reports"></a>Informationen zu Filtern und Hervorhebungen in Power BI-Berichten
 Dieser Artikel informiert Sie über das Zuweisen von Filtern und Hervorhebungen im Power BI-Dienst. Die Benutzeroberfläche ist nahezu identisch mit der von Power BI Desktop. ***Filter*** entfernen alles bis auf die Daten, auf die Sie sich konzentrieren möchten. ***Hervorheben*** ist nicht dasselbe wie Filtern. Dieser Vorgang entfernt keine Daten, sondern hebt eine Teilmenge der sichtbaren Daten. Die nicht hervorgehobenen Daten bleiben sichtbar, sind jedoch abgeblendet.

Zum Zuweisen von Filtern und Hervorhebungen zu Berichten haben Sie in Power BI verschiedene Möglichkeiten. Diese eingehend zu beschreiben, würde den Rahmen dieses Artikels sprengen. Wir haben die Informationen also auf folgende Abschnitte aufgeteilt:

* Einführung in Filter und Hervorhebungen (dieser Artikel)
* Die Möglichkeiten zum [Erstellen und Verwenden von Filtern in der Bearbeitungsansicht](power-bi-report-add-filter.md) in Berichten. Wenn Sie über Berechtigungen zum Bearbeiten von Berichten verfügen, können Sie Filter in Berichten erstellen, ändern und löschen.
* Die Möglichkeiten zum [Verwenden von Filtern und Hervorhebungen in einem für Sie freigegebenen Bericht](consumer/end-user-reading-view.md) in der Leseansicht. Hier bestehen Einschränkungen, Ihnen stehen aber in jedem Fall eine Vielzahl von Optionen für Filter und Hervorhebungen zur Verfügung.  
* Eine ausführliche Tour durch die [Steuerelemente für Filter und Hervorhebungen in der Bearbeitungsansicht](consumer/end-user-report-filter.md), einschließlich der verschiedenen Filtertypen (z.B. Datum und Uhrzeit, Zahlen- und Textfilter) und einer Erläuterung der Unterschiede zwischen grundlegenden und erweiterten Optionen.
* Wenn Sie das Standardverfahren für die Verwendung von Filtern und Hervorhebungen kennengelernt haben, erfahren Sie, [wie Sie die Art und Weise ändern, in der verschiedene Visualisierungen auf einer Seite einander durch Filter und Hervorhebungen beeinflussen](consumer/end-user-interactions.md).

## <a name="intro-to-the-filters-pane"></a>Einführung in den Bereich „Filter“

Sie können die Filter im Bereich **Filter** oder durch [Auswahl von Slicern](visuals/power-bi-visualization-slicers.md) direkt im Bericht anwenden. Im Bereich „Filter“ werden die Tabellen und Felder, die im Bericht verwendet werden, sowie die ggf. angewendeten Filter angezeigt. 

![](media/power-bi-reports-filters-and-highlighting/power-bi-add-filter-reading-view.png)

Es gibt vier Arten von Filtern.

- Ein **Seitenfilter** gilt für Visuals auf der Berichtsseite.     
- Ein **Visualfilter** gilt für ein einzelnes Visual auf einer Berichtsseite. Die Filter auf Visualebene werden nur angezeigt, wenn Sie in der Berichtscanvas ein Visual ausgewählt haben.    
- Ein **Berichtsfilter** gilt für alle Seiten im Bericht.    
- Ein **Drillthroughfilter** gilt für eine einzelne Entität in einem Bericht.    

Sie können in der Lese- oder Bearbeitungsansicht in Seiten-, Visual- und Berichtsfiltern suchen, um den gewünschten Wert zu finden. 

![Suche in einem Filter](media/power-bi-reports-filters-and-highlighting/power-bi-search-filter.png)

Wenn neben einem Filter das Wort **Alle** steht, bedeutet dies, dass alle Werte im Feld in den Filter einbezogen werden.  Beispiel: **Kette(Alle)** (im Screenshot unten „Chain(All)“) bedeutet, dass diese Berichtsseite Informationen über alle Ladenketten enthält.  Andererseits können wir der Angabe **Geschäftsjahr ist 2013 oder 2014** entnehmen, dass der Bericht ausschließlich Informationen aus den Geschäftsjahren 2013 und 2014 umfasst.

## <a name="filters-in-reading-or-editing-view"></a>Filter in der Lese- und der Bearbeitungsansicht
Es gibt zwei Modi für die Interaktion mit Berichten: [Leseansicht](consumer/end-user-reading-view.md) und Bearbeitungsansicht. Welche Filterfunktionen verfügbar sind, richtet sich nach dem Modus, in dem Sie sich befinden.

* In der Bearbeitungsansicht können Sie Berichts-, Seiten-, Drillthrough- und Visualfilter hinzufügen. Beim Speichern des Berichts werden die Filter zusammen mit dem Bericht gespeichert – auch dann, wenn Sie den Bericht in einer mobilen App öffnen. Personen, die den Bericht in der Leseansicht anzeigen, können mit den von Ihnen hinzugefügten Filtern interagieren, aber keine neuen Filter hinzufügen.
* In der Leseansicht können Sie mit allen Filtern interagieren, die im Bericht schon vorhanden sind, und Ihre Auswahl anschließend speichern. Sie können keine neuen Filter hinzufügen.

### <a name="filters-in-reading-view"></a>Filter in der Leseansicht
Wenn Sie auf einen Bericht nur über die Leseansicht zugreifen können, sieht der Bereich „Filter“ etwa wie folgt aus:

![](media/power-bi-reports-filters-and-highlighting/power-bi-filter-reading-view.png)

Diese Berichtsseite verfügt also über sechs Filter auf Seitenebene und einen Filter auf Berichtsebene.

Jedes Visual kann Filter für alle Felder im Visual enthalten, und ein Berichtsautor kann weitere hinzufügen. Im Bild unten weist das Blasendiagramm sechs Filter auf.

![](media/power-bi-reports-filters-and-highlighting/power-bi-filter-visual-level.png)

In der Leseansicht können Sie die Daten untersuchen, indem Sie die bestehenden Filter modifizieren. Selbst wenn Sie den Bericht in einer mobilen App öffnen, werden die von Ihnen vorgenommenen Veränderungen zusammen mit dem Bericht gespeichert. Mehr dazu erfahren Sie im [Überblick über den Berichtsbereich „Filter“](consumer/end-user-report-filter.md).

Wenn Sie den Bericht verlassen, werden Ihre Filter gespeichert. Um die Filterung aufzuheben und zu den Standardwerten für Filter, Slicing, Detailgenauigkeit und Sortierung zurückzukehren, die jeweils vom Berichtsautor festgelegt wurden, wählen Sie aus der Menüleiste oben **Auf Standardwert zurücksetzen** aus.

![](media/power-bi-reports-filters-and-highlighting/power-bi-reset-to-default.png)

### <a name="filters-in-editing-view"></a>Filter in der Bearbeitungsansicht
Wenn Sie über Besitzerberechtigungen für einen Bericht verfügen und diesen in der Bearbeitungsansicht öffnen, sehen Sie, dass der Bereich **Filter** nur einer von verschiedenen verfügbaren Bearbeitungsbereichen ist.

![](media/power-bi-reports-filters-and-highlighting/power-bi-add-filter-editing-view.png)

Wie in der Leseansicht verfügt diese Berichtsseite über sechs Filter auf Seitenebene und einen Filter auf Berichtsebene. Durch Auswahl des Blasendiagramms erfahren wir, dass sechs Filter auf Visualebene angewendet wurden.

In der Bearbeitungsansicht bieten Filter und Hervorhebungen mehr Möglichkeiten. In erster Linie können Sie Filter hinzufügen. Erfahren Sie, wie Sie [einen Filter zu einem Bericht hinzufügen](power-bi-report-add-filter.md), und vieles mehr.

## <a name="ad-hoc-highlighting"></a>Ad-hoc-Hervorhebung
Wählen Sie zum Filtern und Hervorheben der anderen Visuals auf der Seite in der Berichtscanvas ein Feld aus. Wählen Sie in derselben Visualisierung einen leeren Bereich an, um die eben getroffene Auswahl wieder zu entfernen. Dieser Hervorhebungstyp ermöglicht es Ihnen, die Auswirkungen von Daten schnell zu untersuchen. Wie Sie das Verhalten dieser Art von übergreifenden Hervorhebungen anpassen können, erfahren Sie unter [Interaktionen mit Visuals](consumer/end-user-interactions.md).

![](media/power-bi-reports-filters-and-highlighting/power-bi-adhoc-filter.gif)


## <a name="next-steps"></a>Nächste Schritte
[Hinzufügen eines Filters zu einem Bericht (in der Bearbeitungsansicht)](power-bi-report-add-filter.md)

[Überblick über Berichtsfilter](consumer/end-user-report-filter.md)

[Ändern der Kreuzfilterung und -hervorhebung von Berichtsvisualisierungen](consumer/end-user-interactions.md)

Weitere Fragen? [Wenden Sie sich an die Power BI-Community](http://community.powerbi.com/)

