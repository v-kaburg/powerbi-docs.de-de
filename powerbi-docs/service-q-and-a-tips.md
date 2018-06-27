---
title: Tipps und Tricks für Fragen mit Q&A in Power BI
description: Tipps und Tricks für Fragen mit Q&A in Power BI
author: mihart
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 01/18/2018
ms.author: jastru
LocalizationGroup: Ask questions of your data
ms.openlocfilehash: 0165eb7161e9ba931c336300f73316d215b1c88d
ms.sourcegitcommit: 2a7bbb1fa24a49d2278a90cb0c4be543d7267bda
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2018
ms.locfileid: "34247068"
---
# <a name="tips-for-asking-questions-in-power-bi-qa"></a>Tipps zum Stellen von Fragen mit Power BI Q&A
## <a name="words-and-terminology-that-qa-recognizes"></a>Wörter und Begriffe, die von Q&A erkannt werden
Die Liste mit Schlüsselwörtern ist nicht vollständig.  Die beste Möglichkeit, um festzustellen, ob Power BI ein Schlüsselwort erkennt, besteht darin, es durch Eingeben im Fragefeld auszuprobieren.  Wenn das Wort oder der Begriff ausgegraut dargestellt wird, erkennt Power BI es oder ihn nicht bzw. in diesem Kontext nicht.

In der nachstehenden Liste wird Präsens verwendet, jedoch werden in den meisten Fällen alle Zeitformen erkannt. Beispielsweise beinhaltet „is“ auch „are“, „was“, „were“, „will be“, „have“, „has“, „had“, „will have“, „has got“, „do“, „does“, „did“.  Außerdem ist in „sort“ auch „sorted“ und „sorting“ enthalten.  Darüber hinaus erkennt Power BI Singular- und Pluralversionen eines Worts und schließt diese mit ein. Power BI erkennt z.B. „year“ und „years“.

> [!NOTE]
> Q&A steht auch in der [Microsoft Power BI-App für iOS auf iPads, iPhones und iPod Touch-Geräten](mobile-apps-ios-qna.md) zur Verfügung.
> 
> 

Wenn Sie der Besitzer eines Datasets sind, sollten Sie Ausdrücke und Synonyme hinzufügen, um die Q&A-Ergebnisse für Ihre Kunden zu verbessern.

**Aggregate**: total, sum, amount, number, quantity, count, average, most, least, fewest, largest, smallest, highest, biggest, maximum, max, greatest, lowest, littlest, minimum, min

**Artikel**: a, an, the

**Leerzeichen und Boolesch**: blank, empty, null, prefixed with “non” or “non-“, empty string, empty text, true, t, false, f

**Vergleiche**: vs, versus, compared to, compared with

**Konjunktionen**: and, or, each of, with, versus, &, and, but, nor, along with, in addition to

**Kontraktionen**: Q&A erkennt fast alle Kontraktionen, probieren Sie es aus.  Hier sind einige Beispiele: didn’t, haven’t, he’d, he’s, isn’t, it’s, she’ll, they’d, weren’t, where’ll, who’s, won’t, wouldn’t.

**Datumsangaben**: Power BI erkennt die meisten Datumsbegriffe (day, week, month, year, quarter, decade, usw. …) und Daten in vielen verschiedenen Formaten (siehe unten). Power BI erkennt außerdem die folgenden Schlüsselwörter: MonthName, Days 1-31, decade.

Beispiele: January 3rd of 1995, January 3rd 1995, jan 03 1995, 3 Jan 1995, the 3rd of January, January 1995, 1995 January, 1995-01, 01/1995, Monatsnamen.

**Relative Datumsangaben**: today, right now, current time, yesterday, tomorrow, the current, next, the coming, last, previous, ago, before now, sooner than, after, later than, from, at, on, from now, after now, in the future, past, last, previous, within, in, over, N days ago, N days from now, next, once, twice.

Beispiel: count of orders in the past 6 days.

**Gleichheit (Bereich)**: in, equal to, =, after, is more than, in, between, before

Beispiele: Order year is before 2012? Price equals between 10 and 20? Is the age of John greater than 40? Total sales in 200-300?

**Gleichheit (Wert)**: is, equal, equal to, in, of, for, within, is in, is on

Beispiele: Which products are green? Order date equals 2012. Is the age of John 40? Total sales that is not equal to 200? Order date of 1/1/2016. 10 in price? Green for color? 10 in price?

**Namen:** Enthält eine Spalte im Dataset den Begriff „Name“ (wie z. B. in Mitarbeitername), erkennt Q&A, dass die Werte in dieser Spalte Namen sind, sodass Sie Fragen wie „welche Mitarbeiter heißen Robert“ stellen können.

**Pronomen**: he, him, himself, his, she, herself, her, hers, it, itself, its, they, their, them, themselves, theirs, this, these, that, those

**Abfragebefehle**: sorted, sort by, direction, group, group by, by, show, list, display, give me, name, just, only, arrange, rank, compare, to, with, against, alphabetically, ascending, descending, order

**Bereich**: greater, more, larger, above, over, >, less, smaller, fewer, below, under, <, at least, no less than, >=, at most, no more than, <=, in, between, in the range of, from, later, earlier, sooner, after, on, at, later than, after, since, starting with, starting from, ending with

**Zeitangaben**: am, pm, o'clock, noon, midnight, hour, minute, second, hh:mm:ss

Beispiele: 10 pm, 10:35 pm, 10:35:15 pm, 10 oclock, noon, midnight, hour, minute, second.

**Top N** (Reihenfolge, Rangfolge): top, bottom, highest, lowest, first, last, next, earliest, newest, oldest, latest, most recent, next

**Visualisierungstypen**: alle nativen Power BI-Visualisierungstypen  Wenn die Option im Bereich „Visualisierungen“ vorhanden ist, können Sie sie in Ihre Frage einschließen.  Die Ausnahme stellen hierbei [benutzerdefinierte Visualisierungen](power-bi-custom-visuals.md) dar, die Sie manuell zum Bereich „Visualisierungen“ hinzugefügt haben.

Beispiel: show districts by month and sales total as bar chart

**W-Fragewörter (Beziehung, qualifiziert)**: when, where, which, who, whom, how many, how much, how many times, how often, how frequently, amount, number, quantity, how long, what

## <a name="qa-helps-you-phrase-the-question"></a>Q&A hilft Ihnen beim Formulieren der Frage
Q&A ist so konzipiert, dass die Antwort die Frage möglichst genau widerspiegelt. Dies geschieht auf verschiedene Weise. Für all diese können Sie die Aktion vollständig, teilweise oder gar nicht akzeptieren. Beim Eingeben Ihrer Frage in Q&A geschieht Folgendes:

* Die Wörter und Fragen werden automatisch vervollständigt. Es kommen verschiedene Strategien zur Anwendung, einschließlich der automatischen Vervollständigung wiedererkennbarer Wörter, häufig gestellter Fragen für die zugrunde liegenden Arbeitsmappen und zuvor bereits verwendeter Fragen, die gültige Antworten zurückgegeben haben. Wenn mehr als eine Option für die automatische Vervollständigung verfügbar ist, werden diese in einer Dropdownliste angezeigt.
* Die Rechtschreibung wird korrigiert.
* Eine Vorschau der Antwort wird in Form einer Visualisierung angezeigt. Diese Visualisierung wird immer wieder aktualisiert, wenn Sie weitere Eingaben vornehmen und die Frage bearbeiten (es wird nicht darauf gewartet, dass Sie die EINGABETASTE drücken).
* Es werden automatisch Ersatzbegriffe aus den zugrunde liegenden Datasets vorgeschlagen, wenn Sie den Cursor wieder in das Fragefeld setzen.
* Die Frage wird anhand der Daten in den zugrunde liegenden Datasets umformuliert. Damit wird sichergestellt, dass Q&A Ihre Frage richtig verstanden hat, da Q&A die von Ihnen verwendeten Wörter durch Synonyme aus den zugrunde liegenden Datasets ersetzt.
* Nicht verstandene Wörter werden abgeblendet.

## <a name="dont-stop-now"></a>Das ist noch nicht alles
Halten Sie die Konversation am Laufen, nachdem Q&A Ihre Ergebnisse anzeigt! Nutzen Sie die interaktiven Features der Visualisierung und von Q&A, um weitere Einblicke zu gewinnen.

## <a name="next-steps"></a>Nächste Schritte
Zurück zu [Q&A in Power BI](power-bi-q-and-a.md)  

[Power BI – Grundkonzepte](service-basic-concepts.md)  

Weitere Fragen? [Wenden Sie sich an die Power BI-Community](http://community.powerbi.com/)

