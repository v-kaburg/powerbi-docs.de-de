---
title: Erstellen von Vorlageninhaltspaketen in Power BI
description: Erstellen von Vorlageninhaltspaketen
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 10/09/2017
ms.author: maggies
ms.openlocfilehash: ab80739b64a3fc72fec0af000b7678bfad585c6c
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/15/2019
ms.locfileid: "54285068"
---
# <a name="author-template-content-packs-in-power-bi"></a>Erstellen von Vorlageninhaltspaketen in Power BI
Für die Erstellung eines Vorlageninhaltspakets werden Power BI Desktop und „PowerBI.com“ verwendet. Ein Inhaltspaket besteht aus vier Komponenten:

* Über Abfragen können Sie die Daten [verbinden](desktop-connect-to-data.md) und [transformieren](desktop-query-overview.md) sowie [Parameter](https://powerbi.microsoft.com/blog/deep-dive-into-query-parameters-and-power-bi-templates/) definieren.  
* Mit dem Datenmodell können [Beziehungen](desktop-create-and-manage-relationships.md), [Measures](desktop-measures.md) und Q&A-Verbesserungen erstellt werden.  
* [Berichtseiten](desktop-report-view.md) enthalten visuelle Elemente und Filter für umfassende Einblicke in Ihre Daten.  
* [Dashboards](consumer/end-user-dashboards.md) und [Kacheln](service-dashboard-create.md) bieten eine Übersicht über die enthaltenen Einblicke.  

Möglicherweise sind Sie mit den einzelnen verfügbaren Power BI-Features vertraut. Beim Erstellen eines Inhaltspakets sind für die einzelnen Funktionen jedoch zusätzliche Aspekte zu berücksichtigen. Ausführliche Informationen dazu finden Sie in den nachfolgenden Abschnitten.

<a name="queries"></a>

## <a name="queries"></a>Abfragen
Bei Vorlageninhaltspaketen werden die in Power BI Desktop entwickelten Abfragen zum Herstellen einer Verbindung mit Ihrer Datenquelle und zum Importieren von Daten verwendet. Diese Abfragen sind erforderlich, um ein konsistentes Schema zurückzugeben. Sie werden für die geplante Datenaktualisierung unterstützt (die direkte Abfrage wird nicht unterstützt).

Vorlageninhaltspakete unterstützen nur eine Datenquelle pro Inhaltspaket. Definieren Sie daher Ihre Abfragen sorgfältig. Eine Datenquelle ist eine Quelle, für die die gleiche Authentifizierung erforderlich ist. Sie können mehrere API-Aufrufe in verschiedenen Abfragen vornehmen, wenn alle Aufrufe an den gleichen API-Endpunkt gerichtet sind und die gleiche Authentifizierung verwenden. Power BI-Inhaltspakete unterstützen nicht mehrere Quellen, für die verschiedene Authentifizierungen erforderlich sind.

### <a name="connect-to-your-api"></a>Herstellen einer Verbindung mit der API
Zunächst müssen Sie eine Verbindung mit der API aus Power BI Desktop herstellen, um Abfragen zu erstellen.

Sie können die in Power BI Desktop verfügbaren Datenconnectors direkt verwenden, um eine Verbindung mit der API herzustellen. Sie können mit dem Web-Datenconnector („Daten abrufen“ > „Web“) eine Verbindung mit Ihrer Rest-API oder mit dem OData-Connector („Daten abrufen“ > „OData-Feed“) eine Verbindung mit dem OData-Feed herstellen. Beachten Sie, dass diese Connectors nur ohne Anpassung verwendet werden können, wenn die API die Standardauthentifizierung unterstützt.

> [!NOTE]
> Wenn Ihre API andere Authentifizierungstypen wie OAuth 2.0 oder einen Web-API-Schlüssel verwendet, müssen Sie einen eigenen Datenconnector entwickeln, damit Power BI Desktop erfolgreich eine Verbindung mit der API herstellen und die Authentifizierung darüber durchführen kann. Informationen zum Entwickeln eines eigenen Datenconnectors für Ihr Inhaltspaket finden Sie in der [Dokumentation zu Datenconnectors](https://aka.ms/DataConnectors). 
>
>

### <a name="consider-the-source"></a>Überlegungen zur Quelle
Die Abfragen definieren die Daten, die im Datenmodell enthalten sind. Abhängig von der Größe Ihres Systems sollten diese Abfragen auch Filter enthalten, um sicherzustellen, dass Ihre Kunden mit einer überschaubaren Größe arbeiten, die für Ihr Geschäftsszenario geeignet ist.

Power BI-Inhaltspakete können mehrere Abfragen parallel und für mehrere Benutzer gleichzeitig ausführen.  Planen Sie Ihre Strategie für die Bandbreitendrosselung und Parallelität im Voraus, und fragen Sie uns, wie Sie Ihr Inhaltspaket fehlertolerant erstellen können.

### <a name="schema-enforcement"></a>Schemaerzwingung
Stellen Sie sicher, dass Ihre Abfragen bei Änderungen im System stabil bleiben. Durch Änderungen am Schema bei der Aktualisierung kann das Modell unterbrochen werden. Wenn die Quelle unter Umständen bei einigen Abfragen ein Nullschema oder ein fehlendes Schema zurückgeben kann, empfiehlt es sich, eine leere Tabelle zurückzugeben oder benutzerdefinierte Fehlermeldungen auszugeben, die für Benutzer aussagekräftig sind.

### <a name="parameters"></a>Parameter
Mit [Parametern](https://powerbi.microsoft.com/blog/deep-dive-into-query-parameters-and-power-bi-templates/) in Power BI Desktop können Benutzer Eingabewerte angeben, mit denen die von den Benutzern abgerufenen Daten angepasst werden. Machen Sie sich vorab Gedanken über die Parameter, und vermeiden Sie so die Nachbearbeitung nach der zeitaufwendigen Erstellung detaillierter Abfragen oder Berichte.

> [!NOTE]
> Vorlageninhaltspakete unterstützen derzeit nur Textparameter. Bei der Entwicklung können zwar andere Parametertypen verwendet werden, während des [Testens](template-content-pack-testing.md#templates) werden jedoch alle von den Benutzern angegebenen Werte als Literale verwendet.
>
>

### <a name="additional-query-tips"></a>Weitere Tipps zu Abfragen

* Stellen Sie sicher, dass alle Spalten richtig angegeben sind.
* Spalten müssen über aussagekräftige Namen verfügen (siehe „Q&A“).  
* Bei gemeinsam verwendeter Logik empfiehlt sich die Verwendung von Funktionen oder Abfragen.  
* Sicherheitsstufen werden derzeit im Dienst nicht unterstützt. Wenn Sie eine Aufforderung zu Sicherheitsstufen erhalten, müssen Sie die Abfrage möglicherweise für die Verwendung relativer Pfade neu schreiben.  

## <a name="data-model"></a>Datenmodell

Durch ein klar definiertes Datenmodell wird sichergestellt, dass Ihre Kunden mühelos und intuitiv mit dem Inhaltspaket interagieren können. Erstellen Sie das Datenmodell in Power BI Desktop.

> [!NOTE]
> Ein Großteil der grundlegenden Modellierung (Typisierung, Spaltennamen) sollte in den [Abfragen](#queries) erfolgen.
>
>

### <a name="qa"></a>Q&A
Die Modellierung wirkt sich auch darauf aus, inwiefern beim Q&A Ergebnisse für Ihre Kunden bereitgestellt werden können. Stellen Sie sicher, dass Sie für häufig verwendete Spalten Synonyme hinzufügen und dass die Spalten in den [Abfragen](#queries) richtig benannt sind.

### <a name="additional-data-model-tips"></a>Weitere Tipps zum Datenmodell
* Auf alle Wertspalten müssen Formatierungen angewendet werden.
    >[!NOTE]
    >In der Abfrage sollten Typen angewendet werden.  
* Auf alle Measures müssen Formatierungen angewendet werden.  
* Die Standardzusammenfassung ist festgelegt, insbesondere ggf. „Nicht zusammenfassen“ (z. B. für eindeutige Werte).  
* Die Datenkategorie ist bei Bedarf festgelegt.  
* Beziehungen sind bei Bedarf festgelegt.  

## <a name="reports"></a>Berichte
Die Berichtseiten bieten zusätzliche Einblicke in die im Inhaltspaket enthaltenen Daten. Verwenden Sie die Seiten der Berichte, um die wichtigsten unternehmerischen Fragestellungen zu beantworten, auf die mit dem Inhaltspaket eingegangen werden soll. Erstellen Sie den Bericht mithilfe von Power BI Desktop.

> [!NOTE]
> Ein Inhaltspaket kann jeweils nur einen Bericht enthalten. Nutzen Sie die verschiedenen Seiten, um bestimmte Bereiche Ihres Szenarios aufzurufen.
>
>

### <a name="additional-report-tips"></a>Weitere Tipps zu Berichten
* Verwenden Sie mehrere visuelle Elemente pro Seite für die Kreuzfilterung.  
* Richten Sie die visuellen Elemente sorgfältig aus (keine Überlappungen).  
* Das Layout der Seite ist auf den Modus „4:3“ oder „16:9“ festgelegt.  
* Alle dargestellten Aggregationen sind im Hinblick auf numerische Werte sinnvoll (Mittelwerte, eindeutige Werte).  
* Segmentierungen führen zu vernünftigen Ergebnissen.  
* Das Logo ist mindestens im obersten Bericht vorhanden.  
* Elemente sind weitestgehend im Farbschema des Kunden definiert.  

<a name="dashboard"></a>

## <a name="dashboard"></a>Dashboard
Das Dashboard ist für Ihre Kunden der zentrale Ort der Interaktion mit Ihrem Inhaltspaket. Es sollte eine Übersicht über die Inhalte, insbesondere die wichtigen Metriken Ihres Geschäftsszenarios, enthalten.

Zum Erstellen eines Dashboards für Ihr Vorlageninhaltspaket laden Sie einfach Ihre PBIX-Datei über „Daten abrufen“ > „Dateien“ hoch, oder veröffentlichen Sie sie direkt über Power BI Desktop.

> [!NOTE]
> Bei Vorlageninhaltspaketen sind derzeit pro Inhaltspaket jeweils ein einzelner Bericht und ein einzelnes Dataset erforderlich. Heften Sie keine Inhalte aus mehreren Berichten oder Datasets an das im Inhaltspaket verwendete Dashboard an.
>
>

### <a name="additional-dashboard-tips"></a>Weitere Tipps zum Dashboard
* Behalten Sie beim Anheften dasselbe Design bei, sodass die Kacheln im Dashboard einheitlich sind.  
* Heften Sie ein Logo an das Design an, damit Kunden wissen, woher das Inhaltspaket stammt.  
* Als Layout für die meisten Bildschirmauflösungen empfehlen sich 5 bis 6 kleine Kacheln in der Breite.  
* Alle Dashboardkacheln müssen über geeignete Titel bzw. Untertitel verfügen.  
* Ziehen Sie für verschiedene Szenarios vertikale oder horizontale Gruppierungen im Dashboard in Betracht.  

<a name="restrictions"></a>

## <a name="summary-of-restrictions"></a>Zusammenfassung der Einschränkungen
Wie in den Abschnitten oben angeführt, weisen die Vorlageninhaltspakete derzeit einige Einschränkungen auf:  

| Unterstützt | *Nicht unterstützt* |
| --- | --- |
| In PBI Desktop erstellte Datasets |*Datasets aus anderen Inhaltspaketen oder Eingaben wie z. B. Excel-Dateien* |
| Datenquelle wird für die geplante Datenaktualisierung in der Cloud unterstützt |*Direkte Abfrage oder lokale Konnektivität wird nicht unterstützt* |
| Abfragen, die ein konsistentes Schema oder gegebenenfalls Fehler zurückgeben |*Dynamische oder benutzerdefinierte Schemas* |
| Eine Datenquelle pro Dataset |*Mehrere Datenquellen, z. B. Mashups oder URLs, die als mehrere Datenquellen erkannt werden* |
| Parameter vom Typ „Text“ |*Andere Parametertypen (z. B. „Datum“) oder „Liste zulässiger Werte“* |
| Ein Dashboard, ein Bericht und ein Dataset |*Mehrere Dashboards, Berichte oder Datasets* |

## <a name="next-step"></a>Nächster Schritt
[Testen und Einreichen von Vorlageninhaltspaketen](template-content-pack-testing.md)