---
title: Überblick über den Berichtsbereich „Filter“
description: Hinzufügen eines Filters für einen Bericht im Power BI-Dienst für Kunden
author: mihart
manager: kvivek
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-consumer
ms.topic: conceptual
ms.date: 05/30/2019
ms.author: mihart
LocalizationGroup: Reports
ms.openlocfilehash: dcf62925d8e5eef07fb6295f8d8141413947f8fb
ms.sourcegitcommit: d88cc6a87d4ba82ad2c4d496a3634f927e4ac529
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/30/2019
ms.locfileid: "66413129"
---
# <a name="take-a-tour-of-the-report-filters-pane"></a>Überblick über den Berichtsbereich „Filter“
Dieser Artikel wirft einen Blick auf den Berichtsbereich "Filter" in Power BI-Dienst. Verwenden Sie die Filter, um neue Einsichten in Ihren Daten zu gewinnen.

Es gibt viele verschiedene Arten von Datenfiltern in Power BI. Lesen Sie den Artikel [Informationen zu Filtern und Hervorhebungen](../power-bi-reports-filters-and-highlighting.md).

![Bericht im Browser](media/end-user-report-filter/power-bi-browser-new2.png)

## <a name="working-with-the-report-filters-pane"></a>Arbeiten mit dem Bereich „Filter“ in Berichten
Wenn ein Kollege einen Bericht mit Ihnen teilt, suchen Sie immer nach dem Bereich **Filter**. Manchmal befindet er sich zugeklappt am rechten Rand des Berichts. Klicken Sie darauf, um ihn aufzuklappen.   

![Bericht im Browser](media/end-user-report-filter/power-bi-filter-pane.png)

Der Bereich „Filter“ enthält Filter, die dem Bericht durch den Berichts-*Designer* hinzugefügt wurden. *Consumer* wie Sie interagieren können, mit den vorhandenen Filter, und speichern Sie Ihre Änderungen, aber keine neuen Filter zum Bericht hinzufügen. Auf dem obigen Screenshot hat der Designer beispielsweise zwei Filter auf Seitenebene hinzugefügt: Segmentieren und Jahr an. Sie können mit diesen Filtern interagieren und sie ändern, Sie können jedoch keinen dritten Filter auf Seitenebene hinzufügen.

-Berichte im Power BI-Dienst in den Bereich "Filter" vorgenommene Änderungen beizubehalten, und diese Änderungen werden in der mobilen Version des Berichts übernommen. Klicken Sie auf der oberen Menüleiste auf **Auf Standardwert zurücksetzen**, um den Bereich „Filter“ auf den Standard zurückzusetzen.  

![Auf Standard zurücksetzen](media/end-user-report-filter/power-bi-reset-to-default.png)   

## <a name="view-all-the-filters-for-a-report-page"></a>Alle Filter für eine Berichtsseite anzeigen
Der Bereich "Filter" zeigt alle hinzugefügten filtern, um den Bericht nach der *Designer*. Der Bereich "Filter" ist auch der Bereich, in dem Sie Informationen über die Filter anzeigen und mit ihnen interagieren können. Sie können die Änderungen, die Sie vornehmen oder speichern **auf Standardwert zurücksetzen** , um die ursprünglichen filtereinstellungen wiederherzustellen.

Wenn Änderungen, die Sie speichern möchten, können Sie auch ein persönliches Lesezeichen erstellen.  Weitere Informationen finden Sie unter [Hinzufügen eines Lesezeichens zu einem Bericht](end-user-bookmarks.md).

Es gibt mehrere Typen von Berichtsfiltern, die angezeigt und verwaltet wird, klicken Sie im Bereich "Filter", die auf die zu einer Visualisierung auf einer Berichtsseite und den gesamten Bericht angewendet.

In diesem Beispiel haben wir eine Visualisierung ausgewählt, die über 2 Filter verfügt. Die Berichtsseite verfügt auch über Filter, die unter der **Filter auf dieser Seite** Überschrift. Und der gesamte Bericht verfügt über einen Filter für das Datum.

![Liste der Filter](media/end-user-report-filter/power-bi-all-filters2.png)

Neben einigen Filtern sehen Sie das Wort **Alle**; dies bedeutet, dass sämtliche Werte in den Filter eingeschlossen werden.  Z. B. **Segment(All)** im obigen Screenshot gibt an, dass diese Berichtsseite die Daten über die Produktsegmente enthält.  Andererseits, die auf der Seitenebene Filtern von **Region West ist** gibt an, dass die Berichtsseite nur Daten für die Region West enthält.

Jeder, der den Bericht aufruft, kann auch mit den Filtern interagieren.

### <a name="view-only-those-filters-applied-to-a-visual"></a>Zeigen Sie nur diese auf eine Visualisierung angewendeten Filter an
Zeigen Sie auf das visuelle Element, um das Symbol "Filter" anzuzeigen, rufen Sie einen genaueren Blick auf die zu einer bestimmten Visualisierung angewendeten Filter ![Symbol](media/end-user-report-filter/power-bi-filter-icon.png). Wählen Sie dieses Symbol "Filter", um ein Popupfenster mit der alle Filter, Slicer und So weiter, die Auswirkungen auf das visuelle anzuzeigen. Die Filter im Popupfenster sind die gleichen Filter angezeigt, auf die **Filter** Bereich. 

![Liste der Filter](media/end-user-report-filter/power-bi-hover-visual-filter.png)

 
Hier sind die Typen von Filtern, die in dieser Ansicht angezeigt werden kann:
- Basisfilter
- Datenschnitte
- Übergreifende Hervorhebung
- Kreuzfilterung
- Erweiterte Filter
- Top N-Filter
- Relative Datenfilter
- Synchronisierungsslicer
- Einschluss-/Ausschlussfilter
- Per URL übergebene Filter



Im Beispiel unten:
1. Wir sehen, dass im Säulendiagramm kreuzgefiltert wurde.
2. **Enthalten** gibt an, dass für die kreuzfilterung ist **Segment**, und drei enthalten sind. 
3. Ein Slicer für angewendet wurde **Quartal**.
4. **Region** ist ein Filter angewendet, die zu dieser Berichtsseite, und
5. **IsVanArsdel** und **Jahr** angewendeten Filter auf dieses visual sind.


![Liste der Filter](media/end-user-report-filter/power-bi-visual-pop-up.png)

### <a name="search-in-a-filter"></a>Suche in einem Filter
Manchmal kann eine lange Liste von Werten über einen Filter verfügen. Verwenden Sie das Suchfeld zum Suchen und wählen Sie den gewünschten Wert. 

![Suche in einem Filter](media/end-user-report-filter/power-bi-fiter-search.png)

### <a name="display-filter-details"></a>Filterdetails anzeigen
Um einen Filter zu verstehen, sehen Sie sich die verfügbaren Werte und Anzahlen.  Zeigen Sie die Details des Filters können Sie an, indem Sie mit dem Mauszeiger aus, und Sie den Pfeil neben dem Filternamen auswählen. 
  
![Zeigt ausgewählte Lindseys](media/end-user-report-filter/power-bi-expand-filter.png)

### <a name="change-filter-selections"></a>Filterauswahl ändern
Eine Möglichkeit, die zu suchende von Erkenntnissen aus Daten ist mit den Filtern interagieren. Sie können mit den Dropdownpfeil neben dem Feldnamen Filterauswahl ändern.  Je nach den Filter und der Typ der Daten, die gefiltert wird werden die Optionen aus einfachen Auswahl aus einer Liste zum Identifizieren von Bereichen des Datums- oder Zahlenangaben reichen. Im folgenden erweiterten Filter, haben wir den Filter geändert **Total Units YTD** im TreeMap-Diagramm zwischen 2.000 und 3.000 sein. Beachten Sie, dass dadurch Prirum aus das TreeMap-Diagramm entfernt. 
  
![Zeigt ausgewählte Fashions Direct](media/end-user-report-filter/power-bi-filter-treemap.png)

> [!TIP]
> Um mehr als ein Filterwert zu einem Zeitpunkt auszuwählen, halten Sie die STRG-Taste aus. Die meisten Filter unterstützen mehrere Elemente auswählen. 

### <a name="reset-filter-to-default"></a>Filter auf Standard zurücksetzen
Wenn Sie aus der alle Änderungen sichern möchten Sie den Filtern, wählen vorgenommen haben **auf Standardwert zurücksetzen** in der oberen Menüleiste.  Dadurch wird der Filter auf den ursprünglichen Zustand, mit dem Bericht wieder *Designer*. 

![Auf Standard zurücksetzen](media/end-user-report-filter/power-bi-reset-to-default.png)
    
### <a name="clear-a-filter"></a>Löschen eines Filters
Es ist nur ein Filter, der festgelegt werden sollen **(alle)** , löschen Sie ihn, indem Sie auf das radierersymbol ![ radierersymbol ](media/end-user-report-filter/power-bi-eraser-icon.png) neben dem Filternamen.
  
<!--  too much detail for consumers

## Types of filters: text field filters
### List mode
Ticking a checkbox either selects or deselects the value. The **All** checkbox can be used to toggle the state of all checkboxes on or off. The checkboxes represent all the available values for that field.  As you adjust the filter, the restatement updates to reflect your choices. 

![list mode filter](media/end-user-report-filter/power-bi-restatement-new.png)

Note how the restatement now says "is Mar, Apr or May".

### Advanced mode
Select **Advanced Filtering** to switch to advanced mode. Use the dropdown controls and text boxes to identify which fields to include. By choosing between **And** and **Or**, you can build complex filter expressions. Select the **Apply Filter** button when you've set the values you want.  

![advanced mode](media/end-user-report-filter/power-bi-advanced.png)

## Types of filters: numeric field filters
### List mode
If the values are finite, selecting the field name displays a list.  See **Text field filters** &gt; **List mode** above for help using checkboxes.   

### Advanced mode
If the values are infinite or represent a range, selecting the field name opens the advanced filter mode. Use the dropdown and text boxes to specify a range of values that you want to see. 

![advanced filter](media/end-user-report-filter/power-bi-dropdown-and-text.png)

By choosing between **And** and **Or**, you can build complex filter expressions. Select the **Apply Filter** button when you've set the values you want.

## Types of filters: date and time
### List mode
If the values are finite, selecting the field name displays a list.  See **Text field filters** &gt; **List mode** above for help using checkboxes.   

### Advanced mode
If the field values represent date or time, you can specify a start/end time when using Date/Time filters.  

![datetime filter](media/end-user-report-filter/pbi_date-time-filters.png)

-->

## <a name="next-steps"></a>Nächste Schritte
[Lernen Sie, wie und warum es zu Kreuzfilterung und -hervorhebung von Visualisierungen auf einer Berichtsseite kommt](end-user-interactions.md)