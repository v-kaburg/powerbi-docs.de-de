---
title: Tabellenvisualisierungen in Power BI-Berichten und -Dashboards
description: Tutorial zum Arbeiten mit Tabellenvisualisierungen in Power BI-Berichten und -Dashboards, einschließlich Erläuterungen zum Ändern der Spaltenbreite.
author: mihart
manager: kvivek
ms.reviewer: ''
featuredvideoid: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 09/24/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: d2aae3abeca51cdcc142660190332f84adcfddfb
ms.sourcegitcommit: 769ef3c8cbafd9ad5979eb4023a394ac7dba8d02
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/28/2018
ms.locfileid: "47448820"
---
# <a name="tables-in-power-bi-reports-and-dashboards"></a>Tabellen in Power BI-Berichten und -Dashboards
Eine Tabelle ist ein Raster, das zusammengehörende Daten in einer logischen Folge von Zeilen und Spalten enthält. Zudem können auch Kopfzeilen und eine Zeile für Summen enthalten sein. Tabellen empfehlen sich insbesondere für quantitative Vergleiche, bei denen Sie viele Werte einer einzigen Kategorie betrachten. In dieser Tabelle werden beispielsweise fünf verschiedene Measures für **Kategorie** angezeigt.

![](media/power-bi-visualization-tables/table.png)

## <a name="when-to-use-a-table"></a>Verwenden von Tabellen
Tabellen sind für folgende Zwecke gut geeignet:

* Anzeigen und Vergleichen detaillierter Daten und genauer Werte (anstelle von visuellen Darstellungen)
* Auflisten von Daten in einem Tabellenformat
* Anzeigen numerischer Daten nach Kategorien   

> [!NOTE]
> Enthält eine Tabelle zu viele Werte, erwägen Sie, sie in eine Matrix zu konvertieren und/oder die Drilldownfunktion zu verwenden. Es werden maximal 3.500 Datenpunkte angezeigt.

## <a name="prerequisites"></a>Voraussetzungen
- Power BI-Dienst oder Power BI Desktop
- Retail Analysis sample

## <a name="create-a-table"></a>Erstellen einer Tabelle
Wir erstellen die oben abgebildete Tabelle, in der Umsatzwerte nach Artikelkategorien angezeigt werden. Melden Sie sich beim Power BI-Dienst an, navigieren Sie zu **Daten abrufen\> Beispiele \> Analysebeispiel für Einzelhandel > Verbinden**, und klicken Sie auf **Zum Dashboard wechseln**. Zum Erstellen einer Visualisierung benötigen Sie Bearbeitungsberechtigungen für das Dataset und den Bericht. Erfreulicherweise können die Power BI-Beispiele alle bearbeitet werden. Wenn ein Bericht für Sie freigegeben wurde, können Sie keine Visualisierungen in Berichten erstellen.

1. Wählen Sie links im Navigationsbereich **Arbeitsbereiche > Mein Arbeitsbereich** aus.    
2. Wählen Sie die Registerkarte „Datasets“ aus, und führen Sie einen Bildlauf nach unten zum gerade hinzugefügten Dataset „Analysebeispiel für Einzelhandel“ durch.  Wählen Sie das Symbol **Bericht erstellen** aus.

    ![Pfeil auf das Berichtssymbol](media/power-bi-visualization-tables/power-bi-create-report.png)
2. Wählen Sie im Berichts-Editor **Element** > **Kategorie** aus.  Power BI erstellt automatisch eine Tabelle, in der alle Kategorien aufgelistet werden.

    ![Ergebnis: „Kategorie“ hinzugefügt](media/power-bi-visualization-tables/power-bi-table1.png)
3. Wählen Sie **Sales > Average Unit Price** (Umsatz > Durchschnittlicher Stückpreis), **Sales > Last Year Sales** (Umsatz > Vorjahresumsatz) und **Sales > This Year Sales** (Umsatz > Diesjähriger Umsatz) aus, und wählen Sie alle drei Optionen („Wert“, „Ziel“, „Status“) aus.   
4. Suchen Sie im Visualisierungsbereich den Bereich **Werte**, und verschieben Sie die Werte mit Drag & Drop, bis die Reihenfolge der Diagrammspalten der in der ersten Abbildung auf dieser Seite entspricht.  Ihre Werte sehen nun wie folgt aus.

    ![Werte](media/power-bi-visualization-tables/power-bi-table2.png)
5. Heften Sie die Tabelle durch Auswählen des Anheften-Symbols am Dashboard an  

     ![Reißzwecke](media/power-bi-visualization-tables/pbi_pintile.png)

## <a name="format-the-table"></a>Formatieren der Tabelle
Es gibt viele Möglichkeiten zum Formatieren einer Tabelle, hier werden nur einige davon behandelt. Wenn Sie andere Formatierungsoptionen kennenlernen möchten, können Sie den Formatierungsbereich öffnen (Farbrollensymbol ![Farbrolle)](media/power-bi-visualization-tables/power-bi-format.png)und die einzelnen Optionen testen.

* Experimentieren Sie mit der Formatierung des Tabellenrasters. Hier haben wir ein blaues vertikales Raster hinzugefügt, Abstand zwischen den Zeilen hinzugefügt und die Kontur und den Text etwas vergrößert.

    ![Karte „Raster“](media/power-bi-visualization-tables/power-bi-table-gridnew.png)

    ![Tabelle mit Ergebnissen](media/power-bi-visualization-tables/power-bi-table-grid3.png)
* Bei den Spaltenüberschriften wurde die Hintergrundfarbe geändert, eine Gliederung hinzugefügt und die Schriftgröße vergrößert. 

    ![Karte „Spaltenüberschriften“](media/power-bi-visualization-tables/power-bi-table-column-headers.png)

    ![Headerformate in Tabelle](media/power-bi-visualization-tables/power-bi-table-column2.png)

* Sie können sogar einzelne Spalten und Spaltenheader formatieren. Erweitern Sie dazu zunächst die **Feldformatierung**, und wählen Sie die zu formatierende Spalte aus der Dropdownliste aus. Je nach Spaltenwerten können Sie über die Feldformatierung u.a Folgendes festlegen: Anzeigeeinheiten, Anzahl der Dezimalstellen, Hintergrund und Ausrichtung. Wenn Sie die Einstellungen angepasst haben, können Sie diese auch auf die Header und die Ergebniszeile anwenden.

    ![Feldformatierung für Verkäufe in diesem Jahr](media/power-bi-visualization-tables/power-bi-field-formatting.png)

* Unten sehen Sie die fertige Tabelle nach einigen weiteren Formatierungen. Da es so viele Formatierungsoptionen gibt, lernen Sie am besten, indem Sie mit der Standardformatierung beginnen, den Formatierungsbereich ![](media/power-bi-visualization-tables/power-bi-format.png) öffnen und die verschiedenen Optionen ausprobieren. 

    ![Tabelle mit allen bereits vorgenommenen Formatierungen](media/power-bi-visualization-tables/power-bi-table-format.png)

### <a name="conditional-formatting"></a>Bedingte Formatierung
Eine bestimmte Art der Formatierung wird als *bedingte Formatierung* bezeichnet und auf Felder in den Bereichen **Werte** und **Visualisierungen** im Power BI-Dienst oder in der Desktopversion angewendet. 

Mit der bedingten Formatierung für Tabellen können Sie benutzerdefinierte Hintergrundfarben für Zellen und Schriftfarben auf Grundlage von Zellwerten angeben, u.a. mit Verlaufsfarben. 

1. Wählen Sie im Bereich **Visualisierungen** im Power BI-Dienst oder in der Desktopversion den Dropdownpfeil neben dem Wert im Bereich **Werte** aus, den Sie formatieren möchten (oder klicken Sie mit der rechten Maustaste in das Feld). Sie können die bedingte Formatierung nur für Felder im Bereich **Werte** des Bereichs **Felder** verwalten.

    ![Pfad zu Skalen für die Hintergrundfarbe](media/power-bi-visualization-tables/power-bi-conditional-formatting-background.png)
2. Wählen Sie **Skalen für die Hintergrundfarbe** aus. Im angezeigten Dialogfeld können Sie die Farbe sowie die Werte für *Minimum* und *Maximum* konfigurieren. Wenn Sie das Kontrollkästchen **Abweichend** aktivieren, können Sie auch einen optionalen Wert für *Zentriert* konfigurieren.

    ![Anzeige „Skalen für die Hintergrundfarbe“](media/power-bi-visualization-tables/power-bi-conditional-formatting-background2.png)

    Lassen Sie uns jetzt einige benutzerdefinierte Formatierungen auf die Werte für den durchschnittlichen Einzelpreis anwenden. Wählen Sie **Abweichend** aus, fügen Sie Farben hinzu, und wählen Sie **OK** aus. 

    ![Tabelle mit abweichenden Farbskalen](media/power-bi-visualization-tables/power-bi-conditional-formatting-data-background.png)
3. Fügen Sie der Tabelle ein neues Feld mit positiven und negativen Werten hinzu.  Wählen Sie **Verkäufe > Gesamtabweichung Verkäufe** aus. 

    ![Neues Feld auf der rechten Seite](media/power-bi-visualization-tables/power-bi-conditional-formatting2.png)
4. Fügen Sie eine bedingte Formatierung für Datenbalken hinzu, indem Sie den Dropdownpfeil neben **Gesamtabweichung Verkäufe** und dann **Bedingte Formatierung > Datenbalken** auswählen.

    ![Pfad zum Auswählen von Datenbalken](media/power-bi-visualization-tables/power-bi-conditional-formatting-data-bars.png)
5. Legen Sie im daraufhin angezeigten Dialogfeld Farben für **Positiver Balken** und **Negativer Balken** fest, aktivieren Sie **Nur Balken anzeigen**, und nehmen Sie ggf. weitere Änderungen vor.

    ![Kontrollkästchen „Show bar only“ (Nur Balken anzeigen)](media/power-bi-visualization-tables/power-bi-data-bars.png)

    Wenn Sie **OK** auswählen, werden die numerischen Werte in der Tabelle durch Datenbalken ersetzt und sind so leichter zu erkennen.

    ![Dieselbe Tabelle, aber mit Balken in der letzten Spalte](media/power-bi-visualization-tables/power-bi-conditional-formatting-data-bars2.png)
6. Wenn Sie eine bedingte Formatierung aus einer Visualisierung entfernen möchten, klicken Sie einfach mit der rechten Maustaste erneut auf das Feld, und wählen Sie **Bedingte Formatierung entfernen** aus.

> [!TIP]
> Die bedingte Formatierung ist auch über den Formatierungsbereich verfügbar (Farbrollensymbol). Wählen Sie den zu formatierenden Wert aus, und legen Sie dann **Farbskalen** oder **Datenbalken** auf „Ein“ fest, um die Standardeinstellungen zu übernehmen. Wählen Sie **Erweiterte Steuerelemente** aus, um die Einstellungen anzupassen.
> 
> 

## <a name="adjust-the-column-width-of-a-table"></a>Anpassen der Spaltenbreite in einer Tabelle
Gelegentlich wird in Power BI eine Spaltenüberschrift in einem Bericht oder in einem Dashboard abgeschnitten. Zeigen Sie zum Anzeigen des gesamten Spaltennamens mit dem Mauszeiger auf den Bereich rechts neben der Überschrift, um die Doppelpfeile einzublenden, wählen Sie sie aus, und ziehen Sie sie.

![Video: Nahaufnahme zum Ändern der Größe von Spalten](media/power-bi-visualization-tables/resizetable.gif)

## <a name="considerations-and-troubleshooting"></a>Zu beachtende Aspekte und Problembehandlung
* Wenn Sie die Spaltenformatierung anwenden, können Sie nur eine Ausrichtungsoption pro Spalte auswählen: Auto, Links, Zentriert, Rechts. Normalerweise enthält eine Spalte den gesamten Text oder alle Zahlen und keine Mischung daraus. In Fällen, in denen jedoch eine Spalte jeweils Zahlen und Text enthält, wird durch die Auswahl von **Auto** der Text nach links ausgerichtet, und die Zahlen werden nach rechts ausgerichtet. Dieses Verhalten unterstützt Sprachen, in denen von links nach rechts gelesen wird.   

## <a name="next-steps"></a>Nächste Schritte

[Treemaps in Power BI](power-bi-visualization-treemaps.md)

[Visualisierungstypen in Power BI](power-bi-visualization-types-for-reports-and-q-and-a.md)