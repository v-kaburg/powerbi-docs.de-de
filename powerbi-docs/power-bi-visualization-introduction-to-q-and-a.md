---
title: Erste Schritte mit Power BI – Q&A
description: Erste Schritte mit Q&A im Power BI-Dienst mit dem Analysebeispiel für den Einzelhandel
author: mihart
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 01/16/2018
ms.author: mihart
LocalizationGroup: Ask questions of your data
ms.openlocfilehash: c567921b765f03fbaa11f2b98724cea1a1ce1905
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2018
ms.locfileid: "34240983"
---
# <a name="get-started-with-power-bi-qa"></a>Erste Schritte mit Power BI – Q&A
## <a name="use-power-bi-qa-with-the-retail-analysis-sample"></a>Verwenden von Power BI Q&A mit dem Analysebeispiel für den Einzelhandel
Manchmal ist die schnellste Möglichkeit, um eine Antwort auf Basis Ihrer Daten zu erhalten, eine Frage in natürlicher Sprache zu stellen.  In diesem Schnellstart lernen wir zwei verschiedenen Methoden zum Erstellen der gleichen Visualisierung kennen: in einem Bericht und mithilfe einer Frage mit Q&A. Wir verwenden den Power BI-Dienst, der Vorgang ist jedoch mit Power BI Desktop fast der gleiche.

Zum Durchführen der Schritte müssen Sie einen Bericht verwenden, den Sie bearbeiten können. Deshalb verwenden wir eines der für Power BI verfügbaren Beispiele.

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
[Q&A in Power BI](power-bi-q-and-a.md)

[Optimieren Ihrer Daten für Q&A in Power BI](service-prepare-data-for-q-and-a.md)

Weitere Fragen? [Wenden Sie sich an die Power BI-Community](http://community.powerbi.com/)

