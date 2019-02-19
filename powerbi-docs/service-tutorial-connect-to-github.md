---
title: 'Tutorial: Herstellen einer Verbindung mit einem GitHub-Beispiel mit Power BI'
description: In diesem Tutorial stellen Sie mit Power BI eine Verbindung mit realen Daten im GitHub-Dienst her. Anschließend erstellt Power BI automatisch Dashboards und Berichte.
author: maggiesMSFT
manager: kfile
ms.reviewer: SarinaJoan
ms.service: powerbi
ms.subservice: powerbi-service
ms.custom: connect-to-services
ms.topic: tutorial
ms.date: 05/17/2018
ms.author: maggies
LocalizationGroup: Connect to services
ms.openlocfilehash: 8f44356f79b8a77ef06fe464671dbbaaaa4187e9
ms.sourcegitcommit: 5e83fa6c93a0bc6599f76cc070fb0e5c1fce0082
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/13/2019
ms.locfileid: "56215573"
---
# <a name="tutorial-connect-to-a-github-sample-with-power-bi"></a>Tutorial: Herstellen einer Verbindung mit einem GitHub-Beispiel mit Power BI
In diesem Tutorial stellen Sie mit Power BI eine Verbindung mit realen Daten im GitHub-Dienst her. Anschließend erstellt Power BI automatisch Dashboards und Berichte. Sie stellen eine Verbindung mit dem öffentlichen *Repository* mit Power BI-Inhalten her und sehen dort Informationen, wie z.B. die Anzahl der Mitwirkenden an öffentlichen Power BI-Inhalten. Sie erfahren, wer sich am aktivsten beteiligt und am welchen Tag der Woche es die meisten Beiträge gab. Außerdem finden Sie Antworten auf weitere Fragen. 

![Der GitHub-Bericht in Power BI](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-punch-card.png)

In diesem Tutorial führen Sie die folgenden Schritte aus:

> [!div class="checklist"]
> * Registrieren für ein GitHub-Konto, falls Sie noch keines haben 
> * Anmelden bei Ihrem Power BI-Konto oder sich dafür registrieren, falls Sie noch keines haben
> * Öffnen des Power BI-Diensts
> * Navigieren zur GitHub-App
> * Eingeben der Informationen für das öffentliche GitHub-Repository von Power BI
> * Anzeigen des Dashboards und Berichts mit GitHub-Daten
> * Bereinigen von Ressourcen durch Löschen der App

Wenn Sie noch nicht bei Power BI registriert sind, müssen Sie sich zuerst für eine [kostenlose Testversion registrieren](https://app.powerbi.com/signupredirect?pbi_source=web).

## <a name="prerequisites"></a>Voraussetzungen

Für dieses Tutorial benötigen Sie ein GitHub-Konto, falls Sie noch keines haben. 

- Registrieren für ein [GitHub-Konto](https://docs.microsoft.com/contribute/get-started-setup-github)


## <a name="how-to-connect"></a>Herstellen der Verbindung
1. Melden Sie sich beim Power BI-Dienst (http://powerbi.com)) an. 
2. Wählen Sie im linken Navigationsbereich **Apps** und dann **Apps abrufen** aus.
   
   ![Power BI-Option „Apps abrufen“](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial.png) 

3. Wählen Sie **Apps** aus, geben Sie **github** in das Suchfeld ein, und klicken Sie dann auf **Jetzt anfordern**.
   
   ![Power BI-Option zum Anfordern von GitHub](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-get-it-now.png) 

4. Geben Sie den Namen und Besitzer des Repositorys ein. Die URL für dieses Repository ist https://github.com/MicrosoftDocs/powerbi-docs, sodass **MicrosoftDocs** der **Besitzer des Repositorys** und **Powerbi-Docs** das **Repository** ist. 
   
    ![Power BI: Name des GitHub-Repositorys](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-repo-name.png)

5. Geben Sie die GitHub-Anmeldeinformationen ein, die Sie erstellt haben. Power BI überspringt diesen Schritt möglicherweise, wenn Sie bereits in Ihrem Browser bei GitHub angemeldet sind. 

6. Wählen Sie als **Authentifizierungsmethode** die Option **oAuth2** \> **Anmelden** aus.

7. Befolgen Sie die Anweisungen auf den Bildschirmen der Github-Authentifizierung. Erteilen Sie den GitHub-Daten die Berechtigung für Power BI.
   
   Jetzt kann Power BI eine Verbindung mit GitHub und den Daten herstellen.  Die Daten werden einmal täglich aktualisiert.

8. Nachdem Power BI die Daten importiert hat, sehen Sie die neue GitHub-Kachel. 
 
   ![Power BI: GitHub-Kachel](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-tile.png) 

8. Klicken Sie auf das Symbol für die globale Navigation, um den linken Navigationsbereich zu minimieren, damit Sie mehr Platz haben.

    ![Symbol „Globale Navigation“](media/service-tutorial-connect-to-github/power-bi-global-navigation-icon.png)

10. Wählen Sie die GitHub-Kachel aus Schritt 8 aus. 
    
    Das GitHub-Dashboard wird geöffnet. Dies sind Livedaten, weshalb die angezeigten Werte ggf. anders sind.

    ![GitHub-Dashboard in Power BI](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-dashboard.png)

    

## <a name="ask-a-question"></a>Frage stellen

11. Platzieren Sie den Cursor in **Stellen Sie eine Frage zu Ihren Daten**, und wählen Sie dann **Pull Requests** aus. 

    ![Power BI-Option „Stellen Sie eine Frage zu Ihren Daten.“](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-ask-question.png)

12. Geben Sie **by month** ein.
 
    ![Pull Requests nach Monat](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-ask-question-by-month.png)

     Power BI erstellt ein Balkendiagramm, das die Anzahl der Pull Requests pro Monat zeigt.

13. Klicken Sie auf **Q&A verlassen**.

## <a name="view-the-github-report"></a>Anzeigen des GitHub-Berichts 

1. Wählen Sie im GitHub-Dashboard die Kombination aus Spalten- und Liniendiagramm **Pull Requests by month** aus, um den zugehörigen Bericht zu öffnen.

    ![Kombinationsdiagramm „Pull Requests by month“](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-pull-requests-combo-chart.png)

2. Wählen Sie im Diagramm **Total pull requests by user** einen Benutzernamen aus. Sie sehen in diesem Beispiel, dass die durchschnittliche Anzahl der Stunden höher ist als der Gesamtdurchschnitt für März.

    ![Power BI mit Hervorhebung im GitHub-Bericht](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-report-highlight.png)

3. Wählen Sie die Registerkarte **Punktekarte** aus, um die nächste Seite im Bericht anzuzeigen. 
 
    ![Power BI mit Punktekarte im GitHub-Bericht](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-tues-3pm.png)

    Anscheinend ist dienstags 15:00 Uhr der häufigste Zeitpunkt für *Commits*, wenn Mitarbeiter ihre Arbeit einchecken.

## <a name="clean-up-resources"></a>Bereinigen von Ressourcen

Nachdem Sie das Tutorial abgeschlossen haben, können Sie die GitHub-App löschen. 

1. Wählen Sie auf der linken Navigationsleiste **Apps** aus.
2. Zeigen Sie auf die GitHub-Kachel, und klicken Sie auf das Symbol **Löschen**.

    ![GitHub-App löschen](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-delete.png)

## <a name="next-steps"></a>Nächste Schritte

In diesem Tutorial haben Sie eine Verbindung mit einem öffentlichen GitHub-Repository hergestellt und Daten abgerufen, die Power BI in einem Dashboard und einem Bericht formatiert hat. Sie haben einige Fragen zu den Daten beantwortet, indem Sie das Dashboard und den Bericht untersucht haben. Jetzt können Sie mehr über das Herstellen einer Verbindung mit anderen Diensten wie Salesforce, Microsoft Dynamics und Google Analytics erfahren. 
 
> [!div class="nextstepaction"]
> [Herstellen einer Verbindung mit von Ihnen verwendeten Onlinediensten](service-connect-to-services.md)


