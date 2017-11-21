---
title: Herstellen einer Verbindung mit AT Internet Bridge mithilfe von Power BI
description: "AT Internet Bridge für Power BI"
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
ms.openlocfilehash: a96e4b0f20eaea1a9f9e9fc71ea2724952f61fc3
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2017
---
# <a name="connect-to-at-internet-bridge-with-power-bi"></a>Herstellen einer Verbindung mit AT Internet Bridge mithilfe von Power BI
AT Internet ermöglicht Ihnen mithilfe seiner Analytics Suite, einer vereinheitlichten digitalen Analyseplattform, einen unmittelbaren Nutzen aus Ihren Daten zu ziehen. Das AT Internet Bridge-Inhaltspaket für Power BI enthält Daten zu Seitenaufrufen, Datenquellen, Lokalisierung und Geräten für Ihre Website.

Stellen Sie die Verbindung zum [AT Internet Bridge-Inhaltspaket](https://app.powerbi.com/getdata/services/at-internet-bridge) für Power BI her.

## <a name="how-to-connect"></a>Herstellen der Verbindung
1. Wählen Sie unten im linken Navigationsbereich **Daten abrufen** aus.
   
   ![](media/service-connect-to-at-internet/pbi_getdata.png) 
2. Wählen Sie im Feld **Dienste** die Option **Abrufen**aus.
   
   ![](media/service-connect-to-at-internet/pbi_getservices.png) 
3. Wählen Sie **AT Internet Bridge** \> **Abrufen** aus.
   
   ![](media/service-connect-to-at-internet/atinternet.png)
4. Geben Sie Nummer der AT Internet-Website an, mit der Sie eine Verbindung herstellen möchten.
   
   ![](media/service-connect-to-at-internet/params.png)
5. Wählen Sie als Authentifizierungsmechanismus **Standard** aus, geben Sie Ihren AT Internet-Benutzernamen und Ihr Kennwort an, und klicken Sie auf **Anmelden**.
   
   ![](media/service-connect-to-at-internet/creds.png)
6. Klicken Sie auf **Verbinden** , um den Importvorgang zu starten. Nach Abschluss des Vorgangs werden im Navigationsbereich ein neues Dashboard, ein Bericht und ein Modell angezeigt. Wählen Sie das Dashboard aus, um die importierten Daten anzuzeigen.
   
    ![](media/service-connect-to-at-internet/atinternet.png)

**Was nun?**

* Versuchen Sie, am oberen Rand des Dashboards [im Q&A-Feld eine Frage zu stellen](service-q-and-a.md).
* [Ändern Sie die Kacheln](service-dashboard-edit-tile.md) im Dashboard.
* [Wählen Sie eine Kachel aus](service-dashboard-tiles.md), um den zugrunde liegenden Bericht zu öffnen.
* Ihr Dataset ist auf eine tägliche Aktualisierung festgelegt. Sie können jedoch das Aktualisierungsintervall ändern oder es über **Jetzt aktualisieren** nach Bedarf aktualisieren.

## <a name="whats-included"></a>Inhalt
Dieses Inhaltspaket enthält Daten der letzten 45 Tage in den folgenden Tabellen:  

    - Conversion (Konvertierung)  
    - Devices (Geräte)  
    - Localization (Lokalisierung)  
    - Sources (Quellen)  
    - Global Visits (Besuche weltweit)  

## <a name="next-steps"></a>Nächste Schritte
[Erste Schritte mit Power BI](service-get-started.md)

[Power BI – Grundkonzepte](service-basic-concepts.md)

