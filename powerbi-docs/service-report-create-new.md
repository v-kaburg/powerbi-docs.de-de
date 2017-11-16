---
title: 'Erstellen eines neuen Berichts aus einem Dataset '
description: Erstellen Sie einen neuen Power BI-Bericht aus einem Dataset.
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: monitoring
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/28/2017
ms.author: mihart
ms.openlocfilehash: f4afb1eaa1b3012fdbdb0eff35e9eff695cc32e4
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2017
---
# <a name="create-a-new-power-bi-report-by-importing-a-dataset"></a>Erstellen Sie einen neuen Power BI-Bericht durch Importieren eines Datasets.
Sie haben [Berichte in Power BI](service-reports.md) gelesen, und jetzt möchten Sie Ihren eigenen erstellen. Es gibt viele verschiedene Möglichkeiten zum Erstellen eines Berichts. In diesem Artikel wird zunächst ein sehr einfacher Bericht aus einem Excel-Dataset erstellt. Nachdem Sie die Grundlagen zur Erstellung eines Berichts kennen, gelangen Sie über die **nächsten Schritte** ganz unten zu komplexeren Themen über Berichte.  

> **TIPP:** Informationen zum Erstellen eines Berichts durch Kopieren eines vorhandenen Berichts finden Sie unter [Kopieren eines Berichts](power-bi-report-copy.md)
> 
> 

## <a name="import-the-dataset"></a>Importieren des Datasets
Diese Methode zum Erstellen eines Berichts beginnt mit einem Dataset und einem leeren Berichtszeichenbereich. Um die Vorgehensweise selbst nachzuvollziehen, [laden Sie das Excel-Dataset „Analysebeispiel für Einzelhandel“ herunter](http://go.microsoft.com/fwlink/?LinkId=529778), und speichern Sie es in OneDrive for Business (bevorzugt) oder lokal.

1. Wir erstellen den Bericht in einem Arbeitsbereich des Power BI-Diensts. Wählen Sie daher einen vorhandenen Arbeitsbereich aus, oder erstellen Sie einen neuen.
   
   ![](media/service-report-create-new/power-bi-workspaces2.png)
2. Wählen Sie unten im linken Navigationsbereich **Daten abrufen** aus.
   
   ![](media/service-report-create-new/power-bi-get-data3.png)
3. Wählen Sie **Dateien** aus, und navigieren Sie zum Speicherort des Beispiels für die Einzelhandelsanalyse.
   
    ![](media/service-report-create-new/power-bi-select-files.png)
4. Wählen Sie für diese Übung **Importieren** aus.
   
   ![](media/service-report-create-new/power-bi-import.png)
5. Nachdem das Dataset importiert wurde, wählen Sie **Dataset anzeigen** aus.
   
   ![](media/service-report-create-new/power-bi-view-dataset.png)
6. Durch das Anzeigen eines Datasets wird der Berichts-Editor geöffnet.  Sie sehen dort einen leeren Zeichenbereich und Bearbeitungstools für den Bericht.
   
   ![](media/service-report-create-new/power-bi-blank-report.png)

> **TIPP:** Wenn Sie mit dem Berichtszeichenbereich nicht vertraut sind oder Ihre Kenntnisse auffrischen möchten, [verschaffen Sie sich einen Überblick über den Berichts-Editor](service-the-report-editor-take-a-tour.md), bevor Sie fortfahren.
> 
> 

## <a name="add-a-radial-gauge-to-the-report"></a>Hinzufügen eines radialen Messgeräts zum Bericht
Nachdem das Dataset importiert wurde, beginnen wir damit, einige Fragen zu beantworten.  Die leitende Marketingbeauftragte (Chief Marketing Officer, CMO) möchte wissen, wie nahe wir den Vertriebszielen dieses Jahres sind. Ein Messgerät ist eine [gute Visualisierungsoption](power-bi-report-visualizations.md), um diese Art von Informationen anzuzeigen.

1. Wählen Sie im Felderbereich die Option **Sales** > **This Year Sales** > **Wert**.
   
    ![](media/service-report-create-new/power-bi-report-step1.png)
2. Konvertieren Sie die Visualisierung in einen Maßstab, indem Sie die Vorlage für „Maßstab“ ![](media/service-report-create-new/powerbi-gauge-icon.png) aus dem Bereich **Visualisierungen** auswählen.
   
    ![](media/service-report-create-new/power-bi-report-step2.png)
3. Ziehen Sie **Sales** > **This Year Sales** > **Ziel** in den Bereich **Zielwert**. Anscheinend haben wir unser Ziel nahezu erreicht.
   
    ![](media/service-report-create-new/power-bi-report-step3.png)
4. Jetzt sollte [der Bericht gespeichert werden](service-report-save.md).
   
   ![](media/service-report-create-new/powerbi-save.png)

## <a name="add-an-area-chart-and-slicer-to-the-report"></a>Hinzufügen eines Flächendiagramms und Slicers zum Bericht
Die CMO stellt noch weitere Fragen, die beantwortet werden müssen. Sie möchte die Umsätze dieses Jahres im Vergleich zum Vorjahr einsehen. Die Ergebnisse möchte sie nach Region geordnet anzeigen.

1. Zunächst schaffen wir etwas Platz im Zeichenbereich. Wählen Sie das Messgerät aus, und verschieben Sie es in die obere rechte Ecke. Ziehen Sie dann eine der Ecken, und verkleinern Sie es.
2. Heben Sie die Auswahl des Messgeräts auf. Wählen Sie im Felderbereich die Option **Sales** > **This Year Sales** > **Wert**, und wählen Sie dann **Sales** > **Last Year Sales**.
   
    ![](media/service-report-create-new/power-bi-report-step4.png)
3. Konvertieren Sie das Visual in ein Flächendiagramm, indem Sie die Vorlage für Flächendiagramme ![](media/service-report-create-new/power-bi-areachart-icon.png) aus dem Bereich **Visualisierungen** auswählen.
4. Wählen Sie **Zeit** > **Zeitraum**, um es auch der **Achse** hinzuzufügen.
   
    ![](media/service-report-create-new/power-bi-report-step5.png)
5. Wählen Sie zum Sortieren des Visuals die Auslassungspunkte und anschließend die Option **Sort by Period** (Nach Zeitraum sortieren) aus.
6. Nun fügen wir den Slicer hinzu. Wählen Sie einen leeren Bereich im Zeichenbereich aus, und wählen Sie dann die Vorlage für Slicer ![](media/service-report-create-new/power-bi-slicer-icon.png) aus. Dadurch wird im Zeichenbereich ein leerer Slicer hinzugefügt.
   
    ![](media/service-report-create-new/power-bi-report-step6.png)    
7. Wählen Sie im Bereich „Felder“ die Option **Region** > **Region** aus. Verschieben Sie den Slicer, und ändern Sie seine Größe.
   
    ![](media/service-report-create-new/power-bi-report-step7.png)  
8. Verwenden Sie den Slicer, um nach Mustern und Einblicken nach Region zu suchen.
   
   ![](media/service-report-create-new/power-bi-slicer-video2.gif)  
9. Fügen Sie optional weitere Visualisierungen hinzu.

## <a name="next-steps"></a>Nächste Schritte
* [Erstellen der Kopie eines Berichts](power-bi-report-copy.md)
* [Speichern des Berichts](service-report-save.md)    
* [Hinzufügen einer neuen Seite zum Bericht](power-bi-report-add-page.md)  
* Erfahren Sie, wie Sie [Visualisierungen an ein Dashboard anheften](service-dashboard-pin-tile-from-report.md).    
* Weitere Fragen? [Wenden Sie sich an die Power BI-Community](http://community.powerbi.com/)

