---
title: Tabellenvisualisierungen in Power BI-Berichten und -Dashboards
description: Tutorial zum Arbeiten mit Tabellenvisualisierungen in Power BI-Berichten und -Dashboards, einschließlich Erläuterungen zum Ändern der Spaltenbreite.
author: mihart
manager: kfile
ms.reviewer: ''
featuredvideoid: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 04/11/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 37f4e06aee41b8741dd3a1a1a52e3237fbd893a3
ms.sourcegitcommit: 638de55f996d177063561b36d95c8c71ea7af3ed
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/17/2018
ms.locfileid: "34293258"
---
# <a name="working-with-tables-in-power-bi-reports-and-dashboards"></a>Arbeiten mit Tabellen in Power BI-Berichten und -Dashboards
Eine Tabelle ist ein Raster, das zusammengehörende Daten in einer logischen Folge von Zeilen und Spalten enthält. Zudem können auch Kopfzeilen und eine Zeile für Summen enthalten sein. Tabellen empfehlen sich insbesondere für quantitative Vergleiche, bei denen Sie viele Werte einer einzigen Kategorie betrachten. In dieser Tabelle werden beispielsweise fünf verschiedene Measures für **Kategorie** angezeigt.

![](media/power-bi-visualization-tables/table.png)

## <a name="when-to-use-a-table"></a>Verwenden von Tabellen
Tabellen sind für folgende Zwecke gut geeignet:

* Anzeigen und Vergleichen detaillierter Daten und genauer Werte (anstelle von visuellen Darstellungen)
* Auflisten von Daten in einem Tabellenformat
* Anzeigen numerischer Daten nach Kategorien   

> [!NOTE]
> Enthält eine Tabelle zu viele Werte, erwägen Sie, sie in eine Matrix zu konvertieren und/oder die Drilldownfunktion zu verwenden.
> 
> 
## <a name="prerequisites"></a>Voraussetzungen
 - Power BI-Dienst oder Power BI Desktop
 - Retail Analysis sample


## <a name="create-a-table"></a>Erstellen einer Tabelle
Wir erstellen die oben abgebildete Tabelle, in der Umsatzwerte nach Artikelkategorien angezeigt werden. Melden Sie sich beim Power BI-Dienst an, wählen Sie **Daten abrufen\> Beispiele \> Analysebeispiel für Einzelhandel > Verbinden** aus, und wählen Sie **„Zum Dashboard wechseln“. Zum Erstellen einer Visualisierung benötigen Sie Bearbeitungsberechtigungen für das Dataset und den Bericht. Erfreulicherweise können die Power BI-Beispiele alle bearbeitet werden. Wenn ein Bericht für Sie freigegeben wurde, können Sie keine Visualisierungen in Berichten erstellen.

1. Wählen Sie links im Navigationsbereich **Arbeitsbereiche > Mein Arbeitsbereich** aus.    
2. Wählen Sie die Registerkarte „Datasets“ aus, und führen Sie einen Bildlauf nach unten zum gerade hinzugefügten Dataset „Analysebeispiel für Einzelhandel“ durch.  Wählen Sie das Symbol **Bericht erstellen** aus.
   
    ![](media/power-bi-visualization-tables/power-bi-create-report.png)
2. Wählen Sie im Berichts-Editor **Element** > **Kategorie** aus.  Power BI erstellt automatisch eine Tabelle, in der alle Kategorien aufgelistet werden.
   
    ![](media/power-bi-visualization-tables/power-bi-table1.png)
3. Wählen Sie **Sales > Average Unit Price** (Umsatz > Durchschnittlicher Stückpreis), **Sales > Last Year Sales** (Umsatz > Vorjahresumsatz) und **Sales > This Year Sales** (Umsatz > Diesjähriger Umsatz) aus, und wählen Sie alle drei Optionen („Wert“, „Ziel“, „Status“) aus.   
4. Suchen Sie im Visualisierungsbereich den Bereich **Werte**, und verschieben Sie die Werte mit Drag & Drop, bis die Reihenfolge der Diagrammspalten der in der ersten Abbildung auf dieser Seite entspricht.  Ihre Werte sehen nun wie folgt aus.
   
    ![](media/power-bi-visualization-tables/power-bi-table2.png)
5. Heften Sie die Tabelle durch Auswählen des Anheften-Symbols am Dashboard an  
   
     ![](media/power-bi-visualization-tables/pbi_pintile.png)

## <a name="format-the-table"></a>Formatieren der Tabelle
Es gibt viele Möglichkeiten zum Formatieren einer Tabelle, hier werden nur einige davon behandelt. Eine hervorragende Möglichkeit zum Kennenlernen der weiteren Formatierungsoptionen besteht darin, den Formatierungsbereich zu öffnen (Farbrollensymbol ![](media/power-bi-visualization-tables/power-bi-format.png)) und diesen genauer zu betrachten.

* Experimentieren Sie mit der Formatierung des Tabellenrasters. Hier haben wir ein blaues vertikales Raster hinzugefügt, Abstand zwischen den Zeilen hinzugefügt und die Kontur und den Text etwas vergrößert.
  
    ![](media/power-bi-visualization-tables/power-bi-table-gridnew.png)
  
    ![](media/power-bi-visualization-tables/power-bi-table-grid3.png)
* Bei den Spaltenüberschriften wurde die Hintergrundfarbe geändert, eine Gliederung hinzugefügt und die Schriftgröße vergrößert. 
  
    ![](media/power-bi-visualization-tables/power-bi-table-column-headers.png)

  
    ![](media/power-bi-visualization-tables/power-bi-table-column2.png)

* Sie können sogar einzelne Spalten und Spaltenheader formatieren. Erweitern Sie dazu zunächst die **Feldformatierung**, und wählen Sie die zu formatierende Spalte aus der Dropdownliste aus. Je nach Spaltenwerten können Sie über die Feldformatierung u.a Folgendes festlegen: Anzeigeeinheiten, Anzahl der Dezimalstellen, Hintergrund und Ausrichtung. Wenn Sie die Einstellungen angepasst haben, können Sie diese auch auf die Header und die Ergebniszeile anwenden.

    ![](media/power-bi-visualization-tables/power-bi-field-formatting.png)

* Unten sehen Sie die fertige Tabelle nach einigen weiteren Formatierungen. Da es so viele Formatierungsoptionen gibt, lernen Sie am besten, indem Sie mit der Standardformatierung beginnen, den Formatierungsbereich ![](media/power-bi-visualization-tables/power-bi-format.png) öffnen und die verschiedenen Optionen ausprobieren. 
  
    ![](media/power-bi-visualization-tables/power-bi-table-format.png)

### <a name="conditional-formatting"></a>Bedingte Formatierung
Eine bestimmte Art der Formatierung wird als *bedingte Formatierung* bezeichnet und auf Felder in den Bereichen **Werte** und **Visualisierungen** im Power BI-Dienst oder in der Desktopversion angewendet. 

Mit der bedingten Formatierung für Tabellen können Sie benutzerdefinierte Hintergrundfarben für Zellen und Schriftfarben auf Grundlage von Zellwerten angeben, u.a. mit Verlaufsfarben. 

1. Wählen Sie im Bereich **Visualisierungen** im Power BI-Dienst oder in der Desktopversion den Dropdownpfeil neben dem Wert im Bereich **Werte** aus, den Sie formatieren möchten (oder klicken Sie mit der rechten Maustaste in das Feld). Sie können die bedingte Formatierung nur für Felder im Bereich **Werte** des Bereichs **Felder** verwalten.
   
    ![](media/power-bi-visualization-tables/power-bi-conditional-formatting-background.png)
2. Wählen Sie **Skalen für die Hintergrundfarbe** aus. Im angezeigten Dialogfeld können Sie die Farbe sowie die Werte für *Minimum* und *Maximum* konfigurieren. Wenn Sie das Kontrollkästchen **Abweichend** aktivieren, können Sie auch einen optionalen Wert für *Zentriert* konfigurieren.
   
    ![](media/power-bi-visualization-tables/power-bi-conditional-formatting-background2.png)
   
    Lassen Sie uns jetzt einige benutzerdefinierte Formatierungen auf die Werte für den durchschnittlichen Einzelpreis anwenden. Wählen Sie **Abweichend** aus, fügen Sie Farben hinzu, und wählen Sie **OK** aus. 
   
    ![](media/power-bi-visualization-tables/power-bi-conditional-formatting-data-background.png)
3. Fügen Sie der Tabelle ein neues Feld mit positiven und negativen Werten hinzu.  Wählen Sie **Verkäufe > Gesamtabweichung Verkäufe** aus. 
   
    ![](media/power-bi-visualization-tables/power-bi-conditional-formatting2.png)
4. Fügen Sie eine bedingte Formatierung für Datenbalken hinzu, indem Sie den Dropdownpfeil neben **Gesamtabweichung Verkäufe** und dann **Bedingte Formatierung > Datenbalken** auswählen.
   
    ![](media/power-bi-visualization-tables/power-bi-conditional-formatting-data-bars.png)
5. Legen Sie im daraufhin angezeigten Dialogfeld Farben für **Positiver Balken** und **Negativer Balken** fest, aktivieren Sie **Nur Balken anzeigen**, und nehmen Sie ggf. weitere Änderungen vor.
   
    ![](media/power-bi-visualization-tables/power-bi-data-bars.png)
   
    Wenn Sie **OK** auswählen, werden die numerischen Werte in der Tabelle durch Datenbalken ersetzt und sind so leichter zu erkennen.
   
    ![](media/power-bi-visualization-tables/power-bi-conditional-formatting-data-bars2.png)
6. Wenn Sie eine bedingte Formatierung aus einer Visualisierung entfernen möchten, klicken Sie einfach mit der rechten Maustaste erneut auf das Feld, und wählen Sie **Bedingte Formatierung entfernen** aus.

> [!TIP]
> Die bedingte Formatierung ist auch über den Formatierungsbereich verfügbar (Farbrollensymbol). Wählen Sie den zu formatierenden Wert aus, und legen Sie dann **Farbskalen** oder **Datenbalken** auf „Ein“ fest, um die Standardeinstellungen zu übernehmen. Wählen Sie **Erweiterte Steuerelemente** aus, um die Einstellungen anzupassen.
> 
> 

## <a name="adjust-the-column-width-of-a-table"></a>Anpassen der Spaltenbreite in einer Tabelle
Gelegentlich wird in Power BI eine Spaltenüberschrift in einem Bericht oder in einem Dashboard abgeschnitten. Zeigen Sie zum Anzeigen des gesamten Spaltennamens mit dem Mauszeiger auf den Bereich rechts neben der Überschrift, um die Doppelpfeile einzublenden, wählen Sie sie aus, und ziehen Sie sie.

![](media/power-bi-visualization-tables/resizetable.gif)

Weitere Fragen? [Wenden Sie sich an die Power BI-Community](http://community.powerbi.com/)

