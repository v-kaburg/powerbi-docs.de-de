---
title: Herstellen einer Verbindung mit GitHub mithilfe von Power BI
description: GitHub für Power BI
author: maggiesMSFT
manager: kfile
ms.reviewer: sarinas
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 04/26/2019
ms.author: maggies
LocalizationGroup: Connect to services
ms.openlocfilehash: b0f2bd53f1d8b82b70072446723c2ca3723eeacd
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2019
ms.locfileid: "65608435"
---
# <a name="connect-to-github-with-power-bi"></a>Herstellen einer Verbindung mit GitHub mithilfe von Power BI
Dieser Artikel führt Sie durch Abrufen von Daten aus Ihrem GitHub-Konto mit einer Power BI-app-Vorlage. Der vorlagenanwendung generiert einen Arbeitsbereich mit einem Dashboard, eine Reihe von Berichten und ein Dataset, damit Sie Ihre GitHub-Daten analysieren können. Die GitHub-app für Power BI erfahren Sie, Einblicke in Ihr GitHub-Repository, auch bekannt als Repository mit Daten zu Beiträgen, Problemen, pullanforderungen und aktive Benutzer.

Nachdem Sie die Vorlagen-app installiert haben, können Sie auf dem Dashboard und Bericht ändern. Anschließend können Sie sie als app an Kollegen in Ihrer Organisation verteilen.

Herstellen einer Verbindung mit der [GitHub vorlagenanwendung](https://app.powerbi.com/getdata/services/github) oder erfahren Sie mehr über die [GitHub-Integration](https://powerbi.microsoft.com/integrations/github) mit Power BI.

Sie können auch versuchen, den [GitHub Tutorial](service-tutorial-connect-to-github.md). Real-GitHub-Daten über das öffentliche Repository für Power BI-Dokumentation wird installiert.

>[!NOTE]
>Die Vorlagen-app erfordert das GitHub-Konto, um Zugriff auf das Repository zu erhalten. Es folgen weitere Informationen zu den Anforderungen.

## <a name="how-to-connect"></a>Herstellen der Verbindung
[!INCLUDE [powerbi-service-apps-get-more-apps](./includes/powerbi-service-apps-get-more-apps.md)]
   
3. Wählen Sie **GitHub** \> **jetzt**.
4. In **dieses Power BI-App installieren?** wählen **installieren**.
4. In der **Apps** wählen Sie im Bereich der **GitHub** Kachel.

    ![Power BI: GitHub-Kachel](media/service-connect-to-github/power-bi-github-tile.png)

6. In **beginnen Sie mit der neuen app**Option **Verbindungsdaten**.

    ![Erste Schritte mit Ihrer neuen App](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-connect-data.png)

5. Geben Sie den Namen und Besitzer des Repositorys ein. Nachstehend finden Sie weitere Informationen zum [Suchen dieser Parameter](#FindingParams).
   
    ![Power BI: Name des GitHub-Repositorys](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-connect.png)

5. Geben Sie Ihre GitHub-Anmeldeinformationen (dieser Schritt kann übersprungen werden, wenn Sie bereits mit Ihrem Browser angemeldet sind). 
6. Wählen Sie als **Authentifizierungsmethode** die Option **oAuth2** \> **Anmelden** aus. 
7. Führen Sie den Bildschirmen der GitHub-Authentifizierung. Gewähren Sie GitHub für Power BI-Vorlage app-Berechtigung für die GitHub-Daten.
   
   ![Autorisieren von GitHub für Power BI](media/service-connect-to-github/github_authorize.png)
   
    Powerbi verbindet sich mit GitHub und Ihre Daten.  Die Daten werden einmal täglich aktualisiert. Nachdem Power BI die Daten importiert wurden, sehen Sie den Inhalt des neuen GitHub-Arbeitsbereichs.

## <a name="modify-and-distribute-your-app"></a>Ändern Sie und verteilen Sie Ihre app

Sie haben die GitHub-app-Vorlage installiert. Das bedeutet, dass Sie auch den GitHub-app-Arbeitsbereich erstellt haben. Im Arbeitsbereich können Sie den Bericht und das Dashboard zu ändern und verteilen Sie es als ein *app* an Kollegen in Ihrer Organisation. 

1. Wählen Sie in der linken Navigationsleiste auf den Pfeil neben der Name des Arbeitsbereichs. Sie sehen, dass der Arbeitsbereich ein Dashboard und einen Bericht enthält.

    ![App im linken Navigationsbereich](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-left-nav-expanded.png)

8. Wählen Sie die neue [GitHub-Dashboard](https://powerbi.microsoft.com/integrations/github).    
    ![GitHub-Dashboards in Power BI](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-new-dashboard.png)

3. Wählen Sie zum Anzeigen der gesamte Inhalt des dem neuen GitHub-Arbeitsbereich, in der linken Navigationsleiste **Arbeitsbereiche** > **GitHub**.
 
   ![Arbeitsbereich "GitHub" im linken Navigationsbereich](media/service-connect-to-github/power-bi-github-left-nav.png)

    Diese Ansicht ist die Liste mit den Inhalten für den Arbeitsbereich. In der oberen rechten Ecke finden Sie **app aktualisieren**. Wenn Sie Ihre app an Ihre Kollegen verteilen möchten, ist, in dem Sie beginnen. 

    ![GitHub content list](media/service-connect-to-github/power-bi-github-content-list.png)

2. Wählen Sie **Berichte** und **Datasets** die anderen Elementen im Arbeitsbereich angezeigt.

    Erfahren Sie mehr über [Verteilen von apps](service-create-distribute-apps.md) an Ihre Kollegen.

## <a name="whats-included-in-the-app"></a>Was ist in der app enthalten.
Die folgenden Daten sind über GitHub in Power BI verfügbar:     

| Tabellenname | Beschreibung |
| --- | --- |
| Beiträge |Die Beiträge-Tabelle enthält die gesamten Zugänge, löschungen und Commits, die von den Mitwirkenden, die wöchentlich aggregiert erstellt wurde. Die Top 100-Mitwirkenden sind inklusive. |
| Probleme |Listet alle Probleme für das ausgewählte Repository auf und enthält Berechnungen wie die gesamte und durchschnittliche Zeit zum Schließen eines Problems, die Gesamtzahl offener Probleme sowie die Gesamtzahl geschlossener Probleme. Diese Tabelle ist leer, wenn im Repository keine Probleme vorliegen. |
| Pullanforderungen |Diese Tabelle enthält alle Pullanforderungen für das Repository und die Information, welcher Benutzer den Pullvorgang für die Anforderung ausgeführt hat. Es enthält auch Berechnungen dazu, wie viele geöffnete, geschlossene und insgesamt pullanforderungen, wie lange es gedauert hat die pullanforderungen und wie lange die durchschnittliche pullanforderung gedauert hat. Diese Tabelle ist leer, wenn im Repository keine Probleme vorliegen. |
| Benutzer |Diese Tabelle enthält eine Liste der GitHub-Benutzern oder Mitwirkenden, die Beiträge geleistet, Probleme gemeldet oder pullanforderungen für das ausgewählte Repository gelöst haben. |
| Meilensteine |Diese Tabelle enthält alle Meilensteine für das ausgewählte Repository. |
| DateTable |Diese Tabelle enthält die Datumsangaben von heute und für vergangene Jahre, die Ihnen ermöglichen, Ihre GitHub-Daten nach Datum zu analysieren. |
| ContributionPunchCard |Diese Tabelle kann als Lochkarte für Beiträge für das ausgewählte Repository verwendet werden. Es zeigt die Commits nach Wochentag und Tagesstunde an. Diese Tabelle ist nicht mit anderen Tabellen im Modell verbunden. |
| RepoDetails |Diese Tabelle enthält die Details für das ausgewählte Repository. |

## <a name="system-requirements"></a>Systemanforderungen
* Das GitHub-Konto, das Zugriff auf das Repository hat  
* Berechtigung für die Power BI für GitHub-App während der erstmaligen Anmeldung Nachstehend finden Sie Details zum Sperren des Zugriffs.  
* Ausreichende Anzahl verfügbarer API-Aufrufe zum Abrufen und Aktualisieren der Daten  

### <a name="de-authorize-power-bi"></a>Aufheben der Autorisierung von Power BI
Um die Power BI Autorisierung zur mit Ihrem GitHub-Repository verbunden wird, können Sie den Zugriff in GitHub widerrufen. Finden Sie in diesem [Hilfe zu GitHub](https://help.github.com/articles/keeping-your-ssh-keys-and-application-access-tokens-safe/#reviewing-your-authorized-applications-oauth) Informationen.

<a name="FindingParams"></a>
## <a name="finding-parameters"></a>Suchen von Parametern
Sie können den Besitzer und das Repository ermitteln, indem Sie das Repository in GitHub betrachten:

![Repository-Namen und Besitzer](media/service-connect-to-github/github_ownerrepo.png)

Der erste Teil „Azure“ ist der Besitzer und der zweite Teil „azure-sdk-for-php“ ist das Repository selbst.  Dieselben beiden Elemente werden in der URL des Repositorys angezeigt:

    <https://github.com/Azure/azure-sdk-for-php> .

## <a name="troubleshooting"></a>Problembehandlung
Bei Bedarf können Sie Ihre GitHub-Anmeldeinformationen überprüfen.  

1. In einem anderen Browserfenster wechseln Sie zur GitHub-Website, und melden Sie sich bei GitHub. Sie können in der oberen rechten Ecke der GitHub-Website sehen, dass Sie angemeldet sind.    
2. Navigieren Sie in GitHub zur URL des Repositorys, auf das Sie in Power BI zugreifen möchten. Beispiel: https://github.com/dotnet/corefx  
3. Versuchen Sie anschließend in Power BI, die Verbindung zu GitHub herzustellen. Verwenden Sie im Dialogfeld zum Konfigurieren von GitHub den Namen und Besitzer des Repositorys für dasselbe Repository.  

## <a name="next-steps"></a>Nächste Schritte

* [Tutorial: Verbinden Sie mit einem GitHub-Repository mit Power BI](service-tutorial-connect-to-github.md)
* [Erstellen Sie die neue Arbeitsbereiche in Power BI](service-create-the-new-workspaces.md)
* [Installieren und Verwenden von Apps in Power BI](consumer/end-user-apps.md)
* [Verbinden Sie mit Power BI-apps für externe Dienste](service-connect-to-services.md)
* Haben Sie Fragen? [Stellen Sie Ihre Frage in der Power BI-Community.](http://community.powerbi.com/)

