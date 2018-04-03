---
title: Von DirectQuery in Power BI unterstützte Datenquellen
description: Rufen Sie eine Liste der Datenquellen ab, die DirectQuery verwenden können.
services: powerbi
documentationcenter: ''
author: davidiseminger
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 03/09/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: fcd8e4705fe5ee3a3a567c0e7a44a5a4d1a73e76
ms.sourcegitcommit: e31fc1f6e4af427f8b480c8dbc537c3617c9b2c0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/22/2018
---
# <a name="data-sources-supported-by-directquery-in-power-bi"></a>Von DirectQuery in Power BI unterstützte Datenquellen
**Power BI Desktop** und der **Power BI-Dienst** verfügen über viele Datenquellen, mit denen Sie Verbindungen herstellen und auf deren Daten Sie zugreifen können. Dieser Artikel beschreibt, welche Datenquellen für Power BI die als **DirectQuery** bezeichnete Verbindungsmethode unterstützen. Weitere Informationen zu DirectQuery finden Sie unter [**DirectQuery in Power BI**](desktop-directquery-about.md).

Die folgenden Datenquellen unterstützen DirectQuery in Power BI:

* Amazon Redshift
* Azure HDInsight Spark (Beta)
* Azure SQL-Datenbank
* Azure SQL Data Warehouse
* BigQuery von Google (Beta)
* IBM Netezza (Beta)
* Impala (Version 2.x)
* Oracle-Datenbank (Version 12 und höher)
* SAP Business Warehouse-Anwendungsserver
* SAP Business Warehouse-Nachrichtenserver (Beta)
* SAP HANA
* Snowflake
* Spark (Beta) (Version 0.9 und höher)
* SQL Server
* Teradata-Datenbank
* Vertica (Beta)

Datenquellen, auf deren Namen **(Beta)** oder **(Vorschau)** folgt, unterliegen noch Änderungen und werden für den Einsatz in Produktionsumgebungen nicht unterstützt. Möglicherweise werden sie auch nach dem Veröffentlichen eines Berichts im **Power BI-Dienst** nicht unterstützt, was bedeutet, dass das Öffnen eines veröffentlichten Berichts oder das Untersuchen des Datasets zu einem Fehler führen kann.

Der einzige Unterschied zwischen als **(Beta)** und als **(Vorschau)** gekennzeichneten Datenquellen besteht darin, dass **(Vorschau)**-Datenquellen als Vorschaufunktion aktiviert werden müssen, um zur Verwendung verfügbar zu sein. Um einen **(Vorschau)**-Datenconnector zu aktivieren, wechseln Sie in **Power BI Desktop** zu **Datei > Optionen und Einstellungen > Optionen** und dann zu **Vorschaufeatures**.

## <a name="on-premises-gateway-requirements"></a>Anforderungen an lokale Gateways
Die folgende Tabelle gibt an, ob für das Herstellen von Verbindungen mit der angegebenen Datenquelle nach dem Veröffentlichen eines Berichts im **Power BI-Dienst** ein **Lokales Datengateway** erforderlich ist.

| Quelle | Gateway erforderlich? |
| --- | --- |
| SQL Server |Ja |
| Azure SQL-Datenbank |Nein |
| Azure SQL Data Warehouse |Nein |
| SAP HANA |Ja |
| Oracle-Datenbank |Ja |
| Teradata-Datenbank |Ja |
| Amazon Redshift |Nein |
| Impala (Version 2.x) |Ja |
| Snowflake |Ja |
| Spark (Beta) (Version 0.9 und höher) |Im **Power BI-Dienst** noch nicht unterstützt |
| Azure HDInsight Spark (Beta) |Nein |
| IBM Netezza |Ja |
| SAP Business Warehouse-Anwendungsserver |Ja |
| SAP Business Warehouse-Nachrichtenserver |Im **Power BI-Dienst** noch nicht unterstützt |
| BigQuery von Google |Nein |


## <a name="next-steps"></a>Nächste Schritte
Weitere Informationen zu DirectQuery finden Sie in den folgenden Ressourcen:

* [DirectQuery in Power BI](desktop-directquery-about.md)
* [DirectQuery und SAP HANA](desktop-directquery-sap-hana.md)
* [DirectQuery und SAP BW](desktop-directquery-sap-bw.md)
* [Lokales Datengateway](service-gateway-onprem.md)

