---
title: Erste Schritte mit Power BI-Berichtsserver
description: 'Erfahren Sie, wie Power BI-Berichtsserver installiert wird. '
services: powerbi
documentationcenter: 
author: guyinacube
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 11/01/2017
ms.author: maghan
ms.openlocfilehash: a1dc05e722d4b50321b1fc825eeab9284d2d88b5
ms.sourcegitcommit: eec6b47970bf69ed30638d1a20051f961ba792f2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/06/2018
---
# <a name="get-started-with-power-bi-report-server"></a>Erste Schritte mit Power BI-Berichtsserver
Mithilfe der zahlreichen sofort einsetzbaren Tools und Dienste von Power BI-Berichtsserver können Sie Power BI-, mobile und paginierte Berichte lokal erstellen, bereitstellen und verwalten.

## <a name="create-deploy-and-manage-reports"></a>Erstellen, Bereitstellen und Verwalten von Berichten
Power BI-Berichtsserver ist eine Lösung, die Kunden lokal für das Erstellen, Veröffentlichen und Verwalten von Berichten bereitstellen. Diese Berichte werden anschließend auf verschiedene Weisen den gewünschten Benutzern zur Verfügung gestellt, z.B. in einem Webbrowser, auf einem Mobilgerät oder als E-Mail im Posteingang.

Power BI-Berichtsserver bietet ein Paket von Produkten:

* Ein modernes Webportal, das Sie in einem beliebigen modernen Browser anzeigen können. Im Webportal können Sie Berichte und KPIs organisieren und anzeigen. Sie können im Portal auch Excel-Arbeitsmappen speichern.
* Mit Power BI Desktop erstellte Power BI-Berichte, die Sie im Webportal in Ihrer Umgebung anzeigen können.
* Paginierte Berichte, damit Sie mit den entsprechenden Tools modern aussehende Berichte erstellen können.
* Mobile Berichte mit einem reaktionsfähigen Layout, das sich an verschiedene Geräte und die verschiedenen Möglichkeiten anpasst, diese zu halten.

Mehr dazu erfahren Sie im weiteren Verlauf dieses Artikels.

### <a name="whats-new-in-power-bi-report-server"></a>Neuerungen in Power BI-Berichtsserver
Mithilfe dieser Quellen bleiben Sie hinsichtlich neuer Features in Power BI-Berichtsserver auf dem neuesten Stand.

* [Neuerungen in Power BI-Berichtsserver](whats-new.md)
* [Microsoft Power BI-Blog](https://powerbi.microsoft.com/blog/)
* [Blog des SQL Server Reporting Services-Teams](https://blogs.msdn.microsoft.com/sqlrsteamblog/)
* [YouTube-Kanal „Guy in a Cube“](https://aka.ms/guyinacube)

## <a name="web-portal"></a>Webportal
![](media/get-started/web-portal.png)

Für Endbenutzer von Power BI-Berichtsserver erfolgt der Zugriff über ein modernes Webportal, das Sie in modernen Browsern anzeigen können. Sie können im neuen Portal auf alle Berichte und KPIs zugreifen.

Sie können Ihr benutzerdefiniertes [Branding](https://docs.microsoft.com/sql/reporting-services/branding-the-web-portal) auf das Webportal anwenden. Und auch KPIs können Sie direkt im Webportal erstellen. KPIs dienen zum Erfassen wichtiger Geschäftsmetriken auf einen Blick im Browser, ohne einen Bericht öffnen zu müssen.

Der Inhalt des Webportals ist nach Typ organisiert: Power BI-Berichte, mobile Berichte, paginierte Berichte und KPIs sowie Excel-Arbeitsmappen, freigegebene Datasets und freigegebene Datenquellen, die als Bausteine für Ihre Berichte dienen. Sie können diese hier in der herkömmlichen Ordnerhierarchie sicher speichern und verwalten. Sie können Ihre Favoriten markieren und den Inhalt verwalten, sofern Sie über diese Rolle verfügen.

Außerdem können Sie im neuen Webportal die Berichtsverarbeitung planen, auf Berichte bedarfsgesteuert zugreifen und veröffentlichte Berichte abonnieren.

Weitere Informationen zum [Webportal](https://docs.microsoft.com/sql/reporting-services/web-portal-ssrs-native-mode).

## <a name="power-bi-reports"></a>Power BI-Berichte
![](media/get-started/powerbi-reports.png)

Ein Power BI-Bericht stellt eine Ansicht eines Datasets aus verschiedenen Perspektiven dar, wobei die aus dem Dataset gewonnenen verschiedenen Ergebnisse und Einblicke als Visualisierungen angezeigt werden.  Ein Bericht kann eine einzelne Visualisierung, aber auch mehrere mit Visualisierungen gefüllte Seiten enthalten. Abhängig von Ihrem Aufgabengebiet erstellen Sie vielleicht Berichte, und/oder Sie nutzen oder verwenden Berichte.

Berichte basieren auf einem einzelnen Dataset. Jede Visualisierung in einem Bericht stellt eine wertvolle Information dar. Und die Visualisierungen sind nicht statisch. Sie können Daten hinzufügen und entfernen, die Visualisierungstypen ändern sowie Filter und Slicer anwenden, wenn Sie die Daten detaillierter untersuchen, um Erkenntnisse zu gewinnen und Antworten zu finden. Ähnlich wie ein Dashboard – aber mit noch mehr Funktionen – ist ein Bericht ausgesprochen interaktiv und weitgehend anpassbar, und die Visualisierungen werden aktualisiert, wenn sich die zugrunde liegenden Daten ändern.

## <a name="paginated-reports"></a>Paginierte Berichte
![](media/get-started/paginated-reports.png)

Paginierte Berichte haben ein Dokumentformat. Je mehr Daten Sie haben, desto mehr Zeilen enthalten die Tabellen und desto mehr Seiten enthält der Bericht. Dieses Format ist ideal zum Generieren zu druckender Dokumente mit festem Layout und perfektem Aussehen, wie z.B. PDF- und Word-Dateien.

Sie können mit dem [Berichts-Generator](https://docs.microsoft.com/sql/reporting-services/report-builder/report-builder-in-sql-server-2016) oder Berichts-Designer in [SQL Server Data Tools (SSDT)](https://docs.microsoft.com/sql/reporting-services/tools/reporting-services-in-sql-server-data-tools-ssdt) modern aussehende Berichte erstellen.

## <a name="report-server-programming-features"></a>Berichtsserver-Programmierfeatures
Nutzen Sie Programmierfeatures von Power BI-Berichtsserver zum Erweitern und Anpassen Ihrer Berichterstellungsfunktionen mithilfe von APIs für das Integrieren oder Erweitern der Daten- und Berichtsverarbeitung in benutzerdefinierten Anwendungen.

Weitere [Entwicklerdokumentation für Berichtsserver](https://docs.microsoft.com/sql/reporting-services/reporting-services-developer-documentation).

## <a name="next-steps"></a>Nächste Schritte
[Benutzerhandbuch](user-handbook-overview.md)  
[Administratorhandbuch](admin-handbook-overview.md)  
[Schnellstart: Installieren von Power BI-Berichtsserver](quickstart-install-report-server.md)  
[Installieren des Berichts-Generators](https://docs.microsoft.com/sql/reporting-services/install-windows/install-report-builder)  
[Herunterladen der SQL Server Data Tools](http://go.microsoft.com/fwlink/?LinkID=616714)

Weitere Fragen? [Stellen Sie Ihre Frage in der Power BI-Community.](https://community.powerbi.com/)

