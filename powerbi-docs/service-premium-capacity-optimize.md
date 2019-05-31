---
title: Optimieren von Microsoft Power BI Premium-Kapazitäten
description: Beschreibt Optimierungsstrategien für die für Power BI Premium-Kapazitäten.
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 04/09/2019
ms.custom: seodec18
LocalizationGroup: Premium
ms.openlocfilehash: 06712b6bcf57ca84ec03d2c7b99b32ea61ad8c71
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2019
ms.locfileid: "65565329"
---
# <a name="optimizing-premium-capacities"></a>Optimieren der Premium-Kapazitäten

Beim Premium-Kapazität Leistungsprobleme auftreten, werden eine gängige Methode für die erste Optimierung oder optimieren Ihre Lösungen zum Wiederherstellen von zulässigen Antwortzeiten. Der Grund, um zu vermeiden, erwerben zusätzlichen Premium-Kapazität, es sei denn, im Blocksatz ausgerichtet werden.

Wenn zusätzlicher Premium-Kapazität erforderlich ist, stehen Ihnen zwei Optionen, die in diesem Artikel beschrieben:

- Zentrales hochskalieren einer vorhandenen Premium-Kapazität
- Hinzufügen einer neuen Premium-Kapazität

Schließlich testen Ansätze und Premium-Kapazitäten, schließen Sie in diesem Artikel.

## <a name="best-practices"></a>Bewährte Methoden

Beim Versuch, die optimale Auslastung und Leistung zu erhalten, gibt es einige empfohlenen bewährten Methoden, einschließlich:

- Verwenden app-Arbeitsbereiche, anstelle der persönlichen Arbeitsbereiche.
- Trennen geschäftskritische und Self-Service-BI (SSBI) direkt in verschiedenen Kapazitäten an.

  ![Aufteilen von unternehmenskritisch und Self-Service-BI in verschiedenen Kapazitäten](media/service-premium-capacity-optimize/separate-capacities.png)

- Wenn die Freigabe von Inhalten nur mit Power BI Pro-Benutzer möglicherweise nicht erforderlich, um den Inhalt in einer dedizierten Kapazität zu speichern.
- Verwenden Sie dedizierte Kapazität, bei der Suche um eine bestimmte Aktualisierungszeit zu erreichen, oder wenn bestimmte Features erforderlich sind. Z. B. mit großen Datasets oder paginierten reporting.

### <a name="addressing-common-questions"></a>Allgemeine Fragen

Optimieren der Power BI Premium-Bereitstellungen ist ein komplexes Thema, die einen Überblick über die für die arbeitsauslastung verfügbaren Ressourcen und deren effektive Verwendung betreffen.

Dieser Artikel enthält sieben häufig gestellte Fragen, beschreiben mögliche Probleme und Beschreibungen und Informationen zum Identifizieren und beheben Sie diese.

### <a name="why-is-the-capacity-slow-and-what-can-i-do"></a>Warum ist die Kapazität, die langsam, und was kann ich tun?

Es gibt viele Gründe, die zu einer langsamen Premium-Kapazität beitragen können. Diese Frage erfordert Weitere Informationen zu verstehen, was mit langsamen gemeint ist. Sind Berichte langsam geladen? Oder werden sie nicht geladen werden? Sind Sie berichtsvisuals langsam geladen oder aktualisiert werden, wenn der Benutzer mit dem Bericht interagieren? Werden aktualisiert, dauert länger als erwartet wird, oder bereits aufgetreten ist?

Müssen erhielten einen Überblick über den Grund, können Sie anschließend beginnen, zu untersuchen. Antworten auf die folgenden sechs Fragen helfen Ihnen, mehr zu adressieren bestimmter Probleme.

### <a name="what-content-is-using-up-my-capacity"></a>Welche Inhalte wird meine Kapazität verwenden?

Sie können der **Kapazitätsmetriken für Power BI Premium** app zum Filtern von Kapazität und überprüfen die Leistungsmetriken für den Inhalt des Arbeitsbereichs. Es ist möglich, überprüfen die Leistung Metriken und die ressourcennutzung pro Stunde für die letzten sieben Tage für den gesamten Inhalt in einer Premium-Kapazität gespeichert. Überwachung ist häufig der erste Schritt bei der Problembehandlung für eine allgemeine Angelegenheiten handelt, zur Leistung für Premium-Kapazität.

Wichtige zu überwachende Metriken umfassen:

- Durchschnittliche CPU-Nutzung und hohe Auslastung Anzahl.
- Die durchschnittliche Arbeitsspeicher und Anzahl der hohe Auslastung und speicherauslastung für bestimmte Datasets, Datenflüsse und paginierten Berichte.
- Aktiver Datasets, die in den Arbeitsspeicher geladen werden.
- Durchschnittliche und maximale abfragedauern.
- Durchschnittliche abfragewartezeiten.
- Durchschnittliche Dataset und den Datenfluss aktualisieren Zeiten auf.

In der Kapazitätsmetriken für Power BI Premium-app zeigt aktiven Arbeitsspeichers den gesamten Arbeitsspeicher für einen Bericht, der innerhalb der letzten drei Minuten wurde nicht entfernt werden kann. Eine hohe Spitze in der Wartezeit für die Aktualisierung konnte mit einem großen und/oder sehr aktiven Dataset korreliert werden.

Die **Top 5 nach Durchschnittlicher Dauer** Diagramm hervorgehoben, die fünf wichtigsten Datasets, paginierte Berichte und Datenflüsse kapazitätsressourcen verbrauchen. Inhalte in den oberen fünf Listen ist die Kandidaten für die Untersuchung und mögliche Optimierung.

### <a name="why-are-reports-slow"></a>Warum Berichte sind langsam?

Die folgenden Tabellen zeigen mögliche Probleme sowie Möglichkeiten zu identifizieren und behandeln.

#### <a name="insufficient-capacity-resources"></a>Nicht genügend Kapazität-Ressourcen

| Mögliche Erklärungen | Identifizieren von | Gewusst wie: Auflösen |
| --- | --- | --- |
| Hohe active Gesamtspeicher (Modell kann nicht entfernt werden, weil es innerhalb der letzten drei Minuten verwendet wird).<br><br> Mehrere hohe Spitzen in der Abfrage Wartezeiten.<br><br> Mehrere hohe Spitzen bei der Aktualisierung Wartezeiten. | Überwachen von Metriken zum Arbeitsspeicher \[ [1](#endnote-1)\], und der Anzahl der Entfernung \[ [2](#endnote-2)\]. | Verringern der Größe des Datenbankmodells oder DirectQuery-Modus konvertieren. Finden Sie unter den [optimieren Datenmodellen](#optimizing-models) Abschnitt in diesem Artikel.<br><br> Zentrales hochskalieren der Kapazitätsbedarfs.<br><br> Weisen Sie den Inhalt einer anderen Kapazität. |

#### <a name="inefficient-report-designs"></a>Ineffiziente Berichtsentwürfe

| Mögliche Erklärungen | Identifizieren von | Gewusst wie: Auflösen |
| --- | --- | --- |
| Seiten des Berichts enthält zu viele Visualisierungen, die (interaktive Filterung kann mindestens eine Abfrage pro visuellem auszulösen).<br><br> Visuelle Elemente abgerufen werden mehr Daten als nötig. | Überprüfen Sie die Berichtsentwürfe.<br><br> Befragen Sie berichtsbenutzer, um zu verstehen, wie sie mit den Berichten interagieren.<br><br> Überwachen von Dataset-abfragemetriken \[ [3](#endnote-3)\]. | Neuentwurf von Berichten mit weniger Visualisierungen pro Seite. |

#### <a name="dataset-is-slow-especially-when-reports-have-previously-performed-well"></a>DataSet ist langsam, insbesondere, wenn Berichte auch zuvor ausgeführt haben

| Mögliche Erklärungen | Identifizieren von | Gewusst wie: Auflösen |
| --- | --- | --- |
| Zunehmend große Mengen an Daten importieren.<br><br> Komplexen oder ineffizienten Berechnungslogik, einschließlich der RLS-Rollen.<br><br> Das Modell nicht vollständig optimiert.<br><br> (DQ/LC) Gateway-Latenz.<br><br> Langsame DQ Quelle Antwortzeiten für Abfragen. | Überprüfen Sie die Modell-Entwürfe.<br><br> Überwachen Sie die Gateway-Leistungsindikatoren. | Finden Sie unter den [optimieren Datenmodellen](#optimizing-models) Abschnitt in diesem Artikel. |

#### <a name="high-concurrent-report-usage"></a>Hohe gleichzeitige Berichte zur Nutzung

| Mögliche Erklärungen | Identifizieren von | Gewusst wie: Auflösen |
| --- | --- | --- |
| Hohe abfragewartezeiten.<br><br> Die CPU-Auslastung.<br><br> DQ/LC verbindungsbeschränkungen überschritten. | Überwachen der CPU-Auslastung \[ [4](#endnote-4)\], abfragewartezeiten und DQ/LC Auslastung \[ [5](#endnote-5) \] Metriken + Dauer der Abfrage. Wenn schwankt, kann von Parallelitätsproblemen angeben. | Zentrales hochskalieren der Kapazitätsbedarfs, oder weisen Sie den Inhalt einer anderen Kapazität.<br><br> Neuentwurf von Berichten mit weniger Visualisierungen pro Seite. |

**Anmerkungen zu dieser Version:**    
<a name="endnote-1"></a>\[1\] durchschnittliche Speicherauslastung (GB) und höchste Arbeitsspeichernutzung (GB).   
<a name="endnote-2"></a>\[2\] Dataset entfernungen.   
<a name="endnote-3"></a>\[3\] Datasetabfragen, Dataset durchschnittliche Abfragedauer (ms), Datasets zu warten, Anzahl und Durchschnitt von Dataset-Wartezeit (ms).   
<a name="endnote-4"></a>\[4\] Anzahl von hoher CPU-Auslastung und CPU-Zeit der höchsten Auslastung (in den letzten sieben Tage).   
<a name="endnote-5"></a>\[5\] DQ/LC hohe Auslastung Anzahl und den DQ/LC-Zeitpunkt der höchsten Auslastung (in den letzten sieben Tage).   

### <a name="why-are-reports-not-loading"></a>Warum Berichte werden nicht geladen?

Wenn Berichte nicht geladen werden, ist es ein sicheres Zeichen, die Kapazität hat nicht genügend Arbeitsspeicher und zu auseinandersetzungen ist. Dies kann auftreten, wenn alle geladenen Modelle sind aktiv, die abgefragt wird, und können nicht entfernt werden, und alle Aktualisierungsvorgänge wurde angehalten oder verzögert wird. Power BI-Dienst versucht, laden das Dataset für 30 Sekunden, und der Benutzer ist der Fehler mit der eine Empfehlung, versuchen es in Kürze ordnungsgemäß benachrichtigt.

Es gibt derzeit keine Metrik für den Bericht von Ladefehlern überwachen. Sie können das Potenzial für dieses Problem durch Überwachung Systemspeicher, insbesondere der höchsten Auslastung und die Uhrzeit der höchsten Auslastung ermitteln. Hohe Dataset entfernungen und lange Dataset Aktualisierung durchschnittliche Wartezeit konnte wird empfohlen, dieses Problem auftritt.

In diesem nur sehr selten der Fall ist, kann dies nicht Prioritäten betrachtet werden. Benutzer des Berichts werden darüber informiert, dass der Dienst ausgelastet ist und, dass sie nach kurzer Zeit wiederholt werden soll. In diesem zu häufig der Fall ist, kann das Problem durch zentrale Skalierung der Premium-Kapazität oder durch Zuweisen des Inhalts einer anderen Kapazität aufgelöst werden.

Capacity Admins (und Power BI-Dienstadministratoren) können überwachen, die **Abfragefehlern** Metrik, um zu bestimmen, wenn dies geschieht. Sie können auch die Kapazität, die alle Vorgänge bei einem System Überladung zurücksetzen neu starten.

### <a name="why-are-refreshes-not-starting-on-schedule"></a>Warum werden die Aktualisierungen nicht nach Zeitplan gestartet?

Startzeiten der geplanten Aktualisierung sind nicht garantiert. Denken Sie daran, dass es sich bei Power BI-Dienst immer interaktive Vorgänge über Hintergrundvorgänge priorisieren wird. Datenaktualisierung ist eine Hintergrundoperation, die auftreten können, wenn zwei Bedingungen erfüllt sind:

- Ausreichend Arbeitsspeicher ist verfügbar
- Die Anzahl der unterstützten gleichzeitige Aktualisierungen für die Premium-Kapazität wurde nicht überschritten.

Wenn die Bedingungen nicht erfüllt sind, wird die Aktualisierung in die Warteschlange, bis die Bedingungen günstig sind.

Eine vollständige Aktualisierung Denken Sie daran, dass mindestens doppelt die aktuellen Dataset Arbeitsspeichergröße erforderlich ist. Wenn nicht genügend Arbeitsspeicher verfügbar ist, kann nicht die Aktualisierung beginnen, bis Modell Entfernung gibt Speicherplatz frei – Dies verzögert, bedeutet bis ein oder mehrere Datasets inaktiv und entfernt werden kann.

Denken Sie daran, dass die unterstützte Anzahl von maximalen gleichzeitigen Aktualisierungen 1,5 Mal die Back-End-V-Kerne, aufgerundet festgelegt ist.

Eine geplante Aktualisierung schlägt fehl, wenn er beginnen kann nicht vor die nächste geplante Aktualisierung aufgrund von zu beginnen. Eine bedarfsgesteuerte Aktualisierung manuell ausgelöst werden, über die Benutzeroberfläche versucht, die bis zu drei Mal ausführen, bevor ein Fehler auftritt.

Capacity Admins (und Power BI-Dienstadministratoren) können überwachen, die **durchschnittliche aktualisieren Wartezeit (Minuten)** Metrik für die durchschnittliche Verzögerung zwischen dem geplanten Zeitpunkt und dem Beginn des Vorgangs zu ermitteln.

Während eine administrative Priorität für die beeinflussen, in-Time-Daten in der Regel nicht aktualisiert werden soll, stellen Sie sicher, dass genügend Arbeitsspeicher verfügbar ist. Dies kann beinhalten, Datasets, auf die Kapazitäten, die mit bekannten genügend Ressourcen zu isolieren. Es ist auch möglich, dass Administratoren mit dem Besitzer von Datasets koordinieren konnte können staffeln, oder verringern Sie die geplante Aktualisierungen auf Zeiten, Konflikte zu minimieren. Beachten Sie, dass es nicht möglich, dass ein Administrator die Warteschlange für die Aktualisierung anzeigen oder zum Abrufen von Datasets plant.

### <a name="why-are-refreshes-slow"></a>Warum werden aktualisiert, die langsam?

Aktualisierungen kann slow- oder wahrgenommene langsam ist (wie die vorherige Frage Adressen allgemeine) sein.

Wenn die Aktualisierung in der Tat langsam ist, kann es verschiedene Ursachen sein:

- Unzureichende CPU (Aktualisierung kann sehr CPU-intensiv sein).
- Nicht genügend Arbeitsspeicher, sodass Aktualisierung anhalten (erfordert die Aktualisierung beginnen, wenn Bedingungen neu beginnen müssen günstig sind).
- Nicht-Kapazität Gründe, z. B. Datasource Reaktionsfähigkeit des Systems, Netzwerklatenz, ungültige Berechtigungen oder Gateway-Durchsatz.
- Datenvolume – ein guter Grund so konfigurieren Sie inkrementelle zu aktualisieren, wie im folgenden erläutert.

Capacity Admins (und Power BI-Dienstadministratoren) können überwachen, die **durchschnittliche aktualisieren Dauer (Minuten)** Metrik, um zu bestimmen, eine Benchmark für den Vergleich im Laufe der Zeit und die **durchschnittliche aktualisieren Wartezeit (Minuten)** Metriken, um zu bestimmen, Durchschnittliche Verzögerung zwischen den Durchschnittliche Verzögerung zwischen dem geplanten Zeitpunkt und dem Beginn des Vorgangs.

Die inkrementelle Aktualisierung kann die Dauer des Daten aktualisieren, insbesondere bei großen Modelltabellen deutlich reduzieren. Es gibt vier Vorteile, die inkrementelle Aktualisierung zugeordnet:

- **Aktualisierungen sind schneller** – nur eine Teilmenge einer Tabelle benötigt, laden, verringern Auslastung von CPU und Arbeitsspeicher und Parallelität kann höher sein, wenn Sie mehrere Partitionen zu aktualisieren.
- **Aktualisierungen auftreten, nur im Bedarfsfall** -Richtlinien für die inkrementelle Aktualisierung können so konfiguriert werden, dass Laden nur, wenn Daten geändert haben.
- **Aktualisierungen sind zuverlässiger** -kürzere ausgeführte Verbindungen mit flüchtigen Datasource-Systeme sind weniger anfällig für die Trennung der Verbindung.
- **Modelle bleiben trim** -Richtlinien für die inkrementelle Aktualisierung können konfiguriert werden, um automatisch Verlauf über ein gleitendes Fenster von Zeit zu entfernen.

Weitere Informationen finden Sie unter [inkrementell zu aktualisieren, klicken Sie in Power BI Premium](service-premium-incremental-refresh.md).

### <a name="why-are-data-refreshes-not-completing"></a>Warum Daten werden aktualisiert, nicht abgeschlossen?

Wenn die datenaktualisierung beginnt, aber es kann nicht abgeschlossen werden, kann es verschiedene Ursachen sein:

- Unzureichender Arbeitsspeicher, auch wenn es nur ein Modell in der Premium-Kapazität ist z. B. die Größe des Datenbankmodells sehr groß.
- Nicht-Kapazitätsgründen, z. B. Datasource System trennen, ungültige Berechtigungen oder Gatewayfehler.

Capacity Admins (und Power BI-Dienstadministratoren) können überwachen, die **Aktualisieren von Fehlern aufgrund von nicht genügend Arbeitsspeicher** Metrik.

## <a name="optimizing-models"></a>Optimieren von Modellen

Optimale Modellentwurf ist entscheidend für die Bereitstellung einer effizienten und skalierbare Lösung. Es ist jedoch Gegenstand dieser Artikel soll Ihnen eine detaillierte Erläuterung zu. Stattdessen wird in diesem Abschnitt wichtige Bereiche berücksichtigt bereitstellen, der beim Optimieren der Modelle.

### <a name="optimizing-power-bi-hosted-models"></a>Optimieren von Power BI gehosteten Modelle

Optimieren von Modellen, die in einer Premium-Kapazität gehostet, kann auf Datenquellen und Modell erreicht werden.

Beachten Sie die optimierungsmöglichkeiten für ein Modell importieren:

![Optimierungsmöglichkeiten für ein Modell importieren](media/service-premium-capacity-optimize/import-model-optimizations.png)

Auf der Datasource-Ebene:

- Relationale Datenquellen um sicherzustellen, dass die schnellste Möglichkeit Aktualisierung mithilfe der vorab Integrieren von Daten, Anwenden der geeigneten Indizes, Tabellenpartitionen, die ausgerichtet sind für die inkrementelle Aktualisierung Zeiträume definieren und Umsetzung von Berechnungen optimiert werden können (anstelle von berechnet Model-Tabellen und Spalten) oder zum Hinzufügen von Berechnungslogik zu Sichten.
- Nicht relationale Datenquellen können in relationale Speicher integriert werden.
- Sicherstellen Sie, dass Gateways ausreichende Ressourcen, vorzugsweise auf dedizierten Computern, die mit genügend Netzwerkbandbreite und in der Nähe zu den Datenquellen.

Auf der Modellebene:

- Power Query-Abfrage Entwürfe minimieren oder entfernen Sie komplexe Transformationen und insbesondere über diejenigen, die verschiedene Datenquellen (Datawarehouses dies erreichen, während ihre extrahieren-transformieren-laden-Phase) zusammenführen können. Darüber hinaus sicherstellen, entsprechende Datasource datenschutzebenen festgelegt werden, dies kann vermeiden, dass Power BI beim Laden der vollständigen Ergebnisse, um ein kombiniertes Ergebnis über mehrere Abfragen zu erstellen.
- Die Modellstruktur bestimmt die zu ladenden Daten und wirkt sich direkt auf die Größe des Datenbankmodells. Es kann entworfen werden, um zu vermeiden, laden überflüssige Daten durch Entfernen von Spalten, und Entfernen von Zeilen (vor allem historischen Daten) oder durch das Laden von zusammengefasster Daten (auf Kosten der detaillierte Daten wird geladen). Erhebliche Reduzierung kann erreicht werden, durch das Entfernen von Spalten mit hoher Kardinalität (insbesondere Textspalten), die nicht speichern oder sehr effizient komprimieren.
- Modell die abfrageleistung kann verbessert werden, durch Konfigurieren von Richtung Beziehungen, es sei denn, es gibt ein zwingenden Grund bidirektionales filtern können. Berücksichtigen Sie auch mithilfe der [CROSSFILTER](https://docs.microsoft.com/dax/crossfilter-function) Funktion statt bidirektionales filtern.
- Aggregationstabellen können schnelle Abfragen, dass Antworten durch das Laden von Daten zusammengefasst, die vor erreichen, aber dies das Modell und das Ergebnis in längeren Aktualisierungszeiten vergrößert wird. Im Allgemeinen sollten Aggregationstabellen für sehr große Modelle oder zusammengesetzten Modells Entwürfe reserviert werden.
- Berechnete Tabellen und Spalten erhöhen Sie die Modellgröße aus, und führen mehr Aktualisierungszeiten bereit. Im Allgemeinen können eine geringere Datenspeichergröße und eine schnellere Aktualisierung erreicht werden, wenn die Daten materialisiert oder in der Datenquelle berechnet werden. Wenn dies nicht möglich ist, kann die mithilfe von Power Query, benutzerdefinierte Spalten verbesserte speicherkomprimierung anbieten.
- Es gibt möglicherweise Gelegenheit zum Optimieren von DAX-Ausdrücken für Measures und RLS-Regeln, die vielleicht umschreibungslogik zu formulieren um teure Formeln zu vermeiden.
- Die inkrementelle Aktualisierung kann erheblich Aktualisierungszeit reduzieren und Einsparen von Arbeitsspeicher und CPU. Die inkrementelle Aktualisierung kann auch konfiguriert werden, um Modelle trim behalten Verlaufsdaten zu entfernen.
- Ein Modell kann als zwei Modelle überarbeitet werden, bei anderen und in Konflikt stehende Abfragemuster. Für andere Berichte vorhanden allgemeine Aggregate über alle Verlauf, und es wird z. B. Wartezeit von 24 Stunden tolerieren. Andere Berichte sind mit Daten und differenzierten Zugriff auf einzelne Transaktionen benötigen. Anstatt Entwurf ein einzelnes Modell, um alle Berichte zu erfüllen erstellen Sie zwei Modelle, die für die einzelnen Anforderungen optimiert.

Erwägen Sie die optimierungsmöglichkeiten für ein DirectQuery-Modell. Wie das Modell abfrageanforderungen an die zugrunde liegenden Datenquelle ausgibt, ist die Datasource-Optimierung wichtig für die Bereitstellung von reaktionsfähigen Modell Abfragen.

 ![Optimierungsmöglichkeiten für ein DirectQuery-Modell](media/service-premium-capacity-optimize/direct-query-model-optimizations.png)

Auf der Datasource-Ebene:

- Die Datenquelle kann optimiert werden um sicherzustellen, dass die schnellste Möglichkeit Abfragen nach vorab Integrieren von Daten (die nicht auf der Ebene des möglich ist), Anwenden der geeigneten Indizes, Definieren von Tabellenpartitionen, die durch das materialisieren zusammengefasste Daten (mit indizierten Sichten), und Minimieren den Betrag, der Berechnung an. Optimale Ergebnisse wird erreicht, bei der Pass-Through-Abfragen müssen, nur filtern und Ausführen innerer Verknüpfungen zwischen indizierten Tabellen oder Sichten.
- Sicherstellen Sie, dass Gateways ausreichende Ressourcen, vorzugsweise auf dedizierten Computern, die mit genügend Netzwerkbandbreite und in der Nähe der Datenquelle.

Auf der Modellebene:

- Power Query-Abfrage, die Entwürfe sollte vorzugsweise gelten keine Transformationen – andernfalls versucht, die Transformationen auf ein absolutes minimum zu beschränken.
- Modell die abfrageleistung kann verbessert werden, durch Konfigurieren von Richtung Beziehungen, es sei denn, es gibt ein zwingenden Grund bidirektionales filtern können. Darüber hinaus sollte Modellieren von Beziehungen konfiguriert werden, um wird davon ausgegangen wird referenzielle Integrität erzwungen (Wenn dies der Fall ist) und führt zu einer Datenquelle Abfragen effizienter innere Joins (anstelle von äußeren Joins).
- Erstellen benutzerdefinierter Spalten von Power Query-Abfrage oder eine berechnete modellspalte vermeiden – materialisieren in der Datenquelle, wenn möglich.
- Es gibt möglicherweise Gelegenheit zum Optimieren von DAX-Ausdrücken für Measures und RLS-Regeln, z. B. umschreibungslogik zu formulieren um teure Formeln zu vermeiden.

Erwägen Sie die optimierungsmöglichkeiten für eine zusammengesetzte Modell ein. Denken Sie daran, dass eine kombinierte Modell eine Mischung von Import und DirectQuery-Tabellen ermöglicht.

![Optimierungsmöglichkeiten für eine zusammengesetzte Modell](media/service-premium-capacity-optimize/composite-model-optimizations.png)

- Im Allgemeinen die Optimierung für Import- und DirectQuery-Modelle mit dem gelten für zusammengesetzten Modells-Tabellen, die diese Speichermodi verwenden.
- In der Regel sich bemühen Sie, einen Entwurf mit Lastenausgleich zu erzielen, indem Sie Konfigurieren von Dimensionstyp Tabellen (für Geschäftseinheiten) als Dual-Modus und Faktentyp Speichertabellen (häufig große Tabellen, die betriebliche Fakten darstellt) als DirectQuery-Speichermodus. Dual-Speichermodus bedeutet, dass beide zu importieren und DirectQuery-Speichermodi und dadurch können die Power BI-Dienst, um zu bestimmen, die effizientesten-Speichermodus verwendet zur Erstellung einer systemeigenen Abfrage für die Passthrough.
- Sicherstellen Sie, dass Gateways ausreichende Ressourcen, vorzugsweise auf dedizierten Computern, die mit genügend Netzwerkbandbreite und in der Nähe zu den Datenquellen verfügen.
- Aggregationen Tabellen wird konfiguriert, wie Speicher Importmodus eindrucksvolle Abfrage leistungsverbesserungen bei der mit dem DirectQuery-Modus Faktentyp Speichertabellen zusammengefasst, liefern kann. In diesem Fall Aggregationstabellen werden die Größe des Modells sowie erhöhen Aktualisierungszeit, und dies ist häufig ein akzeptabler Kompromiss zu schnelleren Abfragen.

### <a name="optimizing-externally-hosted-models"></a>Optimieren der extern gehosteten Modellen

Viele optimierungsmöglichkeiten beschrieben, der [Optimieren von Power BI gehosteten Modelle](#optimizing-power-bi-hosted-models) Abschnitt gelten auch für Modelle, die mit Azure Analysis Services und SQL Server Analysis Services entwickelt. Löschen von Ausnahmen sind bestimmte Features, die derzeit nicht einschließlich zusammengesetzten Modelle und Aggregationstabellen unterstützt werden.

Eine weitere Überlegungen für extern gehostete Datasets ist eine Datenbank in Bezug auf Power BI-Dienst hostet. Für Azure Analysis Services bedeutet dies, erstellen die Azure-Ressource in der gleichen Region wie das Power BI-Mandant (home-Region). Für SQL Server Analysis Services für IaaS Dies bedeutet, dass den virtuelle Computer in derselben Region gehostet, und für lokale, es bedeutet, dass eine effiziente gatewaysetup sichergestellt.

Übrigens kann es sein, von Interesse sind, beachten Sie, dass Azure Analysis Services-Datenbanken und tabellarische SQL Server Analysis Services-Datenbanken erfordern, dass ihre Modelle vollständig in den Arbeitsspeicher geladen werden, dass sie es überhaupt bleiben Male auf, um Abfragen zu unterstützen. Wie im Power BI-Dienst muss es über ausreichend Arbeitsspeicher für aktualisiert, wenn es bei der Aktualisierung des Modells online bleiben muss. Im Gegensatz zu den Power BI-Dienst ist keine vorhanden, dass die Modelle in den Arbeitsspeicher gemäß Nutzung automatisch ersetzt werden. Power BI Premium bietet daher einen effizienteren Ansatz zur Maximierung des Modells Erstellen von Abfragen mit niedriger Auslastung des Speichers.

## <a name="capacity-planning"></a>Planen der Kapazität

Die Größe von einer Premium-Kapazität wird bestimmt, die Speicherplatz und Prozessorressourcen und Grenzwerte für die Kapazität. Die Anzahl der Premium-Kapazitäten wird auch berücksichtigt, wie das Erstellen mehrerer Premium Kapazitäten können Workloads voneinander zu isolieren. Beachten Sie, dass Speicher 100 TB pro kapazitätsknoten beträgt, und dies ist meist mehr als ausreichend für alle Workloads.

Ermitteln der Größe und Anzahl der Premium-Kapazitäten kann, insbesondere für die anfängliche Kapazitäten schwierig sein, die Sie erstellen. Der erste Schritt, wenn die erforderlichen Kapazitäten, die durchschnittlichen Workload, die Darstellung der erwartete täglichen Verwendung zu verstehen ist. Es ist wichtig zu verstehen, dass nicht alle arbeitsauslastungen gleich sind. Beispiel: an einem Ende einer Bandbreite - 100 gleichzeitige Benutzer, die Zugriff auf eine einzelne Berichtsseite, die ein einzelnes visuelles enthält ist einfach erreichbares. Noch - am anderen Ende des Spektrums - 100 gleichzeitige Benutzer, die Zugriff auf 100 verschiedene Berichte, jeweils mit 100 Visuals auf der Berichtsseite wird sehr unterschiedliche Anforderungen von kapazitätsressourcen stellen.

Kapazitätsadministratoren müssen daher viele Faktoren zu berücksichtigen, die spezifisch für Ihre Umgebung, die Inhalte und die erwartete Nutzung. Das Überschreiben wird, zugleich konsistente Abfragezeiten akzeptablen Wartezeiten und entfernungsraten Ausnutzung der Speicherkapazität zu maximieren. Zu berücksichtigende Faktoren können umfassen:

- **Modellieren Sie Größe und Merkmale** -importmodelle muss vollständig geladen ist, in den Arbeitsspeicher können Abfragen oder aktualisieren. LC/DQ-Datasets können erhebliche Prozessorzeit und möglicherweise erheblichen Speicherplatz zum Auswerten von komplexen Measures oder RLS-Regeln erforderlich. Arbeitsspeicher und Prozessorgröße und abfragedurchsatz LC/DQ werden durch die Größe der Kapazität beschränkt.
- **Gleichzeitige aktive Modelle** -das gleichzeitige Abfragen der verschiedenen importmodelle liefert beste Reaktionsfähigkeit und Leistung, wenn sie im Speicher verbleiben. Es sollte genügend Arbeitsspeicher, um alle häufig abgefragte Modelle mit zusätzlichen Arbeitsspeicher für die datenaktualisierung zu hosten.
- **Aktualisierung des Modells Import** -der Aktualisierungstyp (vollständig oder inkrementell), die Dauer und Komplexität von Power Query-Abfragen und berechnete Tabelle/Spalte-Logik können an Arbeitsspeicher und insbesondere CPU-Leistung beeinträchtigen. Gleichzeitige Aktualisierungen werden durch die Größe der Kapazität (1,5 X backend V-Kerne, aufgerundet) beschränkt.
- **Gleichzeitige Abfragen** -können viele gleichzeitige Abfragen führen in nicht reagiert wird berichtet, wenn Prozessor oder LC/DQ-Verbindungen überschreitet den Grenzwert von Kapazität. Dies gilt insbesondere für Berichtsseiten, die viele visuelle Elemente enthalten.
- **Datenflüsse und paginierten Berichten** – die Kapazität kann so konfiguriert werden, dass die um Datenflüsse und paginierte Berichte, mit jeder erfordert einen konfigurierbaren maximalen Prozentsatz der Speicherkapazität zu unterstützen. Arbeitsspeicher wird dynamisch zugewiesen, um Datenflüsse, aber Sie paginierte Berichte statisch zugeordnet.

Zusätzlich zu dieser Faktoren kann Kapazitätsadministratoren erwägen, mehrere Kapazitäten zu erstellen. Mehrere Kapazitäten ermöglichen die Isolierung von Workloads und können konfiguriert werden, um sicherzustellen, dass Kritischer arbeitsauslastungen garantiert, dass Ressourcen haben. Beispielsweise können zwei Kapazitäten erstellt werden, um geschäftskritische Workloads vom Self-service-BI (SSBI)-Workloads zu trennen. Die unternehmenskritischen Kapazität kann verwendet werden, um große Unternehmen Modelle bereit, mit garantierten Ressourcen, mit der Erstellung der Zugriff gewährt, die nur für die IT-Abteilung zu isolieren. Die Kapazität SSBI kann zu einem host eine wachsende Anzahl von kleineren Modellen mit Zugriff erteilt für Wirtschaftsanalytiker verwendet werden. Die Kapazität SSBI treten möglicherweise gelegentlich Abfrage oder Aktualisierung Wartevorgänge, die akzeptiert werden.

Im Laufe der Zeit kann Kapazitätsadministratoren Arbeitsbereiche auf Kapazitäten durch das Verschieben von Inhalten zwischen Arbeitsbereichen oder zwischen Kapazitäten-Arbeitsbereiche und skalieren Kapazitäten, oben oder unten zu verteilen. Im Allgemeinen Skalieren für Host größere Modelle, die Sie skalieren, und höhere Parallelität zu erzielen Sie.

Denken Sie daran, dass Erwerb einer Lizenz des Mandanten mit der V-Kerne zur Verfügung. Der Kauf von einer **P3** -Abonnement verwendet werden kann, erstellen, oder bis zu vier Premium-Kapazitäten, d. h. 1 x P3 oder 2 x P2 oder 4 x P1. Darüber hinaus können vor dem Upsizing eine P2-Kapazität P3 Kapazität berücksichtigt werden, um die V-Kerne aufteilen zwei P1-Kapazitäten zu erstellen.

## <a name="testing-approaches"></a>Testen von Vorgehensweisen

Sobald eine Kapazitätsgröße entschieden wird, kann Tests ausgeführt werden, durch das Erstellen einer kontrollierten Umgebung. Eine praktische und eine wirtschaftliche Option ist die Erstellung einer Kapazitäten in Azure (A-SKUs), beachten Sie, dass eine P1-Kapazität auf die gleiche Größe wie eine A4-Kapazität, mit dem P2 ist und P3-Kapazitäten die gleiche Größe wie die Kapazitäten A5 und A6 jeweils. Azure-Kapazitäten können schnell erstellt werden und werden auf Stundenbasis in Rechnung gestellt. Also nach Tests abgeschlossen wurden, können sie problemlos gelöscht werden, um verwendungsgebühren Kosten.

Der Testinhalt auf der Azure-Kapazität erstellten Arbeitsbereiche im Rahmen hinzugefügt werden kann, und klicken Sie dann als einen einzelnen Benutzer kann Berichte ausführen, um eine realistische und repräsentativen arbeitsauslastung mit Abfragen zu generieren. Wenn importmodelle vorhanden sind, sollte auch eine Aktualisierung für jedes Modell ausgeführt werden. Überwachungstools kann dann verwendet werden, überprüfen Sie alle Metriken, um die Ressourcenverwendung zu verstehen.

Es ist wichtig, dass die Tests wiederholt werden. Tests sollten mehrere Male ausgeführt werden, und sie sollten jedes Mal, etwa das gleiche Ergebnis liefern. Durchschnittlich diese Ergebnisse kann dann extrapolieren können und schätzen die Workload unter Produktionsbedingungen "true" verwendet werden.

Erwägen Sie die Entwicklung eines Auslastungstests, die Anwendung zur Simulation einer realistischen arbeitsauslastung, um einen Belastungstest zu generieren. Einzelheiten hierzu werden außerhalb des Bereichs der in diesem Artikel. Weitere Informationen einschließlich ein Codebeispiel finden Sie in der [Auslastungstests in Power BI-Anwendungen mit Visual Studio-Auslastungstests](https://blogs.msdn.microsoft.com/charles_sterling/2018/04/04/webinar-load-testing-power-bi-applications-with-visual-studio-load-test/) Webinar.

## <a name="acknowledgements"></a>Bestätigungen

Dieser Artikel geschrieben wurde, indem Peter Myers, Data Platform MVP und unabhängige BI-Experte mit [bitweise Lösungen](https://www.bitwisesolutions.com.au/).

## <a name="next-steps"></a>Nächste Schritte

> [!div class="nextstepaction"]
> [Szenarien für Premium-Kapazität](service-premium-capacity-scenarios.md)   
  
Weitere Fragen? [Stellen Sie Ihre Frage in der Power BI-Community.](https://community.powerbi.com/)

||||||