---
title: Bedingte Tabellenformatierungen in Power BI Desktop
description: Wenden Sie benutzerdefinierte Formatierungen auf Tabellen an.
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 05/17/2018
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 70aa61d6a02bea1b7058a68b20718008ace1b8c8
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2018
ms.locfileid: "34480886"
---
# <a name="conditional-formatting-in-tables"></a>Bedingte Formatierung in Tabellen 
Mithilfe der bedingten Formatierung für Tabellen können Sie benutzerdefinierte Zellenfarben basierend auf Zellwerten oder auf anderen Werten oder Feldern festlegen und Verlaufsfarben verwenden. Sie können auch Zellwerte mit Datenbalken darstellen. 

Wählen Sie zum Zugriff auf die bedingte Formatierung im Bereich **Felder** des Bereichs **Visualisierungen** in Power BI Desktop den Dropdownpfeil neben dem Wert im Bereich **Werte** aus, den Sie formatieren möchten (oder klicken Sie mit der rechten Maustaste in das Feld). Sie können die bedingte Formatierung nur für Felder im Bereich **Werte** des Bereichs **Felder** verwalten.

![Menü „Bedingte Formatierung“](media/desktop-conditional-table-formatting/table-formatting-0-popup-menu.png)

Die folgenden Abschnitte beschreiben die drei Optionen für „Bedingte Formatierung“. Eine oder mehrerer Optionen können in einer einzelnen Tabellenspalte kombiniert werden.

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

### <a name="color-by-rules"></a>Farbe nach Regeln

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
