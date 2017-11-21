---
title: Analysebereich im Power BI-Dienst
description: "Erstellen dynamischer Bezugslinien für Visualisierungen im Power BI-Dienst"
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
ms.date: 05/02/2017
ms.author: mihart
ms.openlocfilehash: 30fc0731f819f063aa04e856e8acc75a69f64a59
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2017
---
# <a name="analytics-pane-in-power-bi-service"></a>Analysebereich im Power BI-Dienst
Mit dem Bereich **Analyse** im **Power BI-Dienst** können Sie Visualisierungen dynamische *Bezugslinien* hinzufügen und wichtige Trends und Erkenntnisse identifizieren.

![](media/service-analytics-pane/power-bi-analytics-pane.png)

> [!NOTE]
> Der Bereich **Analyse** wird nur angezeigt, wenn Sie im Zeichenbereich ein Visual auswählen.
> 
> 

## <a name="using-the-analytics-pane"></a>Verwendung des Bereichs „Analyse“
Mithilfe des Bereichs **Analyse** können Sie die folgenden Arten von dynamischen Bezugslinien erstellen (wobei nicht alle Linien für alle Visualisierungstypen verfügbar sind):

* Bezugslinie für X-Achse
* Bezugslinie für Y-Achse
* Linie für Mindestwert
* Linie für Maximalwert
* Durchschnittslinie
* Linie für Medianwert
* Linie für Perzentil

In den folgenden Abschnitten erfahren Sie, wie Sie den Bereich **Analyse** und die dynamischen Bezugslinien in Ihren Visualisierungen verwenden können.

Um die für eine Visualisierung verfügbaren dynamischen Bezugslinien anzuzeigen, führen Sie die folgenden Schritte aus:

1. Wählen Sie eine Visualisierung aus, oder erstellen Sie eine Visualisierung. Wählen Sie dann das Symbol **Analyse** ![](media/service-analytics-pane/power-bi-analytics-icon.png)im Bereich **Visualisierungen** aus.
2. Wählen Sie für die gewünschte Linie den Pfeil nach unten aus, um die entsprechenden Optionen zu erweitern. In diesem Fall entscheiden wir uns für die **Durchschnittslinie**.
   
   ![](media/service-analytics-pane/power-bi-add.png)
3. Um eine neue Linie zu erstellen, wählen Sie **+ Hinzufügen** aus. Dann können Sie der Linie einen Namen geben, indem Sie auf das Textfeld doppelklicken und dann den Namen eingeben.
   
   Für jede Linie steht eine Reihe an Optionen zur Verfügung, z.B. *Farbe*, *Transparenz*, *Stil* und *Position* (relativ zu den Datenelementen der Visualisierung). Sie können auch festlegen, ob die Bezeichnung angezeigt werden soll. Vor allem können Sie bestimmen, auf welchem **Measure** der Visualisierung die Linie basieren soll. Wählen Sie dazu das Dropdownfeld **Measure** aus, das automatisch mit den Datenelementen der Visualisierung ausgefüllt wird. In diesem Fall entscheiden wir uns für *Open store count* (Anzahl geöffneter Stores) als Measure, geben als Bezeichnung *Avg # Open Stores* (Durchschnittsanzahl geöffnete Stores) ein und passen einige weitere Optionen an (siehe unten).
   
   ![](media/service-analytics-pane/power-bi-average-line.png)
4. Wenn die Datenbezeichnung angezeigt werden soll, aktivieren Sie diese Option mit dem Schieberegler **Datenbeschriftung**. Dadurch wird eine Reihe an weiteren Optionen für die Datenbeschriftung angezeigt.
5. Beachten Sie die Zahl, die neben dem Element **Durchschnittslinie** im Bereich **Analyse** angezeigt wird. Dieser Wert steht für die Anzahl der in Ihrer Visualisierung verwendeten dynamischen Linien und verrät auch, von welchem Typ diese sind. Wenn wir eine **Bezugslinie** als Ziel für die Store-Anzahl 9 hinzufügen, wird im Bereich **Analyse** angezeigt, dass nun auch eine **Bezugslinie** im Visual verwendet wird.
   
   ![](media/service-analytics-pane/power-bi-reference-lines.png)
   
   Wenn Ihre Visualisierung keine dynamischen Bezugslinien verwenden kann (hier eine Visualisierung vom Typ **Karte**), sehen Sie das Folgende, wenn Sie den Bereich **Analyse** aufrufen.
   
   ![](media/service-analytics-pane/power-bi-no-lines.png)

Sie können viele interessante Einblicke gewinnen, wenn Sie mithilfe des Bereichs **Analyse** dynamische Bezugslinien erstellen.

Wir arbeiten an der Umsetzung weiterer Features und Funktionen, u.a. daran, dynamische Bezugslinien für mehr Visualisierungen verfügbar zu machen. Es gibt also regelmäßig Neues zu entdecken.

## <a name="limitations"></a>Einschränkungen
Die Möglichkeit zum Verwenden von dynamischen Bezugslinien ist abhängig vom verwendeten visuellen Element. Die folgende Liste zeigt, welche dynamischen Linien zurzeit für welche visuellen Objekte verfügbar sind:

Dynamische Linien sind für die folgenden visuellen Elemente in vollem Umfang verfügbar:

* Flächendiagramm
* Liniendiagramm
* Punktdiagramm
* Gruppiertes Säulendiagramm
* Gruppiertes Balkendiagramm

Für die folgenden visuellen Elemente kann nur eine *Bezugslinie* aus dem Bereich **Analyse** verwendet werden:

* Gestapelte Fläche
* Gestapelter Balken
* Gestapelte Säule
* Gestapelter Balken (100 %)
* Gestapelte Säule (100 %)

Für die folgenden visuellen Elemente ist die einzige Option zurzeit eine *Trendlinie*:

* Nicht gestapelte Linie
* Gruppiertes Säulendiagramm

Außerdem können für nicht kartesische visuelle Elemente zurzeit keine dynamischen Linien im Bereich **Analyse** anwendet werden, z. B.:

* Matrix
* Kreisdiagramm
* Ringdiagramm
* Tabelle (Table)

## <a name="next-steps"></a>Nächste Schritte
[Analysebereich in Power BI Desktop](desktop-analytics-pane.md)

Weitere Fragen? [Wenden Sie sich an die Power BI-Community](http://community.powerbi.com/)

