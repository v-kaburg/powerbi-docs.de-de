---
title: Zertifizierte benutzerdefinierte Power BI-Visualisierungen
description: Anforderungen und Vorgehensweise für das Einreichen eines benutzerdefinierten Visuals zur Zertifizierung sowie eine Liste bereits zertifizierter benutzerdefinierter Visuals.
author: mihart
manager: kfile
ms.reviewer: ''
featuredvideoid: ''
ms.service: powerbi
ms.component: powerbi-developer
ms.topic: conceptual
ms.date: 02/13/2018
ms.author: mihart
ms.openlocfilehash: 45bd00877aadba2a84ac533add18b82337fa8403
ms.sourcegitcommit: 0ff358f1ff87e88daf837443ecd1398ca949d2b6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/21/2018
ms.locfileid: "46546255"
---
# <a name="getting-a-custom-visual-certified"></a>Wie wird ein benutzerdefiniertes visuelles Element *zertifiziert*?
## <a name="what-is-meant-by-certified"></a>Was bedeutet *zertifiziert*?
Ein *zertifiziertes benutzerdefiniertes visuelles Element* hat verschiedene Codeanforderungen erfüllt und strenge Sicherheitstests bestanden.  Nachdem ein benutzerdefiniertes visuelles Element zertifiziert wurde, kann es [nach PowerPoint exportiert](consumer/end-user-powerpoint.md) werden und wird in den empfangenen E-Mails angezeigt, wenn ein Benutzer [Berichtsseiten abonniert](consumer/end-user-subscribe.md). Dieses kann ebenfalls wie ein [benutzerdefiniertes visuelles Standardelement](power-bi-custom-visuals.md) verwendet, zum Power BI-Dienst und zu Power BI Desktop-Berichten hinzugefügt und in Power BI Mobile angezeigt und eingebettet werden.

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
| [Aster-Plot](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380759) | |
| [Beyondsoft-Kalender](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381096) | |
| [Schleifendiagramm von MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380838) | [Video](https://youtu.be/So5xKMSpVJI) |
| [Kastengrafikdiagramm](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380831) | |
| [Kastengrafikdiagramm von MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381351) | [Video](https://youtu.be/JoHaFLfhXdo) |
| [Ziegeldiagramm von MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380836) | [Video](https://youtu.be/hA3DOsvn2xY) |
| [Blasendiagramm von Akvelon](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381340) | |
| [Bullet-Diagramm](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380755) | [Video](https://youtu.be/AOlsFYkfkcw) |
| [Bullet-Diagramm von OKViz](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380953) | [Video](https://youtu.be/mtvUNl9bMjA) |
| [Kalender von Tallan](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381146) | |
| [Kerzendiagramm von OKViz](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380952) | [Video](https://youtu.be/nT_18gyRxPo) |
| [Karte mit Zuständen von OKViz](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380967) | |
| [Chiclet-Slicer](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380756) | |
| [Chord](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380761) | [Video](https://youtu.be/AQvd2FhRyCI) |
| [Kreisförmiges Messgerät von MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380837) | [Video](https://youtu.be/9NHXALkBXuY) |
| [Clusterzuordnung](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380806) | |
| [Zylindrisches Messgerät von MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380874) | [Video](https://youtu.be/DgdoWi7Gcxo) |
| [Messuhrdiagramm](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381184) | |
| [Punktdiagramm](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380760) | |
| [Punktdiagramm von OKViz](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380949) | [Video](https://youtu.be/By16pX9KT40) |
| [Drilldown-Kartogramm](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381045) | |
| [Drilldown-Choroplethenkarte](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381044) | |
| [Drilldown-Säulendiagramm](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380857) | [Video](https://youtu.be/lBy2gQQ5YsQ) |
| [Drilldown-Säulendiagramm für zeitbasierte Daten](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380881) | [Video](https://youtu.be/T_mRou18vx0) |
| [Drilldown-Ringdiagramm](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380858) | [Video](https://youtu.be/AUVFrSHmPeo) |
| [Dual KPI](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380774) | |
| [Dynamic Tooltip von MAQ](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380983) | [Video](https://youtu.be/Z-tl97BpEr0) |
| [Erweitertes Punktdiagramm](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380762) | [Video](https://youtu.be/xCfM0cjM4do) |
| [Enlighten Aquarium](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381112) | |
| [Enlighten Slicer](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380960) | |
| [Enlighten Stack Shuffle](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380849) | |
| [Enlighten-Waffeldiagramm](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380850) | |
| [Force-Directed Graph](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380764) | [Video](https://youtu.be/YsTa7uyJ4sg) |
| [Trichterdiagramm mit Quelle von MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381334) | [Video](https://youtu.be/R_EcimsLI8U) |
| [Gantt](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380765) | [Video](https://youtu.be/qJ7s_KrGiUU) |
| [Gantt-Diagramm von MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381364) | [Video](https://youtu.be/vJLV9JRCpI8) |
| [Globe Data Bars](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381344) | |
| [Grid by MAQ Software (Raster von MAQ Software)](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380825) | [Video](https://youtu.be/VOPoDJgZfOY) |
| [Hierarchiediagramm von Akvelon](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381333) | [Video](https://youtu.be/0ZGzJaq_KT4) |
| [Histogramm](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380776) | |
| [Histogramm mit Punkten von MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381032) | [Video](https://youtu.be/-ILF--wExrw) |
| [Horizontales Trichterdiagramm von MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380846) | [Video](https://youtu.be/SudZei68PPo) |
| [Bild von CloudScope](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381297) | |
| [Bildraster](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381355) | |
| [Designer für Infografiken](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380898) | |
| [KPI-Diagramm von Akvelon](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381432) | |
| [KPI Column von MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380996) | [Video](https://youtu.be/rU0xoOlIq1U) |
| [KPI-Raster von MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380947) | [Video](https://youtu.be/dM4PvZh71V0) |
| [KPI-Indikator](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380832) | |
| [KPI-Ticker von MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380946) | [Video](https://youtu.be/cudG4gsZ2V8) |
| [Linearmessgerät von MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380821) | [Video](https://youtu.be/7_jFaM30dkc) |
| [LineDot-Diagramm](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380766) | |
| [Mekko-Diagramm](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380785) | [Video](https://youtu.be/90FLCKpgicA) |
| [Overview von CloudScope](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381477) | |
| [Wiedergabeachse (dynamischer Slicer)](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380981) | |
| [Power KPI](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381083) | [Video](https://youtu.be/IvfIP3E6-1Q) |
| [Power-KPI-Matrix](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381299) | [Video](https://youtu.be/1enze8pcGzY) |
| [Pulse-Diagramm](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381006) | [Video](https://youtu.be/DQWdcQtjDVw) |
| [Quadrant Chart by MAQ Software (Quadrant-Diagramm von MAQ Software)](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381011) | [Video](https://youtu.be/ppBnyhqWNC0) |
| [Netzdiagramm](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380771) | |
| [Ringdiagramm von MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380824) | [Video](https://youtu.be/pDToHDFHnq8) |
| [Drehbares Diagramm von MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381007) | [Video](https://youtu.be/d5xBCMmb3hU) |
| [Sankey-Diagramm](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380777) | [Video](https://youtu.be/WWP9wVUHGaA) |
| [Scroller](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381018) | |
| [Intelligenter Filter von OKViz](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380859) | [Video](https://youtu.be/gcJsDDRQq28) |
| [Sparkline von OKViz](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380910) | [Video](https://youtu.be/0m3Vnvso9tY) |
| [Stream-Diagramm](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380772) | |
| [Sunburst](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380767) | |
| [Synoptic Panel von OKViz](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380873) | |
| [Tabellenheatmap](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380818) | |
| [Tachometer](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380937) | [Video](https://youtu.be/C3OXdETbS9o) |
| [Textfilter](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381309) | |
| [Text-Wrapper von MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380826) | |
| [Thermometer von MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380847) | [Video](https://youtu.be/SPX9mgrAdBc) |
| [Time Brush-Slicer](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380798) | |
| [Timeline-Slicer](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380786) | [Video](https://youtu.be/ozMtZ4_NZ10) |
| [Timeline von CloudScope](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381427) | [Video](https://youtu.be/szNi9YgXFJc) |
| [Tornado-Diagramm](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380768) | [Video](https://www.youtube.com/watch?v=AQvd2FhRyCI) |
| [Handelsdiagramm von MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380823) | [Video](https://youtu.be/xhTR6y6J9Ko) |
| [Ultimative Varianz](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381140) | [Video](https://youtu.be/pDYF8iZxERs) |
| [Ultimatives Wasserfalldiagramm](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380956) | [Video](https://youtu.be/0BZsVCQdEkc) |
| [Benutzerliste von CloudScope](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381426) | |
| [Waffeldiagramm](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381049) | [Video](https://youtu.be/1vRqYUsm3Vk) |
| [Wortwolke](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380752) | [Video](https://youtu.be/AblTenl9fqo) |

## <a name="next-steps"></a>Nächste Schritte
[Erste Schritte mit den Power BI-Entwicklertools für benutzerdefinierte visuelle Elemente (Vorschau)](service-custom-visuals-getting-started-with-developer-tools.md)      
[Wiedergabeliste benutzerdefinierter visueller Elemente von Microsoft auf YouTube](https://www.youtube.com/playlist?list=PL1N57mwBHtN1vIjfvuBIzZllrmKo-Vz6x)  
[Visualisierungen in Power BI](visuals/power-bi-report-visualizations.md)  
[Benutzerdefinierte Visualisierungen in Power BI](power-bi-custom-visuals.md)  
[Veröffentlichen von benutzerdefinierten Visuals in Microsoft AppSource](developer/office-store.md)  
Weitere Fragen? [Wenden Sie sich an die Power BI-Community](http://community.powerbi.com/)

