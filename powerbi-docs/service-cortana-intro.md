---
title: Verwenden Sie Cortana zu suchen und Anzeigen von Berichten und Dashboards - Power BI
description: Verwenden Sie Cortana mit Power BI, um Antworten zu Ihren Daten zu erhalten. Derzeit kann mit Berichten und Dashboards gearbeitet werden.
author: maggiesMSFT
manager: kfile
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 05/29/2019
ms.author: maggies
LocalizationGroup: Ask questions of your data
ms.openlocfilehash: 6d53ddcfc4121e8937810bd6f734f91cd7a9fa39
ms.sourcegitcommit: 8bf2419b7cb4bf95fc975d07a329b78db5b19f81
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2019
ms.locfileid: "66375281"
---
# <a name="find-and-view-your-power-bi-data-with-cortana-for-power-bi"></a>Suchen und Anzeigen von Power BI-Daten mit Cortana für Power BI
Verwenden Sie Cortana auf Ihren Windows 10-Geräten, um sofort Antworten auf wichtige geschäftliche Fragen zu erhalten. Durch die Integration mit Power BI kann Cortana wichtige Informationen direkt aus Power BI-Dashboards und -Berichten abrufen. Sie benötigen lediglich die Windows 10-Version vom November 2015 oder eine höhere Version, Cortana, Power BI sowie Zugriff auf mindestens ein Dataset.

> [!IMPORTANT]
> Cortana-Integration ist in Power BI veraltet. Gestartet am 11. Juni, funktioniert Cortana nicht mehr für alle Dashboards und Berichte.

![Cortana-Suchfeld](media/service-cortana-intro/power-bi-cortana-searchbox.png)

## <a name="preview-the-new-cortana-dashboard-search-experience-for-windows-10"></a>Vorschauversion der neuen *Dashboard*-Suche von Cortana für Windows 10
Sie sind bereits eine Weile in der Lage, [mithilfe von Cortana bestimmte Typen von Berichtsseiten abzurufen](service-cortana-answer-cards.md). Nun haben wir eine **neue Benutzererfahrung** hinzugefügt: Sie können nun auch Dashboards abrufen. Probieren Sie es aus und [senden Sie uns Feedback an Power BI Ideas](https://ideas.powerbi.com/forums/265200-power-bi). Schließlich wird die *neue Benutzererfahrung* erweitert, dass auch eine Cortana-Suche für Berichte verfügbar ist.  Einer der wichtigsten Vorteile der neuen Benutzeroberfläche ist der, dass Sie keine speziellen Einrichtungsschritte ausführen müssen – kein Aktivieren von Cortana und keine Konfiguration von Windows 10 erforderlich. Die Features sind sofort einsatzbereit.

> [!NOTE]
> Sollte sie nicht „sofort einsatzbereit“ sein, sehen Sie den [Artikel zur Problembehandlung](service-cortana-troubleshoot.md) ein, um Hilfe zu erhalten.
> 
> 

Die zugrunde liegende Technologie verwendet den [Azure Search-Dienst von Microsoft](https://docs.microsoft.com/azure/search/). Dieser Suchdienst bietet weitere Möglichkeiten, wie intelligente Bewertung, Fehlerkorrektur und Autovervollständigung.

Beide Cortana-Funktionen können die Seite-an-Seite vorhanden sein.

## <a name="cortana-for-power-bi-documentation"></a>Dokumentation zu Cortana für Power BI
Vier Dokumente führen Sie durch das Einrichten und Verwenden von Cortana für Power BI her.

**Artikel 1** (dieser Artikel): So erfolgt die Zusammenarbeit von Cortana und Power BI

**Artikel 2**: [Durchsuchen von Power BI-Berichten: Aktivieren von Cortana für den Zugriff auf Power BI-Berichte](service-cortana-enable.md)

**Artikel 3**: [Durchsuchen von Power BI-Berichten: Erstellen von speziellen *Cortana-Antwortkarten*](service-cortana-answer-cards.md)

**Artikel 4**: [Behandeln von Problemen](service-cortana-troubleshoot.md)

## <a name="how-cortana-and-power-bi-work-together"></a>Zusammenarbeit von Cortana und Power BI
Wenn Sie mit Cortana eine Frage stellen, kann Cortana auch in Power BI nach Antworten suchen. Cortana kann in Power BI umfassende, auf Daten in Power BI-Berichten basierende Antworten ermitteln (die einen besonderen Typ von Berichtsseiten enthalten, der als *Cortana-Antwortkarte* bezeichnet wird). Eine weitere Quelle sind Power BI-Dashboards.

Wenn Cortana eine Übereinstimmung findet, wird der Name des Dashboards oder der Berichtsseite direkt auf dem Cortana-Bildschirm angezeigt. Das Dashboard oder die Berichtsseite kann in Power BI geöffnet werden. Berichtsseiten können auch direkt in Cortana durchsucht werden, denn sie sind interaktiv.

![Interaktive Berichtsseite wird in Cortana angezeigt.](media/service-cortana-intro/power-bi-report-cortana-s.png)

### <a name="cortana-and-dashboards-the-new-experience"></a>Cortana und Dashboards (die *neue Benutzererfahrung*)
Cortana sucht nach Antworten in Ihren eigenen Dashboards sowie in Dashboards, die für Sie freigegeben wurden. Stellen Sie Cortana Fragen anhand von Titeln, Schlüsselwörtern, Besitzernamen, Arbeitsbereichsnamen, App-Namen usw.

Ihre Frage muss mindestens zwei Wörter umfassen, damit Cortana eine Antwort finden kann. Wenn Sie also in einem Dashboard suchen, dessen Name aus einem Wort besteht („Marketing“), fügen Sie den Begriff „anzeigen“ oder „Power BI“ oder den Besitzernamen zu Ihrer Frage hinzu, z.B. „Marketing anzeigen“ und „Michele Hart-Beispiel“. 

Weist Ihr Dashboard einen aus mehreren Wörtern bestehenden Titel auf, gibt Cortana dieses Dashboard nur zurück, wenn die Suche eine Übereinstimmung mit mindestens zwei Wörtern oder einem Wort und dem Besitzernamen ergibt. Für ein Dashboard mit dem Namen „Beispiel zur Kundenrentabilität“: 

* "Kunden b anzeigen" *nicht* Power BI Dashboard als Ergebnis zurück.   
* "äußerungen wie"kundenrentabilität anzeigen","kundenr","Kunde","Beispiel zur kundenrentabilität","Michele Hart-Beispiel","kundenrentabilität anzeigen"und"kundenr anzeigen" *führen* Power BI-Ergebnis zurück.
* Das Wort "Powerbi" hinzugefügt zählt es als eines der zwei erforderlichen Wörter, also "Powerbi Beispiel" *ist* Power BI-Ergebnis zurück. 
  
    ![Cortana-Suche mit mindestens zwei Wörtern](media/service-cortana-intro/power-bi-cortana-2-words.png)

### <a name="cortana-and-reports"></a>Cortana und Berichte
 Cortana findet Antworten in Berichten, die [Seiten enthalten, welche speziell für die Anzeige in Cortana entwickelt wurden](service-cortana-answer-cards.md). Stellen Sie nur Fragen unter Verwendung der Titel oder Schlüsselwörter aus einer dieser speziellen Berichtsseiten.  

Die zugrunde liegende Technologie für die Verwendung von Berichten [Power BI F & A](power-bi-tutorial-q-and-a.md).

Wenn Sie in Cortana eine Frage stellen, gibt Power BI Antworten mit Berichtsseiten aus, die speziell für Cortana entwickelt wurden. Mögliche Antworten werden von Cortana direkt anhand der Cortana-*Antwortkarten* bestimmt, die bereits in Power BI erstellt sind.  Zum weiteren Erkunden einer Antwort öffnen Sie ein Ergebnis in Power BI.

> [!NOTE]
> Bevor Cortana in den Power BI-Berichten nach Antworten suchen kann, müssen Sie [dieses Feature mithilfe des Power BI-Diensts aktivieren und Windows für die Kommunikation mit Power BI](service-cortana-enable.md) einrichten.  
> 
> 

## <a name="using-cortana-to-get-answers-from-power-bi"></a>Verwenden von Cortana, um Antworten aus Power BI abzurufen
1. Beginnen Sie in Cortana. Es gibt viele verschiedene Möglichkeiten, Cortana zu *öffnen*: Wählen Sie das Cortana-Symbol auf der Taskleiste (unten abgebildet) aus, verwenden Sie Sprachbefehle, oder tippen Sie auf das Suchsymbol auf Ihrem Windows-Mobilgerät.
   
     ![](media/service-cortana-intro/power-bi-cortana-searchbox.png)
2. Sobald Cortana bereit ist, können Sie Ihre Frage in der Suchleiste von Cortana eingeben oder sprechen. Cortana zeigt die verfügbaren Ergebnisse an. Wenn ein Power BI-Dashboard vorhanden ist, das Ihrer Frage entspricht, wird sie unter **Höchste Übereinstimmung** oder **Power BI** angezeigt.
   
     ![Cortana-Suche findet Power BI-Dashboard](media/service-cortana-intro/power-bi-cortana-search-hr.png "Cortana findet ein Power BI-Dashboard")
   
   > [!NOTE]
   > Derzeit wird nur die englische Sprache unterstützt.
   > 
   > 
3. Wählen Sie das Dashboard aus, um es in Cortana zu öffnen.

    ![Power BI-Dashboard auswählen](media/service-cortana-intro/power-bi-cortana-dashboard.png "Power BI-Dashboard auswählen")

    Sie können das Layout ändern, indem Sie die [*Telefonansicht* des Dashboards bearbeiten](service-create-dashboard-mobile-phone-view.md). 

1. Von Cortana aus können Sie das Dashboard im Power BI-Dienst oder in Power BI Mobile öffnen. Öffnen Sie das Dashboard im Power BI-Dienst, indem Sie **Im Web öffnen** auswählen. 
   
   ![Öffnen des Dashboards aus Cortana](media/service-cortana-intro/power-bi-dashboard-opens.png "Öffnen des Dashboards aus Cortana")   
4. Suchen Sie nun mithilfe von Cortana nach einem Bericht. Es muss sichergestellt sein, dass es einen [Bericht gibt, der eine Seite mit einer Cortana-Antwortkarte enthält](service-cortana-answer-cards.md). In diesem Beispiel enthält ein Bericht mit dem Namen „Cortana-New-Stores“ eine Cortana-Antwortkarte mit dem Namen „cortana stores“.  
   
     Sprechen oder geben Sie in der Cortana-Suchleiste Ihre Frage ein. Cortana zeigt die verfügbaren Ergebnisse an. Wenn eine Power BI-Berichtsseite vorhanden ist, die Ihrer Frage entspricht, wird sie unter **Höchste Übereinstimmung** oder **Power BI** angezeigt. Und in diesem Beispiel wird zudem die PBIX-Datei (und die Sicherung) angezeigt, die ich zum Erstellen der Antwortkarten verwendet habe (unter **Dokumente**).
   
     ![Suchen nach einem Bericht](media/service-cortana-intro/power-bi-cortana-search3-m.png "Suchen nach einem Bericht") 
5. Wählen Sie die Berichtsseite **Cortana stores** aus, um sie im Cortana-Fenster anzuzeigen.
   
    ![Berichtsseite wird in Cortana geöffnet](media/service-cortana-intro/power-bi-report-cortana-opens.png "Berichtsseite wird in Cortana geöffnet")   
   
    Beachten Sie, dass eine *Antwortkarte* ein besonderer Typ von Power BI-Berichtsseite ist, die vom Besitzer eines Datasets erstellt wurde.  Weitere Informationen finden Sie unter [Erstellen einer Cortana-Antwortkarte](service-cortana-answer-cards.md).
6. Aber das ist noch nicht alles. Sie können wie in Power BI mit den Visualisierungen auf der Antwortkarte interagieren.
   
   * Wählen Sie z.B. ein Element in einer Visualisierung aus, um die anderen Visualisierungen auf der Antwortkarte kreuzzufiltern und hervorzuheben.
     
     ![](media/service-cortana-intro/power-bi-cortana-filtered-new.png)
   * Oder verwenden Sie stattdessen natürliche Sprache, um die Ergebnisse zu filtern.  Wenn Sie z.B. die Frage „Cortana stores for Lindseys“ stellen, wird die Karte gefiltert, sodass nur Daten für die Handelskette Lindseys angezeigt werden.
     
     ![Kreuzfilter in Cortana](media/service-cortana-intro/power-bi-cortana-filtered-2.png "Kreuzfilter in Cortana")
7. Setzen Sie Ihre Erkundung fort. Scrollen Sie zum unteren Rand des Cortana-Fensters, und wählen Sie **In Power BI öffnen** aus.
   
     ![](media/service-cortana-intro/power-bi-cortana-open-new.png)
8. Die Berichtsseite wird in Power BI geöffnet.    
     ![Öffnen des Berichts aus Cortana](media/service-cortana-intro/power-bi-cortana-open2.png "Cortana-Antwortkarte wird in der Cortana-Suche geöffnet.")

## <a name="considerations-and-troubleshooting"></a>Zu beachtende Aspekte und Problembehandlung
* Cortana hat keinen Zugriff auf Cortana-Karten, die noch nicht [für Power BI aktiviert](service-cortana-enable.md).
* Können Sie Cortana immer noch nicht mit Power BI verwenden?  Verwenden Sie die [Cortana-Problembehandlung](service-cortana-troubleshoot.md).
* Cortana ist für Power BI derzeit nur in englischer Sprache verfügbar.
* Cortana für Power BI ist nur auf Windows-Mobilgeräten verfügbar.

Weitere Fragen? [Wenden Sie sich an die Power BI-Community](http://community.powerbi.com/).
Feedback? [Senden Sie uns Ihr Feedback unter „Power BI Ideas“.](https://ideas.powerbi.com/forums/265200-power-bi)

## <a name="next-steps"></a>Nächste Schritte
[Aktivieren der Integration von Cortana – Power BI – Windows für Berichte](service-cortana-enable.md)

