---
title: 'Tutorial: Erstellen von berechneten Spalten in Power BI Desktop'
description: 'Tutorial: Erstellen von berechneten Spalten in Power BI Desktop'
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
ms.openlocfilehash: c99f4180d3c3034fb3a3a0332a4b3fa219028ea6
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2017
---
# <a name="tutorial-create-calculated-columns-in-power-bi-desktop"></a>Tutorial: Erstellen von berechneten Spalten in Power BI Desktop
Manchmal enthalten die Daten, die Sie analysieren, einfach nicht ein bestimmtes Feld, das Sie benötigen, um die gewünschten Ergebnisse zu erzielen. Hier bieten sich berechnete Spalten an. Berechnete Spalten verwenden DAX-Formeln (Data Analysis Expressions), um die Werte einer Spalte zu definieren. Diese Werte können so ziemlich alles sein, von zusammengesetzten Textwerten aus einem Paar verschiedener Spalten an anderen Stellen des Modells bis hin zu berechneten numerischen Werten aus anderen Werten. Angenommen, Ihre Daten weisen eine Spalte „City“ und eine Spalte „State“ auf (als Felder in der Feldliste), Sie möchten aber ein einzelnes Feld verwenden, das beide in einem einzelnen Wert enthält, wie etwa „Miami, FL“. Das ist genau der richtige Einsatzzweck für berechnete Spalten.

Berechnete Spalten ähneln Measures darin, dass beide auf einer DAX-Formel aufbauen, ihre Verwendung sich aber unterscheidet. Measures werden meistens im Bereich „Werte“ einer Visualisierung verwendet, um Ergebnisse auf der Grundlage anderer Felder zu berechnen, die in Form einer Zeile in einer Tabelle vorliegen, oder sie kommen im Bereich „Achse“, „Legende“ oder „Gruppe“ einer Visualisierung vor. Berechnete Spalten werden hingegen verwendet, wenn Sie die Ergebnisse der Spalte in einer Zeile der Tabelle oder im Bereich „Achse“, „Legende“ oder „Gruppe“ einer Visualisierung verwenden möchten.

Dieses Tutorial stellt Ihnen das Konzept vor und führt Sie durch das Erstellen eigener berechneter Spalten in Power BI Desktop. Es richtet sich an Power BI-Benutzer, die mit der Verwendung von Power BI Desktop zum Erstellen etwas fortgeschrittener Modelle bereits vertraut sind. Sie sollten bereits mit der Verwendung des Abfragemoduls zum Importieren von Daten, dem Arbeiten mit mehreren aufeinander bezogenen Tabellen und dem Hinzufügen von Feldern zur Berichtszeichenfläche vertraut sein. Wenn Sie noch nicht mit Power BI Desktop vertraut sind, sollten Sie [Erste Schritte mit Power BI Desktop](desktop-getting-started.md) lesen.

Um die Schritte in diesem Tutorial ausführen zu können, müssen Sie die Datei [Contoso Sales for Power BI Desktop](http://download.microsoft.com/download/4/6/A/46AB5E74-50F6-4761-8EDB-5AE077FD603C/Contoso%20Sales%20Sample%20for%20Power%20BI%20Desktop.zip) herunterladen. Dies ist die gleiche Beispieldatei, die im Tutorial [Erstellen eigener Measures in Power BI Desktop](desktop-tutorial-create-measures.md) verwendet wird. Sie enthält bereits Vertriebsdaten des fiktiven Unternehmens Contoso, Inc. Da die Daten in der Datei aus einer Datenbank importiert wurden, können Sie keine Verbindungen mit der Datenquelle herstellen oder sie im Abfrage-Editor anzeigen. Wenn Sie die Datei auf dem lokalen Computer gespeichert haben, öffnen Sie sie in Power BI Desktop.

## <a name="lets-create-a-calculated-column"></a>Erstellen wir eine berechnete Spalte
Angenommen, wir möchten Produktkategorien zusammen mit Produktunterkategorien als einzelnen Wert in einer Zeile anzeigen, etwa als „Mobiltelefone – Zubehör“, „Mobiltelefone – Smartphones und PDAs“ usw. Wenn wir uns in der Berichtsansicht oder Datenansicht (hier verwenden wir die Berichtsansicht) in der Liste „Felder“ die Produkttabellen ansehen, erkennen wir, dass kein Feld mit den gewünschten Eigenschaften vorhanden ist. Wir haben aber ein Feld „ProductCategory“ und ein Feld „ProductSubcategory“, jedes in jeweils einer eigenen Tabelle.

 ![](media/desktop-tutorial-create-calculated-columns/calccol_fileds_nonewcol.png)

Wir erstellen eine neue berechnete Spalte, um Werte aus diesen zwei Spalten zu neuen Werten für unsere neue Spalte zu kombinieren. Interessanterweise müssen wir dazu Daten aus zwei verschiedenen Tabellen in einer einzelnen Spalte zusammenführen. Da wir DAX zum Erstellen unserer neuen Spalte verwenden, können wir die Leistungsfähigkeit des bereits vorhandenen Modells im vollen Umfang nutzen, einschließlich der bereits bestehenden Beziehungen zwischen verschiedenen Tabellen.

### <a name="to-create-a-productfullcategory-column"></a>So erstellen Sie eine Spalte „ProductFullCategory“
**1.**  Klicken Sie mit der rechten Maustaste in der Tabelle **ProductSubcategory** in der Feldliste, oder klicken Sie auf den Pfeil nach unten, und klicken Sie dann auf **Neue Spalte**. Dadurch wird unsere neue Spalte der Tabelle „ProductSubcategory“ hinzugefügt.

![](media/desktop-tutorial-create-calculated-columns/calccol_fileds_newcolumn.png)

Die Bearbeitungsleiste wird entlang der Oberkante der Berichtszeichenfläche oder des Datenrasters angezeigt. Dies ist der Ort, an dem wir die Spalte umbenennen und eine DAX-Formel eingeben können.

![](media/desktop-tutorial-create-calculated-columns/calccol_fileds_newcolumnformula.png)

Standardmäßig erhält eine neue berechnete Spalte einfach den Namen „Spalte“. Wenn wir sie nicht umbenennen, heißt die nächste erstellte Spalte dann „Spalte 2“, dann „Spalte 3“ usw. Wir möchten unsere Spalten aber leicht wiederfinden können, daher geben wir unserer neuen Spalte einen neuen Namen.

**2.** Da der Name **Spalte** bereits in der Bearbeitungsleiste markiert ist, brauchen Sie nur **ProductFullCategory** einzugeben.

Jetzt können wir mit dem Eingeben unserer Formel beginnen. Wir möchten, dass die Werte in der neuen Spalte mit dem ProductCategory-Namen aus der Tabelle „ProductCategory“ beginnen. Da sich diese Spalte in einer anderen (aber verwandten) Tabelle befindet, verwenden wir die Funktion [RELATED](https://msdn.microsoft.com/library/ee634202.aspx) als Unterstützung beim Abrufen.

**3.**  Geben Sie hinter dem Gleichheitszeichen ein **R** ein. Jetzt wird eine Dropdownliste mit Vorschlägen angezeigt, die alle DAX-Funktionen enthält, die mit dem Buchstaben „R“ beginnen. Je mehr wir eingeben, desto stärker verengt sich die Vorschlagsliste auf die benötigte Funktion. Neben der Funktion wird eine Beschreibung der Funktion angezeigt. Wählen Sie durch Scrollen nach unten **RELATED** aus, und drücken Sie dann die EINGABETASTE.

 ![](media/desktop-tutorial-create-calculated-columns/calccol_fileds_pfc_1.png)

Eine öffnende Klammer wird zusammen mit einer weiteren Vorschlagsliste mit allen verfügbaren Spalten angezeigt, die wir der Funktion RELATED übergeben können. Darüber hinaus werden eine Beschreibung und Details zu den erwarteten Parametern angezeigt.

 ![](media/desktop-tutorial-create-calculated-columns/calccol_fileds_pfc_2.png)

Ein Ausdruck tritt immer zwischen einer öffnenden und einer schließenden Klammer auf. In diesem Fall soll unser Ausdruck ein einzelnes Element enthalten, das an die Funktion RELATED übergeben wird; eine zugeordnete Spalte, aus der Werte zurückgegeben werden. Die Liste der Spalten wird automatisch eingeschränkt und zeigt nur die zugeordneten Spalten an. In diesem Fall möchten wir nur die Spalte „ProductCategory“ in der Tabelle „ProductCategory“ haben.

Wählen Sie **ProductCategory[ProductCategory]**aus, und geben Sie dann eine schließende Klammer ein.

> [!TIP]
> Syntaxfehler werden meistens durch eine fehlende oder falsch platzierte schließende Klammer verursacht. Wenn Sie dies vergessen, werden diese aber häufig von Power BI Desktop hinzugefügt.
> 
> 

![](media/desktop-tutorial-create-calculated-columns/calccol_fileds_pfc_3.png)

**4.** Wir möchten einen Bindestrich verwenden, um die einzelnen Werte zu trennen. Geben Sie also nach der schließenden Klammer des ersten Ausdrucks ein Leerzeichen, ein kaufmännisches Und (&), ein doppeltes Anführungszeichen, ein Leerzeichen, einen Bindestrich (-), noch ein Leerzeichen, ein doppeltes Anführungszeichen und dann ein weiteres kaufmännisches Und ein. Die Formel sollte nun wie folgt aussehen:

 **ProductFullCategory = RELATED(ProductCategory[ProductCategory]) & " - " &**

> [!TIP]
> Klicken Sie rechts von der Formelleiste auf das Erweiterungssymbol (Winkel nach unten), um den Formel-Editor zu erweitern. Drücken Sie auf ALT+EINGABETASTE, um eine Zeile nach unten zu springen, und die TAB-TASTE, um zur Seite zu springen.
> 
> 

**5.** Geben Sie schließlich eine weitere öffnende eckige Klammer ein, und wählen Sie dann die Spalte **[ProductSubcategory]** aus, um die Formel fertig zu stellen. Ihre Formel sollte nun so aussehen:

![](media/desktop-tutorial-create-calculated-columns/calccol_fileds_pfc_5.png)

Sie werden bemerkt haben, dass wir keine weitere RELATED-Funktion im zweiten Ausdruck verwendet haben, mit dem die Spalte „ProductSubcategory“ aufgerufen wird. Das hat den Grund, dass sich diese Spalte bereits in der Tabelle befindet, in der wir unsere neue Spalte erstellen. Wir können [ProductCategory] mit dem Tabellennamen (vollqualifiziert) oder ohne ihn (nicht qualifiziert) eingeben.

**6.**  Stellen Sie die Formel fertig, indem Sie die EINGABETASTE drücken oder in der Bearbeitungsleiste auf das Häkchen klicken. Die Formel wird überprüft und der Feldliste in der Tabelle **ProductSubcategory** hinzugefügt.

![](media/desktop-tutorial-create-calculated-columns/calccol_fileds_pfc_6.png)

Sie werden bemerkt haben, dass für berechnete Spalten ein besonderes Symbol in der Feldliste angezeigt wird. So wird angezeigt, dass sie eine Formel enthalten. Sie werden nur in Power BI Desktop in dieser Weise angezeigt. Im Power BI-Dienst (Ihre Power BI-Website) ist es nicht möglich, eine Formel zu ändern. Daher verfügen Felder berechneter Spalten nicht über ein Symbol.

## <a name="lets-add-our-new-column-to-a-report"></a>Fügen wir die neue Spalte zu einem Bericht hinzu
Jetzt können wir unsere neue Spalte „ProductFullCategory“ der Berichtszeichenfläche hinzufügen. Sehen wir uns „SalesAmount“ nach „ProductFullCategory“ einmal an.

Ziehen Sie die Spalte **ProductFullCategory** aus der Tabelle **ProductSubcategory** auf die Berichtszeichenfläche, und ziehen Sie dann das Feld **SalesAmount** aus der Tabelle **Sales** auf das Diagramm.

![](media/desktop-tutorial-create-calculated-columns/calccol_fileds_report_1.png)

## <a name="lets-create-another"></a>Erstellen wir noch eine Spalte
Da Sie jetzt wissen, wie Sie eine berechnete Spalte erstellen können, erstellen wir gleich noch eine.

Das Modell „Contoso Sales Sample for Power BI Desktop“ enthält Umsatzdaten für aktive und inaktive Ladengeschäfte. Wir möchten sicherstellen, dass Daten für inaktive Ladengeschäfte als solche kenntlich sind. Effektiv wünschen wir uns ein Feld mit dem Namen „Active StoreName“. Zu diesem Zweck erstellen wir eine weitere Spalte. In diesem Fall möchten wir, dass unsere neue Spalte „Active StoreName“ (als Feld) den Namen eines inaktiven Geschäfts als „Inactive“, den Namen von aktiven Geschäften jedoch als vollständigen Namen des Geschäfts anzeigt.

Glücklicherweise weist unsere Tabelle „Stores“ eine Tabelle mit dem Namen „Status“ auf, die den Wert „On“ für aktive Ladengeschäfte und „Off“ für inaktive Ladengeschäfte trägt. Wir können Werte für jede Zeile in der Spalte „Status“ abfragen, um in unserer neuen Spalte neue Werte zu erstellen.

### <a name="to-create-an-active-storename-column"></a>So erstellen Sie eine Spalte „Active StoreName“
**1.**  Erstellen Sie eine neue berechnete Spalte mit dem Namen **Active StoreName** in der Tabelle **Stores**.

Für diese Spalte überprüft unsere DAX-Formel den Status jedes einzelnen Geschäfts. Wenn der Status eines Geschäfts „On“ ist, gibt die Formel den Namen des Geschäfts zurück. Wenn er „Off“ ist, erhält das Geschäft den Namen „Inactive“. Zu diesem Zweck verwenden wir die logische Funktion [IF](https://msdn.microsoft.com/library/ee634824.aspx), um den Status des Geschäfts zu überprüfen und einen bestimmten Wert zurückzugeben, wenn die Bedingung erfüllt bzw. nicht erfüllt wurde.

**2.**  Beginnen Sie mit der Eingabe von **IF**. Die Vorschlagsliste zeigt an, was wir hinzufügen können. Wählen Sie **IF**aus.

![](media/desktop-tutorial-create-calculated-columns/calccol_activestore_1.png)

Das erste Argument für IF ist ein logischer Test. Wir möchten testen, ob ein Geschäft den Status „On“ aufweist oder nicht.

**3.**  Geben Sie eine öffnende eckige Klammer **[** ein, die uns ermöglicht, Spalten aus der Tabelle „Stores“ auszuwählen. Wählen Sie **[Status]**aus.

 ![](media/desktop-tutorial-create-calculated-columns/calccol_activestore_2.png)

**4.**  Geben Sie direkt hinter **[Status]** die Zeichen **=„On“** ein, und geben Sie dann ein Komma (**,**) ein, um das zweite Argument einzugeben. Die QuickInfo schlägt vor, dass wir den Wert für wahre Ergebnisse hinzufügen müssen.

![](media/desktop-tutorial-create-calculated-columns/calccol_activestore_3.png)

**5.**  Wenn das Geschäft aktiv ist („On“), möchten wir den Namen des Geschäfts anzeigen. Geben Sie eine öffnende eckige Klammer **[** ein, wählen Sie die Spalte **[StoreName]** aus, und geben Sie dann ein weiteres Komma ein, damit wir das dritte Argument eingeben können.

![](media/desktop-tutorial-create-calculated-columns/calccol_activestore_step5.png)

**6.**  Wir müssen einen Wert für den Fall eingeben, dass das Ergebnis des Tests falsch ist, und hier möchten wir den Wert **„Inactive“** verwenden.

![](media/desktop-tutorial-create-calculated-columns/calccol_activestore_step6.png)

**7.**  Stellen Sie die Formel fertig, indem Sie die EINGABETASTE drücken oder in der Bearbeitungsleiste auf das Häkchen klicken. Die Formel wird überprüft und der Feldliste in der Tabelle „Stores“ hinzugefügt.

Genau wie jedes andere Feld können wir unsere neue Spalte „Active StoreName“ in Visualisierungen verwenden. In diesem Diagramm werden Geschäfte mit dem Status „On“ einzeln mit ihrem Namen dargestellt, Geschäfte mit dem Status „Off“ werden jedoch gruppiert und als „Inactive“ angezeigt. 

 ![](media/desktop-tutorial-create-calculated-columns/calccol_activestore_viz.png)

## <a name="what-weve-learned"></a>Was wir gelernt haben
Berechnete Spalten können unsere Daten bereichern und Erkenntnisse leichter zugänglich machen. Wir haben gelernt, wie berechnete Spalten mithilfe der Bearbeitungsleiste erstellt werden, wie die Vorschlagsliste verwendet wird und wie Spalten sinnvoll benannt werden.

## <a name="additional-resources"></a>Weitere Ressourcen
Lesen Sie sich die Informationen unter [DAX-Grundlagen in Power BI Desktop](desktop-quickstart-learn-dax-basics.md) durch, wenn Sie tiefer in DAX-Formeln einsteigen und berechnete Spalten unter Verwendung fortgeschrittener DAX-Formeln erstellen möchten. Dieser Artikel konzentriert sich auf grundlegende Konzepte in DAX, wie etwa Syntax, Funktionen und ein tiefer gehendes Verständnis von Kontext.

Denken Sie daran, die [DAX-Referenz (Data Analysis Expressions)](https://msdn.microsoft.com/library/gg413422.aspx) zu Ihren Favoriten hinzuzufügen. Das ist der Ort, an dem Sie detaillierte Informationen zur DAX-Syntax, Operatoren und den über 200 DAX-Funktionen finden.

