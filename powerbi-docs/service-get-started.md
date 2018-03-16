---
title: Erste Schritte mit dem Power BI-Dienst
description: Erste Schritte mit dem Power BI-Dienst
services: powerbi
documentationcenter: 
author: adamw
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: B2vd4MQrz4M
qualityfocus: monitoring
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: get-started-article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 03/01/2018
ms.author: mihart
LocalizationGroup: Get started
ms.openlocfilehash: cbb7697e3d3dbc92c2917b0a80deadfc0b9fd5a0
ms.sourcegitcommit: 85d18d9f11a4ce4d4ed65e4544d13da6c2d9b1d4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2018
---
# <a name="get-started-with-power-bi-service-apppowerbicom"></a>Erste Schritte mit dem Power BI-Dienst (app.powerbi.com)
Dieses Lernprogramm erleichtert Ihnen den Einstieg in den ***Power BI-Dienst***. Damit Sie die Funktion des Power BI-Diensts im Hinblick auf die anderen Power BI-Angebote einordnen können, sollten Sie zunächst [Was ist Power BI?](guided-learning/gettingstarted.yml#step-1) lesen.

![Abbildung der Beziehungen zwischen Desktop, Dienst und Mobil](media/service-get-started/power-bi-components.png)

Der Power BI-Dienst wird in einer kostenlosen Version und einer Pro-Version angeboten. Unabhängig davon, welche Version Sie verwenden, öffnen Sie einen Browser und geben zunächst die Adresse „www.powerbi.com“ ein, um den Power BI-Dienst aufzurufen, *sofern Sie bereits ein Konto besitzen*. Als neuer Benutzer sollten Sie stattdessen unter www.powerbi.com beginnen. Hier erfahren Sie mehr über Power BI, bevor Sie sich beim Dienst anmelden.  Sobald Sie es selbst ausprobieren möchten, klicken Sie rechts oben auf den Link **Kostenlos registrieren**. Wenn Ihr Administrator Power BI bereits für Sie aktiviert hat, verwenden Sie nicht die Schaltfläche „Kostenlos registrieren“, sondern wechseln Sie direkt zu „app.powerbi.com“. 

![Anmelden oder kostenloses Registrieren](media/service-get-started/power-bi-sign-up.png)

Hilfe zu Power BI Desktop finden Sie unter [Erste Schritte mit Desktop](desktop-getting-started.md). Hilfe zu Power BI-Version für Mobilgeräte finden Sie unter [Microsoft Power BI – Mobilgeräte](mobile-apps-for-mobile-devices.md).

> [!TIP]
> Sie möchten Ihre Trainingsgeschwindigkeit lieber selbst bestimmen? [Registrieren Sie sich auf EdX für unseren Kurs zur Datenanalyse und -visualisierung.](http://aka.ms/edxpbi)

Besuchen Sie unsere [Wiedergabeliste auf YouTube](https://www.youtube.com/playlist?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP). Ein anschauliches Video zum Einstieg ist „Introduction in Power BI service“ (in englischer Sprache):
> 
> <iframe width="560" height="315" src="https://www.youtube.com/embed/B2vd4MQrz4M" frameborder="0" allowfullscreen></iframe>
> 
> 
> 

Microsoft Power BI hilft Ihnen, hinsichtlich der für Sie wichtigen Informationen auf dem neuesten Stand zu bleiben.  Beim Power BI-Dienst sorgen Sie mit ***Dashboards*** dafür, dass Sie nie den Überblick über Ihr Unternehmen verlieren.  In Ihren Dashboards werden ***Kacheln*** angezeigt, auf die Sie klicken können, um weitere Informationen in Form von ***Berichten*** zu erhalten.  Stellen Sie Verbindungen mit mehreren ***Datasets*** her, um sämtliche relevanten Daten an einem Ort zusammenzuführen. Benötigen Sie Hilfe, um die Grundkomponenten zu verstehen, aus denen Power BI besteht?  Weitere Informationen finden Sie unter [Power BI – Grundkonzepte](service-basic-concepts.md).

Wenn Sie über wichtige Daten in Excel- oder CSV-Dateien verfügen, können Sie ein Power BI-Dashboard erstellen, um jederzeit informiert zu sein und Erkenntnisse mit anderen zu teilen.  Verfügen Sie über ein Abonnement für eine SaaS-Anwendung wie Salesforce?  Verschaffen Sie sich einen Vorsprung, indem Sie eine Verbindung mit Salesforce herstellen, um aus diesen Daten automatisch ein Dashboard zu erstellen, oder [sehen Sie sich die anderen SaaS-Anwendungen an](service-get-data.md), mit denen Sie eine Verbindung herstellen können. Wenn Sie einer Organisation angehören, überprüfen Sie, ob für Sie [Apps](service-create-distribute-apps.md) veröffentlicht wurden.

Informieren Sie sich über alle anderen Möglichkeiten zum [Abrufen von Daten für Power BI](service-get-data.md).

## <a name="step-1-get-data"></a>Schritt 1: Abrufen von Daten
Hier folgt ein Beispiel zum Abrufen von Daten aus einer CSV-Datei. Möchten Sie dieses Tutorial durchführen? [Laden Sie diese CSV-Beispieldatei herunter](http://go.microsoft.com/fwlink/?LinkID=521962).

1. [Melden Sie sich bei Power BI an](http://www.powerbi.com/). Verfügen Sie über ein Konto? Keine Sorge: Die Registrierung ist kostenlos.
2. Power BI wird in Ihrem Browser geöffnet. Wählen Sie unten auf der linken Navigationsleiste **Daten abrufen** aus.
   
   ![Daten abrufen](media/service-get-started/getdata3.png)
3. Wählen Sie **Dateien**aus. 
   
   ![Dateien abrufen](media/service-get-started/gs1.png)
4. Navigieren Sie zu der Datei auf Ihrem Computer, und wählen Sie dann **Öffnen** aus. Wenn Sie sie in OneDrive for Business gespeichert haben, wählen Sie diese Option aus. Wenn sie lokal gespeichert ist, wählen Sie **Lokale Datei** aus. 
   
   ![Ansicht „Dateien abrufen > Dateien“](media/service-get-started/gs2.png)
5. Für dieses Lernprogramm wählen wir **Importieren** aus, um die Excel-Datei als Dataset hinzuzufügen, mit dem dann Berichte und Dashboards erstellt werden können. Wenn Sie **Hochladen** auswählen, wird die gesamte Excel-Arbeitsmappe in Power BI hochgeladen, sodass Sie sie öffnen und online in Excel bearbeiten können.
   
   ![„Importieren“ auswählen](media/service-get-started/power-bi-import.png)
6. Wenn Ihr Dataset bereit ist, wählen Sie **Dataset anzeigen** aus, um es im Berichts-Editor zu öffnen. 

    ![Dialogfeld „Ihr Dataset ist bereit“](media/service-get-started/power-bi-gs.png)

    Da wir noch keine Visualisierungen erstellt haben, ist der Zeichenbereich des Berichts leer.

    ![Leerer Berichtszeichenbereich](media/service-get-started/power-bi-report-editor.png)

6. Auf der oberen Menüleiste sehen Sie die Option **Leseansicht**. Da die Option „Leseansicht“ angezeigt wird, müssen Sie sich derzeit in der **Bearbeitungsansicht** befinden. 

    ![Option „Leseansicht“](media/service-get-started/power-bi-editing-view.png)

    In der Bearbeitungsansicht können Sie eigene Berichte erstellen und ändern, da Sie der *Besitzer* des Berichts sind, das heißt, Sie sind *Ersteller*. Wenn Sie den Bericht für Mitarbeiter freigeben, können diese den Bericht nur in der Leseansicht verwenden, das heißt, sie sind *Anwender*. Weitere Informationen über [Leseansicht und Bearbeitungsansicht](service-reading-view-and-editing-view.md).
    
    Ein [Überblick](service-the-report-editor-take-a-tour.md) stellt eine hervorragende Möglichkeit dar, sich mit dem Berichts-Editor vertraut zu machen.
   > 
 

## <a name="step-2-start-exploring-your-dataset"></a>Schritt 2: Untersuchen des Datasets
Nachdem die Verbindung mit den Daten hergestellt wurde, können Sie die Daten untersuchen.  Wenn Sie etwas gefunden haben, das für Sie von Interesse ist, können Sie ein Dashboard erstellen, um die Daten zu überwachen und Änderungen zu verfolgen. Sehen wir uns das einmal an.
    
1. Im Berichts-Editor verwenden Sie den Bereich **Felder** rechts auf der Seite, um eine Visualisierung zu erstellen.  Aktivieren Sie die Kontrollkästchen neben **Bruttoumsätze** und **Datum**.
   
   ![Liste „Felder“](media/service-get-started/fields.png)

2. Power BI analysiert die Daten und erstellt eine Visualisierung.  Wenn Sie zuerst **Datum** ausgewählt haben, wird eine Tabelle angezeigt.  Wenn Sie zuerst **Bruttoumsätze** ausgewählt haben, wird ein Diagramm angezeigt. Wechseln Sie für Ihre Daten zu einer anderen Anzeigeart. Im Folgenden werden diese Daten als Liniendiagramm dargestellt. Wählen Sie im Bereich **Visualisierungen** das Symbol für das Liniendiagramm (auch als „Vorlage“ bezeichnet).
   
   ![Berichts-Editor mit ausgewähltem Symbol](media/service-get-started/gettingstart5new.png)

3. Das möchten Sie verwenden und an ein Dashboard *anheften*. Zeigen Sie auf die Visualisierung, und wählen Sie das **Stecknadelsymbol** aus.  Wenn Sie diese Visualisierung anheften, wird sie auf dem Dashboard gespeichert und fortlaufend aktualisiert, sodass Sie den aktuellen Wert auf einen Blick nachverfolgen können.
   
   ![Anheften-Symbol](media/service-get-started/pinnew.png)

5. Da es sich um einen neuen Bericht handelt, werden Sie aufgefordert, ihn zu speichern, bevor Sie eine Visualisierung an ein Dashboard anheften können. Weisen Sie dem Bericht einen Namen zu (z.B. *Umsätze im zeitlichen Verlauf*), und wählen Sie **Speichern und Weiter** aus. 
   
   ![Dialogfeld „Bericht speichern“](media/service-get-started/pbi_getstartsaveb4pinnew.png)
   
6. Heften Sie jetzt das Liniendiagramm an ein neues Dashboard an, und benennen Sie es „Finanzbeispiel für Tutorial“. 
   
   ![Berichtbenennen](media/service-get-started/power-bi-pin.png)
   
 1. Wählen Sie **Anheften**aus.
   
    Eine Erfolgsmeldung (in der Nähe der oberen rechten Ecke) weist Sie darauf hin, dass die Visualisierung als Kachel zu Ihrem Dashboard hinzugefügt wurde.
   
    ![Dialogfeld „An das Dashboard angeheftet“](media/service-get-started/power-bi-pin-success.png)

8. Wählen Sie **Zum Dashboard wechseln** aus. Das Liniendiagramm ist als Kachel an das neue Dashboard angeheftet. Perfektionieren Sie das Dashboard, indem Sie weitere Visualisierungskacheln hinzufügen und [Kacheln umbenennen, verknüpfen, neu positionieren und in der Größe ändern](service-dashboard-edit-tile.md).
   
   ![Dashboard mit angehefteter Visualisierung](media/service-get-started/power-bi-new-dashboard.png)
   
   Wählen Sie die neue Kachel auf dem Dashboard aus, um jederzeit zum Bericht zurückzukehren. Sie kehren in Power BI zum Berichts-Editor in der Leseansicht zurück. Um wieder zur Bearbeitungsansicht zu wechseln, wählen Sie auf der oberen Menüleiste **Bericht bearbeiten** aus. Machen Sie sich in der Bearbeitungsansicht weiter mit den Kacheln und dem Anheften vertraut. 

## <a name="step-3--continue-the-exploration-with-qa-natural-language-querying"></a>Schritt 3: Setzen Sie die Untersuchung mithilfe von Q&A fort (Abfragen in natürlicher Sprache)
1. Versuchen Sie, im Feld für Fragen und Antworten eine Frage zu stellen, um eine schnelle Untersuchung Ihrer Daten durchzuführen. Das Q&A-Fragefeld befindet sich oben auf dem Dashboard (**Stellen Sie eine Frage zu Ihren Daten**) und im Bericht auf der oberen Menüleiste (**Frage stellen**). Geben Sie z. B. Folgendes ein: „Welches Segment weist den höchsten Umsatz auf?“.
   
   ![Q&A-Zeichenbereich](media/service-get-started/powerbi-qna.png)

2. Q&A sucht nach einer Antwort und präsentiert diese in Form einer Visualisierung. Wählen Sie das Anheftsymbol aus ![Anheften-Symbol](media/service-get-started/pbi_pinicon.png) um diese Visualisierung ebenfalls auf dem Dashboard anzuzeigen.
3. Heften Sie die Visualisierung an das Dashboard „Finanzbeispiel für Tutorial“ an.
   
    ![Dialogfeld „An das Dashboard anheften“](media/service-get-started/power-bi-pin2.png)

4. Kehren Sie zum Dashboard zurück, auf dem die neue Kachel angezeigt wird.

   ![Dashboard mit angeheftetem Diagramm](media/service-get-started/power-bi-final-dashboard.png)

## <a name="next-steps"></a>Nächste Schritte
Möchten Sie fortfahren?  Hier folgen einige hervorragenden Möglichkeiten, um sich mit Power BI vertraut zu machen.

* [Herstellen einer Verbindung mit einem anderen Dataset](service-get-data.md).
* [Teilen Sie Ihr Dashboard](service-share-dashboards.md) mit Ihren Kollegen.
* Lesen Sie die [Tipps zum Entwerfen von Dashboards](service-dashboards-design-tips.md).
* Zeigen Sie Ihre Dashboards mit einer [Power BI-App auf einem mobilen Gerät an](mobile-apps-for-mobile-devices.md).

Sind Sie noch nicht bereit, voll einzusteigen? Beginnen Sie mit diesen Themen, die Ihnen dabei helfen sollen, sich mit Power BI vertraut zu machen.

* [Erfahren Sie, wie Berichte, Datasets, Dashboards und Kacheln miteinander verbunden sind](service-basic-concepts.md)
* Besuchen Sie unsere Website [Power BI – Geführtes Lernen](guided-learning/index.md) und absolvieren Sie einige (sehr kurze) Kurse
* Sehen Sie sich [Power BI-Videos](videos.md) an
* [Verfügbare Beispiele](sample-datasets.md)

### <a name="stay-in-touch-with-power-bi"></a>Bleiben Sie hinsichtlich Power BI auf dem Laufenden
* Folgen Sie [@MSPowerBI auf Twitter](https://twitter.com/mspowerbi)
* Abonnieren Sie unseren [YouTube-Kanal](https://www.youtube.com/channel/UCy--PYvwBwAeuYaR8JLmrfg).
* Schauen Sie sich bei Bedarf unsere [Webinare zu den ersten Schritten mit Power BI](webinars.md) an.
* Sie wissen nicht, wo Sie Hilfe erhalten können? Besuchen Sie unsere Seite [10 Tipps, um Hilfe zu erhalten](service-tips-for-finding-help.md)

Weitere Fragen? [Stellen Sie Ihre Frage in der Power BI-Community.](http://community.powerbi.com/)

