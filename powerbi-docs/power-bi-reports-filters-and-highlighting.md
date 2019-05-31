---
title: Filtern und Hervorhebungen in Power BI-Berichten
description: Informationen zu Filtern und Hervorhebungen in Power BI-Berichten
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 05/22/2019
ms.author: maggies
LocalizationGroup: Reports
ms.openlocfilehash: 8084b8dbbc27c856633d84c6628727dcd426964d
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2019
ms.locfileid: "66187546"
---
# <a name="filters-and-highlighting-in-power-bi-reports"></a>Filtern und Hervorhebungen in Power BI-Berichten
 Dieser Artikel informiert Sie filtern und Hervorhebungen in Power BI-Dienst. Die Benutzeroberfläche ist nahezu identisch mit der von Power BI Desktop. *Filter* entfernen alles bis auf die Daten, auf die Sie sich konzentrieren möchten. *Hervorhebung* ist nicht zu filtern. Entfernen Sie keine Daten, sondern werden stattdessen eine Teilmenge der sichtbaren Daten hervorgehoben; die Daten, die nicht markiert bleibt sichtbar, sind jedoch abgeblendet.

Zum Zuweisen von Filtern und Hervorhebungen zu Berichten haben Sie in Power BI verschiedene Möglichkeiten. Diese eingehend zu beschreiben, würde den Rahmen dieses Artikels sprengen. Wir haben die Informationen also auf folgende Abschnitte aufgeteilt:

* Einführung in Filter und Hervorhebungen, Artikel, sind Sie nun bereit.
* Wie Sie [erstellen und verwenden Sie Filter in der Bearbeitungsansicht](power-bi-report-add-filter.md) in Berichten in Power BI Desktop und Power BI-Dienst. Wenn Sie über Berechtigungen zum Bearbeiten von Berichten verfügen, können Sie Filter in Berichten erstellen, ändern und löschen.
* Wie Visuals [filtern und hervorheben in einem Bericht für Sie freigegeben](consumer/end-user-interactions.md)im Leseansicht von Power BI-Dienst zu melden. Hier bestehen Einschränkungen, Ihnen stehen aber in jedem Fall eine Vielzahl von Optionen für Filter und Hervorhebungen zur Verfügung.  
* Einen ausführlichen Überblick über die [filtern und Hervorheben von Steuerelementen in der Bearbeitungsansicht verfügbar](power-bi-report-add-filter.md) in Power BI Desktop und Power BI-Dienst. Der Artikel bietet einen detaillierten Einblick in die Arten von Filtern, z. B. Datum und Uhrzeit, numerischen und Text. Dazu gehört auch die Unterschiede zwischen grundlegenden und erweiterten Optionen.
* Wenn Sie das Standardverfahren für die Verwendung von Filtern und Hervorhebungen kennengelernt haben, erfahren Sie, [wie Sie die Art und Weise ändern, in der verschiedene Visualisierungen auf einer Seite einander durch Filter und Hervorhebungen beeinflussen](service-reports-visual-interactions.md).

**Wussten Sie schon?** Power BI umfasst eine neue Filteroberfläche, die sich zurzeit in der Vorschau befindet. Erfahren Sie mehr über die [neue Filteroberfläche in Power BI-Berichten](power-bi-report-filter-preview.md).

![Neue Filteroberfläche](media/power-bi-reports-filters-and-highlighting/power-bi-filter-reading.png)


## <a name="intro-to-the-filters-pane"></a>Einführung in den Bereich „Filter“

Sie können die Filter im Bereich **Filter** oder durch [Auswahl von Slicern](visuals/power-bi-visualization-slicers.md) direkt im Bericht anwenden. Im Bereich „Filter“ werden die Tabellen und Felder, die im Bericht verwendet werden, sowie die ggf. angewendeten Filter angezeigt. 

![Bereich „Filter“](media/power-bi-reports-filters-and-highlighting/power-bi-add-filter-reading-view.png)

Es gibt vier Arten von Filtern.

- Ein **Seitenfilter** gilt für Visualisierungen auf der Berichtsseite.     
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

![Filter in der Leseansicht](media/power-bi-reports-filters-and-highlighting/power-bi-filter-reading-view.png)

Diese Berichtsseite verfügt also über sechs Filter auf Seitenebene und einen Filter auf Berichtsebene.

Jedes Visual kann Filter für alle Felder im Visual enthalten, und ein Berichtsautor kann weitere hinzufügen. Im Bild unten weist das Blasendiagramm sechs Filter auf.

![-Filter auf visueller Ebene](media/power-bi-reports-filters-and-highlighting/power-bi-filter-visual-level.png)

In der Leseansicht können Sie die Daten untersuchen, indem Sie die bestehenden Filter modifizieren. Selbst wenn Sie den Bericht in einer mobilen App öffnen, werden die von Ihnen vorgenommenen Veränderungen zusammen mit dem Bericht gespeichert. Mehr dazu erfahren Sie im [Überblick über den Berichtsbereich „Filter“](consumer/end-user-report-filter.md).

Wenn Sie den Bericht verlassen, werden Ihre Filter gespeichert. Um die Filterung aufzuheben und zu den Standardwerten für Filter, Slicing, Detailgenauigkeit und Sortierung zurückzukehren, die jeweils vom Berichtsautor festgelegt wurden, wählen Sie aus der Menüleiste oben **Auf Standardwert zurücksetzen** aus.

![Zurücksetzen auf die Standardsymbol](media/power-bi-reports-filters-and-highlighting/power-bi-reset-to-default.png)

### <a name="filters-in-editing-view"></a>Filter in der Bearbeitungsansicht
Wenn Sie über Besitzerberechtigungen für einen Bericht verfügen und diesen in der Bearbeitungsansicht öffnen, sehen Sie, dass der Bereich **Filter** nur einer von verschiedenen verfügbaren Bearbeitungsbereichen ist.

![Bereich "Filter" in der Bearbeitungsansicht](media/power-bi-reports-filters-and-highlighting/power-bi-add-filter-editing-view.png)

Wie in der Leseansicht verfügt diese Berichtsseite über sechs Filter auf Seitenebene und einen Filter auf Berichtsebene. Durch Auswahl des Blasendiagramms erfahren wir, dass sechs Filter auf Visualebene angewendet wurden.

In der Bearbeitungsansicht bieten Filter und Hervorhebungen mehr Möglichkeiten. In erster Linie können Sie Filter hinzufügen. Erfahren Sie, wie Sie [einen Filter zu einem Bericht hinzufügen](power-bi-report-add-filter.md), und vieles mehr.

## <a name="ad-hoc-highlighting"></a>Ad-hoc-Hervorhebung.
Wählen Sie eine Wert oder eine Achse Bezeichnung in einem visuellen Element, um die anderen Visualisierungen auf der Seite hervorzuheben. Um die Hervorhebung zu entfernen, wählen Sie den Wert erneut aus, oder wählen Sie einen leeren Bereich in der gleichen Visualisierung. Hervorhebung ist eine Möglichkeit zum Einfluss von Daten schnell zu durchsuchen. Wie Sie das Verhalten dieser Art von übergreifenden Hervorhebungen anpassen können, erfahren Sie unter [Interaktionen mit Visuals](service-reports-visual-interactions.md).

![Übergreifende Hervorhebung](media/power-bi-reports-filters-and-highlighting/power-bi-adhoc-filter.gif)


## <a name="next-steps"></a>Nächste Schritte

[Die neue Filter-Benutzeroberfläche in Power BI-Berichten](power-bi-report-filter-preview.md)

[Hinzufügen eines Filters zu einem Bericht (in der Bearbeitungsansicht)](power-bi-report-add-filter.md)

[Überblick über Berichtsfilter](consumer/end-user-report-filter.md)

[Ändern der Kreuzfilterung und -hervorhebung von Berichtsvisualisierungen](consumer/end-user-interactions.md)

Weitere Fragen? [Wenden Sie sich an die Power BI-Community](http://community.powerbi.com/)

