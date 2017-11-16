---
title: "Von Power BI unterstützte schnelle Einblicke"
description: Schnelle Einblicke mit Power BI.
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
ms.date: 09/03/2017
ms.author: mihart
ms.openlocfilehash: 13f5614cf121b17d8ae4dff9653f5789372f7f49
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2017
---
# <a name="types-of-quick-insights-supported-by-power-bi"></a>Von Power BI unterstützte schnelle Einblicke
## <a name="how-does-quick-insights-work"></a>Wie funktionieren schnelle Einblicke?
Power BI durchsucht schnell verschiedene Teilmengen des Datasets unter Verwendung eines hoch entwickelten Algorithmus, um potenziell interessante Einblicke zu gewinnen. Power BI untersucht in einer festgelegten Zeit möglichst große Mengen des Datasets.

Sie können schnelle Einblicke für ein Dataset oder eine Kachel ausführen (Verwandte Einblicke).   

## <a name="what-types-of-quick-insights-can-we-find"></a>Nach welchen Typen von schnellen Einblicken kann gesucht werden?
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
[Schnelle Einblicke in Power BI](service-insights.md)

Wenn Sie ein Dataset besitzen, können Sie es [für Schnelleinblicke optimieren](service-insights-optimize.md).

Weitere Fragen? [Wenden Sie sich an die Power BI-Community](http://community.powerbi.com/)

