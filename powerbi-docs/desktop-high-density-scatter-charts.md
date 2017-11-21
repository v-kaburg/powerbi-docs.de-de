---
title: Punktdiagramme mit hoher Dichte in Power BI
description: Punktdiagramme mit hoher Dichte in Power BI
services: powerbi
documentationcenter: 
author: davidiseminger
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
ms.date: 09/06/2017
ms.author: davidi
ms.openlocfilehash: 16c39e646c487789de62d0c030150475c8bb8292
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2017
---
# <a name="high-density-sampling-in-power-bi-scatter-charts"></a>Stichprobenentnahme mit hoher Dichte in Power BI-Punktdiagrammen
Ab der im September 2017 veröffentlichten Version von **Power BI Desktop** und Updates des **Power BI-Diensts** steht ein neuer Stichprobenalgorithmus zur Verfügung, der die Darstellung von Daten mit hoher Dichte in Punktdiagrammen verbessert.

Sie können z.B. ein Punktdiagramm der Verkaufsaktivitäten Ihrer Organisation erstellen, wobei für jedes Ladengeschäft Zehntausende von Datenpunkten pro Jahr vorhanden sind. Ein Punktdiagramm mit derartigen Informationen entnimmt stichprobenartig Daten (wählen Sie eine aussagekräftige Darstellung dieser Daten, um die Verkaufszahlen über die Zeit hinweg darzustellen) aus den verfügbaren Daten und erstellt ein Punktdiagramm, das die zugrunde liegenden Daten veranschaulicht. Dies ist bei Punktdiagrammen mit hoher Dichte eine häufig genutzte Methode. Die Stichprobenentnahme von Daten mit hoher Dichte von Power BI wurde verbessert. Dies wird in diesem Artikel ausführlicher beschrieben.

![](media/desktop-high-density-scatter-charts/high-density-scatter-charts_01.png)

> [!NOTE]
> Der in diesem Artikel beschriebene Algorithmus der **Stichprobenentnahme mit hoher Dichte** gilt für Punktdiagramme in **Power BI Desktop** und im **Power BI-Dienst** und ist in beiden verfügbar.
> 
> 

## <a name="how-high-density-scatter-charts-work"></a>Funktionsweise von Punktdiagrammen mit hoher Dichte
Früher hat **Power BI** zum Erstellen eines Punktdiagramms eine Sammlung von Beispieldatenpunkten im vollständigen Bereich der zugrunde liegenden Daten auf deterministische Weise ausgewählt. In Power BI wurde die erste und die letzte Datenzeile in der Datenreihe des Punktdiagramms ausgewählt, und dann wurden die restlichen Zeilen gleichmäßig unterteilt, sodass im Punktdiagramm insgesamt 3.500 Datenpunkte dargestellt werden. Wenn die Stichprobe beispielsweise 35.000 Zeilen umfasst, werden die erste und letzte Zeile für die Darstellung ausgewählt und außerdem jede zehnte Zeile dargestellt (35.000/10 = jede zehnte Zeile = 3.500 Datenpunkte). Zudem wurden früher NULL-Werte oder nicht darstellbare Punkte (z.B. Textwerte) in Datenreihen nicht angezeigt und somit beim Generieren des Visuals nicht berücksichtigt. Bei einer solchen Stichprobenentnahme basiert die wahrgenommene Dichte des Punktdiagramms auch auf den repräsentativen Datenpunkten. Deshalb war die implizierte visuelle Dichte eine Folge der als Stichprobe entnommenen Datenpunkte und nicht der vollständigen Sammlung der zugrunde liegenden Daten.

Wenn Sie **Stichprobenentnahme mit hoher Dichte** aktivieren, implementiert Power BI einen Algorithmus, der überlappende Punkte ausschließt, und es wird sichergestellt, dass die Punkte im Visual bei der Interaktion mit dem Visual erreicht werden können. Darüber hinaus wird sichergestellt, dass alle Punkte im Dataset im Visual dargestellt werden. So wird nicht nur einfach eine repräsentative Stichprobe, sondern auch der Kontext ausgewählter Punkte dargestellt.

Definitionsgemäß werden Daten mit hoher Dichte als Stichprobe entnommen, um ein schnelles Erstellen von Visuals und deren Interaktivität zu ermöglichen (wenn sich zu viele Datenpunkte in einem Visual befinden, kann sie dadurch verlangsamt und die Sichtbarkeit von Trends beeinträchtigt werden). Das Erstellen des Algorithmus für die Stichprobenentnahme hängt davon ab, wie die Daten entnommen werden, um das beste Visualisierungserlebnis zu bieten und sicherzustellen, dass alle Daten dargestellt werden. Durch den verbesserten Algorithmus in Power BI werden Reaktionsfähigkeit, Darstellung und die Erhaltung von wichtigen Punkten im gesamten Dataset optimal miteinander vereint.

> [!NOTE]
> Punktdiagramme, die **Stichprobenentnahme mit hoher Dichte** verwenden, lassen sich wie alle Punktdiagramme am besten in quadratischen Visuals darstellen.
> 
> 

## <a name="how-the-new-scatter-chart-sampling-algorithm-works"></a>Funktionsweise des neuen Algorithmus der Stichprobenentnahme für Punktdiagramme
Der neue Algorithmus der **Stichprobenentnahme mit hoher Dichte** für Punktdiagramme nutzt Methoden, mit denen die zugrunde liegenden Daten effektiver erfasst und dargestellt und überlappende Punkte ausgeschlossen werden. Hierzu wird mit einem kleinen Radius für jeden Datenpunkt (der visuelle Kreisradius für einen bestimmten Punkt in der Visualisierung) begonnen. Anschließend wird der Radius aller Datenpunkte vergrößert. Wenn sich zwei (oder mehr) Datenpunkte überlappen, werden die überlappenden Datenpunkte durch einen einzelnen Kreis (mit vergrößertem Radius) dargestellt. Der Algorithmus vergrößert den Radius der Datenpunkte weiter, bis der Radiuswert dazu führt, dass im Punktdiagramm eine angemessene Anzahl von Datenpunkten – 3.500 – angezeigt wird.

Die Methoden in diesem Algorithmus stellen sicher, dass Ausreißer im resultierenden Visual dargestellt werden. Der Algorithmus berücksichtigt beim Bestimmen der Überlappung auch die Skalierung, sodass exponentielle Skalierungen gemäß den zugrunde liegenden visualisierten Datenpunkten dargestellt werden.

Der Algorithmus bewahrt zudem die Gesamtform des Punktdiagramms.

> [!NOTE]
> Bei Verwendung des Algorithmus der **Stichprobenentnahme mit hoher Dichte** für Punktdiagramme wird eine *genaue Verteilung* der Daten und *nicht* die implizierte visuelle Dichte angestrebt. Beispielsweise wird eventuell ein Punktdiagramm angezeigt, in dem sich in einem bestimmten Bereich sehr viele Kreise überlappen (Dichte), und Sie nehmen an, dass dort viele Datenpunkte zusammengedrängt sind. Da der Algorithmus für die **Stichprobenentnahme mit hoher Dichte** mit einem einzelnen Kreis viele Datenpunkte darstellen kann, wird die implizierte visuelle Dichte (Clustering) nicht angezeigt. Um weitere Details in einem angegebenen Bereich anzuzeigen, können Sie mit Schiebereglern die Darstellung vergrößern.
> 
> 

Darüber hinaus werden Datenpunkte, die nicht dargestellt werden können (z.B. NULL-Werte oder Textwerte), ignoriert, und stattdessen wird ein anderer Wert ausgewählt, der dargestellt werden kann. Auch dies stellt sicher, dass die richtige Form des Punktdiagramms erhalten bleibt.

### <a name="when-the-standard-algorithm-for-scatter-charts-is-used"></a>Wenn der Standardalgorithmus für Punktdiagramme verwendet wird
Es gibt Situationen, in denen die **Stichprobenentnahme mit hoher Dichte** nicht auf ein Punktdiagramm angewendet werden kann und der ursprüngliche Algorithmus verwendet wird. Dabei handelt es sich um die folgenden Situationen:

* Wenn Sie mit der rechten Maustaste auf **Details** klicken und im daraufhin angezeigten Menü **Elemente ohne Daten anzeigen** auswählen, wird das Punktdiagramm auf den ursprünglichen Algorithmus zurückgesetzt.
  
  ![](media/desktop-high-density-scatter-charts/high-density-scatter-charts_02.png)
* Wenn sich auf der **Wiedergabeachse** Werte befinden, wird das Punktdiagramm auf den ursprünglichen Algorithmus zurückgesetzt.
* Wenn in einem Punktdiagramm die X-und Y-Achse fehlen, wird das Diagramm auf den ursprünglichen Algorithmus zurückgesetzt.
* Wenn im Bereich **Analyse** eine **Verhältnislinie** verwendet wird, wird das Diagramm auf den ursprünglichen Algorithmus zurückgesetzt.
  
  ![](media/desktop-high-density-scatter-charts/high-density-scatter-charts_03.png)

## <a name="how-to-turn-on-high-density-sampling-for-a-scatter-chart"></a>Aktivieren der **Stichprobenentnahme mit hoher Dichte** für ein Punktdiagramm
Wählen Sie zum Aktivieren der **Stichprobenentnahme mit hoher Dichte** ein Punktdiagramm aus, wechseln Sie zum Bereich **Formatierung**, und erweitern Sie die Karte **Allgemein**. Im unteren Bereich der Karte ist ein Schieberegler zum Ein-/Ausschalten mit dem Namen **Stichprobenentnahme mit hoher Dichte** verfügbar. Schieben Sie den Schieberegler auf **Ein**, um den Algorithmus zu aktivieren.

![](media/desktop-high-density-scatter-charts/high-density-scatter-charts_04.png)

> [!NOTE]
> Nachdem der Schieberegler auf „Ein“ geschoben wurde, wird der Algorithmus der **Stichprobenentnahme mit hoher Dichte** in Power BI verwendet, wann immer dies möglich ist. Wenn der Algorithmus nicht verwendet werden kann (z.B. weil Sie auf der *Wiedergabeachse* einen Wert platzieren), bleibt der Schieberegler in der Position **Ein**, obwohl das Diagramm auf den Standardalgorithmus zurückgesetzt wurde. Wenn Sie dann einen Wert von der *Wiedergabeachse* entfernen (oder die Bedingungen sich ändern, sodass der Algorithmus für die Stichprobenentnahme mit hoher Dichte verwendet werden kann), wird automatisch die Stichprobenentnahme mit hoher Dichte für das Diagramm verwendet, da der Schieberegler auf „Ein“ gestellt ist.
> 
> [!NOTE]
> Datenpunkte werden nach dem Index gruppiert und/oder ausgewählt. Das Vorhandensein einer Legende beeinträchtigt nicht die Stichprobenentnahme durch den Algorithmus, es wirkt sich nur auf die Sortierung des Visuals aus.
> 
> 

## <a name="considerations-and-limitations"></a>Überlegungen und Einschränkungen
Der Algorithmus der Stichprobenentnahme mit hoher Dichte ist eine wichtige Verbesserung in Power BI. Es gibt jedoch einige Aspekte, die Sie berücksichtigen sollten, wenn Sie mit Werten hoher Dichte und Punktdiagrammen arbeiten.

* Der Algorithmus der **Stichprobenentnahme mit hoher Dichte** kann nur für Liveverbindungen mit auf dem Power BI-Dienst basierenden Modellen, importierten Modellen oder DirectQuery ausgeführt werden.

## <a name="next-steps"></a>Nächste Schritte
Weitere Informationen über die Stichprobenentnahme mit hoher Dichte in anderen Diagrammen finden Sie im folgenden Artikel.

* [Strichprobenentnahme für visuelle Linienelemente mit hoher Dichte in Power BI](desktop-high-density-sampling.md)

