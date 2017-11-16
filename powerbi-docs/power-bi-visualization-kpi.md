---
title: KPI-Visualisierungen (Tutorial)
description: "Erstellen von KPIs in Power BI"
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: xmja6EpqaO0
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 08/09/2017
ms.author: mihart
ms.openlocfilehash: 23b322c9fbc4c203a5b20aa45bb41c2cb6cb7f0f
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2017
---
# <a name="kpi-visuals-tutorial"></a>KPI-Visualisierungen (Tutorial)
Ein Key Performance Indicator (KPI) ist ein visueller Hinweis, mit dem der Fortschritt in Bezug auf ein messbares Ziel kommuniziert wird. Weitere Informationen über KPIs finden Sie im [Microsoft Developer Network](https://msdn.microsoft.com/library/hh272050).

## <a name="when-to-use-a-kpi"></a>Einsatzmöglichkeiten von KPIs
KPIs sind für folgende Zwecke gut geeignet:

* zum Messen des Fortschritts (wo habe ich Vorsprung, wo bin ich im Rückstand?)
* zum Messen der Entfernung bis zum Ziel (wie groß ist mein Vorsprung oder Rückstand?)   

## <a name="kpi-visual-requirements"></a>Anforderungen für KPI-Visualisierungen
Ein Key Performance Indicator (KPI) basiert auf einer bestimmten Kennzahl und ist so gestaltet, dass sich der aktuelle Wert und der Status einer Metrik im Vergleich zu einem definierten Ziel leicht auswerten lassen. Deshalb wird für eine KPI-Visualisierung eine *Basiskennzahl* benötigt, die im Hinblick auf einen Wert ausgewertet wird, und eine *Zielkennzahl* oder ein Zielwert sowie ein Schwellenwert oder ein Ziel.

> [!NOTE]
> Derzeit muss ein KPI-Dataset Zielwerte für einen KPI enthalten. Wenn Ihr Dataset keinen Zielwert enthält, können Sie Ziele erstellen, indem Sie dem Datenmodell oder der PBIX-Datei ein Excel-Arbeitsblatt mit Zielen hinzufügen.
> 
> 

## <a name="how-to-create-a-kpi"></a>Erstellen eines KPI
Melden Sie sich bei Power BI an, und wählen Sie **Daten abrufen > Beispiele > Analysebeispiel für Einzelhandel**. Im Folgenden wird ein KPI erstellt, der den Fortschritt beim Erreichen von Umsatzzielen misst.

Oder schauen Sie Will beim Erstellen von Einzelmetrik-Visualisierungen wie Messgeräten, Karten und KPIs zu.

<iframe width="560" height="315" src="https://www.youtube.com/embed/xmja6EpqaO0?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>

1. Wählen Sie **Umsatz > Gesamte Einheiten in diesem Jahr**.  Dies wird der Indikator.
2. Fügen Sie **Zeit > Monat** hinzu.  Dies dient zur Darstellung des Trends.
3. WICHTIG: Sortieren Sie das Diagramm nach **Monat**. Nachdem Sie die Visualisierung in einen KPI konvertiert haben, ist keine Option zum Sortieren vorhanden.
4. Wandeln Sie die Visualisierung in einen KPI um, indem Sie im Bereich „Visualisierungen“ das KPI-Symbol auswählen.
   
    ![](media/power-bi-visualization-kpi/power-bi-kpi-icon.png)
5. Fügen Sie ein Ziel hinzu. Verwenden Sie den Umsatz des letzten Jahres als Ziel. Ziehen Sie **Gesamte Einheiten im letzten Jahr** auf das Feld **Ziel**.
   
    ![](media/power-bi-visualization-kpi/power-bi-kpi.png)
6. Optional können Sie den KPI formatieren. Wählen Sie dazu das Farbrollensymbol aus, um den Formatierungsbereich zu öffnen.
   
   * **Indikator**: Dient zum Steuern der Anzeigeeinheiten und der Dezimalstellen des Indikators.
   * **Trendachse**: Wenn hier **Ein** festgelegt ist, wird die Trendachse als Hintergrund der KPI-Visualisierung angezeigt.  
   * **Ziele**: Wenn hier **Ein** festgelegt ist, wird das Ziel in der Visualisierung angezeigt, und die Entfernung zum Ziel wird als Prozentsatz dargestellt.
   * **Status**: Bei einigen KPIs werden höhere Werte als *besser* betrachtet, und bei anderen gelten niedrigere Werte als *besser*. Nehmen Sie als Beispiel Erlös und Wartezeit. Beim Erlös ist ein höherer Wert besser, während bei der Wartezeit ein höherer Wert meist negativ bewertet wird. Mit diesem Umschalter können Sie das Verhalten des KPI festlegen. Der Standardwert für die Statusauswahl lautet **hoch ist besser**.
7. Wenn der KPI Ihren Wünschen entspricht, [heften Sie ihn an ein Dashboard an](service-dashboard-pin-tile-from-report.md).

Die KPIs stehen Ihnen auch auf Mobilgeräten zur Verfügung, sodass Sie immer am Puls Ihres Unternehmens bleiben.

## <a name="considerations-and-troubleshooting"></a>Zu beachtende Aspekte und Problembehandlung
* Wenn der KPI nicht wie in der Abbildung oben aussieht, haben Sie möglicherweise keine Sortierung nach Monat ausgeführt. Da KPIs über keine Sortieroption verfügen, müssen Sie nach Monat sortieren, *bevor* Sie die Visualisierung in einen KPI umwandeln.

## <a name="next-steps"></a>Nächste Schritte
[Berichte in Power BI](service-reports.md)

[Visualisierungen in Power BI-Berichten](power-bi-report-visualizations.md)

[Power BI – Grundkonzepte](service-basic-concepts.md)

Weitere Fragen? [Wenden Sie sich an die Power BI-Community](http://community.powerbi.com/)

