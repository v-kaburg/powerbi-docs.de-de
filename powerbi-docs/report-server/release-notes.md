---
title: 'Power BI-Berichtsserver: Anmerkungen zu dieser Version'
description: "In diesem Thema werden die Einschränkungen und Probleme mit Power BI-Berichtsserver beschrieben."
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
ms.date: 11/01/2017
ms.author: maghan
ms.openlocfilehash: 7f59e3788b24344b5f86b146fb41e440eb0a2098
ms.sourcegitcommit: 6e693f9caf98385a2c45890cd0fbf2403f0dbb8a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2018
---
# <a name="power-bi-report-server-release-notes"></a>Power BI-Berichtsserver: Anmerkungen zu dieser Version
In diesem Thema werden die Einschränkungen und Probleme mit Power BI-Berichtsserver beschrieben.

Um Power BI-Berichtsserver und Power BI Desktop mit Optimierung für Power BI-Berichtsserver herunterzuladen, navigieren Sie zu [Lokale Berichterstellung mit Power BI-Berichtsserver](https://powerbi.microsoft.com/report-server/).

## <a name="october-2017"></a>Oktober 2017
* Unterstützung für importierte Daten in Power BI-Berichten
* Möglichkeit zum Anzeigen von Excel-Arbeitsmappen im Webportal. Hierfür wird Office Online Server konfiguriert.
* Unterstützung der neuen Power BI-Tabellen- und Matrixvisuals.
* REST-API-Unterstützung

## <a name="june-2017"></a>Juni 2017
* Keine neuen Elemente im Juni 2017.

## <a name="may-2017"></a>Mai 2017
* Power BI-Berichte müssen mit für Power BI-Berichtsserver optimiertem Power BI Desktop erstellt werden, um mit Power BI-Berichtsserver zu funktionieren. Sie können Power BI Desktop über den Downloadlink oben auf dieser Seite herunterladen.
* Power BI-Berichte unterstützen nur Liveverbindungen mit Analysis Services (tabellarisch oder mehrdimensional).
* Visuelle R-Elemente werden nicht unterstützt.

**Problem und Kundenbeeinträchtigung:** Wenn Sie SQL Server Reporting Services und Power BI-Berichtsserver auf demselben Computer installiert haben und eine der Anwendungen deinstallieren, können Sie mit dem verbleibenden Berichtsserver mithilfe von Report Server-Konfigurations-Manager keine Verbindung mehr herstellen.

**Problemumgehung** Um dieses Problem zu umgehen, müssen Sie nach der Deinstallation einer der Anwendungen die folgenden Schritte ausführen.

1. Starten Sie eine Eingabeaufforderung im Administratormodus.
2. Wechseln Sie zum Verzeichnis, in dem der verbleibende Berichtsserver installiert ist.
   
    *Standardspeicherort für Power BI-Berichtsserver: C:\Program Files\Microsoft Power BI Report Server*
   
    *Standardspeicherort für SQL Server Reporting Services: C:\Program Files\Microsoft SQL Server Reporting Services*
3. Wechseln Sie dann zum nächsten Ordner. Dieser heißt entweder *SSRS* oder *PBIRS* je nachdem, was übrig ist.
4. Wechseln Sie zum Ordner „WMI“.
5. Führen Sie den folgenden Befehl aus:
   
    ```
    regsvr32 /i ReportingServicesWMIProvider.dll
    ```
   
    Sie können den folgenden Fehler ignorieren, sofern dieser gemeldet wird.
   
    ```
    The module "ReportingServicesWMIProvider.dll" was loaded but the entry-point DLLInstall was not found. Make sure that "ReportingServicesWMIProvider.dll" is a valid DLL or OCX file and then try again.
    ```

## <a name="next-steps"></a>Nächste Schritte
[Neuerungen in Power BI-Berichtsserver](whats-new.md)  
[Benutzerhandbuch](user-handbook-overview.md)  
[Administratorhandbuch](admin-handbook-overview.md)  
[Schnellstart: Installieren von Power BI-Berichtsserver](quickstart-install-report-server.md)  
[Installieren des Berichts-Generators](https://docs.microsoft.com/sql/reporting-services/install-windows/install-report-builder)  
[Herunterladen der SQL Server Data Tools](http://go.microsoft.com/fwlink/?LinkID=616714)

Weitere Fragen? [Stellen Sie Ihre Frage in der Power BI-Community.](https://community.powerbi.com/)

