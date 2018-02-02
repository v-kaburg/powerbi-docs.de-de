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
ms.date: 01/24/2018
ms.author: mihart
ms.openlocfilehash: f9824b29515481742c339bc76e766e5e62cf1716
ms.sourcegitcommit: be5223b62e9a5d57c52f8588d4e539d814751dd6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2018
---
# <a name="getting-a-custom-visual-certified"></a>Wie wird ein benutzerdefiniertes visuelles Element *zertifiziert*?
## <a name="what-is-meant-by-certified"></a>Was bedeutet *zertifiziert*?
Ein *zertifiziertes benutzerdefiniertes visuelles Element* hat verschiedene Codeanforderungen erfüllt und strenge Sicherheitstests bestanden.  Nachdem ein benutzerdefiniertes visuelles Element zertifiziert wurde, kann es [nach PowerPoint exportiert](service-publish-to-powerpoint.md) werden und wird in den empfangenen E-Mails angezeigt, wenn ein Benutzer [Berichtsseiten abonniert](service-report-subscribe.md). Dieses kann ebenfalls wie ein [benutzerdefiniertes visuelles Standardelement](power-bi-custom-visuals.md) verwendet, zum Power BI-Dienst und zu Power BI Desktop-Berichten hinzugefügt und in Power BI Mobile angezeigt und eingebettet werden.

Sind Sie Webentwickler und möchten eigene Visualisierungen erstellen und zu [Microsoft AppSource](https://appsource.microsoft.com) hinzufügen? Weitere Informationen hierzu finden Sie unter [Erste Schritte mit den Entwicklertools](service-custom-visuals-getting-started-with-developer-tools.md).


## <a name="certification-requirements"></a>Zertifizierungsanforderungen
* Von Microsoft AppSource genehmigt    
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
| Link zu AppSource | Link zum Video |
| --- | --- |
| [Zuordnungsregeln](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380815) | |
| [Aster-Plot](https://appsource.microsoft.com/product/power-bi-visuals/WA104380759?src=office&tab=Overview) | |
| [BciCalendar (Beyondsoft-Kalender)](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381096?src=office&tab=Overview)  | |
| [Schleifendiagramm von MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380838?src=office&tab=Overview) |[Video](https://youtu.be/So5xKMSpVJI) |
| [Kastengrafik](https://appsource.microsoft.com/product/power-bi-visuals/WA104380831?src=office&tab=Overview) | |
| [Ziegeldiagramm von MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380836) | |
| [Blasendiagramm von Akvelon](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381340?src=office) | |
| [Bullet-Diagramm](https://store.office.com/app.aspx?assetid=WA104380755) |[Video1](https://youtu.be/AOlsFYkfkcw)   [Video2](https://youtu.be/AQvd2FhRyCI) |
| [Bullet-Diagramm von OKViz](https://store.office.com/bullet-chart-by-okviz-WA104380953.aspx) |[Video](https://youtu.be/mtvUNl9bMjA) |
| [Kalender von Tallan](https://appsource.microsoft.com/product/power-bi-visuals/WA104381146?src=office&tab=Overview) | |
| [Kerzendiagramm von OKViz](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380952) | |
| [Chiclet Slicer ](https://store.office.com/chiclet-slicer-WA104380756.aspx) |[Video](https://youtu.be/iYOkJ1APueY) |
| [Sehnendiagramm](https://appsource.microsoft.com/product/power-bi-visuals/WA104380761?src=office&tab=Overview) |[Video](https://youtu.be/AQvd2FhRyCI) |
| [Kreisförmiges Messgerät von MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380837?tab=Overview) | |
| [Zylinderdiagramm](https://appsource.microsoft.com/product/power-bi-visuals/WA104380874) | |
| [Messuhrdiagramm](https://appsource.microsoft.com/product/power-bi-visuals/WA104381184) |[Video](https://youtu.be/AOlsFYkfkcw) |
| [Ringdiagramm von MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380824?tab=Overview) |[Video](https://youtu.be/pDToHDFHnq8) |
| [Punktdiagramm von MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381101) | |
| [Punktdiagramm von OKViz](https://appsource.microsoft.com/product/power-bi-visuals/WA104381101?src=office&tab=Overview) |[Video](https://youtu.be/4lskRgcpFJY) |
| [Punktdiagramm von Microsoft](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380760?src=office) | |
| [Drilldown-Ringdiagramm von ZoomCharts](https://appsource.microsoft.com/product/power-bi-visuals/WA104380858) | |
| [Drilldown-Kartogramm](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381045?src=office) | |
| [Drilldown-Choroplethenkarte](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381044?src=office) | |
| [Drilldown-Säulendiagramm von ZoomCharts](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380881?src=office) | |
| [Drilldown-Säulendiagramm für zeitbasierte Daten von ZoomCharts](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380881) | |
| [Drilldown-Ringdiagramm von ZoomCharts](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380858) | |
| [Dual KPI](https://store.office.com/dual-kpi-WA104380774.aspx) |[Video](https://youtu.be/821o0-eVBXo?list=PL1N57mwBHtN1vIjfvuBIzZllrmKo-Vz6x) |
| [Erweitertes Punktdiagramm](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380762) | |
| [Enlighten Aquarium](https://appsource.microsoft.com/product/power-bi-visuals/WA104381112?src=office&tab=Overview) | |
| [Enlighten Bubble Stack](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380868) | |
| [Enlighten Slicer](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380960?tab=Overview) | |
| [Enlighten Stack Shuffle](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380849) | |
| [Enlighten Waffle Chart](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380850) | |
| [Enlighten World Flags](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380923) | |
| [Force-Directed Graph](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380764) |[Video](https://youtu.be/YsTa7uyJ4sg) |
| [Forecasting TBATS](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381326?src=office) | |
| [Trichter mit Quelle]() | || [Gantt](https://store.office.com/gantt-WA104380765.aspx) |[Video](https://youtu.be/qJ7s_KrGiUU) |
| [Hierarchiediagramm von Akvelon](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381333?src=office) | |
| [Histogramm](https://store.office.com/histogram-chart-WA104380776.aspx) | |
| [Horizontales Trichterdiagramm](https://appsource.microsoft.com/product/power-bi-visuals/WA104380846) |[Video](https://youtu.be/SudZei68PPo) |
| [Bildzeitachse](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381254) | |
| [Designer für Infografiken](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380898?src=office) | |
| [KPI-Indikator](https://store.office.com/kpi-indicator-WA104380832.aspx) | |
| [KPI-Ticker von MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380946) | |
| [LineDot-Diagramm](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380766?src=office) | |
| [Linearmessgerät von MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380821?src=office&tab=Overview) |[Video](https://youtu.be/AOlsFYkfkcw) |
| [Mekko-Diagramm](https://appsource.microsoft.com/product/power-bi-visuals/WA104380785?src=office&tab=Overview)  | [Video](https://youtu.be/90FLCKpgicA)|
| [Wiedergabeachse (dynamischer Slicer)](https://store.office.com/play-axis-dynamic-slicer-WA104380981.aspx) | |
| [Power KPI](https://appsource.microsoft.com/product/power-bi-visuals/WA104381083) |[Video](https://youtu.be/IvfIP3E6-1Q) |
| [Pulsdiagramm](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381006) | |
| [Netzdiagramm](https://store.office.com/radar-chart-WA104380771.aspx) | |
| [Ringdiagramm von MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380824?src=office&tab=Overview) | [Video](https://youtu.be/pDToHDFHnq8)|
| [Drehbares Diagramm von MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381007?src=office) |  |
| [Sankey-Diagramm](https://store.office.com/app.aspx?assetid=WA104380777.aspx) |[Video](https://youtu.be/WWP9wVUHGaA) |
| [Scroller](https://store.office.com/scroller-WA104381018.aspx) |[Video](https://youtu.be/uhRFQF2cGSY) |
| [Intelligenter Filter von SQLBI](https://store.office.com/smart-filter-by-okviz-WA104380859.aspx) |[Video](https://youtu.be/gcJsDDRQq28) |
| [Sparkline von OKViz](https://appsource.microsoft.com/product/power-bi-visuals/WA104380910?src=office&tab=Overview) |[Video](https://youtu.be/0m3Vnvso9tY) |
| [Stream Graph](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380772?tab=Overview) |  |
| [Sunburst](https://appsource.microsoft.com/product/power-bi-visuals/WA104380767?src=office&tab=Overview) | |
| [Tabellenheatmap](https://store.office.com/table-heatmap-WA104380818.aspx) | |
| [Tachometer](https://store.office.com/tachometer-WA104380937.aspx?) |[Video](https://www.youtube.com/watch?v=C3OXdETbS9o) |
| [Textumbruch](https://appsource.microsoft.com/product/power-bi-visuals/WA104380826) | |
| [Thermometer](https://appsource.microsoft.com/product/power-bi-visuals/WA104380847?src=office&tab=Overview) | [Video](https://youtu.be/SPX9mgrAdBc)|
| [Zeitreihenaufgliederung](https://appsource.microsoft.com/product/power-bi-visuals/WA104380897) | |
| [Timeline Slicer](https://store.office.com/timeline-slicer-WA104380786.aspx) |[Video](https://youtu.be/ozMtZ4_NZ10) |
| [Tornado-Diagramm](https://store.office.com/tornado-chart-WA104380768.aspx) |[Video](https://youtu.be/AQvd2FhRyCI) |
| [Ultimatives Varianzdiagramm von Klaus Birringer](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381140?src=office) | |
| [Ultimatives Wasserfalldiagramm (kostenlos)](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380956) | |
| [VitaraCharts – MicroChart](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381165) | |
| [Waffeldiagramm](https://appsource.microsoft.com/product/power-bi-visuals/WA104381049?src=office&tab=Overview) |[Video](https://youtu.be/1vRqYUsm3Vk) |
| [Wortwolke](https://store.office.com/word-cloud-WA104380752.aspx?) |[Video](https://www.youtube.com/watch?v=AblTenl9fqo) |

## <a name="next-steps"></a>Nächste Schritte
[Erste Schritte mit den Power BI-Entwicklertools für benutzerdefinierte visuelle Elemente (Vorschau)](service-custom-visuals-getting-started-with-developer-tools.md)      
[Wiedergabeliste benutzerdefinierter visueller Elemente von Microsoft auf YouTube](https://www.youtube.com/playlist?list=PL1N57mwBHtN1vIjfvuBIzZllrmKo-Vz6x)  
[Visualisierungen in Power BI](power-bi-report-visualizations.md)  
[Benutzerdefinierte Visualisierungen in Power BI](power-bi-custom-visuals.md)  
[Veröffentlichen von benutzerdefinierten Visuals in Microsoft AppSource](developer/office-store.md)  
Weitere Fragen? [Wenden Sie sich an die Power BI-Community](http://community.powerbi.com/)

