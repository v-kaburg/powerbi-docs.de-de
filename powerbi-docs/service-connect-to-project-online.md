---
title: Herstellen einer Verbindung mit Project Online mithilfe von Power BI
description: Project Online für Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 52bd4b5dc27ff127eadea49cb3e761d6cda4788d
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2018
ms.locfileid: "34249158"
---
# <a name="connect-to-project-online-with-power-bi"></a>Herstellen einer Verbindung mit Project Online mithilfe von Power BI
Microsoft Project Online ist eine flexible Onlinelösung für das Projektportfoliomanagement (PPM) und die tägliche Arbeit. Project Online versetzt Organisationen dazu in die Lage, die ersten Schritte zu unternehmen, Investitionen in Projektportfolios zu priorisieren und den beabsichtigten Geschäftserfolg zu realisieren. Das Projekt Online-Inhaltspaket für Power BI ermöglicht Ihnen, Ihre Projektdaten mit vordefinierten Metriken wie Portfoliostatus und Projektkonformität zu erkunden.

Stellen Sie eine Verbindung zum [Project Online-Inhaltspaket](https://app.powerbi.com/getdata/services/project-online) für Power BI her.

## <a name="how-to-connect"></a>Herstellen der Verbindung
1. Wählen Sie unten im linken Navigationsbereich **Daten abrufen** aus.
   
    ![](media/service-connect-to-project-online/getdata.png)
2. Wählen Sie im Feld **Dienste** die Option **Abrufen**aus.
   
   ![](media/service-connect-to-project-online/services.png)
3. Wählen Sie **Microsoft Project Online** \> **Abrufen** aus.
   
   ![](media/service-connect-to-project-online/mproject.png)
4. Geben Sie im Textfeld **Project Web App-URL** die URL für die Project Web App (PWA) ein, mit der Sie eine Verbindung herstellen möchten, und klicken Sie dann auf **Weiter**. Beachten Sie, dass dies bei Verwendung einer benutzerdefinierten Domäne vom Beispiel abweichen kann.
   
    ![](media/service-connect-to-project-online/params.png)
5. Wählen Sie als Authentifizierungsmethode die Option **oAuth2** \> **Anmelden** aus. Wenn Sie dazu aufgefordert werden, geben Sie Ihre Project Online-Anmeldeinformationen ein, und führen Sie den Authentifizierungsvorgang aus.
   
    ![](media/service-connect-to-project-online/creds.png)
    
Beachten Sie, dass Sie über Portfolio Viewer-, Portfolio Manager- oder Administratorberechtigungen für die Projekt-Web-App verfügen müssen, mit der Sie sich verbinden.

6. Eine Benachrichtigung wird angezeigt, dass Ihre Daten geladen werden. Je nach Größe Ihres Kontos kann dies einige Zeit dauern. Nachdem die Daten von Power BI importiert wurden, werden im linken Navigationsbereich ein neues Dashboard, ein Bericht und ein Dataset angezeigt. Dies ist der Standarddashboard, das Power BI zum Anzeigen Ihrer Daten erstellt hat. Sie können dieses Dashboard anpassen, damit Ihre Daten auf die gewünschte Weise angezeigt werden.
   
   ![](media/service-connect-to-project-online/dashboard2.png)

**Was nun?**

* Versuchen Sie, am oberen Rand des Dashboards [im Q&A-Feld eine Frage zu stellen](power-bi-q-and-a.md).
* [Ändern Sie die Kacheln](service-dashboard-edit-tile.md) im Dashboard.
* [Wählen Sie eine Kachel aus](service-dashboard-tiles.md), um den zugrunde liegenden Bericht zu öffnen.
* Ihr Dataset ist auf eine tägliche Aktualisierung festgelegt. Sie können jedoch das Aktualisierungsintervall ändern oder es über **Jetzt aktualisieren** nach Bedarf aktualisieren.

## <a name="next-steps"></a>Nächste Schritte
[Erste Schritte mit Power BI](service-get-started.md)

[Abrufen von Daten in Power BI](service-get-data.md)

