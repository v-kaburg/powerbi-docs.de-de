---
title: "Verwenden von Schnellmeasures zur einfachen Durchführung gängiger und aufwendiger Berechnungen in Power BI (Vorschau)"
description: "Schnellmeasures bieten vorgefertigte DAX-Formeln zur schnellen Durchführung gängiger Berechnungen."
services: powerbi
documentationcenter: 
author: davidiseminger
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
ms.date: 01/24/2018
ms.author: davidi
ms.openlocfilehash: d0fc21c19a574f096c46c26331df3114e8c46c31
ms.sourcegitcommit: 7249ff35c73adc2d25f2e12bc0147afa1f31c232
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/25/2018
---
# <a name="use-quick-measures-to-easily-perform-common-and-powerful-calculations-preview"></a>Verwenden von Schnellmeasures zur einfachen Durchführung gängiger und aufwendiger Berechnungen (Vorschau)
Ab der **Power BI Desktop**-Version vom April 2017 können Sie mithilfe von **Schnellmeasures** schnell und einfach gängige, aufwendige Berechnungen durchführen. Ein **Schnellmeasure** führt für eine Eingabe, die Sie in einem Dialogfeld vornehmen, im Hintergrund eine Reihe von (vorgefertigten) DAX-Befehlen aus und liefert Ergebnisse, die Sie dann in Ihrem Bericht verwenden können. Und das Beste: Sie können sich ansehen, welche DAX-Befehle das Schnellmeasure ausführt, und sich so besser mit DAX vertraut machen.

![](media/desktop-quick-measures/quick-measures_01.png)

Klicken Sie zum Erstellen von **Schnellmeasures** im Bereich **Felder** mit der rechten Maustaste auf ein Feld, und wählen Sie im daraufhin angezeigten Menü die Option **Schnellmeasures** aus. Alternativ können Sie auch im Bereich **Werte** eines bereits vorhandenen visuellen Elements mit der rechten Maustaste auf einen beliebigen Wert klicken (etwa auf das Feld *Werte* in einem *Balkendiagramm*). Es stehen zahlreiche Berechnungskategorien und Bearbeitungsmöglichkeiten zur Verfügung, mit denen Sie die Berechnungen an Ihre jeweiligen Anforderungen anpassen können.

### <a name="enable-the-quick-measures-preview"></a>Aktivieren von Schnellmeasures (Vorschau)
Das neue Feature **Schnellmeasures** steht ab der **Power BI Desktop**-Version vom **April 2017** zur Verfügung. Wenn Sie dieses Vorschaufeature aktivieren möchten, wählen Sie **Datei > Optionen und Einstellungen > Optionen > Vorschaufeatures** aus, und aktivieren Sie dann das Kontrollkästchen neben **Schnellmeasures**. Sie müssen Power BI Desktop neu starten, nachdem Sie die Auswahl vorgenommen haben.

![](media/desktop-quick-measures/quick-measures_02b.png)

Sie müssen **Power BI Desktop** neu starten, nachdem Sie die Auswahl vorgenommen haben.

## <a name="using-quick-measures"></a>Verwenden von Schnellmeasures
Klicken Sie zum Erstellen eines **Schnellmeasures** in **Power BI Desktop** im Bereich **Felder** mit der rechten Maustaste auf ein beliebiges Feld, und wählen Sie im daraufhin angezeigten Menü die Option **Schnellmeasures** aus.

![](media/desktop-quick-measures/quick-measures_01.png)

Das Feature **Quickmeasures** ist nur verfügbar, wenn das geladene Dataset modellierbar ist. Daher wird bei Liveverbindungen (etwa bei einer Verbindung mit einem Dataset des Power BI-Diensts) das Menüelement **Quickmeasures** nicht angezeigt, wenn Sie mit der rechten Maustaste auf die Liste **Felder** klicken. Diese Einschränkung gilt nicht für SSAS-Liveverbindungen. 

Bei Verwendung von SSAS-Liveverbindungen (SQL Server Analysis Services) sind einige **Quickmeasures** verfügbar. In **Power BI Desktop** wird nur die Sammlung der **Quickmeasures** angezeigt, die für die Version von SSAS unterstützt werden, mit der die Verbindung hergestellt wird. Wenn eine Verbindung mit einer SSAS-Livedatenquelle besteht und bestimmte **Quickmeasures** nicht in der Liste enthalten sind, unterstützt die SSAS-Version, mit der die Verbindung besteht, nicht das DAX-Measure, mit dem das betreffende **Quickmeasure** implementiert wurde.

Nach Auswahl der Option im Kontextmenü erscheint das Fenster **Schnellmeasures**. Hier können Sie die gewünschte Berechnung sowie die Felder auswählen, für die die Berechnung erfolgen soll.

![](media/desktop-quick-measures/quick-measures_03.png)

Wenn Sie das Dropdownmenü auswählen, erhalten Sie eine lange Liste mit verfügbaren **Schnellmeasures**.

![](media/desktop-quick-measures/quick-measures_04.png)

Die Schnellmeasure-Berechnungstypen sind in fünf unterschiedliche Gruppen unterteilt, die jeweils eine Reihe von Berechnungen umfassen. Folgende Gruppen und Berechnungen stehen zur Verfügung:

* **Innerhalb der Kategorie aggregieren**
  * Durchschnitt innerhalb der Kategorie
  * Varianz innerhalb der Kategorie
  * Höchstwert innerhalb der Kategorie
  * Mindestwert innerhalb der Kategorie
  * Gewichteter Durchschnitt pro Kategorie
* **Filter und Baselines**
  * Gefiltertes Measure
  * Differenz zu Baseline
  * Differenz in Prozent zu Baseline
  * Summen aus neuen Kategorien
* **Zeitinformationen**
  * Summe seit Jahresanfang
  * Summe seit Quartalsanfang
  * Summe seit Monatsanfang
  * Änderung zwischen zwei Jahren
  * Änderung zwischen zwei Quartalen
  * Änderung zwischen zwei Monaten
  * Gleitender Durchschnitt
* **Gesamtergebnisse**
  * Laufende Summe
  * Gesamtsumme für die Kategorie (Filter angewendet)
  * Gesamtsumme für die Kategorie (Filter nicht angewendet)
* **Mathematische Operationen**
  * Addition
  * Subtraktion
  * Multiplikation
  * Division
  * Prozentualer Unterschied
* **Text**
  * Bewertungssterne
  * Verkettete Werteliste

Diese Berechnungen werden voraussichtlich noch ergänzt. Daher würden wir gerne von Ihnen erfahren, welche **Schnellmeasures** Sie sich wünschen und ob Sie Vorschläge (einschließlich zugrunde liegender DAX-Formeln) für **Schnellmeasures** haben. Weitere Informationen hierzu finden Sie am Ende dieses Artikels.

## <a name="example-of-quick-measures"></a>Beispiel für Schnellmeasures
In diesem Abschnitt sehen wir uns ein Beispiel dieser **Schnellmeasures** in Aktion an.

Die folgende **Matrix** zeigt eine Verkaufstabelle für verschiedene Elektronikprodukte. Hierbei handelt es sich um eine einfache Tabelle mit der Summe der einzelnen Kategorien.

![](media/desktop-quick-measures/quick-measures_05.png)

Wenn wir mit der rechten Maustaste auf den Feldbereich **Werte** klicken und **Schnellmeasures** auswählen, können wir als *Berechnung* die Option *Durchschnitt innerhalb der Kategorie* und als *Basiswert* die Option *Summe von SalesAmount* auswählen. Anschließend können wir *SalesAmount* angeben, indem wir das entsprechende Feld aus dem Bereich *Felder* (rechts) in den Bereich *Kategorie* (links) ziehen.

![](media/desktop-quick-measures/quick-measures_06.png)

Wenn wir nun **OK** auswählen, passieren einige interessante Dinge, wie in der Abbildung nach der folgenden Liste zu sehen:

1. Die **Matrix** enthält nun eine neue Spalte mit unserer Berechnung (in diesem Fall: *Durchschnitt innerhalb von „SalesAmount“*).
2. Ein neues **Measure** wurde erstellt. Es befindet sich im Bereich **Felder** und wird von Power BI durch ein gelbes Kästchen hervorgehoben. Dieses Measure steht für jedes andere visuelle Element im Bericht zur Verfügung (nicht nur für das visuelle Element, für das es ursprünglich erstellt wurde).
3. Die für das **Schnellmeasure** erstellte DAX-Formel wird auf der Bearbeitungsleiste angezeigt.

![](media/desktop-quick-measures/quick-measures_07.png)

Beachten Sie im Zusammenhang mit dem ersten Punkt, dass das **Schnellmeasure** auf das visuelle Element angewendet wurde. Es gibt eine neue Spalte und einen zugeordneten Wert. Beide basieren auf dem erstellten **Schnellmeasure**.

![](media/desktop-quick-measures/quick-measures_08.png)

Zweitens: Das **Schnellmeasure** wird im Bereich **Felder** des Datenmodells angezeigt und kann wie jedes andere Feld im Modell für ein beliebiges anderes visuelles Element verwendet werden. In der folgenden Abbildung wurde unter Verwendung des neuen Felds, das durch das **Schnellmeasure** erstellt wurde, ein **Balkendiagramm** erstellt.

![](media/desktop-quick-measures/quick-measures_09.png)

Im nächsten Abschnitt beschäftigen wir uns mit dem dritten Punkt: DAX-Formeln.

## <a name="learn-dax-using-quick-measures"></a>Kennenlernen von DAX anhand von Schnellmeasures
Ein weiterer Vorteil von **Schnellmeasures**: Das Feature zeigt Ihnen direkt die DAX-Formel, die zur Implementierung des Measures erstellt wurde. In der folgenden Abbildung haben wir das Measure ausgewählt, das durch das **Schnellmeasure** erstellt wurde. (Es befindet sich nun im Bereich **Felder**, sodass wir lediglich darauf klicken müssen.) Daraufhin wird die **Bearbeitungsleiste** mit der DAX-Formel angezeigt, die Power BI zur Implementierung des Measures erstellt hat.

![](media/desktop-quick-measures/quick-measures_10.png)

Das ist praktisch, denn so erfahren Sie, welche Formel dem Measure zugrunde liegt. Was aber vielleicht noch wichtiger ist: Sie können anhand von **Schnellmeasures** sehen, wie die zugrunde liegenden DAX-Formeln erstellt werden sollten.

Angenommen, Sie müssen eine Berechnung für einen Jahresvergleich durchführen, wissen aber nicht so recht, wie Sie die DAX-Formel strukturieren (oder wo Sie überhaupt anfangen) sollen. In diesem Fall können Sie ein **Schnellmeasure** mit der Berechnung **Änderung zwischen zwei Jahren** erstellen und sich den Vorgang ansehen. Gehen Sie dazu wie folgt vor: Erstellen Sie das **Schnellmeasure**, betrachten Sie die Darstellung in Ihrem visuellen Element, sehen Sie sich an, wie die DAX-Formel funktioniert, und ändern Sie dann entweder die DAX-Formel direkt, oder erstellen Sie ein weiteres Measure, bis die Berechnungen Ihren Anforderungen oder Erwartungen entsprechen.

Das ist fast so als hätten Sie einen Lehrer, der umgehend auf Ihre Was-wäre-wenn-Fragen reagiert – und das mit nur wenigen Mausklicks. Sie können diese Measures jederzeit aus Ihrem Modell löschen, wenn sie Ihnen nicht zusagen. Dazu müssen Sie lediglich mit der rechten Maustaste auf das Measure klicken und **Löschen** auswählen.

![](media/desktop-quick-measures/quick-measures_11.png)

Und wenn Sie das optimale Measure erstellt haben, können Sie es über das gleiche Kontextmenü mit einem beliebigen Namen versehen.

## <a name="limitations-and-considerations"></a>Einschränkungen und Überlegungen
Für die Vorschauversion des Features **Schnellmeasures** gelten einige Einschränkungen und Überlegungen:

* **Quickmeasures** sind nur verfügbar, wenn Sie das Modell ändern können. Das ist bei DirectQuery und den meisten Liveverbindungen nicht der Fall (SSAS-Liveverbindungen werden unterstützt, wie weiter oben erläutert).
* Das Measure, das dem Bereich **Felder** hinzugefügt wird, kann für ein beliebiges visuelles Element im Bericht verwendet werden.
* Sie können jederzeit die DAX-Formel anzeigen, die einem **Schnellmeasure** zugeordnet ist. Wählen Sie hierzu im Bereich **Felder** das erstellte Measure aus, und sehen Sie sich die Formel auf der **Bearbeitungsleiste** an.

> [!WARNING]
> Ein Schnellmeasure generiert derzeit *nur* DAX-Anweisungen mit Kommas als Argumenttrennzeichen. Wenn Ihre Version von **Power BI Desktop** für eine Sprache lokalisiert ist, in der Kommas als Dezimaltrennzeichen verwendet werden, können Quickmeasures nicht ordnungsgemäß funktionieren.
> 
> 

### <a name="time-intelligence-and-quick-measures"></a>Zeitintelligenz und Quickmeasures
Ab dem **Power BI Desktop**-Update von Oktober 2017 können Sie eigene benutzerdefinierte Datumstabellen mit Zeitintelligenz-**Quickmeasures** verwenden. Wenn das Datenmodell eine benutzerdefinierte Datumstabelle enthält, können Sie die primäre Datumsspalte in dieser Tabelle für Zeitintelligenz-Quickmeasures verwenden. Sie *müssen* sicherstellen, dass die primäre Datumsspalte in dieser Tabelle beim Erstellen des Modells als Datumstabelle markiert wurde, wie in [diesem Artikel](https://docs.microsoft.com/sql/analysis-services/tabular-models/specify-mark-as-date-table-for-use-with-time-intelligence-ssas-tabular) beschrieben.

### <a name="additional-information-and-examples"></a>Weitere Informationen und Beispiele
Dieser Schwerpunktartikel wird voraussichtlich noch mit Beispielen und Anleitungen für die einzelnen Berechnungen der **Schnellmeasures** aktualisiert. Schauen Sie daher bald wieder vorbei.

Da es sich hierbei um ein **Vorschaufeature** handelt, sind wir besonders an Ihrem Feedback und an Ihren Ideen interessiert.

Haben Sie eine Idee für ein noch nicht verfügbares **Schnellmeasure**? Sehr gut! Besuchen Sie [diese Seite](https://go.microsoft.com/fwlink/?linkid=842906), und reichen Sie Ihre Ideen (und DAX-Formeln) für das **Schnellmeasure** ein, das Sie sich für **Power BI Desktop** wünschen, damit wir es ggf. in einer späteren Version der Liste mit verfügbaren **Schnellmeasures** hinzufügen können.

