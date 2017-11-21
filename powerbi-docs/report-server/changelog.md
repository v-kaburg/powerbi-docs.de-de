---
title: "Änderungsprotokoll für Power BI-Berichtsserver"
description: "Dieses Änderungsprotokoll bezieht sich auf Power BI-Berichtsserver und enthält neue Elemente sowie Fehlerkorrekturen für jeden veröffentlichten Build."
services: powerbi
documentationcenter: 
author: jtarquino
manager: jonhp
backup: asaxton
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 09/19/2017
ms.author: jaimeta
ms.openlocfilehash: 9fdc757fca252c5c35d308dcd0b326098683b159
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2017
---
# <a name="changelog-for-power-bi-report-server"></a>Änderungsprotokoll für Power BI-Berichtsserver
Dieses Änderungsprotokoll bezieht sich auf Power BI-Berichtsserver und enthält neue Elemente sowie Fehlerkorrekturen für jeden veröffentlichten Build.

Ausführliche Informationen zu neuen Funktionen finden Sie unter [Neuerungen in Power BI-Berichtsserver](whats-new.md).

## <a name="october-2017"></a>Oktober 2017
* **Power BI-Berichtsserver**
  * *Version 1.1.6514.9163 (Build 14.0.600.434), Veröffentlichung: 1. November 2017*
    * Fehlerkorrekturen
      * Korrektur von Problemen bei der Zuverlässigkeit des Uploads von PBIX-Berichten mit mehr als 500 MB
      * Korrektur des Problems beim Laden von Daten für PBIX-Berichte mit mehr als 1 GB
  * *Version 1.1.6513.3500 (Build 14.0.600.433), Veröffentlichung: 31. Oktober 2017*
    * Features
      * Unterstützung von eingebetteten Datenmodellen
      * Anzeigen von Excel-Arbeitsmappen (bei aktivierter Office Online Server-Integration)
      * Geplante Datenaktualisierung (PBIX)
      * Unterstützung von direkten Abfragen
      * Unterstützung von großen Dateien (bis zu 2 GB)
      * Öffentliche REST-API
        * Unterstützung von freigegebenen Datasets in Power BI Desktop (über oData)
      * Unterstützung von URL-Parametern für PBIX-Dateien
      * Verbesserungen in Bezug auf die Barrierefreiheit
* **Power BI Desktop (optimiert für Power BI-Berichtsserver)**
  * *Version: 2.51.4885.1041 (Oktober 2017), Veröffentlichung: 31. Oktober 2017*
    * Enthält Änderungen, die für die Verbindung mit Power BI-Berichtsserver (Oktober 2017) erforderlich sind

## <a name="june-2017"></a>Juni 2017
* **Power BI-Berichtsserver**
  
  * *Build 14.0.600.305, Veröffentlichung: 19. September 2017*  
    
    * Fehlerkorrekturen
      * Aktualisierung auf das neueste [Websteuerelement für Bing Karten](https://msdn.microsoft.com/library/mt712542.aspx)
  * *Build 14.0.600.301, Veröffentlichung: 11. July 2017*
    
    * Fehlerkorrekturen
      * Das {{UserId}}-Tag wird in die gespeicherten Anmeldeinformationen aufgelöst und nicht in den Benutzer, der den Bericht in Power BI-Berichten ausführt.
      * Einige Bilder werden in Berichten in Power BI-Berichtsserver nicht dargestellt.
      * Der Name eines Power BI-Berichts kann im Power BI-Berichtsserver nicht geändert werden.
      * Benutzerdefinierte Visuals können in der mobilen Power BI-App nicht geladen werden (Neuinstallation der mobilen App erforderlich, um den lokalen Cache zu löschen)
  * *Build 14.0.600.271, Veröffentlichung: 12. June 2017*
    
    * Erste Veröffentlichung von Power BI-Berichtsserver

## <a name="next-steps"></a>Nächste Schritte
[Benutzerhandbuch](user-handbook-overview.md)  
[Administratorhandbuch](admin-handbook-overview.md)  
[Schnellstart: Installieren von Power BI-Berichtsserver](quickstart-install-report-server.md)  
[Installieren des Berichts-Generators](https://docs.microsoft.com/sql/reporting-services/install-windows/install-report-builder)  
[Herunterladen der SQL Server Data Tools](http://go.microsoft.com/fwlink/?LinkID=616714)

Weitere Fragen? [Stellen Sie Ihre Frage in der Power BI-Community.](https://community.powerbi.com/)

