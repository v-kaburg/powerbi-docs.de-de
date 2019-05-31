---
title: Erstellen eines Berichts aus einem Dataset
description: Erstellen Sie einen Power BI-Bericht aus einem Dataset.
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 04/25/2019
ms.author: maggies
LocalizationGroup: Reports
ms.openlocfilehash: 6b69c2b1fa811d395a26403de852c44af33491c7
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2019
ms.locfileid: "64770234"
---
# <a name="create-a-report-in-the-power-bi-service-by-importing-a-dataset"></a>Erstellen eines Berichts im Power BI-Dienst durch Importieren eines Datasets
Sie haben [Berichte in Power BI](consumer/end-user-reports.md) gelesen, und jetzt möchten Sie Ihren eigenen erstellen. Es gibt verschiedene Möglichkeiten zum Erstellen eines Berichts. In diesem Artikel beginnen wir durch das Erstellen eines einfachen Berichts im Power BI-Dienst aus einem Excel-Dataset. Wenn Sie die Grundlagen zum Erstellen eines Berichts verstehen, sehen Sie sich die [nächste Schritte](#next-steps) am Ende Weitere Erweiterte Themen des Berichts.  

## <a name="prerequisites"></a>Voraussetzungen
- [Melden Sie sich für Power BI-Dienst](service-self-service-signup-for-power-bi.md). Erstellen von Berichten mit Power BI Desktop, finden Sie unter [Desktop-Berichtsansicht](desktop-report-view.md). 
- [Herunterladen der Beispiel-Excel-Dataset mit Einzelhandelsdaten](http://go.microsoft.com/fwlink/?LinkId=529778) und in OneDrive for Business oder lokal zu speichern.

## <a name="import-the-dataset"></a>Importieren des Datasets
Diese Methode zum Erstellen eines Berichts beginnt mit einem Dataset und einem leeren Berichtszeichenbereich. Sie können in der Beispiel-Excel-Dataset mit Einzelhandelsdaten folgen.

1. Wir müssen den Bericht in einem Arbeitsbereich des Power BI-Dienst erstellen, daher wählen Sie einen vorhandenen Arbeitsbereich oder eine 1: erstellen.
   
   ![Liste von App-Arbeitsbereichen](media/service-report-create-new/power-bi-workspaces2.png)
2. Wählen Sie unten im linken Navigationsbereich, **Abrufen von Daten**.
   
   ![Daten abrufen](media/service-report-create-new/power-bi-get-data3.png)
3. Wählen Sie **Dateien** aus, und navigieren Sie zum Speicherort des Beispiels für die Einzelhandelsanalyse.
   
    ![„Dateien“ auswählen](media/service-report-create-new/power-bi-select-files.png)
4. Wählen Sie für diese Übung **Importieren** aus.
   
   ![„Importieren“ auswählen](media/service-report-create-new/power-bi-import.png)
5. Nachdem das Dataset importiert wurde, wählen Sie **Dataset anzeigen** aus.
   
   ![„Dashboard anzeigen“ auswählen](media/service-report-create-new/power-bi-view-dataset.png)
6. Durch das Anzeigen eines Datasets wird der Berichts-Editor geöffnet.  Sie sehen dort einen leeren Zeichenbereich und Bearbeitungstools für den Bericht.
   
   ![Berichts-Editor](media/service-report-create-new/power-bi-blank-report.png)

> [!TIP]
> Wenn Sie nicht vertraut sind, mit dem berichtszeichenbereich oder auffrischen, [Überblick über den Berichts-Editor](service-the-report-editor-take-a-tour.md) vor dem fortfahren. > 
> 

## <a name="add-a-radial-gauge-to-the-report"></a>Hinzufügen eines radialen Messgeräts zum Bericht
Nachdem das Dataset importiert wurde, beginnen wir damit, einige Fragen zu beantworten.  Die leitende Marketingbeauftragte (Chief Marketing Officer, CMO) möchte wissen, wie nahe wir den Vertriebszielen dieses Jahres sind. Ein Messgerät ist eine [gute Visualisierungsoption](visuals/power-bi-report-visualizations.md), um diese Art von Informationen anzuzeigen.

1. Wählen Sie im Felderbereich die Option **Sales** > **This Year Sales** > **Wert**.
   
    ![Balkendiagramm im Berichts-Editor](media/service-report-create-new/power-bi-report-step1.png)
2. Konvertieren Sie das Visual in einen Maßstab, indem Sie im Bereich **Visualisierungen** auf die Vorlage für „Maßstab“ ![Symbol „Maßstab“](media/service-report-create-new/powerbi-gauge-icon.png) klicken.
   
    ![Visuelles Element „Maßstab“ im Berichts-Editor](media/service-report-create-new/power-bi-report-step2.png)
3. Ziehen Sie **Sales** > **This Year Sales** > **Ziel** in den Bereich **Zielwert**. Anscheinend haben wir unser Ziel nahezu erreicht.
   
    ![Visuelles Element „Maßstab“ mit dem Zielwert „Ziel“](media/service-report-create-new/power-bi-report-step3.png)
4. Nun wäre ein guter Zeitpunkt für den Bericht zu speichern.
   
   ![Dateimenü](media/service-report-create-new/powerbi-save.png)

## <a name="add-an-area-chart-and-slicer-to-the-report"></a>Hinzufügen eines Flächendiagramms und Slicers zum Bericht
Die CMO stellt noch weitere Fragen, die beantwortet werden müssen. Sie möchte die Umsätze dieses Jahres im Vergleich zum Vorjahr einsehen. Die Ergebnisse möchte sie nach Region geordnet anzeigen.

1. Zunächst schaffen wir etwas Platz im Zeichenbereich. Wählen Sie das Messgerät aus, und verschieben Sie es in die obere rechte Ecke. Ziehen Sie dann eine der Ecken, und verkleinern Sie es.
2. Heben Sie die Auswahl des Messgeräts auf. Wählen Sie im Felderbereich die Option **Sales** > **This Year Sales** > **Wert**, und wählen Sie dann **Sales** > **Last Year Sales**.
   
    ![Berichts-Editor mit „Maßstab“ und Balkendiagramm](media/service-report-create-new/power-bi-report-step4.png)
3. Konvertieren Sie das Visual in ein Flächendiagramm, indem Sie im Bereich **Visualisierungen** auf die Vorlage für Flächendiagramme ![Symbol „Diagramm“](media/service-report-create-new/power-bi-areachart-icon.png) klicken.
4. Wählen Sie **Zeit** > **Zeitraum**, um es auch der **Achse** hinzuzufügen.
   
    ![Berichts-Editor mit aktivem Flächendiagramm](media/service-report-create-new/power-bi-report-step5.png)
5. Wählen Sie zum Sortieren der Visualisierung die Auslassungspunkte und anschließend die Option **Nach Zeitraum sortieren** aus.
6. Nun fügen wir den Slicer hinzu. Klicken Sie zunächst auf einen leeren Bereich im Zeichenbereich und anschließend auf die Slicer- ![Symbol „Slicer“](media/service-report-create-new/power-bi-slicer-icon.png) Vorlage. Wir haben jetzt einen leeren Slicer im Zeichenbereich.
   
    ![dem Zeichenbereich für den Bericht](media/service-report-create-new/power-bi-report-step6.png)    
7. Wählen Sie im Bereich „Felder“ die Option **Region** > **Region** aus. Verschieben Sie den Slicer, und ändern Sie seine Größe.
   
    ![Berichts-Editor, „Region“ hinzufügen](media/service-report-create-new/power-bi-report-step7.png)  
8. Verwenden Sie den Slicer, um nach Mustern und Einblicken nach Region zu suchen.
   
   ![Video zur Verwendung des Slicers](media/service-report-create-new/power-bi-slicer-video2.gif)  

Erkunden Sie weiter Ihre Daten, und fügen Sie Visualisierungen hinzu. Wenn Sie interessante Einblicke finden, [heften Sie diese an ein Dashboard](service-dashboard-pin-tile-from-report.md) an.

## <a name="next-steps"></a>Nächste Schritte

* Erfahren Sie, wie Sie [Visualisierungen an ein Dashboard anheften](service-dashboard-pin-tile-from-report.md).   
* Weitere Fragen? [Wenden Sie sich an die Power BI-Community](http://community.powerbi.com/)

