---
title: Herstellen einer Verbindung mit Lithium mithilfe von Power BI
description: Lithium für Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 6fa16cf59ece7f701fc50f1914138b9ca5362c45
ms.sourcegitcommit: 762857c8ca09ce222cc3f8b006fa1b65d11e4ace
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/05/2019
ms.locfileid: "66720459"
---
# <a name="connect-to-lithium-with-power-bi"></a>Herstellen einer Verbindung mit Lithium mithilfe von Power BI
Lithium dient zum Aufbauen von Vertrauensverhältnissen zwischen weltweit führenden Herstellern und ihren Kunden und hilft beim Erhalten von Antworten und Weitergeben von Erfahrungen. Durch Verbinden des Lithium-Inhaltspakets mit Power BI können Sie wichtige Metriken in Ihrer Onlinecommunity messen, um den Verkauf anzukurbeln, Servicekosten zu senken und die Kundentreue zu steigern. 

Stellen Sie die Verbindung mit dem [Lithium-Inhaltspaket](https://app.powerbi.com/getdata/services/lithium) für Power BI her.

>[!NOTE]
>Das Power BI-Inhaltspaket verwendet die Lithium-API. Übermäßig viele Aufrufe der API führen möglicherweise zu zusätzlichen Lithium-Kosten. Sprechen Sie sich Sie mit Ihrem Lithium-Administrator ab.

## <a name="how-to-connect"></a>Herstellen der Verbindung
1. Wählen Sie unten im linken Navigationsbereich **Daten abrufen** aus.
   
   ![](media/service-connect-to-lithium/pbi_getdata.png) 
2. Wählen Sie im Feld **Dienste** die Option **Abrufen**aus.
   
   ![](media/service-connect-to-lithium/pbi_getservices.png) 
3. Wählen Sie **Lithium** \> **Abrufen** aus.
   
   ![](media/service-connect-to-lithium/lithiumconnect.png)
4. Geben Sie die URL Ihrer Lithium-Community an. Diese weist das Format *https://community.yoursite.com* auf.
   
   ![](media/service-connect-to-lithium/params.png)
5. Geben Sie bei Aufforderung Ihre Lithium-Anmeldeinformationen ein. Wählen Sie als Authentifizierungsmethode **oAuth 2** aus. Klicken Sie auf **Anmelden**, und befolgen Sie die Schritte zur Lithium-Authentifizierung.
   
   ![](media/service-connect-to-lithium/creds.png)
   
   ![](media/service-connect-to-lithium/creds2.png)
6. Nach Abschluss der Anmeldung wird den Importvorgang gestartet. Nach Abschluss des Vorgangs werden im Navigationsbereich ein neues Dashboard, ein Bericht und ein Modell angezeigt. Wählen Sie das Dashboard aus, um die importierten Daten anzuzeigen.
   
    ![](media/service-connect-to-lithium/lithium.png)

**Was nun?**

* Versuchen Sie, am oberen Rand des Dashboards [im Q&A-Feld eine Frage zu stellen](consumer/end-user-q-and-a.md).
* [Ändern Sie die Kacheln](service-dashboard-edit-tile.md) im Dashboard.
* [Wählen Sie eine Kachel aus](consumer/end-user-tiles.md), um den zugrunde liegenden Bericht zu öffnen.
* Zwar ist Ihr Dataset auf tägliche Aktualisierung festgelegt, jedoch können Sie das Aktualisierungsintervall ändern oder über **Jetzt aktualisieren** nach Bedarf aktualisieren.

## <a name="system-requirements"></a>Systemanforderungen
Das Lithium-Inhaltspaket erfordert mindestens die Lithium Community-Version 15.9. Konsultieren Sie zur Überprüfung Ihren Lithium-Administrator.

## <a name="next-steps"></a>Nächste Schritte
[Was ist Power BI?](power-bi-overview.md)

[Grundlegende Konzepte für Designer im Power BI-Dienst](service-basic-concepts.md)

