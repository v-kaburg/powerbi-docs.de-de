---
title: Überwachen von Power BI Premium-Kapazitäten mithilfe des Verwaltungsportals
description: Verwenden des Power BI-Verwaltungsportals zum Überwachen von Premium-Kapazitäten.
author: minewiskan
ms.author: owend
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 02/05/2019
LocalizationGroup: Premium
ms.openlocfilehash: 59097c07719e4bb8db188e8a86db377076aea7a9
ms.sourcegitcommit: 54d44deb6e03e518ad6378656c769b06f2a0b6dc
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/07/2019
ms.locfileid: "55794117"
---
# <a name="monitor-capacities-in-the-admin-portal"></a>Überwachen von Kapazitäten im Verwaltungsportal

In diesem Artikel wird beschrieben, wie Sie den Einstellungsbereich „Kapazität“ im Verwaltungsportal verwenden, um einen schnellen Überblick über die Leistung Ihrer Kapazität zu erhalten.  Die Verwendung der [Power BI Premium-Kapazitätsmetriken](service-admin-premium-monitor-capacity.md)-App, um die ausführlichsten Metriken zu Ihrer Kapazität zu erhalten.

## <a name="capacity-metrics"></a>Kapazitätsmetriken

Der Bereich **Kapazitätseinstellungen** im Verwaltungsportal bietet Messanzeigen in Bezug auf die Lasten und die von Ihrer Kapazität verwendeten Ressourcen für die letzten 7 Tage. Diese vier Kacheln arbeiten mit einem Zeitfenster von 1 Stunde. Sie zeigen an, wie viele Stunden die zugehörige Metrik in den vergangenen 7 Tagen 80% überschritten hat. Diese Metrik weist auf eine potenzielle Beeinträchtigung für den Endbenutzer hin.

![Nutzung in 7 Tagen](media/service-admin-premium-monitor-capacity/usage-in-days.png)

| **Metrik** | **Beschreibung** |
| --- | --- |
| CPU |Häufigkeit, mit der die CPU eine Auslastung von 80 % überschritten hat. |
| Speicherüberlastung |Zeigt die Speicherauslastung Ihrer Back-End-Kerne. Dies ist insbesondere eine Metrik dazu, wie oft Datasets aufgrund hoher Speicherauslastung bei Verwenden mehrerer Datasets aus dem Arbeitsspeicher entfernt werden. |
| Speicherauslastung |Durchschnittliche Arbeitsspeicherauslastung in Gigabytes (GB). |
| DQ/s | Häufigkeit, mit der die Anzahl von „Direkte Abfrage“- und Liveverbindungen 80 % des Grenzwerts überschritten hat. <br>  Die Gesamtzahl von Abfragen mit DirectQuery und Liveverbindungen pro Sekunde ist eingeschränkt. Die Grenzwerte betragen 30/s für P1, 60/s für P2 und 120/s für P3.  Die Anzahl von Abfragen des Typs „Direkte Abfrage“ und „Liveverbindung“ werden zur Drosselung hinzu gerechnet. Wenn Sie z.B. 15 direkte Abfragen und 15 Liveverbindungen in einer Sekunde haben, ist die Begrenzung erreicht.<br> Dies gilt sowohl für lokale als auch für Cloudverbindungen. |
|  |  |

Metriken spiegeln die Auslastung in der letzten Woche wider.  Wenn Sie eine detailliertere Ansicht der Metriken wünschen, können Sie dies tun, indem Sie auf eine der Zusammenfassungskacheln klicken.  Sie gelangen zu detaillierten Diagrammen für jede der Metriken für Ihre Premium-Kapazität. Das folgende Diagramm zeigt Details zur CPU-Metrik.

![Ausführlicher Nutzungsdiagramm zur CPU](media/service-admin-premium-monitor-capacity/premium-usage-detailed-chart-cpu.png)

Diese Diagramme sind für die letzte Woche stündlich zusammengefasst und können Ihnen helfen zu ermitteln, wann bestimmte leistungsbezogene Ereignisse in Ihrer Premium-Kapazität aufgetreten sind.

Sie können auch die für jede der Metriken zugrunde liegenden Daten in eine CSV-Datei exportieren.  Dieser Export liefert Ihnen im Drei-Minuten-Takt detaillierte Informationen für jeden Tag der vergangenen Woche.

## <a name="next-steps"></a>Nächste Schritte

Nachdem Sie die Überwachung von Power BI Premium-Kapazitäten kennengelernt haben, können Sie sich über das Optimieren von Kapazitäten informieren.

> [!div class="nextstepaction"]
> [Verwaltung und Optimierung der Power BI Premium-Kapazitätsressource](service-premium-understand-how-it-works.md)
