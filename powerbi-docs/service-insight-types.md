---
title: "Von Power BI unterstützte Einblicke"
description: "Schnelle Einblicke und „Einblicke anzeigen“ in Power BI"
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 12/20/2017
ms.author: mihart
ms.openlocfilehash: 53e5e67da9bacd9fc9dcbb770747823647aa3a3c
ms.sourcegitcommit: 6ea8291cbfcb7847a8d7bc4e2b6abce7eddcd0ea
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="types-of-insights-supported-by-power-bi"></a>Von Power BI unterstützte Einblicke
## <a name="how-does-insights-work"></a>Wie funktionieren Einblicke?
Power BI durchsucht schnell verschiedene Teilmengen des Datasets unter Verwendung eines hoch entwickelten Algorithmus, um potenziell interessante Einblicke zu gewinnen. Power BI untersucht in einer festgelegten Zeit möglichst große Mengen des Datasets.

Sie können Einblicke für ein Dataset oder eine Dashboard-Kachel ausführen.   

## <a name="what-types-of-insights-can-we-find"></a>Nach welchen Typen von Informationen kann gesucht werden?
Im Folgenden finden Sie einige der verwendeten Algorithmen:

## <a name="category-outliers-topbottom"></a>Kategorieausreißer (oben/unten)
Hebt die Fälle hervor, in denen für eine Messung im Modell ein oder zwei Elemente einer Dimension wesentlich größere Werte als andere Elemente der Dimension haben.  

![](media/service-insight-types/pbi_auto_insight_types_category_outliers.png)

## <a name="change-points-in-a-time-series"></a>Änderungspunkte in einer Zeitreihe
Hebt hervor, wenn es signifikante Trendänderungen in einer Zeitreihe von Daten gibt.

![](media/service-insight-types/pbi_auto_insight_types_changepoint.png)

## <a name="correlation"></a>Korrelation
Erkennt Fälle, in denen mehrere Messungen eine Korrelation zwischen diesen Messungen zeigen, wenn diese an einer Dimension im Dataset dargestellt werden.

![](media/service-insight-types/pbi_auto_insight_types_correlation.png)

## <a name="low-variance"></a>Geringe Abweichung
Erkennt Fälle, in denen Datenpunkte nicht stark vom Mittelwert abweichen.

![](media/service-insight-types/power-bi-low-variance.png)

## <a name="majority-major-factors"></a>Mehrheit (Hauptfaktoren)
Sucht nach Fällen, in denen eine Mehrheit eines Gesamtwerts beim Aufschlüsseln in eine andere Dimension einem einzelnen Faktor zugeordnet werden kann.  

![](media/service-insight-types/pbi_auto_insight_types_majority.png)

## <a name="overall-trends-in-time-series"></a>Allgemeine Trends in Zeitreihen
Entdeckt Trends nach oben oder unten in Zeitreihendaten.

![](media/service-insight-types/pbi_auto_insight_types_trend.png)

## <a name="seasonality-in-time-series"></a>Saisonabhängigkeit in Zeitreihen
Sucht periodische Muster in Zeitreihendaten, z. B. wöchentliche, monatliche oder jährliche Saisonabhängigkeit.

![](media/service-insight-types/pbi_auto_insight_types_seasonality_new.png)

## <a name="steady-share"></a>Stetiger Anteil
Hebt Fälle hervor, in denen eine Beziehung von übergeordneten und untergeordneten Elementen zwischen dem Anteil eines untergeordneten Werts in Bezug auf den Gesamtwert des übergeordneten Elements für eine kontinuierliche Variable vorhanden ist.

![](media/service-insight-types/pbi_auto_insight_types_steadyshare.png)

## <a name="time-series-outliers"></a>Zeitreihenausreißer
Erkennt in Daten auf einer Zeitreihe, wenn bestimmte Datums- oder Zeitangaben mit sich deutlich von den übrigen Daten unterscheidenden Werten vorliegen.

![](media/service-insight-types/pbi_auto_insight_types_time_series_outliers.png)

## <a name="next-steps"></a>Nächste Schritte
[Power BI-Einblicke](service-insights.md)

Wenn Sie ein Dataset besitzen, können Sie es [für Einblicke optimieren](service-insights-optimize.md).

Weitere Fragen? [Wenden Sie sich an die Power BI-Community](http://community.powerbi.com/)

