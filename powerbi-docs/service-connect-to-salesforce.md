---
title: Herstellen einer Verbindung mit Salesforce mithilfe von Power BI
description: Salesforce für Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 05/30/2018
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: ca035762f16d2e8e6c7ffb59220a2457daf10545
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2019
ms.locfileid: "61172022"
---
# <a name="connect-to-salesforce-with-power-bi"></a>Herstellen einer Verbindung mit Salesforce mithilfe von Power BI
Mit Power BI können Sie sich problemlos mit Ihrem Salesforce.com-Konto verbinden. Durch das Herstellen dieser Verbindung werden Ihre Daten abgerufen. Auf Basis dieser Daten werden dann automatisch ein Dashboard und zugehörige Berichte bereitgestellt.

Stellen Sie eine Verbindung mit dem [Salesforce-Inhaltspaket](https://app.powerbi.com/getdata/services/salesforce) für Power BI her, oder erfahren Sie mehr über die [Salesforce-Integration](https://powerbi.microsoft.com/integrations/salesforce) in Power BI.

## <a name="how-to-connect"></a>Herstellen der Verbindung
1. Wählen Sie unten im linken Navigationsbereich **Daten abrufen** aus.
   
   ![](media/service-connect-to-salesforce/pbi_getdata.png) 
2. Wählen Sie im Feld **Dienste** die Option **Abrufen**aus.
   
   ![](media/service-connect-to-salesforce/pbi_getservices.png) 
3. Klicken Sie auf **Salesforce**, und wählen Sie **Abrufen** aus.  
   
   ![](media/service-connect-to-salesforce/salesforce.png)
4. Wählen Sie **Anmelden** aus, um den Anmeldevorgang zu starten.
   
    ![](media/service-connect-to-salesforce/dialog.png)
5. Wenn Sie dazu aufgefordert werden, geben Sie Ihre Salesforce-Anmeldeinformationen ein. Klicken Sie auf **Zulassen** , damit Power BI auf Ihre grundlegenden Salesforce-Informationen und -Daten zugreifen kann.
   
   ![](media/service-connect-to-salesforce/sf_authorize.png)
6. Konfigurieren Sie mithilfe der Dropdownoption, welche Daten Sie in Power BI importieren möchten:
   
   * **Dashboard**
     
     Wählen Sie auf Grundlage einer Persona ein vordefiniertes Dashboard aus (z.B. **Sales Manager**). Diese Dashboards übernehmen einen bestimmten Satz von Standarddaten aus Salesforce und beziehen keine benutzerdefinierten Felder mit ein.
     
     ![](media/service-connect-to-salesforce/pbi_salesforcechooserole.png)
   * **Berichte**
     
     Wählen Sie mindestens einen benutzerdefinierten Bericht aus Ihrem Salesforce-Konto aus. Diese Berichte entsprechen den Ansichten in Salesforce und können Daten aus benutzerdefinierten Feldern oder Objekten enthalten.
     
     ![](media/service-connect-to-salesforce/pbi_salesforcereports.png)
     
     Wenn keine Berichte angezeigt werden, können Sie diese über Ihr Salesforce-Konto hinzufügen oder erstellen. Anschließend stellen Sie die Verbindung erneut her.
7. Klicken Sie auf **Verbinden** , um den Importvorgang zu starten. Während des Imports wird eine Benachrichtigung angezeigt, dass der Import ausgeführt wird. Wenn der Importvorgang abgeschlossen ist, werden Dashboard, Bericht und Dataset für Ihre Salesforce-Daten im linken Navigationsbereich aufgeführt.
   
   ![](media/service-connect-to-salesforce/pbi_getdatasalesforcedash.png)

Sie können dieses Dashboard anpassen, damit Ihre Daten auf die gewünschte Weise angezeigt werden. Sie können im Q&A-Bereich eine Frage stellen, oder Sie klicken auf eine Kachel, um [den zugrunde liegenden Bericht zu öffnen](consumer/end-user-tiles.md) und [die Kacheln zu ändern](service-dashboard-edit-tile.md), die sich im Dashboard befinden.

**Was nun?**

* Versuchen Sie, am oberen Rand des Dashboards [im Q&A-Feld eine Frage zu stellen](consumer/end-user-q-and-a.md).
* [Ändern Sie die Kacheln](service-dashboard-edit-tile.md) im Dashboard.
* [Wählen Sie eine Kachel aus](service-dashboard-tiles.md), um den zugrunde liegenden Bericht zu öffnen.
* Zwar ist Ihr Dataset auf tägliche Aktualisierung festgelegt, jedoch können Sie das Aktualisierungsintervall ändern oder über **Jetzt aktualisieren** nach Bedarf aktualisieren.

## <a name="system-requirements-and-considerations"></a>Systemanforderungen und Hinweise
- Verbindung mit einem Salesforce-Produktionskonto, für das der API-Zugriff aktiviert ist.
- Berechtigung wurde der Power BI-App während der Anmeldung erteilt.
- Das Konto verfügt über ausreichend API-Aufrufe zum Abrufen und Aktualisieren der Daten.
- Für die Aktualisierung ist ein gültiges Authentifizierungstoken erforderlich. Stellen Sie sicher, dass Sie maximal fünf Salesforce-Datasets importiert haben, da für Salesforce ein Limit von fünf Authentifizierungstoken pro Anwendung besteht.
- Die API für Salesforce-Berichte weist eine Einschränkung auf, die bis zu 2.000 Datenzeilen unterstützt.


## <a name="troubleshooting"></a>Problembehandlung
Wenn Fehler auftreten, überprüfen Sie die oben genannten Anforderungen. Beachten Sie auch, dass es derzeit nicht möglich ist, sich bei einer benutzerdefinierten oder Sandkastendomäne anzumelden.

### <a name="unable-to-connect-to-the-remote-server-message"></a>Meldung: „Es konnte keine Verbindung mit dem Remoteserver hergestellt werden.“

Wenn beim Versuch, eine Verbindung zu Ihrem Salesforce-Konto herzustellen, die Meldung „Die Verbindung mit dem Remoteserver kann nicht hergestellt werden.“ angezeigt wird, sehen Sie sich diese Lösung im Outsystems-Forum an: [Nachricht bzgl. eines Salesforce Connector-Anmeldefehlers: Die Verbindung mit dem Remoteserver kann nicht hergestellt werden](https://www.outsystems.com/forums/Forum_TopicView.aspx?TopicId=17674&TopicName=log-in-error-message-unable-to-connect-to-the-remote-server&)


## <a name="next-steps"></a>Nächste Schritte
[Was ist Power BI?](power-bi-overview.md)

[Abrufen von Daten](service-get-data.md)

