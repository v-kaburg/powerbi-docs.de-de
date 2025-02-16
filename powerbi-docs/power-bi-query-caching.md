---
title: Zwischenspeicherung von Abfragen in Power BI Premium
description: Zwischenspeicherung von Abfragen in Power BI Premium
author: maggiesMSFT
manager: kfile
ms.reviewer: bhmerc
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 04/25/2019
ms.author: maggies
LocalizationGroup: ''
ms.openlocfilehash: c981a3e2a05129a470c8d26675226bfb42c1bb68
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2019
ms.locfileid: "64769532"
---
# <a name="query-caching-in-power-bi-premium"></a>Zwischenspeicherung von Abfragen in Power BI Premium

Organisationen mit Power BI Premium können von der *Zwischenspeicherung von Abfragen* profitieren, um Berichte, die einem Dataset zugeordnet sind, zu beschleunigen. Mit der Zwischenspeicherung von Abfragen wird die Premium-Kapazität angewiesen, den lokalen Cachedienst zu verwenden, um Abfrageergebnisse zu verwalten und um zu vermeiden, dass die zugrunde liegende Datenquelle diese Ergebnisse berechnet.

> [!IMPORTANT]
> Die Zwischenspeicherung von Abfragen ist nur in Power BI Premium verfügbar. Sie kann nicht für LiveConnect-Datasets angewendet werden, die Azure Analysis Services oder SQL Server Analysis Services nutzen.

Zwischengespeicherte Abfrageergebnisse beziehen sich auf den Benutzer- und Datasetkontext und berücksichtigen Sicherheitsregeln. Derzeit führt der Dienst die Zwischenspeicherung von Abfragen nur für die erste Seite durch, auf die Sie gelangen. Abfragen werden also nicht zwischengespeichert, wenn Sie mit dem Bericht interagieren. Der Cache enthält persönliche Lesezeichen und permanente Filter. [Dashboardkacheln](service-dashboard-tiles.md), die von denselben Abfragen unterstützt werden, profitieren ebenfalls davon, sobald die Abfrage zwischengespeichert wurde. Die Leistung wird ebenfalls optimiert, wenn regelmäßig auf ein Dataset zugegriffen wird und dieses nicht oft aktualisiert werden muss. Die Zwischenspeicherung von Abfragen kann zudem die Last auf Ihrer Premium-Kapazität verringern, indem die Gesamtzahl der Abfragen reduziert wird.

Sie steuern das Zwischenspeicherungsverhalten für Abfragen für das Dataset im Power BI-Dienst über die Seite **Einstellungen**. Er hat zwei mögliche Einstellungen:

- **Aus:** Die Zwischenspeicherung von Abfragen darf für dieses Dataset nicht verwendet werden.

- **Ein:** Sie können die Zwischenspeicherung von Abfragen für dieses Dataset verwenden.

![Dialogfeld „Zwischenspeicherung von Abfragen“](media/power-bi-query-caching/power-bi-query-caching.png)

> [!NOTE]
> Wenn Sie die Einstellungen für die Zwischenspeicherung von **Ein** in **Aus** ändern, werden alle zuvor gespeicherten Abfrageergebnisse für das Dataset aus dem Kapazitätscache entfernt. Sie können die Zwischenspeicherung entweder explizit deaktivieren oder durch Wiederherstellen der Standardeinstellung für die Kapazität, die von einem Administrator auf **Aus** festgelegt wurde. Die Deaktivierung kann zu einer kurzen Verzögerung bei der nächsten Ausführung von Abfragen für Datasets führen, die von einem Bericht ausgeführt werden. Die Verzögerung wird ausgelöst, da Berichtabfragen bedarfsgesteuert ausgeführt werden und gespeicherte Ergebnisse nicht genutzt werden. Das erforderliche Dataset muss ggf. neu in den Arbeitsspeicher geladen werden, bevor Abfragen verarbeitet werden können.


