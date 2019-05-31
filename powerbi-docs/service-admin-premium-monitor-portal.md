---
title: Überwachen von Power BI Premium-Kapazitäten mithilfe des Verwaltungsportals
description: Verwenden des Power BI-Verwaltungsportals zum Überwachen von Premium-Kapazitäten.
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 04/10/2019
LocalizationGroup: Premium
ms.openlocfilehash: 36b03a67e7c02702a70b6486880cc8eabf93e823
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2019
ms.locfileid: "65564895"
---
# <a name="monitor-capacities-in-the-admin-portal"></a>Überwachen von Kapazitäten im Verwaltungsportal

Die **Integrität** Registerkarte die **kapazitätseinstellungen** Bereich im Verwaltungsportal finden Sie eine Zusammenfassung zu Ihrer Kapazität "und" enabled Workloads Metriken.  

![Registerkarte "Capacity Integrität" im portal](media/service-admin-premium-monitor-portal/admin-portal-health.png)

Wenn Sie eine umfassendere Metriken benötigen, verwenden die [Kapazitätsmetriken für Power BI Premium](service-admin-premium-monitor-capacity.md) app. Die app bietet Drilldown- und filtern, und die ausführlichsten Metriken für nahezu alle Aspekte, die Auswirkung auf die Leistung der Kapazität. Weitere Informationen finden Sie unter [Monitor Premium-Kapazitäten, mit der app](service-admin-premium-monitor-capacity.md).

## <a name="system-metrics"></a>Systemmetriken

Auf der **Integrität** Registerkarte auf der höchsten Ebene, CPU-Auslastung und speicherauslastung bieten einen schnellen Überblick über die wichtigsten Metriken für die Kapazität. Diese Metriken sind kumulativ, einschließlich alle Workloads für die Kapazität aktiviert.

| **Metrik** | **Beschreibung** |
| --- | --- |
| CPU-AUSLASTUNG | Durchschnittliche CPU-Auslastung als Prozentwert des insgesamt verfügbaren CPU. |
| SPEICHERAUSLASTUNG | Die durchschnittliche arbeitsspeicherauslastung in Gigabyte (GB).|

## <a name="workload-metrics"></a>Workloadmetriken

Für jede Workload, die für die Kapazität aktiviert. CPU-Auslastung und speicherauslastung angezeigt werden.

| **Metrik** | **Beschreibung** |
| --- | --- |
| CPU-AUSLASTUNG | Durchschnittliche CPU-Auslastung als Prozentwert des insgesamt verfügbaren CPU. |
| SPEICHERAUSLASTUNG | Die durchschnittliche arbeitsspeicherauslastung in Gigabyte (GB).|

### <a name="detailed-workload-metrics"></a>Ausführliche workloadmetriken

Jede Workload verfügt über zusätzliche Metriken anzuzeigen. Der Typ der gezeigten Metriken hängen von der arbeitsauslastung ab. Um detaillierte Metriken für eine arbeitsauslastung anzuzeigen, klicken Sie auf die erweitern (Pfeil nach unten).

![Workload-Integrität zu erweitern.](media/service-admin-premium-monitor-portal/admin-portal-health-expand.png)

#### <a name="dataflows"></a>Dataflows

##### <a name="dataflow-operations"></a>Datenflussvorgängen

| **Metrik** | **Beschreibung** |
| --- | --- |
| Gesamtanzahl | Die Gesamtanzahl aller Aktualisierungen für jeden Dataflow. |
| Anzahl erfolgreicher Vorgänge | Insgesamt erfolgreiche Aktualisierungen für jeden Datenfluss.|
| Durchschnittliche Dauer (Min.) | die durchschnittliche Dauer in Minuten für die Aktualisierung des Datenflusses |
| Max. Dauer (Min.) | Die Dauer der Dataflowaktualisierung mit der längsten Ausführungsdauer in Minuten. |
| Durchschnittliche Wartezeit (Min.) | Die durchschnittliche Verzögerung zwischen der geplanten Zeit und dem Start einer Dataflowaktualisierung in Minuten. |
| Max. Wartezeit (Min.) | Die maximale Wartezeit für den Dataflow in Minuten.  |

#### <a name="datasets"></a>Datasets

##### <a name="refresh"></a>Aktualisieren

| **Metrik** | **Beschreibung** |
| --- | --- |
| Gesamtanzahl | Die Gesamtanzahl aller Aktualisierungen für jedes Dataset. |
| Anzahl erfolgreicher Vorgänge | Insgesamt erfolgreiche wird für jedes Dataset aktualisiert. |
| Anzahl Fehler | Gesamtanzahl der fehlgeschlagenen Aktualisierungen für jedes Dataset. |
| Erfolgsrate  | Die Anzahl der erfolgreich aktualisiert, geteilt durch die gesamte wird aktualisiert, um zu messen. Zuverlässigkeit. |
| Durchschnittliche Dauer (Min.) | Die durchschnittliche Dauer der Aktualisierung des Datasets in Minuten.  |
| Max. Dauer (Min.) | Die Dauer der Datasetaktualisierung mit der längsten Ausführungsdauer in Minuten. |
| Durchschnittliche Wartezeit (Min.) | Die durchschnittliche Verzögerung zwischen der geplanten Zeit und dem Start einer Datasetaktualisierung in Minuten. |
| Max. Wartezeit (Min.) | Die maximale Wartezeit für das Dataset in Minuten. |

##### <a name="query"></a>Abfrage

| **Metrik** | **Beschreibung** |
| --- | --- |
| Gesamtanzahl | Die Gesamtzahl der Abfragen, die für das Dataset ausgeführt werden. |
| Durchschnittliche Dauer (ms) |die durchschnittliche Abfragedauer für das Dataset in Millisekunden|
| Maximale Dauer (ms) |Die Dauer der Abfrage mit der längsten Ausführungsdauer im Dataset in Millisekunden. |
| Durchschnittliche Wartezeit (ms) |Die durchschnittliche Abfragewartezeit für das Dataset in Millisekunden. |
| Max. Wartezeit (ms) |Die Dauer der Abfrage mit der längsten Wartezeit für das Dataset in Millisekunden. |

##### <a name="eviction"></a>Entfernung

| **Metrik** | **Beschreibung** |
| --- | --- |
| Modell-Anzahl | Die Gesamtzahl der entfernungen von Datasets für diese Kapazität. Wenn eine Kapazität Arbeitsspeicherauslastung unterliegt, entfernt der Knoten mindestens ein Dataset aus dem Arbeitsspeicher. Datasets, die inaktiv sind (ohne derzeit ausgeführten Abfrage- oder Aktualisierungsvorgang), werden zuerst entfernt. Anschließend orientiert sich die Entfernungsreihenfolge an den „am seltensten verwendeten“ Datasets. |

#### <a name="paginated-reports"></a>Paginated Reports

##### <a name="report-execution"></a>Berichtsausführung

| **Metrik** | **Beschreibung** |
| --- | --- |
| Anzahl von Ausführungen  | Die Anzahl der Male, die der Bericht ausgeführt wurden wurde und von Benutzern angezeigt.|

##### <a name="report-usage"></a>Berichte zur Nutzung

| **Metrik** | **Beschreibung** |
| --- | --- |
| Anzahl erfolgreicher Vorgänge | Die Anzahl der Häufigkeit, mit die Anzeige des Berichts durch einen Benutzer. |
| Anzahl Fehler |Die Anzahl der Häufigkeit, mit die Anzeige des Berichts durch einen Benutzer.|
| Zeilenanzahl |Die Anzahl von Datenzeilen im Bericht. |
| Daten abrufen-Dauer (ms) |die durchschnittlich benötigte Zeit in Millisekunden zum Abrufen von Daten für den Bericht. Eine lange Dauer kann auf langsame Abfragen oder andere Probleme mit der Datenquelle hinweisen.  |
| Verarbeitungsdauer (ms) |Die durchschnittlich benötigte Zeit zum Verarbeiten von Daten für einen Bericht in Millisekunden. |
| Rendering-Dauer (ms) |Die durchschnittlich benötigte Zeit zum Rendern eines Berichts im Browser in Millisekunden. |

> [!NOTE]
> Ausführliche Metriken für die **AI** arbeitsauslastung sind noch nicht verfügbar.

## <a name="next-steps"></a>Nächste Schritte

Nachdem Sie die Überwachung von Power BI Premium-Kapazitäten kennengelernt haben, können Sie sich über das Optimieren von Kapazitäten informieren.

> [!div class="nextstepaction"]
> [Optimieren der Power BI Premium-Kapazitäten](service-premium-capacity-optimize.md)
