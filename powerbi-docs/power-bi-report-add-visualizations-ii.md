---
title: "Teil 2 – Hinzufügen von Visualisierungen zu einem Power BI-Bericht (Lernprogramm)"
description: "Lernprogramm: Teil 2 – Hinzufügen von Visualisierungen zu einem Power BI-Bericht"
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
ms.date: 01/23/2018
ms.author: mihart
ms.openlocfilehash: 40d6ee1f1448856b444201532caffd4b8c904c85
ms.sourcegitcommit: c3be4de522874fd73fe6854333b379b85619b907
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2018
---
# <a name="part-2-add-visualizations-to-a-power-bi-report-tutorial"></a>Teil 2 – Hinzufügen von Visualisierungen zu einem Power BI-Bericht (Lernprogramm)
In [Teil 1](power-bi-report-add-visualizations-ii.md) haben Sie eine einfache Visualisierung erstellt, indem Sie Kontrollkästchen neben Feldnamen aktiviert haben.  In Teil 2 lernen Sie, wie Sie Drag &amp; Drop verwenden und die Funktionen der Bereiche **Felder** und **Visualisierungen** nutzen, um Visualisierungen zu erstellen und zu ändern.

### <a name="prerequisites"></a>Voraussetzungen
- [Teil 1](power-bi-report-add-visualizations-ii.md)
- Power BI-Dienst: Mithilfe von Power BI Desktop bzw. des Power BI-Diensts können Visualisierungen zu Berichten hinzugefügt werden. Dieses Tutorial verwendet den Power BI-Dienst. 
- Analysebeispiel für den Einzelhandel

## <a name="create-a-new-visualization"></a>Erstellen einer neuen Visualisierung
In diesem Tutorial verwenden wir unser Dataset mit Einzelhandelsdaten und erstellen einige wichtige Visualisierungen.

### <a name="open-a-report-and-add-a-new-blank-page"></a>Öffnen Sie einen Bericht, und fügen Sie eine neue leere Seite hinzu.
1. Öffnen Sie den Arbeitsbereich, in dem Sie das Analysebeispiel für den Einzelhandel gespeichert haben. Wählen Sie **Analysebeispiel für Einzelhandel** aus, um den Bericht in der Leseansicht zu öffnen.
   
   ![](media/power-bi-report-add-visualizations-ii/power-bi-open-report.png)
2. Wählen Sie **Bericht bearbeiten** , um den Bericht in der Bearbeitungsansicht zu öffnen.
   
   ![](media/power-bi-report-add-visualizations-ii/editreport1.png)
3. [Fügen Sie eine neue Seite hinzu](power-bi-report-add-page.md), indem Sie das gelbe Pluszeichen am unteren Rand des Zeichenbereichs auswählen.
   
   ![](media/power-bi-report-add-visualizations-ii/pbi_addreportpage.png)

### <a name="add-a-visualization-that-looks-at-this-years-sales-compared-to-last-year"></a>Fügen Sie eine Visualisierung hinzu, mit der der Umsatz dieses Jahres mit dem Umsatz des Vorjahrs verglichen wird.
1. Wählen Sie in der Tabelle **Verkäufe** zunächst **Verkäufe in diesem Jahr** > **Wert** und dann **Verkäufe im letzten Jahr** aus. Power BI erstellt ein Säulendiagramm.  Dies sieht interessant aus, und Sie möchten noch mehr erfahren. Wie hoch sind die Verkäufe pro Monat?  
   
   ![](media/power-bi-report-add-visualizations-ii/pbi_part2_4bnew.png)
2. Ziehen Sie aus der Zeittabelle **Monat** in den Bereich **Achse**.  
   ![](media/power-bi-report-add-visualizations-ii/pbi_part2_5newnew.png)
3. [Ändern Sie die Visualisierung](power-bi-report-change-visualization-type.md) in ein Flächendiagramm.  Es gibt viele Arten von Visualisierung, aus denen Sie wählen können. In den dazugehörigen [Beschreibungen, Tipps für bewährte Methoden und Tutorials](power-bi-visualization-types-for-reports-and-q-and-a.md) finden Sie Hilfe zum Auswählen des geeigneten Typs. Wählen Sie im Bereich „Visualisierungen“ das Symbol für das Flächendiagramm.
4. Sortieren Sie die Visualisierungen, indem Sie auf die Auslassungspunkte klicken und **Sortieren nach Monat** auswählen.
5. [Ändern Sie die Größe der Visualisierung](power-bi-visualization-move-and-resize.md), indem Sie die Visualisierung auswählen und einen der Konturkreise per Ziehbewegung verschieben. Machen Sie die Visualisierung so breit, dass die Scrollleiste ausgeblendet wird, und klein genug, damit noch Platz für eine weitere Visualisierung ist.
   
   ![](media/power-bi-report-add-visualizations-ii/pbi_part2_7b.png)
6. [Speichern Sie den Bericht](service-report-save.md).

### <a name="add-a-map-visualization-that-looks-at-sales-by-location"></a>Hinzufügen einer Kartenvisualisierung für Verkäufe nach Standort
1. Wählen Sie in der Tabelle **Geschäft** **Gebiet** aus. Power BI erkennt, dass „Gebiet“ ein Ort ist, und erstellt eine Kartenvisualisierung.  
   ![](media/power-bi-report-add-visualizations-ii/pbi_part2_8newnew.png)
2. Ziehen Sie **Läden gesamt** in den Bereich „Werte“.  
   ![](media/power-bi-report-add-visualizations-ii/power-bi-add-visual-to-a-reportnew.png)
3. Fügen Sie eine Legende hinzu.  Ziehen Sie **Kette** in den Bereich „Legende“, um die Daten nach dem Namen des Geschäfts anzuzeigen.  
   ![](media/power-bi-report-add-visualizations-ii/power-bi-add-visual-to-a-report-3new.png)

## <a name="next-steps"></a>Nächste Schritte
* Weitere Informationen zum Bereich „Felder“ finden Sie unter [Berichts-Editor: Verschaffen Sie sich einen Überblick](service-the-report-editor-take-a-tour.md).   
* Informationen zum Filtern und Hervorheben der Visualisierungen finden Sie unter [Filter und Hervorhebungen in Power BI-Berichten](power-bi-reports-filters-and-highlighting.md).  
* Weitere Informationen zu [Visualisierungen in Power BI-Berichten](power-bi-report-visualizations.md).  
* Weitere Fragen? [Wenden Sie sich an die Power BI-Community](http://community.powerbi.com/)

