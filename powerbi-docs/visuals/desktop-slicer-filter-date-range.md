---
title: Verwenden eines relativen Datenschnitts mit Datum oder relativen Datumsfilters in Power BI Desktop
description: Hier erfahren Sie, wie Sie mit einem Datenschnitt oder Filter relative Datumsbereiche in Power BI Desktop einschränken.
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/28/2019
ms.author: mihart
LocalizationGroup: Create reports
ms.openlocfilehash: 3d8057c4d35294dd5e83638b721169e4d54d2adf
ms.sourcegitcommit: 8bf2419b7cb4bf95fc975d07a329b78db5b19f81
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2019
ms.locfileid: "66374467"
---
# <a name="use-a-relative-date-slicer-and-filter-in-power-bi"></a>Verwenden eines relativen Datenschnitt mit Datum und relativen Datumsfilters in Power BI
Mit dem **relativen Datenschnitt mit Datum** oder **relativem Datumsfilter** können Sie zeitbasierte Filter auf beliebige Datumsspalten in Ihrem Datenmodell anwenden. Ein Beispiel: Sie können mit dem **relativen Datenschnitt mit Datum** nur Daten zu Verkäufen anzeigen lassen, die innerhalb der letzten dreißig Tage (des letzten Monats, des Kalendermonats usw.) aufgetreten sind. Wenn Sie die Daten aktualisieren, wendet der relative Zeitraum automatisch die entsprechende relative Datumseinschränkung an.

![](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter-01.png)

## <a name="using-the-relative-date-range-slicer"></a>Verwenden des relativen Datenschnitts mit Datumsbereich
Der relative Datenschnitt mit Datum funktioniert wie jeder andere Datenschnitt. Erstellen Sie einfach ein Visual vom Typ **Datenschnitt** für Ihren Bericht, und wählen Sie dann für **Feld** einen Datumswert aus. In der folgenden Abbildung ist das Feld *OrderDate* ausgewählt.

![](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter-02.png)

Wählen Sie den Slicer aus, auf dem Canvas, und klicken Sie dann das Caretzeichen in der oberen rechten Ecke des slicers visual. Wenn das visuelle Element Daten enthält, zeigt das Menü die Option für **Relative**. 

![](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter-03.png)

Wählen Sie für den relativen Datenschnitt mit Datum die Option *Relativ* aus.

Anschließend können Sie die Einstellungen auswählen. Für die erste Dropdownliste im *relativen Datenschnitt mit Datum* stehen folgende Auswahlmöglichkeiten zur Verfügung:

* Letzte
* Weiter
* Diese

Diese Auswahlmöglichkeiten werden in der folgenden Abbildung gezeigt.

![](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter-04.png)

Mit der nächsten (mittleren) Einstellung im *relativen Datenschnitt mit Datum* können Sie eine Zahl eingeben, um den relativen Datumsbereich zu definieren.

Mit der dritten Einstellung können Sie den Datumswert auswählen. Die folgenden Auswahlmöglichkeiten stehen zur Verfügung:

* Tage
* Wochen
* Wochen (Kalender)
* Monate
* Monate (Kalender)
* Jahre
* Jahre (Kalender)

Diese Auswahlmöglichkeiten werden in der folgenden Abbildung gezeigt.

![](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter-05.png)

Folgendes geschieht, wenn Sie in dieser Liste *Monate* auswählen und für die mittlere Einstellung „2“ eingeben: Wenn heute der 20. Juli ist, werden in den vom Datenschnitt eingeschränkten Visuals Daten für die vorhergehenden zwei Monate angezeigt, vom 20. Mai bis zum 20. Juli (dem heutigen Datum).

Wenn Sie hingegen *Monate (Kalender)* auswählen, zeigen die eingeschränkten Visuals Daten vom 1. Mai bis zum 30. Juni (die letzten zwei kompletten Kalendermonate).

## <a name="using-the-relative-date-range-filter"></a>Verwenden des relativen Datumsbereichsfilters
Sie können auch einen relativen Datumsbereichsfilter für Ihre Berichtsseite oder für den gesamten Bericht erstellen. Ziehen Sie hierfür einfach ein Datumsfeld in den Abschnitt **Filter auf Seitenebene** oder **Berichtsstufenfilter** im Bereich **Feld**, wie in der folgenden Abbildung veranschaulicht.

![](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter-06.png)

Dort können Sie den relativen Datumsbereich ähnlich wie den **relativen Datenschnitt mit Datum** anpassen. Wählen Sie in der Dropdownliste **Filtertyp** den Eintrag **Relative Datumsfilterung** aus.

![](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter-07.png)

Nach Auswahl von **Relative Datumsfilterung** sehen Sie drei zu ändernde Abschnitte, einschließlich eines numerischen Feldes in der Mitte (wie beim Datenschnitt).

![](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter-08.png)

Mehr muss zum Verwenden dieser relativen Datumseinschränkungen in Ihren Berichten nicht erklärt werden.

## <a name="limitations-and-considerations"></a>Einschränkungen und Überlegungen
Die folgenden Überlegungen und Einschränkungen betreffen derzeit den **relativen Datenschnitt mit Datum** und den relativen Datumsfilter.

* Datenmodelle in **Power BI** enthalten keine Zeitzoneninformationen. In Modellen können Zeitangaben gespeichert werden, es gibt jedoch keinerlei Hinweise auf die entsprechende Zeitzone.
* Der Datenschnitt und der Filter basieren immer auf der Uhrzeit in UTC. Wenn Sie also einen Filter in einem Bericht konfigurieren und den Bericht an einen Kollegen in einer anderen Zeitzone senden, sehen Sie beide die gleichen Daten. Befinden Sie sich jedoch nicht in der UTC-Zeitzone, entsprechen die Daten möglicherweise nicht dem erwarteten Zeitzonenversatz.
* In einer lokalen Zeitzone erfasste Daten können mit dem **Abfrage-Editor** in UTC konvertiert werden.

