---
title: Inkrementelle Aktualisierung in Power BI Premium
description: Erfahren Sie, wie Sie im Power BI Premium-Dienst sehr große Datasets unterstützen können.
author: christianwade
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-admin
ms.topic: conceptual
ms.date: 04/30/2018
ms.author: chwade
LocalizationGroup: Premium
ms.openlocfilehash: 1b6a3c35abeff33e2fb1e0fecdc5c2a5c88e1530
ms.sourcegitcommit: 2a7bbb1fa24a49d2278a90cb0c4be543d7267bda
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2018
ms.locfileid: "34298180"
---
# <a name="incremental-refresh-in-power-bi-premium"></a>Inkrementelle Aktualisierung in Power BI Premium

Die inkrementelle Aktualisierung bietet im Power BI Premium-Dienst für sehr große Datasets die folgenden Vorteile:

- **Aktualisierungen erfolgen schneller.** Nur Daten, die geändert wurde, müssen aktualisiert werden. Aktualisieren Sie beispielsweise nur die letzten 5 Tage eines 10 Jahre alten Datasets.

- **Aktualisierungen sind zuverlässiger.** Es ist beispielsweise nicht notwendig, langanhaltende Verbindungen mit flüchtigen Quellsystemen aufrechtzuerhalten.

- **Der Ressourcenverbrauch wird reduziert.** Dank weniger zu aktualisierender Daten wird der Gesamtbedarf an Arbeitsspeicher und anderen Ressourcen reduziert.

## <a name="how-to-use-incremental-refresh"></a>Verwenden der inkrementellen Aktualisierung

Die Richtlinien für die inkrementelle Aktualisierung werden in Power BI Desktop definiert und nach Veröffentlichung auf den Power BI-Dienst angewendet.

Starten Sie mit dem Aktivieren der inkrementellen Aktualisierung in der Vorschauversion.

![Optionen in der Vorschauversion](media/service-premium-incremental-refresh/preview-features.png)

### <a name="filter-large-datasets-in-power-bi-desktop"></a>Filtern großer Datasets in Power BI Desktop

Große Datasets mit potenziell Milliarden von Zeilen werden möglicherweise von Power BI Desktop nicht unterstützt, da das Programm in der Regel durch die auf dem Desktop-PC des Benutzers verfügbaren Ressourcen begrenzt wird. Solche Datensätze werden daher üblicherweise beim Import gefiltert, um von Power BI Desktop unterstützt zu werden. Dies ist weiterhin auch dann der Fall, wenn Sie die inkrementelle Aktualisierung verwenden oder nicht.

#### <a name="rangestart-and-rangeend-parameters"></a>Die Parameter „RangeStart“ und „RangeEnd“

Um die inkrementelle Aktualisierung im Power BI-Dienst zu nutzen, muss die Filterung unter Verwendung von Datums- und Uhrzeitparametern von Power Query mit den reservierten Namen **RangeStart** und **RangeEnd** mit Berücksichtigung von Groß- und Kleinschreibung erfolgen.

Wählen Sie im Power Query-Editor **Parameter verwalten** aus, um die Parameter mit Standardwerten zu definieren.

![Parameter verwalten](media/service-premium-incremental-refresh/manage-parameters.png)

Nach der Definition der Parameter können Sie den Filter anwenden, indem Sie für eine Spalte den Menüpunkt **Benutzerdefinierter Filter** auswählen.

![Benutzerdefinierter Filter](media/service-premium-incremental-refresh/custom-filter.png)

Stellen Sie sicher, dass Zeilen gefiltert werden, bei denen der Spaltenwert *nach oder gleich* **RangeStart** und *vor* **RangeEnd** ist.

![Zeilen filtern](media/service-premium-incremental-refresh/filter-rows.png)

> [!TIP]
> Zwar muss der Datentyp der Parameter „Datum/Uhrzeit“ sein, aber es ist möglich, sie an die Anforderungen der Datenquelle anzupassen. Beispielsweise konvertiert die folgende Power Query-Funktion einen Datums-/Uhrzeitwert als ganze Zahl in einen Ersatzschlüssel der Form *JJJJMMDD*, die für Data Warehouses üblich ist. Die Funktion kann vom Filterschritt aufgerufen werden.
>
> `(x as datetime) => Date.Year(x)*10000 + Date.Month(x)*100 + Date.Day(x)`

Wählen Sie im Power Query-Editor **Schließen und übernehmen** aus. Eine Teilmenge des Datasets sollte in Power BI Desktop vorhanden sein.

> [!NOTE]
> Nach Veröffentlichung werden die Parameterwerte vom BI-Dienst automatisch überschrieben. Sie müssen nicht in den Dataseteinstellungen festgelegt werden.

### <a name="define-the-refresh-policy"></a>Definieren der Aktualisierungsrichtlinie

Die inkrementelle Aktualisierung ist mit Ausnahme von Liveverbindungsmodellen im Kontextmenü für Tabellen verfügbar.

![Aktualisierungsrichtlinie](media/service-premium-incremental-refresh/refresh-policy.png)

#### <a name="incremental-refresh-dialog"></a>Dialogfeld „Inkrementelle Aktualisierung“

Das Dialogfeld „Inkrementelle Aktualisierung“ wird angezeigt. Aktivieren Sie das Dialogfeld mithilfe der Umschaltfläche.

![Details zur Aktualisierung](media/service-premium-incremental-refresh/refresh-details.png)

> [!NOTE]
> Wenn sich der Power Query-Ausdruck für die Tabelle nicht auf die Parameter mit reservierten Namen bezieht, ist die Umschaltmöglichkeit deaktiviert.

Im Text der Kopfzeile wird Folgendes erläutert:

-   Die inkrementelle Aktualisierung wird nur für Arbeitsbereiche mit Premium-Kapazität unterstützt. Aktualisierungsrichtlinien werden in Power BI Desktop definiert und über Aktualisierungsvorgänge im Dienst angewendet.

-   Wenn Sie die PBIX-Datei mit einer enthaltenen inkrementellen Aktualisierungsrichtlinie aus dem Power BI-Dienst herunterladen können, wird sie nicht in Power BI Desktop geöffnet. Sie werden sie in Kürze überhaupt nicht mehr herunterladen können. Auch wenn dies in Zukunft möglicherweise unterstützt wird, denken Sie daran, dass diese Datasets so groß werden können, dass sie nicht mehr heruntergeladen und auf einem typischen Desktop-PC geöffnet werden können.

#### <a name="refresh-ranges"></a>Aktualisierungsbereiche

Im folgenden Beispiel wird eine Aktualisierungsrichtlinie definiert, gemäß der Daten der letzten 5 Jahre gespeichert und Daten der letzten 10 Tage inkrementell aktualisiert werden. Wenn das Dataset täglich aktualisiert wird, werden die folgenden Schritte beim jedem Aktualisierungsvorgang durchgeführt.

-   Die Daten eines neuen Tages werden hinzugefügt.

-   Daten der letzten 10 Tage bis zum aktuellen Datum werden aktualisiert.

-   Kalenderjahre, die bezogen auf das aktuelle Datum älter als 5 Jahre sind, werden entfernt. Wenn das aktuelle Datum der 1. Januar 2019 ist, wird z.B. das Jahr 2013 entfernt.

Die erste Aktualisierung im Power BI-Dienst kann länger dauern, da alle 5 Jahre importiert werden. Nachfolgende Aktualisierungen werden möglicherweise in einem Bruchteil der Zeit abgeschlossen.

![Aktualisierungsbereiche](media/service-premium-incremental-refresh/refresh-ranges.png)

**Die Definition dieser Bereiche reicht ggf. schon aus. In diesem Fall können Sie direkt zum folgenden Veröffentlichungsschritt übergehen. Die zusätzlichen Dropdownlisten sind für erweiterte Funktionen vorgesehen.**

#### <a name="detect-data-changes"></a>Erkennen von Datenänderungen

Eine inkrementelle Aktualisierung der Daten von 10 Tagen ist naturgemäß viel effizienter als eine vollständige Aktualisierung von 5 Jahren. Aber möglicherweise geht es noch besser. Wenn Sie das Kontrollkästchen **Datenänderungen erkennen** aktivieren, können Sie eine Datum-/Uhrzeit-Spalte auswählen, um nur die Tage zu bestimmen und zu aktualisieren, an denen sich die Daten geändert haben. Dies setzt voraus, dass eine solche Spalte im Quellsystem vorhanden ist, die typischerweise zu Prüfzwecken dient. Der Maximalwert dieser Spalte wird für jeden der Zeiträume im Inkrementbereich ausgewertet. Wenn sie sich seit der letzten Aktualisierung nicht geändert hat, muss der Zeitraum nicht aktualisiert werden. Im Beispiel kann dies die Anzahl der Tage, die inkrementell aktualisiert werden, von 10 auf vielleicht 2 weiter verringern.

![Änderungen erkennen](media/service-premium-incremental-refresh/detect-changes.png)

> [!TIP]
> Das aktuelle Design erfordert, dass die Spalte zur Erkennung von Datenänderungen beibehalten und im Arbeitsspeicher zwischengespeichert wird. Sie können eine der folgenden Techniken in Betracht ziehen, um die Kardinalität und den Arbeitsspeicherbedarf zu reduzieren.
>
> Behalten Sie nur den Maximalwert dieser Spalte zum Zeitpunkt der Aktualisierung bei, eventuell mithilfe einer Power Query-Funktion.
>
> Reduzieren Sie die Genauigkeit auf ein Niveau, das angesichts Ihrer Anforderungen an die Aktualisierungsfrequenz vertretbar ist.
>
> Wir planen, die Definition benutzerdefinierter Abfragen zur Erkennung von Datenänderungen zu einem späteren Zeitpunkt zu ermöglichen. Dies könnte dazu dienen, das Beibehalten des Spaltenwerts ganz zu vermeiden.

#### <a name="only-refresh-complete-periods"></a>Nur vollständige Zeiträume aktualisieren

Angenommen, Ihre Aktualisierung ist für 4:00 Uhr morgens geplant. Wenn während dieser 4 Stunden Daten im Quellsystem auftauchen, möchten Sie diese möglicherweise nicht berücksichtigen. Einige betriebswirtschaftliche Metriken – wie Fässer pro Tag in der Öl- und Gasindustrie – ergeben bei Teiltagen keinen Sinn.

Ein weiteres Beispiel ist das Aktualisieren von Daten in einem Finanzsystem, bei dem die Daten des Vormonats am 12. Kalendertag des Monats freigegeben werden. Legen Sie in diesem Fall den Inkrementbereich auf 1 Monat fest, und planen Sie die Aktualisierung für den 12. Tag des Monats. Wenn diese Option aktiviert ist, werden z.B. die Daten vom Januar am 12. Februar aktualisiert.

![Vollständige Zeiträume](media/service-premium-incremental-refresh/complete-periods.png)

> [!NOTE]
> Aktualisierungsvorgänge im Dienst erfolgen gemäß der UTC-Zeit. Dies kann den Stichtag bestimmen und sich auf ganze Zeiträume auswirken. Wir planen, die Möglichkeit hinzuzufügen, den Stichtag für eine Aktualisierung zu überschreiben.

## <a name="publish-to-the-service"></a>Veröffentlichen im Dienst

Da die inkrementelle Aktualisierung eine ausschließliche Premium-Funktion ist, ermöglicht das Dialogfeld „Veröffentlichen“ nur die Auswahl eines Arbeitsbereichs mit Premium-Kapazität.

![Veröffentlichen im Dienst](media/service-premium-incremental-refresh/publish.png)

Sie können das Modell nun aktualisieren. Die erste Aktualisierung kann aufgrund des Imports der Verlaufsdaten länger dauern. Nachfolgende Aktualisierungen sind wesentlich schneller, da sie inkrementell erfolgen.

## <a name="query-timeouts"></a>Zeitüberschreitungen bei Abfragen

Im Artikel [Problembehandlung bei Aktualisierungsszenarios](https://docs.microsoft.com/power-bi/refresh-troubleshooting-refresh-scenarios) wird erklärt, dass es bei Aktualisierungsvorgängen im Power BI-Dienst zu Zeitüberschreitungen kommt. Abfragen können auch durch die standardmäßige Zeitüberschreitung für die Datenquelle eingeschränkt werden. Die meisten relationalen Datenquellen erlauben das Überschreiben von Zeitüberschreitungen im Ausdruck „M“. Zum Beispiel wird im folgenden Ausdruck die [SQL Server-Datenzugriffsfunktion](https://msdn.microsoft.com/query-bi/m/sql-database) verwendet, um sie auf 2 Stunden festzulegen. Jeder durch die Richtlinienbereiche definierte Zeitraum sendet eine Abfrage unter Einhaltung der Einstellung für die Befehlszeitüberschreitung.

```
let
    Source = Sql.Database("myserver.database.windows.net", "AdventureWorks", [CommandTimeout=#duration(0, 2, 0, 0)]),
    dbo_Fact = Source{[Schema="dbo",Item="FactInternetSales"]}[Data],
    #"Filtered Rows" = Table.SelectRows(dbo_Fact, each [OrderDate] >= RangeStart and [OrderDate] < RangeEnd)
in
    #"Filtered Rows"
```
