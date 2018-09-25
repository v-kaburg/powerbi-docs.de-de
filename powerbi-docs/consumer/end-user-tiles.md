---
title: Dashboardkacheln im Power BI-Dienst
description: Alle wichtigen Informationen über Dashboardkacheln in Power BI. Dies schließt Kacheln ein, die über SQL Server Reporting Services (SSRS) erstellt wurden.
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 08/21/2018
ms.author: mihart
LocalizationGroup: Dashboards
ms.openlocfilehash: f0ff1d9a49e0566119df2c790ad618700c9a9ca3
ms.sourcegitcommit: 70192daf070ede3382ac13f6001e0c8b5fb8d934
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2018
ms.locfileid: "46565450"
---
# <a name="dashboard-tiles-in-power-bi"></a>Dashboardkacheln in Power BI
Dashboards und Dashboardkacheln sind ein Feature des Power BI-Diensts und nicht von Power BI Desktop. Obwohl Dashboardkacheln nicht in Power BI Mobile erstellt oder angeheftet werden können, lassen sie sich dort [anzeigen und freigeben](mobile/mobile-tiles-in-the-mobile-apps.md). Außerdem können Sie in Power BI Mobile [mit der iPhone-App Grafiken zu Ihrem Dashboard hinzufügen](mobile/mobile-iphone-app-get-started.md).

## <a name="dashboard-tiles"></a>Dashboardkacheln
![Power BI-Dashboard](./media/end-user-tiles/power-bi-dashboard.png)

Eine Kachel ist eine Momentaufnahme Ihrer Daten, die an das Dashboard geheftet ist. Eine Kachel kann aus einem Bericht, einem Dataset, einem Dashboard, aus dem Q&A-Feld, aus Excel, aus SSRS (SQL Server Reporting Services) und noch mehr erstellt werden.  Der Screenshot zeigt viele verschiedene Kacheln, die an ein Dashboard angeheftet sind.

Über das Anheften hinaus können mithilfe der Option [Kachel hinzufügen](../service-dashboard-add-widget.md) eigenständige Kacheln direkt auf dem Dashboard erstellt werden. Eigenständige Kacheln können Textfelder, Bilder, Videos, Streamingdaten und Webinhalte enthalten.

Benötigen Sie Hilfe, um die Grundkomponenten zu verstehen, aus denen Power BI besteht?  Weitere Informationen finden Sie unter [Power BI – Grundkonzepte](end-user-basic-concepts.md).

> [!NOTE]
> Wenn sich die ursprüngliche Visualisierung ändert, die zum Erstellen der Kachel verwendet wurde, ändert sich die Kachel nicht.  Wenn Sie beispielsweise ein Liniendiagramm aus einem Bericht angeheftet haben und dann das Liniendiagramm in ein Balkendiagramm ändern, wird auf der Dashboardkachel weiterhin ein Liniendiagramm angezeigt. Die Daten werden aktualisiert, der Visualisierungstyp hingegen nicht.
> 
> 

## <a name="pin-a-tile-from"></a>Anheften einer Kachel aus...
Es gibt viele verschiedene Möglichkeiten, eine Kachel zu Ihrem Dashboard hinzuzufügen (anzuheften). Kacheln können angeheftet werden aus:

* [Power BI Q&A](../service-dashboard-pin-tile-from-q-and-a.md)
* [einem Bericht](../service-dashboard-pin-tile-from-report.md)
* [einem anderen Dashboard](../service-pin-tile-to-another-dashboard.md)
* [einer Excel-Arbeitsmappe auf OneDrive for Business](../service-dashboard-pin-tile-from-excel.md)
* [Power BI Publisher für Excel](../publisher-for-excel.md)
* [Schnelle Einblicke](end-user-insights.md)
* [SSRS](https://msdn.microsoft.com/library/mt604784.aspx)

Eigenständige Kacheln für Bilder, Textfelder, Videos, Streamingdaten und Webinhalte können mit [Kachel hinzufügen](../service-dashboard-add-widget.md) direkt auf dem Dashboard erstellt werden.

  ![Symbol „Kachel hinzufügen“](./media/end-user-tiles/add_widgetnew.png)

## <a name="interacting-with-tiles-on-a-dashboard"></a>Interagieren mit Kacheln in einem Dashboard
### <a name="move-and-resize-a-tile"></a>Verschieben und Ändern der Größe einer Kachel
Wählen Sie eine Kachel aus, und [verschieben Sie sie auf dem Dashboard](../service-dashboard-edit-tile.md). Zeigen Sie auf eine Kachel, und wählen Sie den Ziehpunkt ![Ziehpunkt](./media/end-user-tiles/resize-handle.jpg) aus, um ihre Größe zu ändern.

### <a name="hover-over-a-tile-to-change-the-appearance-and-behavior"></a>Zeigen Sie auf eine Kachel, um Aussehen und Verhalten zu ändern.
1. Zeigen Sie auf die Kachel, um die Auslassungspunkte anzuzeigen.
   
    ![Kachel „Auslassungspunkte“](./media/end-user-tiles/ellipses_new.png)
2. Wählen Sie die Auslassungspunkte (...) aus, um das Aktionsmenü zu öffnen.
   
    ![Symbol „Auslassungspunkte“](./media/end-user-tiles/power-bi-tile-menu.png)
   
    Hier können Sie Folgendes tun:
   
   * [Den Bericht öffnen, mit dem diese Kachel erstellt wurde ](end-user-reports.md) ![Symbol „Bericht“](./media/end-user-tiles/chart-icon.jpg)  
   
   * [Das Arbeitsblatt öffnen, mit dem diese Kachel erstellt wurde ](end-user-reports.md) ![Symbol „Arbeitsblatt“](./media/end-user-tiles/power-bi-open-worksheet.png)  
     
    * [Im Fokusmodus anzeigen ](end-user-focus.md) ![Symbol „Fokus“](./media/end-user-tiles/fullscreen-icon.jpg)  
     * [Die auf der Kachel verwendeten Daten exportieren](end-user-export-data.md) ![Symbol „Daten exportieren“](./media/end-user-tiles/export-icon.png)
     * [Titel und Untertitel bearbeiten, Link hinzufügen](../service-dashboard-edit-tile.md) ![Symbol „Bearbeiten“](./media/end-user-tiles/pencil-icon.jpg)
     * [Einblicke ausführen ](end-user-insights.md) ![Symbol „Einblicke“](./media/end-user-tiles/power-bi-insights.png)
     * [Anheften der Kachel an ein anderes Dashboard](../service-pin-tile-to-another-dashboard.md)
       ![Stecknadelsymbol](./media/end-user-tiles/pin-icon.jpg)
     * [Kachel entfernen](../service-dashboard-edit-tile.md)
     ![Symbol „Löschen“](./media/end-user-tiles/trash-icon.png)
3. Wählen Sie zum Schließen des Aktionsmenüs eine leere Fläche im Zeichenbereich aus.

### <a name="select-click-a-tile"></a>Auswählen einer Kachel
Wenn Sie eine Kachel auswählen, hängt das anschließenden Vorgehen davon ab, wie die Kachel erstellt wurde und ob sie über einen [benutzerdefinierten Link](../service-dashboard-edit-tile.md) verfügt. Wenn sie einen benutzerdefinierten Link aufweist, bringt Sie das Auswählen der Kachel zum Ziel dieses Links. Andernfalls gelangen Sie nach Auswählen der Kachel zu dem Bericht, der Excel Online-Arbeitsmappe, dem lokalen SSRS-Bericht oder der Q&A-Frage, der/die zum Erstellen der Kachel verwendet wurde.

> [!NOTE]
> Eine Ausnahme sind Videokacheln, die direkt auf dem Dashboard mit **Kachel hinzufügen** erstellt wurden. Bei Auswählen einer Videokachel (die auf diese Weise erstellt wurde) wird das Video direkt auf dem Dashboard wiedergegeben.   
> 
> 

## <a name="considerations-and-troubleshooting"></a>Zu beachtende Aspekte und Problembehandlung
* Wenn der Bericht, der zum Erstellen der Visualisierung verwendet wurde, nicht gespeichert wurde, löst das Auswählen der Kachel keine Aktion aus.
* Wenn die Kachel anhand einer Arbeitsmappe in Excel Online erstellt wurde und Sie nicht mindestens Leseberechtigungen für diese Arbeitsmappe haben, wird durch Auswählen der Kachel die Arbeitsmappe nicht in Excel Online geöffnet.
* Wenn für Kacheln, die mit **Kacheln hinzufügen** direkt auf dem Dashboard erstellt wurden, ein benutzerdefinierter Link festgelegt wurde, wird die betreffende URL durch Auswählen des Titels, des Untertitels oder der Kachel geöffnet.  Standardmäßig erfolgt bei Auswahl einer dieser Kacheln direkt auf dem Dashboard für ein Bild, einen Webcode oder ein Textfeld keine Aktion.
* Wenn Sie über keine Berechtigungen zum Bericht in SSRS verfügen, führt die Auswahl einer über SSRS erstellten Kachel zur Anzeige einer Fehlerseite. Auf dieser werden Sie darauf hingewiesen, dass Sie keinen Zugriff haben (rsAccessDenied).
* Wenn Sie keinen Zugriff auf das Netzwerk mit SSRS haben, führt die Auswahl einer über SSRS erstellten Kachel zur Anzeige einer Fehlerseite. Auf dieser werden Sie darauf hingewiesen, dass der Server nicht gefunden wurde (HTTP 404). Ihr Gerät muss Netzwerkzugriff auf den Berichtsserver besitzen, um den Bericht anzeigen zu können.
* Wenn sich die ursprüngliche Visualisierung ändert, die zum Erstellen der Kachel verwendet wurde, ändert sich die Kachel nicht.  Wenn Sie beispielsweise ein Liniendiagramm aus einem Bericht angeheftet haben und dann das Liniendiagramm in ein Balkendiagramm ändern, wird auf der Dashboardkachel weiterhin ein Liniendiagramm angezeigt. Die Daten werden aktualisiert, der Visualisierungstyp hingegen nicht.

## <a name="next-steps"></a>Nächste Schritte
[Erstellen einer Karte (Kachel für große Zahlen) für das Dashboard](../visuals/power-bi-visualization-card.md)

[Dashboards in Power BI](end-user-dashboards.md)  

[Datenaktualisierung](../refresh-data.md)

[Power BI – Grundkonzepte](end-user-basic-concepts.md)

[Exportieren einer Kachel nach PowerPoint](http://blogs.msdn.com/b/powerbidev/archive/2015/09/28/integrating-power-bi-tiles-into-office-documents.aspx)

[Anheften von Reporting Services-Elementen an Power BI-Dashboards](https://msdn.microsoft.com/library/mt604784.aspx)

Weitere Fragen? [Wenden Sie sich an die Power BI-Community](http://community.powerbi.com/)

