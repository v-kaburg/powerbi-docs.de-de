---
title: Von DirectQuery in Power BI unterstützte Datenquellen
description: Rufen Sie eine Liste der Datenquellen ab, die DirectQuery verwenden können.
author: davidiseminger
ms.author: davidi
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 04/10/2019
LocalizationGroup: Connect to data
ms.openlocfilehash: 3bb7de9685a1e0fc9fa423328ad9e1e5faa53603
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2019
ms.locfileid: "61305453"
---
# <a name="data-sources-supported-by-directquery-in-power-bi"></a>Von DirectQuery in Power BI unterstützte Datenquellen

**Power BI Desktop** und der **Power BI-Dienst** verfügen über viele Datenquellen, mit denen Sie Verbindungen herstellen und auf deren Daten Sie zugreifen können. Dieser Artikel beschreibt, welche Datenquellen für Power BI die als **DirectQuery** bezeichnete Verbindungsmethode unterstützen. Weitere Informationen zu DirectQuery finden Sie unter [**DirectQuery in Power BI**](desktop-directquery-about.md).

Die folgenden Datenquellen unterstützen DirectQuery in Power BI:

* Amazon Redshift
* AtScale (Beta)
* Azure HDInsight Spark
* Azure SQL-Datenbank
* Azure SQL Data Warehouse
* Google BigQuery
* HDInsight Interactive Query
* IBM DB2-Datenbank
* IBM Netezza
* Impala (Version 2.x)
* Oracle-Datenbank (Version 12 und höher)
* Oracle Essbase
* SAP Business Warehouse-Anwendungsserver
* SAP Business Warehouse-Nachrichtenserver
* SAP HANA
* Snowflake
* Spark (Version 0.9 und höher)
* SQL Server
* Teradata-Datenbank
* Vertica

Datenquellen, auf deren Namen **(Beta)** oder **(Vorschau)** folgt, unterliegen noch Änderungen und werden für den Einsatz in Produktionsumgebungen nicht unterstützt. Möglicherweise werden sie auch nach dem Veröffentlichen eines Berichts im **Power BI-Dienst** nicht unterstützt, was bedeutet, dass das Öffnen eines veröffentlichten Berichts oder das Untersuchen des Datasets zu einem Fehler führen kann.

Der einzige Unterschied zwischen als **(Beta)** und als **(Vorschau)** gekennzeichneten Datenquellen besteht darin, dass **(Vorschau)** -Datenquellen als Vorschaufunktion aktiviert werden müssen, um zur Verwendung verfügbar zu sein. Um einen **(Vorschau)** -Datenconnector zu aktivieren, wechseln Sie in **Power BI Desktop** zu **Datei > Optionen und Einstellungen > Optionen** und dann zu **Vorschaufeatures**.

> [!NOTE]
> DirectQuery-Abfragen an SQL Server erfordern die Authentifizierung mit aktuellen Anmeldeinformationen für die Windows-Authentifizierung oder Datenbankanmeldeinformationen, um Zugang herzustellen. Alternative Anmeldeinformationen werden nicht unterstützt.
>

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
| Spark (Beta) (Version 0.9 und höher) |Ja |
| Azure HDInsight Spark (Beta) |Nein |
| IBM Netezza |Ja |
| SAP Business Warehouse-Anwendungsserver |Ja |
| SAP Business Warehouse-Nachrichtenserver |Im **Power BI-Dienst** noch nicht unterstützt |
| Google BigQuery |Nein |


## <a name="next-steps"></a>Nächste Schritte
Weitere Informationen zu DirectQuery finden Sie in den folgenden Ressourcen:

* [DirectQuery in Power BI](desktop-directquery-about.md)
* [DirectQuery und SAP HANA](desktop-directquery-sap-hana.md)
* [DirectQuery und SAP BW](desktop-directquery-sap-bw.md)
* [Lokales Datengateway](service-gateway-onprem.md)

