---
title: Erstellen eines Power BI-Dashboards aus einem Bericht
description: Erstellen eines Power BI-Dashboards aus einem Bericht
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: 
qualityfocus: 
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 05/09/2017
ms.author: mihart
ms.openlocfilehash: 67cc9508d71fa29303d09e8901294a2d6b7f8a56
ms.sourcegitcommit: 804ee18b4c892b7dcbd7d7d5d987b16ef16fc2bb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2018
---
# <a name="create-a-power-bi-dashboard-from-a-report"></a>Erstellen eines Power BI-Dashboards aus einem Bericht
Sie haben [Dashboards in Power BI](service-dashboards.md) gelesen, und jetzt möchten Sie Ihr eigenes erstellen. Ein Dashboard kann auf verschiedene Arten erstellt werden, beispielsweise aus einem Bericht, von Grund auf neu, aus einem Dataset oder durch Duplizieren eines vorhandenen Dashboards.  In diesem Thema und dem zugehörigen Video erfahren Sie, wie Sie ein neues Dashboard durch Anheften von Visualisierungen aus einem vorhandenen Bericht erstellen.

> **HINWEIS**: Dashboards sind ein Feature des Power BI-Diensts und nicht von Power BI Desktop. Obwohl Dashboards nicht mit Power BI Mobile erstellt werden können, lassen sie sich dort [anzeigen und freigeben](mobile-apps-view-dashboard.md).
> 
> 

![](media/service-dashboard-create/power-bi-completed-dashboard-small.png)

## <a name="video-create-a-dashboard-by-pinning-visuals-and-images-from-a-report"></a>Video: Erstellen eines Dashboards durch Anheften von Visuals und Bildern aus einem Bericht
Amanda zeigt Ihnen, wie Sie ein neues Dashboard erstellen, indem Sie Visualisierungen aus einem Bericht anheften. Wenn Sie es selbst ausprobieren möchten, verwenden Sie das Beispiel für die Beschaffungsanalyse, und befolgen Sie die Schritte unter dem Video.

<iframe width="560" height="315" src="https://www.youtube.com/embed/lJKgWnvl6bQ" frameborder="0" allowfullscreen></iframe>

## <a name="import-a-dataset-with-a-report"></a>Importieren eines Datasets mit einem Bericht
Wir werden eines der Beispiel-Power BI-Datasets importieren, um damit unser neues Dashboard zu erstellen. Das Beispiel ist eine Excel-Arbeitsmappe mit zwei PowerView-Tabellen. Wenn Sie die Arbeitsmappe in Power BI importieren, werden ein Dataset und ein Bericht Ihrem Arbeitsbereich hinzugefügt.  Der Bericht wird automatisch aus den PowerView-Tabellen erstellt.

1. [Folgen Sie diesem Link](http://go.microsoft.com/fwlink/?LinkId=529784), um die Excel-Datei des Beispiels für die Beschaffungsanalyse herunterzuladen und zu speichern. Wir empfehlen, die Datei in OneDrive for Business zu speichern.
2. Öffnen Sie den Power BI-Dienst in einem Browser (app.powerbi.com).
3. Wählen Sie einen vorhandenen Arbeitsbereich aus, oder erstellen Sie einen neuen App-Arbeitsbereich.
4. Wählen Sie im linken Navigationsbereich **Daten abrufen** aus.
   
    ![](media/service-dashboard-create/power-bi-get-data3.png)
5. Wählen Sie **Dateien**aus.
   
   ![](media/service-dashboard-create/power-bi-select-files.png)
6. Navigieren Sie zum Speicherort der Excel-Datei des Beispiels für die Beschaffungsanalyse. Wählen Sie die Datei und dann **Verbinden** aus.
   
   ![](media/service-dashboard-create/power-bi-connectnew.png)
7. Wählen Sie für diese Übung **Importieren** aus.
   
    ![](media/service-dashboard-create/power-bi-import.png)
8. Wenn die Erfolgsmeldung angezeigt wird, schließen Sie sie mit **x**.
   
   ![](media/service-dashboard-create/power-bi-view-datasetnew.png)

### <a name="open-the-report-and-pin-some-tiles-to-a-dashboard"></a>Öffnen des Berichts und Anheften von Kacheln an ein Dashboard
1. Wählen Sie in diesem Arbeitsbereich die Registerkarte **Berichte** aus. Der neu importierte Bericht wird mit einem gelben Sternchen gekennzeichnet. Wählen Sie den Namen des Berichts aus, um ihn zu öffnen.
   
    ![](media/service-dashboard-create/power-bi-reports.png)
2. Der Bericht wird in der [Leseansicht](service-reading-view-and-editing-view.md) geöffnet. Beachten Sie die zwei Registerkarten am unteren Rand: „Discount Analysis“ und „Spend Overview“. Jede Registerkarte stellt eine Seite des Berichts dar.
   
    ![](media/service-dashboard-create/power-bi-reading-view.png)
3. Zeigen Sie auf eine Visualisierung, um die verfügbaren Optionen anzuzeigen. Um eine Visualisierung einem Dashboard hinzuzufügen, wählen Sie das Stecknadelsymbol ![](media/service-dashboard-create/power-bi-pin-icon.png) aus.
   
    ![](media/service-dashboard-create/power-bi-hover.png)
4. Da wir ein neues Dashboard erstellen, wählen Sie die Option **Neues Dashboard** aus, und geben Sie einen Namen ein. 
   
   ![](media/service-dashboard-create/power-bi-pin-tile.png)
5. Wenn Sie **Anheften** auswählen, erstellt Power BI das neue Dashboard im aktuellen Arbeitsbereich. Wenn die Meldung **An das Dashboard angeheftet** angezeigt wird, wählen Sie **Zum Dashboard wechseln** aus. Wenn Sie aufgefordert werden, den Bericht zu speichern, wählen Sie **Speichern** aus.
   
     ![](media/service-dashboard-create/power-bi-pin-success.png)
6. Power BI öffnet das neue Dashboard. Es enthält eine Kachel – die eben von uns angeheftete Visualisierung. 
   
   ![](media/service-dashboard-create/power-bi-pinned.png)
7. Um zum Bericht zurückzukehren, wählen Sie die Kachel aus. Heften Sie einige weitere Kacheln an das neue Dashboard an. Wenn das Fenster **An das Dashboard anheften** angezeigt wird, wählen Sie dieses Mal **Vorhandenes Dashboard** aus.  
   
   ![](media/service-dashboard-create/power-bi-existing-dashboard.png)

Glückwunsch, Sie haben Ihr erstes Dashboard erstellt! Da Sie jetzt über ein Dashboard verfügen, stehen Ihnen alle Möglichkeiten offen, die ein Dashboard bietet.  Wenn Sie unseren Empfehlungen folgen möchten, finden Sie unten verschiedene **Nächste Schritte**. Oder studieren Sie dieses Beispiel genauer.   

## <a name="next-steps"></a>Nächste Schritte
* [Ändern der Größe und Position von Kacheln](service-dashboard-edit-tile.md)
* [Alle wichtigen Informationen über Dashboardkacheln](service-dashboard-tiles.md)
* [Freigeben des Dashboards durch Erstellen einer App](service-create-distribute-apps.md)
* [Power BI – Grundkonzepte](service-basic-concepts.md)
* [Dashboards in Power BI](service-dashboards.md)
* [Tipps zum Gestalten überzeugender Power BI-Dashboards](service-dashboards-design-tips.md)

Weitere Fragen? [Wenden Sie sich an die Power BI-Community](http://community.powerbi.com/)

