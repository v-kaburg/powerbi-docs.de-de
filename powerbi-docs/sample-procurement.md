---
title: 'Beispiel zur Beschaffungsanalyse: Tour'
description: "Analysebeispiel für Beschaffung für Power BI: Tour"
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
ms.date: 12/04/2017
ms.author: mihart
ms.openlocfilehash: 957e7c05907f1fc75eddeb271c664f898203e591
ms.sourcegitcommit: 7248b5e449b2495d6baef385470d18edfacec457
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/08/2017
---
# <a name="procurement-analysis-sample-for-power-bi-take-a-tour"></a>Analysebeispiel für Beschaffung für Power BI: Tour
Dieses branchenspezifische Beispiel-Dashboard und der zugrunde liegende Bericht analysieren die Ausgaben eines Fertigungsunternehmens nach Kategorie und Standort. In diesem Beispiel untersuchen wir die folgenden Bereiche:

* Wer sind die Top-Lieferanten?
* Für welche Kategorien haben wir am meisten ausgegeben?
* Welche Lieferanten geben uns den größten Rabatt und wann?

Dieses Beispiel ist Teil einer Reihe, die Ihnen die Verwendung von Power BI anhand geschäftsbezogener Daten, Berichte und Dashboards veranschaulicht. Hierbei handelt es sich um echte Daten von obviEnce ([www.obvience.com](http://www.obvience.com/)) in anonymisierter Form.

![](media/sample-procurement/procurement1.png)

Führen Sie hierzu die folgenden Schritte aus: Navigieren Sie im [Power BI-Dienst](https://powerbi.com) zu **Daten abrufen > Beispiele > Analysebeispiel für Beschaffung > Verbinden**, um ihr eigenes Exemplar des Beispiels abzurufen.

[!Note] Alternativ können Sie [nur das Dataset (Excel-Arbeitsmappe) für dieses Beispiel herunterladen](http://go.microsoft.com/fwlink/?LinkId=529784). Die Arbeitsmappe enthält Power View-Blätter, die Sie anzeigen und ändern können. Wenn Sie die Rohdaten anzeigen möchten, wählen Sie **Power Pivot > Verwalten** aus.

## <a name="spending-trends"></a>Ausgabentrends
Zuerst sehen wir uns Trends bei den Ausgaben nach Kategorie und Standort an.  

1. Öffnen Sie in Ihrem Arbeitsbereich die Registerkarte **Dashboards**, und wählen Sie das Dashboard „Beschaffungsanalyse“ aus.
2. Wählen Sie die Dashboardkachel **Gesamtrechnung nach Land/Region**. Die Seite „Ausgabenübersicht“ des Berichts „Analysebeispiel für Beschaffung“ wird geöffnet.
   
    ![](media/sample-procurement/procurement2.png)

Beachten Sie die folgenden Punkte:

* Im Liniendiagramm **Gesamtrechnung nach Monat und Kategorie** : Die Ausgaben sind für die Kategorie **Direkt** relativ konstant, **Logistik** weist eine Spitze im Dezember auf, und **Sonstige** weist eine Spitze im Februar auf.
* In der Karte **Gesamtrechnung nach Land/Region** : Die meisten Ausgaben fallen in den USA an.
* Im Säulendiagramm **Gesamtrechnung nach Unterkategorie**: **Hardware** und **Indirekte Waren und Dienstleistungen** sind die Kategorien mit den höchsten Ausgaben.
* Im Balkendiagramm „Gesamtrechnung nach Ebene“: Der meiste Geschäftsverkehr wird mit Lieferanten der Ebene 1 (Top 10) abgewickelt. Dies ist für eine bessere Verwaltung der Lieferantenbeziehungen hilfreich.

## <a name="spending-in-mexico"></a>Ausgaben in Mexiko
Sehen wir uns die Ausgabenbereiche für Mexiko an:

1. Wählen Sie im Kreisdiagramm die Blase **Mexiko** aus. Sie sehen, dass im Säulendiagramm „Gesamtrechnung nach Unterkategorie“ der größte Teil in der Unterkategorie **Indirekte Waren und Dienstleistungen** anfällt.
   
   ![](media/sample-procurement/pbi_procsample_spendmexico.png)
2. Führen Sie einen Drilldown in die Spalte **Indirekte Waren und Dienstleistungen** aus:
   
   * Wählen Sie in der oberen rechten Ecke des Diagramms den Drilldownpfeil ![](media/sample-procurement/pbi_drilldown_icon.png) aus.
   * Wählen Sie die Spalte **Indirekte Waren und Dienstleistungen** aus.
     
      Der bei weitem größte Ausgabenposten in dieser Kategoriezusammenfassung ist Vertrieb und Marketing.
   * Wählen Sie in der Karte erneut **Mexiko** aus.
     
      Der größte Ausgabenposten in Mexiko ist Wartung und Reparatur.
     
      ![](media/sample-procurement/pbi_procsample_drill_mexico.png)
3. Wählen Sie den Aufwärtspfeil in der oberen linken Ecke des Diagramms aus, um wieder eine Ebene nach oben zu wechseln.
4. Wählen Sie den Pfeil erneut aus, um den Drilldown zu deaktivieren.  
5. Wählen Sie in der oberen Navigationsleiste **Power BI** aus, um zu Ihrem Arbeitsbereich zurückzukehren.

## <a name="evaluate-different-cities"></a>Auswerten verschiedener Städte
Wir können Hervorhebung verwenden, um verschiedene Städte auszuwerten.

1. Wählen Sie die Dashboardkachel **Gesamtrechnung, Rabatt in % nach Monat**aus. Der Bericht wird auf der Seite „Rabattanalyse“ geöffnet.
2. Wählen Sie die verschiedenen Städte in der Treemap **Gesamtumsatz nach Stadt** aus, um den Vergleich anzuzeigen. Fast alle Rechnungen in Miami beziehen sich auf Lieferanten der Ebene 1.
   
   ![](media/sample-procurement/pbi_procsample_miamitreemap2.png)

## <a name="vendor-discounts"></a>Lieferantenrabatte
Wir sehen uns auch die Rabatte an, die von Lieferanten angeboten werden, und die Zeiträume, in denen wir die meisten Rabatte erhalten. 

![](media/sample-procurement/procurement4.png)

Insbesondere interessieren folgende Fragen:

* Unterscheiden sich Rabatte von Monat zu Monat, oder werden in jedem Monat die gleichen Rabatte gewährt?
* Werden in einigen Städten höhere Rabatte als in anderen eingeräumt?

### <a name="discount-by-month"></a>Rabatt nach Monat
Wenn wir uns das Kombinationsdiagramm **Gesamtrechnung und Rabatt in % nach Monat** ansehen, wird deutlich, dass **Februar** der Monat mit dem höchsten Wert und **September** der Monat mit dem geringsten Aufkommen ist. Jetzt sehen wir uns die Prozentwerte der Rabatte in diesen Monaten an.
Sie sehen, dass sich der Rabatt verringert, wenn das Volumen ansteigt, und dass sich der Rabatt erhöht, wenn das Volumen sinkt. Je mehr wir den Rabatt benötigen, desto schlechter wird das Angebot.

![](media/sample-procurement/procurement5.png)

### <a name="discount-by-city"></a>Rabatt nach Stadt
Wir können uns auch den Rabatt nach Stadt ansehen. Wählen Sie im Treemap-Diagramm die einzelnen Städte aus. Sie sehen dann, wie sich die anderen Diagramme ändern. 

* Für St. Louis, MO gab es bei der Gesamtrechnung im Februar eine große Spitze und einen Einbruch bei den Einsparungen durch Rabatte im April.
* Mexico City, Mexico verfügt über den höchsten Rabatt in Prozent (11,05 %), und Atlanta, GA über den niedrigsten Rabatt in Prozent (0,08 %).

![](media/sample-procurement/procurement6.png)

### <a name="edit-the-report"></a>Bearbeiten des Berichts
Wählen Sie in der oberen linken Ecke **Bericht bearbeiten** aus, und führen Sie die Untersuchung in der Bearbeitungsansicht fort.

* Sehen Sie sich an, wie die Seiten aufgebaut sind.
* Fügen Sie auf der Grundlage der gleichen Daten Seiten und Diagramme hinzu.
* Ändern Sie die Visualisierung für ein Diagramm, indem Sie beispielsweise das Treemap-Diagramm in ein Ringdiagramm ändern.
* Heften Sie sie an Ihr Dashboard an.

Dies ist eine Umgebung, in der Sie sicher experimentieren können. Sie können sich immer noch entscheiden, Ihre Änderungen nicht zu speichern. Wenn Sie sie speichern, können Sie immer wieder zu **Daten abrufen** zurückkehren, um ein neues Exemplar dieses Beispiels herunterzuladen.

## <a name="next-steps-connect-to-your-data"></a>Nächste Schritte: Herstellen der Verbindung mit Ihren Daten
Wir hoffen, diese Tour hat Ihnen gezeigt, wie Power BI-Dashboards und -Berichte Ihnen Einblicke in Beschaffungsdaten geben können. Es ist jetzt an Ihnen – stellen Sie Verbindungen mit Ihren eigenen Daten her. Mit Power BI können Sie Verbindungen zu einer Vielzahl von Datenquellen herstellen. Weitere Informationen zum [Einstieg in Power BI](service-get-started.md).

