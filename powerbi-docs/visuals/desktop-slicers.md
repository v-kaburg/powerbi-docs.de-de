---
title: Verwenden von Slicern in Power BI Desktop
description: Sie können Slicer in Power BI Desktop für das Filtern, Hervorheben und Anpassen von Berichten verwenden.
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 07/27/2018
ms.author: mihart
LocalizationGroup: Create reports
ms.openlocfilehash: 637005f8783dd5f839081f7ad63e25bc5d2f395d
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/15/2019
ms.locfileid: "54282400"
---
# <a name="using-slicers-power-bi-desktop"></a>Verwenden von Slicern in Power BI Desktop

Sie können einen **Slicer** in **Power BI Desktop** verwenden, um die Ergebnisse von Visuals auf Ihrer Berichtsseite zu filtern. Mithilfe von Slicern können Sie den angewendeten Filter einfach anpassen, indem Sie mit dem Slicer interagieren. Sie können ebenfalls Optionen dafür angeben, wie Ihr Slicer angezeigt wird und wie Sie mit diesem interagieren. Die folgende Abbildung stellt einen Slicer dar, dessen Dropdownmenü für *Typen* angezeigt wird. 

![Slicer in Desktop](./media/desktop-slicers/desktop-slicers_01.png)

Ein Slicer kann für folgende Typen angezeigt werden:

* Liste
* Dropdown
* Zwischen
* Kleiner als oder gleich
* Größer als oder gleich

Sie können einen Slicer zu einem Bericht hinzufügen, indem Sie auf das Visual **Slicer** im Bereich **Visualisierungen** klicken.

![der Visualtyp „Slicer“](./media/desktop-slicers/desktop-slicers_02.png)

Das Verhalten von Slicern ist in **Power BI Desktop** und im **Power BI-Dienst** ähnlich. Einen Artikel zur Verwendung von Slicern finden Sie unter [Slicer im Power BI-Dienst](power-bi-visualization-slicers.md).

## <a name="synchronize-slicers-across-report-pages"></a>Synchronisieren von Slicern über mehrere Berichtsseiten

In **Power BI Desktop** können Sie Slicer über mehrere Berichtsseiten synchronisieren. Klicken Sie im Bereich **Ansicht** im Menüband auf **Slicer synchronisieren**, um Slicer zu synchronisieren. Wenn Sie Slicers synchronisieren, wird der Bereich **Slicer synchronisieren** wie in der folgenden Abbildung dargestellt angezeigt.

![Bereich „Slicer synchronisieren“ anzeigen](./media/desktop-slicers/desktop-slicers_03.png)

Im Bereich **Slicer synchronisieren** können Sie angeben, wie der Slicer über mehrere Berichtsseiten synchronisiert werden soll. Sie können angeben, ob jeder Slicer auf jede einzelne Berichtsseite **angewendet** werden soll und ob der Slicer auf jeder einzelnen Berichtsseite **sichtbar** sein soll.

Sie können einen Slicer wie in der folgenden Abbildung dargestellt beispielsweise auf **Seite 2** Ihres Berichts platzieren. Sie können dann auswählen, ob dieser Slicer für jede ausgewählte Seite *gelten* soll und ob der Slicer auf jeder ausgewählten Seite im Bericht *sichtbar* sein soll. Für jeden Slicer können Sie eine beliebige Kombination dieser Optionen anwenden. 

![Slicer synchronisieren](./media/desktop-slicers/desktop-slicers_04.png)

Durch den Link **Allen hinzufügen** in diesem Bereich wird der ausgewählte Slicer auf alle Seiten im Bericht angewendet.


Beachten Sie, dass die Auswahl, die im Bereich **Slicer synchronisieren** angezeigt wird, nur für den *ausgewählten Slicer* gilt. Sie können mehrere Slicer auf verschiedene Seiten anwenden und den Bereich verwenden, um zu definieren, wie jeder Slicer auf die verschiedenen Seiten Ihres Berichts angewendet wird. 

Die Auswahl der Slicer kann synchronisiert werden, andere Auswahlen wie die Formatierung, die Bearbeitung und das Löschen werden jedoch *nicht* synchronisiert. 

## <a name="advanced-options-for-slicers"></a>Erweiterte Optionen für Slicer

Im Bereich **Slicer synchronisieren** können Sie im Abschnitt **Erweiterte Optionen** auch einer Sammlung von Slicern einen **Gruppennamen** zuweisen und Slicer in derselben Gruppe seitenübergreifend synchronisieren lassen. 

![Gruppenname für Slicer](./media/desktop-slicers/desktop-slicers_05.png)

Mit dieser Funktion können Sie eine benutzerdefinierte Gruppe von Slicern erstellen, die synchron gehalten wird. Ein Standardname wird angeboten, aber Sie können auch einen anderen Namen wählen. 

Der Gruppenname bietet zusätzliche Flexibilität bei Slicern. Sie können separate Gruppen erstellen, um Slicer zu synchronisieren, die dasselbe Feld verwenden, oder Slicer, die unterschiedliche Felder verwenden, derselben Gruppe zuordnen. 

## <a name="how-filtering-affects-selection-in-slicers"></a>Auswirkungen der Filterung auf die Auswahl in Datenschnitten

Wenn Sie in einem Datenschnitt eine Auswahl vornehmen und dann einen Filter anwenden, der das ausgewählte Element normalerweise entfernen würde, verbleibt es am Ende der Liste der Elemente im Datenschnitt. Wenn der Filter entfernt wird, ist die Auswahl immer noch im Datenschnitt vorhanden. Sie werden feststellen, dass, wenn Sie das Element im Datenschnitt deaktivieren, es aus der Liste entfernt wird.

![Beibehaltene Auswahl in Datenschnitten](./media/desktop-slicers/retained-selection-in-slicers.gif)


## <a name="next-steps"></a>Nächste Schritte

Folgende Artikel könnten Sie ebenfalls interessieren:

* [Slicer im Power BI-Dienst](power-bi-visualization-slicers.md)
* [Verwenden der Funktion „Slicer für numerischen Bereich“ in Power BI Desktop](../desktop-slicer-numeric-range.md)
* [Verwenden eines relativen Slicers mit Datum und eines relativen Datumsfilters in Power BI Desktop](desktop-slicer-filter-date-range.md)

