---
title: Neuerungen in Power BI-Berichtsserver
description: Lernen Sie die Neuerungen in Power BI-Berichtsserver kennen. Dieser Artikel, in dem die wichtigsten Funktionsbereiche behandelt werden, wird aktualisiert, sobald neue Elemente freigegeben werden.
services: powerbi
documentationcenter: ''
author: maggiesMSFT
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 04/19/2018
ms.author: maggies
ms.openlocfilehash: 21769ee9c88dd2310da2a86be8dbadd1f17522ff
ms.sourcegitcommit: 493f160d04ed411ff4741c599adc63ba1f65230f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33813252"
---
# <a name="whats-new-in-power-bi-report-server"></a>Neuerungen in Power BI-Berichtsserver
Lernen Sie die Neuerungen in Power BI-Berichtsserver kennen. Dieser Artikel, in dem die wichtigsten Funktionsbereiche behandelt werden, wird aktualisiert, sobald neue Elemente freigegeben werden.

Um Power BI-Berichtsserver und Power BI Desktop mit Optimierung für Power BI-Berichtsserver herunterzuladen, navigieren Sie zu [Lokale Berichterstellung mit Power BI-Berichtsserver](https://powerbi.microsoft.com/report-server/).

Sehen Sie sich auch folgende Quellen an, um sich über die neuesten Features in Power BI-Berichtsserver zu informieren.

* [Microsoft Power BI-Blog](https://powerbi.microsoft.com/blog/)
* [Blog des SQL Server Reporting Services-Teams](https://blogs.msdn.microsoft.com/sqlrsteamblog/)
* [YouTube-Kanal „Guy in a Cube“](https://aka.ms/guyinacube)

Informationen zu verwandten Power BI-Neuigkeiten finden Sie hier:

* [Neuigkeiten beim Power BI-Dienst](../service-whats-new.md)
* [Neuigkeiten in Power BI Desktop](../desktop-latest-update.md)
* [Neuigkeiten bei den mobilen Apps für Power BI](../mobile-whats-new-in-the-mobile-apps.md)

## <a name="march-2018-release"></a>Release im März 2018

Das für Power BI-Berichtsserver optimierte Release von Power BI Desktop im März 2018 enthält viele neue Features. Die nach Bereichen aufgeteilten neuen Features sind die folgenden: 
- [Visuals](#visuals-updates)
- [Berichterstellung](#reporting)
- [Analyse](#analytics)
- [Leistung](#performance)
- [Berichtsserver](#report-server)
- [Andere](#other-improvements)

### <a name="highlights-of-this-release"></a>Highlights dieses Releases

Diese neuen Funktionen stechen besonders aus der langen Liste heraus:

#### <a name="rule-based-conditional-formatting-for-table-and-matrixhttpspowerbimicrosoftcomblogpower-bi-desktop-november-2017-feature-summaryconditionalformatting"></a>[Regelbasierte bedingte Formatierung für Tabellen und Matrizen](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2017-feature-summary/#conditionalFormatting)
 
Erstellen von Filtern, die unter bestimmten Bedingungen und abhängig von der spezifischen Geschäftslogik in Ihrer Tabelle oder Matrix die Farbe des Hintergrunds oder der Schriftfarbe einer Spalte verändern.

#### <a name="show-and-hide-pageshttpspowerbimicrosoftcomblogpower-bi-desktop-january-2018-feature-summaryhidepages"></a>[Ein- und Ausblenden von Seiten](https://powerbi.microsoft.com/blog/power-bi-desktop-january-2018-feature-summary/#hidePages)

Sie wollen Lesern den Zugriff auf Ihren Bericht gewähren, obwohl einige Seiten noch nicht fertig bearbeitet sind? Jetzt können Sie diese Seiten ausblenden, bis sie fertig bearbeitet sind. Oder Sie können Seiten ausblenden, die über die normale Navigationsleiste gesucht werden. Leser können diese Seiten mithilfe von Lesezeichen oder Drillthrough abrufen.

#### <a name="bookmarkinghttpspowerbimicrosoftcomblogpower-bi-desktop-march-2018-feature-summarybookmarking"></a>[Hinzufügen von Lesezeichen](https://powerbi.microsoft.com/blog/power-bi-desktop-march-2018-feature-summary/#bookmarking)

Erstellen Sie Lesezeichen, um mit den Daten in Ihrem Bericht eine Geschichte zu erzählen.

- [Kreuzhervorhebung für Lesezeichen](https://powerbi.microsoft.com/blog/power-bi-desktop-december-feature-summary/#bookmarkCrossHighlighting): Lesezeichen enthalten den Status der Kreuzhervorhebung einer Berichtsseite zum Zeitpunkt des Erstellens des Lesezeichens und zeigen diese an.
- [Mehr Flexibilität bei Lesezeichen](https://powerbi.microsoft.com/blog/power-bi-desktop-december-feature-summary/#bookmarkFlexibility): Lesezeichen reflektieren die von Ihnen im Bericht festgelegten Eigenschaften und haben nur Auswirkungen auf die von Ihnen gewählten Visuals.

#### <a name="multi-select-data-points-across-multiple-chartshttpspowerbimicrosoftcomblogpower-bi-desktop-february-2018-feature-summarycrosshighlight"></a>[Mehrfachauswahl von Datenpunkten aus mehreren Diagrammen](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#crosshighlight)

Wählen Sie mehrere Datenpunkte aus mehreren Diagrammen aus, und wenden Sie den Kreuzfilter auf die ganze Seite an.

#### <a name="sync-slicers-across-multiple-pages-of-your-reporthttpspowerbimicrosoftcomblogpower-bi-desktop-february-2018-feature-summarysyncslicers"></a>[Synchronisieren von Slicern auf mehreren Seiten Ihres Berichts](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#syncSlicers)

Ein Slicer kann für eine, zwei oder mehrere Seiten in einem Bericht angewendet werden.

#### <a name="quick-measureshttpspowerbimicrosoftcomblogpower-bi-desktop-february-2018-feature-summaryquickmeasures"></a>[Quickmeasures](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#quickMeasures) 

Erstellen Sie neue Measures, die auf bereits vorhandenen Measures und numerischen Spalten in einer Tabelle basieren.

#### <a name="drilling-down-filters-other-visualshttpspowerbimicrosoftcomblogpower-bi-desktop-december-feature-summarydrillfiltersothervisuals"></a>[Drilldownfilter für andere Visuals](https://powerbi.microsoft.com/blog/power-bi-desktop-december-feature-summary/#drillFiltersOtherVisuals)

Wenn Sie in einer bestimmten Kategorie eines Visuals einen Drilldown ausführen, können Sie alle Visuals auf der Seite nach derselben Kategorie filtern.

### <a name="visuals-updates"></a>Updates für Visuals

- [Zellenausrichtung in Tabellen und Matrizen](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2017-feature-summary/#alignment)
- [Anzeigeeinheiten und Präzisionssteuerung für Tabellen- und Matrixspalten](https://powerbi.microsoft.com/blog/power-bi-desktop-march-2018-feature-summary/#displayUnits)
- [Datenbezeichungen für den Überlauf von Balken- und Säulendiagrammen](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#overflow)
- [Steuern der Hintergrundfarbe von Datenbeschriftungen für kartesische Visuals und Kartenvisuals](https://powerbi.microsoft.com/blog/power-bi-desktop-january-2018-feature-summary/#dataLabelBackground)
- [Steuerelement zum Auffüllen von Leisten und Spalten](https://powerbi.microsoft.com/blog/power-bi-desktop-january-2018-feature-summary/#padding)
- [Vergrößern des für Achsenbezeichnungen verwendeten Bereichs in Diagrammen](https://powerbi.microsoft.com/blog/power-bi-desktop-january-2018-feature-summary/#axisSize)
- [Punktdiagrammvisual aus x- und y-Achsengruppierungen](https://powerbi.microsoft.com/blog/power-bi-desktop-december-feature-summary/#scatterChart)
- [Stichprobenentnahme mit hoher Dichte für Karten auf Grundlage von Breiten- und Längengrad](https://powerbi.microsoft.com/blog/power-bi-desktop-december-feature-summary/#highDensityMaps)
- [Dynamische Datenschnitte](https://powerbi.microsoft.com/blog/power-bi-desktop-december-feature-summary/#responsive)
- [Hinzufügen eines Ankerdatums für einen relativen Datenschnitt mit Datum](https://powerbi.microsoft.com/blog/power-bi-desktop-january-2018-feature-summary/#anchorDate)

### <a name="reporting"></a>Berichterstellung

- [Deaktivieren des visuellen Headers im Lesemodus für einen Bericht](https://powerbi.microsoft.com/blog/power-bi-desktop-march-2018-feature-summary/#visualHeader)
- [Berichtsoptionen für langsame Datenquellen](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2017-feature-summary/#slowDataSource)
- [Verbesserte Standardplatzierung von Visuals](https://powerbi.microsoft.com/blog/power-bi-desktop-march-2018-feature-summary/#visualPlacement)
- [Steuern der Visualsortierung über den Auswahlbereich](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2017-feature-summary/#selectionPane)
- [Sperren von Objekten im Bericht](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2017-feature-summary/#lock)
- [Durchsuchen der Bereiche „Formatierung“ und „Analyse“](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#search)
- [Bereich „Feldeigenschaften“ und Feldbeschreibungen](https://powerbi.microsoft.com/blog/power-bi-desktop-december-feature-summary/#fieldPropertiesPane)

### <a name="analytics"></a>Analytics

- [UTCNOW() und UTCTODAY()](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#utcDAX)
- [Markieren einer benutzerdefinierten Datumstabelle](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#customDateTable)
- [Drillfilter für andere Visuals](https://powerbi.microsoft.com/blog/power-bi-desktop-december-feature-summary/#drillFiltersOtherVisuals)
- [Formatierung auf Zellenebene mehrdimensionaler AS-Modelle für mehrzeilige Zuordnung](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2017-feature-summary/#cellLevelFormatting)
 
### <a name="performance"></a>Performance

- [Verbesserung der Filterleistung](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2017-feature-summary/#filtering)
- [Leistungsverbesserungen für DirectQuery](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#dqPerf)
- [Leistungsverbesserungen beim Öffnen und Speichern](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#savePerf)
- [Verbesserungen an „Elemente ohne Daten anzeigen“](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#showItemsWithNoData)
 
### <a name="report-server"></a>Berichtsserver 

#### <a name="export-to-accessible-pdf"></a>Exportieren in eine zugängliche PDF

Wenn Sie einen paginierten Bericht (RDL) in eine PDF exportieren, erhalten Sie jetzt eine verfügbare/markierte PDF-Datei. Diese Datei ist zwar größer, aber für Sprachausgabedienste und andere unterstützende Technologien leichter zu lesen und zu navigieren. Sie können zugängliche PDFs aktivieren, indem Sie die Geräteinformationseinstellung **AccessiblePDF** auf **TRUE** festlegen. Informationen hierzu finden Sie unter [PDF Device Information Settings (PDF-Geräteinformationseinstellungen)](https://docs.microsoft.com/sql/reporting-services/pdf-device-information-settings) und [Changing Device Information Settings (Ändern der Geräteinformationseinstellungen)](https://docs.microsoft.com/sql/reporting-services/customize-rendering-extension-parameters-in-rsreportserver-config#changing-device-information-settings).


### <a name="other-improvements"></a>Sonstige Verbesserungen

- [Verbesserung der Funktion „Spalte aus Beispielen hinzufügen“](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2017-feature-summary/#addColumnFromExamples)
- [Schnellzugriff auf Beratungsdienste](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#consultingServices)
- [Verbesserte Fehlerberichtserstellung](https://powerbi.microsoft.com/blog/power-bi-desktop-march-2018-feature-summary/#errors)
- [Anzeigen zuvor aufgetretener Fehler](https://powerbi.microsoft.com/blog/power-bi-desktop-march-2018-feature-summary/#viewErrors)

 
## <a name="october-2017-release"></a>Version vom Oktober 2017
### <a name="power-bi-report-data-sources"></a>Power BI-Berichtsdatenquellen
Power BI-Berichte in Power BI-Berichtsserver können mit einer Vielzahl von Datenquellen verbunden werden. Sie können Daten importieren und die Datenaktualisierung planen oder die Daten mit DirectQuery oder über eine Liveverbindung mit SQL Server Analysis Services direkt abfragen. Siehe die Liste der Datenquellen, die die geplante Aktualisierung unterstützen, sowie die Liste der Datenquellen, die DirectQuery unterstützen, in „Datenquellen für Power BI-Berichte in Power BI-Berichtsserver“.

### <a name="scheduled-data-refresh-for-imported-data"></a>Geplante Datenaktualisierung für importierte Daten
In Power BI-Berichtsserver können Sie eine geplante Datenaktualisierung einrichten, um die Daten in Power BI-Berichten mit einem eingebetteten Modell und nicht über eine Liveverbindung oder DirectQuery auf dem aktuellen Stand zu halten. Mit einem eingebetteten Modell importieren Sie die Daten, sodass sie von der ursprünglichen Datenquelle getrennt sind. Die Aktualisierung ist erforderlich, um die Daten auf dem neuesten Stand zu halten, und dies können Sie mit einer geplanten Aktualisierung erreichen. Informieren Sie sich über die „geplante Aktualisierung für Power BI-Berichte in Power BI-Berichtsserver“.

### <a name="editing-power-bi-reports-from-the-server"></a>Bearbeiten von Power BI-Berichten auf dem Server
Sie können Power BI-Berichtsdateien (PBIX-Dateien) vom Server aus öffnen und bearbeiten, Sie erhalten jedoch die hochgeladene Originaldatei zurück.  Das bedeutet, **wenn die Daten durch den Server aktualisiert wurden, sind die Daten beim erstmaligen Öffnen der Datei nicht aktualisiert**. Sie müssen Sie lokal manuell aktualisieren, damit die Änderungen sichtbar werden.

### <a name="large-file-uploaddownload"></a>Hochladen/Herunterladen großer Dateien
Sie können Dateien mit einer Größe von bis zu 2 GB hochladen; standardmäßig ist die Beschränkung jedoch in den Berichtsservereinstellungen in SSMS (SQL Server Management Studio) auf 1 GB festgelegt.  Diese Dateien werden im unveränderten Zustand für SharePoint in der Datenbank gespeichert, und es bedarf keiner speziellen Konfiguration für den SQL Server-Katalog.  

### <a name="accessing-shared-datasets-as-odata-feeds"></a>Zugreifen auf freigegebene Datasets als OData-Feeds
Sie können mit einem OData-Feed auf freigegebene Datasets aus Power BI Desktop zugreifen. Weitere Informationen erhalten Sie unter [Zugreifen auf freigegebene Datasets als OData-Feeds in Power BI-Berichtsserver](access-dataset-odata.md).

### <a name="scale-out"></a>Horizontales Hochskalieren
Diese Version unterstützt das horizontale Hochskalieren. Verwenden Sie einen Lastenausgleich, und legen Sie die Serveraffinität fest, um die optimale Leistung zu erhalten. Beachten Sie, dass das Szenario noch nicht für das horizontale Hochskalieren optimiert ist; daher werden Modelle möglicherweise über mehrere Knoten hinweg repliziert. Das Szenario funktioniert ohne den Netzwerklastenausgleich und persistente Sitzungen. Sie stellen jedoch nicht nur eine übermäßige Nutzung von Arbeitsspeicher über Knoten hinweg fest, da das Modell N-mal geladen wird, auch die Leistung zwischen den Verbindungen wird beeinträchtigt, weil das Modell beim Antreffen eines neuen Knotens zwischen Anforderungen gestreamt wird.  

### <a name="administrator-settings"></a>Administratoreinstellungen
Administratoren können die folgenden Eigenschaften in den erweiterten SSMS-Eigenschaften für die Serverfarm festlegen:

* EnableCustomVisuals: True/False
* EnablePowerBIReportEmbeddedModels: True/False
* EnablePowerBIReportExportData: True/False
* MaxFileSizeMb: Standardeinstellung ist nun 1.000
* ModelCleanupCycleMinutes: Häufigkeit der Überprüfungen zum Entfernen von Modellen aus dem Arbeitsspeicher
* ModelExpirationMinutes: Zeitraum bis zum Ablauf und Entfernen des Modells, basierend auf dem Zeitpunkt der letzten Verwendung
* ScheduleRefreshTimeoutMinutes: Mögliche Dauer der Datenaktualisierung für ein Modell. In der Standardeinstellung beläuft sich diese auf zwei Stunden.  Es gibt keine feste Obergrenze.

**Konfigurationsdatei „rsreportserver.config“**

```
<Configuration>
  <Service>
    <PollingInterval>10</PollingInterval>
    <IsDataModelRefreshService>false</IsDataModelRefreshService>
    <MaxQueueThreads>0</MaxQueueThreads>
  </Service>
</Configuration>
```

### <a name="developer-api"></a>Entwickler-API
Die für SSRS 2017 eingeführte Entwickler-API (REST-API) wurde für Power BI-Berichtsserver in Bezug auf die Arbeit mit Excel-Dateien und PBIX-Dateien ausgeweitet. Ein möglicher Anwendungsfall ist der programmgesteuerte Download von Dateien vom Server, deren Aktualisierung sowie die anschließende Neuveröffentlichung der Dateien. Dies ist beispielsweise die einzige Möglichkeit, Excel-Arbeitsmappen mit PowerPivot-Modellen zu aktualisieren.

Beachten Sie, dass eine neue separate API für große Dateien vorhanden ist, die in der Power BI-Berichtsserverversion von Swagger aktualisiert wird. 

### <a name="sql-server-analysis-services-ssas-and-the-power-bi-report-server-memory-footprint"></a>Speicherbedarf von SQL Server Analysis Services (SSAS) und Power BI-Berichtsserver
Power BI-Berichtsserver hostet SQL Server Analysis Services (SSAS) nun intern. Dies ist für die geplante Aktualisierung nicht spezifisch. Das Hosten von SSAS kann den Speicherbedarf für den Berichtsserver stark erhöhen. Die Konfigurationsdatei „AS.ini“ ist auf den Serverknoten verfügbar. Wenn Sie mit SSAS vertraut sind, können Sie die Einstellungen aktualisieren, u.a. die Obergrenze für Arbeitsspeicher und Datenträgerzwischenspeicherung. Einzelheiten finden Sie unter [Servereigenschaften in Analysis Services](https://docs.microsoft.com/sql/analysis-services/server-properties/server-properties-in-analysis-services).

### <a name="viewing-and-interacting-with-excel-workbooks"></a>Anzeigen von und Interagieren mit Excel-Arbeitsmappen
Excel und Power BI enthalten ein Portfolio von Tools, das in der Branche einmalig ist. Gemeinsam ermöglichen sie es Wirtschaftsanalytikern, ihre Daten einfacher zu erfassen, zu strukturieren, zu analysieren und in visueller Form zu durchsuchen. Geschäftsanwender können nun nicht nur Power BI-Berichte im Webportal, sondern auch Excel-Arbeitsmappen in Power BI-Berichtsserver anzeigen. Damit verfügen sie über einen zentralen Ort zum Veröffentlichen und Anzeigen ihrer Microsoft BI-Self-Service-Inhalte.

Wir haben eine [exemplarische Vorgehensweise zum Hinzufügen von Office Online Server (OOS) zu Ihrer Power BI-Berichtsserver-Umgebung (Vorschauversion)](excel-oos.md) veröffentlicht. Kunden mit einem Volume Licensing-Konto können OOS kostenlos im Volume Licensing-Servicecenter herunterladen. Die Funktionalität für sie ist schreibgeschützt. Nach der Konfiguration können Benutzer Excel-Arbeitsmappen anzeigen und mit diesen interagieren. Für die Arbeitsmappen muss Folgendes gelten:

* Sie verfügen über keine Abhängigkeiten von externen Datenquellen.
* Sie verfügen über eine Liveverbindung mit einer SQL Server Analysis Services-Datenquelle.
* Sie weisen ein PowerPivot-Datenmodell auf.

### <a name="support-for-new-table-and-matrix-visuals"></a>Unterstützung für neue Tabellen- und Matrixvisuals
Power BI-Berichtsserver unterstützt nun die neuen Power BI-Tabellen- und Matrixvisuals. Wenn Sie Berichte mit diesen Visuals erstellen möchten, benötigen Sie eine Power BI Desktop-Version, die für Version vom Oktober 2017 aktualisiert ist. Eine parallele Installation mit der Version Power BI Desktop (Juni 2017) ist nicht möglich. Um die aktuelle Version von Power BI Desktop zu erhalten, wählen Sie auf der [Power BI-Berichtsserver-Downloadseite](https://powerbi.microsoft.com/report-server/) die Option **Erweiterte Downloadoptionen** aus.

## <a name="june-2017"></a>Juni 2017
* Allgemeine Verfügbarkeit von Power BI-Berichtsserver.

## <a name="may-2017"></a>Mai 2017
* Vorschauversion von Power BI-Berichtsserver jetzt verfügbar
* Möglichkeit zum lokalen Veröffentlichen von Power BI-Berichten
  * Unterstützung benutzerdefinierter visueller Elemente
  * Ausschließliche Unterstützung für Analysis Services-Liveverbindungen (weitere Datenquellen folgen)
  * Mobile Power BI-App so aktualisiert, dass in Power BI-Berichtsserver gehostete Power BI-Berichte angezeigt werden
* Bessere Zusammenarbeit in Berichten mit Kommentaren

## <a name="next-steps"></a>Nächste Schritte
[Benutzerhandbuch](user-handbook-overview.md)  
[Administratorhandbuch](admin-handbook-overview.md)  
[Installieren von Power BI-Berichtsserver](install-report-server.md)  
[Installieren des Berichts-Generators](https://docs.microsoft.com/sql/reporting-services/install-windows/install-report-builder)  
[Herunterladen der SQL Server Data Tools](http://go.microsoft.com/fwlink/?LinkID=616714)

Weitere Fragen? [Stellen Sie Ihre Frage in der Power BI-Community.](https://community.powerbi.com/)

