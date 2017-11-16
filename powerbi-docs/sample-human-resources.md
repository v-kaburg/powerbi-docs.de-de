---
title: "Beispiel für Personalwesen: Tour"
description: "Beispiel für Personalwesen für Power BI: Tour"
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
ms.date: 10/28/2017
ms.author: mihart
ms.openlocfilehash: ef064c636880db5d1b6c6106fe742972a7ed3a3c
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2017
---
# <a name="human-resources-sample-for-power-bi-take-a-tour"></a>Beispiel für Personalwesen für Power BI: Tour
Die Personalabteilung verwendet dasselbe Berichtsmodell für unterschiedliche Unternehmen, auch wenn diese sich nach Branche oder Größe unterscheiden. In diesem Beispiel werfen wir einen Blick auf neu eingestellte Mitarbeiter, aktive Mitarbeiter und Mitarbeiter, die das Unternehmen verlassen haben. Es wird versucht, Trends bei der Personalgewinnungsstrategie zu ermitteln. Hauptsächlich sollen folgende Erkenntnisse gewonnen werden:

* Wen wir einstellen
* Tendenzen unserer Personalgewinnungsstrategie
* Trends bei freiwilligem Ausscheiden

Dieses Beispiel ist Teil einer Reihe, die Ihnen die Verwendung von Power BI anhand geschäftsbezogener Daten, Berichte und Dashboards veranschaulicht. Hierbei handelt es sich um echte Daten von obviEnce ([www.obvience.com](http://www.obvience.com/)) in anonymisierter Form.

![](media/sample-human-resources/hr1.png)

Führen Sie hierzu die folgenden Schritte aus: Navigieren Sie im [Power BI-Dienst](https://powerbi.com) zu **Daten abrufen > Beispiele > Beispiel für Personalwesen > Verbinden**, um Ihr eigenes Exemplar des Beispiels abzurufen.

Alternativ können Sie [nur das Dataset (Excel-Arbeitsmappe) für dieses Beispiel herunterladen](http://go.microsoft.com/fwlink/?LinkId=529780).

## <a name="new-hires"></a>Neue Mitarbeiter
Betrachten wir zunächst die Neueinstellungen.

1. Wählen Sie im Arbeitsbereich die Registerkarte **Dashboards**, und öffnen Sie das Dashboard „Personalwesen“.
2. Wählen Sie im Dashboard die Kachel **Anzahl der Neueinstellungen, Neueinstellungen im gleichen Zeitraum des Vorjahres, % Veränderung der Aktiven im Jahresvergleich** **Nach Monat** aus.  
   ![](media/sample-human-resources/hr2.png)  
   
   Der Beispielbericht „Personalwesen“ wird auf der Seite **Neueinstellungen** geöffnet.  
   
   ![](media/sample-human-resources/hr3.png)

Beachten Sie Folgendes:

* Das Kombinationsdiagramm **Anzahl der Neueinstellungen, Neueinstellungen GZVJ und % Aktive im Jahresvergleich – Veränderung nach Monat** zeigt, dass wir in jedem Monat des laufenden Jahres mehr Mitarbeiter als im Vorjahr eingestellt haben – in einigen Monaten erheblich mehr Mitarbeiter.
* Beachten Sie im Kombinationsdiagramm **Anzahl der Neueinstellungen und Anzahl der aktiven Mitarbeiter nach Region und ethnischer Gruppe**, dass wir weniger Personen im Bereich **Osten** einstellen.
* Das Wasserfalldiagramm **Neueinstellungen im Jahresvergleich, Abw. nach Altersgruppe** zeigt, dass wir vor allem jüngere Menschen einstellen. Dies kann daran liegen, dass die Stellen häufig Teilzeitstellen sind.
* Das Kreisdiagramm **Anzahl der Neueinstellungen nach Geschlecht** zeigt eine ziemlich gleichmäßige Verteilung.

Können Sie noch weitere Erkenntnisse gewinnen? Beispielsweise eine Region, in der die Verteilung beim Geschlecht nicht gleichmäßig ist? Wählen Sie in den Diagrammen die verschiedenen Altersgruppen und Geschlechter aus, um die Beziehungen zwischen Alter, Geschlecht, Region und ethnischer Gruppe zu untersuchen.

Wählen Sie den Namen des Dashboards aus der oberen Navigationsleiste aus, um zum Dashboard zurückzukehren.

![](media/sample-human-resources/power-bi-breadcrumbs.png)

## <a name="compare-current-active-and-former-employees"></a>Vergleichen der derzeit aktiven und ehemaligen Mitarbeiter
Wir sehen uns die Daten für die derzeit aktiven Mitarbeiter und die Mitarbeiter an, die nicht mehr für das Unternehmen arbeiten.

Wählen Sie auf dem Dashboard die Kachel **Anzahl der aktiven Mitarbeiter nach Altersgruppen** aus.  
![](media/sample-human-resources/pbi_hr_sample_activepie.png)

Der Beispielbericht „Personalwesen“ wird auf der Seite **Aktive Mitarbeiter i. Vgl. zu Trennungen** geöffnet.  
![](media/sample-human-resources/hr5.png)

**Interessante Elemente:**

* In den Kombinationsdiagrammen auf der linken Seite wird die Veränderung Jahr über Jahr für aktive und ausgeschiedene Mitarbeiter angezeigt. Aufgrund von vermehrten Einstellungen haben wir in diesem Jahr mehr aktive Mitarbeiter, aber auch mehr ausgeschiedene Mitarbeiter als im letzten Jahr.
* Im August hatten wir im Vergleich zu den anderen Monaten mehr ausgeschiedene Mitarbeiter. Wählen Sie die verschiedenen Altersgruppen, Geschlechter oder Regionen aus, um festzustellen, ob Ausreißer vorhanden sind.
* Wenn wir uns die Kreisdiagramme ansehen, fällt auf, dass in Bezug auf die aktiven Mitarbeiter nach Geschlecht und Altersgruppe eine relativ gleichmäßige Verteilung besteht. Wählen Sie verschiedene Altersgruppen aus, um die Geschlechtsverteilung nach Alter anzuzeigen. Liegt für jede Altersgruppe eine gleichmäßige Verteilung nach Geschlecht vor? 

## <a name="reasons-for-separation"></a>Gründe für das Ausscheiden
Wir sehen uns den Bericht in der Bearbeitungsansicht an. Wählen Sie in der oberen linken Ecke **Bericht bearbeiten** aus. 

Ändern Sie die Kreisdiagramme so, dass keine Daten für aktive Mitarbeiter, sondern für ausgeschiedene Mitarbeiter angezeigt werden.

1. Wählen Sie das Kreisdiagramm **Anzahl der aktiven Mitarbeiter nach Altersgruppen** aus.
2. Wählen Sie unter **Felder** den Pfeil neben **Mitarbeiter** aus, um die Mitarbeitertabelle zu erweitern. Deaktivieren Sie das Kontrollkästchen neben **Anzahl der aktiven Mitarbeiter**, um das Feld zu entfernen.
3. Aktivieren Sie in der Tabelle „Mitarbeiter“ das Kontrollkästchen neben **Anzahl der Ausgeschiedenen** , um dieses Element dem Feld **Werte** in der Feldquelle hinzuzufügen.
4. Aktivieren Sie im Zeichenbereich für den Bericht im Balkendiagramm **Anzahl der Trennungen nach Trennungsgrund** den Balken **Freiwillig**. Dies hebt in den anderen Visualisierungen im Bericht die Personen hervor, die freiwillig ausgeschieden sind.
5. Klicken Sie im Kreisdiagramm „Anzahl der Trennungen nach Altersgruppe“ auf das Segment „50+“.
   
   Sehen Sie sich unten rechts das Liniendiagramm „Ausscheiden nach Grund“ an. Dieses Diagramm wird gefiltert, um freiwillig ausgeschiedene Mitarbeiter anzuzeigen.  
   ![](media/sample-human-resources/pbi_hr_sample_sepsover50.png)
   
   Erkennen Sie den Trend in der Altersgruppe 50+? In der zweiten Jahreshälfte scheiden vermehrt Mitarbeiter mit mehr als 50 Jahren freiwillig aus. Dies ist ein Bereich, der anhand von weiteren Daten genauer untersucht werden kann.
6. Sie können die gleichen Schritte auch für das Kreisdiagramm **Anzahl der aktiven Mitarbeiter nach Geschlecht** ausführen und es von aktiven Mitarbeiter in Trennungen ändern. Sehen Sie sich die Daten zum freiwilligen Ausscheiden nach Geschlecht an, um nach weiteren Erkenntnissen zu suchen.
7. Klicken Sie in der oberen Navigationsleiste auf **Power BI** , um zum Dashboard zurückzukehren. Wenn Sie möchten, können Sie die Änderungen speichern, die Sie am Bericht vorgenommen haben.

## <a name="bad-hires"></a>Fehleinstellungen
Als Letztes untersuchen wir den Bereich der Fehleinstellungen. Bei Fehleinstellungen geht es um Mitarbeiter, die weniger als 60 Tage im Unternehmen tätig waren. Wir stellen Mitarbeiter schnell ein. Stellen wir auch gute Kandidaten ein?

1. Wählen Sie die Dashboardkachel **Fehleinstellungen in % aktiver Mitarbeiter nach Altersgruppe** aus. Der Bericht wird auf Seite 3, „Fehleinstellungen“, geöffnet.
   
   ![](media/sample-human-resources/hr7.png)  
2. Aktivieren Sie im Slicer „Region“ auf der linken Seite das Kontrollkästchen **Nordwesten** und das Segment **Männlich** im Ringdiagramm „Anzahl der Fehleinstellungen nach Geschlecht“.  Sehen Sie sich die anderen Diagramme auf der Seite „Fehleinstellungen“ an. Es sind mehr männliche als weibliche Fehleinstellungen und viele Fehleinstellungen in der Gruppe A erkennbar.
   ![](media/sample-human-resources/pbi_hr_sample_badhirespage.png)  
3. Wenn Sie sich das Ringdiagramm **Fehleinstellungen nach Geschlecht** ansehen und durch den Datenschnitt **Region** klicken, sehen Sie, dass „Osten“ die einzige Region mit mehr weiblichen als männlichen Fehleinstellungen ist.  
4. Wählen Sie den Namen des Dashboards aus der oberen Navigationsleiste aus, um zum Dashboard zurückzukehren.

## <a name="asking-a-question-in-the-qa-box"></a>Stellen einer Frage im Feld für Fragen und Antworten
Das [Q&A-Fragefeld](service-how-to-q-and-a.md) ist der Ort, an dem Sie eine natürlichsprachliche Frage eingeben können. Q&A erkennt die eingegebenen Wörter und schließt, wo in Ihrem Dataset eine Antwort zu finden ist.

1. Klicken Sie in das Q&A-Fragefeld. Beachten Sie, dass das Q&A-Feld bereits Vorschläge enthält, noch bevor Sie mit der Eingabe beginnen:
   
   ![](media/sample-human-resources/pbi_hr_sample_qabox.png)
2. Sie können einen dieser Vorschläge auswählen oder eingeben: **Altersgruppe, Geschlecht und Fehleinstellungen im gleichen Vorjahreszeitraum für Region Osten anzeigen**.  
   
   ![](media/sample-human-resources/pbi_hr_sample_qa_answer.png)
   
   Beachten Sie, dass die meisten der weiblichen Fehleinstellungen jünger als 30 Jahre sind.

Dies ist eine Umgebung, in der Sie sicher experimentieren können. Sie können sich immer noch entscheiden, Ihre Änderungen nicht zu speichern. Wenn Sie sie speichern, können Sie immer wieder zu **Daten abrufen** zurückkehren, um ein neues Exemplar dieses Beispiels herunterzuladen.

## <a name="next-steps-connect-to-your-data"></a>Nächste Schritte: Herstellen der Verbindung mit Ihren Daten
Wir hoffen, diese Tour hat Ihnen gezeigt, wie Power BI-Dashboards, das Fragen und Antworten-Modul und Berichte Ihnen Einblicke in Personaldaten geben können. Es ist jetzt an Ihnen – stellen Sie Verbindungen mit Ihren eigenen Daten her. Mit Power BI können Sie Verbindungen zu einer Vielzahl von Datenquellen herstellen. Weitere Informationen zum [Einstieg in Power BI](service-get-started.md).  

