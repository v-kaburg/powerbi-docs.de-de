---
title: Einbetten von Berichten oder Dashboards aus Apps
description: Erfahren Sie, wie Sie einen Bericht oder ein Dashboard aus einer Power BI-App anstatt aus einem App-Arbeitsbereich integrieren bzw. einbetten.
author: markingmyname
ms.author: maghan
ms.date: 07/13/2018
ms.topic: how-to
ms.service: powerbi
ms.component: powerbi-developer
ms.custom: mvc
manager: kfile
ms.openlocfilehash: 2817ccb25fc9aa6d3e8150c776558366dcf0ccb6
ms.sourcegitcommit: 0c870a006e525447497e678484874a2f137b9abd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/17/2018
ms.locfileid: "39088837"
---
# <a name="embed-reports-or-dashboards-from-apps"></a>Einbetten von Berichten oder Dashboards aus Apps

In **Power BI** können Sie Apps erstellen, um zusammengehörige **Dashboards** und **Berichte** an einer Stelle zusammenzuführen und anschließend für große Personengruppen in Ihrer Organisation zu veröffentlichen. Die Verwendung dieser Apps ist ausschlaggebend, wenn alle Ihrer Benutzer Power BI verwenden, damit Sie Inhalte mithilfe von Power BI-Apps für sie freigeben können. In diesem Artikel lernen Sie einige schnelle Schritte zum Einbetten von Inhalten aus einer freigegebenen Power BI-App in eine Drittanbieteranwendung kennen.

## <a name="how-to-grab-report-embed-url-for-embedding"></a>Abrufen einer URL zum Einbetten eines Berichts

1. Instanziieren Sie die Anwendung im Arbeitsbereich eines Benutzers („Mein Arbeitsbereich“), indem Sie sie entweder für sich selbst freigeben oder einen Benutzer durch diesen Arbeitsablauf führen.

2. Öffnen Sie den gewünschten Bericht im Power BI-Dienst.

3. Klicken Sie auf Datei > In SharePoint Online einbetten, und kopieren Sie die Berichteinbettungs-URL (wie im unten gezeigten Screenshot), oder rufen Sie die GetReports/GetReport-REST-API auf, und extrahieren Sie das entsprechende Feld für die Berichteinbettungs-URL aus der Antwort (beachten Sie, dass der REST-Aufruf keinen Bezeichner für den Arbeitsbereich als Teil der URL enthalten sollte, da die App im Arbeitsbereich des Benutzers instanziiert wurde).

4. Verwenden Sie die in Schritt 3 abgerufene Einbettungs-URL mit dem JS SDK.

    ![Einbetten aus Apps](media/embed-from-apps/embed-from-app.png)

## <a name="how-to-grab-dashboard-embed-url-for-embedding"></a>Abrufen einer URL zum Einbetten eines Dashboards

1. Instanziieren Sie die Anwendung im Arbeitsbereich eines Benutzers („Mein Arbeitsbereich“), indem Sie sie entweder für sich selbst freigeben oder einen Benutzer durch diesen Arbeitsablauf führen.

2. Rufen Sie die GetDashboards-REST-API auf, und extrahieren Sie das entsprechende Feld für die URL zum Einbetten des Dashboards aus der Antwort (beachten Sie, dass der REST-Aufruf keinen Bezeichner für den Arbeitsbereich als Teil der URL enthalten sollte, da die App im Arbeitsbereich des Benutzers instanziiert wurde).

3. Verwenden Sie die in Schritt 4 abgerufene Einbettungs-URL mit dem JS SDK.

## <a name="next-steps"></a>Nächste Schritte

Erfahren Sie auch, wie Sie für Drittanbieterkunden und Ihre Organisation aus App-Arbeitsbereiche heraus einbetten.

> [!div class="nextstepaction"]
>[Einbetten für Drittanbieterkunden](embed-sample-for-customers.md)

> [!div class="nextstepaction"]
>[Embed for your organization (Einbetten für Ihre Organisation)](embed-sample-for-your-organization.md)