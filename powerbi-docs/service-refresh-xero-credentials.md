---
title: Aktualisieren der Anmeldeinformationen für das Xero-Inhaltspaket
description: Wenn Sie das Xero-Inhaltspaket für Power BI verwenden, sind Sie möglicherweise auf ein Problem bei der täglichen Aktualisierung des Inhaltspakets festgestellt, das kürzlich durch eine Störung des Power BI-Diensts verursacht wurde.
author: SarinaJoan
manager: kfile
ms.reviewer: kayu
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 08/10/2017
ms.author: sarinas
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 1d773f8c7509fa4bbf872ae62f03bbb4da815d84
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2019
ms.locfileid: "61221029"
---
# <a name="how-to-refresh-your-xero-content-pack-credentials-if-refresh-failed"></a>Aktualisieren der Anmeldeinformationen für das Xero-Inhaltspaket nach einem Aktualisierungsfehler
Wenn Sie das Xero-Inhaltspaket für Power BI verwenden, sind Sie möglicherweise auf Probleme bei der täglichen Aktualisierung des Inhaltspakets festgestellt, das kürzlich durch eine Störung des Power BI-Diensts verursacht wurde.

Sie können feststellen, ob Ihr Inhaltspaket erfolgreich aktualisiert wurde, indem Sie den letzten Aktualisierungsstatus des Xero-Datasets überprüfen, wie im folgenden Screenshot gezeigt.

![](media/service-refresh-xero-credentials/powerbi-xero-refresh-failed.png)

Wenn Sie sehen, dass die Aktualisierung wie oben gezeigt fehlgeschlagen ist, befolgen Sie diese Schritte, um die Anmeldeinformationen für das Inhaltspaket zu erneuern.

1. Klicken Sie auf die Auslassungspunkte (...) neben dem Xero-Dataset, und klicken Sie dann auf **Aktualisierung planen**. Dadurch wird die Einstellungsseite für das Xero-Inhaltspaket geöffnet.
   
    ![](media/service-refresh-xero-credentials/powerbi-xero-schedule-refresh.png)
2. Wählen Sie auf der Seite **Einstellungen für Xero** die Option **Anmeldeinformationen für die Datenquelle** > **Anmeldeinformationen bearbeiten** aus.
   
    ![](media/service-refresh-xero-credentials/powerbi-xero-settings-page.png)
3. Geben Sie den Namen Ihrer Organisation ein, und klicken Sie auf **Weiter**.
   
    ![](media/service-refresh-xero-credentials/powerbi-xero-configure.png)
4. Melden Sie sich mit Ihrem Xero-Konto an.
   
    ![](media/service-refresh-xero-credentials/powerbi-xero-welcome.png)
5. Nachdem Sie Ihre Anmeldeinformationen aktualisiert haben, möchten jetzt wir sicherstellen, dass im Aktualisierungszeitplan die tägliche Ausführung festgelegt ist. Klicken Sie dazu auf die Auslassungspunkte (...) neben dem Xero-Dataset, und klicken Sie dann erneut auf **Aktualisierung planen**.
   
    ![](media/service-refresh-xero-credentials/powerbi-xero-refresh-schedule.png)
6. Sie können das Dataset auch sofort aktualisieren. Klicken Sie auf die Auslassungspunkte (...) neben dem Xero-Dataset, und klicken Sie dann auf **Jetzt aktualisieren**.
   
    ![](media/service-refresh-xero-credentials/powerbi-xero-refresh-now.png)

Wenn weiterhin Probleme beim Aktualisieren auftreten, wenden Sie sich unter [http://support.powerbi.com](http://support.powerbi.com) an uns. 

Weitere Informationen zum Xero-Inhaltspaket für Power BI finden Sie auf der [Hilfeseite für das Xero-Inhaltspaket](service-connect-to-xero.md).

### <a name="next-steps"></a>Nächste Schritte
* Weitere Fragen? [Wenden Sie sich an die Power BI-Community](http://community.powerbi.com/)

