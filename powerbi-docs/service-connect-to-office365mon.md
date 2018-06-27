---
title: Herstellen einer Verbindung mit Office365Mon mithilfe von Power BI
description: Office365Mon für Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 18093772232d119a24e76437d3f62a145a0a7153
ms.sourcegitcommit: 2a7bbb1fa24a49d2278a90cb0c4be543d7267bda
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2018
ms.locfileid: "34247686"
---
# <a name="connect-to-office365mon-with-power-bi"></a>Herstellen einer Verbindung mit Office365Mon mithilfe von Power BI
Die Analyse von Ausfällen und Integritätsdaten von Office 365 ist mit Power BI und dem Office365Mon-Inhaltspaket ein Kinderspiel. Power BI ruft Ihre Daten ab – Stichprobendaten zu Ausfällen und Integrität eingeschlossen –, und erstellt basierend auf diesen Daten ein Dashboard und Berichte.

Stellen Sie eine Verbindung mit dem [Office365Mon-Inhaltspaket](https://app.powerbi.com/groups/me/getdata/services/office365mon) für Power BI her.

>[!NOTE]
>Zum Herstellen der Verbindung und Laden des Power BI-Inhaltspakets ist ein Office365Mon-Administratorkonto erforderlich.

## <a name="how-to-connect"></a>Herstellen der Verbindung
1. Wählen Sie unten im linken Navigationsbereich **Daten abrufen** aus.
   
   ![](media/service-connect-to-office365mon/pbi_getdata.png)
2. Wählen Sie im Feld **Dienste** die Option **Abrufen**aus.
   
   ![](media/service-connect-to-office365mon/pbi_getservices.png) 
3. Wählen Sie **Office365Mon** \> **Abrufen** aus.
   
   ![](media/service-connect-to-office365mon/o365mon.png)
4. Wählen Sie als Authentifizierungsmethode die Option **oAuth2** \> **Anmelden** aus.
   
   Wenn Sie dazu aufgefordert werden, geben Sie Ihre Office365Mon-Administratoranmeldeinformationen ein, und führen Sie den Authentifizierungsvorgang aus.
   
   ![](media/service-connect-to-office365mon/creds.png)
   
   ![](media/service-connect-to-office365mon/creds2.png)
5. Nachdem die Daten von Power BI importiert wurden, werden im linken Navigationsbereich ein neues Dashboard, ein Bericht und ein Dataset angezeigt. Neue Elemente sind mit einem gelben Sternchen (\*) markiert. Wählen Sie den Eintrag „Office365Mon“ aus.
   
   ![](media/service-connect-to-office365mon/dashboard4.png)

**Was nun?**

* Versuchen Sie, am oberen Rand des Dashboards [im Q&A-Feld eine Frage zu stellen](power-bi-q-and-a.md).
* [Ändern Sie die Kacheln](service-dashboard-edit-tile.md) im Dashboard.
* [Wählen Sie eine Kachel aus](service-dashboard-tiles.md), um den zugrunde liegenden Bericht zu öffnen.
* Ihr Dataset ist auf eine tägliche Aktualisierung festgelegt. Sie können jedoch das Aktualisierungsintervall ändern oder es über **Jetzt aktualisieren** nach Bedarf aktualisieren.

## <a name="troubleshooting"></a>Problembehandlung
Wenn nach dem Eingeben Ihrer Office365Mon-Abonnementsanmeldeinformationen zur Anmeldung der **Anmeldefehler** gemeldet wird, verfügt das verwendete Konto nicht über die erforderlichen Berechtigungen, um die Office365Mon-Daten aus Ihrem Konto abzurufen. Überprüfen Sie, ob es sich um ein Administratorkonto handelt, und versuchen Sie es erneut.

## <a name="next-steps"></a>Nächste Schritte
[Erste Schritte mit Power BI](service-get-started.md)

[Abrufen von Daten in Power BI](service-get-data.md)

