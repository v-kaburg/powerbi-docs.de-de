---
title: 'Analysebeispiel für Einzelhandel für Power BI: Übersicht'
description: 'Analysebeispiel für Einzelhandel für Power BI: Übersicht'
author: maggiesMSFT
manager: kfile
ms.reviewer: amac
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 06/24/2018
ms.author: maggies
LocalizationGroup: Samples
ms.openlocfilehash: 04676ee789b90eb09cbed3bafb623e8e9b89e4e4
ms.sourcegitcommit: 762857c8ca09ce222cc3f8b006fa1b65d11e4ace
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/05/2019
ms.locfileid: "66720878"
---
# <a name="retail-analysis-sample-for-power-bi-take-a-tour"></a>Analysebeispiel für Einzelhandel für Power BI: Übersicht

Dieses Branchenbeispieldashboard und der zugrunde liegende Bericht analysieren Umsatzdaten des Einzelhandels von Artikeln, die in verschiedenen Läden und Bezirken verkauft wurden. Die Metriken vergleichen die Leistung dieses Jahres mit der des letzten Jahres in den folgenden Bereichen: Umsatz, Einheiten, Bruttogewinn und Varianz sowie Analyse neuer Läden. Hierbei handelt es sich um echte Daten von obviEnce ([www.obvience.com](http://www.obvience.com)) in anonymisierter Form.

![](media/sample-retail-analysis/retail1.png)

## <a name="prerequisites"></a>Voraussetzungen

 Bevor Sie das Beispiel verwenden können, müssen Sie es zunächst als [Inhaltspaket](https://docs.microsoft.com/power-bi/sample-datasets#get-and-open-a-sample-content-pack-in-power-bi-service), [PBIX-Datei](http://download.microsoft.com/download/9/6/D/96DDC2FF-2568-491D-AAFA-AFDD6F763AE3/Retail%20Analysis%20Sample%20PBIX.pbix) oder [Excel-Arbeitsmappe](http://go.microsoft.com/fwlink/?LinkId=529778) herunterladen.


### <a name="get-the-content-pack-for-this-sample"></a>Abrufen des Inhaltspakets für dieses Beispiel

1. Öffnen Sie den Power BI-Dienst (app.powerbi.com), und melden Sie sich an.
2. Wählen Sie in der linken unteren Ecke **Daten abrufen** aus.
   
    ![](media/sample-datasets/power-bi-get-data.png)
3. Wählen Sie auf der daraufhin angezeigten Seite „Daten abrufen“ das Symbol **Beispiele** aus.
   
   ![](media/sample-datasets/power-bi-samples-icon.png)
4. Wählen Sie das **Analysebeispiel für Einzelhandel** aus, und wählen Sie dann **Verbinden**.  
  
   ![Retail Analysis Sample](media/sample-retail-analysis/retail16.png)
   
5. Das Inhaltspaket wird in Power BI importiert, und dem aktuellen Arbeitsbereich werden ein neues Dashboard, ein neuer Bericht und ein neues Dataset hinzugefügt. Die neuen Inhalte sind mit einem gelben Sternchen markiert. 
   
   ![Retail Analysis Sample](media/sample-retail-analysis/retail17.png)
  
### <a name="get-the-pbix-file-for-this-sample"></a>Abrufen der PBIX-Datei für dieses Beispiel

Alternativ können Sie das Beispiel als PBIX-Datei herunterladen, ein für Power BI Desktop entworfenes Dateiformat. 

 * [Analysebeispiel für den Einzelhandel](http://download.microsoft.com/download/9/6/D/96DDC2FF-2568-491D-AAFA-AFDD6F763AE3/Retail%20Analysis%20Sample%20PBIX.pbix)

### <a name="get-the-excel-workbook-for-this-sample"></a>Abrufen der Excel-Arbeitsmappe für dieses Beispiel
Alternativ können Sie [nur das Dataset (Excel-Arbeitsmappe) für dieses Beispiel herunterladen](http://go.microsoft.com/fwlink/?LinkId=529778). Die Arbeitsmappe enthält Power View-Blätter, die Sie anzeigen und ändern können. Wenn Sie die Rohdaten anzeigen möchten, wählen Sie **Power Pivot > Verwalten** aus.

## <a name="start-on-the-dashboard-and-open-the-report"></a>Starten auf dem Dashboard und Öffnen des Berichts
1. Wählen Sie im Dashboard die Kachel „Total Stores“ aus:

   ![](media/sample-retail-analysis/retail-analysis-7.png)  

   Dadurch gelangen Sie im Bericht zur Seite „Store Sales Overview“ im Bericht. Sie sehen, wir haben insgesamt 104 Geschäfte, davon 10 neue. Wir haben zwei Ketten Fashions Direct und Lindseys. Die Fashions Direct-Geschäfte sind im Durchschnitt größer.
2. Wählen Sie im Kreisdiagramm **Fashions Direct** aus.

   ![](media/sample-retail-analysis/retail3.png)  

   Beachten Sie das Ergebnis im Blasendiagramm:

   ![](media/sample-retail-analysis/pbi_sample_retanlbubbles.png)  

   Der Bezirk FD-01 hat den höchsten durchschnittlichen Umsatz pro Quadratfuß, FD-02 hat die niedrigste Abweichung im Vergleich zum Vorjahr, FD-03 und FD-04 schneiden insgesamt am schlechtesten ab.
3. Wählen Sie einige der einzelnen Blasen oder andere Diagramme, um die übergreifende Hervorhebung den Einfluss Ihrer Auswahl sichtbar machen zu lassen.
4. Um zum Dashboard zurückzukehren, wählen Sie dessen Namen aus der oberen Navigationsleiste aus (Brotkrümel).

   ![](media/sample-retail-analysis/power-bi-breadcrumbs.png)
5. Wählen Sie im Dashboard die Kachel mit dem Titel „This Year’s Sales“ aus.

   ![](media/sample-retail-analysis/pbi_sample_retanlthisyrsales.png)

   Das ist gleichbedeutend mit der Eingabe von „Verkäufe in diesem Jahr“ im Q&A-Feld.

   Dieser Bildschirm wird angezeigt:

   ![](media/sample-retail-analysis/retail7.png)

## <a name="review-a-tile-created-with-power-bi-qa"></a>Überprüfen einer Kachel, die über Fragen und Antworten in Power BI erstellt wurde
Gehen wir mehr ins Detail.

1. Fügen Sie „this year sales **by district**“ zur Frage hinzu. Beobachten Sie das Ergebnis: Die Antwort wird automatisch in ein Balkendiagramm gesetzt, und es werden andere Formulierungen vorgeschlagen:

   ![](media/sample-retail-analysis/retail8.png)
2. Ändern Sie jetzt die Frage in „this year sales **by zip and chain**“.

   Beachten Sie, wie die Frage während Ihrer Eingabe mit den entsprechenden Diagrammen beantwortet wird.
3. Experimentieren Sie ein bisschen mit weiteren Fragen, und sehen Sie sich die erzielten Ergebnisse an.
4. Wenn Sie soweit sind, kehren Sie zum Dashboard zurück.

## <a name="dive-deeper-into-the-data"></a>Eingehendere Untersuchung der Daten
Führen wir unsere Untersuchung auf einer Ebene mit mehr Details fort, indem wir die Leistung der einzelnen Regionen ansehen.

1. Wählen Sie auf dem Dashboard die Kachel aus, auf der die Umsätze dieses Jahres mit denen des letzten verglichen werden.

   ![](media/sample-retail-analysis/pbi_sample_retanlareacht.png)

   Beachten Sie die große Variabilität in „Variance %“ gegenüber dem Vorjahr, mit Jan, Apr und Jul als besonders schlechten Monaten.

   ![](media/sample-retail-analysis/pbi_sample_retanlsalesvarcol.png)

   Sehen wir uns einmal an, ob wir die Probleme eingrenzen können.
2. Wählen Sie das Blasendiagramm und dann **020-Herren**aus.

   ![](media/sample-retail-analysis/retail11.png)  

   Beobachten Sie, dass die Herrenkategorie im April nicht so stark betroffen war wie das Geschäft insgesamt, wobei Januar und Juli dennoch problematische Monate waren.
3. Wählen Sie jetzt die Blase **010-Damen**aus.

   ![](media/sample-retail-analysis/retail12.png)

   Beachten Sie, dass die Frauenkategorie viel schlechter abgeschnitten hat als das Unternehmen insgesamt in allen Monaten und außerdem fast jeden Monat viel schlechter im Vergleich zum Vorjahr.
4. Wählen Sie die Blase erneut aus, um den Filter zu löschen.

## <a name="try-out-the-slicer"></a>Testen des Datenschnitts
Betrachten wir, wie sich einzelne Regionen entwickelt haben.

1. Wählen Sie im Datenschnitt oben links „Allan Guinot“ aus.

   ![](media/sample-retail-analysis/retail13.png)

   Beachten Sie, dass Allans Region letztes Jahr in März und Juni outperformt hat.
2. Wählen Sie nun die Blase für die Damen aus, während Allan weiterhin ausgewählt ist.

   ![](media/sample-retail-analysis/power-bi-allan.png)

   Beachten Sie, dass sein Bezirk in der Frauenkategorie in keinem Fall das Umsatzvolumen des Vorjahres erreichte.
3. Untersuchen  Sie die anderen Regionalmanager und Kategorien – welche Einsichten können Sie außerdem noch gewinnen?
4. Wenn Sie soweit sind – kehren Sie zum Dashboard zurück.

## <a name="what-is-our-data-telling-us-about-sales-growth-this-year"></a>Was sagen unsere Daten zur Umsatzsteigerung in diesem Jahr aus?
Der letzte Bereich, den wir untersuchen möchten, ist unser Wachstum – wir haben in diesem Jahr neue Geschäfte eröffnet.

1. Wählen Sie die Kachel „Stores Opened This Year“.

   ![](media/sample-retail-analysis/retail15.png)

   Wie auf der Kachel deutlich zu sehen – dieses Jahr wurden mehr Fashions Direct-Geschäfte als Lindseys-Geschäfte eröffnet.
2. Betrachten Sie das Diagramm „Sales Per Sq Ft by Name“:

   ![](media/sample-retail-analysis/retail14.png)

    Es gibt einen deutlichen Unterschied bei „Average Sales per SQF“ über die Gesamtheit der neuen Geschäfte.
3. Klicken Sie auf das Legendenelement „Fashions Direct“ im oberen rechten Diagramm. Beachten Sie, dass auch innerhalb der gleichen Kette das stärkste Geschäft (Winchester Fashions Direct) das schwächste Geschäft (Cincinnati 2 Fashions Direct) mit 21,22 $ gegen 12,86 $ deutlich schlägt.

   ![](media/sample-retail-analysis/power-bi-lindseys.png)
4. Klicken Sie im Datenschnitt auf „Winchester Fashions Direct“, und beobachten Sie das Liniendiagramm. Die ersten Umsatzzahlen wurden im Februar gemeldet.
5. Klicken Sie im Datenschnitt auf „Cincinnati 2 Fashions Direct“, daraufhin sehen Sie im Liniendiagramm, dass das Geschäft im Juni eröffnet wurde und die schlechteste Leistung aller Geschäfte zu bringen scheint.
6. Untersuchen Sie wie zuvor durch Klicken auf andere Balken, Linien und Blasen quer durch alle Diagramme, welche Einblicke Sie gewinnen können.

Dies ist eine Umgebung, in der Sie sicher experimentieren können. Sie können sich immer noch entscheiden, Ihre Änderungen nicht zu speichern. Wenn Sie sie aber speichern, können Sie immer wieder zu „Daten abrufen“ zurückkehren, um ein neues Exemplar dieses Beispiels herunterzuladen.

## <a name="connect-to-your-data"></a>Herstellen einer Verbindung mit den Daten
Wir hoffen, diese Tour hat Ihnen gezeigt, wie Power BI-Dashboards, das Fragen- und Antwortenmodul und Berichte Ihnen Einblicke in Daten zum Einzelhandel geben können. Es ist jetzt an Ihnen – stellen Sie Verbindungen mit Ihren eigenen Daten her. Mit Power BI können Sie Verbindungen zu einer Vielzahl von Datenquellen herstellen. Weitere Informationen zum [Einstieg in Power BI](service-get-started.md).

## <a name="next-steps"></a>Nächste Schritte
* [Herunterladen des Beispielinhaltspakets für die Einzelhandelsanalyse](sample-tutorial-connect-to-the-samples.md)
* [Herunterladen einer ZIP-Datei aller Beispieldateien](http://go.microsoft.com/fwlink/?LinkId=535020)    
* [Herunterladen der Excel-Arbeitsmappe für dieses Power BI-Beispiel](http://go.microsoft.com/fwlink/?LinkId=529778)    
* [Abrufen von Daten (für Power BI)](service-get-data.md)    
* [Grundlegende Konzepte für Designer im Power BI-Dienst](service-basic-concepts.md)    
* Weitere Fragen? [Wenden Sie sich an die Power BI-Community](http://community.powerbi.com/)
