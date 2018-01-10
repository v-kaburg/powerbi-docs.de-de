---
title: Neuerungen in Power BI-Berichtsserver
description: Lernen Sie die Neuerungen in Power BI-Berichtsserver kennen. Dieser Artikel, in dem die wichtigsten Funktionsbereiche behandelt werden, wird aktualisiert, sobald neue Elemente freigegeben werden.
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
ms.date: 10/31/2017
ms.author: maghan
ms.openlocfilehash: 433581f77cfeaa002cffeecd927ba8751fc46617
ms.sourcegitcommit: eec6b47970bf69ed30638d1a20051f961ba792f2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/06/2018
---
# <a name="whats-new-in-power-bi-report-server"></a>Neuerungen in Power BI-Berichtsserver
Lernen Sie die Neuerungen in Power BI-Berichtsserver kennen. Dieser Artikel, in dem die wichtigsten Funktionsbereiche behandelt werden, wird aktualisiert, sobald neue Elemente freigegeben werden.

Um Power BI-Berichtsserver und Power BI Desktop mit Optimierung für Power BI-Berichtsserver herunterzuladen, navigieren Sie zu [Lokale Berichterstellung mit Power BI-Berichtsserver](https://powerbi.microsoft.com/report-server/).

![Tipp](media/whats-new/fyi-tip.png "Tipp") Die Versionsanmerkungen finden Sie unter [Power BI-Berichtsserver: Anmerkungen zu dieser Version](release-notes.md).

Informationen zu verwandten Neuigkeiten finden Sie unter:

* [Neuigkeiten beim Power BI-Dienst](../service-whats-new.md)
* [Neuigkeiten in Power BI Desktop](../desktop-latest-update.md)
* [Neuigkeiten bei den mobilen Apps für Power BI](../mobile-whats-new-in-the-mobile-apps.md)
* [Blog des Power BI-Teams](https://powerbi.microsoft.com/blog/)

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
[Power BI-Berichtsserver: Anmerkungen zu dieser Version](release-notes.md)  
[Benutzerhandbuch](user-handbook-overview.md)  
[Administratorhandbuch](admin-handbook-overview.md)  
[Schnellstart: Installieren von Power BI-Berichtsserver](quickstart-install-report-server.md)  
[Installieren des Berichts-Generators](https://docs.microsoft.com/sql/reporting-services/install-windows/install-report-builder)  
[Herunterladen der SQL Server Data Tools](http://go.microsoft.com/fwlink/?LinkID=616714)

Weitere Fragen? [Stellen Sie Ihre Frage in der Power BI-Community.](https://community.powerbi.com/)

