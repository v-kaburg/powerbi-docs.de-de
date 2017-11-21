---
title: Strukturieren und Kombinieren von Daten in Power BI Desktop
description: Strukturieren und Kombinieren von Daten in Power BI Desktop
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
ms.date: 09/06/2017
ms.author: davidi
ms.openlocfilehash: b222addc2e72308e94a3d8836c8e9039c7208bae
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2017
---
# <a name="shape-and-combine-data-in-power-bi-desktop"></a>Strukturieren und Kombinieren von Daten in Power BI Desktop
Mit **Power BI Desktop** können Sie Verbindungen zu vielen unterschiedlichen Arten von Datenquellen herstellen und anschließend die Daten nach Ihren Anforderungen strukturieren. Das *Strukturieren* von Daten ist mit einem Transformieren der Daten gleichzusetzen. So müssen beispielsweise Spalten oder Tabellen umbenannt, Text in Zahlen umgewandelt, Zeilen entfernt oder die erste Zeile als Überschrift festgelegt werden. Als *Kombinieren* von Daten werden das Verbinden von mehreren Datenquellen, das auf die Anforderungen ausgerichtete Strukturieren der Daten und schließlich das Konsolidieren in eine praktische Abfrage bezeichnet.

In diesem Dokument wird veranschaulicht, wie Sie eine Abfrage mit Power BI Desktop strukturieren. Besonders hervorgehoben werden einige der dabei am häufigsten auszuführenden Aufgaben. Die hier verwendete Abfrage (und auch der gesamte Erstellungsvorgang) ist im Handbuch [Erste Schritte mit Power BI-Desktop](desktop-getting-started.md) ausführlicher beschrieben.

Es ist wichtig zu wissen, dass im **Abfrage-Editor** von Power BI Desktop neben den im Menüband verfügbaren Optionen häufig Kontextmenüs (Rechtsklick) zum Einsatz kommen. Die meisten Optionen, die im Menüband **Transformieren** zur Auswahl stehen, können auch über Klicken auf ein Element (z. B. eine Spalte) mit der rechten Maustaste und Auswählen aus dem Kontextmenü aufgerufen werden.

## <a name="shape-data"></a>Strukturieren von Daten
Wenn Sie im Abfrage-Editor Daten strukturieren, geben Sie schrittweise Anweisungen vor (die der Abfrage-Editor dann für Sie ausführt), um die Daten beim Laden und Darstellen im Abfrage-Editor anzupassen. Die ursprüngliche Datenquelle wird davon nicht berührt. Angepasst bzw. *strukturiert* wird nur diese spezifische Ansicht der Daten.

Die Schritte, die Sie angeben (z. B. Umbenennen einer Tabelle, Transformieren eines Datentyps oder Löschen von Spalten), werden vom Abfrage-Editor aufgezeichnet und bei jeder Verbindung zu dieser Datenquelle ausgeführt, sodass die Daten stets in der gewünschten Art "strukturiert" sind. Dieser Vorgang erfolgt jedes Mal, wenn Sie den Abfrage-Editor in Power BI Desktop verwenden, aber auch jedes Mal, wenn jemand auf die freigegebene Abfrage zugreift, z. B. im **Power BI**-Dienst. Diese Schritte werden der Reihe nach im Bereich **Abfrageeinstellungen** unter **Angewendete Schritte** aufgezeichnet.

Die folgende Abbildung zeigt den Bereich **Abfrageeinstellungen** für eine strukturierte Abfrage. In den nächsten Abschnitten werden die Schritte im Einzelnen erläutert.

![](media/desktop-shape-and-combine-data/shapecombine_querysettingsfinished.png)

Wir verwenden wieder die Daten zu den bevorzugten Wohnorten für Pensionäre aus dem Handbuch [Erste Schritte mit Power BI Desktop](https://powerbi.uservoice.com/knowledgebase/articles/471664), die wir über die Verbindung mit einer Webdatenquelle gefunden haben. Wir werden die Daten so strukturieren, dass sie unseren Anforderungen entsprechen.

Zunächst sehen wir, dass die Werte in einer Spalte beim Laden der Tabelle vom Abfrage-Editor nicht automatisch von Text in Zahlen transformiert wurden. Wir benötigen aber Zahlen. Kein Problem: Klicken Sie einfach mit der rechten Maustaste auf die Spaltenüberschrift, und wählen Sie **Typ ändern \> Ganze Zahl** aus, um die Werte zu ändern. Um mehr als eine Spalte auszuwählen, wählen Sie zuerst eine Spalte aus, drücken Sie die **UMSCHALTTASTE**, und wählen Sie dann mit gedrückter Taste weitere angrenzende Spalten aus. Klicken Sie anschließend mit der rechten Maustaste auf eine Spaltenüberschrift, um alle ausgewählten Spalten zu ändern. Sie können auch die **STRG-TASTE** verwenden, um nicht angrenzende Spalten auszuwählen.

![](media/desktop-shape-and-combine-data/shapecombine_changetype.png)

Sie können im Menüband **Transformieren** auch Spalten von Text in Überschriften *transformieren*. Die Abbildung zeigt das Menüband **Transformieren**. Der Pfeil weist auf die Schaltfläche **Datentyp**, mit der Sie den aktuellen Datentyp in einen anderen Typ transformieren können.

![](media/desktop-shape-and-combine-data/queryoverview_transformribbonarrow.png)

Im Bereich **Abfrageeinstellungen** sehen Sie, dass unter **Angewendete Schritte** alle Schritte zum Strukturieren der Daten aufgeführt sind. Wenn Sie einen Schritt aus dem Strukturierungsprozess entfernen möchten, wählen Sie einfach das **X** links neben dem jeweiligen Schritt aus. In der folgenden Abbildung werden unter **Angewendete Schritte** die bisher ausgeführten Schritte aufgelistet: Herstellen einer Verbindung zur Website (**Quelle**), Auswahl der Tabelle (**Navigation**) und die automatische Konvertierung von textbasierten Zahlenspalten von *Text* in *Ganze Zahl* (**Geänderter Typ**) durch den Abfrage-Editor beim Laden der Tabelle. Eine Spalte mit Bewertungen wurde jedoch nicht automatisch in einen zahlenbasierten Typ geändert. Warum das so ist, werden wir in den nächsten Abschnitten feststellen.

![](media/desktop-shape-and-combine-data/shapecombine_appliedstepsearly.png)

Bevor wir mit dieser Abfrage arbeiten können, müssen wir ein paar Änderungen vornehmen, um die Daten nach unseren Anforderungen zu ordnen:

* *Entfernen der ersten Spalte:* Diese Spalte brauchen wir nicht. Sie enthält nur überflüssige Zeilen mit dem Text „Check out how your state ranks for retirement“, ein Artefakt aufgrund der Tatsache, dass es sich bei dieser Datenquelle um eine webbasierte Tabelle handelt.
* *Beheben von Fehlern:* In einer Spalte, **Health care quality** gibt es bei den Bewertungen der Bundesstaaten einige Male einen Gleichstand. Auf der Website waren diese mit dem Text *(tie)* nach den Zahlen versehen. Das funktioniert gut auf der Website, stellt uns aber vor die Aufgabe, diese Spalte manuell von Text in Daten konvertieren zu müssen. Dieses Problem ist in Power BI Desktop ganz einfach zu beheben und veranschaulicht ein nützliches Feature der Abfrage im Bereich **Angewendete Schritte**.
* *Ändern des Tabellennamens:* **Table 0** ist kein sinnvoller Deskriptor, er kann aber sehr einfach geändert werden.

Um die erste Spalte zu entfernen, wählen Sie zuerst die Spalte und dann im Menüband die Registerkarte **Start** aus. Klicken Sie anschließend auf **Spalten entfernen**, wie in der folgenden Abbildung gezeigt.

![](media/desktop-shape-and-combine-data/shapecombine_removecolumnsretirement.png)

Als Nächstes nehmen wir uns die Textspalte vor und transformieren sie in Zahlen. Zunächst erscheint es ganz einfach, den Typ der Spalte **Health care quality** von Text in Zahlen (z. B. *Ganze Zahl* oder *Dezimalzahl*) zu ändern. Wenn wir jedoch den Typ von **Text** in **Ganze Zahl** ändern und dann die Werte in dieser Spalte betrachten, stellen wir fest, dass die Abfrage Fehler meldet.

![](media/desktop-shape-and-combine-data/shapecombine_error.png)

Es gibt verschiedene Möglichkeiten, weitere Informationen zu den einzelnen Fehlern zu erhalten. Sie können entweder die Zelle auswählen (ohne auf das Wort **Fehler**zu klicken) oder direkt auf das Wort **Fehler** klicken. Wenn Sie die Zelle *ohne* Klicken auf das Wort **Fehler**auswählen, zeigt der Abfrage-Editor die Fehlerinformationen unten im Fenster an.

![](media/desktop-shape-and-combine-data/shapecombine_errorinfo.png)

Wenn Sie direkt auf das Wort *Fehler* klicken, erstellt die Abfrage im Bereich **Abfrageeinstellungen** unter **Angewendete Schritte** einen weiteren Schritt und zeigt die Informationen zu dem Fehler an.

![](media/desktop-shape-and-combine-data/shapecombine_errorselect.png)

Um wieder zur Abfrage zu gelangen, müssen Sie diesen Schritt entfernen, indem Sie auf das zugehörige **X** klicken.

Wenn Sie unter **Angewendete Schritte**den letzten Schritt auswählen, wird der eben beschriebene Fehler angezeigt, wie aus der folgenden Abbildung hervorgeht.

![](media/desktop-shape-and-combine-data/shapecombine_querystep1.png)

Da die Abfrage die Schritte nacheinander aufzeichnet, können wir unter **Angewendete Schritte**den Schritt vor der Typänderung auswählen und den Wert dieser Zelle vor der Transformation anzeigen (siehe Abbildung).

![](media/desktop-shape-and-combine-data/shapecombine_querystep2.png)

Nun können wir diese Werte korrigieren und *danach* den Typ ändern. Der Abfrage-Editor zeichnet die Schritte zwar nacheinander, aber unabhängig voneinander auf. Daher können Sie unter **Angewendete Schritte** die Schritte in der Reihenfolge nach oben oder unten verschieben. Klicken Sie einfach mit der rechten Maustaste auf einen Schritt, und der Abfrage-Editor stellt ein Kontextmenü mit folgenden Optionen bereit: **Umbenennen**, **Löschen**, **Bis zum** **Ende löschen** (entfernt den aktuellen und alle nachfolgenden Schritte) **Nach oben** oder **Nach unten**.

![](media/desktop-shape-and-combine-data/shapecombine_querystepreorder.png)

Außerdem können Sie unter **Angewendete Schritte** einen beliebigen Schritt in der Liste auswählen und die Strukturierung der Daten an diesem Punkt der Reihenfolge fortsetzen. Der Abfrage-Editor fügt unter **Angewendete Schritte**nach dem aktuell ausgewählten Schritt automatisch einen neuen Schritt ein. Probieren wir es aus.

Zunächst wählen wir unter **Angewendete Schritte** den Schritt vor der Änderung des Typs der Spalte **Health care quality** aus. Dann ersetzten wir die Werte, die in der Zelle mit dem Text "(tie)" versehen sind so, dass nur noch die Zahlen erhalten bleiben. Klicken Sie mit der rechten Maustaste auf die Zelle mit dem Inhalt "35 (tie)", und wählen Sie *Werte ersetzen...* im angezeigten Kontextmenü aus. Achten Sie darauf, welcher Schritt unter **Angewendete Schritte** aktuell ausgewählt ist (der Schritt vor der Typänderung).

![](media/desktop-shape-and-combine-data/shapecombine_replacevalues.png)

Da wir einen Schritt einfügen, warnt uns der Abfrage-Editor vor möglichen Konsequenzen - die nachfolgenden Schritte könnten u.U. beeinträchtigt und die Abfrage unbrauchbar werden. Wir müssen sorgfältig und mit Bedacht vorgehen! Da dies ein Tutorial ist und wir ein wirklich nützliches Feature der Abfrage zum Erstellen, Löschen, Einfügen und Neuordnen von Schritten veranschaulichen möchten, fahren wir fort und wählen **Einfügen** aus.

![](media/desktop-shape-and-combine-data/shapecombine_insertstep.png)

Dreimal ist eine Zahl mit dem Text "(tie)" versehen. Daher ersetzen wir alle drei Werte. Wenn Sie einen neuen angewendeten Schritt erstellen, benennt ihn der Abfrage-Editor nach der jeweiligen Aktion, in diesem Fall **Ersetzter Wert**. Wenn die Abfrage mehrere Schritte gleichen Namens enthält, versieht der Abfrage-Editor unter **Angewendete Schritte** jeden Folgeschritt zur Unterscheidung mit einer Nummer in der entsprechenden Reihenfolge.

In der folgenden Abbildung sehen Sie in den **Abfrageeinstellungen** die drei Schritte **Ersetzter Wert**, aber noch etwas viel Interessanteres: Da wir alle Instanzen des Texts "(tie)" aus der Spalte **Health care quality** entfernt haben, wird der Schritt **Geänderter Typ** jetzt *ohne Fehler* ausgeführt.

![](media/desktop-shape-and-combine-data/shapecombine_replacedvaluesok.png)

> [!NOTE]
> Sie können auch die Option **Fehler entfernen** (im Menüband oder Kontextmenü) verwenden, mit der fehlerhafte Zeilen entfernt werden. In diesem Fall würden damit alle Bundesstaaten aus den Daten entfernt, deren Zahlen mit dem Text *(tie)* versehen sind. Das möchten wir aber nicht, sondern wir möchten alle Bundesstaaten in der Tabelle behalten.

Zugegeben, das war jetzt ein bisschen kompliziert, aber ein gutes Beispiel für die leistungsfähigen und vielseitigen Abfragefunktionen.

Zum Schluss möchten wir noch den Namen der Tabelle in einen aussagekräftigeren Namen ändern. Bei der späteren Erstellung von Berichten sind aussagekräftige Tabellennamen besonders wichtig, gerade wenn Sie Verbindungen zu mehreren Datenquellen herstellen und alle im Bereich **Felder** der **Berichtsansicht** aufgelistet sind.

Das Ändern des Tabellennamen ist einfach: Geben Sie im Bereich **Abfrageeinstellungen** unter **Eigenschaften**einfach den neuen Namen der Tabelle ein (siehe Abbildung), und drücken Sie dann die **EINGABETASTE**. Wir nennen diese Tabelle *RetirementStats*.

![](media/desktop-shape-and-combine-data/shapecombine_renametable.png)

Die Daten sind nun soweit strukturiert, dass sie unseren Anforderungen entsprechen. Jetzt stellen wir eine Verbindung zu einer anderen Datenquelle her und kombinieren die Daten.

## <a name="combine-data"></a>Kombinieren von Daten
Diese Daten von verschiedenen Bundesstaaten sind interessant und nützlich zur Erstellung weiterer Analysen und Abfragen. Es gibt allerdings ein Problem: Bei den meisten Daten wird ein zweistelliges Länderkürzel als Code für den Bundesstaat und nicht dessen voller Name verwendet. Wir müssen die Namen der Bundesstaaten in irgendeiner Weise mit den Kürzeln verknüpfen.

Glücklicherweise gibt es eine andere öffentliche Datenquelle, die genau das bereitstellt. Die Daten müssen jedoch noch entsprechend strukturiert werden, bevor wir sie mit unserer Tabelle mit bevorzugten Wohnorten für Pensionäre verbinden können. Hier befindet sich die Webressource mit den Länderkürzeln:

<http://en.wikipedia.org/wiki/List_of_U.S._state_abbreviations>

Wählen Sie im Abfrage-Editor im Menüband auf der Registerkarte **Start** die Optionen **Neue Quelle \> Web** aus. Geben Sie die Adresse ein, und klicken Sie auf „OK“. Im Navigator werden die Ergebnisse von dieser Webseite angezeigt.

 ![](media/desktop-shape-and-combine-data/designer_gsg_usstateabbreviationsnavigator.png)

Wählen Sie **Table[edit]** aus, da diese Tabelle die gewünschten Daten enthält. Sie muss aber noch strukturiert werden, damit diese Tabelle nur noch die gewünschten Daten enthält.

> [!TIP]
> Gibt es einen schnelleren oder einfacheren Weg, die nachstehenden Schritte auszuführen? Ja, Sie könnten eine *Beziehung* zwischen den beiden Tabellen erstellen und die Daten basierend auf dieser Beziehung strukturieren. Die folgenden Schritte sind immer noch hilfreich beim Lernen der Arbeit mit Tabellen. Nehmen Sie jedoch zur Kenntnis, dass Beziehungen dabei helfen können, Daten aus mehreren Tabellen schnell zu verwenden.
> 
> 

Befolgen Sie die folgenden Schritte, um diese Daten zu strukturieren:

* Entfernen Sie die beiden oberen Zeilen. Sie sind auf die Erstellungsweise der Webseitentabelle zurückzuführen und werden nicht gebraucht. Wählen Sie im Menüband auf der Registerkarte **Start** die Optionen **Zeilen verringern \> Zeilen entfernen \> Erste Zeilen entfernen** aus.

![](media/desktop-shape-and-combine-data/shapecombine_removetoprows.png)

Das Fenster **Erste Zeilen entfernen** wird angezeigt, in dem Sie angeben können, wie viele Zeilen Sie entfernen möchten.

* Entfernen Sie die letzten 26 Zeilen. Hierbei handelt es sich um Gebiete, die wir nicht brauchen. Wählen Sie im Menüband auf der Registerkarte **Start** die Optionen **Zeilen verringern \> Zeilen entfernen \> Letzte Zeilen entfernen** aus.

![](media/desktop-shape-and-combine-data/shapecombine_removebottomrows.png)

* Da die Tabelle „RetirementStats“ keine Informationen für Washington, D.C., enthält, müssen wir Washington, D.C., aus der Liste herausfiltern. Wählen Sie den Dropdownpfeil neben der Spalte „Region Status“ aus, und deaktivieren Sie das Kontrollkästchen neben **Federal District**.

![](media/desktop-shape-and-combine-data/shapecombine_filterdc.png)

* Entfernen Sie ein paar überflüssige Spalten. Wir benötigen nur die Zuordnung der Bundesstaaten zu den offiziellen zweistelligen Länderkürzeln. Daher können wir die folgenden Spalten entfernen: **Column2**, **Column3** sowie **Column5** bis **Column10**. Wählen Sie zuerst **Column2** aus, und wählen Sie dann mit gedrückter STRG-TASTE die übrigen zu entfernenden Spalten aus (mit STRG können Sie mehrere, nicht angrenzende Spalten auswählen). Wählen Sie im Menüband auf der Registerkarte „Start“ die Optionen **Spalten entfernen \> Spalten entfernen** aus.

![](media/desktop-shape-and-combine-data/shapecombine_removecolumns.png)

* Verwenden Sie die erste Zeile als Überschrift. Da wir die oberen drei Zeilen entfernt haben, ist die aktuelle oberste Zeile die benötigte Überschrift. Sie können **Erste Zeile als Überschriften verwenden** im Menüband entweder auf der Registerkarte **Start** oder auf der Registerkarte **Transformieren** auswählen.

![](media/desktop-shape-and-combine-data/shapecombine_usefirstrowasheaders.png)

    >[!NOTE]
    >This is a good time to point out that the *sequence* of applied steps in Query Editor is important, and can affect how the data is shaped. It’s also important to consider how one step may impact another subsequent step; if you remove a step from the Applied Steps, subsequent steps may not behave as originally intended, because of the impact of the query’s sequence of steps.

    >[!NOTE]
    >When you resize the Query Editor window to make the width smaller, some ribbon items are condensed to make the best use of visible space. When you increase the width of the Query Editor window, the ribbon items expand to make the most use of the increased ribbon area.

* Benennen Sie die Spalten und die eigentliche Tabelle um. Wie üblich gibt es mehrere Möglichkeiten, eine Spalte umzubenennen: Wählen Sie zuerst die Spalte und dann im Menüband auf der Registerkarte **Transformieren** die Option **Umbenennen** aus, oder klicken Sie mit der rechten Maustaste, und wählen Sie im Kontextmenü die Option **Umbenennen** aus. In der folgenden Abbildung weisen Pfeile auf diese beiden Optionen; sie brauchen nur eine davon auszuwählen.

![](media/desktop-shape-and-combine-data/shapecombine_rename.png)

Wir benennen die Spalten in *State Name* und *State Code* um. Um die Tabelle umzubenennen, geben Sie im Bereich **Abfrageeinstellungen** den Namen einfach im Feld **Name** ein. Diese Tabelle nennen wir *StateCodes*.

Nachdem wir nun die Tabelle „StateCodes“ wie gewünscht strukturiert haben, können wir die beiden Tabellen bzw. Abfragen kombinieren. Da die Tabellen, die wir jetzt haben, die Ergebnisse der Abfragen sind, die wir auf die Daten angewendet haben, werden sie häufig auch als *Abfragen* bezeichnet.

Zum Kombinieren von Daten gibt zwei bevorzugte Möglichkeiten: *Zusammenführen* und *Anhängen*.

Wenn eine oder mehrere Spalten zu einer anderen Abfrage hinzugefügt werden sollen, werden die Abfragen **zusammengeführt** . Wenn einer vorhandenen Abfrage zusätzliche Datenzeilen hinzugefügt werden sollen, wird die Abfrage **angehangen** .

Im vorliegenden Fall werden wir die Abfragen zusammenführen. Wählen Sie zunächst im linken Bereich des Abfrage-Editors die Abfrage aus, *mit der* die andere Abfrage zusammengeführt werden soll, in diesem Fall *RetirementStats*. Anschließend wählen Sie im Menüband auf der Registerkarte **Start\> die** Optionen Kombinieren **Abfragen** zusammenführen aus.

![](media/desktop-shape-and-combine-data/shapecombine_mergequeries.png)

Möglicherweise werden Sie aufgefordert, die Sicherheitsstufen festzulegen, um sicherzustellen, dass die Daten kombiniert werden, ohne Daten mit einzuschließen oder zu übertragen, die Sie nicht einschließen oder übertragen möchten.

![](media/desktop-shape-and-combine-data/shapecombine_mergequeriesb.png)

Im Fenster **Zusammenführen** werden Sie aufgefordert, die Tabelle auszuwählen, die mit der ausgewählten Tabelle zusammengeführt werden soll. Anschließend müssen Sie die Spalten angeben, die für die Zusammenführung verwendet werden sollen. Wählen Sie „State“ in der Tabelle (Abfrage) *RetirementStats* und dann die Abfrage *StateCodes* aus. (Das ist in diesem Fall recht einfach, da es nur eine andere Abfrage gibt. Wenn Sie Verbindungen zu vielen Datenquellen herstellen, stehen hier viele Abfragen zur Auswahl.) Wenn Sie die übereinstimmenden Spalten – **State** aus *RetirementStats* und **State Name** aus *StateCodes* – richtig auswählen, sieht das Fenster **Zusammenführen** wie folgt aus, und die Schaltfläche **OK** ist aktiviert.

![](media/desktop-shape-and-combine-data/shapecombine_merge.png)

Am Ende der Abfrage wird eine neue Spalte namens **NewColumn** erstellt, die den Inhalt der Tabelle (Abfrage) enthält, die mit der vorhandenen Abfrage zusammengeführt wurde. Alle Spalten der zusammengeführten Abfrage werden auf die neue Spalte **NewColumn** reduziert. Sie können jedoch die Tabelle **erweitern** und die gewünschten Spalten einbeziehen.

![](media/desktop-shape-and-combine-data/shapecombine_mergenewcolumn.png)

Um die zusammengeführte Tabelle zu erweitern und auszuwählen, welche Spalten einbezogen werden sollen, klicken Sie auf das Erweiterungssymbol (![Erweitern](media/desktop-shape-and-combine-data/icon.png)). Das Fenster **Erweitern** wird geöffnet.

![](media/desktop-shape-and-combine-data/shapecombine_mergeexpand.png)

In unserem Fall benötigen wir nur die Spalte **State Code**. Daher wählen Sie nur diese Spalte aus und klicken dann auf **OK**. Deaktivieren Sie das Kontrollkästchen „Ursprünglichen Spaltennamen als Präfix verwenden“, da wir den ursprünglichen Spaltennamen nicht benötigen. Wenn das Kontrollkästchen aktiviert bleibt, erhält die zusammengeführte Spalte den Namen **NewColumn.State Code** (zusammengesetzt aus dem ursprünglichen Spaltennamen bzw. **NewColumn**, einem Punkt und dem Namen der in die Abfrage eingefügten Spalte).

>[!NOTE]
>Möchten Sie ein wenig mit dem Einfügen der Tabelle **NewColumn** experimentieren? Sie können ein wenig ausprobieren. Wenn Ihnen die Ergebnisse nicht gefallen, löschen Sie diesen Schritt einfach in der Liste **Angewendete Schritte** im Bereich **Abfrageeinstellungen**. Ihre Abfrage wird dann wieder in den Zustand vor Anwenden des Schritts **Erweitern** versetzt. Auf diese Weise können Sie beliebig oft und solange experimentieren, bis die Erweiterung Ihren Vorstellungen entspricht.

Wir haben jetzt eine einzelne Abfrage (Tabelle), in der zwei entsprechend den Anforderungen strukturierte Datenquellen miteinander kombiniert sind. Diese Abfrage kann als Grundlage für viele weitere interessante Datenverbindungen dienen, z. B. für Statistiken zu Wohnkosten, demografischen Daten oder Beschäftigungsmöglichkeiten in den einzelnen Bundesstaaten.

Um die Änderungen zu übernehmen und den Abfrage-Editor zu schließen, wählen Sie im Menüband auf der Registerkarte **Start** die Option „Schließen und Anwenden“ aus. Das transformierte Dataset wird in Power BI Desktop angezeigt und kann zum Erstellen von Berichten verwendet werden.

![](media/desktop-shape-and-combine-data/shapecombine_closeandapply.png)

## <a name="next-steps"></a>Nächste Schritte
Mit Power BI Desktop können Sie viele Aufgaben ausführen. Weitere Informationen zu den Funktionen und Möglichkeiten finden Sie in folgenden Ressourcen:

* [Erste Schritte mit Power BI Desktop](desktop-getting-started.md)
* [Übersicht zu Abfragen mit Power BI Desktop](desktop-query-overview.md)
* [Datenquellen in Power BI Desktop](desktop-data-sources.md)
* [Verbinden mit Daten in Power BI Desktop](desktop-connect-to-data.md)
* [Allgemeine Abfrageaufgaben in Power BI Desktop](desktop-common-query-tasks.md)   

