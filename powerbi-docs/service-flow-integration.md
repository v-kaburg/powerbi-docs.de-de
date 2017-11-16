---
title: 'Tutorial: Integration von Power BI in Microsoft Flow'
description: "Erfahren Sie, wie Sie Flows erstellen, die durch Power BI-Datenwarnungen ausgelöst werden."
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: YhmNstC39Mw
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/30/2017
ms.author: mihart
ms.openlocfilehash: 387f6bf9f9022fedf1266c32da3d61d3035e7d90
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2017
---
# <a name="microsoft-flow-and-power-bi"></a>Microsoft Flow und Power BI
## <a name="what-is-microsoft-flow"></a>Was ist Microsoft Flow?
[Microsoft Flow](https://flow.microsoft.com/en-us/documentation/getting-started) ist ein SaaS-Dienst zum Automatisieren von Workflows zwischen den immer zahlreicheren Anwendungen und SaaS-Diensten, auf die Geschäftsbenutzer zugreifen. Mit Flow können Sie Aufgaben automatisieren, indem Sie Ihre bevorzugten Apps und Dienste (einschließlich Power BI) synchronisieren, um Benachrichtigungen zu erhalten, Dateien zu synchronisieren, Daten zu sammeln und weitere Aktionen ausführen zu lassen. Die Automatisierung von Workflows vereinfacht Aufgaben, die sich wiederholen.

[Erste Schritte mit Flow](https://flow.microsoft.com/documentation/getting-started)

Sehen Sie sich an, wie Sirui einen Flow erstellt, der eine detaillierte E-Mail an Kollegen versendet, wenn eine Power BI-Warnung ausgelöst wird. Befolgen Sie dann die schrittweisen Anleitungen unter dem Video, um es selbst ausprobieren.

<iframe width="560" height="315" src="https://www.youtube.com/embed/YhmNstC39Mw" frameborder="0" allowfullscreen></iframe>

## <a name="create-a-flow-that-is-triggered-by-a-power-bi-data-alert"></a>Erstellen eines Flows, der durch eine Power BI-Datenwarnung ausgelöst wird
In diesem Tutorial erfahren Sie, wie Sie zwei verschiedene Flows erstellen: einen Flow aus einer Vorlage und einen von Grund auf neuen Flow. Um die Schritte des Tutorials auszuführen, [erstellen Sie in Power BI eine Datenwarnung](service-set-data-alerts.md), und [registrieren Sie sich für Microsoft Flow](https://flow.microsoft.com/en-us/#home-signup) (kostenlos!).

## <a name="create-a-flow-that-uses-power-bi---from-a-template"></a>Erstellen eines Flows, der Power BI verwendet – aus einer Vorlage
In dieser Aufgabe verwenden wir eine Vorlage, um einen einfachen Flow zu erstellen, der durch eine Power BI-Datenwarnung (Benachrichtigung) ausgelöst wird.

1. Melden Sie sich bei Microsoft Flow („flow.microsoft.com“) an.
2. Wählen Sie **Meine Flows** aus.
   
   ![](media/service-flow-integration/power-bi-my-flows.png)
3. Wählen Sie **Aus Vorlage erstellen** aus.
   
    ![](media/service-flow-integration/power-bi-template.png)
4. Verwenden Sie das Suchfeld, um Power BI-Vorlagen zu suchen, und wählen Sie **Post a message to a Slack channel when a Power BI data alert is triggered** (Nachricht in einem Slack-Kanal senden, wenn eine Power BI-Datenwarnung ausgelöst wird) aus.
   
    ![](media/service-flow-integration/power-bi-template2.png)
5. Wählen Sie **Diese Vorlage verwenden** aus.
   
   ![](media/service-flow-integration/power-bi-use-template.png)
6. Wenn Sie dazu aufgefordert werden, stellen Sie eine Verbindung mit Slack und Power BI her, indem Sie **Anmelden** auswählen und dann den Anweisungen folgen. Ein grünes Häkchen gibt an, dass Sie angemeldet sind.  Nachdem Sie die Verbindungen bestätigt haben, wählen Sie **Weiter** aus.
   
   ![](media/service-flow-integration/power-bi-flow-signin.png)

### <a name="build-the-flow"></a>Erstellen des Flows
Diese Vorlage verfügt über einen Trigger (Power BI-Datenwarnung bei neuen Olympiamedaillen für Irland) und eine Aktion (Nachricht an Slack senden). Wenn Sie ein Feld auswählen, werden dynamische Inhalte angezeigt, die Sie einschließen können.  In diesem Beispiel haben wir den Kachelwert und die Kachel-URL in den Nachrichtentext eingefügt.

![](media/service-flow-integration/power-bi-flow-template.png)

1. Wählen Sie in der Trigger-Dropdownliste eine Power BI-Datenwarnung aus. Wählen Sie die Option **New medal for Ireland** (Neue Medaille für Irland). Informationen zum Erstellen einer Warnung finden Sie unter [Datenwarnungen in Power BI](service-set-data-alerts.md).
   
   ![](media/service-flow-integration/power-bi-trigger-flow.png)
2. Geben Sie zum Posten in Slack einen Kanalnamen und einen Nachrichtentext ein (Sie können auch die von Flow erstellte Standardnachricht auswählen). Beachten Sie den dynamischen Inhalt, den wir im Textfeld für Nachrichten hinzugefügt haben.
   
   > [!NOTE]
   > Schließen Sie am Anfang des Kanalnamens ein @-Zeichen ein.  Wenn der Slack-Channel beispielsweise „channelA“ heißt, geben Sie in Flow „@channelA“ ein.
   > 
   > 
   
   ![](media/service-flow-integration/power-bi-flow-slacker.png)
3. Wenn Sie fertig sind, wählen Sie **Flow erstellen** oder **Flow speichern** aus.  Der Flow wird erstellt und ausgewertet.  Wenn Fehler gefunden werden, wird Ihnen dies mitgeteilt.
4. Wenn Fehler gefunden wurden, wählen Sie **Fluss bearbeiten** aus, um sie zu beheben. Wählen Sie andernfalls **Fertig** aus, um den neuen Flow auszuführen.
   
   ![](media/service-flow-integration/power-bi-flow-running.png)
5. Öffnen Sie Ihr Slack-Konto, um die Meldung anzuzeigen.  
   
   ![](media/service-flow-integration/power-bi-slack-message.png)

## <a name="create-a-flow-that-uses-power-bi---from-scratch-blank"></a>Erstellen eines Flows, der Power BI verwendet – ohne Vorlage (leer)
In dieser Aufgabe erstellen wir einen einfachen Flow von Grund auf neu, der durch eine Power BI-Datenwarnung (Benachrichtigung) ausgelöst wird.

1. Melden Sie sich bei Microsoft Flow an.
2. Wählen Sie **Meine Flows** > **Ohne Vorlage erstellen** aus.
   
   ![](media/service-flow-integration/power-bi-my-flows.png)
3. Verwenden Sie das Suchfeld, um einen Power BI-Trigger zu suchen, und wählen Sie **Flow mit einer über Power BI-Daten gesteuerten Warnung auslösen** aus.

### <a name="build-your-flow"></a>Erstellen des Flows
1. Wählen Sie in der Dropdownliste den Namen der Warnung aus.  Informationen zum Erstellen einer Warnung finden Sie unter [Datenwarnungen in Power BI](service-set-data-alerts.md).
   
    ![](media/service-flow-integration/power-bi-totalstores.png)
2. Wählen Sie **Neuer Schritt** > **Aktion hinzufügen** aus.
   
   ![](media/service-flow-integration/power-bi-new-step.png)
3. Suchen Sie nach **Outlook**, und wählen Sie **Ereignis erstellen** aus.
   
   ![](media/service-flow-integration/power-bi-create-event.png)
4. Füllen Sie die Ereignisfelder aus. Wenn Sie ein Feld auswählen, werden dynamische Inhalte angezeigt, die Sie einschließen können.
   
   ![](media/service-flow-integration/power-bi-flow-event.png)
5. Wählen Sie zum Abschluss **Flow erstellen** aus.  Der Flow wird gespeichert und ausgewertet. Wenn keine Fehler vorliegen, wählen Sie **Fertig** aus, um diesen Flow auszuführen.  Der neue Flow wird der Seite **Meine Flüsse** hinzugefügt.
   
   ![](media/service-flow-integration/power-bi-flow-running.png)
6. Wenn der Flow durch die Power BI-Datenwarnung ausgelöst wird, erhalten Sie eine ähnliche Outlook-Ereignisbenachrichtigung wie die folgende.
   
    ![](media/service-flow-integration/power-bi-flow-notice.png)

### <a name="next-steps"></a>Nächste Schritte
* [Erste Schritte mit Microsoft Flow](https://flow.microsoft.com/en-us/documentation/getting-started/)
* [Festlegen von Datenwarnungen im Power BI-Dienst](service-set-data-alerts.md)
* [Festlegen von Datenwarnungen auf dem iPhone](mobile-set-data-alerts-in-the-mobile-apps.md)
* [Festlegen von Datenwarnungen in der mobilen Power BI-App für Windows 10](mobile-set-data-alerts-in-the-mobile-apps.md)
* Weitere Fragen? [Wenden Sie sich an die Power BI-Community](http://community.powerbi.com/)

