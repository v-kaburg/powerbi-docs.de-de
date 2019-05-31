---
title: Die neue Filteroberfläche in Power BI-Berichten (Vorschau)
description: Filter in Power BI erhalten eine neue Funktionalität und ein neues Design.
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 05/16/2019
ms.author: maggies
LocalizationGroup: Reports
ms.openlocfilehash: 0a9e4986ae2f686eb8a8fd2d9fa07b169661ce60
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2019
ms.locfileid: "65853474"
---
# <a name="the-new-filter-experience-in-power-bi-reports-preview"></a>Die neue Filteroberfläche in Power BI-Berichten (Vorschau)

Filter in Power BI wurden neue Funktionen und ein neues Design. Wenn Sie sich auf die neue Filter-Benutzeroberfläche entscheiden, können Sie den Bereich "Filter", der Rest des Berichts aussehen formatieren. Sie können Sperren und sogar Filter ausblenden. Wenn Sie den Bericht zu entwerfen, sehen Sie nicht mehr die alte Bereich "Filter" in den Bereich "Visualisierungen". Sie werden alle Filter bearbeiten und die Formatierung in einem einzelnen Bereich "Filter". 

![Neue Filteroberfläche](media/power-bi-report-filter-preview/power-bi-filter-reading.png)

> [!NOTE]
> Die neue Filterfunktion befindet sich in der Vorschau. Neue Builds überschreiben möglicherweise Ihre festgelegte Formatierung.

Als einen Berichts-Designer ist hier was Sie tun können, in der neuen einzelnen Bereich "Filter":

- Hinzufügen und Entfernen von Feldern zu filtern. 
- Ändern Sie den Zustand des Filters.
- Formatieren Sie und passen Sie den Bereich "Filter" so an, dass das Gefühl, Teil des Berichts.
- Sie können festlegen, ob der Filterbereich beim Öffnen des Berichts durch den Nutzer standardmäßig geöffnet oder ausgeblendet werden soll.
- Ausblenden der gesamte Bereich "Filter" oder bestimmte Filter, die Sie nicht, dass Nutzern des Berichts angezeigt möchten.
- Steuern Sie und sogar Lesezeichen Sie die Sichtbarkeit, öffnen, und dem reduzierten Zustand, der der neue Bereich "Filter".
- Sie können Filter sperren, die die Nutzer nicht bearbeiten sollen.

Mit der neuen Oberfläche Filter können Benutzer von Berichten über jedes visuelle Element, um eine schreibgeschützte Liste aller Filter oder Slicer, die Auswirkungen auf das visuelle auch zeigen.

![Liste der Filter für ein visual](media/power-bi-report-filter-preview/power-bi-filter-visual.png)

## <a name="turn-on-the-new-filter-experience"></a>Aktivieren der neuen Filteroberfläche 

Sie aktivieren die neue Benutzeroberfläche in Power BI Desktop. Anschließend können Sie die Filter dort oder im Power BI-Dienst ändern (https://app.powerbi.com). Die neue Filteroberfläche befindet sich in der Vorschau, deshalb muss sie zunächst in Power BI Desktop aktiviert werden. Wenn Sie beginnen, indem Sie einen Bericht im Power BI-Dienst erstellen, darf dieser keine neuen Filter aufweisen.

### <a name="turn-on-new-filters-for-all-new-reports"></a>Aktivieren der neuen Filter für alle neuen Berichte

1. Wählen Sie in Power BI Desktop**Datei** > **Optionen und Einstellungen** > **Optionen** > **Vorschaufeatures** aus, und aktivieren Sie anschließend das Kontrollkästchen **Neue Filteroberfläche**. 
2. Starten Sie Power BI Desktop neu, um die neue Filteroberfläche in allen neuen Berichten anzuzeigen.

Nachdem Sie Power BI Desktop neu gestartet haben, wird die neue Filteroberfläche standardmäßig für alle neu erstellten Berichte aktiviert.  

### <a name="turn-on-new-filters-for-an-existing-report"></a>Aktivieren der neuen Filter für einen vorhandenen Bericht

Sie können die Filter auch für vorhandene Berichte aktivieren.

1. Wählen Sie in Power BI Desktop in einem vorhandenen Bericht **Datei** > **Optionen und Einstellungen** > **Optionen** aus.
2. In der linken Navigationsleiste unter **aktuelle Datei**Option **Berichtseinstellungen**.
3. Unter **Filtern Erfahrung**Option **aktivieren Sie den aktualisierten Filterbereich, und Filter in der visual-Header für diesen Bericht anzeigen**.

## <a name="view-filters-for-a-visual-in-reading-mode"></a>Anzeigen von Filtern für ein Visual im Lesemodus

Bewegen Sie im Lesemodus den Mauszeiger über das Filtersymbol, um für ein Visual ein Popup mit allen Filtern, Slicern usw. anzuzeigen, die sich auf das Visual auswirken. Die Formatierung des im Popupfenster ist identisch mit der Filter-Bereich-Formatierung. 

![Filter, die sich auf ein Visual auswirken](media/power-bi-report-filter-preview/power-bi-filter-per-visual.png)

Diese Filtertypen werden in der Ansicht angezeigt: 
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

## <a name="build-the-new-filters-pane"></a>Erstellen Sie den neuen Bereich "Filter"

Nach der Aktivierung der neuen Bereich "Filter" sehen Sie es rechts neben der Berichtsseite, die standardmäßig basierend auf Ihrer aktuellen Einstellungen formatiert. Sie verwenden den neuen Bereich "Filter" So konfigurieren Sie die Filter enthalten, und Aktualisieren von vorhandenen Filter im neuen Bereich an. Der neue Bereich "Filter" zeigt an, welche Ihrer Nutzern des Berichts angezeigt werden, wenn Sie Ihren Bericht veröffentlichen. 

1. Standardmäßig sehen Ihre Nutzern des Berichts den Bereich "Filter" aus. Wenn Sie nicht, dass sie zum anzeigen möchten, aktivieren Sie das Augensymbol neben **Filter**.

    ![Filter-Augen-Symbol für Power BI](media/power-bi-report-filter-preview/power-bi-filter-eye.png)

2. Um zu beginnen, erstellen Ihre neue Bereich "Filter", entweder als Seite der Visualisierung ziehen Sie relevante Felder in der neue Bereich "Filter", oder auf Berichtsebene.

Wenn Sie eine Visualisierung auf einem Zeichenbereich des Berichts hinzufügen, fügt Power BI automatisch einen Filter auf den Bereich "Filter" für jedes Feld im visuellen Element. 

## <a name="lock-or-hide-filters"></a>Sperren oder Ausblenden von Filtern

Sie können einzelne Filterkarten sperren oder ausblenden. Wenn Sie einen Filter sperren, können Ihre Berichtnutzer den Filter sehen, aber nicht ändern. Wenn Sie einen Filter ausblenden, können die Berichtnutzer den Filter nicht einmal sehen. Das Ausblenden von Filterkarten kann insbesondere dann nützlich sein, wenn Sie Datenbereinigungsfilter ausblenden möchten, die NULL-Werte oder unerwartete Werte ausschließen. 

- Wählen Sie in der neue Bereich "Filter", oder deaktivieren Sie die **Zamknout filtr** oder **ausblenden Filter** Symbole in einer Filterkarte.

   ![Ausblenden oder Sperren von Filtern](media/power-bi-report-filter-preview/power-bi-filter-lock-hide.png)

Wie Sie diese Einstellungen ein- und ausschalten in der neue Bereich "Filter" aktiviert haben, sehen Sie die Änderungen in den Bericht an. Ausgeblendete Filter werden im Filterpopup für ein Visual nicht angezeigt.

Sie können auch den neuen Zustand der Filter-Bereich zur Übertragung mit Ihrem Bericht Lesezeichen konfigurieren. Der Zustand (geöffnet/geschlossen) und der Sichtbarkeitsstatus können als Lesezeichen festgelegt werden.
 
## <a name="format-the-new-filters-pane"></a>Formatieren des neuen Filterbereichs

Ein großer Teil dieser neuen Oberfläche ist, dass Sie den Bereich "Filter", das Erscheinungsbild des Berichts entsprechend formatieren können. Sie können den Bereich "Filter" für jede Seite im Bericht unterschiedlich formatieren. Diese Elemente können formatiert werden: 

- Hintergrundfarbe
- Hintergrundtransparenz
- Rahmen, ein- oder ausschalten
- Rahmenfarbe
- Titel und Header Schriftart, Farbe und Größe

Für Filterkarten können Sie außerdem diese Elemente formatieren – je nachdem, ob sie angewendet wurden (auf einen Wert festgelegt) oder verfügbar (deaktiviert) sind: 

- Hintergrundfarbe
- Hintergrundtransparenz
- Rahmen: ein/aus
- Rahmenfarbe
- Schriftart, Farbe und Textgröße
- Farbe für Eingabefeld

### <a name="format-the-filters-pane-and-cards"></a>Formatieren Sie den Bereich "Filter" und Karten

1. Klicken Sie im Bericht auf den Bericht selbst oder den Hintergrund (*Hintergrundbild*), und wählen Sie dann im Bereich **Visualisierungen** die Einstellung **Format** aus. 
    Optionen für die Formatierung der Berichtsseite, des Hintergrundbilds an, und auch den Bereich "Filter" und Filter Karten angezeigt.

    ![Formatierungssymbol auswählen](media/power-bi-report-filter-preview/power-bi-filter-format.png)    

1. Erweitern Sie den **Filterbereich**, um die Farbe für den Hintergrund, das Symbol und den linken Rahmen festzulegen und die Berichtseite zu vervollständigen.

    ![Filterbereich erweitern](media/power-bi-report-filter-preview/power-bi-filter-format-pane-font.png)

1. Erweitern Sie **Filterkarten**, um Farbe und Rahmen für **Verfügbar** und **Angewendet** festzulegen. Wenn Sie unterschiedliche Farben für verfügbare und angewendete Karten festlegen, ist offensichtlich, welche Filter angewendet wurden. 
  
    ![Filterkarte erweitern](media/power-bi-report-filter-preview/power-bi-filter-format-card-font.png)

## <a name="theming-for-filter-pane"></a>Design für den Bereich "Filter"
Sie können die Standardeinstellung für den Filterbereich jetzt mit der Designdatei ändern. Hier ist ein Codeausschnitt als Beispiel Design für Ihre ersten Schritte:

 
```
"outspacePane": [{ 

"backgroundColor": {"solid": {"color": "#0000ff"}}, 

"foregroundColor": {"solid": {"color": "#00ff00"}}, 

"transparency": 50, 

"titleSize": 35, 

"headerSize": 8, 

"fontFamily": "Georgia", 

"border": true, 

"borderColor": {"solid": {"color": "#ff0000"}} 

}], 

"filterCard": [ 

{ 

"$id": "Applied", 

"transparency": 0, 

"backgroundColor": {"solid": {"color": "#ff0000"}}, 

"foregroundColor": {"solid": {"color": "#45f442"}}, 

"textSize": 30, 

"fontFamily": "Arial", 

"border": true, 

"borderColor": {"solid": {"color": "#ffffff"}}, 

"inputBoxColor": {"solid": {"color": "#C8C8C8"}} 

}, 

{ 

"$id": "Available", 

"transparency": 40, 

"backgroundColor": {"solid": {"color": "#00ff00"}}, 

"foregroundColor": {"solid": {"color": "#ffffff"}}, 

"textSize": 10, 

"fontFamily": "Times New Roman", 

"border": true, 

"borderColor": {"solid": {"color": "#123456"}}, 

"inputBoxColor": {"solid": {"color": "#777777"}} 

}] 
```

## <a name="sort-the-filter-pane"></a>Sortieren Sie den Bereich "Filter"

Benutzerdefinierte Sortierung-Funktionalität ist Teil der neuen Oberfläche des Filter-Bereich. Berichtersteller Drag & drop können Filter, um sie in der Reihenfolge neu anzuordnen, die sie wünschen.

![Ordnen Sie die Sortierreihenfolge für filter](media/power-bi-report-filter-preview/power-bi-filter-sort.gif)

Die Standardsortierreihenfolge ist für Filter alphabetisch. Um benutzerdefinierte Sortiermodus starten möchten, ziehen Sie einfach alle Filter zu einer neuen Position. Sie können nur Filter innerhalb der Ebene sortieren, die für die Sie – z. B. einen Filter auf visueller Ebene, Seitenebene oder Berichtsebene geltende.

## <a name="filters-pane-scaling"></a>Filtert Skalierung im Bereich

Der neue Bereich "Filter" skaliert mit der Berichtsseite und visuellen Elementen, sodass die Berichtsseite und filtert im Bereich bleiben im Verhältnis miteinander.

## <a name="improved-filters-pane-accessibility"></a>Verbesserte Barrierefreiheit der Filter-Bereich

Wir haben die Navigation per Tastatur für den neuen Bereich "Filter" verbessert. Sie können die TAB-Taste in jeden Teil der Bereich "Filter" und verwenden den Kontextschlüssel auf Ihrer Tastatur oder UMSCHALT + F10, um das Kontextmenü zu öffnen.

![Barrierefreiheit der Filter-Bereich](media/power-bi-report-filter-preview/power-bi-filter-accessible.png)

## <a name="rename-filters"></a>Benennen Sie Filter
Wenn Sie den Bereich "Filter" Bearbeiten, können Sie den Titel aus, um ihn zu bearbeiten doppelklicken. Das Umbenennen ist nützlich, wenn Sie die Filterkarte, um mehr Sinn für die Endbenutzer aktualisieren möchten. Denken Sie daran, die Umbenennen der Filterkarte ist *nicht* benennen Sie den Anzeigenamen des Felds in der Feldliste. Es ändert nur den Anzeigenamen, die in der Filterkarte verwendet.

![Benennen Sie einen filter](media/power-bi-report-filter-preview/power-bi-filter-rename.png)

## <a name="restrict-changes-to-filter-type"></a>Einschränken von Änderungen am Typ filtern

Klicken Sie unter den Filtern treten Sie auf, Teil der Berichtseinstellungen, die Sie haben die Möglichkeit, die steuern, wenn Benutzer den Filtertyp ändern können.

![Einschränken der Filtertyp ändern](media/power-bi-report-filter-preview/power-bi-filter-restrict-change.png)

## <a name="next-steps"></a>Nächste Schritte

Probieren Sie die neue Filteroberfläche aus! Geben Sie uns Feedback für diese Funktion und wie wir weiter, verbessern können auf die [Power BI Ideas Site](https://ideas.powerbi.com/forums/265200-power-bi). 

- [Verwenden von Berichtsfiltern](consumer/end-user-report-filter.md)
- [Filter und Hervorhebungen in Berichten](power-bi-reports-filters-and-highlighting.md)

Weitere Fragen? [Wenden Sie sich an die Power BI-Community](http://community.powerbi.com/)

