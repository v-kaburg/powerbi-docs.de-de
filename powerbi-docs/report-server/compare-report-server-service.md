---
title: Vergleich zwischen Power BI-Berichtsserver und Power BI-Dienst
description: In diesem Artikel werden die Features des Power BI-Berichtsservers und des Power BI-Diensts miteinander verglichen.
keywords: ''
author: maggiesMSFT
ms.author: maggies
ms.date: 11/16/2018
ms.topic: overview
ms.service: powerbi
ms.component: powerbi-report-server
manager: kfile
ms.custom: mvc
ms.openlocfilehash: 8689c9a2fded5e283740d82923d674b73434e6a1
ms.sourcegitcommit: a186679e8dae85dce23f6365bf5c36d7f407f15b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/16/2018
ms.locfileid: "51850451"
---
# <a name="comparing-power-bi-report-server-and-the-power-bi-service"></a>Vergleich zwischen Power BI-Berichtsserver und Power BI-Dienst

Der Power BI-Berichtsserver und der Power BI-Dienst weisen viele Ähnlichkeiten, aber auch einige wesentliche Unterschiede auf. In der folgenden Tabelle werden diese Ähnlichkeiten und Unterschiede erläutert.

## <a name="features-of-power-bi-report-server-and-the-power-bi-service"></a>Features des Power BI-Berichtsservers und des Power BI-Diensts

| Features | Power BI-Berichtsserver | Power BI-Dienst | Hinweise
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
| Dashboards | Nein | Ja | [Dashboards im Power BI-Dienst](../consumer/end-user-dashboards.md) 
| Verteilen von Berichtsgruppen mithilfe von Apps | Nein | Ja | [Erstellen und Veröffentlichen von Apps mit Dashboards und Berichten](../service-create-distribute-apps.md) 
| Inhaltspakete | Nein | Ja | [Einführung in organisationsbezogene Inhaltspakete in Power BI](../service-organizational-content-pack-introduction.md) 
| Herstellen einer Verbindung mit Diensten wie Salesforce | Ja | Ja | [Herstellen eine Verbindung mit den verwendeten Diensten](../consumer/end-user-connect-to-services.md) mithilfe von Inhaltspaketen im Power BI-Dienst. Verwenden Sie im Power BI-Berichtsserver Certified Connectors, um eine Verbindung mit Diensten herzustellen. Weitere Informationen finden Sie unter [Datenquellen für Power BI-Berichte in Power BI-Berichtsserver](data-sources.md).
| Q&A | Nein | Ja | [Q&A im Power BI-Dienst und in Power BI Desktop](../consumer/end-user-q-and-a.md) 
| Schnelle Einblicke | Nein | Ja | [Automatisches Erstellen von Einblicken in Daten mit Power BI](../consumer/end-user-insights.md) 
| In Excel analysieren | Nein | Ja | [In Excel analysieren](../service-analyze-in-excel.md) 
| Paginierte Berichte | Ja | Ja | [Paginierte Berichte sind mit der Premium-Kapazität in der Vorschauversion im Power BI-Dienst verfügbar](../paginated-reports-report-builder-power-bi.md)
| Mobile Power BI-Apps | Ja | Ja | [Übersicht über mobile Power BI-Apps](../consumer/mobile/mobile-apps-for-mobile-devices.md) 
| ArcGIS-Karten | Nein | Ja | [ArcGIS Maps von ESRI im Power BI-Dienst und in Power BI Desktop](../power-bi-visualization-arcgis.md)
| E-Mail-Abonnements für Power BI-Berichte | Nein | Ja | [Abonnieren eines Berichts oder Dashboards](../consumer/end-user-subscribe.md) im Power BI-Dienst 
| E-Mail-Abonnements für paginierte Berichte | Ja | Nein | [E-Mail-Übermittlung in Reporting Services](https://docs.microsoft.com/sql/reporting-services/subscriptions/e-mail-delivery-in-reporting-services)  
| Datenwarnungen | Nein | Ja | [Datenwarnungen](../service-set-data-alerts.md) im Power BI-Dienst
| Sicherheit auf Zeilenebene | Nur über die Datenquelle im DirectQuery-Modus | Verfügbar im DirectQuery-Modus (Datenquelle) und im Importmodus | [Sicherheit auf Zeilenebene](../service-admin-rls.md) mit Power BI 
| Vollbildmodus | Nein | Ja | [Vollbildmodus](../consumer/end-user-focus.md) im Power BI-Dienst 
| Erweiterte Zusammenarbeit mit Office 365 | Nein | Ja | [Zusammenarbeiten in einem App-Arbeitsbereich ](../service-collaborate-power-bi-workspace.md) mit Office 365 
| Visuelle R-Elemente | Nein | Ja | [Erstellen von R-Visuals](../desktop-r-visuals.md) in Power BI Desktop, um diese anschließend im Power BI-Dienst zu veröffentlichen. Power BI-Berichte können nicht zusammen mit R-Visuals im Power BI-Berichtsserver gespeichert werden.  
| Vorschaufeatures | Nein | Ja | [Aktivieren von Vorschaufeatures im Power BI-Dienst](../consumer/end-user-preview-features.md) 
| Benutzerdefinierte Visuals | Ja | Ja | [Benutzerdefinierte Visualisierungen in Power BI](../power-bi-custom-visuals.md) 
| Power BI Desktop | Für den Berichtsserver optimierte Version, zum Download mit dem Berichtsserver verfügbar | Für Power BI-Dienst optimierte Version, verfügbar im Windows Store | [Power BI Desktop für den Berichtsserver](https://powerbi.microsoft.com/report-server/) <br><br> [Power BI Desktop für den Power BI-Dienst](http://aka.ms/pbidesktopstore)

## <a name="next-steps"></a>Nächste Schritte
[Installieren von Power BI-Berichtsserver](install-report-server.md)  



