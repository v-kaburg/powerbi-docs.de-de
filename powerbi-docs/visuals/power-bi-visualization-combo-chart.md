---
title: Kombinationsdiagramm in Power BI
description: In diesem Tutorial zu Kombinationsdiagrammen wird erläutert, wann sie verwendet werden sollten und wie sie im Power BI-Dienst und in Power BI Desktop erstellt werden.
author: mihart
manager: kvivek
ms.reviewer: ''
featuredvideoid: lnv66cTZ5ho
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 09/27/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 1855b65277fe778a20bd9e4629f8db1e7b9000a3
ms.sourcegitcommit: 769ef3c8cbafd9ad5979eb4023a394ac7dba8d02
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/28/2018
ms.locfileid: "47448958"
---
# <a name="combo-chart-in-power-bi"></a>Kombinationsdiagramm in Power BI
Ein Kombinationsdiagramm in Power BI ist eine einzelne Visualisierung, die ein Liniendiagramm und ein Säulendiagramm kombiniert. Die Kombination von zwei Diagrammen in einem ermöglicht einen schnelleren Vergleich von Daten.

Kombinationsdiagramme können ein oder zwei y-Achsen haben.

## <a name="when-to-use-a-combo-chart"></a>Einsatz von Kombinationsdiagrammen
Kombinationsdiagramme sind gut für folgende Zwecke geeignet:

* Bei einem Liniendiagramm und ein Säulendiagramm mit der gleichen X-Achse
* Zum Vergleichen mehrerer Kennzahlen mit verschiedenen Wertebereichen
* Zum Verdeutlichen der Zusammenhänge zweier Kennzahlen in einer Visualisierung
* Zum Prüfen, ob eine Kennzahl das durch eine andere Kennzahl vorgegebene Ziel erfüllt
* Zur Platzersparnis im Zeichenbereich

### <a name="prerequisites"></a>Voraussetzungen
Kombinationsdiagramme sind im Power BI-Dienst und in Power BI Desktop verfügbar. In diesem Tutorial wird zum Erstellen eines Kombinationsdiagramms der Power BI-Dienst verwendet. Um die Schritte durchzuführen, öffnen Sie den Power BI-Dienst, und stellen Sie eine Verbindung mit dem Analysebeispiel für Einzelhandel her ([siehe die unten stehenden Anweisungen](#create)).


## <a name="create-a-basic-single-axis-combo-chart"></a>Erstellen eines einfachen Kombinationsdiagramms mit einer Achse
In diesem Video sehen Sie, wie ein Kombinationsdiagramm anhand des Beispiels für Vertrieb und Marketing erstellt wird.

<iframe width="560" height="315" src="https://www.youtube.com/embed/lnv66cTZ5ho?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>  

<a name="create"></a> Melden Sie sich zum Erstellen eines eigenen Kombinationsdiagramms beim Power BI-Dienst an, und wählen Sie **Daten abrufen \> Beispiele \> Analysebeispiel für Einzelhandel > Verbinden > Zum Dashboard wechseln** aus.

1. Wählen Sie im Dashboard „Analysebeispiel für Einzelhandel“ die Kachel **Läden gesamt** aus, um den Bericht „Analysebeispiel für Einzelhandel“ zu öffnen.
2. Wählen Sie **Bericht bearbeiten** , um den Bericht in der Bearbeitungsansicht zu öffnen.
3. [Fügen Sie eine neue Seite zu Ihrem Bericht hinzu](../power-bi-report-add-page.md).
4. Erstellen Sie ein Säulendiagramm, das den Absatz des laufenden Jahres und den Bruttogewinn pro Monat anzeigt.

    a.  Wählen Sie im Bereich „Felder“ die Option **Verkäufe** \> **Verkäufe in diesem Jahr**  >  **Wert**.

    b.  Ziehen Sie **Vertrieb** \>**Bruttogewinn in diesem Jahr** in den Bereich **Wert**.

    c.  Wählen Sie **Zeit** \> **Geschäftsmonat** aus, um den Wert dem Bereich **Achse** hinzuzufügen.

    ![](media/power-bi-visualization-combo-chart/combotutorial1new.png)
5. Klicken Sie erst auf die Auslassungspunkte (...) in der rechten oberen Ecke der Visualisierung und dann auf **Sortieren nach > FiscalMonth**. Wenn Sie die Sortierreihenfolge ändern möchten, klicken Sie erst erneut auf die Auslassungspunkte und anschließend auf **Aufsteigend sortieren** oder **Absteigend sortieren**.

6. Konvertieren Sie das Säulendiagramm in ein Kombinationsdiagramm. Es gibt zwei Kombinationsdiagramme: **Line and stacked column** (gestapeltes Säulendiagramm mit Linien) und **Line and clustered column** (gruppiertes Säulendiagramm mit Linien). Wenn Sie das Säulendiagramm ausgewählt haben, wählen Sie im Bereich **Visualisierungen** die Option **Linien- und gruppiertes Säulendiagramm** aus.

    ![](media/power-bi-visualization-combo-chart/converttocombo_new2.png)
7. Ziehen Sie aus dem Bereich **Felder** die Option **Vertrieb** \> **Verkäufe im letzten Jahr** in den Bucket **Zeilenwerte**.

   ![](media/power-bi-visualization-combo-chart/linevaluebucket.png)

   Das Kombinationsdiagramm sollten nun ungefähr so aussehen:

   ![](media/power-bi-visualization-combo-chart/combochartdone-new.png)

## <a name="create-a-combo-chart-with-two-axes"></a>Erstellen eines Kombinationsdiagramms mit zwei Achsen
In dieser Aufgabe vergleichen wir Bruttogewinn und Umsätze.

1. Erstellen Sie ein neues Liniendiagramm, das den **Bruttogewinn in Prozent im letzten Jahr** nach **Monaten** nachverfolgt. Klicken Sie auf die Auslassungspunkte, um **Aufsteigend** nach **Monat** zu sortieren.  
Im Januar lag der Prozentsatz des Bruttogewinns bei 35 %, der Höchststand im April lag bei 45 %, im Juli fiel der Wert, und im August erreichte er wieder einen Spitzenwert. Sehen wir ein ähnliches Muster bei den Umsätzen im letzten und in diesem Jahr?

   ![](media/power-bi-visualization-combo-chart/combo1_new.png)
2. Fügen Sie dem Liniendiagramm **Verkäufe in diesem Jahr > Wert** und **Verkäufe im letzten Jahr** hinzu. Da der **Bruttogewinn % Vorjahr** wesentlich kleiner ist als die **Umsätze**, können diese Werte nur schwer verglichen werden.      

   ![](media/power-bi-visualization-combo-chart/flatline_new.png)
3. Konvertieren Sie das Liniendiagramm zu einem Linien- und gestapelten Säulendiagramm, damit die Visualisierung besser gelesen und interpretiert werden kann.

   ![](media/power-bi-visualization-combo-chart/converttocombo_new.png)
4. Ziehen Sie **Bruttogewinn % Vorjahr** aus **Spaltenwerte** in **Zeilenwerte**. Power BI erstellt zwei Achsen, sodass die Datasets anders skaliert werden können. Die linke Achse gibt den Dollarbetrag der Umsätze an, die rechte Achse die Prozentzahl. Und hier sehen Sie die Antwort auf unsere Frage: Ja, wir sehen ein ähnliches Muster.

   ![](media/power-bi-visualization-combo-chart/power-bi-combochart.png)    

## <a name="add-titles-to-the-axes"></a>Hinzufügen von Titeln zu den Achsen
1. Wählen Sie das Farbrollersymbol ![](media/power-bi-visualization-combo-chart/power-bi-paintroller.png) aus, um den Formatierungsbereich zu öffnen.
2. Wählen Sie den Pfeil nach unten aus, um die Optionen für die **Y-Achse** zu erweitern.
3. Nehmen Sie für **Y-Achse (Spalte)** die folgenden Einstellungen vor: Wählen Sie für **Position** die Option **Links**, für **Titel** die Option **Ein**, für **Stil** die Option **Nur Titel anzeigen** und für **Anzeigen** die Option **Millionen**.

   ![](media/power-bi-visualization-combo-chart/power-bi-y-axis-column.png)
4. Scrollen Sie unter **Y-Achse (Spalte)** nach unten, und stellen Sie sicher, dass für **Sekundäre anzeigen** die Option **Ein** festgelegt ist. Dadurch werden für den Liniendiagrammanteil des Kombinationsdiagramms Formatierungsoptionen angezeigt.

   ![](media/power-bi-visualization-combo-chart/power-bi-show-secondary.png)
5. Unter **Y-Achse (Linie)** ist für **Position** bereits die hier benötigte Option **Rechts** aktiviert. Stellen Sie **Titel**  auf **Ein**, und wählen Sie für **Stil** die Option **Nur Titel anzeigen**.

   Das Kombinationsdiagramm verfügt nun über zwei Y-Achsen mit jeweils eigenem Titel.

   ![](media/power-bi-visualization-combo-chart/power-bi-titles-on.png)

6. Optional können Sie die Schriftart, den Schriftgrad und die Farbe des Texts ändern und weitere Formatierungsoptionen festlegen, um die Darstellung und Lesbarkeit des Diagramms zu verbessern.

Jetzt haben Sie folgende Möglichkeiten:

* [Fügen Sie das Kombinationsdiagramm als Dashboardkachel hinzu.](../service-dashboard-tiles.md)
* [Speichern Sie den Bericht](../service-report-save.md).
* [Barrierefreiheit in Power BI Desktop-Berichten](../desktop-accessibility.md)

## <a name="cross-highlighting-and-cross-filtering"></a>Kreuzhervorheben und Kreuzfiltern

Das Markieren einer Spalte oder Zeile in einem Kombinationsdiagramm ermöglicht das Kreuzhervorheben und Kreuzfiltern anderer Visualisierungen auf der Berichtsseite und umgekehrt. Verwenden Sie [Visualinteraktionen](../service-reports-visual-interactions.md), um dieses Standardverhalten zu ändern.

## <a name="next-steps"></a>Nächste Schritte

[Ringdiagramme in Power BI](power-bi-visualization-doughnut-charts.md)

[Visualisierungstypen in Power BI](power-bi-visualization-types-for-reports-and-q-and-a.md)
