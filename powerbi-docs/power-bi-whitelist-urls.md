---
title: Power BI-URLs
description: Endpunkte sollten für Kunden, die Power BI verwenden, erreichbar sein.
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 08/13/2018
ms.openlocfilehash: 8e29fa0c9471bb865619102247f38776208c3d87
ms.sourcegitcommit: 8990028a348b642ba5c96f001fe3a4280f0166ee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2018
ms.locfileid: "40101129"
---
# <a name="power-bi-urls"></a>Power BI-URLs

**Der Power BI-Onlinedienst**, auch bekannt als SaaS-App von Power BI (Software-as-a-Service), erfordert eine Verbindung mit dem Internet. Die unten aufgeführten Endpunkte sollten für Kunden, die den Power BI-Onlinedienst verwenden, erreichbar sein.

Um den Online-Dienst in Power BI zu verwenden, müssen Sie Verbindungen zu den in den Tabellen unten als **erforderlich** und auf den verknüpften Websites als **erforderlich** markierten Endpunkten herstellen können. Wenn sich der Link zu einer externen Website auf einen bestimmten Abschnitt bezieht, müssen Sie in diesem Abschnitt nur die Endpunkte überprüfen.

Endpunkte, die als **optional** markiert sind, können **auf die Whitelist gesetzt werden**, wenn die Nutzung bestimmter Funktionen erforderlich ist.

Der Power BI-Onlinedienst setzt nur voraus, dass für die aufgeführten Endpunkte der TCP-Port 443 geöffnet wird.

Platzhalter (*) stellen alle Ebenen unterhalb der Stammdomäne dar, und N/V wird verwendet, wenn keine Informationen verfügbar sind. Die Spalte **Ziel(e)** ist eine Liste mit FQDN/Domänen und Links zu externen Websites, die weitere Informationen zu den Endpunkten enthalten.

>[!Important]
>Die Informationen in den Tabellen unten gelten nicht für die **US-amerikanische Government Cloud**, **die Cloud Deutschland** und **die Cloud China**.

## <a name="authentication"></a>Authentifizierung

Power BI ist auf die verschiedenen Endpunkte in den Office 365-Abschnitten zur Authentifizierung und Identität angewiesen. Zum Verwenden von Power BI müssen Sie eine Verbindung zu den Endpunkten herstellen können, die auf der unten verknüpften Website aufgeführt sind.

| Zeile | Zweck | Ziel(e) | Port(s) |
|-----|-------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------|--------------|---------------------------------------------|
| 1 | **Erforderlich**: Authentifizierung und Identität | Weitere Informationen finden Sie im Abschnitt [Office 365-Authentifizierung und -Identität](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_identity) der Website mit der Office 365-Whitelist. | N/V |

## <a name="general-site-usage"></a>Allgemeine Verwendung der Website

Für die allgemeine Verwendung von Power BI müssen Sie eine Verbindung zu den in der Tabelle aufgeführten Endpunkten und zu den Endpunkten, die auf den verknüpften Websites aufgeführt sind, herstellen können.

| Zeile | Zweck | Ziel(e) | Port(s) |
|-----|-------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------|--------------|---------------------------------------------|
| 1 | **Erforderlich**: Backend-APIs | *.analysis.windows.net | TCP 443 |
| 2 | **Erforderlich**: Office 365-Integration | Weitere Informationen finden Sie im Abschnitt [Office 365-Portal und gemeinsame Dienste](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_portal-identity) der Website mit der Office 365-Whitelist. | N/V |
| 3 | **Erforderlich**: Portal | app.powerbi.com | TCP 443 |
| 4 | **Erforderlich**: Diensttelemetrie | dc.services.visualstudio.com | TCP 443 |
| 5 | **Optional**: Informationsmeldungen | dynmsg.modpim.com | TCP 443 |
| 6 | **Optional**: NPS-Umfragen | nps.onyx.azure.net | TCP 443 |

## <a name="administration"></a>Verwaltung

Zum Ausführen administrativer Funktionen in Power BI müssen Sie eine Verbindung zu den Endpunkten auf den unten verknüpften Websites herstellen können.

| Zeile | Zweck | Ziel(e) | Port(s) |
|-----|-------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------|--------------|---------------------------------------------|
| 1 | **Erforderlich**: Zum Verwalten von Benutzern und Anzeigen von Überwachungsprotokollen | Weitere Informationen finden Sie im Abschnitt [Office 365-Portal und gemeinsame Dienste](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_portal-identity) der Website mit der Office 365-Whitelist. | N/V |

## <a name="get-data"></a>Daten abrufen

Zum Abrufen von Daten aus bestimmten Datenquellen wie OneDrive müssen Sie eine Verbindung zu den Endpunkten unten in der Tabelle herstellen können.

| Zeile | Zweck | Ziel(e) | Port(s) |
|-----|-------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------|--------------|---------------------------------------------|
| 1 | **Erforderlich**: AppSource (interne oder externe Apps in Power BI) | appsource.microsoft.com | TCP 443 |
| 2 | **Optional**: Importieren von Dateien aus OneDrive (privat) | Weitere Informationen finden Sie auf der Website [Required URLs and ports for OneDrive site (Erforderliche URLs und Ports für OneDrive)](https://support.office.com/en-ie/article/required-urls-and-ports-for-onedrive-ce15d2cc-52ef-42cd-b738-d9c6f9b03f3a). | N/V |
| 3 | **Optional**: Power BI in 60 Sekunden, Videotutorial | *.doubleclick.net </br> *.ggpht.com </br> *.google.com </br> *.googlevideo.com </br> *.youtube.com </br> *.ytimg.com </br> fonts.gstatic.com | TCP 443 |
| 4 | **Optional**: PubNub-Streamingdatenquellen | Weitere Informationen finden Sie in der [PubNub-Dokumentation](https://support.pubnub.com/support/solutions/articles/14000043522). | N/V |

## <a name="dashboard-and-report-integration"></a>Dashboard- und Berichtsintegration 

Zur Unterstützung von Dashboards und Berichten ist Power BI auf bestimmte Endpunkte angewiesen. Sie müssen eine Verbindung zu den Endpunkten in der Tabelle und den unten verknüpften Websites herstellen können.

| Zeile | Zweck | Ziel(e) | Port(s) |
|-----|-------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------|--------------|---------------------------------------------|
| 1 | **Erforderlich**: Excel-Integration | Weitere Informationen finden Sie im Abschnitt [Office Online](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_officeonline) der Website mit der Office 365-Whitelist. | N/V |

## <a name="custom-visuals"></a>Benutzerdefinierte Visuals

Power BI ist auf bestimmte Endpunkte angewiesen, um benutzerdefinierte Visuals anzeigen und darauf zugreifen zu können. Sie müssen eine Verbindung zu den Endpunkten in der Tabelle und den unten verknüpften Websites herstellen können.

| Zeile | Zweck | Ziel(e) | Port(s) |
|-----|-------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------|--------------|---------------------------------------------|
| 1 | **Erforderlich**: Importieren eines benutzerdefinierten Visuals über die Marketplace-Schnittstelle und aus einer Datei | *.microsoft.com </br> *.bing.com </br> *.msecnd.net </br> *.osi.office.net </br> *.azureedge.net </br> ajax.aspnetcdn.com </br> nexus.ensighten.com </br> store.office.com | TCP 443 |
| 2 | **Optional**: Bing Karten | bing.com </br> platform.bing.com </br> *.dynamic.tiles.virtualearth.net </br> *.virtualearth.net | TCP 443 |
| 3 | **Optional**: PowerApps | Weitere Informationen finden Sie im Abschnitt [Erforderliche Dienste](https://docs.microsoft.com/powerapps/maker/canvas-apps/limits-and-config#required-services) auf der Website mit den PowerApps-Systemanforderungen. | N/V |
| 4 | **Optional**: Visio | Weitere Informationen finden Sie im Abschnitt [Office Online](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_officeonline) der Website mit der Office 365-Whitelist. | N/V |