---
title: Tipps für die Erstellung von Vorlagen-Apps in Power BI (Vorschau)
description: Tipps für die Erstellung von Abfragen, Datenmodellen, Berichten und Dashboards für gute Vorlagen-Apps
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 04/19/2019
ms.author: maggies
ms.openlocfilehash: 83049a16ecd42b41375da57a5a99a374596a9846
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2019
ms.locfileid: "65514864"
---
# <a name="tips-for-authoring-template-apps-in-power-bi-preview"></a>Tipps für die Erstellung von Vorlagen-Apps in Power BI (Vorschau)

Wenn Sie in Power BI [Ihre Vorlagen-App erstellen](service-template-apps-create.md), besteht ein Teil des Erstellungsprozesses in der Logistik für die Erstellung eines Arbeitsbereichs, für Tests und für die Produktionsphase. Der andere wichtige Teil besteht ganz klar in der Erstellung des Berichts und des Dashboards. Wir können den Erstellungsprozess in vier Hauptkomponenten unterteilen. Das Arbeiten mit diesen Komponenten hilft Ihnen dabei, die Vorlagen-App bestmöglich zu erstellen:

* Mit **Abfragen** [verbinden](desktop-connect-to-data.md) und [transformieren](desktop-query-overview.md) Sie die Daten, und Sie definieren [Parameter](https://powerbi.microsoft.com/blog/deep-dive-into-query-parameters-and-power-bi-templates/). 
* In dem **Datenmodell** können Sie [Beziehungen](desktop-create-and-manage-relationships.md), [Measures](desktop-measures.md) und Q&A-Verbesserungen erstellen.  
* **[Berichtseiten](desktop-report-view.md)** enthalten Visuals und Filter für Einblicke in Ihre Daten.  
* **[Dashboards](consumer/end-user-dashboards.md)** und [Kacheln](service-dashboard-create.md) bieten eine Übersicht über die enthaltenen Einblicke.
* Beispieldaten werden unmittelbar nach der Installation der app gefunden.

Möglicherweise sind Sie mit den einzelnen verfügbaren Power BI-Features vertraut. Beim Erstellen einer Vorlagen-App sind weitere Punkte für jedes Element zu beachten. Weitere Informationen finden Sie in den einzelnen Abschnitten unten.

<a name="queries"></a>

## <a name="queries"></a>Abfragen
Bei Vorlagen-Apps werden die in Power BI Desktop entwickelten Abfragen zum Herstellen einer Verbindung mit Ihrer Datenquelle und zum Importieren von Daten verwendet. Diese Abfragen sind erforderlich, um ein konsistentes Schema zurückzugeben. Sie werden für die geplante Datenaktualisierung unterstützt (DirectQuery wird nicht unterstützt).

### <a name="connect-to-your-api"></a>Herstellen einer Verbindung mit der API
Zunächst müssen Sie eine Verbindung mit der API aus Power BI Desktop herstellen, um Abfragen zu erstellen.

Sie können die in Power BI Desktop verfügbaren Datenconnectors direkt verwenden, um eine Verbindung mit der API herzustellen. Sie können mit dem Web-Datenconnector („Daten abrufen“ > „Web“) eine Verbindung mit Ihrer Rest-API oder mit dem OData-Connector („Daten abrufen“ > „OData-Feed“) eine Verbindung mit dem OData-Feed herstellen. Diese Connectors können nur ohne Anpassung verwendet werden, wenn die API die Standardauthentifizierung unterstützt.

> [!NOTE]
> Wenn Ihre API andere Authentifizierungstypen wie OAuth 2.0 oder einen Web-API-Schlüssel verwendet, müssen Sie einen eigenen Datenconnector entwickeln, damit Power BI Desktop erfolgreich eine Verbindung mit der API herstellen und die Authentifizierung darüber durchführen kann. PBI-Dienst für die sie für den Zugriff durch die Vorlage app-Installer muss Ihr benutzerdefinierte Connector hinzugefügt werden. <br> Informationen zum Entwickeln eines eigenen Datenconnectors für Ihre Vorlagen-App finden Sie in der [Dokumentation zu Datenconnectors](https://aka.ms/DataConnectors). 
>
>

### <a name="consider-the-source"></a>Überlegungen zur Quelle
Die Abfragen definieren die Daten, die im Datenmodell enthalten sind. Abhängig von der Größe Ihres Systems sollten diese Abfragen auch Filter enthalten, um sicherzustellen, dass Ihre Kunden mit einer überschaubaren Größe arbeiten, die für Ihr Geschäftsszenario geeignet ist.

Power BI-Vorlagen-Apps können mehrere Abfragen parallel und für mehrere Benutzer gleichzeitig ausführen.  Planen Sie Ihre Strategie für die Bandbreitendrosselung und Parallelität im Voraus, und fragen Sie uns, wie Sie Ihre Vorlagen-App fehlertolerant erstellen können.

### <a name="schema-enforcement"></a>Schemaerzwingung
Stellen Sie sicher, dass Ihre Abfragen bei Änderungen im System stabil bleiben. Durch Änderungen am Schema bei der Aktualisierung kann das Modell unterbrochen werden. Wenn die Quelle unter Umständen bei einigen Abfragen ein Nullschema oder ein fehlendes Schema zurückgeben kann, empfiehlt es sich, eine leere Tabelle zurückzugeben oder eine aussagekräftige benutzerdefinierte Fehlermeldung auszugeben.

### <a name="parameters"></a>Parameter
Mit [Parametern](https://powerbi.microsoft.com/blog/deep-dive-into-query-parameters-and-power-bi-templates/) in Power BI Desktop können Benutzer Eingabewerte angeben, mit denen die von den Benutzern abgerufenen Daten angepasst werden. Machen Sie sich vorab Gedanken über die Parameter, und vermeiden Sie so die Nachbearbeitung nach der zeitaufwendigen Erstellung detaillierter Abfragen oder Berichte.

> [!NOTE]
> Vorlagen-Apps unterstützen alle Parameter mit Ausnahme von „Any“ und „Binary“.
>

### <a name="additional-query-tips"></a>Weitere Tipps zu Abfragen

* Stellen Sie sicher, dass alle Spalten richtig angegeben sind.
* Spalten müssen über aussagekräftige Namen verfügen (siehe [Q&A](#qa)).  
* Bei gemeinsam verwendeter Logik empfiehlt sich die Verwendung von Funktionen oder Abfragen.  
* Datenschutzebenen werden im Dienst derzeit nicht unterstützt. Wenn Sie eine Aufforderung zu Datenschutzebenen erhalten, müssen Sie die Abfrage möglicherweise neu schreiben, um relative Pfade zu verwenden.  

## <a name="data-models"></a>Datenmodelle

Durch ein klar definiertes Datenmodell wird sichergestellt, dass Ihre Kunden mühelos und intuitiv mit der Vorlagen-App interagieren können. Erstellen Sie das Datenmodell in Power BI Desktop.

> [!NOTE]
> Ein Großteil der grundlegenden Modellierung (Typisierung, Spaltennamen) sollte in den [Abfragen](#queries) erfolgen.

### <a name="qa"></a>Q&A
Die Modellierung wirkt sich auch darauf aus, inwiefern beim Q&A Ergebnisse für Ihre Kunden bereitgestellt werden können. Stellen Sie sicher, dass Sie für häufig verwendete Spalten Synonyme hinzufügen und dass Sie die Spalten in den [Abfragen](#queries) richtig benannt haben.

### <a name="additional-data-model-tips"></a>Weitere Tipps zum Datenmodell

Stellen Sie sicher, dass Sie:

* auf alle Wertspalten Formatierung angewendet haben. in der Abfrage Typen anwenden.  
* auf alle Measures Formatierung angewendet haben.
* Standardzusammenfassung eingestellt haben. wo zutreffend (z.B. für eindeutige Werte), „Nicht zusammenfassen“ eingestellt haben.  
* wenn zutreffend, Datenkategorie eingestellt haben.  
* nach Bedarf Beziehungen eingestellt haben.  

## <a name="reports"></a>Berichte
Die Berichtseiten bieten zusätzliche Einblicke in die in der Vorlagen-App enthaltenen Daten. Verwenden Sie die Seiten der Berichte, um die wichtigsten unternehmerischen Fragestellungen zu beantworten, auf die mit der Vorlagen-App eingegangen werden soll. Erstellen Sie den Bericht mithilfe von Power BI Desktop.


### <a name="additional-report-tips"></a>Weitere Tipps zu Berichten

* Verwenden Sie mehrere Visuals pro Seite für die Kreuzfilterung.  
* Richten Sie die Visuals sorgfältig aus (keine Überlappungen).  
* Das Layout der Seite ist auf den Modus „4:3“ oder „16:9“ festgelegt.  
* Alle dargestellten Aggregationen sind im Hinblick auf numerische Werte sinnvoll (Mittelwerte, eindeutige Werte).  
* Segmentierungen führen zu vernünftigen Ergebnissen.  
* Das Logo ist mindestens im obersten Bericht vorhanden.  
* Elemente sind weitestgehend im Farbschema des Kunden definiert.  

<a name="dashboard"></a>

## <a name="dashboards"></a>Dashboards
Das Dashboard ist für Ihre Kunden der zentrale Ort der Interaktion mit Ihrer Vorlagen-App. Es sollte eine Übersicht über die Inhalte, insbesondere die wichtigen Metriken Ihres Geschäftsszenarios, enthalten.

Zum Erstellen eines Dashboards für Ihre Vorlagen-App laden Sie einfach Ihre PBIX-Datei über „Daten abrufen“ > „Dateien“ hoch, oder veröffentlichen Sie sie direkt über Power BI Desktop.


### <a name="additional-dashboard-tips"></a>Weitere Tipps zum Dashboard

* Behalten Sie beim Anheften dasselbe Design bei, sodass die Kacheln im Dashboard einheitlich sind.  
* Heften Sie ein Logo an das Design an, damit Kunden wissen, woher das Paket stammt.  
* Als Layout für die meisten Bildschirmauflösungen empfehlen sich fünf bis sechs kleine Kacheln in der Breite.  
* Alle Dashboardkacheln müssen über geeignete Titel bzw. Untertitel verfügen.  
* Ziehen Sie für verschiedene Szenarios vertikale oder horizontale Gruppierungen im Dashboard in Betracht.  

## <a name="sample-data"></a>Beispieldaten
Vorlage-apps als Teil der Phase der Clustererstellung app dient als Wrapper für die Daten im Cache im Rahmen der app-Arbeitsbereich:

* Können Sie das Installationsprogramm die Funktionen und den Zweck der app zu verstehen, bevor die Daten verbinden.
* Erstellt eine Erfahrung, die das Installationsprogramm, Erkunden Sie die app-Funktionen, steuert die führt zum Verbinden der app-Datasets.

Es wird empfohlen, müssen vor dem Erstellen der app Qualität Beispieldaten. Stellen Sie sicher, den Bericht zum app- und -Dashboards werden mit Daten gefüllt.

## <a name="publishing-on-appsource"></a>Veröffentlichen auf AppSource
Vorlage-apps auf AppSource veröffentlicht werden können, befolgen Sie diese Richtlinien vor dem übermitteln der app in AppSource:

* Stellen Sie sicher, erstellen Sie eine Vorlage-app mit Beispieldaten, die helfen können Sie das Installationsprogramm zu verstehen, was die app tun kann ansprechende (leerer Bericht und Dashboard sind nicht genehmigt).
Vorlage-apps unterstützen nur Daten beispielapps, stellen Sie sicher, dass das Kontrollkästchen für die statischen app aktivieren. [Weitere Informationen](https://docs.microsoft.com/power-bi/service-template-apps-create#create-the-test-template-app)
* Haben Sie die Anweisungen für das Team Überprüfung ausführen, darunter Anmeldeinformationen und Parametern, die erforderlich sind, zu Daten herstellen.
* Anwendung muss die App-Symbol in Power BI und in Ihrem Angebot CPP enthalten. [Weitere Informationen](https://docs.microsoft.com/power-bi/service-template-apps-create#create-the-test-template-app)
* Zielseite, die konfiguriert werden. [Weitere Informationen](https://docs.microsoft.com/power-bi/service-template-apps-create#create-the-test-template-app)
* Stellen Sie sicher, dass die Dokumentation, führen auf [Power BI-App-Angebot](https://docs.microsoft.com/azure/marketplace/cloud-partner-portal/power-bi/cpp-power-bi-offer).
* Falls ein Dashboard Teil Ihrer app ist, stellen Sie sicher, dass er nicht leer ist.
* Installieren Sie die app über den app-Link vor der Übermittlung, stellen Sie sicher, Sie können das Dataset eine Verbindung herstellen und die app-Testbenutzeroberfläche ist, wie Sie geplant.
* Stellen Sie vor dem Hochladen Bpix in der Vorlage app-Arbeitsbereich an, Sie sicher, dass keine unnötigen Verbindungen zu entladen.
* Führen Sie die Power BI [Bewährte Entwurfsmethoden für Berichte und Visualisierungen](https://docs.microsoft.com/power-bi/visuals/power-bi-visualization-best-practices) um maximale Auswirkungen auf Ihre Benutzer und erhalten der Genehmigung für die Verteilung zu erzielen.

## <a name="known-limitations"></a>Bekannte Einschränkungen

| Feature | Bekannte Einschränkung |
|---------|---------|
|Inhalt:  Datasets   | Genau ein Dataset sollte vorhanden sein. Nur Datasets, die in Power BI Desktop erstellt wurden (.pbix-Dateien), sind zulässig. <br>Nicht unterstützt: Datasets aus anderen Vorlagen-Apps, arbeitsbereichübergreifende Datasets, paginierte Berichte (.rdl-Dateien), Excel-Arbeitsmappen |
|Inhalt: Dashboards | Real-Time-Kacheln sind nicht zulässig (also keine Unterstützung für Push- oder streamingdatasets) |
|Inhalt: Dataflows | Nicht unterstützt: Dataflows |
|Inhalte aus Dateien | Nur PBIX-Dateien sind zulässig. <br>Nicht unterstützt: .rdl-Dateien (paginierte Berichte), Excel-Arbeitsmappen   |
| Datenquellen | Datenquellen, die für geplante Datenaktualisierungen in der Cloud unterstützt werden, sind zulässig. <br>Nicht unterstützt: <li> DirectQuery</li><li>Liveverbindungen (ausgenommen Azure Analysis Services)</li> <li>Lokale Datenquellen (Personal- und Enterprise-Gateways werden nicht unterstützt)</li> <li>Real-Time (keine Unterstützung für Push-Dataset)</li> <li>Zusammengesetzte Modelle</li></ul> |
| Dataset: arbeitsbereichübergreifend | Arbeitsbereichübergreifende Datasets sind nicht zulässig.  |
| Abfrageparameter | Nicht unterstützt: Parameter vom Typ „Any“ oder „Binary“ blockieren den Aktualisierungsvorgang für Datasets. |
| Benutzerdefinierte visuelle Elemente | Es werden nur öffentlich verfügbare benutzerdefinierte Visuals unterstützt. [Benutzerdefinierte Visuals für Organisationen](power-bi-custom-visuals-organization.md) werden nicht unterstützt. |

## <a name="next-steps"></a>Nächste Schritte

[What are Power BI template apps? (preview) (Was sind Power BI-Vorlagen-Apps? (Vorschauversion))](service-template-apps-overview.md)
