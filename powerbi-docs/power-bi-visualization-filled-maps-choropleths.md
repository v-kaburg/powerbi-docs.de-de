---
title: Flächenkartogramme (Choroplethenkarten) in Power BI
description: Dokumentation zum Erstellen von Flächenkartogrammen (Choroplethenkarten) in Power BI
author: mihart
manager: kfile
ms.reviewer: ''
featuredvideoid: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 06/22/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: f056ccb9e8fca4122aa4417a50f1fbd6993a9c2a
ms.sourcegitcommit: 2a7bbb1fa24a49d2278a90cb0c4be543d7267bda
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2018
ms.locfileid: "36944581"
---
# <a name="filled-maps-choropleths-in-power-bi"></a>Flächenkartogramme (Choroplethenkarten) in Power BI
In einem Flächenkartogramm wird mithilfe von Schattierungen, Farben oder Mustern angezeigt, in welchem Verhältnis Werte innerhalb eines geografischen Gebiets stehen.  Diese relativen Unterschiede werden mithilfe von Schattierungen angezeigt, wobei hell eine geringe Menge/Häufigkeit und dunkel eine große Menge/Häufigkeit anzeigt.    

![Karte der USA](media/power-bi-visualization-filled-maps-choropleths/large_map.png)

## <a name="what-is-sent-to-bing"></a>An Bing gesendete Informationen
Power BI arbeitet mit Bing zusammen, um Standardkartenkoordinaten bereitzustellen (ein Prozess, der als Geocodierung bezeichnet wird). Wenn Sie im Power BI-Dienst oder in Power BI Desktop eine Kartenvisualisierung erstellen, werden die Daten in den Buckets **Standort**, **Breitengrad** und **Längengrad** (die dazu verwendet werden, diese Visualisierung zu erstellen) an Bing gesendet.

Sie oder der Administrator müssen möglicherweise die Firewall aktualisieren, um den Zugriff auf die von Bing für die Geocodierung verwendeten URLs zuzulassen.  Diese URLs lauten:
    * https://dev.virtualearth.net/REST/V1/Locations
    * https://platform.bing.com/geo/spatial/v1/public/Geodata
    * https://www.bing.com/api/maps/mapcontrol

Weitere Informationen zu den an Bing gesendeten Daten sowie Tipps für eine erfolgreichere Geocodierung finden Sie unter [Tipps und Tricks für Power BI-Kartenvisualisierungen](power-bi-map-tips-and-tricks.md).

## <a name="when-to-use-a-filled-map"></a>Einsatz von Flächenkartogrammen
Flächenkartogramme sind gut für folgende Zwecke geeignet:

* Zum Anzeigen quantitativer Informationen auf einer Karte
* Zum Anzeigen räumlicher Muster und Beziehungen
* Bei standardisierten Daten
* Bei der Arbeit mit sozioökonomischen Daten
* Wenn bestimmte Regionen von Bedeutung sind
* Für einen Überblick in Bezug auf die Verteilung über geografische Standorte hinweg

### <a name="prerequisites"></a>Voraussetzungen
- Power BI-Dienst oder Power BI Desktop
- Sales and Marketing Sample

Im Tutorial wird der Power BI-Dienst und nicht Power BI Desktop verwendet.

## <a name="create-a-basic-filled-map"></a>Erstellen eines grundlegenden Flächenkartogramms
In diesem Video wird eine einfache Karte erstellt und in ein Flächenkartogramm umgewandelt.

<iframe width="560" height="315" src="https://www.youtube.com/embed/ajTPGNpthcg" frameborder="0" allowfullscreen></iframe>


1. Um ein eigenes Flächenkartogramm zu erstellen, [laden Sie das Beispiel für Vertrieb und Marketing herunter](sample-datasets.md). Melden Sie sich zu diesem Zweck bei Power BI an, und wählen Sie **Daten abrufen \> Beispiele \> Vertrieb und Marketing\> Verbinden** aus.
2. Wenn die Erfolgsmeldung angezeigt wird, wählen Sie **Dataset anzeigen** aus.

   ![Erfolgsmeldung](media/power-bi-visualization-filled-maps-choropleths/power-bi-view-dataset.png)
3. Power BI öffnet einen leeren Berichtszeichenbereich in der [Bearbeitungsansicht](service-interact-with-a-report-in-editing-view.md).

    ![Neuer Bericht](media/power-bi-visualization-filled-maps-choropleths/power-bi-blank-canvas.png)
4. Wählen Sie im Bereich „Felder“ das Feld **Geo** \> **Bundesstaat** aus.    

   ![Häkchen im gelben Kontrollkästchen neben „State“](media/power-bi-visualization-filled-maps-choropleths/img002.png)
5. [Wandeln Sie das Diagramm](power-bi-report-change-visualization-type.md) in ein Flächenkartogramm um. Beachten Sie, dass sich **Bundesstaat** jetzt im Bereich **Standort** befindet. Bing Maps verwendet das Feld unter **Standort**bereich, um die Karte zu erstellen.  Gültige Orte umfassen z. B. Länder, Bundesländer, Landkreise, Städte, Postleitzahlen usw. Bing Maps bietet verschiedene Formen für Orte auf der ganzen Welt. Ohne einen gültigen Wert im Bereich „Ort“ kann Power BI kein Flächenkartogramm erstellen.  

   ![Vorlagen mit dem hervorgehobenen Symbol für Flächenkartogramme](media/power-bi-visualization-filled-maps-choropleths/img003.png)
6. Filtern Sie die Karte, um nur die kontinentalen USA anzuzeigen.

   a.  Suchen Sie im unteren Teil des Visualisierungsbereichs nach **Filter** .

   b.  Zeigen Sie auf **Bundesland** , und klicken Sie auf das Erweiterungssymbol.  
   ![Filter auf visueller Ebene zeigt „State(All)“ an](media/power-bi-visualization-filled-maps-choropleths/img004.png)

   c.  Setzen Sie ein Häkchen neben **Alle** , und entfernen Sie das Häkchen neben **AK**.

   ![Dropdownliste für State, in der die Optionen „All“ und „AK“ nicht ausgewählt ist](media/power-bi-visualization-filled-maps-choropleths/img005.png)
7. Wählen Sie **SalesFact** \> **Stimmung**, um diese Option zum Bereich **Farbsättigung** hinzuzufügen. Das Feld im Bereich **Farbsättigung** steuert die Schattierung der Karte.  
   ![Sentiment im Feld für die Farbsättigung](media/power-bi-visualization-filled-maps-choropleths/power-bi-color-saturation.png)
8. Das Flächenkartogramm ist grün schattiert. Hellgrün steht dabei für schlechtere und dunkelgrün für bessere (d.h. positive) Stimmungsdaten.  Wenn Sie Wyoming (WY) markieren, sehen Sie, dass dieser Bundesstaat über einen positiven Stimmungswert (74) verfügt.  
   ![Schwarzes Dialogfeld zeigt „State“ und „Sentiment“](media/power-bi-visualization-filled-maps-choropleths/img007.png)
9. [Speichern Sie den Bericht](service-report-save.md).

## <a name="highlighting-and-cross-filtering"></a>Hervorheben und Kreuzfiltern
Informationen zur Verwendung des Filterbereichs finden Sie unter [Hinzufügen eines Filters zu einem Bericht in Power BI](power-bi-report-add-filter.md).

Das Markieren eines Orts in einem Flächenkartogramm ermöglicht ein Kreuzfiltern anderer Visualisierungen auf der Berichtsseite – und umgekehrt.

Kopieren Sie nun das Flächenkartogramm, und fügen Sie es auf der Seite **Stimmung** des Berichts *Vertrieb und Marketing* ein.

1. Wählen Sie auf dem Flächenkartogramm einen Bundesstaat aus.  Dadurch werden die anderen Visualisierungen auf der Seite hervorgehoben. Wenn Sie z. B. **Texas** auswählen, wird angezeigt, dass die Stimmung einen Wert von 74 aufweist, Texas sich im „District \#23“ befindet und der Großteil des Verkaufsvolumens den Bereichen „Moderation“ und „Verbrauchsgüter“ zuzuordnen ist.   
   ![Texas ausgewählt](media/power-bi-visualization-filled-maps-choropleths/img008.png)
2. Wechseln Sie im Liniendiagramm zwischen **Nein** und **Ja**. Dadurch wird das Flächenkartogramm gefiltert, und die Stimmung wird für VanArsdel sowie für die Wettbewerber von VanArsdel angezeigt.  
   ![Video der Umschalt-Funktion](media/power-bi-visualization-filled-maps-choropleths/img009.gif)

## <a name="considerations-and-troubleshooting"></a>Zu beachtende Aspekte und Problembehandlung
Kartendaten sind unter Umständen nicht eindeutig.  Neben Paris in Frankreich gibt es auch noch ein Paris in Texas. Ihre geografischen Daten sind wahrscheinlich in separaten Spalten gespeichert – eine Spalte für den Ortsnamen, eine Spalte für den Namen des Bundeslands oder des Landkreises usw. Für Bing ist es daher nicht eindeutig, welches Paris gemeint ist. Wenn das Dataset bereits Daten für die Breiten- und Längengrade enthält, umfasst Power BI spezielle Felder, mithilfe derer die Kartendaten eindeutig zugeordnet werden können. Ziehen Sie das Feld mit den Breitengraddaten in den Bereich „Visualisierungen \> Breitengrad“.  Führen Sie für den Längengrad die gleichen Schritte aus.  
![Bereiche für Visualisierungen und Felder](media/power-bi-visualization-filled-maps-choropleths/pbi_latitude.png)

Wenn Sie zum Bearbeiten des Datasets in Power BI Desktop berechtigt sind, erfahren Sie in diesem Video, wie Sie Mehrdeutigkeiten in Karten beheben.

<iframe width="560" height="315" src="https://www.youtube.com/embed/Co2z9b-s_yM" frameborder="0" allowfullscreen></iframe>

Wenn Sie keinen Zugriff auf die Breiten- und Längengraddaten haben, [befolgen Sie diese Anleitung, um Ihr Dataset zu aktualisieren](https://support.office.com/article/Maps-in-Power-View-8A9B2AF3-A055-4131-A327-85CC835271F7).

Weitere Hilfe zu Kartenvisualisierungen finden Sie unter [Tipps und Tricks für Kartenvisualisierungen](power-bi-map-tips-and-tricks.md).

## <a name="next-steps"></a>Nächste Schritte
[Fügen Sie das Flächenkartogramm als Dashboardkachel hinzu (Anheften des Visuals)](service-dashboard-tiles.md)  .  
 [Hinzufügen einer Visualisierung zu einem Bericht](power-bi-report-add-visualizations-i.md)  
 [Visualisierungstypen in Power BI](power-bi-visualization-types-for-reports-and-q-and-a.md)    
 [Ändern des verwendeten Visualisierungstyps](power-bi-report-change-visualization-type.md)      
Weitere Fragen? [Wenden Sie sich an die Power BI-Community](http://community.powerbi.com/)
