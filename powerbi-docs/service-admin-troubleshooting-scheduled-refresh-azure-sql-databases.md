---
title: Problembehandlung bei der planmäßigen Aktualisierung für Azure SQL-Datenbanken
description: Problembehandlung bei der planmäßigen Aktualisierung für Azure SQL-Datenbanken in Power BI
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 12/06/2017
ms.author: mblythe
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 9439ac6bd0b4df568b964f548372fb94d2fd0b26
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2018
ms.locfileid: "34238524"
---
# <a name="troubleshooting-scheduled-refresh-for-azure-sql-databases-in-power-bi"></a>Problembehandlung bei der planmäßigen Aktualisierung für Azure SQL-Datenbanken in Power BI
Ausführliche Schritte zum Einrichten der planmäßigen Aktualisierung finden Sie unter [Aktualisieren von Daten in Power BI](refresh-data.md).

Wenn Sie beim Einrichten der planmäßigen Aktualisierung für die Azure SQL-Datenbank bei der Bearbeitung der Anmeldeinformationen einen Fehler mit Fehlercode 400 erhalten, versuchen Sie Folgendes, um die entsprechende Firewall-Regel einzurichten:

1. Melden Sie sich beim Azure-Verwaltungsportal an.
2. Wechseln Sie zu dem Azure SQL-Server, für den Sie die Aktualisierung konfigurieren.
3. Aktivieren Sie "Windows Azure Services" im Abschnitt "Zulässige Dienste".

![](media/service-admin-troubleshooting-scheduled-refresh-azure-sql-databases/azurerefresh.png)  

Weitere Fragen? [Wenden Sie sich an die Power BI-Community](http://community.powerbi.com/)

