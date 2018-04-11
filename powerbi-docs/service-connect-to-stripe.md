---
title: Herstellen einer Verbindung mit Stripe mithilfe von Power BI
description: Stripe für Power BI
services: powerbi
documentationcenter: ''
author: SarinaJoan
manager: kfile
backup: maggiesMSFT
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 8d5c99f901471d61ec8483e1f8c898071ce8c25c
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/24/2018
---
# <a name="connect-to-stripe-with-power-bi"></a>Herstellen einer Verbindung mit Stripe mithilfe von Power BI
Visualisieren und durchsuchen Sie Ihre Stripe-Daten in Power BI mithilfe des Power BI-Inhaltspakets. Das Power BI Stripe-Inhaltspaket ruft Daten zu Kunden, Gebühren, Ereignissen und Rechnungen ab. Die Daten umfassen die neuesten 10.000 Ereignisse und 5.000 Gebühren innerhalb der letzten 30 Tage. Der Inhalt wird automatisch einmal täglich nach einem von Ihnen gesteuerten Zeitplan aktualisiert. 

Stellen Sie eine Verbindung mit dem [Stripe-Inhaltspaket](https://app.powerbi.com/getdata/services/stripe) für Power BI her.

## <a name="how-to-connect"></a>Herstellen der Verbindung
1. Wählen Sie unten im linken Navigationsbereich „Daten abrufen“ aus.  
   
    ![](media/service-connect-to-stripe/getdata.png)
2. Wählen Sie im Feld **Dienste** die Option **Abrufen**aus.  
   
    ![](media/service-connect-to-stripe/services.png)  
3. Wählen Sie **Stripe** &gt; **Abrufen** aus.  
   
    ![](media/service-connect-to-stripe/stripe.png)  
4. Geben Sie Ihren [API-Schlüssel](https://dashboard.stripe.com/account/apikeys) für Stripe ein, um die Verbindung herzustellen.  
   
    ![](media/service-connect-to-stripe/creds.png)
5. Der Importvorgang startet automatisch. Nach Abschluss des Vorgangs werden im Navigationsbereich ein neues Dashboard, ein Bericht und ein Modell (mit einem Sternzeichen gekennzeichnet) angezeigt. Wählen Sie das Dashboard aus, um die importierten Daten anzuzeigen.
   
    ![](media/service-connect-to-stripe/dashboard.png)

**Was nun?**

* Versuchen Sie, am oberen Rand des Dashboards [im Q&A-Feld eine Frage zu stellen](power-bi-q-and-a.md).
* [Ändern Sie die Kacheln](service-dashboard-edit-tile.md) im Dashboard.
* [Wählen Sie eine Kachel aus](service-dashboard-tiles.md), um den zugrunde liegenden Bericht zu öffnen.
* Ihr Dataset ist auf eine tägliche Aktualisierung festgelegt. Sie können jedoch das Aktualisierungsintervall ändern oder es über **Jetzt aktualisieren** nach Bedarf aktualisieren.

## <a name="next-steps"></a>Nächste Schritte
[Erste Schritte mit Power BI](service-get-started.md)

[Abrufen von Daten in Power BI](service-get-data.md)

