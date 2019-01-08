---
title: Herstellen einer Verbindung mit Azure Mobile Engagement mithilfe von Power BI
description: Azure Mobile Engagement für Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 8d95ab3675fdced31641a8abbffa31ed0a6643c1
ms.sourcegitcommit: 750f0bfab02af24c8c72e6e9bbdd876e4a7399de
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/04/2019
ms.locfileid: "54008302"
---
# <a name="connect-to-azure-mobile-engagement-with-power-bi"></a>Herstellen einer Verbindung mit Azure Mobile Engagement mithilfe von Power BI
Mit dem Power BI Azure Mobile Engagement-Inhaltspaket können Sie schnell Erkenntnisse aus Ihren App-Daten gewinnen.

Stellen Sie eine Verbindung mit dem [Azure Mobile Engagement-Inhaltspaket](https://app.powerbi.com/groups/me/getdata/services/azme) für Power BI her.

## <a name="how-to-connect"></a>Herstellen der Verbindung
1. Wählen Sie unten im linken Navigationsbereich **Daten abrufen** aus.
   
    ![](media/service-connect-to-azure-mobile/getdata.png)
2. Wählen Sie im Feld **Dienste** die Option **Abrufen**aus.
   
    ![](media/service-connect-to-azure-mobile/services.png)
3. Wählen Sie **Azure Mobile Engagement** \> **Abrufen** aus.
   
    ![](media/service-connect-to-azure-mobile/azme.png) 
4. Geben Sie Ihre App-Sammlung und den Namen der App an. Diese Informationen finden Sie in Ihrem Azure Mobile Engagement-Konto.
   
    ![](media/service-connect-to-azure-mobile/parameters.png) 
5. Geben Sie als Authentifizierungsmethode Ihren Schlüssel an, und klicken Sie dann auf „Anmelden“.
   
    ![](media/service-connect-to-azure-mobile/creds.png)
6. Nachdem die Daten von Power BI importiert wurden, werden im linken Navigationsbereich ein neues Dashboard, ein Bericht und ein Dataset angezeigt. Neue Elemente sind mit einem gelben Sternchen (\*) gekennzeichnet, das nach der Auswahl ausgeblendet wird:
   
    ![](media/service-connect-to-azure-mobile/dashboard.png)

## <a name="what-now"></a>Was nun?

* Versuchen Sie, am oberen Rand des Dashboards [im Q&A-Feld eine Frage zu stellen](consumer/end-user-q-and-a.md).
* [Ändern Sie die Kacheln](service-dashboard-edit-tile.md) im Dashboard.
* [Wählen Sie eine Kachel aus](consumer/end-user-tiles.md), um den zugrunde liegenden Bericht zu öffnen.
* Zwar ist Ihr Dataset auf tägliche Aktualisierung festgelegt, jedoch können Sie das Aktualisierungsintervall ändern oder über **Jetzt aktualisieren** nach Bedarf aktualisieren.

## <a name="next-steps"></a>Nächste Schritte
[Erste Schritte mit Power BI](service-get-started.md)

[Abrufen von Daten in Power BI](service-get-data.md)

