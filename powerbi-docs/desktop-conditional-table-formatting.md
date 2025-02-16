---
title: Bedingte Tabellenformatierungen in Power BI Desktop
description: Wenden Sie benutzerdefinierte Formatierungen auf Tabellen an.
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/07/2019
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: e23fd2aca90ee14c2376b0175c7c8b5132cf9a9f
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2019
ms.locfileid: "66222264"
---
# <a name="conditional-formatting-in-tables"></a>Bedingte Formatierung in Tabellen 
Mithilfe der bedingten Formatierung für Tabellen können Sie benutzerdefinierte Zellenfarben basierend auf Zellwerten oder auf anderen Werten oder Feldern festlegen und Verlaufsfarben verwenden. Sie können auch Zellwerte mit Datenbalken darstellen. 

Wählen Sie zum Zugriff auf die bedingte Formatierung im Bereich **Felder** des Bereichs **Visualisierungen** in Power BI Desktop den Dropdownpfeil neben dem Wert im Bereich **Werte** aus, den Sie formatieren möchten (oder klicken Sie mit der rechten Maustaste in das Feld). Sie können die bedingte Formatierung nur für Felder im Bereich **Werte** des Bereichs **Felder** verwalten.

![Menü „Bedingte Formatierung“](media/desktop-conditional-table-formatting/table-formatting-0-popup-menu.png)

Die folgenden Abschnitte beschreiben die Optionen für „Bedingte Formatierung“. Eine oder mehrerer Optionen können in einer einzelnen Tabellenspalte kombiniert werden.

> [!NOTE]
> Bei der Anwendung auf eine Tabelle überschreibt die bedingte Formatierung alle benutzerdefinierten Tabellenformatierungen, die auf die Zellen mit bedingter Formatierung angewendet wurden.

Wenn Sie eine bedingte Formatierung aus einer Visualisierung entfernen möchten, klicken Sie einfach mit der rechten Maustaste erneut auf das Feld, wählen Sie **Bedingte Formatierung entfernen** und dann den Typ der zu entfernenden Formatierung aus.

![Menü „Bedingte Formatierung entfernen“](media/desktop-conditional-table-formatting/table-formatting-1-remove.png)

## <a name="background-color-scales"></a>Skalen für die Hintergrundfarbe

Durch Auswahl von **Bedingte Formatierung** und **Skalen für die Hintergrundfarbe** wird das folgende Dialogfeld angezeigt.

![Dialogfeld „Skalen für die Hintergrundfarbe“](media/desktop-conditional-table-formatting/table-formatting-1-default-dialog.png)

Sie können ein Feld aus Ihrem Datenmodell auswählen, auf dem die Farben basieren sollen, indem Sie **Farbe basierend auf** für dieses Feld festlegen. Zusätzlich können Sie den Aggregationstyp für das ausgewählte Feld über den Wert **Summarization** (Zusammenfassung) angeben. Das Feld, das farbig werden soll, wird im Feld **Farbe anwenden auf** angegeben. Sie können dies also nachverfolgen. Sie können Text- und Datumsfelder auch bedingt formatieren, sofern Sie einen numerischen Wert als Grundlage für die Formatierung wählen.

![Feld „Farbe basierend auf“](media/desktop-conditional-table-formatting/table-formatting-1-apply-color-to.png)

Um diskrete Farbwerte für angegebene Wertbereiche zu verwenden, wählen Sie **Farbe nach Regeln** aus. Um ein Farbspektrum zu verwenden, lassen Sie **Farbe nach Regeln** deaktiviert. 

![Dialogfeld „Skalen für die Hintergrundfarbe“](media/desktop-conditional-table-formatting/table-formatting-1-color-by-rules-dialog.png)

### <a name="color-by-rules"></a>Nach Regeln färben

Wenn Sie **Farbe nach Regeln** auswählen, können Sie mindestens einen Wertbereich eingeben, jeweils mit einer festgelegten Farbe.  Jeder Wertbereich beginnt mit einer *Wenn Wert*-Bedingung, einem *Und*-Wertbedingung und einer Farbe.

![Wertbereich „Farbe nach Regeln“](media/desktop-conditional-table-formatting/table-formatting-1-color-by-rules-if-value.png)

Tabellenzellen mit Werten in jedem Bereich werden mit der angegebenen Farbe aufgefüllt. In der folgenden Abbildung werden drei Regeln dargestellt.

![Beispiel „Farbe nach Regeln“](media/desktop-conditional-table-formatting/table-formatting-1-color-by-rules.png)

Die Beispieltabelle sieht nun so aus:

![Beispieltabelle mit „Farbe nach Regeln“](media/desktop-conditional-table-formatting/table-formatting-1-color-by-rules-table.png)


### <a name="color-minimum-to-maximum"></a>Farbe Minimum zu Maximum

Sie können die Werte *Minimum* und *Maximum* sowie deren Farben konfigurieren. Wenn Sie das Kontrollkästchen **Abweichend** aktivieren, können Sie auch einen optionalen Wert für *Zentriert* konfigurieren.

![Schaltfläche „Abweichend“](media/desktop-conditional-table-formatting/table-formatting-1-diverging.png)

Die Beispieltabelle sieht nun so aus:

![Beispieltabelle mit abweichenden Farben](media/desktop-conditional-table-formatting/table-formatting-1-diverging-table.png)

## <a name="font-color-scales"></a>Skalen für die Schriftfarbe

Durch Auswahl von **Bedingte Formatierung** und **Skalen für die Schriftfarbe** wird das folgende Dialogfeld angezeigt. Dieses Dialogfeld ähnelt dem Dialogfeld **Skalen für die Hintergrundfarbe**, es wird jedoch die Schriftfarbe geändert und nicht die Hintergrundfarbe der Zelle.

![Dialogfeld „Skalen für die Schriftfarbe“](media/desktop-conditional-table-formatting/table-formatting-2-diverging.png)

Die Beispieltabelle sieht nun so aus:

![Beispieltabelle mit Skalen für die Schriftfarbe](media/desktop-conditional-table-formatting/table-formatting-2-table.png)

## <a name="data-bars"></a>Datenbalken

Durch Auswahl von **Bedingte Formatierung** und **Datenbalken** wird das folgende Dialogfeld angezeigt. 

![Dialogfeld „Datenbalken“](media/desktop-conditional-table-formatting/table-formatting-3-default.png)

In der Standardeinstellung ist die Option **Nur Balken anzeigen** deaktiviert, deshalb werden in der Tabellenzelle jeweils die Leiste und der aktuelle Wert angezeigt.

![Beispieltabelle mit Datenbalken und Werten](media/desktop-conditional-table-formatting/table-formatting-3-default-table.png)

Wenn die Option **Nur Balken anzeigen** aktiviert ist, zeigt die Tabellenzelle nur die Leiste an.

![Beispieltabelle nur mit Datenbalken](media/desktop-conditional-table-formatting/table-formatting-3-default-table-bars.png)

## <a name="color-formatting-by-field-value"></a>Farbformatierung nach Feldwerten

Sie können ein Measure oder eine Spalte zum Festlegen einer Farbe verwenden, indem entweder ein Textwert oder einen Hexadezimalcode verwendet wird, um diese Farbe für den Hintergrund der Schriftfarbe einer Tabelle oder eines Matrixvisuals zu übernehmen. Sie können auch eine benutzerdefinierte Logik für ein angegebenes Feld erstellen, sodass durch diese Logik die gewünschte Farbe für die Schriftart oder den Hintergrund übernommen wird.

In der folgenden Tabelle ist beispielsweise jedem Produktmodell eine Farbe zugeordnet. 

![ProductName-Feld mit dem Namen der Farbe](media/desktop-conditional-table-formatting/conditional-table-formatting_01.png)

Sie können Zelle auf Grundlage des Feldwerts formatieren, indem Sie per Rechtsklick auf die Spalte *Farbe* das Dialogfeld **Bedingte Formatierung** für dieses Visual auswählen und in diesem Fall im Menü auf **Hintergrundfarbe** klicken. 

![Auswählen der Hintergrundfarbe im Menü](media/desktop-conditional-table-formatting/conditional-table-formatting_02.png)

Wählen Sie im angezeigten Dialogfeld wie in der folgenden Abbildung dargestellt **Feldwert** im Dropdownmenü **Formatieren nach** aus.

![Formatieren nach Feldwert](media/desktop-conditional-table-formatting/conditional-table-formatting_03.png)

Sie können diesen Prozess für die Schriftfarbe wiederholen, und das Ergebnis im Visual ist wie im folgenden Bildschirm dargestellt eine Volltonfarbe in der Spalte **Farbe**.

![Formatieren nach Feldwert](media/desktop-conditional-table-formatting/conditional-table-formatting_04.png)

Sie können auch eine auf Geschäftslogik basierende DAX-Berechnung erstellen, die je nach den bevorzugten Bedingungen verschiedene Hexadezimalcodes ausgibt. Dies ist im Allgemeinen einfacher als das Erstellen mehrerer Regeln im Dialogfeld für die bedingte Formatierung. Betrachten Sie das *ColorKPI*-Feld in der folgenden Beispielabbildung.

![DAX-Berechnungen](media/desktop-conditional-table-formatting/conditional-table-formatting_05.png)

Anschließend können Sie den Feldwert für **Hintergrundfarbe** auf folgende Weise festlegen.

![Festlegen der Feldfarbe basierend auf KPI](media/desktop-conditional-table-formatting/conditional-table-formatting_06.png)

Dadurch werden beispielsweise Ergebnisse wie die folgende Matrix angezeigt.

![Matrixvisual mit auf KPI-Wert basierender Farbe](media/desktop-conditional-table-formatting/conditional-table-formatting_07.png)

Mithilfe von DAX und etwas Kreativität können Sie viele weitere Varianten erstellen.

Können Sie die Werte aufgeführt, die in der Spezifikation für CSS-Farbe am [ https://www.w3.org/TR/css-color-3/ ](https://www.w3.org/TR/css-color-3/) , auf die Farbe der visuellen Elemente:
* 3, 6 oder 8 Ziffern hexadezimal-codes z. B. #3E4AFF. Stellen Sie sicher, dass Sie das Symbol "#" am Anfang des Codes enthalten. "3E4AFF" wird nicht akzeptiert. 
* RGB- oder RGBA-Werte z. B. RGBA ("234", "234", "234", "0.5")
* HSL- oder HSLA-Werte z. B. HSLA (123, 75 %, 75 %, 0.5)
* Farbe Namen, z. B. grün SkyBlue, PeachPuff 

## <a name="next-steps"></a>Nächste Schritte
Weitere Informationen finden Sie im folgenden Artikel:  

* [Tipps und Tricks zur Farbformatierung in Power BI](visuals/service-tips-and-tricks-for-color-formatting.md)  

