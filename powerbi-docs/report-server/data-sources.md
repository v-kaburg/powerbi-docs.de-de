---
title: "Datenquellen für Power BI-Berichte in Power BI-Berichtsserver"
description: "Power BI-Berichte können mit verschiedenen Datenquellen verbunden sein. Je nach Verwendung der Daten sind verschiedene Datenquellen verfügbar."
services: powerbi
documentationcenter: 
author: markingmyname
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
ms.date: 11/01/2017
ms.author: maghan
ms.openlocfilehash: caa45aab2c31974abb041a82eb2216ebee2eb148
ms.sourcegitcommit: 6e693f9caf98385a2c45890cd0fbf2403f0dbb8a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2018
---
# <a name="power-bi-report-data-sources-in-power-bi-report-server"></a>Datenquellen für Power BI-Berichte in Power BI-Berichtsserver
Power BI-Berichte können mit verschiedenen Datenquellen verbunden sein. Je nach Verwendung der Daten sind verschiedene Datenquellen verfügbar. Daten können importiert werden, oder Daten können direkt mit DirectQuery oder über eine Liveverbindung mit SQL Server Analysis Services abgefragt werden.

Diese Datenquellen sind spezifisch für Power BI-Berichte, die in Power BI-Berichtsserver verwendet werden. Weitere Informationen zu Datenquellen, die für paginierte Berichte unterstützt werden, finden Sie unter [Von Reporting Services unterstützte Datenquellen](https://docs.microsoft.com/sql/reporting-services/report-data/data-sources-supported-by-reporting-services-ssrs).

> [!IMPORTANT]
> Alle Datenquellen in einem Power BI Desktop-Bericht müssen unterstützt werden, damit geplante Aktualisierungen konfiguriert werden können.
> 
> 

## <a name="list-of-supported-data-sources"></a>Liste der unterstützten Datenquellen
Andere Datenquellen können funktionieren, selbst wenn sie nicht in der Liste der unterstützten Datenquellen aufgeführt werden.

| **Datenquelle** | **Zwischengespeicherte Daten** | **Geplante Aktualisierung** | **Live/DirectQuery** |
| --- | --- | --- | --- |
| SQL Server-Datenbank |Ja |Ja |Ja |
| SQL Server Analysis Services |Ja |Ja |Ja |
| Azure SQL-Datenbank |Ja |Ja |Ja |
| Azure SQL Data Warehouse |Ja |Ja |Ja |
| Excel |Ja |Ja |Nein |
| Access-Datenbank |Ja |Ja |Nein |
| Active Directory |Ja |Ja |Nein |
| Amazon Redshift |Ja |Nein |Nein |
| Azure-BLOB-Speicher |Ja |Ja |Nein |
| Azure Data Lake Store |Ja |Nein |Nein |
| Azure HDInsight (HDFS) |Ja |Ja |Nein |
| Azure HDInsight (Spark) |Ja |Ja |Nein |
| Azure-Tabellenspeicher |Ja |Ja |Nein |
| Dynamics 365 (online) |Ja |Nein |Nein |
| Facebook |Ja |Nein |Nein |
| Ordner |Ja |Ja |Nein |
| Google Analytics |Ja |Nein |Nein |
| Hadoop-Datei (HDFS) |Ja |Nein |Nein |
| IBM DB2-Datenbank |Ja |Ja |Nein |
| Impala |Ja |Nein |Nein |
| JSON |Ja |Ja |Nein |
| Microsoft Exchange |Ja |Nein |Nein |
| Microsoft Exchange Online |Ja |Nein |Nein |
| MySQL-Datenbank |Ja |Ja |Nein |
| OData-Feed |Ja |Ja |Nein |
| ODBC |Ja |Ja |Nein |
| OLE DB |Ja |Ja |Nein |
| Oracle-Datenbank |Ja |Ja |Ja |
| PostgreSQL-Datenbank |Ja |Ja |Nein |
| Power BI-Dienst |Nein |Nein |Nein |
| R-Skript |Ja |Nein |Nein |
| Salesforce-Objekte |Ja |Nein |Nein |
| Salesforce-Berichte |Ja |Nein |Nein |
| SAP Business Warehouse-Server |Ja |Ja |Ja |
| SAP HANA-Datenbank |Ja |Ja |Ja |
| SharePoint-Ordner (lokal) |Ja |Ja |Nein |
| SharePoint-Liste (lokal) |Ja |Ja |Nein |
| SharePoint-Online-Liste |Ja |Nein |Nein |
| Snowflake |Ja |Nein |Nein |
| Sybase-Datenbank |Ja |Ja |Nein |
| Teradata-Datenbank |Ja |Ja |Ja |
| Text/CSV |Ja |Ja |Nein |
| Web |Ja |Ja |Nein |
| XML |Ja |Ja |Nein |
| appFigures (Beta) |Ja |Nein |Nein |
| Azure Analysis Services-Datenbank (Beta) |Ja |Nein |Nein |
| Azure Cosmos DB (Beta) |Ja |Nein |Nein |
| Azure HDInsight Spark (Beta) |Ja |Nein |Nein |
| Common Data Service (Beta) |Ja |Nein |Nein |
| comScore Digital Analytix (Beta) |Ja |Nein |Nein |
| Dynamics 365 für Customer Insights (Beta) |Ja |Nein |Nein |
| Dynamics 365 for Financials (Beta) |Ja |Nein |Nein |
| GitHub (Beta) |Ja |Nein |Nein |
| BigQuery von Google (Beta) |Ja |Nein |Nein |
| IBM Informix-Datenbank (Beta) |Ja |Nein |Nein |
| IBM Netezza (Beta) |Ja |Nein |Nein |
| Kusto (Beta) |Ja |Nein |Nein |
| MailChimp (Beta) |Ja |Nein |Nein |
| Microsoft Azure Consumption Insights (Beta) |Ja |Nein |Nein |
| Mixpanel (Beta) |Ja |Nein |Nein |
| Planview Enterprise (Beta) |Ja |Nein |Nein |
| Projectplace (Beta) |Ja |Nein |Nein |
| QuickBooks Online (Beta) |Ja |Nein |Nein |
| Smartsheet |Ja |Nein |Nein |
| Spark (Beta) |Ja |Nein |Nein |
| SparkPost (Beta) |Ja |Nein |Nein |
| SQL Sentry (Beta) |Ja |Nein |Nein |
| Stripe (Beta) |Ja |Nein |Nein |
| SweetIQ (Beta) |Ja |Nein |Nein |
| Troux (Beta) |Ja |Nein |Nein |
| Twilio (Beta) |Ja |Nein |Nein |
| tyGraph (Beta) |Ja |Nein |Nein |
| Vertica (Beta) |Ja |Nein |Nein |
| Visual Studio Team Services (Beta) |Ja |Nein |Nein |
| Webtrends (Beta) |Ja |Nein |Nein |
| Zendesk (Beta) |Ja |Nein |Nein |

> [!IMPORTANT]
> Die in der Datenquelle konfigurierte Sicherheit auf Zeilenebene sollte für bestimmte DirectQuery-Verbindungen (SQL Server, Azure SQL-Datenbank, Oracle und Teradata) und Liveverbindungen funktionieren, vorausgesetzt, Kerberos ist in der Umgebung ordnungsgemäß konfiguriert.
> 
> 

## <a name="next-steps"></a>Nächste Schritte
Nach erfolgter Auswahl der Datenquelle [erstellen Sie einen Bericht](quickstart-create-powerbi-report.md) anhand der Daten aus der betreffenden Datenquelle.

Weitere Fragen? [Stellen Sie Ihre Frage in der Power BI-Community.](https://community.powerbi.com/)

