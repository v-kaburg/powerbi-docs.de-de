---
title: Vergleich zwischen Power BI-Berichtsserver und Power BI-Dienst
description: In diesem Artikel werden die Features des Power BI-Berichtsservers und des Power BI-Diensts miteinander verglichen.
services: powerbi
keywords: ''
author: maggiesMSFT
ms.author: maggies
ms.component: powerbi-report-server
ms.date: 05/07/2018
ms.topic: overview
ms.service: powerbi
manager: kfile
ms.custom: mvc
ms.openlocfilehash: d0a3e2870edc8b18cb982c33582c7578aa67f2c3
ms.sourcegitcommit: 493f160d04ed411ff4741c599adc63ba1f65230f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33813896"
---
# <a name="comparing-power-bi-report-server-and-the-power-bi-service"></a>Vergleich zwischen Power BI-Berichtsserver und Power BI-Dienst

Der Power BI-Berichtsserver und der Power BI-Dienst weisen viele Ähnlichkeiten, aber auch einige wesentliche Unterschiede auf. In der folgenden Tabelle werden diese Ähnlichkeiten und Unterschiede erläutert.

| Features | Power BI-Berichtsserver | Power BI-Dienst | Hinweise
|---------|---------|---------|---------|
| Bereitstellung | Lokal oder in einer gehosteten Cloud | Cloud | Der Power BI-Berichtsserver kann auf Azure-VMs (gehostete Cloud) bereitgestellt werden, wenn die Lizenzierung über Power BI Premium erfolgt.
| Quelldaten | Cloud und/oder lokal | Cloud und/oder lokal |  
| Lizenz | Power BI Premium oder SQL Server EE mit SA | Power BI Pro und/oder Power BI Premium |  
| Lebenszyklus | Moderne Lebenszyklusrichtlinie | Vollständig verwalteter Dienst |  
| Releasezyklus | Einmal alle 4 Monate | Einmal pro Monat | Die neuesten Features und Fixes werden zuerst im Power BI-Dienst bereitgestellt. Die meisten wichtigen Funktionen werden in den nachfolgenden Releases auch im Power BI-Berichtsserver bereitgestellt. Einige Features bleiben dem Power BI-Dienst vorbehalten.
| Erstellen von Power BI-Berichten in Power BI Desktop | Ja | Ja |  
| Erstellen von Power BI-Berichten im Browser | Nein | Ja |  
| Gateway erforderlich | Nein | Ja für lokale Datenquellen |  
| Echtzeitstreaming | Nein | Ja | [Echtzeitstreaming in Power BI](../service-real-time-streaming.md)
| Dashboards | Nein | Ja | [Dashboards im Power BI-Dienst](../service-dashboards.md) 
| Verteilen von Berichtsgruppen mithilfe von Apps | Nein | Ja | [Erstellen und Veröffentlichen von Apps mit Dashboards und Berichten](../service-create-distribute-apps.md) 
| Inhaltspakete | Nein | Ja | [Einführung in organisationsbezogene Inhaltspakete in Power BI](../service-organizational-content-pack-introduction.md) 
| Herstellen einer Verbindung mit Diensten wie Salesforce | Nein | Ja | [Herstellung einer Verbindung mit den verwendeten Diensten](../service-connect-to-services.md) über den Power BI-Dienst
| Q&A | Nein | Ja | [Q&A im Power BI-Dienst und in Power BI Desktop](../power-bi-q-and-a.md) 
| Schnelle Einblicke | Nein | Ja | [Automatisches Erstellen von Einblicken in Daten mit Power BI](../service-insights.md) 
| In Excel analysieren | Nein | Ja | [In Excel analysieren](../service-analyze-in-excel.md) 
| Paginierte Berichte | Ja | Nein | Paginierte Berichte sind im Power BI-Dienst nicht verfügbar, aber Sie können [paginierte Berichtelemente an Power BI-Dashboards anheften](https://docs.microsoft.com/sql/reporting-services/pin-reporting-services-items-to-power-bi-dashboards).
| Mobile Power BI-Apps | Ja | Ja | [Übersicht über mobile Power BI-Apps](../mobile-apps-for-mobile-devices.md) 
| ArcGIS-Karten | Nein | Ja | [ArcGIS Maps von ESRI im Power BI-Dienst und in Power BI Desktop](../power-bi-visualization-arcgis.md)
| E-Mail-Abonnements für Power BI-Berichte | Nein | Ja | [Abonnieren eines Berichts oder Dashboards](../service-report-subscribe.md) im Power BI-Dienst 
| E-Mail-Abonnements für paginierte Berichte | Ja | Nein | [E-Mail-Übermittlung in Reporting Services](https://docs.microsoft.com/sql/reporting-services/subscriptions/e-mail-delivery-in-reporting-services)  
| Datenwarnungen | Nein | Ja | [Datenwarnungen](../service-set-data-alerts.md) im Power BI-Dienst
| Sicherheit auf Zeilenebene | Nur über die Datenquelle im DirectQuery-Modus | Verfügbar im DirectQuery-Modus (Datenquelle) und im Importmodus | [Sicherheit auf Zeilenebene](../service-admin-rls.md) mit Power BI 
| Vollbildmodus | Nein | Ja | [Vollbildmodus](../service-fullscreen-mode.md) im Power BI-Dienst 
| Erweiterte Zusammenarbeit mit Office 365 | Nein | Ja | [Zusammenarbeiten in einem App-Arbeitsbereich ](../service-collaborate-power-bi-workspace.md) mit Office 365 
| Visuelle R-Elemente | Nein | Ja | [Erstellen von R-Visuals](../service-r-visuals.md) im Power BI-Dienst  
| Vorschaufeatures | Nein | Ja | [Aktivieren von Vorschaufeatures im Power BI-Dienst](../service-preview-features.md) 
| Benutzerdefinierte Visualisierungen | Ja | Ja | [Benutzerdefinierte Visualisierungen in Power BI](../power-bi-custom-visuals.md) 
| Power BI Desktop | Für den Berichtsserver optimierte Version, zum Download mit dem Berichtsserver verfügbar | Für Power BI-Dienst optimierte Version, verfügbar im Windows Store | [Power BI Desktop für den Berichtsserver](https://powerbi.microsoft.com/report-server/) <br><br> [Power BI Desktop für den Power BI-Dienst](http://aka.ms/pbidesktopstore)

## <a name="next-steps"></a>Nächste Schritte
[Installieren von Power BI-Berichtsserver](install-report-server.md)  



