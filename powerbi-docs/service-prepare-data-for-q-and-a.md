---
title: Stellen Sie die Excel-Daten für Q & A in Power BI arbeiten.
description: Optimieren Ihrer Daten für Q&A in Power BI
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 05/13/2019
ms.author: maggies
LocalizationGroup: Ask questions of your data
ms.openlocfilehash: 7ed8eb8e205c05582d2cfd93030ab056be77912a
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2019
ms.locfileid: "65624983"
---
# <a name="make-excel-data-work-well-with-qa-in-power-bi"></a>Stellen Sie die Excel-Daten für Q & A in Power BI arbeiten.
Wenn Sie Datenmodelle oder Excel-Arbeitsmappen erstellen, die mit Power BI verwendet werden, lesen Sie weiter...

Q&A kann in Power BI strukturierte Daten suchen und die richtige Visualisierung für Ihre Frage auswählen – genau diese Funktion macht Power BI zu einem so überzeugenden Tool.   

Q&A funktioniert mit allen hochgeladenen Excel-Dateien, die Tabellen, Bereiche oder PowerPivot-Modelle enthalten. Je häufiger Sie optimieren und Ihre Daten bereinigen, desto robuster wird die Q&A-Leistung.  Wenn Sie beabsichtigen, auf dem Dataset basierende Berichte und Dashboards freizugeben, möchten Sie, dass Ihre Kollegen bequem Fragen stellen können und aufschlussreiche Antworten erhalten.

## <a name="how-qa-works-with-excel"></a>Funktionsweise von Q&A mit Excel
Q&A verfügt über eine Reihe grundlegender Funktionen zum Verstehen natürlicher Sprachen, die Sie für Ihre Daten anwenden können. Es verfügt über eine kontextabhängigen Schlüsselwortsuche für Ihre Excel-Tabelle, die Spalte und die berechneten Feldnamen. Außerdem weiß das Programm, wie Daten gefiltert, sortiert, zusammengeführt, gruppiert und angezeigt werden sollen. 

In einer Excel-Tabelle mit dem Namen „Verkauf“ mit den Spalten „Produkt“, „Monat“, „Verkaufte Einheiten“, „Bruttoumsatz“ und „Gewinn“ können Sie beispielsweise Fragen zu diesen Entitäten stellen.  Sie können beispielsweise die Umsätze oder den Gesamtgewinn pro Monat anzeigen, die Produkte nach verkauften Einheiten sortieren usw. Erfahren Sie mehr über [mit Q & A in Dashboards und Berichten](power-bi-tutorial-q-and-a.md), und [visualisierungstypen, die Sie angeben können, in einer f & A-Abfrage](visuals/power-bi-visualization-types-for-reports-and-q-and-a.md).

## <a name="prepare-an-excel-dataset-for-qa"></a>Vorbereiten eines Excel-Datasets für Q&A
Q&A stützt sich auf die Namen der Tabellen, Spalten und berechneten Felder, um datenspezifische Fragen zu beantworten. Daher sind die Bezeichnungen der Entitäten in Ihrer Arbeitsmappe von großer Bedeutung.

Hier finden Sie einige Tipps zur optimalen Nutzung von Q&A in der Arbeitsmappe.

* Stellen Sie sicher, dass Ihre Daten in einer Excel-Tabelle gespeichert sind. [So erstellen Sie eine Excel-Tabelle](https://support.office.com/article/Create-an-Excel-table-in-a-worksheet-e81aa349-b006-4f8a-9806-5af9df0ac664).
* Stellen Sie sicher, dass die Tabellen, Spalten und berechneten Felds sinnvoll in natürlicher Sprache benannt sind.
  
  Wenn Sie z. B. eine Tabelle mit Verkaufsdaten haben, nennen Sie die Tabelle „Vertrieb“. Spaltennamen wie „Jahr“, „Produkt“, „Vertriebsmitarbeiter“ und „Betrag“ funktionieren in Q&A sehr gut.

* Wenn die Arbeitsmappe ein PowerPivot-Datenmodell aufweist, können Sie noch mehr Optimierungen durchführen. Unter [Demystifying Power BI Q&A Part 2](http://blogs.msdn.com/b/powerbi/archive/2014/02/27/demystifying-power-bi-q-amp-a-part-2.aspx) erhalten Sie von unserem Expertenteam für natürliche Sprachen weitere Informationen.

* Öffnen Sie das Dataset in Power BI Desktop, und erstellen Sie neue Spalten, erstellen Sie berechnete Measures, verketten Sie Felder, um eindeutige Werte zu erstellen, klassifizieren Sie Daten nach Typ (z.B. Datumsangaben, Zeichenfolgen, Geografie, Bilder, URLs), und führen Sie weitere Aktionen aus.

## <a name="next-steps"></a>Nächste Schritte

- [Q & A für Consumer](consumer/end-user-q-and-a.md)  
- [Verwenden von Q & A in Dashboards und Berichten](power-bi-tutorial-q-and-a.md)
- [Vorbereiten von lokalen Datasets für Q & A](service-q-and-a-direct-query.md)   
- [Abrufen von Daten (für Power BI)](service-get-data.md)  

Weitere Fragen? [Wenden Sie sich an die Power BI-Community](http://community.powerbi.com/)

