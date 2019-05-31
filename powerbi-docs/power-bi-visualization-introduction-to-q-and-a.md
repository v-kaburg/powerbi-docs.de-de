---
title: Erstellen Sie eine Visualisierung mit Power BI Q & A
description: Erfahren Sie mehr zum Erstellen einer Visualisierung für Q & A in Power BI-Dienst mit dem Analysebeispiel für Einzelhandel
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 05/13/2019
ms.author: maggies
LocalizationGroup: Ask questions of your data
ms.openlocfilehash: 580b387f8c763b0457bd32a71bfbccd90d4040a3
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2019
ms.locfileid: "65625217"
---
# <a name="create-a-visual-with-power-bi-qa"></a>Erstellen Sie eine Visualisierung mit Power BI Q & A

Manchmal ist die schnellste Möglichkeit, um eine Antwort auf Basis Ihrer Daten zu erhalten, eine Frage in natürlicher Sprache zu stellen.  In diesem Artikel betrachten wir zwei verschiedenen Methoden zum Erstellen der gleichen Visualisierung kennen: Erstens Stellen einer Frage mit Q & A, und andererseits in einem Bericht erstellen. Wir verwenden Power BI-Dienst aus, um die Visualisierung in einem Bericht zu erstellen, aber der Prozess ist fast identisch mit Power BI Desktop.

![Power BI gefüllt-Diagramm](media/power-bi-visualization-introduction-to-q-and-a/power-bi-qna-create-visual.png)

Zum Durchführen der Schritte müssen Sie einen Bericht verwenden, den Sie bearbeiten können. Deshalb verwenden wir eines der für Power BI verfügbaren Beispiele.

## <a name="create-a-visual-with-qa"></a>Erstellen Sie eine Visualisierung für Q & A

Wie gehen wir zum Erstellen dieses Liniendiagramm mit Q & A?

1. Wählen Sie in dem Power BI-Arbeitsbereich **Daten abrufen** \> **Besipiele** \> **Analysebeispiel für den Einzelhandel**  >  **Verbinden** aus.

1. Öffnen Sie das Analysebeispiel für Einzelhandel-Dashboard, und platzieren Sie den Cursor in das Q & A-Feld, **stellen Sie eine Frage zu Ihren Daten**.

    ![Platzieren Sie den Cursor in das Q & A-Feld](media/power-bi-visualization-introduction-to-q-and-a/power-bi-qna-cursor-in-qna-box.png)

2. Geben Sie in das Q & A-Feld etwa diese Frage aus:
   
    **Verkäufe in diesem Jahr und Umsatz letztes Jahr nach Monat als Flächendiagramm**
   
    Wenn Sie eine Frage eingeben, wählt Q&A die optimale Visualisierung, um Ihre Antwort anzuzeigen. Wenn Sie die Frage ändern, wird die Visualisierung dynamisch angepasst. Darüber hinaus hilft Ihnen Q&A dabei, Ihre Frage mit Vorschlägen, automatischer Vervollständigung und Rechtschreibkorrekturen zu formatieren. F & A empfiehlt eine Änderung der kleinen Wortlaut: "Verkäufe in diesem Jahr und Verkäufe im letzten Jahr nach *Zeit Monat* als Flächendiagramm".  

    ![F & A korrigiert Wortlaut](media/power-bi-visualization-introduction-to-q-and-a/power-bi-qna-corrected-create-filled-chart.png)

4. Wählen Sie den Satz den Vorschlag akzeptieren. 
   
   Wenn Sie fertig sind, geben Sie Ihre Frage, ist das Ergebnis das gleiche Diagramm, das Sie im Dashboard angezeigt werden.
   
   ![F & A gefüllt Flächendiagramm](media/power-bi-visualization-introduction-to-q-and-a/power-bi-qna-create-filled-chart.png)

4. Um das Diagramm an Ihr Dashboard anzuheften, wählen Sie das Anheftsymbol. ![Stecknadelsymbol](media/power-bi-visualization-introduction-to-q-and-a/pinnooutline.png) in der rechten oberen Ecke.

## <a name="create-a-visual-in-the-report-editor"></a>Erstellen eines Visuals im Berichts-Editor

1. Navigieren Sie zurück zum Dashboard des Analysebeispiels für den Einzelhandel.
   
2. Das Dashboard enthält die gleiche Kachel mit Flächendiagramm für "Verkäufe im Vorjahr und Verkäufe in diesem Jahr".  Wählen Sie die Kachel. Wählen Sie nicht mit Q & a erstellten Kachel Q & a geöffnet auswählen Die ursprüngliche Kachel mit Flächendiagramm wurde in einem Bericht erstellt, damit der Bericht auf der Seite wird geöffnet, die die Visualisierung enthält.

    ![Retail Analysis Sample-Dashboard](media/power-bi-visualization-introduction-to-q-and-a/power-bi-dashboard.png)

1. Öffnen Sie den Bericht in der Bearbeitungsansicht, indem Sie **Bericht bearbeiten**auswählen.  Wenn Sie nicht der Besitzer eines Berichts sind, steht Ihnen die Option zum Öffnen des Berichts in der Bearbeitungsansicht nicht zur Verfügung.
   
    ![Schaltfläche „ Bericht bearbeiten“](media/power-bi-visualization-introduction-to-q-and-a/power-bi-edit-report.png)
4. Wählen Sie das Flächendiagramm und überprüfen Sie die Einstellungen im Bereich **Felder** .  Der Berichtersteller hat dieses Diagramm durch Auswahl dieser drei Werte erstellt (**Verkäufe im letzten Jahr** und **Verkäufe in diesem Jahr > Wert** aus der **Sales** Tabelle und  **Geschäftsmonat** aus der **Zeit** Tabelle) und durch Anordnen dieser in der **Achse** und **Werte** Wells.
   
    ![Bereich „Visualisierungen“](media/power-bi-visualization-introduction-to-q-and-a/gnatutorial_3-new.png)

    Sie sehen, dass sie dasselbe visuelle geführt hat. Erstellen sie auf diese Weise nicht zu kompliziert. Aber mit Q & A Erstellen einfacher wurde.

## <a name="next-steps"></a>Nächste Schritte

- [Verwenden von Q & A in Dashboards und Berichten](power-bi-tutorial-q-and-a.md)  
- [Q & A für Consumer](consumer/end-user-q-and-a.md)
- [Optimieren Ihrer Daten für Q&A in Power BI](service-prepare-data-for-q-and-a.md)

Weitere Fragen? [Wenden Sie sich an die Power BI-Community](http://community.powerbi.com/)

