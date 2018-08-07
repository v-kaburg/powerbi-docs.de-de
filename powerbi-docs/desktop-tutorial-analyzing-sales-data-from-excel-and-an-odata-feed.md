---
title: 'Tutorial: Kombinieren von Daten aus Excel und einem OData-Feed in Power BI Desktop'
description: 'Tutorial: Kombinieren von Daten aus Excel und einem OData-Feed'
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: tutorial
ms.date: 05/21/2018
ms.author: v-thepet
LocalizationGroup: Learn more
ms.openlocfilehash: 0ec22bd142f7509935691ff7bfcd38cb51a04fb2
ms.sourcegitcommit: fbb7924603f8915d07b5e6fc8f4d0c7f70c1a1e1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/02/2018
ms.locfileid: "39280108"
---
# <a name="tutorial-combine-sales-data-from-excel-and-an-odata-feed"></a>Tutorial: Kombinieren von Umsatzdaten aus Excel und einem OData-Feed

Daten sind üblicherweise auf mehrere Datenquellen verteilt, z.B. Produktinformationen in einer und Umsatzinformationen in einer anderen Datenbank. Mit **Power BI Desktop** können Sie Daten aus verschiedenen Quellen kombinieren, um aufschlussreiche, überzeugende Datenanalysen und Visualisierungen zu erstellen. 

In diesem Tutorial lernen Sie, wie Sie Daten aus zwei Datenquellen kombinieren: einer Excel-Arbeitsmappe mit Produktinformationen und einem OData-Feed mit Auftragsdaten. Nachdem Sie die einzelnen Datasets importiert und die Schritte zur Transformation und Aggregation durchgeführt haben, verwenden Sie Daten aus beiden Quellen zum Erstellen eines Umsatzanalyseberichts mit interaktiven Visualisierungen. Diese Verfahren können auch auf SQL Server-Abfragen, CSV-Dateien und alle anderen Datenquellen in Power BI Desktop angewendet werden.

>[!NOTE]
>In Power BI Desktop gibt es oft mehrere Möglichkeiten zum Ausführen einer Aufgabe. Beispielsweise stehen viele Optionen des Menübands auch per Rechtsklick oder über das Menü **Weitere Optionen** für eine Spalte oder Zelle zur Verfügung. In den folgenden Schritten werden mehrere alternative Methoden beschrieben. 

## <a name="import-the-product-data-from-excel"></a>Importieren der Produktdaten aus Excel

Importieren Sie zunächst die Produktdaten aus der Excel-Arbeitsmappe „Products.xlsx“ in Power BI Desktop.

1. [Laden Sie die Excel-Arbeitsmappe „Products.xlsx“ herunter](http://download.microsoft.com/download/1/4/E/14EDED28-6C58-4055-A65C-23B4DA81C4DE/Products.xlsx), und speichern Sie sie als **Products.xlsx**.
   
2. Klicken Sie im Power BI Desktop-Menüband auf der Registerkarte **Start** auf den Dropdownpfeil neben **Daten abrufen**, und wählen Sie dann in der Dropdownliste **Am häufigsten verwendet** den Eintrag **Excel** aus. 
   
   ![Daten abrufen](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_1.png)
   
   >[!NOTE]
   >Sie können auch das Element **Daten abrufen** selbst auswählen oder im Power BI-Dialogfeld **Erste Schritte** die Option **Daten abrufen** wählen und dann im Dialogfeld **Daten abrufen** auf **Excel** oder **Datei** > **Excel** klicken und **Verbinden** auswählen.
   
3. Navigieren Sie im Dialogfeld **Öffnen** zur Datei **Products.xlsx**, und wählen Sie sie aus. Klicken Sie dann auf **Öffnen**.
   
4. Wählen Sie im Bereich **Navigator** die Tabelle **Produkte** aus, und wählen Sie dann **Bearbeiten**aus.
   
   ![Navigatorbereich für Excel](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_2.png)
   
Eine Vorschau der Tabelle wird im **Power Query-Editor** geöffnet, in dem Sie Transformationen zum Bereinigen der Daten anwenden können. 
   
![Power Query-Editor](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_3.png)
   
>[!NOTE]
>Sie können den **Power Query-Editor** auch öffnen, indem Sie in Power BI Desktop im Menüband **Start** auf **Abfragen bearbeiten** > **Abfragen bearbeiten** klicken, indem Sie mit der rechten Maustaste klicken oder indem Sie neben einer Abfrage in der **Berichtsansicht** auf **Weitere Optionen** klicken und **Abfrage bearbeiten** auswählen.

## <a name="clean-up-the-products-columns"></a>Bereinigen der Produktspalten

Ihr kombinierter Bericht verwendet nur die Spalten **ProductID**, **ProductName**, **QuantityPerUnit** und **UnitsInStock** aus der Excel-Arbeitsmappe. Die übrigen Spalten können Sie daher entfernen. 

1. Wählen Sie im **Power Query-Editor** die Spalten **ProductID**, **ProductName**, **QuantityPerUnit** und **UnitsInStock** aus. (Verwenden Sie **STRG**+**Klicken**, um mehrere Spalten auszuwählen, bzw. **UMSCHALT**+**Klicken**, um Spalten auszuwählen, die nebeneinander liegen.)
   
2. Klicken Sie mit der rechten Maustaste auf eine der ausgewählten Überschriften, und wählen Sie **Andere Spalten entfernen** aus der Dropdownliste aus, um alle außer den ausgewählten Spalten aus der Tabelle zu entfernen. 
   Sie können auch im Menüband auf der Registerkarte **Start** in der Gruppe **Spalten verwalten** auf **Spalten entfernen** > **Andere Spalten entfernen** klicken. 
   
   ![Andere Spalten entfernen](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/analyzingsalesdata_removeothercolumns.png)

## <a name="import-the-order-data-from-an-odata-feed"></a>Importieren der Auftragsdaten aus einem OData-Feed

Importieren Sie als Nächstes die Auftragsdaten aus dem OData-Feed des Northwind-Beispielvertriebssystems. 

1. Klicken Sie im **Power Query-Editor** auf **Neue Quelle**, und wählen Sie dann **OData-Feed** aus der Dropdownliste **Am häufigsten verwendet**. 
   
   ![Abrufen von OData](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/get_odata.png)
   
2. Fügen Sie im Dialogfeld **OData-Feed** die URL für den Northwind-OData-Feed ein (`http://services.odata.org/V3/Northwind/Northwind.svc/`), und wählen Sie **OK**.
   
   ![Dialogfeld „OData-Feed“](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/get_odata2.png)
   
3. Wählen Sie im Bereich **Navigator** die Tabelle **Orders** aus, und wählen Sie dann **OK**, um die Daten in den **Power Query-Editor** zu laden.
   
   ![Navigatorbereich für OData](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/analyzingsalesdata_odatafeed.png)
   
   >[!NOTE]
   >Um eine Vorschau anzuzeigen, können Sie im **Navigator** einen beliebigen Tabellennamen auswählen, ohne das Kontrollkästchen zu aktivieren.

## <a name="expand-the-order-data"></a>Erweitern der Auftragsdaten

Beim Herstellen einer Verbindung mit Datenquellen, die mehrere Tabellen enthalten (z.B. relationale Datenbanken oder der Northwind-OData-Feed), können Sie Verweise zwischen Tabellen verwenden, um Ihre Abfragen zu erstellen. Die Tabelle **Orders** enthält Verweise auf mehrere verknüpfte Tabellen. Sie können die Spalten **ProductID**, **UnitPrice** und **Quantity** aus der verknüpften Tabelle **Order_Details** über den Vorgang **Erweitern** der Betrefftabelle (**Orders**) hinzufügen. 

1. Scrollen Sie in der Tabelle **Orders** nach rechts, bis Sie die Spalte **Order_Details** sehen. Beachten Sie, dass sie anstelle von Daten Verweise auf eine andere Tabelle enthält.
   
   ![Spalte „Order_Details“](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/7.png)
   
2. Klicken Sie in der Spaltenüberschrift **Order_Details** auf das Symbol **Erweitern** (![Symbol Erweitern](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/expand.png)). 
   
3. In der Dropdownliste **Erweitern** :
   
   1. Wählen Sie **(Alle Spalten auswählen)** aus, um alle Spalten zu deaktivieren.
      
   2. Wählen Sie **ProductID**, **UnitPrice** und **Quantity** aus, und klicken Sie dann auf **OK**.
      
      ![Dialogfeld „Erweitern“](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/8.png)

Nach dem Erweitern der Tabelle **Order_Details** wird die Spalte **Order_Details** durch die drei neuen Spalten aus der geschachtelten Tabelle ersetzt, und die Tabelle enthält neue Zeilen für die hinzugefügten Daten aus den einzelnen Aufträgen. 

![Erweiterte Spalten](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/9.png)

## <a name="create-a-custom-calculated-column"></a>Erstellen einer benutzerdefinierten berechneten Spalte

Im Power Query-Editor können Sie Berechnungen und benutzerdefinierte Felder erstellen, um Ihre Daten anzureichern. Sie erstellen eine benutzerdefinierte Spalte zum Berechnen des Gesamtpreises für die einzelnen Zeilenelemente in einem Auftrag, indem der Einzelpreis mit der Artikelanzahl multipliziert wird.

1. Wählen Sie im Power Query-Editor im Menüband auf der Registerkarte **Spalte hinzufügen** die Option **Benutzerdefinierte Spalte**.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/10.png)
   
2. Geben Sie im Dialogfeld **Benutzerdefinierte Spalte** im Feld **Neuer Spaltenname** den Text **LineTotal** ein.

3. Geben Sie im Feld **Benutzerdefinierte Spaltenformel** nach dem **=** Folgendes ein: **[Order_Details.UnitPrice]** \* **[Order_Details.Quantity]**. (Sie können die Feldnamen auch aus dem Scrollfeld **Verfügbare Spalten** auswählen und auf **<< Einfügen** klicken, statt sie einzugeben.) 
3. Wählen Sie **OK**aus.
   
   ![Dialogfeld „Benutzerdefinierte Spalte“](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/11.png)

Das neue Feld **LineTotal** wird als letzte Spalte in der Tabelle **Orders** angezeigt.

## <a name="set-the-data-type-for-the-new-field"></a>Festlegen des Datentyps für das neue Feld

Wenn der Power Query-Editor eine Verbindung mit Daten herstellt, legt er für jedes Feld den idealen Datentyp fest und zeigt die Daten entsprechend an. Die den Feldern zugewiesenen Datentypen erkennen Sie an den Symbolen in den Überschriften, oder Sie finden sie unter **Datentyp** in der Gruppe **Transformieren** im Menüband auf der Registerkarte **Start**. 

Die neue Spalte **LineTotal** weist den Datentyp **Beliebig** auf, die Werte sind jedoch vom Typ „Währung“. Klicken Sie zum Zuweisen eines Datentyps mit der rechten Maustaste auf die Spaltenüberschrift **LineTotal**, wählen Sie in der Dropdownliste den Eintrag **Datentyp ändern**, und klicken Sie dann auf **Feste Dezimalzahl**. 

![Ändern des Datentyps](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/12.png)

>[!NOTE]
>Sie können auch die Spalte **LineTotal** auswählen, dann im Menüband auf der Registerkarte **Start** im Bereich **Transformieren** auf den Dropdownpfeil neben **Datentyp** klicken und dann **Feste Dezimalzahl** auswählen.

## <a name="clean-up-the-orders-columns"></a>Bereinigen der Auftragsspalten

Um das Modell für die Bearbeitung in Berichten zu vereinfachen, können Sie einige der Spalten löschen, umbenennen und neu anordnen.

Ihr Bericht verwendet nur die Spalten **OrderDate**, **ShipCity**, **ShipCountry**, **Order_Details.ProductID**, **Order_Details.UnitPrice** und **Order_Details.Quantity**. Wie bei den Excel-Daten können Sie diese Spalten auswählen und **Andere Spalten entfernen** wählen, oder Sie können alle Spalten mit Ausnahme der aufgelisteten Spalten auswählen, mit der rechten Maustaste auf eine der ausgewählten Spalten klicken und **Spalten entfernen** wählen, um die Spalten zu entfernen. 

Die Spalten **Order_Details.ProductID**, **Order_Details.UnitPrice** und **Order_Details.Quantity** sind leichter zu identifizieren, wenn Sie das Präfix *Order_Details.* aus den Spaltennamen entfernen. So benennen Sie die Spalten in **ProductID**, **UnitPrice** bzw. **Quantity** um:

1. Doppelklicken Sie auf die einzelnen Spaltenüberschriften, oder halten Sie sie gedrückt, oder klicken Sie mit der rechten Maustaste auf die Spaltenüberschrift, und klicken Sie in der Dropdownliste auf **Umbenennen**. 
2. Löschen Sie das Präfix *Order_Details.* aus den einzelnen Namen, und drücken Sie dann die **EINGABETASTE**.

Um schließlich den Zugriff auf die Spalte **LineTotal** zu vereinfachen, ziehen Sie sie nach links, und legen Sie sie rechts neben der Spalte **ShipCountry** ab.

![Bereinigte Tabelle](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/14.png)

## <a name="review-the-query-steps"></a>Überprüfen der Abfrageschritte

Während Sie Daten im Power Query-Editor strukturiert und transformiert haben, wurde jeder Schritt auf der rechten Seite des Power Query-Editors im Bereich **Abfrageeinstellungen** im Abschnitt **Angewendete Schritte** aufgezeichnet. Sie können durch die angewendeten Schritte zurückgehen, um die vorgenommenen Änderungen zu überprüfen, und sie bei Bedarf bearbeiten, löschen oder neu anordnen (obwohl dies riskant sein kann, da das Ändern vorhergehender Schritte spätere Schritte beeinträchtigen kann). 

Wählen Sie die einzelnen Abfragen in der Liste **Abfragen** auf der linken Seite des Power Query-Editors aus, und überprüfen Sie die Schritte unter **Angewendete Schritte** in den **Abfrageeinstellungen**. Nach dem Anwenden der vorherigen Datentransformationen sollte der Abschnitt „Angewendete Schritte“ für Ihre beiden Abfragen wie folgt aussehen:

![Produktabfrage: angewendete Schritte](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/15.png) &nbsp;&nbsp; ![Auftragsabfrage: angewendete Schritte](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/17.png)

>[!TIP]
>Den angewendeten Schritten liegen Formeln zugrunde, die in der **Power Query-Sprache**, auch bekannt als **M**-Sprache, geschrieben sind. Zum Anzeigen und Bearbeiten der Formeln wählen Sie in der Registerkarte „Start“ des Menübands in die Gruppe **Abfrage** die Option **Erweiterter Editor**. 

## <a name="import-the-transformed-queries"></a>Importieren der transformierten Abfragen

Wenn Sie mit den transformierten Daten zufrieden sind, klicken Sie auf der Registerkarte **Start** des Menübands in der Gruppe **Schließen** auf **Schließen und übernehmen** > **Schließen und übernehmen**, um die Daten in die Berichtsansicht von Power BI Desktop zu importieren. 

![Schließen und übernehmen](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_4.png)

Sobald die Daten geladen wurden, werden die Abfragen in der Liste **Felder** in der Berichtsansicht von Power BI Desktop angezeigt.

![Abfragen in der Liste „Felder“](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/18.png)

## <a name="manage-the-relationship-between-the-datasets"></a>Verwalten der Beziehung zwischen den Datasets

Sie müssen in Power BI Desktop keine Abfragen kombinieren, um für diese einen Bericht zu erstellen. Allerdings können Sie die Beziehungen zwischen Datasets, die auf gemeinsamen Feldern beruhen, zum Erweitern und Anreichern Ihre Berichte nutzen. Power BI Desktop kann Beziehungen automatisch erkennen, oder Sie können diese im Power BI Desktop-Dialogfeld **Beziehungen verwalten** erstellen. Weitere Informationen über Beziehungen in Power BI Desktop finden Sie unter [Erstellen und Verwalten von Beziehungen](desktop-create-and-manage-relationships.md).

Die Datasets „Orders“ und „Products“ in diesem Tutorial verwenden ein gemeinsames Feld *ProductID*, daher liegt zwischen ihnen eine Beziehung vor, die auf dieser Spalte beruht. 

1. Klicken Sie in der Berichtsansicht von Power BI Desktop im Menüband auf der Registerkarte **Start** im Bereich **Beziehungen** auf **Beziehungen verwalten**.
   
   ![Menüband „Beziehungen verwalten“](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_5.png)
   
2. Beachten Sie im Dialogfeld **Beziehungen verwalten**, dass Power BI Desktop bereits eine aktive Beziehung zwischen den Tabellen „Products“ und „Orders“ erkannt und aufgeführt hat. Klicke Sie zum Anzeigen der Beziehung auf **Bearbeiten**. 
   
   ![Dialogfeld „Beziehungen verwalten“](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_6.png)
   
   Das Dialogfeld **Beziehung bearbeiten** wird geöffnet und zeigt Details über die Beziehung an.  
   
   ![Dialogfeld „Beziehung bearbeiten“](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_7.png)
   
3. Power BI Desktop hat die Beziehung automatisch richtig erkannt, daher können Sie auf **Abbrechen** und dann auf **Schließen** klicken, um die Beziehungsdialogfelder zu beenden.

Sie können auch die Beziehungen zwischen Ihren Abfragen anzeigen und verwalten, indem Sie die Ansicht **Beziehung** auf der linken Seite des Power BI Desktop-Fensters auswählen. Doppelklicken Sie auf den Pfeil auf der Verbindungslinie zwischen den beiden Abfragen, um das Dialogfeld **Beziehung bearbeiten** zu öffnen und die Beziehung anzuzeigen oder zu ändern. 

![Beziehungsansicht](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_8.png)

Um von der Beziehungsansicht wieder zur Berichtsansicht zu wechseln, klicken Sie auf das Symbol **Berichtsansicht**. 

![Symbol für Berichtsansicht](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_9.png)

## <a name="create-visualizations-using-your-data"></a>Erstellen von Visualisierungen mithilfe Ihrer Daten

In der Berichtsansicht von Power BI Desktop können Sie eine Vielzahl von Visualisierungen erstellen, um Erkenntnisse aus Ihren Daten zu gewinnen. Sie können Berichte mit mehreren Seiten erstellen, und jede Seite kann mehrere Visuals enthalten. Sie und andere können mit den Visualisierungen interagieren, um die Daten einfacher zu analysieren und zu verstehen. Weitere Informationen über das Anzeigen und Bearbeiten von Berichten im Power BI-Dienst (Ihrer Website) finden Sie unter [Bearbeiten eines Berichts](service-interact-with-a-report-in-editing-view.md).

Sie können beide Datasets und die Beziehung zwischen ihnen verwenden, um Ihre Vertriebsdaten zu visualisieren und zu analysieren. 

Erstellen Sie zunächst ein gestapeltes Säulendiagramm, das Felder aus beiden Abfragen verwendet, um die Menge der einzelnen bestellten Produkte anzuzeigen. 

1. Wählen Sie auf der rechten Seite im Bereich **Felder** unter **Orders** das Feld **Quantity** aus, oder ziehen Sie es auf einen leeren Bereich der Canvas. Dadurch wird ein gestapeltes Säulendiagramm erstellt, das die Gesamtmenge aller bestellten Produkte anzeigt. 
   
2. Klicken Sie im Bereich **Felder** unter **Products** auf **ProductName**, oder ziehen Sie das Element auf das Diagramm, um die Menge der einzelnen bestellten Produkte anzuzeigen. 
   
3. Um die Produkte von den meistbestellten bis zu den am wenigsten bestellten zu sortieren, wählen Sie oben rechts in der Visualisierung die Auslassungspunkte **Weitere Optionen** (**...**), und klicken Sie dann auf **Sortieren nach „Quantity“**.
   
4. Verwenden Sie die Handles an den Ecken des Diagramms, um es zu vergrößern, sodass weitere Produktnamen angezeigt werden. 
   
   ![Balkendiagramm mit der Menge nach ProductName](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/19.png)

Als Nächstes erstellen Sie ein Diagramm mit den Geldbeträgen der Aufträge (**LineTotal**) im Zeitverlauf (**OrderDate**). 

1. Während in der Canvas nichts ausgewählt ist, klicken Sie im Bereich **Felder** unter **Orders** auf **LineTotal**, oder ziehen Sie das Element in einen leeren Bereich der Canvas. Das gestapelte Säulendiagramm zeigt den Gesamtbetrag aller Aufträge an. 
   
2. Während das Diagramm ausgewählt ist, klicken Sie unter **Orders** auf **OrderDate**, oder ziehen Sie das Element auf das Diagramm. Das Diagramm zeigt jetzt Zeilengesamtwerte für jedes Auftragsdatum an. 
   
3. Ändern Sie die Größe der Visualisierung durch Ziehen der Ecken, um weitere Daten anzuzeigen. 
   
   ![Liniendiagramm „LineTotals nach OrderDate“](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/20.png)
   
   >[!TIP]
   >Wenn im Diagramm nur Jahre angezeigt werden (nur drei Datenpunkte), klicken Sie im Bereich **Visualisierungen** im Feld **Achse** auf den Pfeil neben **OrderDate**, und wählen Sie **OrderDate** anstelle von **Datumshierarchie** aus. 

Erstellen Sie abschließend eine Kartenvisualisierung, die die Auftragsmengen aus den einzelnen Ländern zeigt. 

1. Während in der Canvas nichts ausgewählt ist, klicken Sie im Bereich **Felder** unter **Orders** auf **ShipCountry**, oder ziehen Sie das Element in einen leeren Bereich der Canvas. Power BI Desktop erkennt, dass es sich bei den Daten um Ländernamen handelt, und erstellt automatisch eine Kartenvisualisierung mit einem Datenpunkt für jedes Land, in dem Aufträge erteilt wurden. 
   
2. Damit die Größe der Datenpunkte die Auftragsmengen für die einzelnen Länder widerspiegelt, ziehen Sie das Feld **LineTotal** auf die Karte (oder ziehen Sie es auf **Datenfelder hierher ziehen** unter **Größe** in der unteren Hälfte des Bereichs **Visualisierungen**). Die Größen der Kreise auf der Karte geben jetzt die Geldbeträge der Aufträge aus den einzelnen Länder wieder. 
   
   ![Kartenvisualisierung „LineTotals nach ShipCountry“](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/21.png)

## <a name="interact-with-your-report-visuals-to-analyze-further"></a>Interagieren mit Berichtsvisuals zur weiteren Analyse

Mithilfe von Power BI Desktop können Sie mit Visuals interagieren, die sich gegenseitig hervorheben und filtern, um so weitere Trends zu erkennen. Weitere Informationen finden Sie unter [Filtern und Hervorheben in Berichten](power-bi-reports-filters-and-highlighting.md) 

Aufgrund der Beziehung zwischen Ihren Abfragen wirken sich Interaktionen mit einer Visualisierung auf alle anderen Visualisierungen auf der Seite aus. 

Wählen Sie auf der Kartenvisualisierung den Kreis aus, der mitten in **Kanada** liegt. Beachten Sie, dass die beiden anderen Visualisierungen so gefiltert werden, dass sie die Zeilengesamtwerte und Auftragsmengen ausschließlich für Kanada anzeigen.

![Für Kanada gefilterte Vertriebsdaten](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/22.png)

Bei Auswahl eines der Produkte im Diagramm **Quantity nach ProductName** werden die Karte und das Datumsdiagramm so gefiltert, dass sie die Daten für das jeweilige Produkt darstellen. Bei Auswahl eines der Datumswerte im Diagramm **LineTotal nach OrderDate** werden die Karte und das Produktdiagramm so gefiltert, dass sie die Daten für das jeweilige Datum anzeigen. 
>[!TIP]
>Um eine Auswahl aufzuheben, wählen Sie sie erneut aus, oder wählen Sie eine der anderen Visualisierungen. 

## <a name="complete-the-sales-analysis-report"></a>Abschließen des Umsatzanalyseberichts

Im fertig gestellten Bericht werden Daten aus der Excel-Datei „Products.xlsx“ und dem Northwind-OData-Feed in Visuals kombiniert, die die Analyse von Auftragsinformationen für verschiedene Länder, Zeitrahmen und Produkte ermöglichen. Wenn Ihr Bericht fertig ist, können Sie ihn [in den Power BI-Dienst hochladen](desktop-upload-desktop-files.md), um ihn für andere Power BI-Benutzer freizugeben.

## <a name="next-steps"></a>Nächste Schritte
* [Weitere Tutorials zu Power BI Desktop lesen](http://go.microsoft.com/fwlink/?LinkID=521937)
* [Videos zu Power BI Desktop ansehen](http://go.microsoft.com/fwlink/?LinkID=519322)
* [Power BI-Forum besuchen](http://go.microsoft.com/fwlink/?LinkID=519326)
* [Power BI-Blog lesen](http://go.microsoft.com/fwlink/?LinkID=519327)