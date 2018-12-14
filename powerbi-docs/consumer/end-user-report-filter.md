---
title: Hinzufügen eines Filters zu einem Bericht
description: Hinzufügen eines Filters für einen Bericht im Power BI-Dienst für Kunden
author: mihart
manager: kvivek
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 12/06/2018
ms.author: mihart
LocalizationGroup: Reports
ms.openlocfilehash: ea219071b475bf5bb9123e1aa3bbaca412507a8e
ms.sourcegitcommit: cd85d88fba0d9cc3c7a4dc03d2f35d2bd096759b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/12/2018
ms.locfileid: "53280763"
---
# <a name="take-a-tour-of-the-report-filters-pane"></a>Überblick über den Berichtsbereich „Filter“
In diesem Artikel sehen wir uns den Berichtsbereich „Filter“ im Power BI-Dienst genauer an.

Es gibt viele verschiedene Arten von Datenfiltern in Power BI. Lesen Sie den Artikel [Informationen zu Filtern und Hervorhebungen](../power-bi-reports-filters-and-highlighting.md).

![Bericht im Browser](media/end-user-report-filter/power-bi-browser.png)

## <a name="working-with-the-report-filters-pane"></a>Arbeiten mit dem Bereich „Filter“ in Berichten
Wenn ein Kollege einen Bericht mit Ihnen teilt, suchen Sie immer nach dem Bereich **Filter**. Manchmal befindet er sich zugeklappt am rechten Rand des Berichts. Klicken Sie darauf, um ihn aufzuklappen.   

![Bericht im Browser](media/end-user-report-filter/power-bi-expanded.png)

Der Bereich „Filter“ enthält Filter, die dem Bericht durch den Berichts-*Designer* hinzugefügt wurden. *Kunden* wie Sie können mit den Filtern interagieren und Ihre Änderungen speichern, aber dem Bericht keine neuen Filter hinzufügen. Auf dem obigen Screenshot hat der Designer beispielsweise zwei Filter auf Seitenebene hinzugefügt: „Segment“ und „Year“. Sie können mit diesen Filtern interagieren und sie ändern, Sie können jedoch keinen dritten Filter auf Seitenebene hinzufügen.

Im Power BI-Dienst speichern Berichte alle von Ihnen im Bereich „Filter“ vorgenommen Veränderungen, und diese Veränderungen werden in der mobilen Version des Berichts übernommen. Klicken Sie auf der oberen Menüleiste auf **Auf Standardwert zurücksetzen**, um den Bereich „Filter“ auf den Standard zurückzusetzen.     

## <a name="open-the-filters-pane"></a>Öffnen Sie den Bereich „Filter“.
Wenn ein Bericht geöffnet ist, wird der Bereich „Filter“ auf der rechten Seite des Berichtszeichenbereichs angezeigt. Wenn der Bereich nicht angezeigt wird, können Sie ihn mit dem Pfeil in der oberen rechten Ecke erweitern.  

In diesem Beispiel arbeiten wir mit einer Visualisierung mit sechs Filtern. Auch die Berichtsseite verfügt über Filter, die Sie unter der Überschrift **Seitenfilter** finden. Es ist ein [Drillthrough-Filter](../power-bi-report-add-filter.md) vorhanden, und der gesamte Bericht weist ebenfalls einen Filter auf:  **Geschäftsjahr** ist 2013 oder 2014.

![Liste der Filter](media/end-user-report-filter/power-bi-filter-list.png)

Neben einigen Filtern sehen Sie das Wort **Alle**; dies bedeutet, dass sämtliche Werte in den Filter eingeschlossen werden.  Beispiel: **Chain(Alle)** (siehe Screenshot oben) zeigt an, dass diese Berichtsseite Informationen über alle Ketten enthält.  Andererseits können wir der Angabe **Geschäftsjahr ist 2013 oder 2014** entnehmen, dass der Bericht ausschließlich Informationen aus den Geschäftsjahren 2013 und 2014 umfasst.

Jeder, der den Bericht aufruft, kann auch mit den Filtern interagieren.

- Durchsuchen Sie Filter auf Seiten-, Visual-, Berichts- oder Drillthroughebene, um den gewünschten Wert zu suchen und auszuwählen. 

    ![Suche in einem Filter](media/end-user-report-filter/power-bi-filter-search.png)

- Einzelheiten zum Filter können angezeigt werden, indem mit dem Cursor auf den Pfeil neben dem Filter gezeigt und dieser ausgewählt wird.
  
   ![Zeigt ausgewählte Lindseys](media/end-user-report-filter/power-bi-expan-filter.png)
* Sie können den Filter anpassen, indem Sie z.B. **Lindseys** in **Fashions Direct** ändern.
  
     ![Zeigt ausgewählte Fashions Direct](media/end-user-report-filter/power-bi-filter-chain.png)

* Setzen Sie die Filter auf ihren Ausgangszustand zurück, indem Sie auf **Auf Standardwert zurücksetzen** in der oberen Menüleiste klicken.    
    ![Auf Standardwert zurücksetzen](media/end-user-report-filter/power-bi-reset-to-default.png)
    
* Löschen Sie den Filter, indem Sie das **x** neben dem Filternamen auswählen.
  
    ![x hervorgehoben](media/end-user-report-filter/power-bi-delete-filter.png)

  Wenn Sie einen Filter löschen, wird nur der Filter aus der Liste entfernt. Die Informationen des Berichts bleiben selbstverständlich erhalten.  Beispiel: Wenn Sie den Filter **Geschäftsjahr gleich 2013 oder 2014** löschen, bleiben die Informationen zum Geschäftsjahr intakt. Da der Filter entfernt wurde, ist der Bericht dann allerdings nicht mehr auf die Geschäftsjahre 2013 und 2014 eingeschränkt. Vielmehr werden alle Geschäftsjahre, die in den Daten enthalten sind, angezeigt.  Sobald Sie einen Filter löschen, können Sie ihn nicht mehr anpassen, da er aus der Liste entfernt wird. Daher wird empfohlen, den Filter mit dem Radierersymbol ![Radierersymbol](media/end-user-report-filter/power-bi-eraser-icon.png) zu löschen.
  
  



## <a name="clear-a-filter"></a>Löschen eines Filters
 Klicken Sie im erweiterten oder Standard-Filtermodus auf das Radierersymbol  ![Radierersymbol](media/end-user-report-filter/pbi_erasericon.jpg) , um den Filter zu löschen. 


## <a name="types-of-filters-text-field-filters"></a>Arten von Filtern: Textfeldfilter
### <a name="list-mode"></a>Listenmodus
Das Aktivieren eines Kontrollkästchens aktiviert oder deaktiviert den Wert. Das Kontrollkästchen **Alle** kann verwendet werden, um den Status aller Kontrollkästchen ein- und auszuschalten. Die Kontrollkästchen stellen die verfügbaren Werte für dieses Feld dar.  Wenn Sie den Filter anpassen, wird er mit Ihrer Auswahl aktualisiert. 

![Listenmodus-Filter](media/end-user-report-filter/power-bi-restatement-new.png)

Beachten Sie, das die Anpassung jetzt „is Mar, Apr or May“ angibt.

### <a name="advanced-mode"></a>Erweiterter Modus
Wählen Sie **Erweiterte Filterung** aus, um in den erweiterten Modus zu wechseln. Verwenden Sie die Dropdownsteuerelemente und Textfelder, um die einzubeziehenden Felder zu identifizieren. Durch die Wahl zwischen **Und** und **Oder**können Sie komplexe Filterausdrücke erstellen. Wählen Sie die Schaltfläche **Filter anwenden** , wenn Sie die Werte wie gewünscht festgelegt haben.  

![Erweiterter Modus](media/end-user-report-filter/power-bi-advanced.png)

## <a name="types-of-filters-numeric-field-filters"></a>Arten von Filtern: Nummernfeldfilter
### <a name="list-mode"></a>Listenmodus
Bei endlichen Werten wird beim Auswählen des Feldnamens eine Liste angezeigt.  Unter **Textfeldfilter** &gt; **Listenmodus** oben finden Sie Hilfe zur Verwendung von Kontrollkästchen.   

### <a name="advanced-mode"></a>Erweiterter Modus
Wenn die Werte unendlich sind oder einen Bereich darstellen, wird beim Auswählen des Feldnamens der erweiterte Filtermodus geöffnet. Verwenden Sie die Dropdownliste und Textfelder, um den Bereich von Werten anzugeben, die Sie anzeigen möchten. 

![Erweiterter Filter](media/end-user-report-filter/power-bi-dropdown-and-text.png)

Durch die Wahl zwischen **Und** und **Oder**können Sie komplexe Filterausdrücke erstellen. Wählen Sie die Schaltfläche **Filter anwenden** , wenn Sie die Werte wie gewünscht festgelegt haben.

## <a name="types-of-filters-date-and-time"></a>Arten von Filtern: Datum und Uhrzeit
### <a name="list-mode"></a>Listenmodus
Bei endlichen Werten wird beim Auswählen des Feldnamens eine Liste angezeigt.  Unter **Textfeldfilter** &gt; **Listenmodus** oben finden Sie Hilfe zur Verwendung von Kontrollkästchen.   

### <a name="advanced-mode"></a>Erweiterter Modus
Wenn die Feldwerte Datum oder Uhrzeit darstellen, können Sie bei der Verwendung von Datums-/Uhrzeitfiltern eine Start- bzw. Endzeit angeben.  

![Datum/Uhrzeit-Filter](media/end-user-report-filter/pbi_date-time-filters.png)


## <a name="next-steps"></a>Nächste Schritte
[Lernen Sie, wie und warum es zu Kreuzfilterung und -hervorhebung von Visualisierungen auf einer Berichtsseite kommt](end-user-interactions.md)