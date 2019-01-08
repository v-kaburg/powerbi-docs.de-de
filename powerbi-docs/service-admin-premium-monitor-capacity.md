---
title: Überwachen von Power BI Premium-Kapazitäten in Ihrer Organisation
description: Verwenden des Power BI-Verwaltungsportals und der Power BI Premium Capacity Metrics-App
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-admin
ms.topic: conceptual
ms.date: 12/13/2018
LocalizationGroup: Premium
ms.openlocfilehash: 250c8b28e4ee9e8b29e2db8195f7883d11708806
ms.sourcegitcommit: 6c6aa214dc36c26a01b29e823598d217a3e2b8a1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/14/2018
ms.locfileid: "53382241"
---
# <a name="monitor-power-bi-premium-and-power-bi-embedded-capacities"></a>Überwachen von Kapazitäten in Power BI Premium und Power BI Embedded

Dieser Artikel bietet einen Überblick über die Überwachung der Metriken für Ihre Power BI Premium-Kapazitäten. Die Überwachung der Kapazitätsauslastung bietet Ihnen einen fundierten Ansatz für die Verwaltung Ihrer Kapazitäten.

Sie können die Kapazität mithilfe der Power BI Premium Capacity Metrics-App oder dem Verwaltungsportal überwachen. Wir empfehlen die Verwendung der App, weil diese sehr viel umfangreichere Informationen bietet, aber dieser Artikel deckt beide Optionen ab.

**Die aktuelle Version der App ist 1.10 (veröffentlicht am 13. Dezember 2018).**

.

<iframe width="560" height="315" src="https://www.youtube.com/embed/UgsjMbhi_Bk?rel=0&amp;showinfo=0" frameborder="0" allowfullscreen></iframe>

## <a name="install-the-premium-capacity-metrics-app"></a>Installieren der Premium Capacity Metrics-App

Sie können direkt zur [Premium Capacity Metrics-App](https://app.powerbi.com/groups/me/getapps/services/capacitymetrics) wechseln oder diese wie andere Apps in Power BI installieren.

1. Klicken Sie in Power BI auf **Apps**.

    ![Wechsel zu „Apps“](media/service-admin-premium-monitor-capacity/apps.png)

1. Klicken Sie auf der rechten Seite auf **Apps abrufen**.

1. Suchen Sie in der Kategorie **Apps** nach der **Power BI Premium Capacity Metrics-App**.

1. Rufen Sie die App ab, um sie zu installieren.

Nachdem Sie die App installiert haben, können Sie Metriken zu den Kapazitäten in Ihrer Organisation anzeigen. Sehen wir uns einige der wichtigsten Metriken an, die zur Verfügung gestellt werden.

## <a name="use-the-metrics-app"></a>Verwenden der Metriken-App

### <a name="metrics-dashboard"></a>Metrikdashboard

Wenn Sie die App öffnen, wird zunächst ein Dashboard mit einer Zusammenfassung aller Kapazitäten angezeigt, für die Sie über Administratorrechte verfügen.

![Metrik-App-Dashboard](media/service-admin-premium-monitor-capacity/app-dashboard.png)

Das Dashboard umfasst die folgenden Metriken.

| **Berichtsabschnitt** | **Metriken** |
| --- | --- |
| **Systemübersicht** | * Version der Anwendung<br> * Anzahl der Kapazitäten, die Sie als Administrator betreuen<br> * Anzahl der Arbeitsbereiche in Ihren Kapazitäten, die Metriken melden<br> * Mittlere Arbeitsspeichernutzung in GB über die letzten sieben Tage<br> * Maximale Arbeitsspeichernutzung in GB über die letzten sieben Tage<br> * Lokale Uhrzeit, zu der die maximale Arbeitsspeichernutzung aufgetreten ist<br> * Anzahl der Fälle, bei denen die CPU-Auslastung in den letzten 7 Tagen 80 % des Schwellenwerts überschritten hat, unterteilt in 3-Minuten-Abschnitte<br> * Häufigste Zeiten, zu denen die CPU-Auslastung in den letzten 7 Tagen 80 % überschritten hat, unterteilt in 1-Stunden-Abschnitte<br> * Lokale Uhrzeit, zu der die CPU am häufigsten 80 % innerhalb einer Stunde überschritten hat |
| **Datasetübersicht** | * Gesamtzahl der Datasets über alle Arbeitsbereiche in Ihren Kapazitäten<br> * Anzahl der Fälle, bei denen Direktabfragen/Liveverbindungen 80 % der Schwellenwerte innerhalb der letzten sieben Tage überschritten haben, aufgeteilt in 3-Minuten-Abschnitte<br> * Häufigste Zeiten, zu denen Direktabfragen/Liveverbindungen 80 % überschritten haben, unterteilt in 1-Stunden-Abschnitte<br> * Lokale Uhrzeit, zu der Direktabfragen/Liveverbindungen am häufigsten 80 % innerhalb einer Stunde überschritten haben<br> * Gesamtanzahl der Aktualisierungen in den letzten 7 Tagen<br> * Die durchschnittliche Wartezeit für Aktualisierungen ist die durchschnittliche Verzögerung zwischen geplanter Zeit und Start der Aktualisierung in Minuten<br> * Die durchschnittliche Aktualisierungsdauer ist die Zeit bis zum Abschluss der Aktualisierung in Minuten<br> * Gesamtanzahl der ausgeführten Abfragen in den letzten 7 Tagen<br> * Durchschnittliche Wartezeit: die Zeit in Millisekunden, während der eine Abfrage vor dem Beginn der Ausführung auf Systemressourcen gewartet hat<br> * Durchschnittliche Abfragedauer: die Zeit in Millisekunden bis zum Abschluss des Abfrage<br> * Gesamtanzahl der entfernten Modelle aufgrund von Speicherauslastung<br> * Durchschnittsgröße von Datasets <br> * Anzahl der durchschnittlich im Arbeitsspeicher geladenen Datasets |
| **Datenflussübersicht** | * Gesamtzahl der Datenflüsse über alle Arbeitsbereiche in Ihren Kapazitäten<br> * Gesamtanzahl der Aktualisierungen in den letzten 7 Tagen<br> * Die durchschnittliche Wartezeit für Aktualisierungen ist die durchschnittliche Verzögerung zwischen geplanter Zeit und Start der Aktualisierung in Minuten<br> * Die durchschnittliche Aktualisierungsdauer ist die Zeit bis zum Abschluss der Aktualisierung in Minuten |
| **Paginierter Bericht – Übersicht** | * Gesamtzahl der paginierten Berichte über alle Arbeitsbereiche in Ihren Kapazitäten<br> * Gesamtzahl der Fälle, in denen alle Berichte von Benutzern angezeigt wurden<br> * Gesamtzahl der Zeilen mit Daten in allen Berichten<br> * Gesamtzeit in Millisekunden für alle Phasen (Abrufen, Verarbeiten und Rendern von Daten) für alle Berichte |
|  |  |

### <a name="metrics-report"></a>Metrikbericht

Klicken Sie auf das Dashboard, um zum zugrunde liegenden Bericht zu gelangen. Der Bericht weist fünf Registerkarten auf, die in den folgenden Abschnitten ausführlicher beschrieben werden.

* **Datasets**: Hier finden Sie ausführliche Metriken zur Integrität der Power BI-Datasets in Ihren Kapazitäten.

* **Paginierte Berichte**: Hier finden Sie ausführliche Metriken zur Integrität der paginierten Berichte in Ihren Kapazitäten.

* **Dataflows**: Hier finden Sie ausführliche Aktualisierungsmetriken für Dataflows in Ihren Kapazitäten.

* **Ressourcenverbrauch**: Metriken zur Gesamtkapazität, einschließlich Arbeitsspeicher und hoher CPU-Auslastung.

* **IDs und Info**: die Namen, IDs und Besitzer von Kapazitäten, Arbeitsbereichen und Workloads.

Auf jeder Registerkarte lassen sich die Metriken nach Kapazität und Datumsbereich filtern. Wenn keine Filter ausgewählt sind, zeigt der Bericht standardmäßig die Metriken der letzten Woche für alle Kapazitäten an, die Metriken melden.

#### <a name="datasets-tab"></a>Registerkarte „Datasets“

Verwenden Sie die Schaltflächen oben auf der Registerkarte **Datasets**, um zu verschiedenen Bereichen zu navigieren: **Zusammenfassung**, **Aktualisierungen**, **Abfragedauern**, **Abfragewartezeiten** und **Datasets**.

![Registerkarte „Datasets“](media/service-admin-premium-monitor-capacity/datasets-tab.png)

##### <a name="refreshes-area"></a>Bereich „Refreshes“ (Aktualisierungen)

Der Bereich **Aktualisierungen** enthält die folgenden Metriken.

| **Berichtsabschnitt** | **Metriken** |
| --- | --- |
| **Zuverlässigkeit der Aktualisierung** | * Gesamtzahl: alle Aktualisierungen für jedes Dataset<br> * Zuverlässigkeit: Prozentsatz der Aktualisierungen, die für jedes Dataset ausgeführt wurden<br> * Durchschnittliche Wartezeit: die durchschnittliche Verzögerung zwischen geplanter Zeit und Start der Datasetaktualisierung in Minuten<br> * Maximale Wartezeit: die maximale Wartezeit für das Dataset in Minuten <br> * Durchschnittliche Dauer: die durchschnittliche Dauer in Minuten für die Aktualisierung des Datasets<br> * Maximale Dauer: die Dauer der längsten Datasetaktualisierung in Minuten |
| **Top 5 Datasets nach durchschnittlicher Aktualisierungsdauer** | * Die fünf Datasets mit der längsten durchschnittlichen Aktualisierungsdauer in Minuten |
| **Top 5 Datasets nach durchschnittlicher Wartezeit** | * Die fünf Datasets mit der längsten durchschnittlichen Aktualisierungswartezeit in Minuten |
| **Durchschnittliche stündliche Aktualisierungswartezeiten** | * Die durchschnittliche Aktualisierungswartezeit, unterteilt in Stunden, Angabe in Ortszeit. Mehrere Spitzen mit langen Aktualisierungswartezeiten weisen auf eine hohe Auslastung der Kapazität hin. |
| **Stündliche Aktualisierungen und Arbeitsspeicherverbrauch** | * Erfolgreiche Vorgänge, Fehler und Arbeitsspeicherverbrauch, unterteilt in Stunden, Angabe in Ortszeit |
|  |  |

##### <a name="query-durations-area"></a>Bereich „Query Durations“ (Abfragedauer) 

Der Bereich **Abfragedauer** enthält die folgenden Metriken.

| **Berichtsabschnitt** | **Metriken** |
| --- | --- |
| **Abfragedauer** | * Daten in diesem Bereich sind nach Datasets, Arbeitsbereich und Stunden für die letzten sieben Tage unterteilt<br> * Gesamt: Gesamtzahl der Abfragen, die für das Dataset ausgeführt werden<br> * Durchschnitt: die durchschnittliche Abfragedauer für das Dataset in Millisekunden<br> * Max: die längste Abfragedauer für das Dataset in Millisekunden|
| **Verteilung der Abfragedauer** | * Das Histogramm der Abfragedauer ist nach der Dauer (in Millisekunden) in die folgenden Kategorien unterteilt: <= 30 ms, 30–100 ms, 100–300 ms, 300 ms bis 1 s, 1–3 s, 3–10 s, 10–30 s und > 30 s. Lange Ausführungsdauern und lange Wartezeiten sind ein Hinweis auf sich erschöpfende Kapazität. Es kann aber auch bedeuten, dass ein einzelnes Dataset Probleme verursacht und weitere Untersuchungen erforderlich sind. |
| **Top 5 Datasets nach durchschnittlicher Dauer** | * Die fünf Datasets mit der längsten durchschnittlichen Abfragedauer in Millisekunden |
| **Direkte Abfrage/Liveverbindungen (> 80 % Auslastung)** | * Häufigkeit einer CPU-Auslastung von über 80 % durch eine direkte Abfrage oder Liveverbindung, unterteilt in Stunden, Angabe in Ortszeit |
| **Verteilung der stündlichen Abfragedauer** | * Abfrageanzahl und durchschnittliche Dauer (in Millisekunden) im Vergleich zum Arbeitsspeicherverbrauch in GB, unterteilt in Stunden, Angabe in Ortszeit |
|  |  |

##### <a name="query-waits-area"></a>Bereich „Query Waits“ (Abfragewartezeit)

Der Bereich **Abfragewartezeit** enthält die folgenden Metriken.

| **Berichtsabschnitt** | **Metriken** |
| --- | --- |
| **Abfragewartezeiten** | * Daten in diesem Bereich sind nach Datasets, Arbeitsbereich und Stunden für die letzten sieben Tage unterteilt<br> * Gesamt: Gesamtzahl der Abfragen, die für das Dataset ausgeführt werden<br> * Anzahl der Wartevorgänge: Anzahl von Abfragen im Dataset, die vor der Ausführung auf Systemressourcen gewartet haben <br> * Durchschnitt: die durchschnittliche Abfragewartezeit für das Dataset in Millisekunden<br> * Max: die längste Abfragewartezeit für das Dataset in Millisekunden|
| **Verteilung der Wartezeit** | * Das Histogramm der Abfragedauer ist nach der Dauer (in Millisekunden) in die folgenden Kategorien unterteilt: <= 50 ms, 50–100 ms, 100–200 ms, 200–400 ms, 400 ms bis 1 s, 1–5 s und > 5 s |
| **Top 5 Datasets nach durchschnittlicher Wartezeit** | * Die fünf Datasets mit der längsten durchschnittlichen Wartezeit bis zum Start der Ausführung einer Abfrage in Millisekunden |
| **Stündliche Abfragewartevorgänge und -zeiten** | * Anzahl von Abfragewartevorgängen und durchschnittliche Wartezeit (in Millisekunden) im Vergleich zum Arbeitsspeicherverbrauch in GB, unterteilt in Stunden, Angabe in Ortszeit |
|  |  |

##### <a name="datasets-area"></a>Bereich „Datasets“

Der Bereich **Datasets** enthält die folgenden Metriken.

| **Berichtsabschnitt** | **Metriken** |
| --- | --- |
| **Anzahl von entfernten Datasets** | * Gesamt: Gesamtzahl der *entfernten* Datasets für jede Kapazität. Wenn eine Kapazität Arbeitsspeicherauslastung unterliegt, entfernt der Knoten mindestens ein Dataset aus dem Arbeitsspeicher. Datasets, die inaktiv sind (ohne derzeit ausgeführten Abfrage- oder Aktualisierungsvorgang), werden zuerst entfernt. Anschließend orientiert sich die Entfernungsreihenfolge an den „am seltensten verwendeten“ Datasets.|
| **Stündlich entfernte Datasets und Arbeitsspeicherverbrauch** | * Entfernte Datasets im Vergleich zum Arbeitsspeicherverbrauch in GB, unterteilt in Stunden, Angabe in Ortszeit |
| **Anzahl der stündlich geladenen Datasets** | * Anzahl der in den Arbeitsspeicher geladenen Datasets im Vergleich zum Arbeitsspeicherverbrauch in GB, unterteilt in Zeitfenster, Angabe in Ortszeit |
| **Datengrößen**  | * Maximale Größe: die maximale Größe des Dataset in MB für den angezeigten Zeitraum |
|  |  |

#### <a name="paginated-reports-tab"></a>Registerkarte „Paginierte Berichte“

Die Registerkarte **Paginierte Berichte** zeigt ausführliche Metriken zur Integrität der paginierten Berichte in Ihren Kapazitäten an.

![Registerkarte „Paginierte Berichte“](media/service-admin-premium-monitor-capacity/paginated-reports-tab.png)

Die Registerkarte **Paginierte Berichte** enthält die folgenden Metriken.

| **Berichtsabschnitt** | **Metriken** |
| --- | --- |
| **Verwendung gesamt** | * Gesamtzahl der Aufrufe: Häufigkeit der Berichtaufrufe durch Benutzer<br> * Zeilenanzahl: Anzahl von Datenzeilen im Bericht<br> * Abrufe (durchschn.): die durchschnittlich benötigte Zeit in Millisekunden zum Abrufen von Daten für den Bericht. Eine lange Dauer kann auf langsame Abfragen oder andere Probleme mit der Datenquelle hinweisen. <br> * Verarbeitung (durchschn.): die durchschnittlich benötigte Zeit zum Verarbeiten von Daten für einen Bericht in Millisekunden<br>* Rendering (durchschn.): die durchschnittlich benötigte Zeit zum Rendern eines Berichts im Browser in Millisekunden<br> * Gesamtzeit: von allen Phasen des Berichts benötigte Zeit in Millisekunden|
| **Top 5 Berichte nach durchschnittlicher Datenabrufzeit** | * Die fünf Berichte mit der längsten durchschnittlichen Datenabrufzeit in Millisekunden |
| **Top 5 Berichte nach durchschnittlicher Berichtverarbeitungsdauer** | * Die fünf Berichte mit der längsten durchschnittlichen Berichtverarbeitungsdauer in Millisekunden |
| **Stündliche Dauer** | * Datenabruf im Vergleich zur Verarbeitungs- und Renderingdauer, unterteilt in Stunden, Angabe in Ortszeit |
| **Stündliche Ergebnisse** | * Erfolgreiche Vorgänge, Fehler und Arbeitsspeicherverbrauch, unterteilt in Stunden, Angabe in Ortszeit |
|  |  |

#### <a name="dataflows-tab"></a>Registerkarte „Dataflows“

Die Registerkarte **Dataflows** zeigt ausführliche Aktualisierungsmetriken für Dataflows in Ihren Kapazitäten.

![Registerkarte „Dataflows“](media/service-admin-premium-monitor-capacity/dataflows-tab.png)

Die Registerkarte **Dataflows** enthält die folgenden Metriken.

| **Berichtsabschnitt** | **Metriken** |
| --- | --- |
| **Aktualisierung** | * Gesamt: alle Aktualisierungen für jeden Dataflow<br> * Zuverlässigkeit: Prozentsatz der Aktualisierungen, die für jeden Dataflow ausgeführt wurden<br> * Durchschnittliche Wartezeit: die durchschnittliche Verzögerung zwischen geplanter Zeit und Start der Datenflussaktualisierung in Minuten<br> * Maximale Wartezeit: maximale Wartezeit für den Datenfluss in Minuten <br> * Durchschnittliche Dauer: die durchschnittliche Dauer in Minuten für die Aktualisierung des Datenflusses<br> * Maximale Dauer: die Dauer der längsten Datenflussaktualisierung in Minuten |
| **Top 5 Dataflows nach durchschnittlicher Aktualisierungsdauer** | * Die fünf Dataflows mit der längsten durchschnittlichen Aktualisierungsdauer in Minuten |
| **Top 5 Dataflows nach durchschnittlicher Wartezeit** | * Die fünf Dataflows mit der längsten durchschnittlichen Aktualisierungswartezeit in Minuten |
| **Durchschnittliche stündliche Aktualisierungswartezeiten** | * Die durchschnittliche Aktualisierungswartezeit, unterteilt in Stunden, Angabe in Ortszeit. Mehrere Spitzen mit langen Aktualisierungswartezeiten weisen auf eine hohe Auslastung der Kapazität hin. |
| **Stündliche Aktualisierungen und Arbeitsspeicherverbrauch** | * Erfolgreiche Vorgänge, Fehler und Arbeitsspeicherverbrauch, unterteilt in Stunden, Angabe in Ortszeit |
|  |  |

#### <a name="resource-consumption-tab"></a>Registerkarte „Ressourcenverbrauch“

Die Registerkarte **Ressourcenverbrauch** zeigt die CPU-Auslastung und den Arbeitsspeicherverbrauch für alle Kapazitäten und Workloads.

![Registerkarte „Ressourcenverbrauch“](media/service-admin-premium-monitor-capacity/resource-consumption-tab.png)

Die Registerkarte **Ressourcenverbrauch** enthält die folgenden Metriken.

| **Berichtsabschnitt** | **Metriken** |
| --- | --- |
| **CPU-Auslastung** | * Die Anzahl von Vorkommen, bei denen die CPU-Auslastung in den letzten 7 Tagen 80% des Schwellenwerts überschritten hat, unterteilt in 3-Minuten-Abschnitte |
| **Arbeitsspeicherverbrauch** | * Arbeitsspeicherverbrauch der letzten sieben Tage, unterteilt in 3-Minuten-Bereiche |
|  |  |

#### <a name="ids-and-info-tab"></a>Registerkarte „IDs und Info“

Die Registerkarte **IDs und Info** zeigt die Namen, IDs und Besitzer von Kapazitäten, Arbeitsbereichen und Workloads.

![Registerkarte „IDs und Info“](media/service-admin-premium-monitor-capacity/info-tab.png)

## <a name="monitor-power-bi-embedded-capacity"></a>Überwachen einer Power BI Embedded-Kapazität

Sie können die Power BI Premium Capacity Metrics-App auch zum Überwachen von Kapazitäten mit *A-SKU* in Power BI Embedded verwenden. Diese Kapazitäten werden im Bericht angezeigt, sofern Sie ein Administrator der Kapazität sind. Die Aktualisierung des Berichts ist jedoch nur erfolgreich, wenn Sie Power BI bestimmte Berechtigungen für Ihre A-SKUs erteilen:

1. Öffnen Sie Ihre Kapazität im Azure-Portal.

1. Klicken Sie auf **Zugriffssteuerung (IAM)**, und fügen Sie die App „Power BI Premium“ zur Rolle „Leser“ hinzu. Wenn Sie den Namen der App nicht finden, können Sie sie auch per Client-ID hinzufügen: cb4dc29f-0bf4-402a-8b30-7511498ed654.

    ![Berechtigungen für Power BI Embedded](media/service-admin-premium-monitor-capacity/embedded-permissions.png)

> [!NOTE]
> Sie können die Nutzung der Power BI Embedded-Kapazität in der App oder im Azure-Portal überwachen, nicht jedoch im Power BI-Verwaltungsportal.

## <a name="basic-monitoring-in-the-admin-portal"></a>Grundlegende Überwachung im Verwaltungsportal

Der Bereich **Kapazitätseinstellungen** im Verwaltungsportal bietet Messanzeigen in Bezug auf die Lasten und die von Ihrer Kapazität verwendeten Ressourcen für die letzten 7 Tage. Diese vier Kacheln arbeiten mit einem Zeitfenster von 1 Stunde. Sie zeigen an, wie viele Stunden die zugehörige Metrik in den vergangenen 7 Tagen 80% überschritten hat. Diese Metrik weist auf eine potenzielle Beeinträchtigung für den Endbenutzer hin.

![Nutzung in 7 Tagen](media/service-admin-premium-monitor-capacity/usage-in-days.png)

| **Metrik** | **Beschreibung** |
| --- | --- |
| CPU |Häufigkeit, mit der die CPU eine Auslastung von 80 % überschritten hat. |
| Speicherüberlastung |Zeigt die Speicherauslastung Ihrer Back-End-Kerne. Dies ist insbesondere eine Metrik dazu, wie oft Datasets aufgrund hoher Speicherauslastung bei Verwenden mehrerer Datasets aus dem Arbeitsspeicher entfernt werden. |
| Speicherauslastung |Durchschnittliche Arbeitsspeicherauslastung in Gigabytes (GB). |
| DQ/s | Häufigkeit, mit der die Anzahl von „Direkte Abfrage“- und Liveverbindungen 80 % des Grenzwerts überschritten hat. <br> * Die Gesamtzahl von DirectQuery-Abfragen und Liveverbindungen pro Sekunde ist eingeschränkt.* Limits: 30/s für P1, 60/s für P2 und 120/s für P3. * Die Anzahl von Abfragen des Typs „Direkte Abfrage“ und „Liveverbindung“ werden zur Drosselung hinzu gerechnet. Wenn Sie z.B. 15 direkte Abfragen und 15 Liveverbindungen in einer Sekunde haben, ist die Begrenzung erreicht.<br>* Dies gilt sowohl für lokale als auch Cloudverbindungen. |
|  |  |

Metriken spiegeln die Auslastung in der letzten Woche wider.  Wenn Sie eine detailliertere Ansicht der Metriken wünschen, können Sie dies tun, indem Sie auf eine der Zusammenfassungskacheln klicken.  Sie gelangen zu detaillierten Diagrammen für jede der Metriken für Ihre Premium-Kapazität. Das folgende Diagramm zeigt Details zur CPU-Metrik.

![Ausführlicher Nutzungsdiagramm zur CPU](media/service-admin-premium-monitor-capacity/premium-usage-detailed-chart-cpu.png)

Diese Diagramme sind für die letzte Woche stündlich zusammengefasst und können Ihnen helfen zu ermitteln, wann bestimmte leistungsbezogene Ereignisse in Ihrer Premium-Kapazität aufgetreten sind.

Sie können auch die für jede der Metriken zugrunde liegenden Daten in eine CSV-Datei exportieren.  Dieser Export liefert Ihnen im Drei-Minuten-Takt detaillierte Informationen für jeden Tag der vergangenen Woche.

## <a name="next-steps"></a>Nächste Schritte

Nachdem Sie die Überwachung von Power BI Premium-Kapazitäten kennengelernt haben, können Sie sich über das Optimieren von Kapazitäten informieren.

> [!div class="nextstepaction"]
> [Verwaltung und Optimierung der Power BI Premium-Kapazitätsressource](service-premium-understand-how-it-works.md)
