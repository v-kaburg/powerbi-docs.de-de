---
title: Zertifizierte benutzerdefinierte Power BI-Visualisierungen
description: "Anforderungen und Vorgehensweise für das Einreichen eines benutzerdefinierten Visuals zur Zertifizierung sowie eine Liste bereits zertifizierter benutzerdefinierter Visuals."
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/27/2017
ms.author: mihart
ms.openlocfilehash: 27af387a6d789b00837e6bbf8c6be9aa219c7198
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2017
---
# <a name="getting-a-custom-visual-certified"></a>Wie wird ein benutzerdefiniertes visuelles Element *zertifiziert*?
## <a name="what-is-meant-by-certified"></a>Was bedeutet *zertifiziert*?
Ein *zertifiziertes benutzerdefiniertes visuelles Element* hat verschiedene Codeanforderungen erfüllt und strenge Sicherheitstests bestanden.  Nachdem ein benutzerdefiniertes visuelles Element zertifiziert wurde, kann es [nach PowerPoint exportiert](service-publish-to-powerpoint.md) werden und wird in den empfangenen E-Mails angezeigt, wenn ein Benutzer [Berichtsseiten abonniert](service-report-subscribe.md).

* Sind Sie Webentwickler und möchten eigene Visualisierungen erstellen und dem Store hinzufügen? Lesen Sie [Erste Schritte mit den Entwicklertools](service-custom-visuals-getting-started-with-developer-tools.md), und besuchen Sie den [Office Store](service-custom-visuals-office-store.md), um zu erfahren, wie Sie vorgehen müssen.
* Gibt es ein Office Store-Visual, das Sie regelmäßig verwenden? Bitten Sie den Entwickler des Visuals, dieses von Microsoft zertifizieren zu lassen.  Die Kontaktinformationen des Entwicklers befinden sich auf der Seite **Weitere Informationen** des visuellen Elements unter **Anbieter**.

## <a name="certification-requirements"></a>Zertifizierungsanforderungen
* Genehmigung für Office Store    
* Das benutzerdefinierte visuelle Element wurde mit der API-Version 1.2 oder höher geschrieben    
* Coderepository steht zur Überprüfung bereit (z.B. als auf GitHub für uns verfügbarer Code des visuellen Elements)    
* Ausschließliche Verwendung öffentlich überprüfbarer OSS-Komponenten    
* Kein Zugriff auf externe Dienste oder Ressourcen    

> **TIPP**: Es wird empfohlen, dass Sie EsLint mit dem standardmäßigen Sicherheitsregelsatz verwenden, um Ihren Code vor der Einreichung zu überprüfen.
> 
> 

## <a name="process-for-submitting-a-custom-visual-for-certification"></a>Vorgang zum Einreichen eines benutzerdefinierten visuellen Elements zur Zertifizierung
So reichen Sie ein benutzerdefiniertes visuelles Element zur Zertifizierung ein

1. Senden Sie eine E-Mail an den Power BI-Support für benutzerdefinierte visuelle Elemente (pbicvsupport@microsoft.com). Fügen Sie der E-Mail die folgende Informationen hinzu:    
   
   * Titel: Zertifizierungsanforderung für visuelles Element    
   * Link zum GitHub-Repository, in dem der Quellcode des visuellen Elements gehostet wird    
   * Befolgen der Anforderungen (siehe oben)    
   * Bestehen der Code- und Sicherheitsüberprüfung    
2. Das Microsoft-Team für benutzerdefinierte visuelle Elemente benachrichtigt Sie, sobald Ihr benutzerdefiniertes visuelles Element zertifiziert und der Liste „Zertifiziert“ (siehe unten) hinzugefügt wurde oder mit einem Bericht zu den zu behebenden Problemen abgelehnt wurde. Es ist Aufgabe des Entwicklers, eine offene Kommunikation mit Microsoft zu pflegen und seine zertifizierten visuellen Elemente bei Bedarf zu aktualisieren.

## <a name="removal-of-power-bi-certified-custom-visuals"></a>Entfernen benutzerdefinierter zertifizierter visueller Power BI-Elemente
Microsoft kann nach eigenem Ermessen ein visuelles Element aus der Liste „Zertifiziert“ entfernen.  

## <a name="list-of-custom-visuals-that-have-been-certified"></a>Liste benutzerdefinierter visueller Elemente, die zertifiziert wurden
| Link zum Office Store | Link zum Video |
| --- | --- |
| [Zuordnungsregeln](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380815) | |
| [Aster-Plot](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380759?src=office&tab=Overview) | |
| [BciCalendar] demnächst verfügbar | |
| [Kastengrafik](https://appsource.microsoft.com/product/power-bi-visuals/WA104380831?src=office&tab=Overview) | |
| [Bullet-Diagramm](https://store.office.com/en-us/app.aspx?assetid=WA104380755) |[Video1](https://youtu.be/AOlsFYkfkcw)   [Video2](https://youtu.be/AQvd2FhRyCI) |
| [Bullet-Diagramm von OKViz](https://store.office.com/bullet-chart-by-okviz-WA104380953.aspx) |[Video](https://youtu.be/mtvUNl9bMjA) |
| [Karte mit Zuständen von OKViz](https://store.office.com/card-with-states-by-okviz-WA104380967.aspx) |[Video1](https://youtu.be/myiX0BmZd8U)   [Video2](https://youtu.be/AOlsFYkfkcw) |
| [Chiclet Slicer ](https://store.office.com/chiclet-slicer-WA104380756.aspx) |[Video](https://youtu.be/iYOkJ1APueY) |
| [Kreisförmiges Messgerät von MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380837?tab=Overview) | |
| [Zylinderdiagramm](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380874) | |
| [Messuhrdiagramm](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381184) |[Video](https://youtu.be/AOlsFYkfkcw) |
| [Ringdiagramm von MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380824?tab=Overview) |[Video](https://youtu.be/pDToHDFHnq8) |
| [Drilldown-Ringdiagramm](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380858) | |
| [Dual KPI](https://store.office.com/dual-kpi-WA104380774.aspx) |[Video](https://youtu.be/821o0-eVBXo?list=PL1N57mwBHtN1vIjfvuBIzZllrmKo-Vz6x) |
| Schwungrad – in Kürze verfügbar | |
| [Gantt](https://store.office.com/gantt-WA104380765.aspx) |[Video](https://youtu.be/qJ7s_KrGiUU) |
| [Histogramm](https://store.office.com/histogram-chart-WA104380776.aspx) | |
| [Horizontales Trichterdiagramm](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380846) |[Video](https://youtu.be/SudZei68PPo) |
| [Bildzeitachse](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381254) | |
| [KPI-Indikator](https://store.office.com/kpi-indicator-WA104380832.aspx) | |
| Flüssigkeitspegel-Tachometerdiagramm – in Kürze verfügbar |[Video](https://youtu.be/wQ51TTqIZc4) |
| [Linearmessgerät von MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380821?src=office&tab=Overview) |[Video](https://youtu.be/AOlsFYkfkcw) |
| Viewer für langen Text – demnächst verfügbar | |
| [Wiedergabeachse (dynamischer Slicer)](https://store.office.com/play-axis-dynamic-slicer-WA104380981.aspx) | |
| [Power KPI](https://appsource.microsoft.com/product/power-bi-visuals/WA104381083) |[Video](https://youtu.be/IvfIP3E6-1Q) |
| [Pulsdiagramm](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381006?src=office&tab=Overview) |[Video](https://www.youtube.com/watch?v=DQWdcQtjDVw) |
| [Netzdiagramm](https://store.office.com/radar-chart-WA104380771.aspx) | |
| [Sankey-Diagramm](https://store.office.com/app.aspx?assetid=WA104380777.aspx) |[Video](https://youtu.be/WWP9wVUHGaA) |
| [Ringdiagramm von MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380824) |[Video](https://youtu.be/pDToHDFHnq8) |
| [Scroller](https://store.office.com/scroller-WA104381018.aspx) |[Video](https://youtu.be/uhRFQF2cGSY) |
| [Intelligenter Filter von OKViz](https://store.office.com/smart-filter-by-okviz-WA104380859.aspx) |[Video](https://youtu.be/gcJsDDRQq28) |
| [Sparkline von OKViz](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380910?src=office&tab=Overview) |[Video](https://youtu.be/0m3Vnvso9tY) |
| [Sunburst](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380767?src=office&tab=Overview) | |
| [Tachometer](https://store.office.com/tachometer-WA104380937.aspx?) |[Video](https://www.youtube.com/watch?v=C3OXdETbS9o) |
| [Zeitreihenaufgliederung](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380897) | |
| [Tabellenheatmap](https://store.office.com/table-heatmap-WA104380818.aspx) | |
| [Textumbruch](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380826) | |
| [Timeline Slicer](https://store.office.com/timeline-slicer-WA104380786.aspx) |[Video](https://youtu.be/ozMtZ4_NZ10) |
| [Tornado-Diagramm](https://store.office.com/tornado-chart-WA104380768.aspx) |[Video](https://youtu.be/AQvd2FhRyCI) |
| [Visio-Visual (Vorschauversion)](https://store.office.com/visio-visual-preview-WA104381132.aspx) |[Video](https://www.youtube.com/watch?v=dCcd7rftjZA&list=PL1N57mwBHtN1vIjfvuBIzZllrmKo-Vz6x&index=2) |
| [Waffeldiagramm](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381049?src=office&tab=Overview) |[Video](https://youtu.be/1vRqYUsm3Vk) |
| [Wortwolke](https://store.office.com/word-cloud-WA104380752.aspx?) |[Video](https://www.youtube.com/watch?v=AblTenl9fqo) |

## <a name="next-steps"></a>Nächste Schritte
[Herunterladen und Verwenden benutzerdefinierter Visualisierungen aus dem Office Store](service-custom-visuals-office-store.md)  
[Erste Schritte mit den Power BI-Entwicklertools für benutzerdefinierte visuelle Elemente (Vorschau)](service-custom-visuals-getting-started-with-developer-tools.md)      
[Wiedergabeliste benutzerdefinierter visueller Elemente von Microsoft auf YouTube](https://www.youtube.com/playlist?list=PL1N57mwBHtN1vIjfvuBIzZllrmKo-Vz6x)  
[Visualisierungen in Power BI](power-bi-report-visualizations.md)  
[Benutzerdefinierte Visualisierungen in Power BI](power-bi-custom-visuals.md)  
[Verwenden benutzerdefinierter Visualisierungen in Power BI Desktop](power-bi-custom-visuals-use.md)  
[Veröffentlichen benutzerdefinierter Visualisierungen im Office Store](developer/office-store.md)  
Weitere Fragen? [Wenden Sie sich an die Power BI-Community](http://community.powerbi.com/)

