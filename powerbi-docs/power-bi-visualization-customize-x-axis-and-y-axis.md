---
title: Anpassen der Eigenschaften der X- und Y-Achse
description: Anpassen der Eigenschaften der X- und Y-Achse
services: powerbi
documentationcenter: ''
author: mihart
manager: kfile
backup: ''
featuredvideoid: 9DeAKM4SNJM
editor: ''
tags: ''
qualityfocus: complete
qualitydate: 05/16/2017
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 01/20/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: be31751c8ca6efb4e7b2dbcbd0215a1c7d002df5
ms.sourcegitcommit: 493f160d04ed411ff4741c599adc63ba1f65230f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="customize-x-axis-and-y-axis-properties"></a>Anpassen der Eigenschaften der X- und Y-Achse
In diesem Tutorial lernen Sie verschiedene Möglichkeiten zum Anpassen der X- und Y-Achse in Ihren visuellen Elementen kennen. Nicht alle visuellen Elemente verfügen über Achsen oder können angepasst werden. Bei Kreisdiagrammen gibt es z. B. keine Achsen. Darüber hinaus variieren die Anpassungsoptionen für die verschiedenen visuellen Elemente, sodass nicht alle Optionen in einem einzigen Artikel abgedeckt werden können. Betrachten wir daher die gängigsten Achsenanpassungen, damit Sie sich mit der Registerkarte für die visuelle Formatierung im Berichtszeichenbereich von Power BI vertraut machen können.  

> [!NOTE]
> Diese Seite gilt für sowohl den Power BI-Dienst als auch für Power BI Desktop. Diese Anpassungsmöglichkeiten sind auch in Power BI Desktop verfügbar, wenn **Format** (das Farbrollersymbol ![](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-paintroller.png)) ausgewählt ist.  
>
>

Sehen Sie sich an, wie Amanda ihre X- und Y-Achse anpasst und die verschiedenen Möglichkeiten zum Steuern der Verkettung bei Verwenden der Drillup- und Drilldownfunktionen veranschaulicht. Befolgen Sie dann die detaillierten Anweisungen unter dem Video, um es selbst mit dem Analysebeispiel für den Einzelhandel auszuprobieren.

<iframe width="560" height="315" src="https://www.youtube.com/embed/9DeAKM4SNJM" frameborder="0" allowfullscreen></iframe>


## <a name="customizing-visualization-x-axes-in-reports"></a>Anpassen der Visualisierung von X-Achsen in Berichten
## <a name="create-a-stacked-chart-visualization"></a>Erstellen einer Visualisierung eines gestapelten Diagramms
Melden Sie sich beim Power BI-Dienst an, und öffnen Sie den Bericht des **Analysebeispiels für den Einzelhandel** in der [Bearbeitungsansicht](service-interact-with-a-report-in-editing-view.md). Laden Sie hierfür das [Analysebeispiel für den Einzelhandel](sample-datasets.md) herunter.

1. Erstellen Sie ein Säulendiagramm, das den Wert für den Absatz des laufenden Jahres und den des Vorjahres nach Geschäftsmonat anzeigt.
2. Konvertieren Sie es in ein gestapeltes Säulendiagramm.

    ![](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-create-chart.png)

## <a name="customize-the-x-axis"></a>Anpassen der X-Achse
1. Wählen Sie im Bereich für Visualisierungen und Filter die Option **Format** (das Farbrollersymbol ![](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-paintroller.png)) aus, um die Anpassungsoptionen anzuzeigen.
2. Erweitern Sie die Optionen für die X-Achse.

   ![](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-x-axis.png)
3. Mithilfe des Schiebereglers für „Ein“ und „Aus“ aktivieren bzw. deaktivieren Sie die X-Achse. Belassen Sie die Einstellung vorerst bei **Ein**.  Das Deaktivieren der X-Achse empfiehlt sich u.a., um mehr Platz für weitere Daten zu schaffen.

    ![](media/power-bi-visualization-customize-x-axis-and-y-axis/onoffslider.png)
4. Formatieren Sie die Textfarbe, die Textgröße und die Schriftart. In diesem Beispiel haben wir die **Farbe** für den Text auf Schwarz, die **Textgröße** auf 14 und die **Schriftart** auf Arial Black festgelegt.  
5. Wählen Sie für den Titel der X-Achse die Einstellung **Ein** aus, und zeigen Sie die Bezeichnung der X-Achse an – in diesem Fall **Geschäftsmonat**.  
6. Formatieren Sie die Textfarbe, die Textgröße und die Schriftart des Titels.  In diesem Beispiel wurde **Farbe des Titels** auf Orange festgelegt, **Achsentitel** wurde in **Geschäftsmonat** geändert, und **Größe des Titeltexts** wurde auf 21 festgelegt.
7. Wählen Sie zum Sortieren nach Geschäftsmonat die Auslassungspunkte (...) in der rechten oberen Ecke des Diagramms aus, und wählen Sie **Nach Geschäftsmonat sortieren**.

    Nach diesen Anpassungen sollte Ihr Säulendiagramm etwa so aussehen:

     ![](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-customize-axis.png)

Wenn Sie die Anpassungen der X-Achse zurücksetzen möchten, wählen Sie **Standardwert wiederherstellen** am unteren Rand des Anpassungsbereichs der **X-Achse** aus.

## <a name="customize-the-y-axis"></a>Anpassen der Y-Achse
1. Erweitern Sie die Optionen für die Y-Achse.

   ![](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-y-axis.png)

2. Mithilfe des Schiebereglers für „Ein“ und „Aus“ aktivieren bzw. deaktivieren Sie die Y-Achse. Belassen Sie die Einstellung vorerst bei **Ein**.  Das Deaktivieren der Y-Achse empfiehlt sich u.a., um mehr Platz für weitere Daten zu schaffen.
   
    ![](media/power-bi-visualization-customize-x-axis-and-y-axis/onoffslider.png)
3. Verschieben Sie die **Position** der Y-Achse nach rechts.
4. Formatieren Sie die Textfarbe, die Textgröße und die Schriftart. In diesem Beispiel haben wir die **Farbe** für den Text auf Schwarz, die **Textgröße** auf 14 und die **Schriftart** auf Arial Black festgelegt.  
5. Lassen Sie **Anzeigeeinheiten** auf „Millionen“ und **Dezimalstellen für Werte** auf 0 (null) festgelegt.
6. Da diese Visualisierung durch eine Y-Achse nicht verbessert wird, lassen Sie **Titel** deaktiviert.  
7. Wir heben die Gitternetzlinien hervor, indem wir die **Farbe** in Dunkelgrau ändern und die **Strichstärke** auf 2 erhöhen.

    Nach diesen Anpassungen sollte Ihr Säulendiagramm etwa so aussehen:

     ![](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-y-axis-complete.png)

## <a name="customizing-visualizations-with-dual-y-axes"></a>Anpassen von Visualisierungen mit zwei Y-Achsen
Zunächst erstellen Sie ein Kombinationsdiagramm, das die Auswirkungen der Ladenanzahl auf die Verkäufe prüft.  Dies ist das gleiche Diagramm, das auch im [Tutorial zu Kombinationsdiagrammen](power-bi-visualization-combo-chart.md) erstellt wird. Danach formatieren Sie die beiden Y-Achsen.

### <a name="create-a-chart-with-two-y-axes"></a>Erstellen eines Diagramms mit zwei Y-Achsen
1. Erstellen Sie ein neues Liniendiagramm, das **Verkäufe > Bruttogewinn % Vorjahr** nach **Zeit > Geschäftsmonat** nachverfolgt.
2. Sortieren Sie die visuellen Elemente nach Monat, indem Sie auf die Auslassungspunkte (...) klicken und **Sortieren nach Monat** auswählen.

    ![](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-line-chart.png)

>[NOTE]: For help sorting by month, see [sorting by other criteria](power-bi-report-change-sort.md#other)
1. Im Januar lag der Prozentsatz des Bruttogewinns bei 35 %, der Höchststand im April lag bei 45 %, im Juli fiel der Wert, und im August erreichte er wieder einen Spitzenwert. Sehen wir ein ähnliches Muster bei den Umsätzen im letzten und in diesem Jahr?
2. Fügen Sie dem Liniendiagramm **Verkäufe in diesem Jahr > Wert** und **Verkäufe im letzten Jahr** hinzu. Da der **Bruttogewinn % Vorjahr** (die blaue Linie entlang der Gitternetzlinie für 0 %) wesentlich kleiner ist als die **Umsätze**, können diese Werte nur schwer verglichen werden. Und die Prozentwerte in den Bezeichnungen auf der Y-Achse sind viel zu groß.      

   ![](media/power-bi-visualization-customize-x-axis-and-y-axis/flatline_new.png)
5. Konvertieren Sie das Liniendiagramm zu einem Linien- und gestapelten Säulendiagramm, damit die Visualisierung besser gelesen und interpretiert werden kann.

   ![](media/power-bi-visualization-customize-x-axis-and-y-axis/converttocombo_new.png)

6. Ziehen Sie **Bruttogewinn % Vorjahr** aus **Spaltenwerte** in **Zeilenwerte**. Wir verfügen jetzt über das gestapelte Säulendiagramm, das wir oben erstellt haben, ***und*** ein Liniendiagramm.  (Optional können Sie die Schriftfarbe und -größe der Achsen formatieren, indem Sie anwenden, was Sie weiter oben gelernt haben.)
   

   Power BI erstellt zwei Achsen, sodass die Datasets anders skaliert werden können. Die linke Achse gibt den Dollarbetrag an, die rechte Achse die Prozentzahl.

   ![](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-dual-axes-new.png)

### <a name="format-the-secondary-y-axis"></a>Formatieren der sekundären Y-Achse
1. Wählen Sie im Bereich **Visualisierungen** das Farbrollersymbol aus, um die Formatierungsoptionen anzuzeigen.
2. Erweitern Sie die Optionen für die Y-Achse, indem Sie den Pfeil nach unten auswählen.
3. Scrollen Sie in der Liste zu den Optionen für **Sekundäre anzeigen**. Legen Sie **Sekundäre anzeigen** von **Aus** auf **Ein** fest.

   ![](media/power-bi-visualization-customize-x-axis-and-y-axis/combo3.png)

   ![](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-dual-axes.png)
4. (Optional) Passen Sie die beiden Achsen an. Wenn Sie die **Position** für die Spaltenachse oder Zeilenachse wechseln, werden die Seiten der beiden Achsen vertauscht.

   ![](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-y-axes-options.png)

### <a name="add-titles-to-both-axes"></a>Hinzufügen von Titeln zu beiden Achsen
Bei einer so komplexen Visualisierung ist es hilfreich, wenn den Achsen Titel hinzugefügt werden.  Mithilfe von Titeln können Ihre Kollegen nachvollziehen, was mit der Visualisierung angegeben werden soll.

1. Legen Sie **Titel** für **Y-Achse (Spalte)** und **Y-Achse (Linie)** auf **Ein** fest.
2. Wählen Sie für **Stil** die Option **Nur Titel anzeigen**.

   ![](media/power-bi-visualization-customize-x-axis-and-y-axis/yaxissettings.png)
3. Das Kombinationsdiagramm zeigt nun zwei Achsen mit Titeln an.

   ![](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-combo-chart.png)

Weitere Informationen finden Sie unter [Tipps und Tricks zu Farbformatierung, Beschriftung und Achseneigenschaften](service-tips-and-tricks-for-color-formatting.md).

## <a name="considerations-and-troubleshooting"></a>Zu beachtende Aspekte und Problembehandlung
Wenn vom Besitzer des Berichts die X-Achse als Datentyp kategorisiert wurde, wird die Option **Typ** angezeigt, und Sie können zwischen „Fortlaufend“ und „Kategorie“ wählen.

## <a name="next-steps"></a>Nächste Schritte
Weitere Informationen zu [Visualisierungen in Power BI-Berichten](power-bi-report-visualizations.md)

[Anpassen von T](power-bi-visualization-customize-title-background-and-legend.md)[iteln, Hintergründen und Legenden](power-bi-visualization-customize-title-background-and-legend.md)

[Anpassen von Farben und Achseneigenschaften](service-getting-started-with-color-formatting-and-axis-properties.md)

[Power BI – Grundkonzepte](service-basic-concepts.md)

Weitere Fragen? [Wenden Sie sich an die Power BI-Community](http://community.powerbi.com/)
