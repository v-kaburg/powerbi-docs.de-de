---
title: Datenquellen in Power BI Desktop
description: Datenquellen in Power BI Desktop
services: powerbi
documentationcenter: 
author: davidiseminger
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: complete
qualitydate: 04/29/2016
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 01/24/2018
ms.author: davidi
ms.openlocfilehash: 42acbc0823f798ee0c0d762fc124c0f371494bd9
ms.sourcegitcommit: 7249ff35c73adc2d25f2e12bc0147afa1f31c232
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/25/2018
---
# <a name="data-sources-in-power-bi-desktop"></a>Datenquellen in Power BI Desktop
Mit Power BI Desktop können Sie Verbindungen mit Daten aus vielen verschiedenen Quellen herstellen. Eine vollständige Liste der verfügbaren Datenquellen wird am unteren Rand dieser Seite angezeigt.

Wählen Sie zum Herstellen einer Verbindung mit Daten im Menüband **Start** den Eintrag **Daten abrufen** aus. Wenn Sie den Pfeil nach unten oder den Text **Daten abrufen** auf der Schaltfläche auswählen, wird das Datentypmenü **Am häufigsten verwendet** angezeigt, das in der folgenden Abbildung veranschaulicht wird.

![](media/desktop-data-sources/data-sources_1.png)

Wenn Sie die Option **Mehr...** im Menü **Am häufigsten verwendet** auswählen, wird das Fenster **Daten abrufen** angezeigt. Sie können das Fenster **Daten abrufen** auch durch direktes Auswählen der **Symbolschaltfläche** **Daten abrufen** öffnen (und das Menü **Am häufigsten verwendet** umgehen).

![](media/desktop-data-sources/data-sources_2.png)

> [!NOTE]
> Das Power BI-Team erweitert laufend die Datenquellen, die für **Power BI Desktop** und den **Power BI-Dienst** verfügbar sind. Daher finden Sie häufig Vorabversionen von noch nicht in der Endversion vorliegenden Datenquellen, die als *Beta* oder *Vorschau* gekennzeichnet sind. Für alle als *Beta* oder *Vorschau* markierten Datenquellen stehen nur eingeschränkter Support und weniger Funktionen zur Verfügung, und sie sollten nicht in Produktionsumgebungen verwendet werden.
> 
> 

## <a name="data-sources"></a>Datenquellen
Datentypen werden in die folgenden Kategorien unterteilt:

* Alles
* Datei
* Datenbank
* Azure
* Online-Dienste
* Sonstige

Die Kategorie **Alles** umfasst alle Datenverbindungstypen aus allen Kategorien.

Die Kategorie **Datei** bietet die folgenden Datenverbindungen:

* Excel
* Text/CSV
* XML
* JSON
* Ordner
* SharePoint-Ordner

Die folgende Abbildung zeigt das Fenster **Daten abrufen** für **Datei**.

![](media/desktop-data-sources/data-sources_3.png)

> [!NOTE]
> In früheren Versionen von Power BI Desktop handelte es sich bei **CSV** und **Text** um separate Datenverbindungstypen. Diese Datenconnectors wurden in **Text/CSV** zusammengefasst.
> 
> 

Die Kategorie **Datenbank** bietet die folgenden Datenverbindungen:

* SQL Server-Datenbank
* Access-Datenbank
* SQL Server Analysis Services-Datenbank
* Oracle-Datenbank
* IBM DB2-Datenbank
* IBM Informix-Datenbank (Beta)
* IBM Netezza (Beta)
* MySQL-Datenbank
* PostgreSQL-Datenbank
* Sybase-Datenbank
* Teradata-Datenbank
* SAP HANA-Datenbank
* SAP Business Warehouse-Server
* Amazon Redshift
* Impala
* BigQuery von Google (Beta)
* Snowflake

> [!NOTE]
> Sie müssen einige Datenbankconnectors aktivieren, indem Sie **Datei > Optionen und Einstellungen > Optionen** und dann **Vorschaufeatures** auswählen und den Connector aktivieren. Wenn einige der oben genannten Connectors nicht angezeigt werden und Sie diese verwenden möchten, überprüfen Sie die Einstellungen von **Vorschaufeatures**. Außerdem stehen für alle als *Beta* oder *Vorschau* markierten Datenquellen nur eingeschränkter Support und weniger Funktionen zur Verfügung, und sie sollten nicht in Produktionsumgebungen verwendet werden.
> 
> 

Die folgende Abbildung zeigt das Fenster **Daten abrufen** für **Datenbank**.

![](media/desktop-data-sources/data-sources_4.png)

Die Kategorie **Azure** bietet die folgenden Datenverbindungen:

* Azure SQL-Datenbank
* Azure SQL Data Warehouse
* Azure Analysis Services-Datenbank (Beta)
* Azure-BLOB-Speicher
* Azure-Tabellenspeicher
* Azure Cosmos DB (Beta)
* Azure Data Lake Store
* Azure HDInsight (HDFS)
* Azure HDInsight Spark (Beta)

Die folgende Abbildung zeigt das Fenster **Daten abrufen** für **Azure**.

![](media/desktop-data-sources/data-sources_5.png)

Die Kategorie **Online Services** bietet die folgenden Datenverbindungen:

* Power BI-Dienst
* SharePoint-Online-Liste
* Microsoft Exchange Online
* Dynamics 365 (online)
* Dynamics 365 for Financials (Beta)
* Common Data Service (Beta)
* Microsoft Azure Consumption Insights (Beta)
* Visual Studio Team Services (Beta)
* Salesforce-Objekte
* Salesforce-Berichte
* Google Analytics
* appFigures (Beta)
* comScore Digital Analytix (Beta)
* Dynamics 365 für Customer Insights (Beta)
* Facebook
* GitHub (Beta)
* Kusto (Beta)
* MailChimp (Beta)
* Mixpanel (Beta)
* Planview Enterprise (Beta)
* Projectplace (Beta)
* QuickBooks Online (Beta)
* Smartsheet
* SparkPost (Beta)
* SQL Sentry (Beta)
* Stripe (Beta)
* SweetIQ (Beta)
* Troux (Beta)
* Twilio (Beta)
* tyGraph (Beta)
* Webtrends (Beta)
* Zendesk (Beta)

Die folgende Abbildung zeigt das Fenster **Daten abrufen** für **Onlinedienste** an.

![](media/desktop-data-sources/data-sources_6b.png)

Die Kategorie **Sonstige** bietet die folgenden Datenverbindungen:

* Vertica (Beta)
* Web
* SharePoint-Liste
* OData-Feed
* Active Directory
* Microsoft Exchange
* Hadoop-Datei (HDFS)
* Spark (Beta)
* R-Skript
* ODBC
* OLE DB
* Leere Abfrage

Die folgende Abbildung zeigt das Fenster **Daten abrufen** für **Sonstige**.

![](media/desktop-data-sources/data-sources_7a.png)

> [!NOTE]
> Zurzeit ist es nicht möglich, eine Verbindung mit benutzerdefinierten Datenquellen herzustellen, die mit Azure Active Directory gesichert wurden.
> 
> 

## <a name="connecting-to-a-data-source"></a>Herstellen der Verbindung mit einer Datenquelle
Wenn Sie die Verbindung mit einer Datenquelle herstellen möchten, wählen Sie die Datenquelle im Fenster **Daten abrufen** und dann **Verbinden**aus. In der folgenden Abbildung ist **Web** aus der Datenverbindungskategorie **Sonstige** ausgewählt.

![](media/desktop-data-sources/data-sources_7b.png)

Es wird ein für den Typ der Datenverbindung spezifisches Verbindungsfenster angezeigt. Wenn Anmeldeinformationen erforderlich sind, werden Sie aufgefordert, diese bereitzustellen. Die folgende Abbildung zeigt eine URL, die eingegeben wird, um die Verbindung mit einer Webdatenquelle herzustellen.

![](media/desktop-data-sources/datasources_fromwebbox.png)

Wählen Sie bei der Eingabe der URL oder Ressourcenverbindungsinformationen **OK**aus. Power BI Desktop stellt die Verbindung mit der Datenquelle her und zeigt die verfügbaren Datenquellen im **Navigator**an.

![](media/desktop-data-sources/datasources_fromnavigatordialog.png)

Sie können die Daten entweder durch Auswählen der Schaltfläche **Laden** laden, die sich am unteren Rand des Bereichs **Navigator** befindet, oder Sie bearbeiten die Abfrage vor dem Laden der Daten, indem Sie die Schaltfläche **Bearbeiten** auswählen.

Das ist alles, was zum Herstellen der Verbindung mit Datenquellen im Power BI-Designer erforderlich ist. Sie können eine Verbindung mit Daten aus der wachsenden Liste von Datenquellen herstellen, die wir kontinuierlich erweitern.

## <a name="next-steps"></a>Nächste Schritte
Mit Power BI Desktop können Sie viele Aufgaben ausführen. Weitere Informationen zu den Funktionen und Möglichkeiten finden Sie in folgenden Ressourcen:

* [Erste Schritte mit Power BI Desktop](desktop-getting-started.md)
* [Übersicht zu Abfragen mit Power BI Desktop](desktop-query-overview.md)
* [Datentypen in Power BI Desktop](desktop-data-types.md)
* [Strukturieren und Kombinieren von Daten mit Power BI Desktop](desktop-shape-and-combine-data.md)
* [Allgemeine Abfrageaufgaben in Power BI Desktop](desktop-common-query-tasks.md)    

