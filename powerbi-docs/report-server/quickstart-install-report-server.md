---
title: 'Schnellstart: Installieren von Power BI-Berichtsserver'
description: Die Installation von Power BI-Berichtsserver selbst erfolgt sehr schnell. Die Schritte zum Herunterladen, Installieren und Konfigurieren bis zur Inbetriebnahme dauern nur wenige Minuten.
services: powerbi
documentationcenter: 
author: markingmyname
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
ms.date: 01/29/2018
ms.author: maghan
ms.openlocfilehash: 3ddf8870fd4fb3186ff884220fc4a7de7632c78d
ms.sourcegitcommit: 6e693f9caf98385a2c45890cd0fbf2403f0dbb8a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2018
---
# <a name="quickstart-install-power-bi-report-server"></a>Schnellstart: Installieren von Power BI-Berichtsserver
Die Installation von Power BI-Berichtsserver selbst erfolgt sehr schnell. Die Schritte zum Herunterladen, Installieren und Konfigurieren bis zur Inbetriebnahme dauern nur wenige Minuten.

Dies ist ein kurzer Überblick über die Installation eines Berichtsservers, wenn Sie lediglich einen neuen Server in Betrieb nehmen möchten. Detaillierte Informationen zum Installieren eines Berichtsservers finden Sie unter [Installieren von Power BI-Berichtsserver](install-report-server.md).

 **Herunterladen** ![herunterladen](media/quickstart-install-report-server/download.png "herunterladen")

Um Power BI-Berichtsserver herunterzuladen, navigieren Sie zu [Lokale Berichterstellung mit Power BI-Berichtsserver](https://powerbi.microsoft.com/report-server/). 

Wechseln Sie zum Microsoft Download Center, um [Microsoft Power BI Desktop](https://go.microsoft.com/fwlink/?linkid=861076) (optimiert für Power BI-Berichtsserver – Oktober 2017) herunterzuladen.

![Tipp](media/quickstart-install-report-server/fyi-tip.png "Tipp") Die Versionsanmerkungen finden Sie unter [Power BI-Berichtsserver: Anmerkungen zu dieser Version](release-notes.md).

<iframe width="640" height="360" src="https://www.youtube.com/embed/zacaEb9A4F0?showinfo=0" frameborder="0" allowfullscreen></iframe>

## <a name="before-you-begin"></a>Vorbereitende Schritte
Vor der Installation von Power BI-Berichtsserver wird empfohlen, dass Sie die [Hardware- und Softwareanforderungen für die Installation von Power BI-Berichtsserver](system-requirements.md) überprüfen.

## <a name="step-1-download"></a>Schritt 1: Herunterladen
Laden Sie Installationsdateien für Power BI-Berichtsserver lokal herunter. Power BI-Berichtsserver können Sie aus dem [Microsoft Download Center](https://go.microsoft.com/fwlink/?linkid=839351) herunterladen.

![Herunterladen von Power BI-Berichtsserver](media/quickstart-install-report-server/download-pbireportserver.png)

## <a name="step-2-run-installer"></a>Schritt 2: Ausführen des Installationsprogramms
Führen Sie die Datei „PowerBIReportServer.exe“ aus, die Sie heruntergeladen haben, und durchlaufen Sie die Installationsbildschirme. Sie können den Installationspfad und auch die zu installierende Edition auswählen. Sie haben die Wahl zwischen einer Evaluierungsversion mit einer Laufzeit von180 Tagen, einer Edition für Entwickler und der Angabe eines Produkt Keys.

![Installieren von Power BI-Berichtsserver](media/quickstart-install-report-server/pbireportserver-install.png)

## <a name="step-3-configure-the-server"></a>Schritt 3: Konfigurieren des Servers
Nach der Installation führen Sie den Konfigurations-Manager aus, um die Einrichtung des Servers abzuschließen. Sie müssen eine Report Server-Katalogdatenbank erstellen und die Webportal- und Webdienst-URLs bestätigen.

![Konfigurieren von Power BI-Berichtsserver](media/quickstart-install-report-server/pbireportserver-configure.png)

## <a name="step-4-browse-to-web-portal"></a>Schritt 4: Navigieren zum Webportal
Im Anschluss an die Konfiguration sollten Sie in einem Browser zum Webportal des Servers navigieren können. Dessen Adresse ist standardmäßig `http://localhost/reports`. Sie können anstelle der standardmäßigen Verwendung von „localhost“ auch den Computernamen angeben, vorausgesetzt, Sie werden nicht durch einen beliebigen Typ von Firewall blockiert.

![Webportal von Power BI-Berichtsserver](media/quickstart-install-report-server/web-portal.png)

## <a name="next-steps"></a>Nächste Schritte
[Administratorhandbuch](admin-handbook-overview.md)  
[Ermitteln des Product Key für den Berichtsserver](find-product-key.md)  
[Installieren von Power BI-Berichtsserver](install-report-server.md)  
[Installieren von für Power BI-Berichtsserver optimiertem Power BI Desktop](install-powerbi-desktop.md)  
[Browserunterstützung für Power BI-Berichtsserver](browser-support.md)

Weitere Fragen? [Stellen Sie Ihre Frage in der Power BI-Community.](https://community.powerbi.com/)

