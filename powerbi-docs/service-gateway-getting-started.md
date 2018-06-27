---
title: Was sind Power BI-Gateways?
description: Erfahren Sie Grundlegendes zu Datengateways für Power BI.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-gateways
ms.topic: overview
ms.date: 04/18/2018
ms.author: mblythe
LocalizationGroup: Gateways
ms.openlocfilehash: 1da7591a490ae5bc6d132136691db05af7cffd81
ms.sourcegitcommit: 2a7bbb1fa24a49d2278a90cb0c4be543d7267bda
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2018
ms.locfileid: "34754907"
---
# <a name="what-are-power-bi-gateways"></a>Was sind Power BI-Gateways?

Ein Power BI-Gateway ist eine Softwareanwendung, die Sie in einem lokalen Netzwerk installieren. Es ermöglicht Zugriff auf Daten in diesem Netzwerk. Es handelt sich dabei um eine Art Torwächter, der Verbindungsanforderungen überwacht und diese nur zulässt, wenn die Benutzeranforderung bestimmte Kriterien erfüllt. So können Organisationen Datenbanken und andere Datenquellen in ihren eigenen Netzwerken behalten, diese lokalen Daten aber sicher in Power BI-Berichten und -Dashboards verwenden.

Ein Gateway kann für eine oder mehrere Datenquellen verwendet werden. Das folgende Diagramm zeigt eine grundlegende Ansicht, in der das Gateway Anforderungen aus der Cloud für drei lokale Computer verarbeitet. Dies wird weiter unten in diesem Artikel erläutert.

![Übersicht über Gateways](media/service-gateway-getting-started/gateway-overview.png)

## <a name="types-of-gateways"></a>Arten von Gateways

Power BI bietet zwei Gateways, je eines für verschiedene Szenarien:

* **Lokales Datengateway (persönlicher Modus)**: ermöglicht einem Benutzer die Verbindung mit Datenquellen und kann nicht für andere Benutzer freigegeben werden. Kann nur mit Power BI verwendet werden. Dieses Gateway eignet sich für Szenarien, in denen Sie die einzige Person sind, die Berichte erstellt, und Sie die Datenquellen nicht für andere Personen freigeben müssen.

* **Lokales Datengateway**: ermöglicht mehreren Benutzern, eine Verbindung mit mehreren lokalen Datenquellen herzustellen. Kann in einer einzigen Gatewayinstallation von Power BI, PowerApps, Flow, Azure Analysis Services und Azure Logic-Apps verwendet werden. Dieses Gateway eignet sich für komplexere Szenarien, in denen mehrere Benutzer auf mehrere Datenquellen zugreifen. 

## <a name="using-a-gateway"></a>Verwenden eines Gateways

Die Verwendung eines Gateways besteht aus vier Hauptschritten:

1. **Installieren des Gateways** auf einem lokalen Computer im geeigneten Modus
2. **Hinzufügen von Benutzern zum Gateway**, sodass diese auf lokale Datenquellen zugreifen können
3. **Herstellen einer Verbindung mit Datenquellen**, sodass diese in Berichten und Dashboards verwendet werden können
4. **Aktualisieren von lokalen Daten**, damit die Power BI-Berichte immer aktuell sind

Sie können ein eigenständiges Gateway installieren oder ein Gateway zu einem *Cluster* hinzufügen – Letzteres empfiehlt sich, um Hochverfügbarkeit sicherzustellen.

## <a name="how-gateways-work"></a>Funktionsweise von Gateways

Das Gateway, das Sie installieren, wird als Windows-Dienst **Lokales Datengateway** ausgeführt. Dieser lokale Dienst wird über Azure Service Bus beim Gatewayclouddienst registriert. Das folgende Diagramm zeigt den Datenfluss zwischen den lokalen Daten und den Clouddiensten, die das Gateway verwenden.

![Diagramm mit dem Datenfluss im Gateway](media/service-gateway-getting-started/gateway-how-it-works.png)

Abfragen und Datenfluss:

1. Der Clouddienst erstellt eine Abfrage mit den verschlüsselten Anmeldeinformationen für die lokale Datenquelle. Dann wird die Abfrage zur Verarbeitung an eine Warteschlange für das Gateway gesendet.
2. Der Gatewayclouddienst analysiert die Abfrage und übermittelt die Anforderung per Push an den Azure Service Bus.
3. Das lokale Datengateway fragt Azure Service Bus für ausstehende Anforderungen ab.
4. Das Gateway ruft die Abfrage ab, entschlüsselt die Anmeldeinformationen und stellt unter Verwendung dieser Anmeldeinformationen eine Verbindung mit den Datenquellen her.
5. Das Gateway sendet die Abfrage zur Ausführung an die Datenquelle.
6. Die Ergebnisse werden von der Datenquelle zurück an das Gateway und anschließend weiter an den Clouddienst und Ihren Server gesendet.

## <a name="next-steps"></a>Nächste Schritte
[Installieren des lokalen Datengateways](service-gateway-install.md)

Weitere Fragen? [Wenden Sie sich an die Power BI-Community](http://community.powerbi.com/)

