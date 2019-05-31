---
title: Herstellen einer Verbindung mit MailChimp mithilfe von Power BI
description: MailChimp für Power BI
author: maggiesMSFT
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 04/26/2019
ms.author: maggies
LocalizationGroup: Connect to services
ms.openlocfilehash: 8599c22246183d28d13eb80f05250baa8dc27f5d
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2019
ms.locfileid: "64579067"
---
# <a name="connect-to-mailchimp-with-power-bi"></a>Herstellen einer Verbindung mit MailChimp mithilfe von Power BI
Dieser Artikel führt Sie durch Abrufen von Daten aus Ihrem MailChimp-Konto mit einer Power BI-app-Vorlage. Der vorlagenanwendung generiert einen Arbeitsbereich mit einem Dashboard, eine Reihe von Berichten und ein Dataset, damit Sie Ihre MailChimp-Daten analysieren können. Beziehen Sie Analysen ein, um [MailChimp-Dashboards](https://powerbi.microsoft.com/integrations/mailchimp) zu erstellen und innerhalb Ihrer Kampagnen, Berichte und einzelnen Abonnenten schnell Trends zu erkennen. Die Daten aktualisiert täglich, um sicherzustellen, dass die Daten, die Sie überwachen, auf dem neuesten Stand ist.

Nachdem Sie die Vorlagen-app installiert haben, können Sie auf dem Dashboard und Bericht ändern. Anschließend können Sie sie als app an Kollegen in Ihrer Organisation verteilen.

Herstellen einer Verbindung mit der [MailChimp-vorlagenanwendung](https://app.powerbi.com/getdata/services/mailchimp) für Power BI her.

## <a name="how-to-connect"></a>Herstellen der Verbindung

[!INCLUDE [powerbi-service-apps-get-more-apps](./includes/powerbi-service-apps-get-more-apps.md)]

3. Wählen Sie **MailChimp** \> **jetzt**.
4. In **dieses Power BI-App installieren?** wählen **installieren**.
4. In der **Apps** wählen Sie im Bereich der **MailChimp** Kachel.

    ![Power BI-MailChimp-app-Kachel](media/service-connect-to-mailchimp/power-bi-connect-mailchimp.png)

6. In **beginnen Sie mit der neuen app**Option **Verbindungsdaten**.

    ![Erste Schritte mit Ihrer neuen App](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-connect-data.png)

1. Wählen Sie als Authentifizierungsmethode die Option **oAuth2** \> **Anmelden** aus.
   
    Geben Sie bei der entsprechenden Aufforderung Ihre MailChimp-Anmeldeinformationen ein, und führen Sie den Authentifizierungsvorgang aus.
   
    Wenn Sie die Verbindung zum ersten Mal herstellen, werden Sie von Power BI aufgefordert, den Lesezugriff auf Ihr Konto zu erteilen. Klicken Sie auf **Zulassen** , um den Importvorgang zu starten. Es dauert einige Minuten, je nach der Datenmenge in Ihrem Konto.
   
    ![Power BI-Connector für MailChimp](media/service-connect-to-mailchimp/allow.png)

5. Nachdem Power BI die Daten importiert wurden, wird das MailChimp-Dashboard geöffnet.
   
    ![Power BI-MailChimp-dashboard](media/service-connect-to-mailchimp/power-bi-mailchimp-dashboard.png)

## <a name="modify-and-distribute-your-app"></a>Ändern Sie und verteilen Sie Ihre app

Sie haben die MailChimp-app-Vorlage installiert. Das bedeutet, dass Sie auch die MailChimp-app-Arbeitsbereich erstellt haben. Im Arbeitsbereich können Sie den Bericht und das Dashboard zu ändern und verteilen Sie es als ein *app* an Kollegen in Ihrer Organisation. 

1. Wählen Sie zum Anzeigen der gesamte Inhalt des dem neuen MailChimp-Arbeitsbereich, in der linken Navigationsleiste **Arbeitsbereiche** > **MailChimp**. 

    ![MailChimp-Arbeitsbereichs im linken Navigationsbereich](media/service-connect-to-mailchimp/power-bi-mailchimp-left-nav.png)

    Diese Ansicht ist die Liste mit den Inhalten für den Arbeitsbereich. In der oberen rechten Ecke finden Sie **app aktualisieren**. Wenn Sie Ihre app an Ihre Kollegen verteilen möchten, ist, in dem Sie beginnen.

    ![MailChimp-Liste Inhalt](media/service-connect-to-mailchimp/power-bi-mailchimp-content-list.png)

2. Wählen Sie **Berichte** und **Datasets** die anderen Elementen im Arbeitsbereich angezeigt. 

    Erfahren Sie mehr über [Verteilen von apps](service-create-distribute-apps.md) an Ihre Kollegen.

## <a name="next-steps"></a>Nächste Schritte

* [Erstellen Sie die neue Arbeitsbereiche in Power BI](service-create-the-new-workspaces.md)
* [Installieren und Verwenden von Apps in Power BI](consumer/end-user-apps.md)
* [Power BI-Apps für externe Dienste](service-connect-to-services.md)
* Haben Sie Fragen? [Stellen Sie Ihre Frage in der Power BI-Community.](http://community.powerbi.com/)

