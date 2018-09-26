---
title: Hinzufügen eines Visuals-, Seiten-, Drillthrough- oder Berichtsfilters zu einem Bericht
description: Hinzufügen eines Seiten-, Visualisierungs- oder Berichtsfilters zu einem Bericht in Power BI
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 05/26/2018
ms.author: maggies
LocalizationGroup: Reports
ms.openlocfilehash: 3758415dc41a5f94419193240d4ce71aa4aca1d8
ms.sourcegitcommit: fb1885da7cf11367660edbf7b7346dc039ee9b5d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/26/2018
ms.locfileid: "47187212"
---
# <a name="add-a-filter-to-a-power-bi-service-report-in-editing-view"></a>Hinzufügen eines Filters zu einem Bericht im Power BI-Dienst (in der Bearbeitungsansicht)
> [!TIP]
> Es wird empfohlen, zuerst den Artikel [Informationen zu Filtern und Hervorhebungen in Power BI-Berichten](power-bi-reports-filters-and-highlighting.md) zu lesen.

Die Beispiele in diesem Artikel drehen sich um den Power BI-Dienst. Allerdings sind die dargestellten Schritte fast identisch mit denen in Power BI Desktop.
> 
> 

## <a name="what-is-the-difference-between-report-filters-in-editing-view-versus-reading-view"></a>Unterschiede zwischen Berichtsfiltern in der Bearbeitungsansicht und in der Leseansicht
Es gibt zwei Modi für die Interaktion mit Berichten: [Leseansicht](consumer/end-user-reading-view.md) und [Bearbeitungsansicht](service-interact-with-a-report-in-editing-view.md).  Es hängt vom Modus ab, in dem Sie sich befinden, welche Filterfunktionen verfügbar sind.

* In der Bearbeitungsansicht können Sie Berichts-, Seiten- und visuelle Filter hinzufügen. Wenn Sie den Bericht speichern, werden die Filter ebenfalls gespeichert. Personen, die den Bericht in der Leseansicht anzeigen, können mit den von Ihnen hinzugefügten Filtern interagieren.
* In der Leseansicht können Sie mit allen Berichts-, Drillthrough-, Seiten- und visuellen Filtern interagieren, die im Bericht bereits vorhanden sind. Sie können jedoch keine neuen Filter hinzufügen. Jedoch werden die Änderungen, die Sie im Bereich „Filter“ vornehmen, mit dem Bericht gespeichert, auch wenn Sie den Bericht in einer mobilen App anzeigen, oder wenn Sie den Bericht verlassen und später zurückkehren.  

> [!NOTE]
> In diesem Artikel wird beschrieben, wie Sie Filter im Bericht **Bearbeitungsansicht** erstellen.  Weitere Informationen zu Filtern in der Leseansicht finden Sie unter [Interagieren mit Filtern und Hervorhebungen in der Leseansicht von Berichten](consumer/end-user-reading-view.md).


## <a name="filters-available-in-the-power-bi-filters-pane"></a>Filter, die im Bereich *Filter* in Power BI verfügbar sind
Der Bereich „Filter“ wird auf der rechten Seite des Zeichenbereichs für den Bericht angezeigt, egal ob Sie den Desktop- oder Power BI-Dienst verwenden. Wenn der Filterbereich nicht angezeigt wird, wählen Sie das Symbol „>“ in der oberen rechten Ecke aus, um ihn zu erweitern.

Es gibt vier Arten von Filtern.

- Ein **Seitenfilter** gilt für Visualisierungen auf der Berichtsseite.     
- Ein **visueller Filter** gilt für ein einzelne Visualisierung auf einer Berichtsseite.    
- Ein **Drillthroughfilter** gilt für eine einzelne Entität in einem Bericht.    
- Ein **Berichtsfilter** gilt für alle Seiten im Bericht.    

    ![Der Bereich „Filter“ in der Leseansicht](media/power-bi-report-add-filter/power-bi-add-filter-reading-view.png)

Da Filter *beibehalten werden*, wenn Sie den Bericht verlassen, behält Power BI die Filter, Slicer und andere Änderungen an der Datenansicht, die Sie vorgenommen haben, bei. Wenn Sie zum Bericht zurückkehren, können Sie also dort weitermachen, wo Sie aufgehört haben. Wenn Sie Ihre Filteränderungen nicht beibehalten möchten, wählen Sie auf der oberen Menüleiste **Auf Standardwert zurücksetzen** aus.

![Schaltfläche „Permanente Filter“](media/power-bi-report-add-filter/power-bi-reset-to-default.png)

## <a name="add-a-filter-to-a-specific-visualization-aka-visual-filter"></a>Hinzufügen eines Filters zu einer bestimmten Visualisierung (Visualisierungsfilter)
Hierfür gibt es zwei Methoden: 

* Fügen Sie einem Feld, das bereits von der Visualisierung verwendet wird, einen Filter hinzu.
* Suchen Sie ein Feld, das noch nicht von der Visualisierung verwendet wird, und fügen Sie dieses Feld direkt dem Bucket **Filter auf visueller Ebene** hinzu.

### <a name="by-filtering-the-fields-already-in-the-visualization"></a>Filtern Sie die Felder, die bereits in der Visualisierung enthalten sind.
1. Öffnen Sie Ihren Bericht in der [Bearbeitungsansicht](consumer/end-user-reading-view.md).
   
   ![](media/power-bi-report-add-filter/power-bi-edit-view.png)
2. Öffnen Sie den Bereich für die Visualisierungen und Filter und den Bereich für die Felder (falls nicht bereits geöffnet).
   
   ![](media/power-bi-report-add-filter/power-bi-display-panes.png)
3. Wählen Sie eine Visualisierung aus, um ihn zu aktivieren. Alle Felder, die vom Visual verwendet werden, sind im Bereich **Felder** angegeben und auch im Bereich **Filter** unter der Überschrift **Filter auf visueller Ebene** aufgeführt.
   
   ![](media/power-bi-report-add-filter/power-bi-default-visual-filter.png)
4. Jetzt wird einem Feld, das bereits von der Visualisierung verwendet wird, ein Filter hinzugefügt. 
   
   * Scrollen Sie zum Bereich **Filter auf visueller Ebene**, und wählen Sie den Pfeil aus, um das Feld zu erweitern, das Sie filtern möchten. In diesem Beispiel wird **StoreNumberName** gefiltert.
     
      ![](media/power-bi-report-add-filter/power-bi-visual-level-filter.png) 
   * Legen Sie für die Filtersteuerelemente entweder **Einfach**, **Erweitert** oder **Top N** fest (siehe [Verwenden von Berichtsfiltern](consumer/end-user-report-filter.md)). In diesem Beispiel wird die einfache Filterung ausgewählt, und neben den Zahlen 10, 11, 15 und 18 wird jeweils ein Häkchen gesetzt.
     
      ![](media/power-bi-report-add-filter/power-bi-basic-filters.png) 
   * Die Visualisierung ändert sich und spiegelt den neuen Filter wider. Wenn Sie Ihren Bericht mit dem Filter speichern, können Leser des Berichts mit dem Filter in der Leseansicht interagieren und Werte auswählen oder löschen.
     
      ![](media/power-bi-report-add-filter/power-bi-filter-effect.png)
5. Fügen wir der Visualisierung nun ein ganz neues Feld als Filter auf visueller Ebene hinzu.
   
   * Wählen Sie im Bereich „Felder“ das Feld aus, das Sie als neuen Filter auf visueller Ebene hinzufügen möchten, und ziehen Sie es in den Bereich **Filter auf visueller Ebene**.  In diesem Beispiel ziehen wir **District Manager** in den Bucket **Filter auf visueller Ebene** und wählen nur „Andrew Ma“ aus. 
     
      ![](media/power-bi-report-add-filter/power-bi-andrew.png)
   * Beachten Sie, dass **District Manager** der Visualisierung selbst *nicht* hinzugefügt wird. Die Visualisierung besteht weiterhin aus **StoreNumberName** als Achse und aus **This Year Sales** als Wert.  
     
      ![](media/power-bi-report-add-filter/power-bi-visualization.png)
   * Die Visualisierung selbst wird nun gefiltert, sodass nur die diesjährigen Verkäufe von Andrew für die angegebenen Geschäfte angezeigt werden.
     
     ![](media/power-bi-report-add-filter/power-bi-filtered-andrew.png)

## <a name="add-a-filter-to-an-entire-page-aka-page-view-filter"></a>Hinzufügen eines Filters für eine komplette Seite (Seitenansichtsfilter)
1. Öffnen Sie Ihren Bericht in der [Bearbeitungsansicht](consumer/end-user-reading-view.md).
2. Öffnen Sie den Bereich für die Visualisierungen und Filter und den Bereich für die Felder (falls nicht bereits geöffnet).
3. Wählen Sie im Bereich „Felder“ das Feld aus, das Sie als neuen Filter auf Seitenebene hinzufügen möchten, und ziehen Sie es in den Bereich **Filter auf Seitenebene**.  
4. Wählen Sie die Werte aus, die Sie filtern möchten, und legen Sie für die Filtersteuerelemente entweder **Einfach** oder **Erweitert** fest (siehe [Verwenden von Berichtsfiltern](consumer/end-user-report-filter.md)).
   
   Alle Visualisierungen auf der Seite, die von diesem Filter beeinflusst werden, werden neu gezeichnet, um die Änderung zu übernehmen. 
   
   ![](media/power-bi-report-add-filter/filterpage.gif)

Wenn Sie Ihren Bericht mit dem Filter speichern, können Leser des Berichts mit dem Filter in der Leseansicht interagieren und Werte auswählen oder löschen.

## <a name="add-a-drillthrough-filter"></a>Hinzufügen eines Drillthroughfilters
Mit Drillthrough im Power BI-Dienst und Power BI Desktop können Sie eine *Ziel*-Berichtseite erstellen, die auf eine bestimmte Entität fokussiert ist, z.B. einen Lieferanten, Kunden oder Hersteller. Nun können Benutzer auf den anderen Berichtseiten mit der rechten Maustaste auf einen Datenpunkt für die Entität klicken und einen Drillthrough für die fokussierte Seite ausführen.

### <a name="create-a-drillthrough-filter"></a>Erstellen eines Drillthroughfilters
Öffnen Sie das Beispiel zur Kundenrentabilität in der Bearbeitungsansicht. Angenommen, Sie benötigen eine Seite, die auf Managementgeschäftsbereiche fokussiert ist.   

1. Fügen Sie dem Bericht eine neue Seite hinzu, und benennen Sie diese **Team Executive** (Teammanager). Dies wird die *Ziel*-Drillthroughseite.
2. Fügen Sie Visualisierungen zum Verfolgen von Schlüsselmetriken für die Geschäftsbereiche der Teammanager hinzu.    
3. Fügen Sie dem Bereich „Drillthroughfilter“ **Executive > Executive Name** (Führungskraft > Name der Führungskraft) hinzu.    
   
    ![](media/power-bi-report-add-filter/power-bi-drillthrough-filter.png)
   
    Beachten Sie, dass Power BI der Berichtseite einen Zurück-Pfeil hinzufügt.  Wenn der Benutzer auf den Zurück-Pfeil klickt, kehrt er zur *Ausgangs*berichtseite zurück – zu der Seite, auf der er den Drillthrough ausgewählt hat. Der Zurück-Pfeil kann nur in der Leseansicht verwendet werden.
   
     ![](media/power-bi-report-add-filter/power-bi-back-arrow.png)

### <a name="use-the-drillthrough-filter"></a>Verwenden des Drillthroughfilters
Im Folgenden wird beschrieben, wie der Drillthroughfilter funktioniert.

1. Starten Sie auf der Berichtseite **Team-Scorecard**.    
2. Angenommen, Sie sind Andrew Ma und möchten die „Team Executive“-Berichtseite so gefiltert anzeigen, dass nur Ihre Daten enthalten sind.  Klicken Sie im Flächendiagramm oben rechts auf einen grünen Datenpunkt, um die Menüoption „Drillthrough“ zu öffnen.
   
    ![](media/power-bi-report-add-filter/power-bi-drillthrough.png)
3. Wählen Sie **Drillthrough > Team Executive** aus, um einen Drillthrough zur Berichtseite **Team Executive** (Teammanager) durchzuführen. Die Seite wird so gefiltert, dass Informationen zum Datenpunkt angezeigt werden, auf den Sie mit der rechten Maustaste geklickt haben; in diesem Fall „Andrew Ma“. An die Drillthroughberichtseite wird nur das Feld übergeben, das sich im Bereich „Drillthroughfilter“ befindet.  
   
    ![](media/power-bi-report-add-filter/power-bi-drillthrough-executive.png)

## <a name="add-a-filter-to-an-entire-report-aka-report-filter"></a>Hinzufügen eines Filters für einen gesamten Bericht (Berichtsfilter)
1. Öffnen Sie Ihren Bericht in der [Bearbeitungsansicht](consumer/end-user-reading-view.md).
2. Öffnen Sie den Bereich für die Visualisierungen und Filter und den Bereich für die Felder (falls nicht bereits geöffnet).
3. Wählen Sie im Bereich „Felder“ das Feld aus, das Sie als neuen Filter auf Berichtsstufe hinzufügen möchten, und ziehen Sie es in den Bereich **Berichtsstufenfilter**.  
4. Wählen Sie die zu filternden Werte aus (siehe [Verwenden von Berichtsfiltern](consumer/end-user-report-filter.md)).

    Die Visuals auf der aktiven Seite und auf allen Seiten des Berichts ändern sich, um den neuen Filter widerzuspiegeln. Wenn Sie Ihren Bericht mit dem Filter speichern, können Leser des Berichts mit dem Filter in der Leseansicht interagieren und Werte auswählen oder löschen.

1. Wählen Sie den Zurück-Pfeil aus, um zur vorherigen Berichtseite zurückzukehren.

## <a name="considerations-and-troubleshooting"></a>Zu beachtende Aspekte und Problembehandlung

- Es gibt Situationen, in denen Ihre Filters auf Visualisierungsebene und auf Seitenebene unterschiedliche Ergebnisse zurückgeben.  Wenn Sie beispielsweise einen Filter auf Visualisierungsebene hinzufügen, filtert Power BI die aggregierten Ergebnisse.  Die standardmäßige Aggregatfunktion ist „Summe“, Sie können jedoch den [Aggregattyp ändern](service-aggregates.md).  

    Wenn Sie dann einen Filter auf Seitenebene hinzufügen, filtert Power BI ohne Aggregieren.  Dies liegt daran, dass eine Seite über viele Visualisierungen verfügen kann, die jeweils unterschiedliche Aggregationstypen verwenden.  Daher wird der Filter auf jede Datenzeile angewendet.

- Wenn der Bereich „Felder“ nicht angezeigt wird, stellen Sie sicher, dass Sie die [Bearbeitungsansicht](service-interact-with-a-report-in-editing-view.md) des Berichts geöffnet haben.    
- Wenn Sie viele Änderungen an den Filtern vorgenommen haben und zu den Standardeinstellungen des Berichtsautors zurückkehren möchten, wählen Sie auf der oberen Menüleiste **Auf Standardwert zurücksetzen** aus.

## <a name="next-steps"></a>Nächste Schritte
 [Verwenden von Berichtsfiltern](consumer/end-user-report-filter.md)

  [Filter und Hervorhebungen in Berichten](power-bi-reports-filters-and-highlighting.md)

[Interagieren mit Filtern und Hervorhebungen in der Leseansicht von Berichten](consumer/end-user-reading-view.md)

[Ändern der Kreuzfilterung und -hervorhebung von Berichtsvisualisierungen](consumer/end-user-interactions.md)

Weitere Fragen? [Wenden Sie sich an die Power BI-Community](http://community.powerbi.com/)

