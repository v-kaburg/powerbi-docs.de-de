---
title: Remotekonfiguration des Zugriffs der mobilen Power BI-App für iOS auf Berichtsserver
description: Erfahren Sie, wie Sie Ihre mobilen iOS-Apps remote für Ihren Berichtsserver konfigurieren.
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-report-server
ms.topic: conceptual
ms.date: 05/22/2018
ms.author: maggies
ms.openlocfilehash: bbade67c9510b8d316364d991c09444712309514
ms.sourcegitcommit: 2a7bbb1fa24a49d2278a90cb0c4be543d7267bda
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2018
ms.locfileid: "34722176"
---
# <a name="configure-power-bi-ios-mobile-app-access-to-a-report-server-remotely"></a>Remotekonfiguration des Zugriffs der mobilen Power BI-App für iOS auf Berichtsserver

In diesem Artikel erfahren Sie, wie Sie das MDM-Tool Ihrer Organisation verwenden, um den Zugriff für mobile Power BI-App für iOS auf Berichtsserver zu konfigurieren. Für die Einrichtung erstellen IT-Administratoren eine Richtlinie für die App-Konfiguration mit den erforderlichen Informationen, die per Push an die App weitergeleitet werden sollen. 

 Anschließend können Benutzer der mobilen iOS-App für Power BI einfacher eine Verbindung mit dem Berichtsserver ihrer Organisation herstellen, da die Berichtsserververbindung bereits konfiguriert ist. 


## <a name="create-the-app-configuration-policy-in-mdm-tool"></a>Erstellen der Richtlinie für die App-Konfiguration im MDM-Tool 

Dies sind die Schritte, die Sie als Administrator in Microsoft Intune befolgen, um die Richtlinie für die App-Konfiguration zu erstellen. Die Schritte und Erfahrungen beim Erstellen der Richtlinie für die App-Konfiguration unterscheiden sich womöglich in anderen MDM-Tools. 

1. Verbinden Sie Ihr MDM-Tool. 
2. Erstellen Sie einen Namen und eine neue Richtlinie für die App-Konfiguration. 
3. Wählen Sie aus, an welchen Benutzer diese Richtlinie für die App-Konfiguration verteilt wird. 
4. Erstellen Sie Schlüssel-Wert-Paare. 

In der folgenden Tabelle sind die Paare aufgeführt.

|Schlüssel  |Typ  |Description  |
|---------|---------|---------|
| com.microsoft.powerbi.mobile.ServerURL | Zeichenfolge | Berichtsserver-URL </br> Muss mit http/https beginnen |
| com.microsoft.powerbi.mobile.ServerUsername | Zeichenfolge | [Optional] </br> Der Benutzername, der zum Verbinden des Servers verwendet wird. </br> Wenn keiner vorhanden ist, fordert die App den Benutzer auf, den Benutzernamen für die Verbindung einzugeben.| 
| com.microsoft.powerbi.mobile.ServerDisplayName | Zeichenfolge | [Optional] </br> Der Standardwert ist „Berichtsserver“. </br> Ein Anzeigename, der in der App zur Darstellung des Servers verwendet wird | 
| com.microsoft.powerbi.mobile.OverrideServerDetails | Boolesch | Der Standardwert ist TRUE </br> Wenn der Standardwert auf TRUE festgelegt ist, wird jede Berichtsserverdefinition, die sich bereits auf dem mobilen Gerät befindet, außer Kraft gesetzt (vorhandene Server, die bereits konfiguriert sind, werden gelöscht). </br> Wenn die Außerkraftsetzung auf TRUE festgelegt ist, wird dadurch auch verhindert, dass der Benutzer diese Konfiguration entfernt. </br> Bei FALSE werden die mithilfe von Push übertragenen Werte hinzugefügt, und vorhandene Einstellungen werden beibehalten. </br> Wenn die gleiche Server-URL bereits in der mobilen App konfiguriert ist, behält die App diese Konfiguration bei und fordert den Benutzer nicht auf, sich neu für denselben Server zu authentifizieren. |

Unten sehen Sie ein Beispiel der Festlegung der Konfigurationsrichtlinie über Intune.

![Konfigurationseinstellungen in Intune](media/configure-powerbi-mobile-apps-remote/power-bi-ios-remote-configuration-settings.png)

## <a name="end-users-connecting-to-a-report-server"></a>Endbenutzer, die eine Verbindung mit einem Berichtsserver herstellen

Nachdem Sie die Richtlinie für die App-Konfiguration veröffentlicht haben, verfügen Benutzer und Geräte, die der Verteilungsliste angehören, die für diese Richtline definiert wurde, über die folgende Benutzeroberfläche, wenn die mobile Power BI-App für iOS gestartet wird. 

1. Den Benutzern wird eine Meldung angezeigt, die besagt, dass ihre mobile App mit einem Berichtsserver konfiguriert ist. Der Benutzer tippt dann auf **Anmelden**.

    ![Anmelden beim Berichtsserver](media/configure-powerbi-mobile-apps-remote/power-bi-config-server-sign-in.png)

2.  Auf der Seite **Mit Server verbinden** sind die Berichtsserverdetails bereits ausgefüllt. Die Benutzer müssen auf **Verbinden** tippen.

    ![Ausgefüllte Berichtsserverdetails](media/configure-powerbi-mobile-apps-remote/power-bi-ios-remote-configure-connect-server.png)

3. Zur Authentifizierung müssen Benutzer ein Kennwort eingeben und anschließend auf **Anmelden** tippen. 

    ![Ausgefüllte Berichtsserverdetails](media/configure-powerbi-mobile-apps-remote/power-bi-config-server-address.png)

Sie können nun KPIs und Power BI-Berichte, die auf dem Berichtsserver gespeichert sind, anzeigen und mit diesen interagieren.

## <a name="next-steps"></a>Nächste Schritte
[Administratorübersicht](admin-handbook-overview.md)  
[Installieren von Power BI-Berichtsserver](install-report-server.md)  

Weitere Fragen? [Stellen Sie Ihre Frage in der Power BI-Community.](https://community.powerbi.com/)

