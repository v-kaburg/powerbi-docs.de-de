---
title: Herstellen einer Verbindung mit Azure Mobile Engagement mithilfe von Power BI
description: "Azure Mobile Engagement für Power BI"
services: powerbi
documentationcenter: 
author: joeshoukry
manager: kfile
backup: maggiesMSFT
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/16/2017
ms.author: yshoukry
ms.openlocfilehash: 85b43579785983da2ddc3ac2e302396d1a282792
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2017
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

 **Was nun?**

* Versuchen Sie, am oberen Rand des Dashboards [im Q&A-Feld eine Frage zu stellen](service-q-and-a.md).
* [Ändern Sie die Kacheln](service-dashboard-edit-tile.md) im Dashboard.
* [Wählen Sie eine Kachel aus](service-dashboard-tiles.md), um den zugrunde liegenden Bericht zu öffnen.
* Ihr Dataset ist auf eine tägliche Aktualisierung festgelegt. Sie können jedoch das Aktualisierungsintervall ändern oder es über **Jetzt aktualisieren** nach Bedarf aktualisieren.

## <a name="next-steps"></a>Nächste Schritte
[Erste Schritte mit Power BI](service-get-started.md)

[Abrufen von Daten in Power BI](service-get-data.md)

