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
ms.date: 08/29/2018
LocalizationGroup: Premium
ms.openlocfilehash: 8e19bc596bef3862dca79ac92ffbd74954a9c756
ms.sourcegitcommit: 6be2c54f2703f307457360baef32aee16f338067
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2018
ms.locfileid: "43300159"
---
# <a name="monitor-power-bi-premium-capacities-in-your-organization"></a>Überwachen von Power BI Premium-Kapazitäten in Ihrer Organisation

Dieser Artikel bietet einen Überblick über die Überwachung der Metriken für Ihre Power BI Premium-Kapazitäten. Die Überwachung der Kapazitätsauslastung bietet Ihnen einen fundierten Ansatz für die Verwaltung Ihrer Kapazitäten. 

Sie können die Kapazität mithilfe der Power BI Premium Capacity Metrics-App oder dem Verwaltungsportal überwachen. Wir empfehlen die Verwendung der App, weil diese sehr viel umfangreichere Informationen bietet, aber dieser Artikel deckt beide Optionen ab.

## <a name="install-the-premium-capacity-metrics-app"></a>Installieren der Premium Capacity Metrics-App

Sie können direkt zur [Premium Capacity Metrics-App](https://app.powerbi.com/groups/me/getapps/services/capacitymetrics) wechseln oder diese wie andere Apps in Power BI installieren.

> [!IMPORTANT]
> Um diese App zu installieren und zu verwenden, müssen Sie als Kapazitätsadministrator für mindestens eine Kapazität fungieren. Power BI-Administratorrechte reichen nicht aus. 

1. Klicken Sie in Power BI auf **Apps**.

    ![Wechsel zu „Apps“](media/service-admin-premium-monitor-capacity/apps.png)

2. Klicken Sie auf der rechten Seite auf **Apps abrufen**.

3. Suchen Sie in der Kategorie **Apps** nach der **Power BI Premium Capacity Metrics-App**.

4. Rufen Sie die App ab, um sie zu installieren.

Nachdem Sie die App installiert haben, können Sie Metriken zu den Kapazitäten in Ihrer Organisation anzeigen. Sehen wir uns einige der wichtigsten Metriken an, die zur Verfügung gestellt werden.

## <a name="use-the-metrics-app"></a>Verwenden der Metriken-App 
Wenn Sie die App öffnen, wird zunächst ein Dashboard mit einer Zusammenfassung aller Kapazitäten angezeigt, für die Sie über Administratorrechte verfügen.

![Übersicht der Premium-Berichte](media/service-admin-premium-monitor-capacity/app-dashboard.png)

### <a name="filtering"></a>Filter

Auf der Registerkarte **Filters applied to all pages** (Auf alle Seiten angewendete Filter) können Sie eine Kapazität, ein Dataset und/oder einen Datumsbereich innerhalb der letzten 7 Tage auswählen. Diese Filter wenden die Auswahl auf alle relevanten Seiten und Kacheln in diesem Bericht an. Wenn keine Auswahl getroffen wurde, zeigt der Bericht standardmäßig die Metriken der letzten Woche für alle Kapazitäten an, die Sie besitzen.

![Übersicht der Premium-Berichte](media/service-admin-premium-monitor-capacity/premium-report-overview.png)

### <a name="summary-tab"></a>Registerkarte „Summary“ (Zusammenfassung)

Auf der Registerkarte **Summary** (Zusammenfassung) wird eine Ansicht der Kapazität basierend auf Entitäten, System und Datasets angezeigt.

![Filter, die auf alle Seiten angewendet werden](media/service-admin-premium-monitor-capacity/premium-summary-report.png)

| **Bereich** | **Metriken** |
| --- | --- |
| **Entities** (Entitäten) | * Die Anzahl von Kapazitäten, die Sie besitzen<br> * Die Anzahl von Datasets in Ihrer Kapazität<br> * Die Anzahl von Arbeitsbereichen in Ihrer Kapazität |
| **System** | * Die durchschnittliche Arbeitsspeicherverwendung in GB in den letzten 7 Tagen<br> * Der höchste Arbeitsspeicherverbrauch in GB in den letzten 7 Tagen, mit Angabe der Uhrzeit des Auftretens<br> * Die Anzahl von Vorkommen, bei denen die CPU-Auslastung in den letzten 7 Tagen 80% des Schwellenwerts überschritten hat, unterteilt in 3-Minuten-Abschnitte<br> * Häufigste Zeiten, zu denen die CPU-Auslastung in den letzten 7 Tagen 80% überschritten hat, unterteilt in 1-Stunden-Abschnitte und mit Angabe der Uhrzeit des Auftretens<br> * Die Anzahl von Vorkommen, bei denen direkte Abfragen/Liveverbindungen in den letzten 7 Tagen 80% des Schwellenwerts überschritten haben, unterteilt in 3-Minuten-Abschnitte<br> * Häufigste Zeiten, zu denen direkte Abfragen/Liveverbindungen 80% überschritten haben, unterteilt in 1-Stunden-Abschnitte und mit Angabe der Uhrzeit des Auftretens |
| **Dataset Workloads** (Datasetworkloads) | * Gesamtanzahl der Aktualisierungen in den letzten 7 Tagen<br> * Gesamtanzahl der erfolgreichen Aktualisierungen in den letzten 7 Tagen<br> * Gesamtanzahl der fehlerhaften Aktualisierungen in den letzten 7 Tagen<br> * Gesamtanzahl der fehlerhaften Aktualisierungen aufgrund von Arbeitsspeichermangel<br> * Durchschnittliche Aktualisierungsdauer in Minuten, angegeben als Zeit bis zum Abschluss des Vorgangs<br> * Durchschnittliche Wartezeit für Aktualisierungen in Minuten, angegeben als durchschnittliche Verzögerung zwischen geplanter Zeit und Start des Vorgangs<br> * Gesamtanzahl der ausgeführten Abfragen in den letzten 7 Tagen<br> * Gesamtanzahl der erfolgreichen Abfragen in den letzten 7 Tagen<br> * Gesamtanzahl der fehlerhaften Abfragen in den letzten 7 Tagen<br> * Durchschnittliche Abfragedauer in Minuten, angegeben als Zeit bis zum Abschluss des Vorgangs<br> * Gesamtanzahl der entfernten Modelle aufgrund von Speicherauslastung |
|  |  |

### <a name="refreshes-tab"></a>Registerkarte „Refreshes“ (Aktualisierungen)

Auf der Registerkarte **Refreshes** (Aktualisierungen) werden die abgeschlossenen Aktualisierungen, Erfolgskennzahlen, die durchschnittliche/maximale Wartezeit und die durchschnittliche/maximale Dauer der Aktualisierungen in den letzten 7 Tagen angezeigt, unterteilt nach Datasets. Die zwei unteren Diagramme zeigen die Aktualisierungen und den Arbeitsspeicherverbrauch in GB im Vergleich sowie die durchschnittliche Wartezeit an, unterteilt in 1-Stunden-Abschnitte, angegeben in der Ortszeit. Die oberen Diagramme zeigen die fünf wichtigsten Datasets nach der Gesamtdauer der Aktualisierung des Datasets (Aktualisierungsdauer) und der maximalen Wartezeit bei der Aktualisierung. Mehrere Spitzen bei der Wartezeit für die Aktualisierung weisen auf eine hohe Auslastung der Kapazität hin.

![Premium-Bericht zu Aktualisierungen](media/service-admin-premium-monitor-capacity/premium-refresh-report.png)

### <a name="datasets-tab"></a>Registerkarte „Datasets“

Die Registerkarte **Datasets** zeigt die Entfernung vollständiger Datasets aufgrund von Speicherauslastung nach Stunde an.

![Premium-Bericht zu Datasets](media/service-admin-premium-monitor-capacity/premium-datasets-report.png)

### <a name="system-tab"></a>Registerkarte „System“

Auf der Registerkarte **System** werden eine hohe CPU-Auslastung (Anzahl von Überschreitungen von 80%), eine hohe Auslastung für direkte Abfragen/Liveverbindungen und der Arbeitsspeicherverbrauch angezeigt.

![Premium-Bericht zum System](media/service-admin-premium-monitor-capacity/premium-system-report.png)

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
| Memory Usage |Durchschnittliche Arbeitsspeicherauslastung in Gigabytes (GB). |
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
