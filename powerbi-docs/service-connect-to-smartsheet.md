---
title: Herstellen einer Verbindung mit Smartsheet mithilfe von Power BI
description: Smartsheet für Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 55d61e89b1fb01de472d967a312b25340d482951
ms.sourcegitcommit: 750f0bfab02af24c8c72e6e9bbdd876e4a7399de
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/04/2019
ms.locfileid: "54008463"
---
# <a name="connect-to-smartsheet-with-power-bi"></a>Herstellen einer Verbindung mit Smartsheet mithilfe von Power BI
Smartsheet bietet eine einfache Plattform für Zusammenarbeit und Dateifreigabe. Das Smartsheet-Inhaltspaket für Power BI bietet ein Dashboard, Berichte und ein Dataset mit einer Übersicht über Ihr Smartsheet-Konto. Sie können sich auch über [Power BI Desktop](desktop-connect-to-data.md) direkt mit einzelnen Blättern in Ihrem Konto verbinden. 

Stellen Sie eine Verbindung mit dem [Smartsheet-Inhaltspaket](https://app.powerbi.com/groups/me/getdata/services/smartsheet) für Power BI her.

>[!NOTE]
>Zum Herstellen der Verbindung und Laden des Power BI-Inhaltspakets sollte nach Möglichkeit ein Smartsheet-Administratorkonto verwendet werden, da es über zusätzlichen Zugriff verfügt.

## <a name="how-to-connect"></a>Herstellen der Verbindung
1. Wählen Sie unten im linken Navigationsbereich **Daten abrufen** aus.
   
   ![](media/service-connect-to-smartsheet/pbi_getdata.png)
2. Wählen Sie im Feld **Dienste** die Option **Abrufen**aus.
   
   ![](media/service-connect-to-smartsheet/pbi_getservices.png) 
3. Wählen Sie **Smartsheet \> Abrufen** aus.
   
   ![](media/service-connect-to-smartsheet/smartsheet.png)
4. Wählen Sie für die Authentifizierungsmethode **oAuth2 \> Anmelden** aus.
   
   Geben Sie bei der entsprechenden Aufforderung Ihre Smartsheet-Anmeldeinformationen ein, und führen Sie den Authentifizierungsvorgang aus.
   
   ![](media/service-connect-to-smartsheet/creds.png)
   
   ![](media/service-connect-to-smartsheet/creds2.png)
5. Nachdem die Daten von Power BI importiert wurden, werden im linken Navigationsbereich ein neues Dashboard, ein Bericht und ein Dataset angezeigt. Neue Elemente sind mit einem gelben Sternchen (\*) markiert. Wählen Sie den Eintrag „Smartsheet“ aus.
   
   ![](media/service-connect-to-smartsheet/dashboard.png)

**Was nun?**

* Versuchen Sie, am oberen Rand des Dashboards [im Q&A-Feld eine Frage zu stellen](consumer/end-user-q-and-a.md).
* [Ändern Sie die Kacheln](service-dashboard-edit-tile.md) im Dashboard.
* [Wählen Sie eine Kachel aus](consumer/end-user-tiles.md), um den zugrunde liegenden Bericht zu öffnen.
* Zwar ist Ihr Dataset auf tägliche Aktualisierung festgelegt, jedoch können Sie das Aktualisierungsintervall ändern oder über **Jetzt aktualisieren** nach Bedarf aktualisieren.

## <a name="whats-included"></a>Inhalt
Das Smartsheet-Inhaltspaket für Power BI enthält einen Überblick über Ihr Smartsheet-Konto, z.B. die Anzahl von Arbeitsbereichen, Berichten und Blättern, über die Sie verfügen, wenn sie geändert werden usw. Benutzer mit Administratorrechten sehen auch einige Informationen über die Benutzer in Ihrem System wie diejenigen, die die meisten Blätter erstellt haben.  

Sie können sich über den Smartsheet-Connector in [Power BI Desktop](desktop-connect-to-data.md) direkt mit einzelnen Blättern in Ihrem Konto verbinden.  

## <a name="next-steps"></a>Nächste Schritte:

[Was ist Power BI?](power-bi-overview.md)

[Abrufen von Daten in Power BI](service-get-data.md)