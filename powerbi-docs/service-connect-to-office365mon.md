---
title: Herstellen einer Verbindung mit Office365Mon mithilfe von Power BI
description: Office365Mon für Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: cce886edbed00075efaa43bae9c8a712929e8b9a
ms.sourcegitcommit: 750f0bfab02af24c8c72e6e9bbdd876e4a7399de
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/04/2019
ms.locfileid: "54007980"
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

* Versuchen Sie, am oberen Rand des Dashboards [im Q&A-Feld eine Frage zu stellen](consumer/end-user-q-and-a.md).
* [Ändern Sie die Kacheln](service-dashboard-edit-tile.md) im Dashboard.
* [Wählen Sie eine Kachel aus](consumer/end-user-tiles.md), um den zugrunde liegenden Bericht zu öffnen.
* Zwar ist Ihr Dataset auf tägliche Aktualisierung festgelegt, jedoch können Sie das Aktualisierungsintervall ändern oder über **Jetzt aktualisieren** nach Bedarf aktualisieren.

## <a name="troubleshooting"></a>Problembehandlung
Wenn nach dem Eingeben Ihrer Office365Mon-Abonnementsanmeldeinformationen zur Anmeldung der **Anmeldefehler** gemeldet wird, verfügt das verwendete Konto nicht über die erforderlichen Berechtigungen, um die Office365Mon-Daten aus Ihrem Konto abzurufen. Überprüfen Sie, ob es sich um ein Administratorkonto handelt, und versuchen Sie es erneut.

## <a name="next-steps"></a>Nächste Schritte
[Was ist Power BI?](power-bi-overview.md)

[Abrufen von Daten in Power BI](service-get-data.md)

