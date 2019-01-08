---
title: Herstellen einer Verbindung mit MailChimp mithilfe von Power BI
description: MailChimp für Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: e4986227b408dfec7ac10a880ff6110aa2ad5b9a
ms.sourcegitcommit: 750f0bfab02af24c8c72e6e9bbdd876e4a7399de
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/04/2019
ms.locfileid: "54007670"
---
# <a name="connect-to-mailchimp-with-power-bi"></a>Herstellen einer Verbindung mit MailChimp mithilfe von Power BI
Das Power BI-Inhaltspaket ruft Daten aus Ihrem MailChimp-Konto ab und generiert ein Dashboard, eine Reihe von Berichten sowie ein Dataset, damit Sie Ihre Daten analysieren können. Beziehen Sie Analysen ein, um [MailChimp-Dashboards](https://powerbi.microsoft.com/integrations/mailchimp) zu erstellen und innerhalb Ihrer Kampagnen, Berichte und einzelnen Abonnenten schnell Trends zu erkennen. Die Daten werden täglich aktualisiert, um sicherzustellen, dass sie auf dem neuesten Stand sind.

Stellen Sie eine Verbindung mit dem [MailChimp-Inhaltspaket](https://app.powerbi.com/getdata/services/mailchimp) für Power BI her.

## <a name="how-to-connect"></a>Herstellen der Verbindung
1. Wählen Sie unten im linken Navigationsbereich **Daten abrufen** aus.
   
    ![](media/service-connect-to-mailchimp/pbi_getdata.png)
2. Wählen Sie im Feld **Dienste** die Option **Abrufen**aus.
   
   ![](media/service-connect-to-mailchimp/pbi_getservices.png)
3. Wählen Sie **MailChimp** \> **Abrufen** aus.
   
   ![](media/service-connect-to-mailchimp/mailchimp.png)
4. Wählen Sie als Authentifizierungsmethode die Option **oAuth2** \> **Anmelden** aus.
   
    Geben Sie bei der entsprechenden Aufforderung Ihre MailChimp-Anmeldeinformationen ein, und führen Sie den Authentifizierungsvorgang aus.
   
    Wenn Sie die Verbindung zum ersten Mal herstellen, werden Sie aufgefordert, Power BI den Lesezugriff für Ihr Konto zu gewähren. Wählen Sie **Zulassen** aus, um den Importvorgang zu starten, der je nach der Datenmenge in Ihrem Konto einige Minuten dauern kann.
   
    ![](media/service-connect-to-mailchimp/allow.png)
5. Nachdem die Daten von Power BI importiert wurden, werden im linken Navigationsbereich ein neues Dashboard, ein Bericht und ein Dataset angezeigt. Dies ist der Standarddashboard, das Power BI zum Anzeigen Ihrer Daten erstellt hat. Sie können dieses Dashboard anpassen, damit Ihre Daten auf die gewünschte Weise angezeigt werden.
   
   ![](media/service-connect-to-mailchimp/pbi_mailchimpnewdash.png)

**Was nun?**

* Versuchen Sie, am oberen Rand des Dashboards [im Q&A-Feld eine Frage zu stellen](consumer/end-user-q-and-a.md).
* [Ändern Sie die Kacheln](service-dashboard-edit-tile.md) im Dashboard.
* [Wählen Sie eine Kachel aus](consumer/end-user-tiles.md), um den zugrunde liegenden Bericht zu öffnen.
* Zwar ist Ihr Dataset auf tägliche Aktualisierung festgelegt, jedoch können Sie das Aktualisierungsintervall ändern oder über **Jetzt aktualisieren** nach Bedarf aktualisieren.

## <a name="next-steps"></a>Nächste Schritte
[Was ist Power BI?](power-bi-overview.md)

[Power BI – Grundkonzepte](consumer/end-user-basic-concepts.md)

