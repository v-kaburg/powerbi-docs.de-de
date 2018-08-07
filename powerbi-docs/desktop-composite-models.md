---
title: Verwenden von zusammengesetzten Modellen in Power BI Desktop (Vorschauversion)
description: Erstellen von Datenmodellen mit mehreren Datenverbindungen und m:n-Beziehungen in Power BI Desktop
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 07/26/2018
ms.author: davidi
LocalizationGroup: Transform and shape data
ms.openlocfilehash: 2eb69896de8226fdf0033f980a8b4b5164c68c3d
ms.sourcegitcommit: df7a58dae14ef311516c9b3098f87742786f0479
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/27/2018
ms.locfileid: "39280154"
---
# <a name="composite-models-in-power-bi-desktop-preview"></a>Zusammengesetzte Modelle in Power BI Desktop (Vorschauversion)

Wenn Sie bislang in **Power BI Desktop** DirectQuery in einem Bericht verwendet haben, waren keine anderen Datenverbindungen für diesen Bericht zulässig, ganz gleich, ob es sich um DirectQuery- oder Importdatenverbindungen handelte. Bei **zusammengesetzten Modellen** ist diese Einschränkung hinfällig, da ein Bericht problemlos mehrere DirectQuery- oder Importdatenverbindungen in einer beliebigen Kombination derselbigen umfassen kann.

![Zusammengesetzte Modelle in Power BI Desktop](media/desktop-composite-models/composite-models_01.png)

Die Funktion **Zusammengesetzte Modelle** in **Power BI Desktop** besteht aus drei in Beziehung stehenden Features:

* **Zusammengesetzte Modelle**: Hierbei kann ein Bericht mehrere Datenverbindungen beinhalten, einschließlich DirectQuery- oder Importverbindungen in beliebiger Kombination.
* **m:n Beziehungen**: Mit dem Feature **Zusammengesetzte Modelle** können Sie **m:n-Beziehungen** zwischen Tabellen erstellen, wodurch die Notwendigkeit für eindeutige Werte in Tabellen und frühere Problemumgehungen wie die Einführung neuer Tabellen nur für die Erstellung von Beziehungen entfallen. 
* **Speichermodus**: Ab sofort können Sie angeben, welche Visuals eine Abfrage an Back-End-Datenquellen erfordern, und festlegen, dass Visuals, die keine erfordern, importiert werden, auch wenn diese auf DirectQuery basieren. Hierdurch wird die Leistung verbessert und die Auslastung des Back-Ends verringert. Vorher initiierten sogar einfache Visuals wie Slicer Abfragen, die an Back-End-Quellen gesendet wurden. 

Diese Sammlung aus drei in Beziehung stehenden Features für das Feature **Zusammengesetzte Modelle** werden jeweils in separaten Artikeln beschrieben:

* In dem vorliegenden Artikel werden **zusammengesetzte Modelle** näher beschrieben.
* **m:n-Beziehungen** werden in einem eigenen Artikel beschrieben, nämlich unter [m:n Beziehungen in Power BI Desktop (Vorschauversion)](desktop-many-to-many-relationships.md).
* Der **Speichermodus** wird in einem eigenen Artikel beschrieben: [Speichermodus in Power BI Desktop (Vorschauversion)](desktop-storage-mode.md).

## <a name="enabling-the-composite-models-preview-feature"></a>Aktivieren des Vorschaufeatures für zusammengesetzte Modelle

Das Feature **Zusammengesetzte Modelle** ist in der Vorschauversion verfügbar und muss in **Power BI Desktop** aktiviert werden. Um **Zusammengesetzte Modelle** zu aktivieren, wählen Sie **Datei > Optionen und Einstellungen > Optionen > Vorschaufeatures** aus, und aktivieren Sie anschließend das Kontrollkästchen **Zusammengesetzte Modelle**. 

![Aktivieren der Vorschaufeatures](media/desktop-composite-models/composite-models_02.png)

Sie müssen **Power BI Desktop** neu starten, damit das Feature aktiviert wird.

![Meldung, dass zur Anwendung der Änderungen ein Neustart erforderlich ist](media/desktop-composite-models/composite-models_03.png)


## <a name="using-composite-models"></a>Verwendung von zusammengesetzten Modellen

Bei **zusammengesetzten Modellen** können Sie eine Verbindung mit allen möglichen verschiedenen Datenquellen herstellen, wenn Sie **Power BI Desktop** oder den **Power BI-Dienst** verwenden, und es gibt unterschiedliche Möglichkeiten, diese Datenverbindungen herzustellen. Sie können Daten in Power BI importieren, was die gängigste Methode ist, um Daten abzurufen. Alternativ können Sie mit DirectQuery eine direkte Verbindung mit Daten im ursprünglichen Quellrepository herstellen. Weitere Einzelheiten zu DirectQuery finden Sie im Artikel [Verwendung von DirectQuery in Power BI](desktop-directquery-about.md).

Bei Verwendung von DirectQuery mit **zusammengesetzten Modellen** ist es möglich, ein Power BI-Modell (z.B. eine einzelne Power BI Desktop-Datei im PBIX-Format) für folgende Zwecke zu erstellen:

* Kombinieren von Daten aus mindestens einer DirectQuery-Quelle und/oder
* Kombinieren von Daten aus DirectQuery-Quellen und Importdaten

Mit **zusammengesetzten Modellen** kann beispielsweise ein Modell erstellt werden, das Umsatzdaten aus einem Data Warehouse eines Unternehmens mit Daten zu Umsatzvorgaben, die in einer abteilungsspezifischen SQL Server-Datenbank-Instanz gespeichert sind, sowie einigen aus einem Arbeitsblatt importierte Daten kombiniert. Ein Modell, bei dem Daten aus mehr als einer DirectQuery-Quelle kombiniert werden oder bei dem DirectQuery mit importierten Daten kombiniert wird, wird als *zusammengesetztes Modell* bezeichnet.

> [!NOTE]
> Zusammengesetzte Modelle sind zwar in der Vorschauversion verfügbar, können jedoch nicht als zusammengesetzte Modelle im Power BI-Dienst veröffentlicht werden. 

Sie können wie gewohnt Beziehungen zwischen Tabellen erstellen, auch wenn diese Tabellen von verschiedenen Quellen stammen. Hierbei gilt jedoch eine Einschränkung: Beziehungen, die sich über mehrere Quellen erstrecken, müssen so definiert werden, dass sie die Kardinalität **m:n** aufweisen, unabhängig von der tatsächlichen Kardinalität. Das Verhalten solcher Beziehungen entspricht dann dem normalen Verhalten für **m:n**-Beziehungen, wie unter [m:n-Beziehungen in Power BI Desktop (Vorschauversion)](desktop-many-to-many-relationships.md) beschrieben wird. Beachten Sie, dass im Kontext von zusammengesetzten Modellen, alle importierten Tabellen im Grunde eine einzelne Quelle darstellen, unabhängig von der tatsächlichen zugrunde liegenden Datenquelle, aus der sie eigentlich importiert wurden.   

## <a name="example-of-using-composite-models"></a>Beispiel für die Verwendung von zusammengesetzten Modellen

Als Beispiel für ein **zusammengesetztes Modell** können Sie einen Bericht heranziehen, bei dem mithilfe von DirectQuery eine Verbindung mit einem Data Warehouse eines Unternehmens (in SQL Server) hergestellt wurde. Das Data Warehouse enthält dabei Daten zu *BikeSales und Country*, *CalendarQuarter* und *Bike*, wie in der folgenden Abbildung dargestellt wird.

![Beziehungsansicht bei zusammengesetzten Modellen](media/desktop-composite-models/composite-models_04.png)

Nun könnten Sie mithilfe von Feldern aus dieser Quelle einfache Visuals erstellen. Das folgende Visual zeigt z.B. den Gesamtumsatz nach *ProductName* für ein ausgewähltes Quartal. 

![Visual basierend auf Daten](media/desktop-composite-models/composite-models_05.png)

Doch was wäre, wenn Sie einige Informationen zum Produktmanager, der den einzelnen Produkten zugewiesen wurde, sowie zur Marketingpriorität besäßen? Wo würden diese Daten in einem Excel-Arbeitsblatt verwaltet werden? Hierbei sollten Sie *SalesAmount* nach *ProductManagers* heranziehen, wobei ein Hinzufügen dieser lokalen Daten zum Data Warehouse des Unternehmens jedoch aller Wahrscheinlichkeit nach unmöglich wäre oder bestenfalls Monate dauern würde. Umsatzdaten könnten zwar aus dem Data Warehouse (anstatt mit DirectQuery) importiert werden, wobei die Daten in diesem Fall mit aus dem Arbeitsblatt importierten Daten kombiniert werden könnten, dieser Ansatz ist jedoch nicht sinnvoll angesichts der Beweggründe, aus denen DirectQuery überhaupt verwendet wird – nämlich um z.B. die Sicherheitsregeln, die in der zugrunde liegenden Quelle erzwungen werden, im gewissen Maß zu kombinieren, die neuesten Daten einsehen zu können und wegen des schieren Volumens der Daten. 

An dieser Stelle kommen **zusammengesetzte Modelle** ins Spiel. Zusammengesetzte Modelle ermöglichen es Ihnen, über DirectQuery eine Verbindung mit dem Data Warehouse herzustellen und dann auch GetData für zusätzliche Quellen zu verwenden. In diesem Fall wird die DirectQuery-Verbindung mit dem Data Warehouse des Unternehmens hergestellt, anschließend GetData verwendet und Excel geöffnet. In das Arbeitsblatt, das die lokalen Daten enthält, kann das Blatt mit den *ProductNames*, dem zugewiesenen *SalesManager* und der *Priority* importiert werden.  

![Navigator-Fenster](media/desktop-composite-models/composite-models_06.png)

Nun sehen Sie in der Liste **Felder** die ursprüngliche Tabelle *Bike* (von SQL Server) und eine neue Tabelle *ProductManagers* (mit den aus Excel importierten Daten). 

![Felderansicht der Tabellen](media/desktop-composite-models/composite-models_07.png)

Auch in **Power BI Desktop** finden Sie unter **Beziehungsansicht** nun eine weitere Tabelle mit dem Namen *ProductManagers*. 

![Beziehungsansicht der Tabellen](media/desktop-composite-models/composite-models_08.png)

Nun müssen diese – wie auch bislang immer üblich – mit den anderen Tabellen im Modell in Beziehung gesetzt werden, indem eine Beziehung zwischen der Tabelle *Bike* (in SQL Server) und der (importierten) Tabelle *ProductManagers* erstellt wird, z.B. zwischen *Bike[ProductName]* und *ProductManagers[ProductName]*. Wie weiter oben in diesem Artikel erläutert wurde, müssen alle Beziehungen, die sich über mehrere Quellen erstrecken, die Kardinalität **m:n** aufweisen. Diese ist entsprechend als Standardkardinalität ausgewählt. 

![Dialogfeld „Beziehung erstellen“](media/desktop-composite-models/composite-models_09.png)

Nachdem Sie diese Beziehung erstellt haben, wird die Beziehung erwartungsgemäß in **Power BI Desktop** in der **Beziehungsansicht** angezeigt.

![Ansicht „Neue Beziehung“](media/desktop-composite-models/composite-models_10.png)

Nachdem diese Tabellenbeziehungen erstellt wurden, können nun mit einem der Felder in der Liste **Felder** Visuals erstellt werden, die nahtlos Daten aus verschiedenen Quellen einbinden. Das unten dargestellte Visual zeigt z.B. den gesamten *SalesAmount* für die einzelnen *ProductManagers*. 

![Visual mit dem angezeigten Bereich „Felder“](media/desktop-composite-models/composite-models_11.png)

In diesem Beispiel wird ein häufiges Szenario gezeigt, bei dem die Tabelle *dimension* (z.B. *Product* oder *Customer*) um einige zusätzliche Daten erweitert wird, die aus einer anderen Quelle importiert wurden. Bei Tabellen kann auch mittels DirectQuery eine Verbindung mit anderen Quellen hergestellt werden. Stellen Sie sich aufbauend auf unserem Beispiel vor, *SalesTargets* würden nach *Country* und *Period* in einer separaten Abteilungsdatenbank gespeichert werden. Mit **GetData** können Sie wie gewohnt eine Verbindung mit diesen Daten herstellen, wie in der folgenden Abbildung dargestellt wird. 

![Dialogfeld „Navigator“](media/desktop-composite-models/composite-models_12.png)

Ähnlich wie weiter oben in diesem Beispiel können dann Beziehungen zwischen der neuen Tabelle und anderen Tabellen im Modell sowie Visuals erstellt werden, die die jeweiligen Daten kombinieren. Werfen wir erneut einen Blick auf die **Beziehungsansicht**, in der wir in unserem Szenario mit dem erweiterten Beispiel neue Beziehungen erstellt haben.

![Beziehungsansicht mit vielen Tabellen](media/desktop-composite-models/composite-models_13.png)

Wie in der folgenden Abbildung dargestellt wird, die auf den neuen soeben erstellten Daten und Beziehungen basiert, zeigt das Visual in der unteren linken Ecke den gesamten *SalesAmount* im Vergleich zu *Ziel* an. Die Abweichungsberechnung stellt dabei den Unterschied zwischen *SalesAmount* und *Target*, die aus zwei verschiedenen SQL Server-Datenbank-Instanzen stammen. 

![Visual mit weiteren Daten](media/desktop-composite-models/composite-models_14.png)

## <a name="setting-storage-mode"></a>Festlegen des Speichermodus

Jede Tabelle in einem **zusammengesetzten Modell** weist einen **Speichermodus** auf, der angibt, ob die Tabelle auf DirectQuery oder Importen basiert. Der **Speichermodus** kann im Bereich **Eigenschaft** angezeigt und geändert werden. Um zu dieser Ansicht zu gelangen, wählen Sie in der Liste **Felder** die Option **Eigenschaften** aus, und klicken Sie mit der rechten Maustaste auf das Kontextmenü. Die folgende Abbildung zeigt den **Speichermodus** (in der Abbildung aufgrund der Breite des Bereichs auf **Speicher...** gekürzt).

![Festlegen des Speichermodus](media/desktop-composite-models/composite-models_15.png)

Der **Speichermodus** ist auch in der QuickInfo für die einzelnen Tabellen einsehbar.

![QuickInfo mit dem Speichermodus](media/desktop-composite-models/composite-models_16.png)

Bei **Power BI Desktop**-Dateien (PBIX-Format), die zum Teil Tabellen vom DirectQuery und importierte Tabellen enthalten, wird in der Statusleiste der **Speichermodus** mit dem Status **Gemischt** angezeigt. Durch Klicken auf diese Bezeichnung in der Statusleiste können Sie einfach zwischen allen zu importierenden Tabellen wechseln.

Der **Speichermodus** wird im Artikel [Speichermodus in Power BI Desktop (Vorschauversion)](desktop-storage-mode.md) vollständig beschrieben.  

## <a name="calculated-tables"></a>Berechnete Tabellen

Berechnete Tabellen können einem Modell hinzugefügt werden, das DirectQuery verwendet, und die DAX-Bibliothek, die die berechnete Tabelle definiert, kann entweder auf importierte oder DirectQuery-Tabellen oder auf eine Kombination derselbigen verweisen. 

Berechnete Tabellen werden immer importiert, und die Daten in diesen Tabellen werden bei Aktualisierung der Tabelle aktualisiert. Wenn eine berechnete Tabelle folglich auf eine DirectQuery-Tabelle verweist, zeigen Visuals, die auf die DirectQuery-Tabelle verweisen, immer die aktuellen Werte in der zugrunde liegenden Quelle an, während Visuals, die auf die berechnete Tabelle verweisen, die Werte zu dem Zeitpunkt anzeigen, an dem die berechnete Tabelle zuletzt aktualisiert wurde.

## <a name="security-implications"></a>Folgen für die Sicherheit 

Zusammengesetzte Modelle haben Folgen für die Sicherheit. Eine an eine Datenquelle gesendete Abfrage kann Datenwerte enthalten, die von einer anderen Quelle abgerufen wurden. Für das zuvor in diesem Artikel beschriebene Beispiel führt das Visual, das *SalesAmount* nach *ProductManagers* anzeigt, dazu, dass eine SQL-Abfrage an die relationale Datenbank **Sales** gesendet wird, in der diese SQL-Abfrage möglicherweise die Namen der *ProductManagers* und die ihnen zugeordneten *Products* enthalten kann. 

![Skript mit den Folgen für die Sicherheit](media/desktop-composite-models/composite-models_17.png)

Aus diesem Grund werden die in der Tabelle gespeicherten Informationen nun in eine Abfrage eingefügt, die an die relationale Datenbank gesendet wird. Berücksichtigen Sie die genannten Folgen für die Sicherheit, wenn diese Informationen vertraulich sind. Insbesondere sollten Sie die folgenden Auswirkungen berücksichtigt werden:

* Ein Administrator der Datenbank, der Ablaufverfolgungen oder Überwachungsprotokolle sehen kann, würde diese Informationen auch dann sehen können, wenn dieser keine Berechtigungen für die Daten in ihrer ursprünglichen Quelle (in diesem Fall Berechtigungen für die Excel-Datei) besitzt.

* Die Verschlüsselungseinstellungen für die einzelnen Quellen sollten berücksichtigt werden, um zu verhindern, dass Informationen über eine verschlüsselte Verbindung von einer Quelle abgerufen werden, jedoch versehentlich in eine Abfrage eingeschlossen werden, die über eine unverschlüsselte Verbindung an eine andere Quelle gesendet wird. 

In **Power BI Desktop** wird als Bestätigung, dass die Folgen für die Sicherheit berücksichtigt wurden, eine Warnmeldung angezeigt, wenn eine Aktion zum Erstellen eines zusammengesetzten Modells ausgeführt wird.  

Aus ähnlichen Gründen müssen Sicherheitsvorkehrungen getroffen werden, wenn eine **Power BI Desktop**-Datei geöffnet wird, die nicht von einer vertrauenswürdigen Quelle gesendet wurde. Wenn diese Datei zusammengesetzte Modelle enthält, bedeutet dies, dass Informationen, die von einer Quelle (mit den Anmeldeinformationen des Benutzers, der die Datei öffnet) abgerufen wurden, als Teil der Abfrage an eine andere Datenquelle gesendet werden (diese können dann möglicherweise vom böswilligen Ersteller der Power BI Desktop-Datei eingesehen werden). Wenn eine Power BI Desktop-Datei, die mehrere Quellen enthält, zum ersten Mal geöffnet wird, wird daher eine Warnung angezeigt. Diese Warnung ist mit der Warnung vergleichbar, die beim Öffnen einer Datei mit nativen SQL-Abfragen angezeigt wird.  

## <a name="performance-implications"></a>Folgen für die Leistung  

Bei der Verwendung von DirectQuery sollte stets die Leistung berücksichtigt werden, und zwar in erster Linie, um sicherzustellen, dass die Back-End-Quelle genügend Ressourcen aufweist, um ein zufriedenstellendes Benutzererlebnis bereitzustellen. Ein gutes Erlebnis bedeutet, dass Visuals in max. 5 Sekunden aktualisiert sein sollten. Zudem sollten Sie den Hinweis hinsichtlich der Leistung im Artikel [Verwendung von DirectQuery in Power BI](desktop-directquery-about.md) berücksichtigen. Bei der Verwendung von zusammengesetzten Modellen müssen weitere Punkte hinsichtlich der Leistung berücksichtigt werden, da ein einzelnes Visual bewirken kann, dass Abfragen an mehrere Quellen gesendet werden, wobei häufig Ergebnisse von einer Abfrage an eine zweite Quelle übergeben werden. Diese Situation kann in den folgenden möglichen Ausführungsformen eintreten:

* **Eine SQL-Abfrage, die eine große Anzahl von Literalwerten enthält**: Beispielsweise müsste ein Visual, das den gesamten *SalesAmount* (aus SQL-Datenbank) für eine Gruppe von ausgewählten *ProductManagers* (aus der verknüpften Tabelle, die aus einem Arbeitsblatt importiert wurde) anfordert, zuerst ermitteln, welche *Products* von diesen Produktmanagern verwaltet wurden, bevor eine SQL-Abfrage mit allen Produkt-IDs in einer *WHERE*-Klausel gesendet wird.

* **Eine SQL-Abfrage, die auf einer niedrigeren Granularitätsebene ausgeführt wird und bei der Daten dann lokal aggregiert werden**: Basierend auf dem gleichen Beispiel wie im vorherigen Aufzählungspunkt in dieser Liste ist es an einem bestimmten Punkt ineffizient oder unmöglich bei steigender *Products*-Anzahl, die dem Filter für *ProductManagers* entsprechen, alle in einer *WHERE*-Klausel einzuschließen. Stattdessen muss die relationale Quelle auf der unteren *Product*-Ebene abgefragt werden, und die Ergebnisse müssen dann lokal aggregiert werden. Wenn die Kardinalität der *Produkte* einen Grenzwert von 1 Million überschreitet, tritt bei der Abfrage ein Fehler auf.

* **Mehrere SQL-Abfragen, eine pro Gruppe nach Wert**: Wenn die Aggregation **DistinctCount** verwendet, gruppiert nach einer bestimmten Spalte aus einer anderen Quelle, muss eine SQL-Abfrage pro Gruppe nach Wert gesendet werden, wenn die externe Quelle keine effiziente Übergabe von vielen Literalwerten unterstützt, die die Gruppierung definieren. Beispielsweise müsste ein Visual, das eine andere *CustomerAccountNumber*-Anzahl (aus der SQL Server-Tabelle) von *ProductManagers* (aus der verknüpften Tabelle, die aus einer Tabelle importiert wurde) anfordert, die Details aus der Tabelle *ProductManagers* in der Abfrage übergeben, die an SQL Server gesendet wird. Bei anderen Quellen (z.B. Redshift) ist dies nicht möglich. In diesem Fall müsste eine SQL-Abfrage pro *Sales Manager* gesendet werden (bis zu einem bestimmten durchführbaren Grenzwert, bei dem die Abfrage bei Überschreitung einen Fehler verursachen würde). 

Jeder dieser Fälle bringt andere Folgen für die Leistung mit sich, wobei die jeweiligen Details je nach Datenquelle variieren können. Eine gute Faustregel lautet wie folgt: Wenn die Kardinalität der Spalten, die in einer zwei Quellen verknüpfenden Beziehung verwendet werden, weiterhin gering ausfällt (im vierstelligen Bereich), sollte die Leistung nicht sonderlich beeinträchtigt werden. Je größer die Kardinalität ausfällt, desto mehr Punkte müssen hinsichtlich der Auswirkungen auf die resultierende Leistung beachtet werden. 

Darüber hinaus hat die Verwendung von **m:n**-Beziehungen zur Folge, dass die Einzelwerte nicht lokal aggregiert werden, sondern dass für die einzelnen Ebenen der Gesamt- bzw. Zwischensumme separate Abfragen an die zugrunde liegende Quelle gesendet werden müssen. Daher würde ein einfaches Tabellenvisual mit Gesamtbeträgen anstelle von einer SQL-Abfrage zwei senden. 

## <a name="limitations-and-considerations"></a>Einschränkungen und Überlegungen

Bei diesem Release des Features **Zusammengesetzte Modelle** gibt es einige Einschränkungen.

Die folgenden mehrdimensionalen Quellen können nicht mit **zusammengesetzten Modellen** verwendet werden:

* SAP HANA
* SAP Business Warehouse
* SQL Server Analysis Services
* Power BI-Datasets

Wenn mithilfe von DirectQuery eine Verbindung mit diesen mehrdimensionalen Quellen hergestellt wird, können Sie weder eine Verbindung mit einer anderen DirectQuery-Quelle herstellen noch importierte Daten kombinieren.

Die bestehenden Einschränkungen für die Verwendung von DirectQuery gelten nach wie vor für die Verwendung des Features **Zusammengesetzte Modelle**. Viele dieser Einschränkungen gelten jetzt abhängig vom **Speichermodus** der Tabelle für eine einzelne Tabelle. Beispielsweise kann eine berechnete Spalte in einer importierten Tabelle auf andere Tabellen verweisen, wohingegen eine berechnete Spalte in einer DirectQuery-Tabelle nach wie vor nur auf Spalten in derselben Tabelle verweisen kann. Es gelten weitere Einschränkungen für das Modell als Ganzes, wenn eine der Tabellen im Modell DirectQuery enthält. Die Features **QuickInsights** und **Q&A** sind nicht für Modelle verfügbar, wenn eine der Tabellen den **Speichermodus** „DirectQuery“ aufweist. 

## <a name="next-steps"></a>Nächste Schritte

Die folgenden Artikeln enthalten weitere Informationen über zusammengesetzte Modelle sowie Details zu DirectQuery.

* [m:n Beziehungen in Power BI Desktop (Vorschauversion)](desktop-many-to-many-relationships.md)
* [Speichermodus in Power BI Desktop (Vorschauversion)](desktop-storage-mode.md)

Artikel zu DirectQuery:

* [Verwendung von DirectQuery in Power BI](desktop-directquery-about.md)
* [Von DirectQuery in Power BI unterstützte Datenquellen](desktop-directquery-data-sources.md)

