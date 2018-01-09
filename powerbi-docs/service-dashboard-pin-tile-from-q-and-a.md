---
title: Anheften einer Kachel an ein Dashboard aus Q&A
description: "Dokumentation zum Anheften einer Kachel an ein Power BI-Dashboard aus dem Fragefeld für Fragen und Antworten (F&A)"
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
ms.date: 12/20/2017
ms.author: mihart
ms.openlocfilehash: 8a876c5a05fcdadff1a874148f5d56465bcc8c62
ms.sourcegitcommit: 6ea8291cbfcb7847a8d7bc4e2b6abce7eddcd0ea
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="pin-a-tile-to-a-dashboard-from-qa"></a>Anheften einer Kachel an ein Dashboard aus Q&A
## <a name="how-to-pin-a-tile-from-qa"></a>Anheften einer Kachel aus Q&A
F&A ist das Power BI-Tool zur Ad-hoc-Berichterstellung. Sie möchten bestimmte Erkenntnisse gewinnen? Stellen Sie eine Frage zu den Daten und erhalten Sie eine Antwort in Form einer Visualisierung.

Q&A steht in Dashboards und Berichten zur Verfügung. In diesem Artikel wird Q&A über ein Dashboard geöffnet. Dashboards stehen im Power BI-Dienst, aber nicht in Power BI Desktop zur Verfügung. Um die Schritte selbst nachzuvollziehen, öffnen Sie das [Dashboard zum Analysebeispiel für Einzelhandel](sample-retail-analysis.md).
> 
> 

1. Öffnen Sie ein [Dashboard](service-dashboards.md), an das mindestens eine Kachel aus einem Bericht angeheftet wurde. Wenn Sie eine Frage stellen, sucht Power BI in jedem Dataset nach der Antwort, in dem an dieses Dashboard eine Kachel angeheftet ist.  Weitere Informationen finden Sie unter [Abrufen von Daten](service-get-data.md).
2. Geben Sie oben auf Ihrem Dashboard im Fragefeld ein, was Sie über Ihre Daten wissen möchten.  
   ![](media/service-dashboard-pin-tile-from-q-and-a/power-bi-question-box.png)
3. Während Sie beispielsweise „Umsatz letztes Jahr nach Monat und Gebiet“ eingeben ...  
   ![](media/service-dashboard-pin-tile-from-q-and-a/power-bi-type-q-and-a.png)
   
   werden im Fragefeld Vorschläge angezeigt.
4. Um das Diagramm als Kachel zu Ihrem Dashboard hinzuzufügen, wählen Sie das Anheftsymbol ![](media/service-dashboard-pin-tile-from-q-and-a/pbi_pintile.png) oben rechts im Zeichenbereich.
5. Heften Sie die Kachel an ein vorhandenes oder neues Dashboard an. 

   ![](media/service-dashboard-pin-tile-from-q-and-a/power-bi-pin-to-dashboard.png)

   * Vorhandenes Dashboard: Wählen Sie den Namen des Dashboards aus der Dropdownliste aus. Sie können nur die Dashboards innerhalb des aktuellen Arbeitsbereichs auswählen.
   * Neues Dashboard: Geben Sie den Namen des neuen Dashboards ein. Dieses wird anschließend dem aktuellen Arbeitsbereich hinzugefügt.
6. Wählen Sie **Anheften**aus.
   
   Eine Erfolgsmeldung (in der Nähe der oberen rechten Ecke) weist darauf hin, dass die Visualisierung als Kachel zu Ihrem Dashboard hinzugefügt wurde.  
   
   ![](media/service-dashboard-pin-tile-from-q-and-a/power-bi-pin.png)
7. Wählen Sie **Zum Dashboard wechseln**, um die neue Kachel anzuzeigen. Dort können Sie es u.a. [umbenennen, die Größe ändern, einen Link hinzufügen und die Kachel auf dem Dashboard verschieben](service-dashboard-edit-tile.md). 
   
   ![](media/service-dashboard-pin-tile-from-q-and-a/power-bi-pinned.png)

## <a name="considerations-and-troubleshooting"></a>Zu beachtende Aspekte und Problembehandlung
* Wenn Sie anfangen, eine Frage einzugeben, sucht F&A sofort nach der besten Antwort aus allen Datasets, die mit dem aktuellen Dashboard verknüpft sind.  Das „aktuelle Dashboard“ ist das Dashboard, das in der oberen Navigationsleiste aufgeführt wird. Diese Frage wird beispielsweise im Dashboard **Analysebeispiel für den Einzelhandel** gestellt, das Teil des App-Arbeitsbereichs **mihart** ist.
  
  ![](media/service-dashboard-pin-tile-from-q-and-a/power-bi-navbar.png)
* **Woher weiß F&A, welche Datasets verwendet werden sollen**?  F&A hat Zugriff auf alle Datasets, die über an das Dashboard angeheftete Visualisierungen verfügen.

## <a name="next-steps"></a>Nächste Schritte
[Umbenennen, Ändern der Größe und Position, Hinzufügen eines Hyperlinks und mehr](service-dashboard-edit-tile.md)    
[Anzeigen einer Dashboardkachel im Fokusmodus](service-focus-mode.md)     
[Zurück zu Q&A in Power BI](service-q-and-a.md)  
Weitere Fragen? [Wenden Sie sich an die Power BI-Community](http://community.powerbi.com/)

