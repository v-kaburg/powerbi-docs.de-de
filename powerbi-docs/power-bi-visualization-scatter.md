---
title: Punktdiagramme in Power BI (Tutorial)
description: "Tutorial: Punktdiagramme in Power BI"
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: PVcfPoVE3Ys
qualityfocus: identified
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 12/23/2017
ms.author: mihart
ms.openlocfilehash: 2d8ed3c30d289646504071daca098df1f41f6aab
ms.sourcegitcommit: d803e85bb0569f6b357ba0586f5702c20d27dac4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="scatter-charts-and-bubble-charts-in-power-bi-tutorial"></a>Punktdiagramme und Blasendiagramme in Power BI (Tutorial)
Ein Punktdiagramm weist immer zwei Wertachsen auf, sodass ein Satz von numerischen Daten entlang einer horizontalen Achse und ein anderer Satz von numerischen Werten entlang einer vertikalen Achse angezeigt werden. Das Diagramm zeigt Schnittpunkte von x- und y-Zahlenwerten an, wobei diese Werte in jeweils einem einzelnen Punkt kombiniert werden. Diese Datenpunkte können in Abhängigkeit von den Daten gleichmäßig oder ungleichmäßig auf der horizontalen Achse verteilt sein.

In einem Blasendiagramm werden die Datenpunkte durch Blasen ersetzt, wobei die *Blasengröße* eine zusätzliche Datendimension darstellt.

![](media/power-bi-visualization-scatter/power-bi-bubble-chart.png)

Sie können die Anzahl der Datenpunkte festlegen.  

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

## <a name="create-a-scatter-chart"></a>Erstellen eines Punktdiagramms
In diesem Video sehen Sie, wie Will ein Punktdiagramm erstellt. Mit den unten beschriebenen Schritten können Sie dann selbst ein solches Diagramm erstellen.

<iframe width="560" height="315" src="https://www.youtube.com/embed/PVcfPoVE3Ys?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>


In dieser Anleitung wird das Analysebeispiel für den Einzelhandel verwendet. Wenn Sie diese Schritte selbst ausführen möchten, [laden Sie das Beispiel für den Power BI-Dienst („app.powerbi.com“) oder Power BI Desktop herunter](sample-datasets.md).   

1. Beginnen Sie mit einer [leeren Berichtsseite](power-bi-report-add-page.md), und wählen Sie die Felder **Umsätze** \> **Umsätze pro Quadratfuß** und **Umsätze** > **Gesamtabweichung Umsatz %** aus. Wenn Sie den Power BI-Dienst verwenden, achten Sie darauf, den Bericht in der [Bearbeitungsansicht](service-interact-with-a-report-in-editing-view.md) zu öffnen.
 
2. Wählen Sie im Bereich „Felder“ die Option **Region > Region** aus.
   
    ![](media/power-bi-visualization-scatter/power-bi-bar-chart.png)
4. Führen Sie eine Konvertierung in ein Punktdiagramm durch. Wählen Sie im Bereich „Visualisierungen“ das Symbol für das Punktdiagramm aus.
   ![](media/power-bi-visualization-scatter/pbi_scatter_chart_icon.png).
5. Ziehen Sie **Region** von **Details** auf **Legende**.
   
    ![](media/power-bi-visualization-scatter/power-bi-scatter.png)

Wir haben jetzt ein Punktdiagramm, in dem „Gesamtabweichung Umsatz %“ der Y-Achse und „Umsätze pro Quadratfuß“ der X-Achse zugewiesen sind.  Die Farben der Datenpunkte stellen die Regionen dar.  Nun fügen wir eine dritte Dimension hinzu.

## <a name="create-a-bubble-chart"></a>Erstellen eines Blasendiagramms
1. Ziehen Sie aus dem Bereich „Felder“ die Option **Umsätze** > **Umsätze dieses Jahr** > **Wert** in den Bereich **Größe**. 
   
   ![](media/power-bi-visualization-scatter/power-bi-bubble.png)
2. Zeigen Sie auf eine Blase.  Die Größe der Blase gibt den Wert von **Umsätze dieses Jahr**an.
   
    ![](media/power-bi-visualization-scatter/pbi_scatter_chart_hover.png)
3. Optional können Sie [Visualisierungsfarben, Bezeichnungen, Titel, Hintergrund und mehr formatieren](service-getting-started-with-color-formatting-and-axis-properties.md).

   Sie können auch die Markierungsform in Raute, Dreieck oder Quadrat ändern:

   ![Quadratischer Marker](media/power-bi-visualization-scatter/pbi_scatter_chart_hover_square.png)

4. Wenn Sie die Anzahl der im Blasendiagramm anzuzeigenden Punkte festlegen möchten, erweitern Sie im Abschnitt **Format** des Bereichs **Visualisierungen** die Karte **Allgemein**, und passen Sie die **Datenmenge** an. Der Standardwert lautet 3500. 
 
    ![Datenmenge](media/power-bi-visualization-scatter/pbi_scatter_data_volume.png) 

   > [!NOTE]
   > Durch eine größere Anzahl von Datenpunkten kann sich die Ladezeit verlängern. Daher sollten Sie, wenn Sie Berichte veröffentlichen, deren Datenmenge im oberen Bereich liegt, die Berichte im Web und auf mobilen Plattformen testen, um sicherzustellen, dass die Leistung den Erwartungen der Benutzer entspricht.

5.   Optional können Sie zum Auswählen der Markierungsform die Karte **Formen** erweitern und dann eine Markierungsform auswählen.

      ![Markierungsform](media/power-bi-visualization-scatter/pbi_scatter_marker.png)

## <a name="considerations-and-troubleshooting"></a>Zu beachtende Aspekte und Problembehandlung
### <a name="your-scatter-chart-has-only-one-data-point"></a>**Das Punktdiagramm weist nur einen Datenpunkt auf**
Weist Ihr Punktdiagramm nur einen Datenpunkt auf, in dem alle Werte auf der X- und der Y-Achse zusammengefasst sind?  Oder werden alle Werte auf einer einzelnen horizontalen oder vertikalen Linie zusammengefasst?

![](media/power-bi-visualization-scatter/pbi_scatter_tshoot1.png)

Fügen Sie im Bereich **Details** ein Feld hinzu, sodass Power BI erkennt, wie die Werte gruppiert werden sollen. Das Feld muss für jeden Punkt, der dargestellt werden soll, eindeutig sein.  
Beispielsweise ein einfaches Zeilennummern- oder ID-Feld:

![](media/power-bi-visualization-scatter/pbi_scatter_tshoot.png)

Wenn dies mit Ihren Daten nicht möglich ist, erstellen Sie ein Feld, in dem die X- und Y-Werte für jeden Punkt auf individuelle Weise dargestellt werden:

![](media/power-bi-visualization-scatter/pbi_scatter_tshoot2.png)

Um ein neues Feld zu erstellen, [fügen Sie mit dem Abfrage-Editor von Power BI Desktop dem Dataset eine Indexspalte hinzu](desktop-add-custom-column.md).  Fügen Sie diese Spalte dann dem Bereich **Details** Ihrer Visualisierung hinzu.

## <a name="next-steps"></a>Nächste Schritte
 [Visualisierungstypen in Power BI](power-bi-visualization-types-for-reports-and-q-and-a.md)

[Jetzt kostenlos testen](https://powerbi.com/)  

Weitere Fragen? [Wenden Sie sich an die Power BI-Community](http://community.powerbi.com/)

