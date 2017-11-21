---
title: Herstellen einer Verbindung mit Visual Studio Team Services mithilfe von Power BI
description: "Visual Studio Team Services für Power BI"
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
ms.openlocfilehash: 20ea9117cf1eee3d7b05be21e5964226349a58c1
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2017
---
# <a name="connect-to-visual-studio-team-services-with-power-bi"></a>Herstellen einer Verbindung mit Visual Studio Team Services mithilfe von Power BI
Verwenden Sie das Visual Studio Team Services-Inhaltspaket für Power BI, um Erkenntnisse über Ihre Git- und TFVC-Teamprojekte zu erhalten. Nachdem Sie eine Verbindung hergestellt haben, werden Ihre Daten automatisch in einem Dashboard und in Berichten angezeigt. 

Stellen Sie eine Verbindung mit dem [Visual Studio Team Services-Inhaltspaket](https://app.powerbi.com/getdata/services/visual-studio-online) her, oder informieren Sie sich über die [Visual Studio Team Services-Integration](https://powerbi.microsoft.com/integrations/visual_studio_online) in Power BI.

>[!NOTE]
>Dieses Inhaltspaket erfordert Zugriff auf ein Konto, für das OAuth aktiviert ist. Es folgen weitere Informationen zu den Anforderungen.

## <a name="how-to-connect"></a>Herstellen der Verbindung
1. Wählen Sie unten im linken Navigationsbereich **Daten abrufen** aus.  
   ![](media/service-connect-to-visual-studio/pbi_getdata.png) 
2. Wählen Sie im Feld **Dienste** die Option **Abrufen**aus.  
   ![](media/service-connect-to-visual-studio/pbi_getservices.png) 
3. Wählen Sie das Inhaltspaket **Visual Studio Team Services**  aus, und klicken Sie dann auf **Abrufen**.     
   ![](media/service-connect-to-visual-studio/vsts.png)
4. Geben Sie Informationen zu Ihrem Visual Studio Team Services-Konto ein. Nachstehend finden Sie weitere Informationen zum [Suchen dieser Parameter](#FindingParams).
   
   ![](media/service-connect-to-visual-studio/pbi_vsosignin.png)
   
   Ihr Kontoname stellt den vorderen Teil der URL für visualstudio.com dar:    
   ![](media/service-connect-to-visual-studio/urlimage.png)
   
   Ihr Projektname ist der Name, der in Visual Studio Team Services am Anfang jeder Seite angezeigt wird:  
   ![](media/service-connect-to-visual-studio/projectimage.png)
5. Führen Sie die Authentifizierung mit Visual Studio Team Services mithilfe von „oAuth2“ durch. Möglicherweise wird daraufhin auch ein Visual Studio Team Services-Anmeldefenster angezeigt. 
   
   > [!IMPORTANT]
   > Einige Visual Studio Team Services-Bereitstellungen unterstützen „oAuth2“ nicht.  Befolgen Sie die Anleitungen im Abschnitt zur Problembehandlung, wenn bei der Anmeldung ein Fehler auftritt.
   > 
   > 
   
   ![](media/service-connect-to-visual-studio/pbi_vsosignin2.png)
6. Befolgen Sie die Anweisungen auf den Bildschirmen der Visual Studio Team Services-Authentifizierung, um dem Visual Studio-Inhaltspaket für Power BI die Berechtigung für den Zugriff auf Ihre Teamprojektdaten zu gewähren.   
   ![](media/service-connect-to-visual-studio/vsoauthorizeapp450.png)
7. Nach dem Herstellen einer Verbindung mit dem Visual Studio Team Services-Projekt werden im linken Navigationsbereich ein neues Dashboard, ein Bericht und ein Dataset angezeigt. Neue Elemente werden mit einem gelben Sternchen \* markiert.  
   ![](media/service-connect-to-visual-studio/visualstudioonline800px.png) 

**Was nun?**

* Versuchen Sie, am oberen Rand des Dashboards [im Q&A-Feld eine Frage zu stellen](service-q-and-a.md).
* [Ändern Sie die Kacheln](service-dashboard-edit-tile.md) im Dashboard.
* [Wählen Sie eine Kachel aus](service-dashboard-tiles.md), um den zugrunde liegenden Bericht zu öffnen.
* Ihr Dataset ist auf eine tägliche Aktualisierung festgelegt. Sie können jedoch das Aktualisierungsintervall ändern oder es über **Jetzt aktualisieren** nach Bedarf aktualisieren.

## <a name="whats-included"></a>Inhalt
Visual Studio Team Services in Power BI bietet eine Vielzahl von Tabellen und Feldern für Ihre Berichte. Die vollständige Liste des Funktionsumfangs im Inhaltspaket finden Sie hier: <https://www.visualstudio.com/get-started/report/vso-pbi-whats-available-vs>

## <a name="system-requirements"></a>Systemanforderungen
* Zugriff auf das Visual Studio Team Services-Konto mit der Berechtigung zum Erfassen der Daten mithilfe der REST-API.  
* Die Berechtigung für die Anwendung „Power BI“ wurde während der ersten Verbindung gewährt. Sie können den Zugriff auf Visual Studio Team Services widerrufen, um die Verbindung mit Power BI zu trennen und seine Autorisierung für den Zugriff auf Ihr Visual Studio Team Services-Konto aufzuheben. Weitere Informationen finden Sie unter <https://www.visualstudio.com/get-started/setup/change-application-access-policies-vs>.  

Weitere Informationen finden Sie unter <https://www.visualstudio.com/en-us/get-started/report/connect-vso-pbi-vs>.

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>Suchen von Parametern
Ihr Kontoname stellt den vorderen Teil der URL für visualstudio.com dar:    
    ![](media/service-connect-to-visual-studio/urlimage.png)

Ihr Projektname ist der Name, der in Visual Studio Team Services am Anfang jeder Seite angezeigt wird:  
    ![](media/service-connect-to-visual-studio/projectimage.png)

Sie können auch Platzhalter verwenden, um mehrere Projekte auszuwählen. Sie können z. B. alle Projekte auswählen, indem Sie einfach „\*“ eingeben. Sie können auch alle Projekte auswählen, die mit „Azure“ beginnen, indem Sie „Azure\*“ eingeben.

## <a name="troubleshooting"></a>Problembehandlung
Wenn Sie versuchen, sich bei Visual Studio Team Services anzumelden, erhalten Sie möglicherweise die Meldung, dass bei der Anmeldung ein Fehler aufgetreten ist.

Es gibt zwei häufige Gründe, warum die Authentifizierung möglicherweise nicht erfolgreich ausgeführt werden kann:

1) Sie sind mit Ihrem privaten Konto angemeldet und nicht mit Ihrem Geschäfts- oder Schulkonto.  

2) Ihre Visual Studio Team Services-Bereitstellung unterstützt oAuth nicht. 

**Anmelden mit Ihrem Geschäfts- oder Schulkonto**  
Wenn dieses Problem auftritt, kann dies darauf hinweisen, dass Sie bereits mit einem anderen Konto bei Visual Studio Team Services authentifiziert sind als dem Konto, über das Sie Daten laden möchten – wenn Sie sich z. B. mit einem privaten Microsoft-Konto bei Visual Studio Team Services und mit einem Geschäfts- oder Schulkonto bei Power BI angemeldet haben.

So beheben Sie dieses Problem:  

* Beenden Sie das Dialogfeld „Konfiguration“.  
* Melden Sie sich mit Ihrem privaten Konto bei Visual Studio Team Services ab.  
* Melden Sie sich mit Ihrem Geschäfts- oder Schulkonto bei Visual Studio Online an.  
* Starten Sie den oben aufgeführten Prozess „Daten abrufen“.  

Herstellen einer Verbindung mit Ihrem Geschäfts- oder Schulkonto (Azure Active Directory/AAD):  
    ![](media/service-connect-to-visual-studio/vsologinscreen.png)

Wenn dieses Dialogfeld angezeigt wird und Sie eine Verbindung mit Ihrem Geschäfts- oder Schulkonto (Azure Active Directory) herstellen möchten, stellen Sie sicher, dass Sie auf der linken Seite auf den Link klicken, um sich mit diesem Konto anzumelden. Geben Sie nicht Ihre AAD-Anmeldeinformationen auf der rechten Seite an, da hier ein Microsoft-Konto (Ihr privates Konto) erwartet wird.

**Visual Studio Team Services-Bereitstellungen, die „oAuth2“ nicht unterstützen**  
Ihr Visual Studio Team Services-Administrator hat „oAuth“ möglicherweise für Ihre Bereitstellung von Visual Studio Team Services deaktiviert.  In diesem Fall sind Sie nicht in der Lage, das Visual Studio-Inhaltspaket zu diesem Zeitpunkt zu verwenden. 

![](media/service-connect-to-visual-studio/oauth.png)

## <a name="next-steps"></a>Nächste Schritte
* [Erste Schritte mit Power BI](service-get-started.md)
* [Abrufen von Daten](service-get-data.md)

