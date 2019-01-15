---
title: Verwenden eines relativen Datenschnitts mit Datum oder relativen Datumsfilters in Power BI Desktop
description: Hier erfahren Sie, wie Sie mit einem Datenschnitt oder Filter relative Datumsbereiche in Power BI Desktop einschränken.
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 07/27/2018
ms.author: mihart
LocalizationGroup: Create reports
ms.openlocfilehash: c29145e4a51821bab284693bc13a508cb9c046c6
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/15/2019
ms.locfileid: "54279157"
---
# <a name="use-a-relative-date-slicer-and-filter-in-power-bi-desktop"></a>Verwenden eines relativen Datenschnitts mit Datum und relativen Datumsfilters in Power BI Desktop
Mit dem **relativen Datenschnitt mit Datum** oder **relativem Datumsfilter** können Sie zeitbasierte Filter auf beliebige Datumsspalten in Ihrem Datenmodell anwenden. Ein Beispiel: Sie können mit dem **relativen Datenschnitt mit Datum** nur Daten zu Verkäufen anzeigen lassen, die innerhalb der letzten dreißig Tage (des letzten Monats, des Kalendermonats usw.) aufgetreten sind. Wenn Sie die Daten aktualisieren, wendet der relative Zeitraum automatisch die entsprechende relative Datumseinschränkung an.

![](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter_01.png)

## <a name="using-the-relative-date-range-slicer"></a>Verwenden des relativen Datenschnitts mit Datumsbereich
Der relative Datenschnitt mit Datum funktioniert wie jeder andere Datenschnitt. Erstellen Sie einfach ein Visual vom Typ **Datenschnitt** für Ihren Bericht, und wählen Sie dann für **Feld** einen Datumswert aus. In der folgenden Abbildung ist das Feld *OrderDate* ausgewählt.

![](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter_02.png)

Klicken Sie rechts oben im **relativen Datenschnitt mit Datum** auf das Zirkumflexzeichen. Ein Menü wird angezeigt.

![](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter_03.png)

Wählen Sie für den relativen Datenschnitt mit Datum die Option *Relativ* aus.

Anschließend können Sie die Einstellungen auswählen. Für die erste Dropdownliste im *relativen Datenschnitt mit Datum* stehen folgende Auswahlmöglichkeiten zur Verfügung:

* Ende
* Weiter
* Diese

Diese Auswahlmöglichkeiten werden in der folgenden Abbildung gezeigt.

![](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter_04.png)

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

![](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter_05.png)

Folgendes geschieht, wenn Sie in dieser Liste *Monate* auswählen und für die mittlere Einstellung „2“ eingeben: Wenn heute der 20. Juli ist, werden in den vom Datenschnitt eingeschränkten Visuals Daten für die vorhergehenden zwei Monate angezeigt, vom 20. Mai bis zum 20. Juli (dem heutigen Datum).

Wenn Sie hingegen *Monate (Kalender)* auswählen, zeigen die eingeschränkten Visuals Daten vom 1. Mai bis zum 30. Juni (die letzten zwei kompletten Kalendermonate).

## <a name="using-the-relative-date-range-filter"></a>Verwenden des relativen Datumsbereichsfilters
Sie können auch einen relativen Datumsbereichsfilter für Ihre Berichtsseite oder für den gesamten Bericht erstellen. Ziehen Sie hierfür einfach ein Datumsfeld in den Abschnitt **Filter auf Seitenebene** oder **Berichtsstufenfilter** im Bereich **Feld**, wie in der folgenden Abbildung veranschaulicht.

![](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter_06.png)

Dort können Sie den relativen Datumsbereich ähnlich wie den **relativen Datenschnitt mit Datum** anpassen. Wählen Sie in der Dropdownliste **Filtertyp** den Eintrag **Relative Datumsfilterung** aus.

![](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter_07.png)

Nach Auswahl von **Relative Datumsfilterung** sehen Sie drei zu ändernde Abschnitte, einschließlich eines numerischen Feldes in der Mitte (wie beim Datenschnitt).

![](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter_08.png)

Mehr muss zum Verwenden dieser relativen Datumseinschränkungen in Ihren Berichten nicht erklärt werden.

## <a name="limitations-and-considerations"></a>Einschränkungen und Überlegungen
Die folgenden Überlegungen und Einschränkungen betreffen derzeit den **relativen Datenschnitt mit Datum** und den relativen Datumsfilter.

* Datenmodelle in **Power BI** enthalten keine Zeitzoneninformationen. In Modellen können Zeitangaben gespeichert werden, es gibt jedoch keinerlei Hinweise auf die entsprechende Zeitzone.
* Der Datenschnitt und der Filter basieren immer auf der Uhrzeit in UTC. Wenn Sie also einen Filter in einem Bericht konfigurieren und den Bericht an einen Kollegen in einer anderen Zeitzone senden, sehen Sie beide die gleichen Daten. Befinden Sie sich jedoch nicht in der UTC-Zeitzone, entsprechen die Daten möglicherweise nicht dem erwarteten Zeitzonenversatz.
* In einer lokalen Zeitzone erfasste Daten können mit dem **Abfrage-Editor** in UTC konvertiert werden.

