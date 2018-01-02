---
title: "Installieren von für Power BI-Berichtsserver optimiertem Power BI Desktop"
description: "Erfahren Sie mehr zum Installieren von für Power BI-Berichtsserver optimiertem Power BI Desktop"
services: powerbi
documentationcenter: 
author: maggiesMSFT
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
ms.date: 12/06/2017
ms.author: maggies
ms.openlocfilehash: 589a77624169e9fb59999109668439c5f729c5f5
ms.sourcegitcommit: 7248b5e449b2495d6baef385470d18edfacec457
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/08/2017
---
# <a name="install-power-bi-desktop-optimized-for-power-bi-report-server"></a>Installieren von für Power BI-Berichtsserver optimiertem Power BI Desktop
Erfahren Sie mehr zum Installieren von für Power BI-Berichtsserver optimiertem Power BI Desktop.

Damit Sie Power BI-Berichte für Power BI-Berichtsserver erstellen können, müssen Sie die für Power BI-Berichtsserver optimierte Power BI Desktop-Version herunterladen und installieren. Diese Version unterscheidet sich von der Power BI Desktop-Version, die mit dem Power BI-Dienst verwendet wird. Beispielsweise enthält die Power BI Desktop-Version für den Power BI-Dienst keine Vorschaufeatures, die nach der Veröffentlichung in der Version für den Power BI-Berichtsserver verfügbar sind. Sie müssen diese Version verwenden, um sicherzustellen, dass der Berichtsserver mit einer bekannten Version der Berichte und des Modells interagieren kann. 

> [!NOTE]
> Power BI Desktop und das für Power BI-Berichtsserver optimierte Power BI Desktop können parallel auf dem gleichen Computer installiert werden.

## <a name="download-and-install-power-bi-desktop"></a>Herunterladen und Installieren von Power BI Desktop

Die einfachste Möglichkeit, um sicherzustellen, dass Sie die aktuelle Version des für Power BI-Berichtsserver optimiertem Power BI Desktop verwenden, besteht darin, zunächst das Webportal des Berichtsservers aufzurufen.

1. Wählen Sie im Report Server Web-Portal die **herunterladen** Pfeil > **Power BI Desktop**.

    ![Power BI Desktop aus dem Webportal herunterladen](media/install-powerbi-desktop/report-server-download-web-portal.png)

    Sie können auch direkt [Microsoft Power BI Desktop](https://go.microsoft.com/fwlink/?linkid=861076) (optimiert für Power BI-Berichtsserver – Oktober 2017) im Microsoft Download Center aufrufen.

2. Wählen Sie im Download Center **Download** aus.

3. Wählen Sie abhängig von Ihrem Computer eine der folgenden Versionen aus: 

    - **PBIDesktopRS.msi** (32-Bit-Version) oder

    - **PBIDesktopRS_x64.msi** (64-Bit-Version).

1. Nachdem Sie das Installationsprogramm heruntergeladen haben, führen Sie den Setup-Assistenten für Power BI Desktop (Oktober 2017) aus.
2. Aktivieren Sie am Ende des Installationsvorgangs **Power BI Desktop jetzt starten**.
   
    Die App wird automatisch gestartet, sodass Sie gleich loslegen können.

## <a name="verify-you-are-using-the-correct-version"></a>Überprüfen, ob Sie die richtige Version verwenden
Sie können überprüfen, ob Sie die richtige Power BI Desktop-Version verwenden, indem Sie einen Blick auf den Startbildschirm oder die Titelleiste in Power BI Desktop werfen. In der Titelleiste werden Monat und Jahr des Releases angegeben.

![Titelleiste für „Installieren von für Power BI-Berichtsserver optimiertem Power BI Desktop“](media/quickstart-create-powerbi-report/report-server-desktop-october-2017-version.png)

Die Power BI Desktop-Version für den Power BI-Dienst gibt Monat und Jahr nicht in der Titelleiste an.

## <a name="file-extension-association"></a>Zuordnung der Dateinamenerweiterung
Wenn Sie Power BI Desktop und für Power BI-Berichtsserver optimiertes Power BI Desktop auf demselben Computer installiert haben, weist die letzte Installation von Power BI Desktop die Dateizuordnung zu PBIX auf. Wenn Sie nun auf eine PBIX-Datei doppelklicken, wird die Power BI Desktop-Version gestartet, die zuletzt installiert wurde.

Wenn Sie Power BI Desktop bereits installiert hatten und dann für Power BI-Berichtsserver optimiertes Power BI Desktop installiert haben, werden alle PBIX-Dateien standardmäßig in für Power BI-Berichtsserver optimiertem Power BI Desktop geöffnet. Wenn Sie möchten, dass beim Öffnen von PBIX-Dateien standardmäßig Power BI Desktop gestartet wird, müssen Sie Power BI Desktop über den Power BI-Dienst erneut installieren.

Sie können immer zuerst die Version von Power BI Desktop öffnen, die Sie verwenden möchten. Öffnen Sie anschließend die Datei in Power BI Desktop.

Zum Bearbeiten eines Power BI-Berichts in Power BI-Berichtsserver oder Erstellen eines neuen Power BI-Berichts über das Webportal wird stets die richtige Version von Power BI Desktop geöffnet.

## <a name="next-steps"></a>Nächste Schritte
Nachdem Sie Power BI Desktop installiert haben, können Sie mit dem Erstellen von Power BI-Berichten beginnen.

[Schnellstart: Erstellen eines Power BI-Berichts für Power BI-Berichtsserver](quickstart-create-powerbi-report.md)  
[Erste Schritte mit Power BI Desktop](../desktop-getting-started.md)  
Anleitung: [Erste Schritte mit Power BI Desktop](../guided-learning/gettingdata.yml#step-2)  
[Benutzerhandbuch: Übersicht über Power BI-Berichtsserver](user-handbook-overview.md)

Weitere Fragen? [Stellen Sie Ihre Frage in der Power BI-Community.](https://community.powerbi.com/)

