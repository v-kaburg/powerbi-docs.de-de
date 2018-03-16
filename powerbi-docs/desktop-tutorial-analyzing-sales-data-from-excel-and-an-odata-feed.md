---
title: 'Tutorial: Analysieren von Umsatzdaten aus Excel und einem OData-Feed in Power BI Desktop'
description: 'Lernprogramm: Analysieren von Umsatzdaten aus Excel und einem OData-Feed'
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
LocalizationGroup: Learn more
ms.openlocfilehash: 4cab3ed114d03d42c6acf1bf62f70e7d920e16b2
ms.sourcegitcommit: d91b7bf18d5c504037134f375886633379f28ede
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/27/2018
---
# <a name="tutorial-analyzing-sales-data-from-excel-and-an-odata-feed"></a>Lernprogramm: Analysieren von Umsatzdaten aus Excel und einem OData-Feed
Mit **Power BI Desktop** können Sie Verbindungen mit allen Arten unterschiedlicher Datenquellen herstellen und diese dann in einer Weise kombinieren und formen, die es ermöglicht, interessante und überzeugende Datenanalysen und Visualisierungen zu erstellen. In diesem Tutorial erfahren Sie, wie Sie Daten aus zwei Datenquellen kombinieren. 

Es ist üblich, die Daten auf mehrere Datenquellen zu verteilen, z. B. Produktinformationen in einer Datenbank, während sich die Umsatzinformationen in einer anderen Datenbank befinden. Die Techniken, die in diesem Dokument vorgestellt werden, beziehen sich auf eine Excel-Arbeitsmappe und einen OData-Feed, können aber auch auf andere Datenquellen wie SQL Server-Abfragen, CSV-Dateien oder eine beliebige Datenquelle in Power BI Desktop angewendet werden.

In diesem Tutorial importieren Sie Daten aus Excel (dies sind Produktinformationen) und aus einem OData-Feed (der die Auftragsdaten enthält). Sie werden Transformations- und Aggregationsschritte durchführen und Daten aus beiden Quellen kombinieren, um einen Bericht zum **Gesamtumsatz pro Produkt und Jahr** zu erstellen, der interaktive Visualisierungen einbezieht. 

Der fertige Bericht wird wie folgt aussehen:

![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/18.png)

Damit Sie die Schritte in diesem Tutorial ausführen können, benötigen Sie die Arbeitsmappe „Produkte“, die Sie herunterladen können: **[Klicken Sie hier, um die Datei „Products.xlsx“ herunterzuladen](http://download.microsoft.com/download/1/4/E/14EDED28-6C58-4055-A65C-23B4DA81C4DE/Products.xlsx)**.

Weisen Sie der Datei im Dialogfeld **Speichern unter** die Bezeichnung **Products.xlsx**zu.

## <a name="task-1-get-product-data-from-an-excel-workbook"></a>Aufgabe 1: Abrufen von Produktdaten aus einer Excel-Arbeitsmappe
In dieser Aufgabe importieren Sie Produkte aus der Datei „Products.xlsx“ in Power BI Desktop.

### <a name="step-1-connect-to-an-excel-workbook"></a>Schritt 1: Herstellen der Verbindung mit einer Excel-Arbeitsmappe
1. Starten Sie Power BI Desktop.
2. Wählen Sie im Menüband „Start“ den Befehl **Daten abrufen**aus. Excel ist eine der **Am häufigsten verwendeten** Datenverbindungen, sodass Sie diese direkt im Menü **Daten abrufen** auswählen können.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_1.png)
3. Wenn Sie die Schaltfläche „Daten abrufen“ direkt auswählen, können Sie auch **Datei \> Excel** und dann **Verbinden** auswählen.
4. Wählen Sie im Dialogfeld **Datei öffnen** die Datei **Products.xlsx** aus.
5. Wählen Sie im Bereich **Navigator** die Tabelle **Produkte** aus, und wählen Sie dann **Bearbeiten**aus.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_2.png)

### <a name="step-2-remove-other-columns-to-only-display-columns-of-interest"></a>Schritt 2: Entfernen sonstiger Spalten zur ausschließlichen Anzeige relevanter Spalten
In diesem Schritt entfernen Sie alle Spalten außer **ProductID**, **ProductName**, **UnitsInStock**und **QuantityPerUnit**. In Power BI Desktop gibt es oft mehrere Möglichkeiten zum Ausführen einer Aufgabe. Beispielsweise lassen sich viele Schaltflächen im Menüband auch erreichen, indem das Kontextmenü für eine Spalte oder Zelle verwendet wird.

Power BI Desktop umfasst den Abfrage-Editor, der die Komponente ist, in der Sie Ihre Datenquellen formen und transformieren. Der Abfrage-Editor wird automatisch geöffnet, wenn Sie **Bearbeiten** im **Navigator**auswählen. Sie können den Abfrage-Editor auch öffnen, indem Sie in Power BI Desktop im Menüband **Start** den Befehl **Abfragen bearbeiten** auswählen. Die folgenden Schritte werden im Abfrage-Editor ausgeführt.

1. Wählen Sie im Abfrage-Editor die Spalten **ProductID**, **ProductName**, **QuantityPerUnit**und **UnitsInStock** aus (verwenden Sie **STRG+Klicken** , um mehrere Spalten auszuwählen, oder **UMSCHALT+Klicken** , um Spalten auszuwählen, die nebeneinander liegen).
2. Wählen Sie im Menüband den Befehl **Spalten entfernen**\>**Andere Spalten entfernen**aus, oder klicken Sie mit der rechten Maustaste auf eine Spaltenüberschrift, und klicken Sie dann auf **Andere Spalten entfernen**.

![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/anlayzingsalesdata_removeothercolumns.png)

### <a name="step-3-change-the-data-type-of-the-unitsinstock-column"></a>Schritt 3: Ändern des Datentyps der Spalte „UnitsInStock“
Wenn der Abfrage-Editor eine Verbindung mit Daten herstellt, prüft er jedes Feld, um den besten Datentyp zu ermitteln. Für die Excel-Arbeitsmappe werden die auf Lager befindlichen Produkte immer mit ganzen Zahlen angegeben, weshalb Sie in diesem Schritt bestätigen, dass die Spalte **UnitsInStock** den Datentyp „Ganze Zahl“ hat.

1. Wählen Sie die Spalte **UnitsInStock** aus.
2. Klicken Sie im Menüband **Start** auf die Dropdown-Schaltfläche **Datentyp** .
3. Wenn nicht bereits „Ganze Zahl“ angezeigt wird, wählen Sie in der Dropdownliste „Datentyp“ den Typ **Ganze Zahl** aus (die Schaltfläche **Datentyp:** zeigt auch den Datentyp für die aktuelle Auswahl an).
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/anlayzingsalesdata_wholenumber.png)      

### <a name="power-bi-desktop-steps-created"></a>Erstellte Schritte in Power BI Desktop
Beim Ausführen von Abfrageaktivitäten im Abfrage-Editor werden Abfrageschritte erstellt und im Bereich **Abfrageeinstellungen** in der Liste **Angewendete Schritte** aufgelistet. Jeder Abfrageschritt verfügt über eine entsprechende Formel, die auch als Sprache „M“ bezeichnet wird. Weitere Informationen zur Formelsprache „M“ finden Sie unter [Informationen zu Power BI-Formeln](https://support.office.com/Article/Learn-about-Power-Query-formulas-6bc50988-022b-4799-a709-f8aafdee2b2f).

| Aufgabe | Abfrageschritt | Formel |
| --- | --- | --- |
| Herstellen der Verbindung mit einer Excel-Arbeitsmappe |Quelle |Quelle{[Item="Products",Kind="Table"]}[Data] |
| Heraufstufen der ersten Zeile zu Tabellenspaltenüberschriften |FirstRowAsHeader |[Table.PromoteHeaders](https://support.office.com/Article/TablePromoteHeaders-b8eaeb95-042a-42e1-9164-6d3c646acadc "Table.PromoteHeaders") <br /> (Produkte) |
| Entfernen sonstiger Spalten zur ausschließlichen Anzeige relevanter Spalten |RemovedOtherColumns |[Table.SelectColumns](https://support.office.com/Article/TableSelectColumns-20bb9e28-9fd3-4cd2-a21b-97972c82ec22 "Table.SelectColumns")  <br />(FirstRowAsHeader,{"ProductID", "ProductName", "QuantityPerUnit", "UnitsInStock"}) |
| Geänderter Datentyp |Geänderter Typ |Table.TransformColumnTypes(\#"Removed Other Columns",{{"UnitsInStock", Int64.Type}}) |

## <a name="task-2-import-order-data-from-an-odata-feed"></a>Aufgabe 2: Importieren von Bestelldaten aus einem OData-Feed
In dieser Aufgabe lesen Sie die Bestelldaten ein. Dieser Schritt stellt das Herstellen der Verbindung mit einem Vertriebssystem dar. Sie importieren Daten in Power BI Desktop aus dem Northwind-OData-Beispielfeed unter der folgenden URL, die Sie kopieren und in einem der nächsten Schritte einfügen können: <http://services.odata.org/V3/Northwind/Northwind.svc/> 

### <a name="step-1-connect-to-an-odata-feed"></a>Schritt 1: Herstellen der Verbindung mit einem OData-Feed
1. Wählen Sie im Abfrage-Editor auf der Registerkarte des Menübands **Start** den Befehl **Daten abrufen** aus.
2. Navigieren Sie zu der **OData-Feed** -Datenquelle.
3. Fügen Sie im Dialogfeld **OData-Feed** die **URL** für den Northwind-OData-Feed ein.
4. Wählen Sie **OK**aus.
5. Wählen Sie im Bereich **Navigator** die Tabelle **Orders** aus, und wählen Sie dann **Bearbeiten**aus.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/anlayzingsalesdata_odatafeed.png)

>[!NOTE]
>Zum Anzeigen einer Vorschau können Sie auf einen Tabellennamen klicken, ohne das Kontrollkästchen zu aktivieren.

### <a name="step-2-expand-the-orderdetails-table"></a>Schritt 2: Erweitern der Tabelle „Order\_Details“
Die Tabelle **Orders** enthält einen Verweis auf eine Tabelle **Details** mit den einzelnen Produkten, die in den jeweiligen Aufträgen enthalten sind. Wenn Sie eine Verbindung mit einer Datenquellen herstellen, die mehrere Tabellen hat (z. B. eine relationale Datenbank), können Sie mithilfe dieser Verweise Ihre Abfrage erstellen. 

In diesem Schritt erweitern Sie die Tabelle **Order\_Details**, die mit der Tabelle **Orders** verknüpft ist, um die Spalten **ProductID**, **UnitPrice** und **Quantity** aus der Tabelle **Order\_Details** in der Tabelle **Orders** zu kombinieren. Dies ist eine Darstellung der Daten in diesen Tabellen:

![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/orderdetails.png)

Der Vorgang **Erweitern** kombiniert Spalten aus einer verknüpften Tabelle in einer Subjekttabelle. Wenn die Abfrage ausgeführt wird, werden Zeilen aus der verknüpften Tabelle (**Order\_Details**) mit Zeilen aus der Subjekttabelle (**Orders**) kombiniert.

Nachdem Sie die Tabelle **Order\_Details** erweitert haben, werden der Tabelle **Orders** drei neue Spalten und zusätzliche Zeilen hinzugefügt – eine für jede Zeile in der geschachtelten oder verknüpften Tabelle.

1. Scrollen Sie in der **Abfrageansicht** nach unten zur Spalte **Order\_Details**.
2. Wählen Sie in der Spalte **Order\_Details** das Erweiterungssymbol aus (![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/expand.png)).
3. In der Dropdownliste **Erweitern** :
   1. Wählen Sie **(Alle Spalten auswählen)** aus, um alle Spalten zu deaktivieren.
   2. Wählen Sie **ProductID**, **UnitPrice**und **Quantity**aus.
   3. Klicken Sie auf **OK**.
      ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/7.png)

### <a name="step-3-remove-other-columns-to-only-display-columns-of-interest"></a>Schritt 3: Entfernen sonstiger Spalten zur ausschließlichen Anzeige relevanter Spalten
In diesem Schritt entfernen Sie alle Spalten außer **OrderDate, ShipCity**, **ShipCountry**, **Order\_Details.ProductID**, **Order\_Details.UnitPrice** und **Order\_Details.Quantity**. In der vorherigen Aufgabe haben Sie **Andere Spalten entfernen**verwendet. Für diese Aufgabe entfernen Sie die ausgewählten Spalten.

1. Wählen Sie in der **Abfrageansicht** alle Spalten aus, indem Sie die Schritte a und b ausführen:
   1. Klicken Sie auf die erste Spalte (**OrderID**).
   2. Klicken Sie bei gedrückter UMSCHALTTASTE auf die letzte Spalte (**Shipper**).
   3. Klicken Sie nun, nachdem alle Spalten ausgewählt sind, bei gedrückter STRG-TASTE auf die folgenden Spalten, um ihre Auswahl aufzuheben: **OrderDate**, **ShipCity**, **ShipCountry**, **Order\_Details.ProductID**, **Order\_Details.UnitPrice** und **Order\_Details.Quantity**.
2. Nun sind nur die Spalten ausgewählt, die entfernt werden sollen. Klicken Sie mit der rechten Maustaste auf eine der ausgewählten Spaltenüberschrift, und klicken Sie dann auf **Spalten entfernen**.

### <a name="step-4-calculate-the-line-total-for-each-orderdetails-row"></a>Schritt 4: Berechnen der Zwischensumme für jede Zeile in „Order\_Details“
Mit Power BI Desktop können Sie Berechnungen erstellen, die auf den von Ihnen importierten Spalten basieren, um die Daten optimal zu nutzen, mit denen Sie eine Verbindung herstellen. In diesem Schritt erstellen Sie eine **Benutzerdefinierte Spalte**, um die Zwischensumme für jede Zeile in **Order\_Details** zu berechnen.

Berechnen der Zwischensumme für jede Zeile in **Order\_Details**

1. Klicken Sie auf der Menübandregisterkarte **Spalte hinzufügen** auf **Benutzerdefinierte** **Spalte hinzufügen**.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_4.png)
2. Geben Sie im Dialogfeld **Benutzerdefinierte Spalte hinzufügen** im Textfeld **Benutzerdefinierte Spaltenformel** Folgendes ein: **[Order\_Details.UnitPrice] \* [Order\_Details.Quantity]**.
3. Geben Sie in das Textfeld **Neuer Spaltenname** den Namen **LineTotal**ein.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/8.png)
4. Klicken Sie auf **OK**.

### <a name="step-5-set-the-datatype-of-the-linetotal-field"></a>Schritt 5: Festlegen des Datentyps des Felds „LineTotal“
1. Klicken Sie mit der rechten Maustaste auf die Spalte **LineTotal** .
2. Wählen Sie **Typ ändern** und dann **Dezimalzahl** aus.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/9.png)

### <a name="step-6-rename-and-reorder-columns-in-the-query"></a>Schritt 6: Umbenennen und erneutes Anordnen von Spalten in der Abfrage
In diesem Schritt schließen Sie den Vorgang ab, das Modell für das Erstellen von Berichten einfach zu gestalten, indem Sie die abschließenden Spalten umbenennen und ihre Reihenfolge ändern.

1. Ziehen Sie im **Abfrage-Editor**die Spalte **LineTotal** nach links hinter die Spalte **ShipCountry**.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/10.png)
2. Entfernen Sie das Präfix *Order\_Details.* aus den Spalten **Order\_Details.ProductID**, **Order\_Details.UnitPrice** und **Order\_Details.Quantity**, indem Sie auf jede Spaltenüberschrift doppelklicken und diesen Text aus dem Spaltennamen löschen.

### <a name="power-bi-desktop-steps-created"></a>Erstellte Schritte in Power BI Desktop
Beim Ausführen von Abfrageaktivitäten im Abfrage-Editor werden Abfrageschritte erstellt und im Bereich **Abfrageeinstellungen** in der Liste **Angewendete Schritte** aufgelistet. Jeder Abfrageschritt verfügt über eine entsprechende Power Query-Formel, die auch als Sprache „M“ bezeichnet wird. Weitere Informationen zu dieser Formelsprache finden Sie unter [Informationen zu Power BI-Formeln](https://support.office.com/Article/Learn-about-Power-Query-formulas-6bc50988-022b-4799-a709-f8aafdee2b2f "Informationen zu Power Query-Formeln").

| Aufgabe | Abfrageschritt | Formel |
| --- | --- | --- |
| Herstellen einer Verbindung mit einem OData-Feed |Quelle |Quelle{[Name="Orders"]}[Data] |
| Erweitern der Tabelle „Order\_Details“ |Erweitern von „Order\_Details“ |[Table.ExpandTableColumn](https://support.office.com/Article/TableExpandTableColumn-54903f25-75a2-4a44-a9a3-52a9d895ee98 "Table.ExpandTableColumn") <br /> (Orders, "Order\_Details", {"ProductID", "UnitPrice", "Quantity"}, {"Order\_Details.ProductID", "Order\_Details.UnitPrice", "Order\_Details.Quantity"}) |
| Entfernen sonstiger Spalten zur ausschließlichen Anzeige relevanter Spalten |RemovedColumns |[Table.RemoveColumns](https://support.office.com/Article/TableRemoveColumns-6265190e-2f58-4300-85b8-df88fc1a67d3 "Table.RemoveColumns") <br />(\#"Expand Order\_Details",{"OrderID", "CustomerID", "EmployeeID", "RequiredDate", "ShippedDate", "ShipVia", "Freight", "ShipName", "ShipAddress", "ShipCity", "ShipRegion", "ShipPostalCode", "ShipCountry", "Customer", "Employee", "Shipper"}) |
| Berechnen der Zwischensumme für jede Zeile in „Order\_Details“ |InsertedColumn |[Table.AddColumn](https://support.office.com/Article/TableAddColumn-6c64d0a5-9654-4d15-bfb6-9cc380aaf3c0 "Table.AddColumn") <br /> (RemovedColumns, "Custom", each [Order\_Details.UnitPrice] \* [Order\_Details.Quantity]) |

## <a name="task-3-combine-the-products-and-total-sales-queries"></a>Aufgabe 3: Kombinieren der Abfragen für Produkte und Gesamtumsätze
Sie müssen in Power BI Desktop keine Abfragen kombinieren, um für diese einen Bericht zu erstellen. Sie können stattdessen **Beziehungen** zwischen Datasets erstellen. Diese Beziehungen können für eine beliebige Spalte erstellt werden, die Ihren Datasets gemeinsam ist. Weitere Informationen finden Sie unter [Erstellen und Verwalten von Beziehungen](desktop-create-and-manage-relationships.md).

In diesem Tutorial gibt es Auftrags- (Orders) und Produktdaten (Products), die das gemeinsame Feld „ProductID“ haben. Daher muss sichergestellt werden, dass es eine Beziehung zwischen diesen Daten in dem Modell gibt, das mit Power BI Desktop verwendet wird. Geben Sie in Power BI Desktop einfach an, dass die Spalten aus jeder Tabelle verknüpft sind (d. h. Spalten, die dieselben Werte haben). Power BI Desktop ermittelt die Richtung und Kardinalität der Beziehung für Sie. In einigen Fällen werden die Beziehungen sogar automatisch erkannt.

In dieser Aufgabe bestätigen Sie, dass in Power BI Desktop eine Beziehung zwischen den Abfragen **Products** und **Total Sales** eingerichtet ist.

### <a name="step-1-confirm-the-relationship-between-products-and-total-sales"></a>Schritt 1: Bestätigen der Beziehung zwischen „Products“ und „Total Sales“
1. Zunächst muss das Modell geladen werden, das im Abfrage-Editor in Power BI Desktop erstellt wurde. Wählen Sie im Abfrage-Editor auf der Registerkarte des Menübands **Start** den Befehl **Schließen & laden** aus.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_4.png)
2. Power BI Desktop lädt die Daten aus den beiden Abfragen.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/11.png)      
3. Nachdem die Daten geladen sind, wählen Sie auf der Menübandregisterkarte **Start** den Befehl **Beziehungen verwalten** aus.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_5.png)
4. Wählen Sie die Schaltfläche **Neu...** aus.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_6.png)
5. Wenn Sie versuchen, die Beziehung zu erstellen, sehen Sie, dass bereits eine Beziehung vorhanden ist. Wie im Dialogfeld **Beziehung erstellen** dargestellt (durch die schattierten Spalten), gibt es bereits eine Beziehung zwischen den **ProductsID** -Feldern in den beiden Abfragen.
   
    ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/12.png)
6. Wählen Sie **Abbrechen**aus, und wählen Sie dann die Ansicht **Beziehung** in Power BI Desktop aus.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_7.png)
7. Sie sehen die folgende Darstellung, die die Beziehung zwischen den Abfragen visualisiert.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_8.png)
8. Wenn Sie auf den Pfeil auf der Verbindungslinie der Abfragen doppelklicken, wird das Dialogfeld **Beziehung bearbeiten** angezeigt.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_9.png)
9. Es ist nicht erforderlich, irgendeine Änderung vorzunehmen, also wählen Sie einfach **Abbrechen** aus, um das Dialogfeld **Beziehung bearbeiten** zu schließen.

## <a name="task-4-build-visuals-using-your-data"></a>Aufgabe 4: Erstellen von Visualisierungen mithilfe Ihrer Daten
Mithilfe von Power BI Desktop können Sie eine Vielzahl von Visualisierungen erstellen, um Erkenntnisse aus Ihren Daten zu gewinnen. Sie können Berichte mit mehreren Seiten erstellen und jede Seite kann mehrere visuelle Elemente enthalten. Sie können mit den Visualisierungen interagieren, um dabei zu helfen, die Daten einfacher zu analysieren und zu verstehen. Weitere Informationen zum Bearbeiten von Berichten finden Sie unter [Bearbeiten eines Berichts](service-interact-with-a-report-in-editing-view.md).

In dieser Aufgabe erstellen Sie einen Bericht auf Basis der zuvor geladenen Daten. Sie können die Spalten, über die Sie die Visualisierungen erstellen, im Bereich „Felder“ auswählen.

### <a name="step-1-create-charts-showing-units-in-stock-by-product-and-total-sales-by-year"></a>Schritt 1: Erstellen von Diagrammen, die Einheiten im Bestand nach Produkt und Gesamtumsätzen pro Jahr anzeigen
Ziehen Sie **UnitsInStock** aus dem Bereich „Felder“ (dieser Bereich befindet sich am rechten Rand des Bildschirms) auf eine leere Stelle des Zeichenbereichs. Es wird eine Tabellenvisualisierung erstellt. Ziehen Sie nun „ProductName“ in das Feld „Achse“. Dieses befindet sich in der unteren Hälfte des Bereichs „Visualisierungen“. Wählen Sie dann über das Symbol mit den Auslassungspunkten, das sich in der rechten oberen Ecke der Visualisierung befindet, **Sortieren nach \> UnitsInStock** aus.

![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/14.png)

Ziehen Sie **OrderDate** auf den Zeichenbereich unter das erste Diagramm, ziehen Sie dann „LineTotal“ (ebenfalls aus dem Bereich „Felder“) auf das visuelle Objekt, und wählen Sie dann „Liniendiagramm“ aus. Die folgende Visualisierung wird erstellt.

![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/15.png)

 Ziehen Sie nun **ShipCountry** in einen Abschnitt oben rechts im Zeichenbereich. Da Sie ein geografisches Feld ausgewählt haben, wurde automatisch eine Karte erstellt. Ziehen Sie nun **LineTotal** in das Feld **Werte**. Die Kreise auf der Karte für jedes Land haben jetzt eine relative Größe in Bezug auf **LineTotal** für Aufträge, die an das jeweilige Land geliefert wurden.

![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/17.png)

### <a name="step-2-interact-with-your-report-visuals-to-analyze-further"></a>Schritt 2: Interagieren mit Berichtsvisualisierungen zur weiteren Analyse
Mithilfe von Power BI Desktop können Sie mit visuellen Elementen interagieren, die sich gegenseitig hervorheben und filtern, um weitere Trends zu erkennen. Weitere Informationen finden Sie unter [Filtern und Hervorheben in Berichten](power-bi-reports-filters-and-highlighting.md)

1. Klicken Sie auf den hellblauen Kreis, der zentriert in **Canad****a.** angezeigt wird Beachten Sie, wie die anderen visuellen Elemente gefiltert werden, um den Bestand (**ShipCountry**) und die gesamten Aufträge (**LineTotal**) ausschließlich für Kanada anzuzeigen.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/18.png)

## <a name="complete-sales-analysis-report"></a>Abschließen des Umsatzanalyseberichts
Nachdem Sie alle Schritte ausgeführt haben, verfügen Sie über einen Umsatzbericht, der die Daten aus der Datei „Products.xlsx“ und dem Northwind-OData-Feed kombiniert. Der Bericht zeigt Visualisierungen, die bei der Analyse der Umsatzdaten aus verschiedenen Ländern helfen. Sie können [hier](http://download.microsoft.com/download/1/4/E/14EDED28-6C58-4055-A65C-23B4DA81C4DE/Analyzing_Sales_Data.pbix) eine vollständige Power BI Desktop-Datei für dieses Tutorial herunterladen.

## <a name="next-steps"></a>Nächste Schritte
* [Weitere Tutorials zu Power BI Desktop lesen](http://go.microsoft.com/fwlink/?LinkID=521937)
* [Videos zu Power BI Desktop ansehen](http://go.microsoft.com/fwlink/?LinkID=519322)
* [Power BI-Forum besuchen](http://go.microsoft.com/fwlink/?LinkID=519326)
* [Power BI-Blog lesen](http://go.microsoft.com/fwlink/?LinkID=519327)


