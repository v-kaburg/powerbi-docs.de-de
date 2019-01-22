---
title: Teil 1 – Hinzufügen von Visualisierungen zu einem Power BI-Bericht
description: Teil 1 – Hinzufügen von Visualisierungen zu einem Power BI-Bericht
author: mihart
manager: kvivek
ms.reviewer: ''
featuredvideoid: IkJda4O7oGs
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 08/23/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 52c0211aea0462e0bf79d7a48808f1f826c09fb6
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/15/2019
ms.locfileid: "54296085"
---
# <a name="part-i-add-visualizations-to-a-power-bi-report"></a>Teil 1 – Hinzufügen von Visualisierungen zu einem Power BI-Bericht
Dieser Artikel enthält eine kurze Einführung in das Erstellen einer Visualisierung in einem Bericht mit dem Power BI-Dienst oder Power BI Desktop.  Für komplexere Inhalte sehen Sie sich bitte [Teil 2](power-bi-report-add-visualizations-ii.md) an. Sehen Sie, wie Amanda verschiedene Methoden zum Erstellen, Bearbeiten und Formatieren von Visuals im Berichtszeichenbereich demonstriert. Versuchen Sie es dann selbst, indem Sie das [Beispiel für Vertrieb und Marketing](../sample-datasets.md) verwenden, um einen eigenen Bericht zu erstellen.

<iframe width="560" height="315" src="https://www.youtube.com/embed/IkJda4O7oGs" frameborder="0" allowfullscreen></iframe>


## <a name="open-a-report-and-add-a-new-page"></a>Öffnen eines Berichts und Hinzufügen einer neuen Seite
1. Öffnen Sie einen Bericht in der [Bearbeitungsansicht](../consumer/end-user-reading-view.md). In diesem Lernprogramm wird das [Beispiel für Vertrieb und Marketing](../sample-datasets.md) genutzt.
2. Wenn der Felderbereich nicht sichtbar ist, wählen Sie das Pfeilsymbol, um ihn zu öffnen. 
   
   ![](media/power-bi-report-add-visualizations-i/pbi_nancy_fieldsfiltersarrow.png)
3. Fügen Sie dem Bericht eine leere Seite hinzu.

## <a name="add-visualizations-to-the-report"></a>Hinzufügen von Visualisierungen zum Bericht
1. Erstellen Sie eine Visualisierung durch Auswahl eines Felds aus dem Bereich **Felder** .  
   
   **Beginnen Sie mit einem numerischen Feld** wie „SalesFact > Sales $“ (SalesFact > Verkäufe in $). Power BI erstellt ein Säulendiagramm mit einer einzelnen Spalte.
   
   ![](media/power-bi-report-add-visualizations-i/pbi_onecolchart.png)
   
   **Beginnen Sie alternativ mit einem Kategoriefeld**, z.B. mit „Name“ oder „Produkt“: Power BI erstellt eine Tabelle und fügt das Feld dem Bereich **Werte** hinzu.
   
   ![](media/power-bi-report-add-visualizations-i/pbi_agif_createchart3.gif)
   
   **Oder Sie beginnen mit einem geografischen Feld** wie „Geo > Ort“. Power BI und Bing Maps erstellen eine Kartenvisualisierung.
   
   ![](media/power-bi-report-add-visualizations-i/power-bi-map.png)
2. Erstellen Sie eine Visualisierung, und ändern Sie deren Typ. Wählen Sie **Produkt > Kategorie** und **Produkt > Count of Product** (Anzahl Produkt) aus, um beide dem Bereich **Werte** hinzuzufügen.
   
   ![](media/power-bi-report-add-visualizations-i/part1table1.png)
3. Ändern Sie die Visualisierung in einem Säulendiagramm, indem Sie das entsprechende Symbol wählen.
   
   ![](media/power-bi-report-add-visualizations-i/part1converttocolumn.png)
4. Wenn Sie Visualisierungen in Ihrem Bericht erstellen, können Sie sie [an Ihr Dashboard anheften](../service-dashboard-pin-tile-from-report.md). Um die Visualisierung anzuheften, wählen Sie das Anheftsymbol ![](media/power-bi-report-add-visualizations-i/pinnooutline.png).
   
   ![](media/power-bi-report-add-visualizations-i/part1pin1.png)
  

## <a name="next-steps"></a>Nächste Schritte
 Fortfahren mit [Teil 2: Hinzufügen von Visualisierungen zu einem Power BI-Bericht](power-bi-report-add-visualizations-ii.md)
   
   [Mit den Visualisierungen](../consumer/end-user-reading-view.md) im Bericht interagieren
   
   [Weiter Aktionen mit Visualisierungen ausführen](power-bi-report-visualizations.md)
   
   [Den Bericht speichern](../service-report-save.md)
