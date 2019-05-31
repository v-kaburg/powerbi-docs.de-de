---
title: Herstellen einer Verbindung mit Smartsheet mithilfe von Power BI
description: Smartsheet für Power BI
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 04/26/2019
ms.author: maggies
LocalizationGroup: Connect to services
ms.openlocfilehash: 841201aa87139b9630d6fc076d57109fb2b09804
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2019
ms.locfileid: "64578908"
---
# <a name="connect-to-smartsheet-with-power-bi"></a>Herstellen einer Verbindung mit Smartsheet mithilfe von Power BI
Dieser Artikel führt Sie durch Abrufen von Daten aus Ihrer Smartsheet-Konto mit einer Power BI-app-Vorlage. Smartsheet bietet eine einfache Plattform für Zusammenarbeit und Dateifreigabe. Die Smartsheet-Vorlagen-app für Power BI bietet ein Dashboard, Berichte und Datasets, die einen Überblick über Ihr Smartsheet-Konto anzeigen. Sie können auch [Power BI Desktop](desktop-connect-to-data.md) für die Verbindung direkt mit einzelnen Blättern in Ihrem Konto. 

Nachdem Sie die Vorlagen-app installiert haben, können Sie auf dem Dashboard und Bericht ändern. Anschließend können Sie sie als app an Kollegen in Ihrer Organisation verteilen.

Herstellen einer Verbindung mit der [Smartsheet vorlagenanwendung](https://app.powerbi.com/groups/me/getdata/services/smartsheet) für Power BI her.

>[!NOTE]
>Ein Smartsheet-Administratorkonto wird bevorzugt, für die Verbindung und Laden Power BI-app-Vorlage aus, da es über zusätzlichen Zugriff verfügt.

## <a name="how-to-connect"></a>Herstellen der Verbindung

[!INCLUDE [powerbi-service-apps-get-more-apps](./includes/powerbi-service-apps-get-more-apps.md)]

3. Wählen Sie **Smartsheet** \> **jetzt**.
4. In **dieses Power BI-App installieren?** wählen **installieren**.
4. In der **Apps** wählen Sie im Bereich der **Smartsheet** Kachel.

    ![Power BI-Smartsheet-app-Kachel](media/service-connect-to-smartsheet/power-bi-smartsheet-tile.png)

6. In **beginnen Sie mit der neuen app**Option **Verbindungsdaten**.

    ![Erste Schritte mit Ihrer neuen App](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-connect-data.png)

4. Wählen Sie für die Authentifizierungsmethode **oAuth2 \> Anmelden** aus.
   
   Geben Sie bei der entsprechenden Aufforderung Ihre Smartsheet-Anmeldeinformationen ein, und führen Sie den Authentifizierungsvorgang aus.
   
   ![Smartsheet-Anmeldeinformationen](media/service-connect-to-smartsheet/creds.png)
   
   ![Smartsheet-Anmeldung](media/service-connect-to-smartsheet/creds2.png)

5. Nachdem Power BI die Daten importiert wurden, wird der Smartsheet-Dashboard geöffnet.
   
   ![Smartsheet-dashboard](media/service-connect-to-smartsheet/power-bi-smartsheet-dashboard.png)

## <a name="modify-and-distribute-your-app"></a>Ändern Sie und verteilen Sie Ihre app

Sie haben die Smartsheet-app-Vorlage installiert. Das bedeutet, dass Sie auch den Smartsheet-app-Arbeitsbereich erstellt haben. Im Arbeitsbereich können Sie den Bericht und das Dashboard zu ändern und verteilen Sie es als ein *app* an Kollegen in Ihrer Organisation. 

1. Wählen Sie zum Anzeigen der gesamte Inhalt des dem neuen Smartsheet-Arbeitsbereich, in der linken Navigationsleiste **Arbeitsbereiche** > **Smartsheet**. 

    ![Smartsheet-Arbeitsbereichs im linken Navigationsbereich](media/service-connect-to-smartsheet/power-bi-smartsheet-workspace.png)

    Diese Ansicht ist die Liste mit den Inhalten für den Arbeitsbereich. In der oberen rechten Ecke finden Sie **app aktualisieren**. Wenn Sie Ihre app an Ihre Kollegen verteilen möchten, ist, in dem Sie beginnen. 

    ![Liste der Smartsheet-Inhalten](media/service-connect-to-smartsheet/power-bi-smartsheet-workspace-content.png)

2. Wählen Sie **Berichte** und **Datasets** die anderen Elementen im Arbeitsbereich angezeigt.

    Erfahren Sie mehr über [Verteilen von apps](service-create-distribute-apps.md) an Ihre Kollegen.

## <a name="whats-included"></a>Inhalt
Das Smartsheet-Vorlagen-app für Power BI einen Überblick über Ihr Smartsheet-Konto, z. B. die Anzahl von Arbeitsbereichen, enthält Berichte, blättern und Sie können geändert werden usw. Administratoren finden Sie unter auch einige Informationen über die Benutzer in ihrem System, z. B. die meisten Blätter Ersteller.  

Sie können sich über den Smartsheet-Connector in [Power BI Desktop](desktop-connect-to-data.md) direkt mit einzelnen Blättern in Ihrem Konto verbinden.  

## <a name="next-steps"></a>Nächste Schritte

* [Erstellen Sie die neue Arbeitsbereiche in Power BI](service-create-the-new-workspaces.md)
* [Installieren und Verwenden von Apps in Power BI](consumer/end-user-apps.md)
* [Verbinden Sie mit Power BI-apps für externe Dienste](service-connect-to-services.md)
* Haben Sie Fragen? [Stellen Sie Ihre Frage in der Power BI-Community.](http://community.powerbi.com/)