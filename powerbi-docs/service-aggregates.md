---
title: Aggregate (Summe, Durchschnitt, Maximalwert usw.) in Power BI
description: "Ändern der Aggregation in einem Diagramm (Summe, Mittelwert, Maximum usw.) in Power BI"
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: modifying
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 09/23/2017
ms.author: mihart
ms.openlocfilehash: c1b926e129e8d82edd9c329a51623908c4e7c9e0
ms.sourcegitcommit: 8f72ce6b35aa25979090a05e3827d4937dce6a0d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/27/2017
---
# <a name="aggregates-in-power-bi"></a>Aggregate in Power BI
## <a name="what-is-an-aggregate"></a>Was ist ein Aggregat?
Unter Umständen möchten Sie die Werte von Zeilen mathematisch in einer Spalte miteinander kombinieren. Dabei kann es sich um die mathematische Operation zum Ermitteln von Summe, Mittelwert, Maximum, Anzahl usw. handeln. Das Kombinieren der Werte von Daten aus Zeilen in einer Spalte wird als „aggregieren“ bezeichnet. Das Ergebnis dieser mathematischen Operation ist ein *Aggregat*. 

Ein numerisches Feld ist ein Wert, der über ein Kategoriefeld aggregiert wird. (Es wird also beispielsweise eine Summe oder ein Mittelwert gebildet.)  Beispiele wären etwa „Umsatz nach Produkt“ und „Mängelanzahl nach Region“. Numerische Felder werden häufig als **Measures** bezeichnet. In der Liste „Felder“ werden Measures mit dem Symbol „∑“ angezeigt. Weitere Informationen finden Sie unter [Berichts-Editor: Verschaffen Sie sich einen Überblick](service-the-report-editor-take-a-tour.md).

Manchmal handelt es sich bei einem *Measure* eigentlich um ein *berechnetes Measure*. Berechnete Measures werden in Power BI zusammen mit den Daten importiert, die in dem Datenmodell definiert sind, auf dem Ihr Bericht basiert. Jedes berechnete Measure verfügt über eine eigene hartcodierte Formel. Die verwendete Aggregation kann nicht geändert werden. Eine Summe bleibt also beispielsweise eine Summe. In der Feldliste sind *berechnete Measures* mit dem Rechnersymbol gekennzeichnet. Weitere Informationen zur Erstellung berechneter Measures finden Sie unter [Measures in Power BI Desktop](desktop-measures.md).

Kategoriefelder sind zwar nicht numerisch, können aber trotzdem aggregiert werden.  Wenn Kategoriefelder in einem *rein numerischen* Bucket wie **Werte** oder **QuickInfos** platziert werden, kann Power BI die Vorkommen oder die eindeutigen Vorkommen der einzelnen Kategorien ermitteln.  Für Zeichenfolgen und Datumsangaben stehen in Power BI mit „Früheste“, „Neueste“, „Erste“ und „Letzte“ noch einige weitere Aggregierungsoptionen zur Verfügung.  

## <a name="why-dont-aggregates-work-the-way-i-want-them-to"></a>Warum funktionieren Aggregate nicht wie ich mir das vorstelle?
Die Verwendung von Aggregaten in Power BI kann teilweise etwas verwirrend sein. Haben Sie ein numerisches Feld, und Power BI lässt keine Änderung der Aggregation zu? Oder haben Sie ein Feld (beispielsweise ein Jahr), das nicht aggregiert werden soll, sondern für das Sie lediglich die Anzahl von Vorkommen ermitteln möchten?

In den meisten Fällen ist das Problem auf die Kategorisierung des Felds im Power BI-Dataset zurückzuführen. Möglicherweise wurde das Feld als Text kategorisiert, was erklären würde, warum keine Summe oder kein Mittelwert gebildet werden kann. [Die Kategorisierung eines Felds kann allerdings nur vom Besitzer des Datasets geändert werden.](desktop-measures.md)  

Als Orientierungshilfe haben wir am **Ende dieses Artikels** einige Tipps und Problembehandlungsinformationen bereitgestellt.  Sollten Sie dort keine passende Antwort finden, posten Sie Ihre Frage im [Forum der Power BI-Community](http://community.powerbi.com). Dort erhalten Sie eine schnelle Antwort direkt vom Power BI-Team.

## <a name="change-how-a-numeric-field-is-aggregated"></a>Ändern, wie ein numerisches Feld aggregiert wird
Angenommen, Sie haben ein Diagramm, das die Verkaufsdaten für verschiedene Regionen zusammenfasst. Sie bevorzugen aber den Mittelwert. 

1. Fügen Sie in der Bearbeitungsansicht des Berichts das Measure einer Visualisierung hinzu.
2. Suchen Sie das Feld im Visualisierungsbereich, klicken Sie mit der rechten Maustaste darauf, und wählen Sie den gewünschten Aggregattyp aus. Wenn die benötigte Aggregation nicht angezeigt wird, wenden Sie sich an den Datasetbesitzer. Möglicherweise verursacht die Kategorisierung des Felds durch den Besitzer das Problem.  
   
   ![](media/service-aggregates/aggregate_new.png)
   
   > [!NOTE]
   > Die in der Dropdownliste verfügbaren Optionen hängen erstens vom ausgewählten Feld und zweitens von der Kategorisierung des ausgewählten Felds durch den Datasetbesitzer ab.
   > 
   > 

Hier sind einige der Optionen aufgeführt, die möglicherweise zum Aggregieren eines Felds zur Verfügung stehen:

* **Nicht zusammenfassen**. Ist diese Option ausgewählt, wird jeder Wert in diesem Feld separat behandelt und nicht zusammengefasst. Die Option wird häufig verwendet, wenn Sie eine Spalte mit numerischen IDs besitzen, die nicht addiert werden sollen.
* **Summe**. Mit dieser Option werden alle Werte in diesem Feld addiert.
* **Mittelwert**. Ermittelt den arithmetischen Mittelwert der Werte.
* **Minimum**. Zeigt den kleinsten Wert.
* **Maximum**. Zeigt den größten Wert.
* **Anzahl (ohne Leerstellen)**. Mit dieser Option wird die Anzahl der Werte im Feld gezählt, die nicht leer sind.
* **Anzahl (diskret)**. Mit dieser Option wird die Anzahl der verschiedenen Werte im Feld gezählt.
* **Standardabweichung**.
* **Varianz.**
* **Median**.  Zeigt den Medianwert (mittlerer Wert) an. Dies ist der Wert, der die gleiche Anzahl von Werten über und unter sich hat.  Wenn 2 Mediane vorhanden sind, erstellt Power BI einen Durchschnittswert.

Die Daten:

| Land | Menge |
|:--- |:--- |
| USA |100 |
| VEREINIGTES KÖNIGREICH |150 |
| Kanada |100 |
| Deutschland |125 |
| Frankreich | |
| Japan |125 |
| Australien |150 |

führen zu folgenden Ergebnissen:

* **Nicht zusammenfassen**: Jeder Wert wird separat dargestellt.
* **Summe**: 750
* **Mittelwert**: 125
* **Maximum**: 150
* **Minimum**: 100
* **Anzahl (ohne Leerstellen):** 6
* **Anzahl (diskret):** 4
* **Standardabweichung:** 20,4124145...
* **Varianz:** 416,666...
* **Median:** 125

## <a name="use-a-non-aggregated-field-as-a-numeric-field"></a>Nicht aggregiertes Feld als numerisches Feld verwenden
Sie können auch ein nicht aggregiertes Feld als numerisches Feld verwenden. Wenn beispielsweise das Feld „Produktname“ vorhanden ist, können Sie es als Wert hinzufügen und dafür **Anzahl** oder **Diskrete Anzahl**festlegen. 

1. Beispiel: Auswahl von **Store > Kette**.
   
   ![](media/service-aggregates/count-of-chain-do_not_summarize.png)
2. Und wenn Sie die Aggregation von der Standardeinstellung **Nicht zusammenfassen** in **Anzahl (diskrete)**ändern, zählt Power BI die Anzahl der verschiedenen Ketten. In diesem Fall gibt es zwei: Fashions Direct und Lindseys.
   
   ![](media/service-aggregates/aggregates_count.png)
3. Und wenn Sie die Aggregation in **Anzahl**ändern, zählt Power BI die Gesamtanzahl. In diesem Fall sind es 104 Einträge für **Kette**. Durch Hinzufügen von **Kette** als Filter können Sie sehen, dass es 37 Zeilen für Fashions Direct und 67 Zeilen für Lindseys gibt.  
   
   ![](media/service-aggregates/count_of_chain_104.png)

## <a name="tips-and-troubleshooting"></a>Tipps und Problembehandlung
F: Warum ist die Funktion **Nicht zusammenfassen** nicht verfügbar?

A: Bei dem gewählten Feld handelt es sich wahrscheinlich um ein berechnetes Measure. Zur Erinnerung: Jedes berechnete Measure verfügt über eine eigene hartcodierte Formel. Die Berechnung kann also nicht geändert werden.

F: Mein Feld **ist** numerisch. Warum stehen mir nur die Optionen **Count** und **Distinct Count** zur Verfügung?

A: Wahrscheinlich hat der Besitzer des Datasets das Feld (versehentlich oder absichtlich) *nicht* als Zahl klassifiziert. Wenn beispielsweise ein Dataset das Feld **Jahr** enthält, wurde es vom Besitzer des Datasets eventuell als Text kategorisiert, da die Wahrscheinlichkeit höher ist, dass der Inhalt des Felds **Jahr** gezählt (z. B. die Anzahl der 1974 geborenen Personen) wird, als dass sein Inhalt addiert oder sein Mittelwert berechnet wird. Als Besitzer können Sie das Dataset in Power BI Desktop öffnen und auf der Registerkarte **Modellierung** den Datentyp ändern.  

A: Eine weitere Möglichkeit: Sie haben das Feld in einem *Bucket* platziert, in dem nur Kategoriewerte zulässig sind.  In diesem Fall stehen nur die Optionen „Count“ und „Distinct Count“ zur Verfügung.

A: Dritte Möglichkeit: Das Feld wird für eine Achse verwendet. Auf der Achse eines Balkendiagramms zeigt Power BI beispielsweise jeweils einen Balken pro eindeutigem Wert an. Die Feldwerte werden also überhaupt nicht aggregiert. 

>[!NOTE]
>Eine Ausnahme sind Punktdiagramme, bei denen aggregierte Werte für die X- und Y-Achse *erforderlich* sind.


F: Ich habe ein Punktdiagramm und möchte *nicht*, dass mein Feld aggregiert wird.  Wie kann ich das erreichen?

A: Fügen Sie das Feld dem Bucket **Details** (und nicht den Buckets für die X- oder Y-Achse) hinzu.

F: Wenn ich ein numerisches Feld einer Visualisierung hinzufüge, wird bei den meisten standardmäßig eine Summe gebildet, bei einigen wird hingegen standardmäßig ein Mittelwert gebildet, die Anzahl ermittelt oder eine andere Aggregation verwendet.  Warum ist die standardmäßige Aggregation nicht immer gleich?

A: Besitzer von Datasets können die Standardzusammenfassung individuell für einzelne Felder festlegen. Als Besitzer eines Datasets können Sie die Standardzusammenfassung auf der Power BI Desktop-Registerkarte **Modellierung** ändern.

F: Mein Feld **ist** numerisch. Warum enthält die Dropdownliste keinerlei Zusammenfassungsoptionen?

A: Wenn das Feld mit einem Rechnersymbol gekennzeichnet ist, handelt es sich um ein *berechnetes Measure*. Jedes berechnete Measure verfügt über eine eigene hartcodierte Formel, die im Power BI-Dienst nicht geändert werden kann. Bei der verwendeten Berechnung kann es sich um eine einfache Aggregation wie einen Mittelwert oder eine Summe handeln, aber auch kompliziertere Aggregationen wie "prozentualer Anteil an einer übergeordneten Kategorie“ oder „laufende Summe seit Jahresbeginn“ sind möglich. Power BI bildet keine Summe und keinen Mittelwert für die Ergebnisse, sondern führt stattdessen lediglich eine Neuberechnung für die einzelnen Datenpunkte durch (unter Verwendung der hartcodierten Formel).

F: Ich bin Besitzer eines Datasets und möchte sicherstellen, dass ein Feld nicht aggregiert wird. Wie gehe ich dazu vor?

A: Legen Sie in Power BI Desktop auf der Registerkarte **Modellierung** die Option **Datentyp** auf **Text** fest.

F: In der Dropdownliste steht die Option **Nicht zusammenfassen** nicht zur Verfügung. Was kann ich tun?

A: Entfernen Sie das Feld, und fügen Sie es anschließend wieder hinzu.

Weitere Fragen? [Wenden Sie sich an die Power BI-Community](http://community.powerbi.com/)

