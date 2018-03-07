---
title: "Drittanbieterdienst: Google Analytics-Connector für Power BI Desktop"
description: "Drittanbieterdienst: Google Analytics-Connector für Power BI Desktop"
services: powerbi
documentationcenter: 
author: davidiseminger
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 12/06/2017
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: e05f64b52c34b3f038994e9cac8a9b7e6aebc7ad
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/24/2018
---
# <a name="google-analytics-connector-for-power-bi-desktop"></a>Google Analytics-Connector für Power BI Desktop
> [!NOTE]
> Das Google Analytics-Inhaltspaket und der Connector in Power BI Desktop basieren auf der Google Analytics Core Reporting-API. Daher können Funktionen und Verfügbarkeit im Laufe der Zeit variieren.
> 
> 

Sie können mithilfe des **Google Analytics**-Connectors eine Verbindung zu Google Analytics-Daten herstellen. Gehen Sie dazu folgendermaßen vor:

1. Wählen Sie in **Power BI Desktop** auf der Registerkarte des Menübands **Start** den Eintrag **Daten abrufen**.
2. Wählen Sie im Fenster **Daten abrufen** aus den Kategorien im linken Bereich **Andere** .
3. Wählen Sie **Google Analytics** aus der Auswahl im rechten Bereich aus.
4. Wählen Sie am unteren Rand des Fensters **Verbinden**aus.  
   ![](media/service-google-analytics-connector/tps_googleanalytics_1.png)

Es erscheint ein Dialogfeld, in dem neben anderen Klarstellungen erläutert wird, dass der Connector ein Dienst von Drittanbietern ist, und in dem davor gewarnt wird, wie Funktionen und Verfügbarkeit sich im Laufe der Zeit ändern können.  
![](media/service-google-analytics-connector/tps_googleanalytics_2.png)

Wenn Sie **Weiter** wählen, werden Sie dazu aufgefordert, sich bei Google Analytics anzumelden.  
![](media/service-google-analytics-connector/tps_googleanalytics_3.png)

Wenn Sie Ihre Anmeldeinformationen eingeben, wird Ihnen mitgeteilt, dass Power BI den Offlinezugriff möchte. So nutzen Sie **Power BI Desktop** zum Zugriff auf Ihre Google Analytics-Daten.  

Sobald Sie dies akzeptiert haben, zeigt **Power BI Desktop** an, dass Sie derzeit angemeldet sind.  
![](media/service-google-analytics-connector/tps_googleanalytics_5.png)

Wählen Sie **Verbinden**. Ihre Google Analytics-Daten sind mit **Power BI Desktop** verbunden, und die Daten werden geladen.  
![](media/service-google-analytics-connector/tps_googleanalytics_6.png)

## <a name="changes-to-the-api"></a>Änderungen an der API
Obwohl wir versuchen, gemäß allen Änderungen Updates zu veröffentlichen, könnte die API so abgeändert werden, dass sich dies auf die Ergebnisse der generierten Abfragen auswirkt. In einigen Fällen könnten bestimmte Abfragen nicht mehr unterstützt werden. Aufgrund dieser Abhängigkeit können wir die Ergebnisse Ihrer Abfragen nicht garantieren, wenn Sie diesen Connector verwenden.

Weitere Informationen zu Änderungen an der Google Analytics-API finden Sie im [Änderungsprotokoll](https://developers.google.com/analytics/devguides/changelog).

