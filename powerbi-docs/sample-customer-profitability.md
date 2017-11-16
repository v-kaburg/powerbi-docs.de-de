---
title: "Beispiel zur Kundenrentabilität für Power BI: Tour"
description: "Beispiel zur Kundenrentabilität für Power BI: Tour"
services: powerbi
documentationcenter: 
author: amandacofsky
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
ms.date: 10/29/2017
ms.author: mihart
ms.openlocfilehash: 9a100b7d13c11a8bd066b72a570f45d0c2bc08be
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2017
---
# <a name="customer-profitability-sample-for-power-bi-take-a-tour"></a>Beispiel zur Kundenrentabilität für Power BI: Tour
Das Inhaltspaket „Beispiel zur Kundenrentabilität“ enthält ein Dashboard, einen Bericht und ein Dataset für ein Unternehmen, das Marketingmaterial herstellt. Dieses Dashboard wurde von einer Finanzdirektorin (CFO) erstellt, um die Metriken für ihre fünf Business Unit Manager (Führungskräfte), Produkte, Kunden und den Bruttogewinn verfolgen zu können. Sie sieht auf einen Blick, welche Faktoren sich auf die Rentabilität auswirken.

Dieses Beispiel ist Teil einer Reihe, die Ihnen die Verwendung von Power BI anhand geschäftsbezogener Daten, Berichte und Dashboards veranschaulicht. Hierbei handelt es sich um echte Daten von obviEnce ([www.obvience.com](http://www.obvience.com/)) in anonymisierter Form.

Alternativ können Sie [nur das Dataset (Excel-Arbeitsmappe) für dieses Beispiel herunterladen](http://go.microsoft.com/fwlink/?LinkId=529781).  
![](media/sample-customer-profitability/power-bi-dash.png)

## <a name="what-is-our-dashboard-telling-us"></a>Welche Erkenntnisse gewinnen wir über unser Dashboard?
### <a name="company-wide-dashboard-tiles"></a>Unternehmensweite Dashboardkacheln
Mit diesen Kacheln erhält die Finanzdirektorin einen groben Überblick über die Metriken des Unternehmens, die für sie wichtig sind.  Wenn sie etwas Interessantes sieht, kann sie eine Kachel auswählen, um einen genaueren Blick auf die Daten zu werfen.

1. Der Bruttogewinn des Unternehmens beträgt 42,5 %.
2. Es hat 80 Kunden.
3. Es verkauft fünf verschiedene Produkte.
4. Die geringste Umsatzabweichung vom Budget in Prozent war im Februar, gefolgt von der höchsten Abweichung im März.
5. Die meisten Einnahmen stammen aus den Regionen „Osten“ und „Norden“. Der Bruttogewinn hat zu keinem Zeitpunkt das Budget überschritten, wobei die Punkte „ER-0“ und „MA-0“ einer weiteren Untersuchung bedürfen.
6. Der Gesamtumsatz für das Jahr liegt nahe an der Budgetvorgabe.

### <a name="manager-specific-dashboard-tiles"></a>Managerspezifische Dashboardkacheln
Diese Kacheln verfügen über eine Team-Scorecard. Die Finanzdirektorin muss die Aktivitäten ihrer Manager verfolgen können, und über diese Kacheln erhält sie einen ersten Überblick über den Gewinn (unter Verwendung des Bruttogewinns in %). Falls der Trend für den Bruttogewinn in % für einen Manager ungewöhnlich ist, kann sie dies näher untersuchen.

Der Bruttogewinn in % von Annelie ist am niedrigsten, aber es ist ein kontinuierlicher Anstieg seit März zu erkennen. Der Bruttogewinn in % von Valery ist dagegen erheblich gefallen. Und Andrew hatte ein wechselhaftes Jahr. Klicken Sie auf eine managerspezifische Kachel, um den zugrunde liegenden Bericht zu öffnen. Der Bericht hat drei Seiten und beginnt mit der Seite „Industry Margin Analysis“.

## <a name="explore-the-pages-in-the-report"></a>Untersuchen der Seiten des Berichts
Der Bericht hat drei Seiten:

* Auf der Seite „Team Scorecard“ werden die Leistung der fünf Manager und ihre Umsatzdaten aufgeführt.
* Auf der Seite „Industry Margin Analysis“ wird die Rentabilität im Vergleich zur gesamten Branche analysiert.
* Auf der Seite „Executive Scorecard“ wird eine für Cortana formatierte Ansicht der Daten der einzelnen Manager geboten.

### <a name="team-scorecard-page"></a>Seite „Team-Scorecard“
![](media/sample-customer-profitability/customer2.png)

Wir sehen uns nun zwei Teammitglieder genauer an und ermitteln, welche Erkenntnisse wir gewinnen können. Wählen Sie links im Datenschnitt den Namen „Andrew“ aus, um die Berichtsseite zu filtern und nur Daten für Andrew anzuzeigen.

* Um schnell einen Blick auf den KPI zu werfen, sehen Sie sich den **Umsatzstatus** von Andrew an – er ist grün. Er erzielt gute Ergebnisse.
* Im Flächendiagramm „Umsatzabweichung in % vom Budget nach Monat“ ist zu sehen, dass Andrew bis auf einen Einbruch im Februar insgesamt gute Ergebnisse erzielt. Seine wichtigste Region ist „Osten“, und er bearbeitet 49 Kunden und fünf (von sieben) Produkten. Sein Bruttogewinn in % ist nicht der höchste und nicht der niedrigste.
* Unter „Jahresumsatz und Umsatzabweichung in % vom Budget nach Monat“ wird ein kontinuierlicher und gleichmäßiger Gewinnverlauf angezeigt. Wenn Sie filtern, indem Sie im Treemap-Diagramm für die Region auf das Quadrat für **Mitte** klicken, erkennen Sie aber, dass Andrew nur im März und nur in Indiana über Umsatz verfügt. Ist dies Absicht, oder handelt es sich um etwas, das näher untersucht werden sollte?

Jetzt machen wir mit Valery weiter. Wählen Sie im Datenschnitt den Namen „Valery“ aus, um die Berichtsseite zu filtern und nur Daten für Valery anzuzeigen.  
![](media/sample-customer-profitability/customer3.png)

* Beachten Sie den roten KPI-Hinweis für **Jahresumsatzstatus**. Dies sollte auf jeden Fall näher untersucht werden.
* Die Umsatzabweichung gibt ebenfalls Anlass zur Sorge, denn sie erreicht ihre Umsatzmargen nicht.
* Valery hat nur neun Kunden, bearbeitet nur zwei Produkte und arbeitet fast ausschließlich mit Kunden im Norden zusammen. Diese Art der Spezialisierung könnte eine Erklärung für die großen Schwankungen in ihren Metriken sein.
* Wenn Sie das Quadrat **Norden** im Treemap-Diagramm auswählen, erkennen Sie, dass der Bruttogewinn von Valery im Norden mit ihrer Gesamtmarge übereinstimmt.
* Die Auswahl der anderen Quadrate für die **Region** führt zu einem interessanten Ergebnis: der Bruttogewinn in Prozent schwankt zwischen 23 % und 79 %, und die Umsatzzahlen sind in allen Regionen – mit Ausnahme des Nordens – stark saisonabhängig.

Forschen Sie weiter, um herauszufinden, warum im Bereich von Valery keine gute Leistung erzielt wird. Sehen Sie sich die Regionen, die anderen Geschäftseinheiten und die nächste Seite des Berichts an: „Analyse der Branchenmarge“.

### <a name="industry-margin-analysis"></a>Analyse der Branchenmarge
Auf dieser Berichtsseite wird ein anderes Segment der Daten bereitgestellt. Es geht um den Bruttogewinn der gesamten Branche, unterteilt nach Segment. Die Finanzdirektorin verwendet diese Seite, um Metriken des Unternehmens und der Geschäftseinheiten mit Branchenmetriken zu vergleichen und so Trends und Auswirkungen auf die Rentabilität erklären zu können. Vielleicht fragen Sie sich, warum das Flächendiagramm „Bruttogewinn nach Monat und Managername“ auf dieser Seite angeordnet ist, obwohl es eher für das Team gilt. Der Grund ist, dass wir die Seite hiermit nach Business Unit Manager filtern können.  
![](media/sample-customer-profitability/customer6.png)

Inwiefern variiert die Rentabilität nach der Branche? Wie lassen sich die Produkte und Kunden nach Branche unterteilen? Wählen Sie oben links eine oder mehrere Branchen aus. (Beginnen Sie mit den Verbrauchsgütern (CPG).) Wählen Sie das Radierersymbol aus, um den Filter zu löschen.

Im Blasendiagramm sucht die Finanzdirektorin nach den größten Blasen, da sich diese am stärksten auf den Umsatz auswirken. Wenn Sie die Seite nach Manager filtern, indem Sie im Flächendiagramm auf den jeweiligen Namen klicken, können Sie die Beiträge der Manager nach Branchensegment sehen.

* Der Einflussbereich von Andrew reicht über viele verschiedene Branchensegmente und weist starke Abweichungen beim Bruttogewinn in % (meist positiv) und bei der Abweichung in % auf. 
* Das Diagramm von Annelie ist ähnlich. Die Ausnahme ist, dass sie nur eine Handvoll Branchensegmente abdeckt und dass der Schwerpunkt auf dem Segment „Behörden“ und dem Produkt „Gladius“ liegt. 
* Bei Carlos liegt der Schwerpunkt eindeutig auf dem Segment „Dienstleistungen“, und der Gewinn ist gut. Er hat die Abweichung in % für das Segment „Hightech“ stark verbessert und im neuen Segment „Industrie“ gegenüber dem Budget ein hervorragendes Ergebnis erzielt. 
* Tina bearbeitet eine Handvoll Segmente und verfügt über den höchsten Bruttogewinn in %, aber an den zumeist kleinen Blasen ist erkennbar, dass ihr Beitrag zum Gesamtergebnis des Unternehmens sehr gering ist. 
* Valery, die nur für ein Produkt verantwortlich ist, bearbeitet nur fünf Branchensegmente. Ihr Brancheneinfluss ist saisonabhängig, aber es ergibt sich immer eine große Blase. Dies deutet auf einen signifikanten Beitrag zum Gesamtergebnis des Unternehmens hin. Beruht die negative Leistung auf der Branche?

### <a name="executive-scorecard"></a>Executive Scorecard
Diese Seite wird als Antwortkarte für Cortana formatiert. Weitere Informationen finden Sie unter [Erstellen von Antwortkarten für Cortana](service-cortana-answer-cards.md).

## <a name="dig-into-the-data-by-asking-questions-with-qa"></a>Näheres Untersuchen der Daten durch Stellen von Fragen mit Q&A
Für die Analyse wäre es hilfreich zu ermitteln, in welcher Branche Valery den höchsten Umsatz erzielt. Hierfür verwenden wir Q&A.

1. Wählen Sie in der oberen Navigationsleiste **Power BI** aus, um zum Dashboard zurückzukehren.
2. Wählen Sie oben im Dashboard das Q&A-Feld aus.
   
    ![](media/sample-customer-profitability/customer4.png)
3. Geben Sie **Gesamtumsatz nach Branche für Valery**ein. Sie sehen, wie die Visualisierung beim Eingeben der Frage aktualisiert wird.
   
    ![](media/sample-customer-profitability/customer5.png)
   
   Die Distribution ist der größte Umsatzbereich für Valery.

### <a name="dig-deeper-by-adding-filters"></a>Nähere Untersuchung durch das Hinzufügen von Filtern
Wir sehen uns die Branche *Distribution* an.  

1. Kehren Sie zum Dashboard zurück, und wählen Sie das Flächendiagramm mit dem Bruttogewinntrend für Andrew aus. Der Bericht wird mit der Seite „Analyse der Branchenmarge“ geöffnet.
2. Erweitern Sie den Filterbereich auf der rechten Seite, ohne eine der Visualisierungen auf der Berichtsseite auszuwählen. Im Filterbereich sollten nur Filter auf Seitenebene angezeigt werden.  
   
   ![](media/sample-customer-profitability/power-bi-filters.png)
3. Suchen Sie den Filter für **Branche**, und wählen Sie den Pfeil, um die Liste zu erweitern. Fügen wir nun einen Seitenfilter für die Branche „Distribution“ hinzu. Heben Sie zunächst die gesamte Auswahl auf, indem Sie das Kontrollkästchen **Alles auswählen** deaktivieren. Wählen Sie dann **Distribution** aus.  
   
   ![](media/sample-customer-profitability/customer7.png)
4. Im Flächendiagramm „Bruttogewinn nach Monat und Managername“ sehen wir, dass nur Valery und Tina Kunden aus dieser Branche haben und dass Valery für diese Branche nur von Juni bis November tätig war.   
5. Wählen Sie in der Legende des Flächendiagramms „Bruttogewinn nach Monat und Managername“ zuerst **Tina** und dann **Valery** aus. Beachten Sie, dass der Anteil von „Gesamtumsatz nach Produkt“ im Vergleich zu Valery sehr gering ist. 
6. Kehren Sie zum Anzeigen des tatsächlichen Umsatzes zum Dashboard zurück, und verwenden Sie den Q&A-Bereich, um nach dem **Gesamtumsatz für Distribution nach Szenario nach Manager** zu fragen.  
   
   ![](media/sample-customer-profitability/customer8.png)

Auf ähnliche Weise können wir andere Branchen untersuchen und den visuellen Elementen sogar Kunden hinzufügen, um nach Gründen für die Leistung von Valery zu suchen.

Dies ist eine Umgebung, in der Sie sicher experimentieren können. Sie können sich immer noch entscheiden, Ihre Änderungen nicht zu speichern. Wenn Sie sie speichern, können Sie immer wieder zu **Daten abrufen** zurückkehren, um ein neues Exemplar dieses Beispiels herunterzuladen.

## <a name="next-steps-connect-to-your-data"></a>Nächste Schritte: Herstellen der Verbindung mit Ihren Daten
Wir hoffen, diese Tour hat Ihnen gezeigt, wie Power BI-Dashboards, Q&A und Berichte Ihnen Einblicke in Kundendaten geben können. Es ist jetzt an Ihnen – stellen Sie Verbindungen mit Ihren eigenen Daten her. Mit Power BI können Sie Verbindungen zu einer Vielzahl von Datenquellen herstellen. Weitere Informationen zum [Einstieg in Power BI](service-get-started.md).

[Zurück zu den Beispielen in Power BI](sample-datasets.md)  

