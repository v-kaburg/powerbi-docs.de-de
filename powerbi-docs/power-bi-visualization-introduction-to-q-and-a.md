---
title: Erste Schritte mit Power BI Q&A (Tutorial)
description: "Tutorial: Erste Schritte mit Q&A im Power BI-Dienst mit dem Analysebeispiel für den Einzelhandel"
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: 
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 09/25/2017
ms.author: mihart
ms.openlocfilehash: 2038fb5bd4a21235c3026c8506ae30b8c3e287e4
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2017
---
# <a name="get-started-with-power-bi-qa-tutorial"></a>Erste Schritte mit Power BI Q&A (Tutorial)
## <a name="tutorial-use-power-bi-qa-with-the-retail-analysis-sample"></a>Tutorial: Verwenden von Power BI Q&A mit dem Analysebeispiel für den Einzelhandel
Manchmal ist die schnellste Möglichkeit, um eine Antwort auf Basis Ihrer Daten zu erhalten, eine Frage in natürlicher Sprache zu stellen.  In diesem Lernprogramm lernen wir zwei verschiedenen Methoden zum Erstellen der gleichen Visualisierung kennen: in einem Bericht und mithilfe einer Frage mit Fragen & Antworten (F&A).  

## <a name="method-1-using-the-report-editor"></a>Methode 1: Mithilfe des Berichts-Editors
1. Wählen Sie in dem Power BI-Arbeitsbereich **Daten abrufen** \> **Besipiele** \> **Analysebeispiel für den Einzelhandel**  >  **Verbinden** aus.
   
    ![](media/power-bi-visualization-introduction-to-q-and-a/power-bi-dashboard.png)
2. Das Dashboard enthält eine Kachel mit Flächendiagramm für „Verkäufe im Vorjahr und Verkäufe im laufenden Jahr“.  Wählen Sie die Kachel. 
   
   * Wenn diese Kachel mit F&A erstellt wurde, wird die Kachel durch Auswählen von F&A geöffnet. 
   * Diese Kachel wurde jedoch in einem Bericht erstellt, sodass der Bericht die Seite öffnet, die die Visualisierung enthält.
3. Öffnen Sie den Bericht in der Bearbeitungsansicht, indem Sie **Bericht bearbeiten**auswählen.  Wenn Sie nicht der Besitzer eines Berichts sind, steht Ihnen die Option zum Öffnen des Berichts in der Bearbeitungsansicht nicht zur Verfügung.
   
    ![](media/power-bi-visualization-introduction-to-q-and-a/power-bi-edit-report.png)
4. Wählen Sie das Flächendiagramm und überprüfen Sie die Einstellungen im Bereich **Felder** .  Der Berichtersteller hat dieses Diagramm durch Auswahl dieser drei Werte (**Time > FiscalMonth**, **Sales > This Year Sales**, **Sales > Last Year Sales > Wert**) und durch Anordnen dieser Werte in den Bereichen **Achse** und **Werte** erstellt.
   
    ![](media/power-bi-visualization-introduction-to-q-and-a/gnatutorial_3-new.png)

## <a name="method-2-using-qa"></a>Methode 2: Mithilfe von Fragen und Antworten
Wie gehen wir beim Erstellen des gleichen Liniendiagramms mithilfe von F&A vor?

![](media/power-bi-visualization-introduction-to-q-and-a/power-bi-qna.png)

1. Navigieren Sie zurück zum Dashboard des Analysebeispiels für den Einzelhandel.
2. Geben Sie in natürlicher Sprache etwa Folgendes in das Fragefeld ein:
   
   **Wie sieht der Umsatz in diesem und im letzten Jahr nach Monat als Flächendiagramm aus?**
   
   Wenn Sie eine Frage eingeben, wählt Q&A die optimale Visualisierung, um Ihre Antwort anzuzeigen. Wenn Sie die Frage ändern, wird die Visualisierung dynamisch angepasst. Darüber hinaus hilft Ihnen F&A dabei, Ihre Frage mit Vorschlägen, automatischer Vervollständigung und Rechtschreibkorrekturen zu formatieren.
   
   Wenn Sie Ihre Frage eingegeben haben, ist das Ergebnis genau dasselbe Diagramm, das wir im Bericht gesehen haben.  Auf diese Weise funktioniert die Erstellung aber viel schneller!
   
   ![](media/power-bi-visualization-introduction-to-q-and-a/powerbi-qna-areachart.png)
3. In Q&A haben Sie, wie bei der Arbeit mit Berichten auch, Zugriff auf die Bereiche „Visualisierungen“, „Filter“ und „Felder“.  Öffnen Sie diese Bereiche, um Ihre Visualisierung weiter zu verbessern und zu ändern.
4. Um das Diagramm an Ihr Dashboard anzuheften, wählen Sie das Anheftsymbol ![](media/power-bi-visualization-introduction-to-q-and-a/pinnooutline.png).

## <a name="next-steps"></a>Nächste Schritte
[Welche Art von Fragen kann ich Q&A stellen?](service-q-and-a.md)

[Q&A in Power BI](service-q-and-a.md)

[Optimieren Ihrer Daten für Q&A in Power BI](service-prepare-data-for-q-and-a.md)

[Vorbereiten einer Arbeitsmappe für Q&A](service-prepare-data-for-q-and-a.md)

Weitere Fragen? [Wenden Sie sich an die Power BI-Community](http://community.powerbi.com/)

