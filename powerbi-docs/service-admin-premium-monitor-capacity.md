---
title: Überwachen von Power BI Premium-Kapazitäten mit der App „Power BI Premium-Kapazitätsmetriken“
description: Verwenden des Power BI-Verwaltungsportals und der Power BI Premium Capacity Metrics-App
author: minewiskan
ms.author: owend
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 02/05/2019
LocalizationGroup: Premium
ms.openlocfilehash: c4e919de95c86051257ddc38b65c4dfda78dfc03
ms.sourcegitcommit: 54d44deb6e03e518ad6378656c769b06f2a0b6dc
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/07/2019
ms.locfileid: "55794612"
---
# <a name="monitor-premium-capacities-with-the-app"></a>Überwachen von Premium-Kapazitäten über die App

Die Überwachung Ihrer Kapazitäten ist entscheidend für das Treffen fundierter Entscheidungen zur optimalen Nutzung Ihrer Premium-Kapazitäten. Sie können die Kapazitäten im Verwaltungsportal oder mithilfe der App **Power BI Premium-Kapazitätsmetriken** überwachen. In diesem Artikel wird die Verwendung der Premium-Kapazitätsmetriken-App erläutert. Die App stellt ausführliche Informationen zur Leistung Ihrer Kapazitäten bereit. Einen allgemeineren Überblick durchschnittlicher Nutzungsmetriken der letzten sieben Tage finden Sie im Verwaltungsportal. Weitere Informationen zur Überwachung im Portal finden Sie unter [Monitor Premium capacities in the Admin portal (Überwachung von Premium-Kapazitäten im Verwaltungsportal)](service-admin-premium-monitor-portal.md).

Die App erhält regelmäßige Updates mit neuen Features und Funktionalitäten. Stellen Sie sicher, dass Sie die neueste Version verwenden.
**Die neueste Version der App ist Version 1.10.1.1 (Stand: 5. Februar 2019)**.   
Wenn Sie bereits eine ältere Version installiert haben, löschen Sie sie aus Ihren Apps, und drücken Sie das STRG+F5 zum Aktualisieren. 

## <a name="install-the-app"></a>Installieren der App

Sie können direkt zur [Premium-Kapazitätsmetriken-App](https://app.powerbi.com/groups/me/getapps/services/capacitymetrics) navigieren, oder Sie installieren sie wie jede andere App in Power BI.


1. Klicken Sie in Power BI auf **Apps**.   
    ![Zu Apps navigieren](media/service-admin-premium-monitor-capacity/apps.png)

2. Klicken Sie auf der rechten Seite auf **Apps abrufen**.
3. Suchen Sie in der Kategorie **Apps** nach der **Power BI Premium Capacity Metrics-App**.
4. Rufen Sie die App ab, um sie zu installieren.

Warten Sie einen Augenblick. Das Installieren und Aktualisieren der Metriken dauert einige Minuten. Wenn die App leere Metriken anzeigt, drücken Sie F5 zum Aktualisieren der Seite.


## <a name="get-app-refresh-history"></a>Abrufen des Aktualisierungsverlaufs der App

Klicken Sie auf **Einstellungen** > **Datasets** > **Power BI Premium-Kapazitätsmetriken** > **Aktualisierungsverlauf**. 

![Aktualisierungsverlauf in den Einstellungen](media/settings-refresh-history.png)

Die letzte Aktualisierung wird angezeigt. Wenn Sie auf **Aktualisierungsverlauf** klicken, werden geplante und abrufbare Aktualisierungen angezeigt.

![Letzte Aktualisierung](media/service-admin-premium-monitor-capacity/settings-last-refresh.png)

## <a name="monitor-a-capacity-with-the-app"></a>Überwachen einer Kapazität mit der App

Nachdem Sie die App installiert haben, können Sie Metriken zu den Kapazitäten in Ihrer Organisation anzeigen. Sehen wir uns einige der wichtigsten Metriken an, die zur Verfügung gestellt werden.

### <a name="metrics-dashboard"></a>Metrikdashboard

Wenn Sie die App öffnen, wird zunächst ein Dashboard mit einer Zusammenfassung aller Kapazitäten angezeigt, für die Sie über Administratorrechte verfügen.

![Metrik-App-Dashboard](media/service-admin-premium-monitor-capacity/app-dashboard.png)

Das Dashboard umfasst die folgenden Metriken:

| **Berichtsabschnitt** | **Metriken** |
| --- | --- |
| **Systemübersicht** |  Version der Anwendung<br>  Anzahl der Kapazitäten, die Sie als Administrator betreuen<br>  Anzahl der Arbeitsbereiche in Ihren Kapazitäten, die Metriken melden<br>  Mittlere Arbeitsspeichernutzung in GB über die letzten sieben Tage<br>  Maximale Arbeitsspeichernutzung in GB über die letzten sieben Tage<br>  Lokale Uhrzeit, zu der die maximale Arbeitsspeichernutzung aufgetreten ist<br>  Anzahl der Fälle, bei denen die CPU-Auslastung in den letzten sieben Tagen 80 % des Schwellenwerts überschritten hat, unterteilt in 3-Minuten-Abschnitte<br>  Häufigste Zeiten, zu denen die CPU-Auslastung in den letzten sieben Tagen 80 % überschritten hat, unterteilt in 1-Stunden-Abschnitte<br>  Lokale Uhrzeit, zu der die CPU am häufigsten 80 % innerhalb einer Stunde überschritten hat |
| **Datasetübersicht** |  Gesamtzahl der Datasets über alle Arbeitsbereiche in Ihren Kapazitäten<br>  Anzahl der Fälle, bei denen Direktabfragen/Liveverbindungen 80 % der Schwellenwerte innerhalb der letzten sieben Tage überschritten haben, aufgeteilt in 3-Minuten-Abschnitte<br>  Häufigste Zeiten, zu denen Direktabfragen/Liveverbindungen 80 % überschritten haben, unterteilt in 1-Stunden-Abschnitte<br>  Lokale Uhrzeit, zu der Direktabfragen/Liveverbindungen am häufigsten 80 % innerhalb einer Stunde überschritten haben<br>  Gesamtanzahl der Aktualisierungen in den letzten sieben Tagen<br>  Die durchschnittliche Wartezeit für Aktualisierungen ist die durchschnittliche Verzögerung zwischen geplanter Zeit und Start der Aktualisierung in Minuten<br>  Die durchschnittliche Aktualisierungsdauer ist die Zeit bis zum Abschluss der Aktualisierung in Minuten<br>  Gesamtanzahl der ausgeführten Abfragen in den letzten sieben Tagen<br>  Durchschnittliche Wartezeit: die Zeit in Millisekunden, während der eine Abfrage vor dem Beginn der Ausführung auf Systemressourcen gewartet hat<br>  Durchschnittliche Abfragedauer: die Zeit in Millisekunden bis zum Abschluss des Abfrage<br>  Gesamtanzahl der entfernten Modelle aufgrund von Speicherauslastung<br>  Durchschnittsgröße von Datasets <br>  Anzahl der durchschnittlich im Arbeitsspeicher geladenen Datasets |
| **Datenflussübersicht** |  Gesamtzahl der Datenflüsse über alle Arbeitsbereiche in Ihren Kapazitäten<br>  Gesamtanzahl der Aktualisierungen in den letzten sieben Tagen<br>  Die durchschnittliche Wartezeit für Aktualisierungen ist die durchschnittliche Verzögerung zwischen geplanter Zeit und Start der Aktualisierung in Minuten<br>  Die durchschnittliche Aktualisierungsdauer ist die Zeit bis zum Abschluss der Aktualisierung in Minuten |
| **Paginierter Bericht – Übersicht** |  Gesamtzahl der paginierten Berichte über alle Arbeitsbereiche in Ihren Kapazitäten<br>  Gesamtzahl der Fälle, in denen alle Berichte von Benutzern angezeigt wurden<br>  Gesamtzahl der Zeilen mit Daten in allen Berichten<br>  Gesamtzeit in Millisekunden für alle Phasen (Abrufen, Verarbeiten und Rendern von Daten) für alle Berichte |
|  |  |

### <a name="metrics-report"></a>Metrikbericht

Klicken Sie auf das Dashboard, um zum zugrunde liegenden Bericht zu gelangen. Am unteren Rand des Berichts finden Sie fünf Registerkarten:

* [**Datasets:**](#datasets) Hier finden Sie ausführliche Metriken zur Integrität der Power BI-Datasets in Ihren Kapazitäten.

* [**Paginierte Berichte:**](#paginated-reports) Hier finden Sie ausführliche Metriken zur Integrität der paginierten Berichte in Ihren Kapazitäten.

* [**Dataflows:**](#dataflows) Hier finden Sie ausführliche Aktualisierungsmetriken für Dataflows in Ihren Kapazitäten.

* [**Ressourcenverbrauch:**](#resource-consumption) Hier finden Sie Metriken zur Gesamtkapazität, einschließlich Arbeitsspeicher und hoher CPU-Auslastung.

* [**IDs und Info:**](#ids-and-info) Hier finden Sie die Namen, IDs und Besitzer von Kapazitäten, Arbeitsbereichen und Workloads.

Auf jeder Registerkarte lassen sich die Metriken nach Kapazität und Datumsbereich filtern. Wenn keine Filter ausgewählt sind, zeigt der Bericht standardmäßig die Metriken der letzten Woche für alle Kapazitäten an, die Metriken melden. 

#### <a name="datasets"></a>Datasets

Verwenden Sie die Schaltflächen oben auf der Registerkarte **Datasets**, um zu verschiedenen Bereichen zu navigieren: **Aktualisierungen**, **Abfragedauern**, **Abfragewartezeiten** und **Datasets**.

##### <a name="refreshes-area"></a>Bereich „Refreshes“ (Aktualisierungen)

Der Bereich **Aktualisierungen** enthält die folgenden Metriken.

| **Berichtsabschnitt** | **Metriken** |
| --- | --- |
| **Zuverlässigkeit der Aktualisierung** |  Gesamtanzahl: alle Aktualisierungen für jedes Dataset<br>  Zuverlässigkeit: Prozentsatz der Aktualisierungen, die für jedes Dataset ausgeführt wurden<br>  Durchschnittliche Wartezeit: die durchschnittliche Verzögerung zwischen geplanter Zeit und Start der Datasetaktualisierung in Minuten<br>  Maximale Wartezeit: die maximale Wartezeit für das Dataset in Minuten <br>  Durchschnittliche Dauer: die durchschnittliche Dauer in Minuten für die Aktualisierung des Datasets<br>  Maximale Dauer: die Dauer der längsten Datasetaktualisierung in Minuten |
| **Top 5 Datasets nach durchschnittlicher Aktualisierungsdauer** |  Die fünf Datasets mit der längsten durchschnittlichen Aktualisierungsdauer in Minuten |
| **Top 5 Datasets nach durchschnittlicher Wartezeit** |  Die fünf Datasets mit der längsten durchschnittlichen Aktualisierungswartezeit in Minuten |
| **Durchschnittliche stündliche Aktualisierungswartezeiten** |  Die durchschnittliche Aktualisierungswartezeit, unterteilt in Stunden, Angabe in Ortszeit. Mehrere Spitzen mit langen Aktualisierungswartezeiten weisen auf eine hohe Auslastung der Kapazität hin. |
| **Stündliche Aktualisierungen und Arbeitsspeicherverbrauch** |  Erfolgreiche Vorgänge, Fehler und Arbeitsspeicherverbrauch, unterteilt in Stunden, Angabe in Ortszeit |
|  |  |

##### <a name="query-durations-area"></a>Bereich „Query Durations“ (Abfragedauer) 

Der Bereich **Abfragedauer** enthält die folgenden Metriken.

| **Berichtsabschnitt** | **Metriken** |
| --- | --- |
| **Abfragedauer** |  Daten in diesem Bereich sind nach Datasets, Arbeitsbereich und Stunden für die letzten sieben Tage unterteilt<br>  Gesamt: Gesamtzahl der Abfragen, die für das Dataset ausgeführt werden<br>  Durschnitt: die durchschnittliche Abfragedauer für das Dataset in Millisekunden<br>  Maximal: die längste Abfragedauer für das Dataset in Millisekunden|
| **Verteilung der Abfragedauer** |  Das Histogramm der Abfragedauer ist nach der Dauer (in Millisekunden) in die folgenden Kategorien unterteilt: <= 30 ms, 30–100 ms, 100–300 ms, 300 ms bis 1 s, 1–3 s, 3–10 s, 10–30 s und > 30 s. Lange Ausführungsdauern und lange Wartezeiten sind ein Hinweis auf sich erschöpfende Kapazität. Es kann aber auch bedeuten, dass ein einzelnes Dataset Probleme verursacht und weitere Untersuchungen erforderlich sind. |
| **Top 5 Datasets nach durchschnittlicher Dauer** |  Die fünf Datasets mit der längsten durchschnittlichen Abfragedauer in Millisekunden |
| **Direkte Abfrage/Liveverbindungen (> 80 % Auslastung)** |  Häufigkeit einer CPU-Auslastung von über 80 % durch eine direkte Abfrage oder Liveverbindung, unterteilt in Stunden, Angabe in Ortszeit |
| **Verteilung der stündlichen Abfragedauer** |  Abfrageanzahl und durchschnittliche Dauer (in Millisekunden) im Vergleich zum Arbeitsspeicherverbrauch in GB, unterteilt in Stunden, Angabe in Ortszeit |
|  |  |

##### <a name="query-waits-area"></a>Bereich „Query Waits“ (Abfragewartezeit)

Der Bereich **Abfragewartezeit** enthält die folgenden Metriken.

| **Berichtsabschnitt** | **Metriken** |
| --- | --- |
| **Abfragewartezeiten** |  Daten in diesem Bereich sind nach Datasets, Arbeitsbereich und Stunden für die letzten sieben Tage unterteilt<br>  Gesamt: Gesamtzahl der Abfragen, die für das Dataset ausgeführt werden<br>  Anzahl der Wartevorgänge: Anzahl von Abfragen im Dataset, die vor der Ausführung auf Systemressourcen gewartet haben <br>  Durschnitt: die durchschnittliche Abfragewartezeit für das Dataset in Millisekunden<br>  Maximal: die längste Abfragewartezeit für das Dataset in Millisekunden|
| **Verteilung der Wartezeit** |  Das Histogramm der Abfragedauer ist nach der Dauer (in Millisekunden) in die folgenden Kategorien unterteilt: <= 50 ms, 50–100 ms, 100–200 ms, 200–400 ms, 400 ms bis 1 s, 1–5 s und > 5 s |
| **Top 5 Datasets nach durchschnittlicher Wartezeit** |  Die fünf Datasets mit der längsten durchschnittlichen Wartezeit bis zum Start der Ausführung einer Abfrage in Millisekunden |
| **Stündliche Abfragewartevorgänge und -zeiten** |  Anzahl von Abfragewartevorgängen und durchschnittliche Wartezeit (in Millisekunden) im Vergleich zum Arbeitsspeicherverbrauch in GB, unterteilt in Stunden, Angabe in Ortszeit |
|  |  |

##### <a name="datasets-area"></a>Bereich „Datasets“

Der Bereich **Datasets** enthält die folgenden Metriken.

| **Berichtsabschnitt** | **Metriken** |
| --- | --- |
| **Anzahl von entfernten Datasets** |  Gesamt: Gesamtzahl der *entfernten* Datasets für jede Kapazität. Wenn eine Kapazität Arbeitsspeicherauslastung unterliegt, entfernt der Knoten mindestens ein Dataset aus dem Arbeitsspeicher. Datasets, die inaktiv sind (ohne derzeit ausgeführten Abfrage- oder Aktualisierungsvorgang), werden zuerst entfernt. Anschließend orientiert sich die Entfernungsreihenfolge an den „am seltensten verwendeten“ Datasets.|
| **Stündlich entfernte Datasets und Arbeitsspeicherverbrauch** |  Entfernte Datasets im Vergleich zum Arbeitsspeicherverbrauch in GB, unterteilt in Stunden, Angabe in Ortszeit |
| **Anzahl der stündlich geladenen Datasets** |  Anzahl der in den Arbeitsspeicher geladenen Datasets im Vergleich zum Arbeitsspeicherverbrauch in GB, unterteilt in Zeitfenster, Angabe in Ortszeit |
| **Prozentsatz des verbrauchten Arbeitsspeichers** |  Gesamtanzahl der aktiven Datasets im Arbeitsspeicher, angegeben als Prozentsatz des gesamten Arbeitsspeichers. Das Delta zwischen den aktiven und allen definierten Datasets, die entfernt werden können. Angabe in Stunden für die letzten sieben Tage. |
| **Datengrößen**  |  Maximale Größe: die maximale Größe des Dataset in MB für den angezeigten Zeitraum |
|  |  |

#### <a name="paginated-reports"></a>Paginierte Berichte

Die Registerkarte **Paginierte Berichte** zeigt ausführliche Metriken zur Integrität der paginierten Berichte in Ihren Kapazitäten an.

| **Berichtsabschnitt** | **Metriken** |
| --- | --- |
| **Verwendung gesamt** |  Aufrufe gesamt: Häufigkeit der Berichtaufrufe durch Benutzer<br>  Zeilenanzahl: Anzahl von Datenzeilen im Bericht<br>  Abrufe (durchschn.): die durchschnittlich benötigte Zeit in Millisekunden zum Abrufen von Daten für den Bericht. Eine lange Dauer kann auf langsame Abfragen oder andere Probleme mit der Datenquelle hinweisen. <br>  Verarbeitung (durchschn.): die durchschnittlich benötigte Zeit zum Verarbeiten von Daten für einen Bericht in Millisekunden<br> Rendering (durchschn.): die durchschnittlich benötigte Zeit zum Rendern eines Berichts im Browser in Millisekunden<br>  Gesamtzeit: von allen Phasen des Berichts benötigte Zeit in Millisekunden|
| **Top 5 Berichte nach durchschnittlicher Datenabrufzeit** |  Die fünf Berichte mit der längsten durchschnittlichen Datenabrufzeit in Millisekunden |
| **Top 5 Berichte nach durchschnittlicher Berichtverarbeitungsdauer** |  Die fünf Berichte mit der längsten durchschnittlichen Berichtverarbeitungsdauer in Millisekunden |
| **Stündliche Dauer** |  Datenabruf im Vergleich zur Verarbeitungs- und Renderingdauer, unterteilt in Stunden, Angabe in Ortszeit |
| **Stündliche Ergebnisse** |  Erfolgreiche Vorgänge, Fehler und Arbeitsspeicherverbrauch, unterteilt in Stunden, Angabe in Ortszeit |
|  |  |

#### <a name="dataflows"></a>Dataflows

Die Registerkarte **Dataflows** zeigt ausführliche Aktualisierungsmetriken für Dataflows in Ihren Kapazitäten.

| **Berichtsabschnitt** | **Metriken** |
| --- | --- |
| **Aktualisierung** |  Gesamt: alle Aktualisierungen für jeden Dataflow<br>  Zuverlässigkeit: Prozentsatz der Aktualisierungen, die für jeden Dataflow ausgeführt wurden<br>  Durchschnittliche Wartezeit: die durchschnittliche Verzögerung zwischen geplanter Zeit und Start der Datenflussaktualisierung in Minuten<br>  Maximale Wartezeit: maximale Wartezeit für den Datenfluss in Minuten <br>  Durchschnittliche Dauer: die durchschnittliche Dauer in Minuten für die Aktualisierung des Datenflusses<br>  Maximale Dauer: die Dauer der längsten Datenflussaktualisierung in Minuten |
| **Top 5 Dataflows nach durchschnittlicher Aktualisierungsdauer** |  Die fünf Dataflows mit der längsten durchschnittlichen Aktualisierungsdauer in Minuten |
| **Top 5 Dataflows nach durchschnittlicher Wartezeit** |  Die fünf Dataflows mit der längsten durchschnittlichen Aktualisierungswartezeit in Minuten |
| **Durchschnittliche stündliche Aktualisierungswartezeiten** |  Die durchschnittliche Aktualisierungswartezeit, unterteilt in Stunden, Angabe in Ortszeit. Mehrere Spitzen mit langen Aktualisierungswartezeiten weisen auf eine hohe Auslastung der Kapazität hin. |
| **Stündliche Aktualisierungen und Arbeitsspeicherverbrauch** |  Erfolgreiche Vorgänge, Fehler und Arbeitsspeicherverbrauch, unterteilt in Stunden, Angabe in Ortszeit |
|  |  |

#### <a name="resource-consumption"></a>Ressourcenverbrauch

Die Registerkarte **Ressourcenverbrauch** zeigt die CPU-Auslastung und den Arbeitsspeicherverbrauch für alle Kapazitäten und Workloads.

| **Berichtsabschnitt** | **Metriken** |
| --- | --- |
| **CPU-Auslastung** |  Auslastung nach Arbeitsauslastung als Prozentsatz der gesamten CPU-Kapazität. Angabe in Stunden für die letzten sieben Tage. |
| **Arbeitsspeicherverbrauch** |  Arbeitsspeicherverbrauch in GB nach Arbeitsauslastung (durchgezogene Linien) im Vergleich zu Arbeitsauslastungsgrenzen (gepunktete Linie). Angabe in Stunden für die letzten sieben Tage. |
|  |  |

#### <a name="ids-and-info"></a>IDs und Info

Die Registerkarte **IDs und Info** zeigt die Namen, IDs und Besitzer von Kapazitäten, Arbeitsbereichen und Workloads.


## <a name="monitor-power-bi-embedded-capacity"></a>Überwachen einer Power BI Embedded-Kapazität

Sie können die Power BI Premium-Kapazitätsmetriken-App zum Überwachen von Kapazitäten mit *A-SKU* in Power BI Embedded verwenden. Diese Kapazitäten werden im Bericht angezeigt, sofern Sie ein Administrator der Kapazität sind. Die Aktualisierung des Berichts ist jedoch nur erfolgreich, wenn Sie Power BI bestimmte Berechtigungen für Ihre A-SKUs erteilen:

1. Öffnen Sie Ihre Kapazität im Azure-Portal.

1. Klicken Sie auf **Zugriffssteuerung (IAM)**, und fügen Sie die App „Power BI Premium“ zur Rolle „Leser“ hinzu. Wenn Sie den Namen der App nicht finden, können Sie sie auch per Client-ID hinzufügen: cb4dc29f-0bf4-402a-8b30-7511498ed654.

    ![Berechtigungen für Power BI Embedded](media/service-admin-premium-monitor-capacity/embedded-permissions.png)

> [!NOTE]
> Sie können die Nutzung der Power BI Embedded-Kapazität in der App oder im Azure-Portal überwachen, nicht jedoch im Power BI-Verwaltungsportal.


## <a name="next-steps"></a>Nächste Schritte

> [!div class="nextstepaction"]
> [Verwaltung und Optimierung der Power BI Premium-Kapazitätsressource](service-premium-understand-how-it-works.md)
