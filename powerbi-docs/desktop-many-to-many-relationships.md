---
title: m:n-Beziehungen in Power BI Desktop (Vorschauversion)
description: Verwendung von m:n-Beziehungen in Power BI Desktop
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 07/23/2018
ms.author: davidi
LocalizationGroup: Transform and shape data
ms.openlocfilehash: 1105de002f6461589d61c6f0077cceeedaada471
ms.sourcegitcommit: 6faeb642721ee5abb41c04a8b729880c01c4d40e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2018
ms.locfileid: "39211342"
---
# <a name="many-to-many-relationships-in-power-bi-desktop-preview"></a>m:n-Beziehungen in Power BI Desktop (Vorschauversion)

Mit dem Feature **m:n-Beziehungen** in **Power BI Desktop** können Tabellen, in denen die Kardinalität **m:n** verwendet wird, verknüpft und Datenmodelle, die mehrere Datenquellen enthalten, einfacher und intuitiver erstellt werden. Das Feature **m:n-Beziehungen** ist Teil der umfangreicheren Funktionen des Features **Zusammengesetzte Modelle** in **Power BI Desktop**.

![Option „m:n“ im Dialogfeld „Beziehung bearbeiten“](media/desktop-many-to-many-relationships/many-to-many-relationships_01.png)

Die Funktion **m:n-Beziehungen** in **Power BI Desktop** ist Teil einer Sammlung von drei in Beziehung stehenden Features:

* **Zusammengesetzte Modelle**: Hierbei kann ein Bericht mehrere Datenverbindungen beinhalten, einschließlich DirectQuery-Verbindungen oder Importe in beliebiger Kombination.
* **m:n Beziehungen**: Mit dem Feature **Zusammengesetzte Modelle** können Sie **m:n-Beziehungen** zwischen Tabellen erstellen, wodurch die Notwendigkeit für eindeutige Werte in Tabellen und frühere Problemumgehungen wie die Einführung neuer Tabellen nur für die Erstellung von Beziehungen entfallen. 
* **Speichermodus**: Ab sofort können Sie angeben, welche Visuals eine Abfrage an Back-End-Datenquellen erfordern, und festlegen, dass Visuals, die keine erfordern, importiert werden, auch wenn diese auf DirectQuery basieren. Hierdurch wird die Leistung verbessert und die Auslastung des Back-Ends verringert. Vorher initiierten sogar einfache Visuals wie Slicer Abfragen, die an Back-End-Quellen gesendet wurden. 

Diese Sammlung aus drei in Beziehung stehenden Features für das Feature **Zusammengesetzte Modelle** werden jeweils in separaten Artikeln beschrieben:

* **Zusammengesetzte Modelle** werden im Artikel [Zusammengesetzte Modelle in Power BI Desktop (Vorschauversion)](desktop-composite-models.md) ausführlich beschrieben.
* Im vorliegenden Artikel werden **m:n-Beziehungen** beschrieben.
* Der **Speichermodus** wird in einem eigenen Artikel beschrieben: [Speichermodus in Power BI Desktop (Vorschauversion)](desktop-storage-mode.md).

## <a name="enabling-the-many-to-many-relationships-preview-feature"></a>Aktivieren des Vorschaufeatures „m: n-Beziehungen“

Das Feature **m:n-Beziehungen**, das als Vorschauversion verfügbar ist, ist Teil der Funktionen des Features **Zusammengesetzte Modelle**. Dieses muss in **Power BI Desktop** aktiviert werden. Um **Zusammengesetzte Modelle** zu aktivieren, wählen Sie **Datei > Optionen und Einstellungen > Optionen > Vorschaufeatures** aus, und aktivieren Sie anschließend das Kontrollkästchen **Zusammengesetzte Modelle**.

![Aktivieren der Vorschaufeatures](media/desktop-composite-models/composite-models_02.png)

Sie müssen **Power BI Desktop** neu starten, damit das Feature aktiviert wird.

![Meldung, dass zur Anwendung der Änderungen ein Neustart erforderlich ist](media/desktop-composite-models/composite-models_03.png)


## <a name="what-many-to-many-relationships-solves"></a>Verbesserung durch m:n-Beziehungen

Bevor das Feature **m:n-Beziehungen** eingeführt wurde, musste bei der Definition einer Beziehung zwischen zwei Tabellen in Power BI mindestens eine der Spalten, die in der Beziehung verwendet wurde, eindeutige Werte enthalten. In vielen Fällen enthielt jedoch keine Spalte in der Tabelle eindeutige Werte. 

Beispielsweise enthielten zwei Tabellen eine Spalte mit *Country*, jedoch waren die Werte von *Country* in keiner der beiden Tabellen eindeutig. Um solche Tabellen zu verknüpfen, musste eine Problemumgehung angewendet werden, indem z.B. zusätzliche Tabellen in das Modell eingeführt wurden, die die erforderlichen eindeutigen Werte enthielten. Das Feature **m:n-Beziehungen** bietet eine alternative Methode, mit der diese Tabellen anhand einer Beziehung mit der Kardinalität **m:n** direkt verknüpft werden können.  

## <a name="using-many-to-many-relationships"></a>Verwendung von m:n-Beziehungen

Wenn Sie eine Beziehung zwischen zwei Tabellen in Power BI definieren, müssen Sie die Kardinalität der Beziehung definieren. Die Beziehung zwischen *ProductSales* und *Produkt* (mit den Spalten *ProductSales[ProductCode]* und *Product[ProductCode]*) würde z.B. als **n:1** definiert werden, da es viele Umsätze für die einzelnen Produkte gibt und die Spalte in der Tabelle *Produkt* *(ProductCode)* eindeutig ist. Wird eine Beziehungskardinalität als **n: 1**, **1:n**, oder **1:1** definiert, führt Power BI eine Überprüfung durch, um sicherzustellen, dass die ausgewählte Kardinalität den tatsächlichen Daten entspricht.

Werfen Sie beispielsweise einen Blick auf das einfache Modell in der folgenden Abbildung.

![Beziehungsansicht](media/desktop-many-to-many-relationships/many-to-many-relationships_02.png)

Nehmen wir an, die Tabelle *Product* würde nur zwei Zeilen enthalten.

![Tabellenvisual](media/desktop-many-to-many-relationships/many-to-many-relationships_03.png)

Nehmen wir zudem an, die Tabelle *Sales* würde nur vier Zeilen enthalten, darunter *Sales* für ein Produkt **C**, das nicht in der Tabelle *Product* enthalten ist (aufgrund eines Fehlers in der referentiellen Integrität).

![Tabellenvisual](media/desktop-many-to-many-relationships/many-to-many-relationships_04.png)

Ein Visual, das *ProductName* und *Price* (aus der Tabelle *Product*) zusammen mit der gesamten *Qty* für jedes Produkt (aus der Tabelle *ProductSales*) anzeigt, würde wie in der folgenden Abbildung zu sehen aussehen: 

![Tabellenvisual](media/desktop-many-to-many-relationships/many-to-many-relationships_05.png)

Wie Sie in der obigen Abbildung sehen können, ist eine Zeile im Visual mit einem leeren *ProductName* vorhanden, der den Umsätzen für das Produkt *C* zugeordnet ist. Diese leere Zeile würde Folgendes abdecken:

* Zeilen in der Tabelle *ProductSales*, für die es keine entsprechende Zeile in der Tabelle *Product* gibt: Hier besteht ein Problem mit der referentiellen Integrität, wie am Produkt *C* in diesem Beispiel zu erkennen ist.

* Zeilen in der Tabelle *ProductSales*, bei denen die Fremdschlüsselspalte „NULL“ ist. 

Aus diesen Gründen deckt die leere Zeile in beiden Fällen Umsätze ab, bei denen *ProductName* und *Price* unbekannt sind.

Manchmal kann es allerdings vorkommen, dass die Tabellen durch zwei Spalten verknüpft sind, jedoch keine Spalte eindeutig ist. Betrachten Sie beispielsweise die folgenden zwei Tabellen:

* Die Tabelle *Sales* enthält die Umsatzdaten nach *State*, wobei jede Zeile den Umsatzbetrag für den Typ des Umsatzes im jeweiligen Bundesstaat (z.B. Bundesstaaten wie CA, WA, CA und TX) enthält. 

    ![Tabellenvisual](media/desktop-many-to-many-relationships/many-to-many-relationships_06.png)

* Die Tabelle *CityData* enthält Daten zu Städten, einschließlich der Einwohnerzahl und des Bundesstaats (z.B. Bundesstaaten wie CA, WA und New York).

    ![Tabellenvisual](media/desktop-many-to-many-relationships/many-to-many-relationships_07.png)

Es gibt zwar eine Spalte für *State* in beiden Tabellen und es ist sinnvoll, den gesamten *Sales* nach *State* zusammen mit der Gesamteinwohnerzahl der einzelnen Bundesstaaten zu melden, jedoch besteht folgendes Problem: die Spalte *State* ist in keiner der Tabellen eindeutig. 

## <a name="the-prior-workaround"></a>Die vorherige Problemumgehung

Bei **Power BI Desktop**-Versionen, die vor dem Release von Juli 2018 eingeführt wurden, war es nicht möglich, eine direkte Beziehung zwischen diesen Tabellen zu erstellen. Eine gängige Problemumgehung für dieses Problem bestand darin, die folgenden Schritte durchzuführen:

* Eine dritte Tabelle wurde erstellt, die ausschließlich die eindeutigen *State*-IDs enthält. Hierbei konnte es sich entweder um eine berechnete Tabelle (mithilfe von DAX definiert) handeln oder um eine Tabelle, die mit einer Abfrage im **Abfrage-Editor** definiert wurde. Diese konnte eindeutige IDs enthalten, die einer der Tabellen oder der vereinigten gesamten Gruppe entnommen wurden.

* Die beiden ursprünglichen Tabellen wurden mithilfe der allgemeinen **n:1*-Beziehungen mit dieser neuen Tabelle in Beziehung gesetzt.

Diese Problemumgehungstabelle konnte entweder eingeblendet oder ausgeblendet sein, sodass sie nicht in der Feldliste angezeigt wurde. In letzterem Fall würden die **n: 1**-Beziehungen häufig zum Filtern in beiden Richtungen festgelegt werden, sodass das Feld *State* von beiden Tabellen verwendet werden konnte. Anschließend würde die Kreuzfilterung an die andere Tabelle verteilt werden. Diese Problemumgehungsmethode wird in der folgenden Abbildung zur **Beziehungsansicht** dargestellt.

![Beziehungsansicht](media/desktop-many-to-many-relationships/many-to-many-relationships_08.png)

Ein Visual, das *State* (aus der Tabelle *CityData*) zusammen mit der gesamten *Population* und dem gesamten *Sales* anzeigt, würde dann wie folgt aussehen:

![Tabellenvisual](media/desktop-many-to-many-relationships/many-to-many-relationships_09.png)

Beachten Sie, dass hinsichtlich der Verwendung des Bundesstaats von der Tabelle *CityData* in dieser Problemumgehung nur die *State*-Werte in dieser Tabelle aufgeführt werden (daher ist TX ausgeschlossen). Im Gegensatz zu **n:1**-Beziehungen ist in den Details darüber hinaus keine leere Zeile enthalten, die solche nicht übereinstimmenden Zeilen abdeckt. Die Zeile „Total“ enthält hingegen alle *Sales*-Werte (einschließlich der von TX). Analog dazu gäbe es keine leere Zeile, die alle *Sales*-Werte abdeckt, bei denen der Wert für *State* „NULL“ lauten würde.

Wenn *City* ebenfalls diesem Visual hinzugefügt worden wäre, wäre zwar die Einwohnerzahl für die jeweilige *City* bekannt, der *Sales*-Wert für *City* würde jedoch einfach den *Sales*-Wert für den entsprechenden *State* wiederholen (wie es normalerweise der Fall ist, wenn für eine Spalte eine Gruppierung vorgenommen wird, die nicht mit aggregierten Measures verknüpft ist). Dies wird in der folgenden Abbildung veranschaulicht.

![Tabellenvisual](media/desktop-many-to-many-relationships/many-to-many-relationships_10.png)

Wenn die neue Tabelle *Sales* als Vereinigung aller *State*-Werte in dieser Problemumgehung definiert und in der Feldliste sichtbar gemacht worden wäre, würden dieses Visual, das *State* anzeigt (in der neuen Tabelle), sowie der Gesamtwert von *Population* und der Gesamtwert von *Sales* dann wie folgt aussehen:

![Tabellenvisual](media/desktop-many-to-many-relationships/many-to-many-relationships_11.png)

In diesem Fall und wie anhand des Visuals gezeigt würden *TX* (mit *Sales*, jedoch unbekannter Einwohnerzahl) und *New York* (mit bekannter Einwohnerzahl, jedoch ohne *Sales*) eingeschlossen werden. 

Wie Sie sehen können, war diese Problemumgehung nicht optimal und führt zu vielen Problemen. Mit der Erstellung der **m:n-Beziehung** werden diese Probleme gelöst, wie im folgenden Abschnitt beschrieben wird.

## <a name="using-many-to-many-relationships-instead-of-the-workaround"></a>Verwendung von m:n-Beziehungen anstelle der Problemumgehung

In **Power BI Desktop**-Versionen, die ab Juli 2018 veröffentlicht wurden, können Sie die im vorherigen Abschnitt beschriebenen Tabellen direkt in Beziehung setzen, ohne auf diese Problemumgehungen zurückgreifen zu müssen. Ab sofort kann die Kardinalität einer Beziehung auf **m:n** festgelegt werden, wodurch angegeben wird, dass keine der Tabellen eindeutige Werte enthält. Bei solchen Beziehungen können Sie nach wie vor steuern, welche Tabelle die jeweils andere Tabelle filtert, oder die bidirektionale Filterung festlegen, bei der beide Tabellen sich gegenseitig filtern.  

> [!NOTE]
> Das Feature zur Erstellung von **m:n**-Beziehungen ist in der Vorschauversion verfügbar, es können jedoch keine Modelle mit **m:n**-Beziehungen für den Power BI-Dienst veröffentlicht werden. 

In **Power BI Desktop** wird die Kardinalität standardmäßig auf **m:n** festgelegt, wenn festgestellt wird, dass keine der Tabellen eindeutige Werte für die Spalten in der Beziehung enthält. In solchen Fällen wird eine Warnung angezeigt, um zu bestätigen, dass diese Beziehungseinstellung Ihr beabsichtigtes Verhalten widerspiegelt und keine unbeabsichtigte Auswirkung eines Datenproblems darstellt. 

Beispielsweise wird bei der Erstellung einer direkten Beziehung zwischen *CityData* und *Sales*, bei dem Filter von *CityData* zu *Sales* übergehen sollten, wird das Dialogfeld zur Beziehung angezeigt. Dies wird in der folgenden Abbildung dargestellt.

![Dialogfeld „Beziehung bearbeiten“](media/desktop-many-to-many-relationships/many-to-many-relationships_01.png)

Die resultierende **Beziehungsansicht** würde dann die direkte **m:n**-Beziehung zwischen den beiden Tabellen enthalten. Die Darstellung in der Liste **Felder** und das anschließende Verhalten bei der Erstellung von Visuals stimmt mit der im vorherigen Abschnitt beschriebenen Problemumgehung überein, bei der die zusätzliche Tabelle (mit den darin enthaltenen unterschiedlichen *State*-Werten) nicht sichtbar gemacht wurde. Ein Visual, das z.B. *State* zusammen mit der Gesamteinwohnerzahl und des Gesamtumsatzes anzeigt, wie im vorherigen Abschnitt zur Problemumgehung beschrieben wurde, würde wie folgt aussehen:

![Tabellenvisual](media/desktop-many-to-many-relationships/many-to-many-relationships_12.png)

Zwischen **m:n**-Beziehungen und den geläufigeren **n:1**-Beziehungen besteht der folgende wesentliche Unterschied:

* Die angezeigten Werte enthalten keine leere Zeile, die nicht übereinstimmende Zeilen in der anderen Tabelle oder Zeilen abdeckt, bei denen die in der Beziehung verwendete Spalte in der anderen Tabelle „NULL“ ist.
* Die *RELATED()*-Funktion kann nicht verwendet werden (da mehr als eine Zeile verknüpft sein könnte).
* Mit der *ALL()*-Funktion in einer Tabelle werden keine Filter entfernt, die auf andere Tabellen angewendet wurden, die wiederum durch eine **m:n**-Beziehung verknüpft wurden. Beispielsweise würde ein wie folgt definiertes Measure im vorherigen Beispiel nicht Filter für Spalten zur zugehörigen Tabelle *CityData* entfernen:

    ![Beispiel für ein Skript](media/desktop-many-to-many-relationships/many-to-many-relationships_13.png)

    Dementsprechend würde ein Visual, das *State*, *Sales* und *Sales Total* anzeigt, wie folgt aussehen:

    ![Tabellenvisual](media/desktop-many-to-many-relationships/many-to-many-relationships_14.png)

Aus diesem Grund sollte dies berücksichtigt werden, um sicherzustellen, dass Berechnungen mit *ALL(\<Table>)* (z.B. *% der Gesamtsumme*), die gewünschten Ergebnisse zurückgeben. 


## <a name="limitations-and-considerations"></a>Einschränkungen und Überlegungen

Bei diesem Release der Features **m:n-Beziehungen** und **Zusammengesetzte Modelle** gibt es einige Einschränkungen.

Die folgenden mehrdimensionalen Quellen können nicht mit **zusammengesetzten Modellen** verwendet werden:

* SAP HANA
* SAP Business Warehouse
* SQL Server Analysis Services
* Power BI-Datasets

Wenn mithilfe von DirectQuery eine Verbindung mit diesen mehrdimensionalen Quellen hergestellt wird, können Sie weder eine Verbindung mit einer anderen DirectQuery-Quelle herstellen noch importierte Daten kombinieren.

Die bestehenden Einschränkungen für die Verwendung von DirectQuery gelten nach wie vor für die Verwendung des Features **m:n-Beziehungen**. Viele dieser Einschränkungen gelten jetzt abhängig vom **Speichermodus** der Tabelle für eine einzelne Tabelle. Beispielsweise kann eine berechnete Spalte in einer importierten Tabelle auf andere Tabellen verweisen, wohingegen eine berechnete Spalte in einer DirectQuery-Tabelle nach wie vor nur auf Spalten in derselben Tabelle verweisen kann. Es gelten weitere Einschränkungen für das Modell als Ganzes, wenn eine der Tabellen im Modell DirectQuery enthält. Die Features **QuickInsights** und **Q&A** sind nicht für Modelle verfügbar, wenn eine der Tabellen den **Speichermodus** „DirectQuery“ aufweist. 

## <a name="next-steps"></a>Nächste Schritte

Die folgenden Artikeln enthalten weitere Informationen über zusammengesetzte Modelle sowie Details zu DirectQuery.

* [Zusammengesetzte Modelle in Power BI Desktop (Vorschauversion)](desktop-composite-models.md)
* [Speichermodus in Power BI Desktop (Vorschauversion)](desktop-storage-mode.md)

Artikel zu DirectQuery:

* [Verwendung von DirectQuery in Power BI](desktop-directquery-about.md)
* [Von DirectQuery in Power BI unterstützte Datenquellen](desktop-directquery-data-sources.md)

