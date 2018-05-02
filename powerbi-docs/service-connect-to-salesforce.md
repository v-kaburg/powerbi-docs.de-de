---
title: Herstellen einer Verbindung mit Salesforce mithilfe von Power BI
description: Salesforce für Power BI
services: powerbi
documentationcenter: ''
author: SarinaJoan
manager: kfile
backup: maggiesMSFT
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 04/13/2018
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 62624d35f1fb477c4daf2ffcef92bb18fb8a6a8e
ms.sourcegitcommit: df94efc51f261113fa90ebdf3fe68dd149cc4936
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2018
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

Sie können dieses Dashboard anpassen, damit Ihre Daten auf die gewünschte Weise angezeigt werden. Sie können im Q&A-Bereich eine Frage stellen, oder Sie klicken auf eine Kachel, um [den zugrunde liegenden Bericht zu öffnen](service-dashboard-tiles.md) und [die Kacheln zu ändern](service-dashboard-edit-tile.md), die sich im Dashboard befinden.

**Was nun?**

* Versuchen Sie, am oberen Rand des Dashboards [im Q&A-Feld eine Frage zu stellen](power-bi-q-and-a.md).
* [Ändern Sie die Kacheln](service-dashboard-edit-tile.md) im Dashboard.
* [Wählen Sie eine Kachel aus](service-dashboard-tiles.md), um den zugrunde liegenden Bericht zu öffnen.
* Ihr Dataset ist auf eine tägliche Aktualisierung festgelegt. Sie können jedoch das Aktualisierungsintervall ändern oder es über **Jetzt aktualisieren** nach Bedarf aktualisieren.

## <a name="system-requirements-and-considerations"></a>Systemanforderungen und Hinweise
- Verbindung mit einem Salesforce-Produktionskonto, für das der API-Zugriff aktiviert ist.
- Berechtigung wurde der Power BI-App während der Anmeldung erteilt.
- Das Konto verfügt über ausreichend API-Aufrufe zum Abrufen und Aktualisieren der Daten.
- Für die Aktualisierung ist ein gültiges Authentifizierungstoken erforderlich. Stellen Sie sicher, dass Sie maximal fünf Salesforce-Datasets importiert haben, da für Salesforce ein Limit von fünf Authentifizierungstoken pro Anwendung besteht.
- Die API für Salesforce-Berichte weist eine Einschränkung auf, die bis zu 2.000 Datenzeilen unterstützt.


## <a name="troubleshooting"></a>Problembehandlung
Wenn Fehler auftreten, überprüfen Sie die oben genannten Anforderungen. Beachten Sie auch, dass es derzeit nicht möglich ist, sich bei einer benutzerdefinierten oder Sandkastendomäne anzumelden.

## <a name="next-steps"></a>Nächste Schritte
[Erste Schritte mit Power BI](service-get-started.md)

[Abrufen von Daten](service-get-data.md)

