---
title: Azure SQL-Datenbank mit DirectQuery
description: Azure SQL-Datenbank mit DirectQuery
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.custom: ''
ms.date: 06/20/2018
LocalizationGroup: Data from databases
ms.openlocfilehash: 5365c076b75d0989df8db15c1dc16f4e11bc3f09
ms.sourcegitcommit: c539726c9c180e899a8a34443e3fda2b9848beb2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/31/2019
ms.locfileid: "66448401"
---
# <a name="azure-sql-database-with-directquery"></a>Azure SQL-Datenbank mit DirectQuery

Erfahren Sie, wie Sie eine direkte Verbindung mit der Azure SQL-Datenbank herstellen und Berichte erstellen, in denen Livedaten verwendet werden. Sie können Ihre Daten in der Datenquelle und nicht in Power BI speichern.

Durch DirectQuery werden Abfragen zurück zur Azure SQL-Datenbank gesendet, während Sie die Daten in der Berichtsansicht untersuchen. Diese Variante wird für Benutzer empfohlen, die mit den Datenbanken und den Entitäten vertraut sind, mit denen die Verbindung hergestellt wird.

**Hinweise:**

* Geben Sie beim Herstellen der Verbindung den vollqualifizierten Servernamen an (weitere Informationen folgen später im Abschnitt)
* Stellen Sie sicher, dass die Firewallregeln für die Datenbank so konfiguriert sind, dass sie den „[Zugriff auf Azure-Dienste erlauben](https://msdn.microsoft.com/library/azure/ee621782.aspx)“.
* Durch jede Aktion, z. B. beim Auswählen einer Spalte oder dem Hinzufügen eines Filters, wird eine Abfrage zurück an die Datenbank gesendet.
* Die Kacheln werden stündlich aktualisiert (die Aktualisierung muss nicht geplant werden). Dies kann in den erweiterten Einstellungen angepasst werden, wenn Sie eine Verbindung herstellen.
* Q&A steht für DirectQuery-Datasets nicht zur Verfügung.
* Schemaänderungen werden nicht automatisch übernommen.

Diese Einschränkungen und Hinweise können sich ändern, da wir die Benutzeroberfläche fortlaufend optimieren. Die Schritte zum Herstellen der Verbindung werden nachfolgend beschrieben.

> [!Important]
> Die Konnektivität mit Azure SQL-Datenbank wurde verbessert.  Verwenden Sie Power BI Desktop für optimale Ergebnisse beim Herstellen einer Verbindung mit Ihrer Azure SQL-Datenbank-Datenquelle.  Sobald Sie Ihr Modell und Ihren Bericht erstellt haben, können Sie diese im Power BI-Dienst veröffentlichen.  Der direkte Connector für Azure SQL-Datenbank im Power BI-Dienst ist mittlerweile veraltet.

## <a name="power-bi-desktop-and-directquery"></a>Power BI Desktop und DirectQuery

Zum Herstellen einer Verbindung mit der Azure SQL-Datenbank über DirectQuery müssen Sie Power BI Desktop verwenden. Dieser Ansatz bietet zusätzliche Flexibilität und Funktionalität. Mit Power BI Desktop erstellte Berichte können dann im Power BI-Dienst veröffentlicht werden. [Hier](desktop-use-directquery.md) erhalten Sie weitere Informationen zum Herstellen einer Verbindung mit der Azure SQL-Datenbank über DirectQuery in Power BI Desktop.

## <a name="finding-parameter-values"></a>Suchen von Parameterwerten

Ihren vollqualifizierten Servernamen und den Datenbanknamen finden Sie im Azure-Portal.

![Neues Azure Port-Update](media/service-azure-sql-database-with-direct-connect/azureportnew_update.png)

![Azure Portal-Update](media/service-azure-sql-database-with-direct-connect/azureportal_update.png)

[!INCLUDE [direct-query-sso](includes/direct-query-sso.md)]

## <a name="next-steps"></a>Nächste Schritte

* [Verwenden von DirectQuery in Power BI Desktop](desktop-use-directquery.md)  
* [Was ist Power BI?](power-bi-overview.md)  
* [Abrufen von Daten in Power BI](service-get-data.md)  

Weitere Fragen? [Wenden Sie sich an die Power BI-Community](http://community.powerbi.com/)
