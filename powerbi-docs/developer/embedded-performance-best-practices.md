---
title: Bewährte Methoden für die Leistung von Power BI Embedded
description: Dieser Artikel enthält Anleitungen zu bewährten Methoden für Embedded Analytics
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-embedded
ms.topic: conceptual
ms.date: 12/12/2018
ms.openlocfilehash: 50fbb175640e38431db62df34276417f1080e42a
ms.sourcegitcommit: a36f82224e68fdd3489944c9c3c03a93e4068cc5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/31/2019
ms.locfileid: "55430348"
---
# <a name="power-bi-embedded-performance-best-practices"></a>Bewährte Methoden für die Leistung von Power BI Embedded

Dieser Artikel enthält Empfehlungen zum schnelleren Rendern von Berichten, Dashboards und Kacheln in Ihrer Anwendung

## <a name="embed-parameters"></a>Einbettungsparameter

Die Powerbi.embed()-Methode empfängt einige Parameter zum Einbetten eines Berichts, eines Dashboards oder einer Kachel. Diese Parameter haben Auswirkungen auf die Leistung.

### <a name="embed-url"></a>Einbettungs-URL

Vermeiden Sie es, die Einbettungs-URL selbst zu erstellen. Stellen Sie stattdessen sicher, dass Sie die Einbettungs-URL durch einen Aufruf der API [Get reports](/rest/api/power-bi/reports/getreportsingroup), [Get dashboards](/rest/api/power-bi/dashboards/getdashboardsingroup) oder [Get tiles](/rest/api/power-bi/dashboards/gettilesingroup) abrufen. Wir haben der URL einen neuen Parameter mit der Bezeichnung **_config_** hinzugefügt, der für Verbesserungen der Leistung verwendet wird.

### <a name="permissions"></a>Berechtigungen

Erteilen Sie die Berechtigung **Ansicht**, wenn Sie keinen Bericht im **Bearbeitungsmodus** einbetten möchten. Auf diese Weise initialisiert der Einbettungscode nicht die Komponenten, die für den Bearbeitungsmodus verwendet werden.

### <a name="filters-bookmarks-and-slicers"></a>Filter, Lesezeichen und Slicer

Normalerweise werden Visuals für Berichte mit zwischengespeicherten Daten gespeichert. Aufgrund der zwischengespeicherten Daten verbessert sich die gefühlte Leistung. Berichte können zwischengespeicherte Daten rendern, während die Abfragen ausgeführt werden. Wenn Filter, Lesezeichen oder Slicer angegeben werden, sind die zwischengespeicherten Daten nicht relevant. In diesen Fällen erfolgt das Rendern der Visuals erst nach dem Ausführen der Visual-Abfrage.

Wenn Sie Berichte mit gleichen Filtern einbetten, speichern Sie den Bericht mit bereits angewendeten Filtern, um die Übergabe einer Liste von Filtern in der Ladekonfiguration zu vermeiden.

## <a name="preload"></a>Vorab Laden

Verwenden Sie die JavaScript-API *preload*, um die Endbenutzerleistung zu verbessern.
Powerbi.preload() lädt Javascript, CSS-Dateien und weitere Artefakten herunter, die später für die Einbettung in einem Bericht verwendet werden.

Rufen Sie preload auf, wenn Sie den Bericht nicht sofort einbetten. Wenn Sie beispielsweise einen Bericht auf den Klick auf eine Schaltfläche hin einbetten, ist es sinnvoll, preload während des Ladens der vorhergehenden Seite aufzurufen. Wenn der Benutzer der Anwendung dann auf die Schaltfläche klickt, erfolgt das Rendern schneller.

## <a name="measure-performance"></a>Messen der Leistung

Verwenden Sie zum Messen der Leistung diese Indikatoren:

1. Loaded (Geladen): Zeit bis zur Initialisierung des Berichts (dem Benutzer wird kein Wartekreisel angezeigt).
2. Rendered (Gerendert): Zeit bis zur vollständigen Darstellung des Berichts mit realen Daten. Das Gerendert-Ereignis wird bei jedem erneuten Rendern des Berichts (also nach der Anwendung von Filtern) ausgelöst. Achten Sie bei der erstmaligen Messung eines Berichts darauf, die Berechnungen auf der Grundlage des zuerst ausgelösten Ereignisses durchzuführen.

Zwischengespeicherte Daten werden gerendert, wenn sie verfügbar sind, jedoch gibt es für diese Daten noch kein Ereignis.

## <a name="update-tools-and-sdk-packages"></a>Aktualisieren von Tools und SDK-Paketen

Halten Sie Tools und SDK-Pakete auf dem aktuellen Stand.

* Verwenden Sie immer die aktuellste Version von [Power BI Desktop](https://powerbi.microsoft.com/desktop/).

* Installieren Sie die aktuellste Version des [Power BI-Client-SDKs](https://github.com/Microsoft/PowerBI-JavaScript). Wir veröffentlichen fortlaufend weitere Verbesserungen, also sehen Sie von Zeit zu Zeit einmal nach.

* Zu installierende Pakete:
    * Npm-Paket: powerbi-client
    * NuGet-Paket: Microsoft.PowerBI.JavaScript

> [!Note]
> Bedenken Sie, dass die Ladezeit in erster Linie von den Elementen abhängt, die für den eigentlichen Bericht und die Daten wichtig sind. Das sind etwa die Anzahl der Visuals, die Größe der Daten und die Komplexität der Abfragen und berechneten Measures. Orientieren Sie sich an den [bewährten Methoden](../power-bi-reports-performance.md), um die Ladezeit des Berichts zu verbessern.

## <a name="next-steps"></a>Nächste Schritte

* [Bewährte Methoden für die Power BI-Leistung](../power-bi-reports-performance.md)
* [Behandeln von Problemen mit Power BI Embedded](embedded-troubleshoot.md)
* [Power BI Embedded – FAQ](embedded-faq.md)
