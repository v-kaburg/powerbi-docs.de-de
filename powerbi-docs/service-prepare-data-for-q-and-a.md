---
title: "Optimieren Ihrer Daten für Q&A in Power BI"
description: "Optimieren Ihrer Daten für Q&A in Power BI"
services: powerbi
documentationcenter: 
author: mihart
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
ms.date: 09/26/2017
ms.author: mihart
ms.openlocfilehash: 499c3beca9046af9336de6dfec96994004050986
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2017
---
# <a name="make-your-data-work-well-with-qa-in-power-bi"></a>Optimieren Ihrer Daten für Q&A in Power BI
Wenn Sie Datenmodelle oder Excel-Arbeitsmappen erstellen, die mit Power BI verwendet werden, lesen Sie weiter...

Q&A kann in Power BI strukturierte Daten suchen und die richtige Visualisierung für Ihre Frage auswählen – genau diese Funktion macht Power BI zu einem so überzeugenden Tool.   

Q&A funktioniert mit allen hochgeladenen Excel-Dateien, die Tabellen, Bereiche oder PowerPivot-Modelle enthalten. Je häufiger Sie optimieren und Ihre Daten bereinigen, desto robuster wird die Q&A-Leistung. 

## <a name="how-qa-works"></a>Funktionsweise von Q&A
Q&A verfügt über eine Reihe grundlegender Funktionen zum Verstehen natürlicher Sprachen, die Sie für Ihre Daten anwenden können. Es verfügt über eine kontextabhängigen Schlüsselwortsuche für Ihre Excel-Tabelle, die Spalte und die berechneten Feldnamen. Außerdem weiß das Programm, wie Daten gefiltert, sortiert, zusammengeführt, gruppiert und angezeigt werden sollen. 

In einer Excel-Tabelle mit dem Namen „Verkauf“ mit den Spalten „Produkt“, „Monat“, „Verkaufte Einheiten“, „Bruttoumsatz“ und „Gewinn“ können Sie beispielsweise Fragen zu diesen Entitäten stellen.  Sie können beispielsweise die Umsätze oder den Gesamtgewinn pro Monat anzeigen, die Produkte nach verkauften Einheiten sortieren usw. Erfahren Sie mehr über die [Arten möglicher Fragen](http://blogs.msdn.com/b/powerbi/archive/2014/02/27/demystifying-power-bi-q-amp-a-part-1.aspx), [Fragen, die mit einer Fragevorlage gestellt werden können](service-q-and-a.md) und [Visualisierungstypen, die Sie in einer Abfrage in Q&A angeben können](power-bi-visualization-types-for-reports-and-q-and-a.md).

## <a name="prepare-a-workbook-for-qa"></a>Vorbereiten einer Arbeitsmappe für Q&A
Q&A stützt sich auf die Namen der Tabellen, Spalten und berechneten Felder, um datenspezifische Fragen zu beantworten. Daher sind die Bezeichnungen der Entitäten in Ihrer Arbeitsmappe von großer Bedeutung.

Hier finden Sie einige Tipps zur optimalen Nutzung von Q&A in der Arbeitsmappe.

* Stellen Sie sicher, dass Ihre Daten in einer Excel-Tabelle gespeichert sind. [So erstellen Sie eine Excel-Tabelle](https://support.office.com/article/Create-an-Excel-table-in-a-worksheet-e81aa349-b006-4f8a-9806-5af9df0ac664?ui=en-US&rs=en-US&ad=US).
* Stellen Sie sicher, dass die Tabellen, Spalten und berechneten Felds sinnvoll benannt sind.
  
  Wenn Sie z. B. eine Tabelle mit Verkaufsdaten haben, nennen Sie die Tabelle „Vertrieb“. Spaltennamen wie „Jahr“, „Produkt“, „Vertriebsmitarbeiter“ und „Betrag“ funktionieren in Q&A sehr gut.

> [!NOTE]
> Wenn die Arbeitsmappe ein PowerPivot-Datenmodell aufweist, können Sie noch mehr Optimierungen durchführen. Unter [Demystifying Power BI Q&A Part 2](http://blogs.msdn.com/b/powerbi/archive/2014/02/27/demystifying-power-bi-q-amp-a-part-2.aspx) erhalten Sie von unserem Expertenteam für natürliche Sprachen weitere Informationen.
> 
> 

## <a name="next-steps"></a>Nächste Schritte
[Q&A in Power BI](service-q-and-a.md)  
[Tutorial: Einführung in Power BI Q&A](power-bi-visualization-introduction-to-q-and-a.md)  
[Abrufen von Daten (für Power BI)](service-get-data.md)  
[Power BI – Grundkonzepte](service-basic-concepts.md)

Weitere Fragen? [Wenden Sie sich an die Power BI-Community](http://community.powerbi.com/)

