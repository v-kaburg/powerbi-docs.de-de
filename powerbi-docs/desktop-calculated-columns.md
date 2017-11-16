---
title: Verwenden von berechneten Spalten in Power BI Desktop
description: Berechnete Spalten in Power BI Desktop
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
ms.date: 10/12/2017
ms.author: davidi
ms.openlocfilehash: 3b3f77444ef71c190404eb4dc40970ffa634aa47
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2017
---
# <a name="using-calculated-columns-in-power-bi-desktop"></a>Verwenden von berechneten Spalten in Power BI Desktop
Mit berechneten Spalten können Sie einer bereits in Ihrem Modell vorhandenen Tabelle neue Daten hinzufügen. Aber statt Werte abzufragen und sie aus einer Datenquelle in Ihre neue Spalte zu laden, erstellen Sie eine DAX-Formel, die die Werte der Spalte definiert. In Power BI Desktop werden berechnete Spalten mithilfe der Funktion "Neue Spalte" in der Berichtsansicht erstellt.

Im Gegensatz zu benutzerdefinierten Spalten, die als Teil einer Abfrage im Abfrage-Editor mithilfe von „Benutzerdefinierte Spalte hinzufügen“ erstellt werden, basieren berechnete Spalten, die in der Berichtsansicht oder in der Datenansicht erstellt werden, auf bereits in das Modell geladenen Daten. Sie können beispielsweise entscheiden, Werte aus zwei verschiedenen Spalten in zwei verschiedenen, aber aufeinander bezogenen Tabellen zu verketten, eine Addition auszuführen oder Teilzeichenfolgen zu extrahieren.

Die von Ihnen erstellten berechneten Spalten werden ebenso in der Liste "Felder" angezeigt wie jedes andere Feld, sie weisen jedoch ein besonderes Symbol auf, das seine Werte als Ergebnis einer Formel anzeigt. Sie können Ihre Spalten nach Belieben benennen und sie Berichtsvisualisierungen hinzufügen, genau wie andere Felder.

![](media/desktop-calculated-columns/calccolinpbid_fields.png)

Berechnete Spalten verwenden zum Berechnen von Ergebnissen [DAX](https://msdn.microsoft.com/library/gg413422.aspx) (Data Analysis Expressions), eine Formelsprache, die für das Arbeiten mit relationalen Daten, wie sie in Power BI Desktop verwendet werden, konzipiert wurde. DAX beinhaltet eine Bibliothek aus über 200 Funktionen, Operatoren und Konstrukten, die eine enorme Flexibilität beim Erstellen von Formeln zum Berechnen von Ergebnissen für so ungefähr jede benötigte Datenanalyse verfügbar macht. Weitere Informationen zu DAX finden Sie im Abschnitt "Weitere Ressourcen" am Ende dieses Artikels.

DAX-Formeln sind ähnlich wie Excel-Formeln. Tatsächlich verwendet DAX viele der gleichen Formeln wie Excel. DAX-Funktionen sind jedoch für die Überarbeitung von interaktiv segmentierten oder in einem Bericht gefilterten Daten, wie in Power BI-Desktop, konzipiert. Anders als in Excel, wo Sie für jede Zeile in einer Tabelle eine andere Formel verwenden können, berechnet eine für eine neue Spalte erstellte DAX-Formel ein Ergebnis für jede Zeile in der Tabelle. Spaltenwerte werden bei Bedarf neu berechnet, etwa wenn die zugrundeliegenden Daten aktualisiert werden und sich Werte geändert haben.

## <a name="lets-look-at-an-example"></a>Betrachten wir dazu ein Beispiel.
Tyge ist Versandleiter bei Contoso. Er möchte einen Bericht erstellen, aus dem die Anzahl der Lieferungen in verschiedene Städte hervorgeht. Er verfügt über eine Tabelle „Geography“ mit separaten Feldern für Stadt und Bundesstaat. Allerdings möchte Tyge in seinem Bericht Stadt und Bundesstaat als einen einzelnen Wert in der gleichen Zeile anzeigen. Zurzeit weist Tyges Tabelle „Geography“ das gewünschte Feld nicht auf.

![](media/desktop-calculated-columns/calccolinpbid_cityandstatefields.png)

Mit einer berechneten Spalte kann Tyge die Städte aus der Spalte „City“ aber einfach mit den Bundesstaaten aus der Spalte „State“ zusammenführen, was auch als „Verketten“ bezeichnet wird.

Tyge klickt mit der rechten Maustaste auf die Tabelle „Geography“ und dann auf „Neue Spalte“. Anschließend gibt er die folgende DAX-Formel in die Bearbeitungsleiste ein:

![](media/desktop-calculated-columns/calccolinpbid_formula.png)

Diese Formel erstellt einfach eine neue Spalte mit dem Namen „CityState“, und für jede Zeile in der Tabelle „Geography“ nimmt sie Werte aus der Spalte „City“, fügt ein Komma und ein Leerzeichen hinzu und verkettet sie dann mit Werten aus der Spalte „State“.

Jetzt hat Tyge das gewünschte Feld.

![](media/desktop-calculated-columns/calccolinpbid_citystatefield.png)

Und er kann es zusammen mit der Anzahl der Lieferungen zum Berichtszeichenbereich hinzufügen. Sehr schnell und mit minimalem Aufwand hat Tyge jetzt ein Feld für Stadt und Bundesstaat. Er kann dieses Feld nahezu beliebigen Visualisierungen hinzufügen. Tyge kann auch sehen, dass Power BI Desktop beim Erstellen einer Kartenvisualisierung sogar weiß, wie die Werte für Stadt und Bundesstaat in der neuen Spalte zu lesen sind.

![](media/desktop-calculated-columns/calccolinpbid_citystatemap.png)

## <a name="learn-more"></a>Weitere Informationen
Dies ist nur eine kurze Einführung in berechnete Spalten. Lesen Sie unbedingt das Lernprogramm [Erstellen von berechneten Spalten in Power BI Desktop](desktop-tutorial-create-calculated-columns.md), für das Sie eine Beispieldatei herunterladen können und weitere schrittweise Lektionen zum Erstellen weiterer Spalten erhalten. 

Weitere Informationen zu DAX finden Sie unter [DAX-Grundlagen in Power BI Desktop](desktop-quickstart-learn-dax-basics.md).

Weitere Informationen über Spalten, die im Rahmen von Abfragen erstellt werden, finden Sie im Abschnitt „Erstellen von benutzerdefinierten Spalten“ in [Allgemeine Abfrageaufgaben in Power BI Desktop](desktop-common-query-tasks.md).  

