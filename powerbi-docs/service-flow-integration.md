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
ms.date: 01/22/2018
ms.author: mihart
ms.openlocfilehash: edae145e8eef6dfe7a2c4cea3a7f467f6f7961a9
ms.sourcegitcommit: c3be4de522874fd73fe6854333b379b85619b907
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2018
---
# <a name="microsoft-flow-and-power-bi"></a>Microsoft Flow und Power BI

[Microsoft Flow](https://flow.microsoft.com/en-us/documentation/getting-started) ist ein SaaS-Dienst zum Automatisieren von Workflows zwischen den immer zahlreicheren Anwendungen und SaaS-Diensten, auf die Geschäftsbenutzer zugreifen. Mit Flow können Sie Aufgaben automatisieren, indem Sie Ihre bevorzugten Apps und Dienste (einschließlich Power BI) synchronisieren, um Benachrichtigungen zu erhalten, Dateien zu synchronisieren, Daten zu sammeln und weitere Aktionen ausführen zu lassen. Die Automatisierung von Workflows vereinfacht Aufgaben, die sich wiederholen.

[Erste Schritte mit Flow](https://flow.microsoft.com/documentation/getting-started)

Sehen Sie sich an, wie Sirui einen Flow erstellt, der eine detaillierte E-Mail an Kollegen versendet, wenn eine Power BI-Warnung ausgelöst wird. Befolgen Sie dann die schrittweisen Anleitungen unter dem Video, um es selbst ausprobieren.

<iframe width="560" height="315" src="https://www.youtube.com/embed/YhmNstC39Mw" frameborder="0" allowfullscreen></iframe>

## <a name="create-a-flow-that-is-triggered-by-a-power-bi-data-alert"></a>Erstellen eines Flows, der durch eine Power BI-Datenwarnung ausgelöst wird

### <a name="prerequisites"></a>Voraussetzungen
In diesem Tutorial erfahren Sie, wie Sie zwei verschiedene Flows erstellen: einen Flow aus einer Vorlage und einen von Grund auf neuen Flow. Um die Schritte des Tutorials auszuführen, [erstellen Sie in Power BI eine Datenwarnung](service-set-data-alerts.md), erstellen ein kostenloses Slack-Konto und [registrieren Sie sich für Microsoft Flow](https://flow.microsoft.com/en-us/#home-signup) (kostenlos!).

## <a name="create-a-flow-that-uses-power-bi---from-a-template"></a>Erstellen eines Flows, der Power BI verwendet – aus einer Vorlage
In dieser Aufgabe verwenden wir eine Vorlage, um einen einfachen Flow zu erstellen, der durch eine Power BI-Datenwarnung (Benachrichtigung) ausgelöst wird.

1. Melden Sie sich bei Microsoft Flow („flow.microsoft.com“) an.
2. Wählen Sie **Meine Flows** aus.
   
   ![](media/service-flow-integration/power-bi-my-flows.png)
3. Wählen Sie **Aus Vorlage erstellen** aus.
   
    ![](media/service-flow-integration/power-bi-template.png)
4. Verwenden Sie das Suchfeld, um Power BI-Vorlagen zu suchen, und wählen Sie **Eine E-Mail an eine beliebige Zielgruppe senden, sobald durch Power BI-Daten eine Warnung ausgelöst wird > Weiter** aus.
   
    ![](media/service-flow-integration/power-bi-flow-alert.png)


### <a name="build-the-flow"></a>Erstellen des Flows
Diese Vorlage verfügt über einen Trigger (Power BI-Datenwarnung bei neuen Olympiamedaillen für Irland) und eine Aktion (E-Mail senden). Wenn Sie ein Feld auswählen, werden dynamische Inhalte angezeigt, die Sie einschließen können.  In diesem Beispiel haben wir den Kachelwert und die Kachel-URL in den Nachrichtentext eingefügt.

![](media/service-flow-integration/power-bi-template1.png)

1. Wählen Sie in der Trigger-Dropdownliste eine Power BI-Datenwarnung aus. Wählen Sie die Option **New medal for Ireland** (Neue Medaille für Irland). Informationen zum Erstellen einer Warnung finden Sie unter [Datenwarnungen in Power BI](service-set-data-alerts.md).
   
   ![](media/service-flow-integration/power-bi-trigger-flow.png)
2. Geben Sie mindestens eine gültige E-Mail-Adresse ein, und wählen Sie dann **Bearbeiten** (siehe unten) oder **Dynamische Inhalte hinzufügen** aus. 
   
   ![](media/service-flow-integration/power-bi-flow-email.png)

3. Flow erstellt einen Titel und eine Nachricht für Sie, den bzw. die Sie beibehalten oder ändern können. Alle Werte, die von Ihnen beim Erstellen der Warnung in Power BI festgelegt wurden, können nun verwendet werden. Platzieren Sie einfach Ihren Cursor, und wählen Sie aus dem grau hervorgehobenen Bereich aus. 

   ![](media/service-flow-integration/power-bi-flow-email-default.png)

1.  Wenn Sie beispielsweise in Power BI eine Warnung mit dem Titel **Wir haben eine weitere Medaille gewonnen** erstellt haben, können Sie **Warnungstitel** auswählen, um den Text in die Betreffzeile Ihrer E-Mail einzufügen.

    ![](media/service-flow-integration/power-bi-flow-message.png)

    Darüber hinaus haben Sie Möglichkeit, den standardmäßigen E-Mail-Text zu übernehmen oder einen eigenen zu erstellen. Das obige Beispiel enthält einige Änderungen an der Nachricht.

1. Wenn Sie fertig sind, wählen Sie **Flow erstellen** oder **Flow speichern** aus.  Der Flow wird erstellt und ausgewertet.  Wenn Fehler gefunden werden, wird Ihnen dies mitgeteilt.
2. Wenn Fehler gefunden wurden, wählen Sie **Fluss bearbeiten** aus, um sie zu beheben. Wählen Sie andernfalls **Fertig** aus, um den neuen Flow auszuführen.
   
   ![](media/service-flow-integration/power-bi-flow-running.png)
5. Sobald die Datenwarnung ausgelöst wird, wird eine E-Mail an die von Ihnen angegeben Adressen gesendet.  
   
   ![](media/service-flow-integration/power-bi-flow-email2.png)

## <a name="create-a-flow-that-uses-power-bi---from-scratch-blank"></a>Erstellen eines Flows, der Power BI verwendet – ohne Vorlage (leer)
In dieser Aufgabe erstellen wir einen einfachen Flow von Grund auf neu, der durch eine Power BI-Datenwarnung (Benachrichtigung) ausgelöst wird.

1. Melden Sie sich bei Microsoft Flow an.
2. Wählen Sie **Meine Flows** > **Ohne Vorlage erstellen** aus.
   
   ![](media/service-flow-integration/power-bi-my-flows.png)
3. Verwenden Sie das Suchfeld, um einen Power BI-Trigger zu suchen, und wählen Sie **Power BI – wenn eine datenbasierte Warnung ausgelöst wird** aus.

### <a name="build-your-flow"></a>Erstellen des Flows
1. Wählen Sie in der Dropdownliste den Namen der Warnung aus.  Informationen zum Erstellen einer Warnung finden Sie unter [Datenwarnungen in Power BI](service-set-data-alerts.md).
   
    ![](media/service-flow-integration/power-bi-totalstores2.png)
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

## <a name="next-steps"></a>Nächste Schritte
* [Erste Schritte mit Microsoft Flow](https://flow.microsoft.com/en-us/documentation/getting-started/)
* [Festlegen von Datenwarnungen im Power BI-Dienst](service-set-data-alerts.md)
* [Festlegen von Datenwarnungen auf dem iPhone](mobile-set-data-alerts-in-the-mobile-apps.md)
* [Festlegen von Datenwarnungen in der mobilen Power BI-App für Windows 10](mobile-set-data-alerts-in-the-mobile-apps.md)
* Weitere Fragen? [Wenden Sie sich an die Power BI-Community](http://community.powerbi.com/)

