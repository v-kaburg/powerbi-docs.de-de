---
title: 'Paginierte Berichte in Power BI: Häufig gestellte Fragen (FAQ, Vorschau)'
description: Dieser Artikel behandelt häufig gestellte Fragen zu paginierten Berichten. Diese Berichte sind umfassend formatiert und pixelgenau, somit eignet sich ihre Ausgabe ideal zum Drucken und Erstellen von PDFs.
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: report-builder
ms.topic: overview
ms.date: 11/05/2018
ms.openlocfilehash: cedf72585d7aa4f2ece39739dc0bdba33ca66e21
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2019
ms.locfileid: "60987783"
---
# <a name="paginated-reports-in-power-bi-faq-preview"></a>Paginierte Berichte in Power BI: Häufig gestellte Fragen (FAQ, Vorschau)

Dieser Artikel behandelt häufig gestellte Fragen zu paginierten Berichten. Diese Berichte sind umfassend formatiert und pixelgenau, somit eignet sich ihre Ausgabe ideal zum Drucken und Erstellen von PDFs. Sie werden als „paginiert“ bezeichnet, weil sie so formatiert sind, dass sie gut auf mehrere Seiten passen. Paginierte Berichte basieren auf der RDL-Berichtstechnologie von SQL Server Reporting Services (SSRS). 

In diesem Artikel werden viele häufig gestellte Fragen zu paginierten Berichten in Power BI Premium und zum Berichts-Generator beantwortet, dem eigenständigen Tool zum Erstellen von paginierten Berichten. Sie benötigen eine Power BI Pro-Lizenz, um einen Bericht im Dienst zu veröffentlichen. Sie können paginierte Berichte in Ihrem Arbeitsbereich oder in App-Arbeitsbereichen veröffentlichen und freigeben, solange sich der Arbeitsbereich in einer Power BI Premium-Kapazität befindet. 

## <a name="administration"></a>Verwaltung

### <a name="what-size-premium-capacity-do-i-need-for-paginated-reports"></a>Welche Premium-Kapazitätsgröße benötige ich für paginierte Berichte?

Die Workload der paginierten Berichte ist für die SKUs P1–P3 für die Public Preview verfügbar.  Sie können sie auch für Test- und Entwicklungszwecke mit den SKUs A4–A6 verwenden.

### <a name="what-is-the-maximum-memory-threshold-i-can-put-for-paginated-reports-in-my-capacity"></a>Was ist der Maximalwert für den Arbeitsspeicher, den ich in meiner Kapazität für paginierte Berichte festlegen kann?

Derzeit können Sie nur 50 % des Arbeitsspeichers für diese Workload reservieren. 

### <a name="how-does-user-access-work-for-paginated-reports"></a>Wie funktioniert der Benutzerzugriff auf paginierte Berichte?

Der Benutzerzugriff auf paginierte Berichte entspricht dem Benutzerzugriff auf alle anderen Inhalte im Power BI-Dienst. 

### <a name="how-do-i-turn-onoff-my-paginated-reports-workload"></a>Wie aktiviere/deaktiviere ich die Workload paginierter Berichte?

Der Kapazitätsadministrator kann die Workload paginierter Berichte im Portal für Kapazitätsadministratoren aktivieren bzw. deaktivieren.  

### <a name="how-can-i-monitor-usage-of-paginated-reports-in-my-tenant"></a>Wie kann ich die Verwendung von paginierten Berichten in meinem Mandanten überwachen?

Die Office 365-Überwachungsprotokolle vermerken die detaillierte Verwendung dieses Berichtstyps bei folgenden Ereignissen: 

- Anzeigen des Power BI-Berichts
- Löschen des Power BI-Berichts
- Erstellen des Power BI-Berichts
- Downloaded Power BI report (Power BI-Bericht herunterladen)

Das Feld „ReportType“ hat den Wert „PaginatedReport“, um paginierte Berichte von Power BI-Berichten zu unterscheiden.

Darüber hinaus stellen Überwachungsprotokolle die folgenden Ereignisse für paginierte Berichte zur Verfügung:

- Binden von Power BI-Datasets an Gateways
- Untersuchen von Power BI-Datenquellen
- TakeOverDataset

### <a name="can-i-monitor-this-workload-through-the-premium-capacity-monitoring-app"></a>Kann ich diese Workload in der App zum Überwachen der Premium-Kapazität überwachen?

Ja, Überwachung ist als neue Registerkarte mit den gleichen relevanten Details wie für Ihre Power BI-Datasets verfügbar.

### <a name="do-i-need-a-pro-license-to-create-and-publish-paginated-reports"></a>Benötige ich eine Pro-Lizenz, um paginierte Berichte zu erstellen und zu veröffentlichen?

Ja. Ohne Pro-Lizenz können Sie keine Berichte in den Arbeitsbereich hochladen. Wir empfehlen Ihnen, herunterladen und Verwenden von Power BI-Berichts-Generator auch ohne die Pro-Lizenz, aber die gewünschten paginierten Berichte, die Sie, ohne ihn erstellen können nicht veröffentlicht werden. 

### <a name="what-if-i-have-a-paginated-report-in-a-workspace-and-the-paginated-report-workload-is-turned-off"></a>Was geschieht, wenn sich ein paginierter Bericht in einem Arbeitsbereich befindet und die Workload des paginierten Berichts deaktiviert ist?

Sie erhalten eine Fehlermeldung und können Ihren Bericht erst wieder anzeigen, wenn die Workload wieder aktiviert ist. Sie können den Bericht nach wie vor aus dem Arbeitsbereich löschen.

### <a name="what-is-the-default-memory-for-each-of-the-premium-skus-supported-for-paginated-reports"></a>Welcher Standardarbeitsspeicher wird für die jeweilige Premium-SKU für paginierte Berichte unterstützt?

Der Standardarbeitsspeicher der jeweiligen Premium-SKU für paginierte Berichte lautet:

- **P1/A4**: 20 % Standard, mindestens 10 %
- **P2/A5**: 20 % Standard, mindestens 5 %
- **P3/A6**: 20 % Standard, mindestens 2,5 %

## <a name="general"></a>Allgemein

### <a name="when-should-i-use-a-paginated-report-vs-a-power-bi-report"></a>Wofür sollte ich einen paginierten und wofür einen Power BI-Bericht verwenden?

Paginierte Berichte sind die ideal Wahl, wenn Sie eine umfassend formatierte und pixelgenaue Ausgabe für den Druck oder die PDF-Erstellung benötigen.  Ein gutes Beispiel dafür ist eine Gewinn- und Verlustrechnung.  

Power BI-Berichte sind ideal zum Untersuchen und Interagieren.  Ein gutes Beispiel für einen Power BI-Bericht ist beispielsweise ein Vertriebsbericht. Hier können mehrere Vertriebsmitarbeiter die Daten im selben Bericht nach bestimmten Regionen/Branchen/Kunden aufteilen und dann sehen, wie sich die Zahlen verändern.

### <a name="the-documentation-says-power-bi-report-builder-is-the-preferred-authoring-tool-can-i-create-paginated-reports-in-sql-server-data-tools-for-power-bi"></a>Die Dokumentation besagt, dass es sich bei Power BI-Berichts-Generator das bevorzugte authoring Tool ist. Kann ich paginierte Berichte auch mit SQL Server Data Tools für Power BI erstellen?

Ja, doch Power BI ermöglicht das Hochladen von jeweils nur einem einzelnen Element, sodass viele Szenarien, für die Ersteller SQL Server Data Tools (SSDT) verwenden, noch nicht unterstützt werden. Weiter unten finden Sie die vollständige [Liste der nicht unterstützten Funktionen](#what-paginated-report-features-in-ssrs-arent-yet-supported-in-power-bi).  

### <a name="what-versions-of-report-builder-do-you-support"></a>Welche Versionen des Berichts-Generators werden unterstützt?

Wir vor kurzem veröffentlicht, Power BI-Berichts-Generator als primäres authoring Tool für paginierte Berichte im Power BI-Dienst. Installieren Sie [Power BI-Berichts-Generator aus dem Microsoft Download Center](https://go.microsoft.com/fwlink/?linkid=2086513).

### <a name="how-do-i-move-existing-reports-i-have-saved-in-sql-server-reporting-services-to-power-bi"></a>Wie verschiebe ich vorhandene Berichte, die ich in SQL Server Reporting Services gespeichert habe, zu Power BI?

Sie müssen den Bericht vom Server herunterladen und dann über das Portal in Power BI hochladen.  Zurzeit ist kein Migrationstool verfügbar. Allerdings ist die Entwicklung solch eines Tools geplant, nachdem die Public Preview beendet und die optimale Featureparität zwischen den Produkten erreicht wurde.

### <a name="can-i-open-reports-and-publish-directly-to-the-service"></a>Kann ich Berichte öffnen und direkt im Dienst veröffentlichen?

Zurzeit nicht. Wir fügen Unterstützung für das Öffnen von Berichten und deren Veröffentlichung direkt an den Dienst von Power BI-Berichts-Generator vor der allgemeinen Verfügbarkeit, wie Sie mit Power BI Desktop.

### <a name="what-paginated-report-features-in-ssrs-arent-yet-supported-in-power-bi"></a>Welche Funktionen von paginierten Berichten in SSRS werden in Power BI noch nicht unterstützt?

Paginierte Berichte unterstützen derzeit nicht die folgenden Elemente:

- Freigegebene Datenquellen
- Freigegebene Datasets
- Unterberichte
- Klick- und Drillthroughaktionen
- Verknüpfte Berichte
- Lesezeichen
- Bing-Kartenebenen
- Benutzerdefinierte Schriftarten

Sie erhalten eine Fehlermeldung, wenn Sie versuchen, eine Datei hochzuladen, die über eine nicht unterstützte Funktion im Power BI-Dienst verfügt – mit Ausnahme von Umschalten/Sortieren.

### <a name="what-data-sources-do-you-support-currently-for-paginated-reports"></a>Welche Datenquellen werden derzeit für paginierte Berichte unterstützt?

Wir unterstützen die folgende Datenquelle: 

- Power BI-Premium-Datasets
- Azure Analysis Services (über einmaliges Anmelden (SSO))
- Azure SQL-Datenbank
- SQL Server *
- SQL Server Analysis Services (SSAS) tabellarisch (DAX) und MDX (Multidimensional Expressions) Modelle * 
- Oracle * 
- Teradata* 

* ist das lokale Gateway erforderlich.

Beim Zugriff auf SSAS über das Gateway benötigt der Benutzer, dessen Anmeldeinformationen gespeichert sind, erhöhte Berechtigungen in SSAS, um über das Gateway zu arbeiten.

### <a name="what-authentication-methods-do-you-support"></a>Welche Authentifizierungsmethoden werden unterstützt?

Wir unterstützen SSO für Azure Analysis Services und Power BI Premium-Datenquellen.  Für alle anderen Datenquellen müssen Sie derzeit einen Benutzernamen und ein Kennwort mit der Datenquelle in das Portal oder das Gateway zu speichern.  

### <a name="can-i-use-a-power-bi-dataset-as-a-data-source-for-my-paginated-report"></a>Kann ich ein Power BI-Dataset als Datenquelle für meinen paginierten Bericht verwenden?

Ja, unterstützen wir jetzt Power BI Premium-Datasets als Datenquellen für paginierte Berichte.

### <a name="can-i-use-stored-procedures-through-the-gateway"></a>Kann ich gespeicherte Prozeduren über das Gateway verwenden?

Sie können eine gespeicherte Prozedur über das Gateway verwenden, jedoch können in bestimmten Szenarien Probleme auftreten, wenn die gespeicherte Prozedur über Parameter verfügt.

### <a name="what-export-formats-are-available-for-my-report-in-the-power-bi-service"></a>Welche Exportformate sind für meinen Bericht in Power BI verfügbar?

Sie können in Microsoft Excel, Microsoft Word, Microsoft PowerPoint sowie in die Formate PDF, CSV, XML und MHTML exportieren.

### <a name="can-i-print-paginated-reports"></a>Kann ich paginierte Berichte drucken?

Ja, ist die Drucken für paginierte Berichte, einschließlich eine Seitenansicht für neue und verbesserte Oberfläche zur Verfügung. 

### <a name="are-e-mail-subscriptions-available-yet-for-paginated-reports"></a>Sind E-Mail-Abonnements für paginierte Berichte bereits verfügbar?

Nein, E-Mail-Abonnements werden aber in Kürze eingeführt.

### <a name="what-features-from-ssrs-will-you-be-supporting-in-the-power-bi-service"></a>Welche SSRS-Funktionen werden im Power BI-Dienst unterstützt?

Es ist unser Plan, in den meisten Szenarien Gleichstand bei den Funktionen bereitzustellen, jedoch gibt es einige Details bei SSRS und Power BI, die sich nicht sinnvoll auf vorhandene SSRS-Muster abbilden lassen.  Beispielsweise lassen sich die verschiedenen Berechtigungsmodelle in Power BI nicht auf SSRS zurück übertragen.  Wir stützen uns bei Entscheidungen dieser Art auf das Feedback unserer Kunden und Partner.

### <a name="can-i-run-custom-code-in-my-report"></a>Kann ich in meinem Bericht benutzerdefinierten Code ausführen?

Ja, das Ausführen von Code in Berichten wird – wie in SSRS – unterstützt.

### <a name="does-this-mean-ssrs-is-going-away"></a>Bedeutet das, SSRS wird eingestellt?

Ganz und gar nicht.  Das neue Angebot bietet Kunden eine cloudbasierte Option für ihre paginierten Berichte.  

### <a name="can-i-use-power-bi-embedded-to-embed-my-paginated-reports-into-an-app-im-hosting"></a>Kann ich mit Power BI Embedded meine paginierten Berichte in eine App einbetten, die ich hoste?

Die Unterstützung dieses Szenarios mit den vorhandenen Power BI-APIs ist geplant. Allerdings liegt dafür noch kein konkreter Zeitplan vor.

### <a name="can-i-drill-through-from-a-power-bi-report-to-a-paginated-report"></a>Kann ich einen Drillthrough von einem Power BI-Bericht zu einem paginierten Bericht ausführen?

Noch nicht, doch die Einführung dieser Funktion ist geplant.

### <a name="can-i-share-my-paginated-report-content-through-a-power-bi-app"></a>Kann ich Inhalte meines paginierten Berichts mit einer Power BI-App freigeben?

Ja, unterstützt paginierte Berichte sind mit apps in v1- und v2-Arbeitsbereichen bereitgestellt werden. 

### <a name="will-other-report-specific-features-in-power-bi-like-pinning-to-report-tiles-to-dashboards-work-with-paginated-reports"></a>Werden andere berichtsspezifische Funktionen in Power BI, z.B. das Anheften von Berichtskacheln an Dashboards, mit paginierten Berichten funktionieren?

Es ist geplant, dass Berichte so weit wie möglich die gleichen wichtigen Funktionen im Dienst unterstützen.  Obwohl das Erstellungstool sich unterscheidet, ist das Ziel, dass Endbenutzer diesen Bericht einfach als einen weiteren Bericht in ihrer Liste im Portal betrachten. Denn es geht nicht darum, wie der Bericht erstellt wurde, sondern darum, dass die Anforderungen der Benutzer erfüllt werden.  Ein gutes Beispiel für diese Featureparität ist die geplante Kommentarunterstützung. Obwohl sich die Funktionsweise des Features in den Berichten ggf. etwas unterscheidet, können Sie Kommentare in beiden verwenden.

### <a name="is-a-migration-tool-planned-so-ssrs-customers-can-move-their-existing-reports-and-assets-to-power-bi"></a>Ist ein Migrationstool geplant, damit SSRS-Kunden ihre vorhandenen Berichte und Ressourcen nach Power BI verschieben können?

Wir werten zurzeit Optionen für das automatisierte Verschieben von Inhalten zu Power BI aus, diese Funktion wird aber erst nach der allgemeinen Verfügbarkeit erhältlich sein.

### <a name="will-i-ever-be-able-to-create-both-paginated-reports-and-power-bi-reports-in-a-single-authoring-tool"></a>Werde ich jemals sowohl paginierte Berichte als auch Power BI-Berichte in einem einzigen Erstellungstool generieren können?

Möglicherweise.  Wir untersuchen im Moment Möglichkeiten, dieses Szenario zu unterstützen. Alternativ könnten wir die Erstellungstools gemeinsam als einzelne BI-Suite verteilen, statt sie als individuelle Downloads/Brandings anzubieten.

### <a name="is-there-a-report-viewer-control-for-paginated-reports-in-the-power-bi-service"></a>Gibt es in Power BI ein Berichtanzeige-Steuerelement für paginierte Berichte?

Nein, derzeit ist kein Berichtanzeige-Steuerelement verfügbar.

### <a name="can-you-search-for-paginated-reports-from-the-new-home-experience-in-the-power-bi-service"></a>Kann ich auf der neuen Power BI-Startseite nach paginierten Berichten suchen?

Nein, Sie können auf der Startseite derzeit nicht nach Ihren paginierten Berichten suchen.  Sie werden jedoch in anderen Bereichen der neuen Startseite angezeigt.

## <a name="next-steps"></a>Nächste Schritte

- [Installieren von Power BI-Berichts-Generator aus dem Microsoft Download Center](https://go.microsoft.com/fwlink/?linkid=2086513)
- [Tutorial: Erstellen eines paginierten Berichts](paginated-reports-quickstart-aw.md)
