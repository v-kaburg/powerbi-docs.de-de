---
title: Herstellen einer Verbindung mit Azure Security Center mithilfe von Power BI
description: "Azure Security Center für Power BI"
services: powerbi
documentationcenter: 
author: joeshoukry
manager: kfile
backup: maggiesMSFT
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/16/2017
ms.author: yshoukry
ms.openlocfilehash: d052bc054e55eabfab53ad3b1ac9229f0a750785
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2017
---
# <a name="connect-to-azure-security-center-with-power-bi"></a>Herstellen einer Verbindung mit Azure Security Center mithilfe von Power BI
Verknüpfen Sie die Azure Security-Daten mit Power BI, um Erkenntnisse zur Sicherheit der Azure-Arbeitslast zu gewinnen. Power BI erstellt automatisch ein Dashboard und einen Bericht anhand der Azure Security Center-Daten, sodass Sie die Daten analysieren und untersuchen können.

Stellen Sie eine Verbindung mit dem [Azure Security Center-Inhaltspaket](https://app.powerbi.com/getdata/services/azure-security-center) für Power BI her.

## <a name="how-to-connect"></a>Herstellen der Verbindung
1. Wählen Sie unten im linken Navigationsbereich **Daten abrufen** aus.
   
   ![](media/service-connect-to-azure-security-center/getdata.png)
2. Wählen Sie im Feld **Dienste** die Option **Abrufen**aus.
   
   ![](media/service-connect-to-azure-security-center/services.png)
3. Wählen Sie **Azure Security Center** \> **Abrufen** aus.
   
   ![](media/service-connect-to-azure-security-center/asc.png)
4. Geben Sie Ihre Abonnement-ID an. Unten finden Sie Einzelheiten zum [Suchen dieser Parameter](#FindingParams).
   
   ![](media/service-connect-to-azure-security-center/params.png)
5. Wählen Sie als **Authentifizierungsmethode** die Option **oAuth2** \> **Anmelden** aus. Wenn Sie dazu aufgefordert werden, geben Sie Ihre Azure-Anmeldeinformationen ein.
   
    ![](media/service-connect-to-azure-security-center/creds.png)
6. Nach der Genehmigung wird der Importvorgang automatisch gestartet. Nach Abschluss des Vorgangs werden im Navigationsbereich ein neues Dashboard, ein Bericht und ein Modell angezeigt. Wählen Sie das Dashboard aus, um die importierten Daten anzuzeigen.
   
     ![](media/service-connect-to-azure-security-center/dashboard.png)

**Was nun?**

* Versuchen Sie, am oberen Rand des Dashboards [im Q&A-Feld eine Frage zu stellen](service-q-and-a.md).
* [Ändern Sie die Kacheln](service-dashboard-edit-tile.md) im Dashboard.
* [Wählen Sie eine Kachel aus](service-dashboard-tiles.md), um den zugrunde liegenden Bericht zu öffnen.
* Ihr Dataset ist auf eine tägliche Aktualisierung festgelegt. Sie können jedoch das Aktualisierungsintervall ändern oder es über **Jetzt aktualisieren** nach Bedarf aktualisieren.

## <a name="whats-included"></a>Inhalt
Das Inhaltspaket bietet Erkenntnisse im Hinblick auf die Statistik der Ressourcensicherheit, Analysen von Warnungen und Präventionsanalysen.

## <a name="system-requirements"></a>Systemanforderungen
Dieses Inhaltspaket erfordert Zugriff auf eine Abonnement-ID mit aktiviertem Azure Security Center. Weitere Informationen finden Sie im [Azure Security Center](https://portal.azure.com/#blade/Microsoft_Azure_Security/SecurityDashboardStartBladeV2) im Azure-Portal.

Bei Inhaltspaketen ist es erforderlich, dass der Benutzer mit einem Unternehmenskonto angemeldet ist (nicht mit seinem persönlichen Konto).

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>Suchen von Parametern
Es gibt zwei einfache Möglichkeiten, Ihre Abonnement-ID zu suchen.

1. Über „https://portal.azure.com“ &gt; „Durchsuchen“ &gt; „Abonnements“ &gt; „Abonnement-ID“
2. Über „https://manage.windowsazure.com“ &gt; „Einstellungen“ &gt; „Abonnement-ID“

Ihre Abonnement-ID besteht aus einer langen Abfolge von Zahlen und Zeichen, ähnlich wie in dem Beispiel in Schritt 4 oben. 

## <a name="troubleshooting"></a>Problembehandlung
Je nach Größe Ihres Kontos kann es eine gewisse Zeit dauern, bis die Daten geladen sind. Wenn während der Anmeldung ein Fehler auftritt, überprüfen Sie die Parameter, und vergewissern Sie sich, dass Azure Security Center im Konto aktiviert ist.

Wenn das Inhaltspaket geladen wird, aber keine Daten angezeigt werden, stellen Sie sicher, dass Ihr Zugriff über ein Unternehmenskonto erfolgt. Obwohl persönliche Konten durch Azure Security Center unterstützt werden, gibt die API (und damit betrifft dies auch das Inhaltspaket) nur dann die erwarteten Werte zurück, wenn der Benutzer mit einem Unternehmenskonto angemeldet ist. Melden Sie sich mit einem Unternehmenskonto an, und stellen Sie die Verbindung erneut her.

## <a name="next-steps"></a>Nächste Schritte
[Erste Schritte mit Power BI](service-get-started.md)

[Abrufen von Daten in Power BI](service-get-data.md)

