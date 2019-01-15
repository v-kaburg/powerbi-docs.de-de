---
title: Punkt-, Blasen- und Punktplotdiagramme in Power BI
description: Punktdiagramme, Punktplotdiagramme und Blasendiagramme in Power BI
author: mihart
manager: kvivek
ms.reviewer: ''
featuredvideoid: PVcfPoVE3Ys
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 10/24/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 26dd55f1084d62f9506b02c5852f0396adba305a
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/15/2019
ms.locfileid: "54290312"
---
# <a name="scatter-charts-bubble-charts-and-dot-plot-charts-in-power-bi"></a>Punktdiagramme, Punktplotdiagramme und Blasendiagramme in Power BI
Ein Punktdiagramm weist immer zwei Wertachsen auf, sodass ein Satz von numerischen Daten entlang einer horizontalen Achse und ein anderer Satz von numerischen Werten entlang einer vertikalen Achse angezeigt werden. Das Diagramm zeigt Schnittpunkte von x- und y-Zahlenwerten an, wobei diese Werte in jeweils einem einzelnen Punkt kombiniert werden. Diese Datenpunkte können in Abhängigkeit von den Daten gleichmäßig oder ungleichmäßig auf der horizontalen Achse verteilt sein.

In einem Blasendiagramm werden Datenpunkte durch Blasen ersetzen, hierbei repräsentiert die *Größe* der Blase eine zusätzliche Dimension der Daten.

![Beispielblasendiagramm](media/power-bi-visualization-scatter/power-bi-bubble-chart.png)

Ein Punktplotdiagramm ähnelt einem Blasen- und einem Punktdiagramm mit der Ausnahme, dass numerische oder Kategoriedaten entlang der X-Achse dargestellt werden können. 

![Beispielblasendiagramm](media/power-bi-visualization-scatter/power-bi-dot-plot.png)

Sie können die Anzahl der Datenpunkte auf maximal 10.000 festlegen.  

## <a name="when-to-use-a-scatter-chart-or-bubble-chart"></a>Wann sollte ein Punktdiagramm oder ein Blasendiagramm verwendet werden?
### <a name="scatter-charts-are-a-great-choice"></a>Punktdiagramme sind in folgenden Fällen gut geeignet:
* Zum Anzeigen von Beziehungen zwischen zwei (Punktdiagramm) oder drei (Blasendiagramm) **numerischen** Werten.
* Zum Darstellen zweier Gruppen von Zahlen als eine Reihe von XY-Koordinaten.
* Anstelle eines Liniendiagramm, wenn Sie die Skalierung der horizontalen Achse ändern möchten.    
* Zum Darstellen der horizontalen Achse in logarithmischer Skalierung.
* Zum Anzeigen von Arbeitsblattdaten, die Paare oder gruppierte Werte enthalten. In einem Punktdiagramm können Sie die unabhängigen Skalierungen der Achsen anpassen, um weitere Informationen zu den gruppierten Werten anzugeben.
* Um Muster in großen Mengen von Daten aufzuzeigen, z. B. lineare oder nicht lineare Trends, Ansammlungen oder Ausreißer.
* Um große Mengen von Datenpunkten ohne Berücksichtigung der Zeit zu vergleichen.  Je mehr Daten Sie in ein Punktdiagramm aufnehmen, desto bessere Vergleiche können Sie vornehmen.

### <a name="bubble-charts-are-a-great-choice"></a>Blasendiagramme sind in folgenden Fällen gut geeignet:
* Wenn Ihre Daten drei Datenreihen aufweisen, die jeweils einen Satz von Werten enthalten.
* Zum Präsentieren von Finanzdaten.  Unterschiedliche Blasengrößen sind nützlich zum optischen Hervorheben bestimmter Werte.
* Für die Verwendung mit Quadranten.

### <a name="dot-plot-charts-are-a-great-choice-in-place-of-a-scatter-or-bubble"></a>Im folgenden Fall sind Punktplotdiagramme eine hervorragende Alternative zu einem Punkt- oder Blasendiagrammen:
* Sie möchten Kategoriedaten entlang der X-Achse einschließen

## <a name="create-a-scatter-chart"></a>Erstellen eines Punktdiagramms
In diesem Video sehen Sie, wie Will ein Punktdiagramm erstellt. Mit den unten beschriebenen Schritten können Sie dann selbst ein solches Diagramm erstellen.

<iframe width="560" height="315" src="https://www.youtube.com/embed/PVcfPoVE3Ys?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>


In dieser Anleitung wird das Analysebeispiel für den Einzelhandel verwendet. Wenn Sie diese Schritte selbst ausführen möchten, [laden Sie das Beispiel für den Power BI-Dienst („app.powerbi.com“) oder Power BI Desktop herunter](../sample-datasets.md).   

1. Öffnen Sie den Bericht in der Bearbeitungsansicht, und klicken Sie auf das gelbe Plussymbol, um eine leere Berichtsseite zu erstellen.
 
2. Wählen Sie im Bereich „Felder“ die folgenden Felder aus:
   - **Umsätze** > **Umsätze pro Quadratmeter**
   - **Umsätze** > **Abweichungen der Gesamtumsätze in Prozent**
   - **Region** > **Region**

     ![](media/power-bi-visualization-scatter/power-bi-bar-chart.png)

     Wenn Sie den Power BI-Dienst verwenden, achten Sie darauf, den Bericht in der [Bearbeitungsansicht](../service-interact-with-a-report-in-editing-view.md) zu öffnen.

3. Führen Sie eine Konvertierung in ein Punktdiagramm durch. Wählen Sie im Bereich „Visualisierungen“ das Symbol für das Punktdiagramm aus.

   ![](media/power-bi-visualization-scatter/power-bi-scatter-new.png).

4. Ziehen Sie **Region** von **Details** auf **Legende**. Es wird ein Punktdiagramm angezeigt, in dem die **Abweichungen des Gesamtumsatzes in Prozent** auf der Y-Achse und der **Umsatz pro Quadratmeter** auf der X-Achse dargestellt werden. Die Farben der Datenpunkte stellen die Regionen dar:

    ![](media/power-bi-visualization-scatter/power-bi-scatter2.png)

Nun fügen wir eine dritte Dimension hinzu.

## <a name="create-a-bubble-chart"></a>Erstellen eines Blasendiagramms

1. Ziehen Sie aus dem Bereich **Felder** die Option **Umsätze** > **Umsätze dieses Jahr** > **Wert** in den Bereich **Größe**. Die Datenpunkte werden zu Werten erweitert, die proportional zu den Umsatzwerten sind.
   
   ![Punkte werden zu Blasen](media/power-bi-visualization-scatter/power-bi-scatter-chart-size.png)

2. Zeigen Sie auf eine Blase. Die Größe der Blase gibt den Wert von **Umsätze dieses Jahr**an.
   
    ![Anzeige von QuickInfos](media/power-bi-visualization-scatter/pbi_scatter_chart_hover.png)

3. Wenn Sie die Anzahl der im Blasendiagramm anzuzeigenden Datenpunkte festlegen möchten, erweitern Sie im Abschnitt **Format** des Bereichs **Visualisierungen** die Karte **Allgemein**, und passen Sie die **Datenmenge** an. Sie können die maximale Datenmenge auf eine beliebige Zahl bis 10.000 festlegen. Sobald Sie höhere Zahlen erreichen, wird empfohlen, zuerst einen Test durchzuführen, um gute Leistung sicherzustellen. 

    ![Datenmenge](media/power-bi-visualization-scatter/pbi_scatter_data_volume.png) 

   Durch eine größere Anzahl von Datenpunkten kann sich die Ladezeit verlängern. Daher sollten Sie, wenn Sie Berichte veröffentlichen, deren Datenmenge im oberen Bereich liegt, die Berichte im Web und auf mobilen Plattformen testen, um sicherzustellen, dass die Leistung den Erwartungen der Benutzer entspricht. 

4. Sie können [u.a. Visualisierungsfarben, Bezeichnungen, Titel, Hintergrund formatieren](service-getting-started-with-color-formatting-and-axis-properties.md). Zum [Verbessern der Barrierefreiheit](../desktop-accessibility.md) sollten Sie das Hinzufügen von Markierungsformen zu jeder Linie in Betracht ziehen. Die Verwendung einer anderen Markierungsform für jede Linie macht es den Benutzern des Berichts leichter, die Linien (oder Flächen) voneinander zu unterscheiden. Sie können zum Auswählen der Markierungsform die Karte **Formen** erweitern und dann eine Markierungsform auswählen.

      ![Markierungsform](media/power-bi-visualization-scatter/pbi_scatter_marker.png)

   Sie können auch die Markierungsform in Raute, Dreieck oder Quadrat ändern:

   ![Quadratischer Marker](media/power-bi-visualization-scatter/pbi_scatter_chart_hover_square.png)

## <a name="create-a-dot-plot"></a>Erstellen eines Punktplotdiagramms
Um ein Punktplotdiagramm zu erstellen, ersetzen Sie das numerische Feld für die X-Achse durch ein Kategoriefeld.

Entfernen Sie im Bereich **X-Achse** das Feld **Verkäufe pro qm**, und ersetzen Sie es durch **Distrikt > DM**.
   
![Neues Punktplotdiagramm](media/power-bi-visualization-scatter/power-bi-dot-plot-squares.png)


## <a name="considerations-and-troubleshooting"></a>Zu beachtende Aspekte und Problembehandlung

### <a name="your-scatter-chart-has-only-one-data-point"></a>**Das Punktdiagramm weist nur einen Datenpunkt auf**
Weist Ihr Punktdiagramm nur einen Datenpunkt auf, in dem alle Werte auf der X- und der Y-Achse zusammengefasst sind?  Oder werden alle Werte auf einer einzelnen horizontalen oder vertikalen Linie zusammengefasst?

![](media/power-bi-visualization-scatter/pbi_scatter_tshoot1.png)

Fügen Sie im Bereich **Details** ein Feld hinzu, sodass Power BI erkennt, wie die Werte gruppiert werden sollen. Das Feld muss für jeden Punkt, der dargestellt werden soll (z.B. eine einfache Zeilennummer oder ein ID-Feld), eindeutig sein.

![](media/power-bi-visualization-scatter/pbi_scatter_tshoot.png)

Wenn dies mit Ihren Daten nicht möglich ist, erstellen Sie ein Feld, in dem die X- und Y-Werte für jeden Punkt auf individuelle Weise dargestellt werden:

![](media/power-bi-visualization-scatter/pbi_scatter_tshoot2.png)

Um ein neues Feld zu erstellen, [fügen Sie mit dem Abfrage-Editor von Power BI Desktop dem Dataset eine Indexspalte hinzu](../desktop-add-custom-column.md).  Fügen Sie diese Spalte dann dem Bereich **Details** Ihrer Visualisierung hinzu.

## <a name="next-steps"></a>Nächste Schritte

[High density scatter charts (Stichprobenentnahme mit hoher Dichte in Punktdiagrammen)](desktop-high-density-scatter-charts.md)

[Visualisierungstypen in Power BI](power-bi-visualization-types-for-reports-and-q-and-a.md)

