---
title: Inhaltspaket für die SQL-Datenbanküberwachung
description: Inhaltspaket für Power BI für die SQL-Datenbanküberwachung
author: SarinaJoan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 08/10/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: f0c98d88ad9b87e57cf8f1cf7c36a58e30b684ea
ms.sourcegitcommit: 0ff358f1ff87e88daf837443ecd1398ca949d2b6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/21/2018
ms.locfileid: "46545358"
---
# <a name="sql-database-auditing-content-pack-for-power-bi"></a>Inhaltspaket für Power BI für die SQL-Datenbanküberwachung
Dieses Power BI-Inhaltspaket für die Azure [SQL-Datenbanküberwachung](http://azure.microsoft.com/documentation/articles/sql-database-auditing-get-started/) kann Sie beim Verstehen der Datenbankaktivität und dem Gewinnen von Einsichten in Abweichungen und Anomalien unterstützen, die auf Geschäftsprobleme oder vermutete Sicherheitsverletzungen hinweisen können. 

Stellen Sie eine Verbindung mit dem [Inhaltspaket für die SQL-Datenbanküberwachung](https://app.powerbi.com/getdata/services/sql-db-auditing) für Power BI her.

>[!NOTE]
>Das Inhaltspaket importiert Daten aus allen Tabellen, die „AuditLogs“ in deren Namen enthalten, und fügt diese an eine Datenmodelltabelle namens „AuditLogs“ an. Die letzten 250 KB an Ereignissen werden einbezogen, und die Daten werden täglich aktualisiert.

## <a name="how-to-connect"></a>Herstellen der Verbindung
1. Wählen Sie unten im linken Navigationsbereich **Daten abrufen** aus.
   
   ![](media/service-connect-to-azure-sql-database-auditing/pbi_getdata.png) 
2. Wählen Sie im Feld "Dienste" die Option "Abrufen" aus.
   
   ![](media/service-connect-to-azure-sql-database-auditing/pbi_getservices.png) 
3. Wählen Sie **SQL-Datenbanküberwachung** \> **Abrufen** aus.
   
   ![](media/service-connect-to-azure-sql-database-auditing/sqldbaudit.png)
4. Führen Sie im Fenster „Mit der SQL-Datenbanküberwachung verbinden“ die folgenden Aktionen aus:
   
   - Geben Sie den Kontonamen für den Azure-Tabellenspeicher oder die URL ein, in dem bzw. unter der die Protokolle gespeichert sind.
   
   - Geben Sie den Namen des SQL Servers ein, der Sie interessiert. Geben Sie „\*“ ein, um Überwachungsprotokolle für alle Server zu laden.
   
   - Geben Sie den Namen der gewünschten SQL-Datenbank ein. Geben Sie „\*“ ein, um Überwachungsprotokolle für alle Datenbanken zu laden.
   
   - Geben Sie den Namen der Azure-Tabelle ein, die die gewünschten Protokolle enthält. Geben Sie „\*“ ein, um Überwachungsprotokolle aus allen Tabellen zu laden, deren Name „AuditLogs“ enthält.
   
   >[!IMPORTANT]
   >Aus Leistungsgründen empfiehlt es sich, immer einen expliziten Tabellennamen anzugeben, selbst wenn alle Überwachungsprotokolle in einer einzelnen Tabelle gespeichert sind.
   
   - Geben Sie das Startdatum der gewünschten Überwachungsprotokolle ein. Geben Sie „\*“ ein, um Überwachungsprotokolle ohne untere Zeitgrenze zu laden, oder geben Sie „1d“ ein, um die Überwachungsprotokolle des letzten Tags zu laden.
   
   - Geben Sie das Enddatum für die Sie interessierenden Überwachungsprotokolle ein. Geben Sie „\*“ ein, um Überwachungsprotokolle ohne obere Zeitgrenze zu laden.
   
   ![](media/service-connect-to-azure-sql-database-auditing/dbauditing_param.png)
5. Wählen Sie als Authentifizierungsmethode **Schlüssel** aus, geben Sie Ihren **Kontoschlüssel** \> **Anmelden** ein.
   
   ![](media/service-connect-to-azure-sql-database-auditing/pbi_sqlauditing3.png)
6. Nachdem die Daten von Power BI importiert wurden, werden im linken Navigationsbereich ein neues Dashboard, ein Bericht und ein Dataset angezeigt. Neue Elemente werden mit einem gelben Sternchen \* markiert.
   
   ![](media/service-connect-to-azure-sql-database-auditing/pbi_sqldbauditingnewdash.png)

**Was nun?**

* Versuchen Sie, am oberen Rand des Dashboards [im Q&A-Feld eine Frage zu stellen](consumer/end-user-q-and-a.md).
* [Ändern Sie die Kacheln](service-dashboard-edit-tile.md) im Dashboard.
* [Wählen Sie eine Kachel aus](consumer/end-user-tiles.md), um den zugrunde liegenden Bericht zu öffnen.
* Zwar ist Ihr Dataset auf tägliche Aktualisierung festgelegt, jedoch können Sie das Aktualisierungsintervall ändern oder über **Jetzt aktualisieren** nach Bedarf aktualisieren.

## <a name="next-steps"></a>Nächste Schritte
[Abrufen von Daten in Power BI](service-get-data.md)
[Was ist Power BI?](power-bi-overview.md)
