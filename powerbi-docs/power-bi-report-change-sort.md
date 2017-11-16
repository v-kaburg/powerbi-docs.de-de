---
title: "Ändern der Sortierung eines Diagramms in einem Power BI-Bericht"
description: "Ändern der Sortierung eines Diagramms in einem Power BI-Bericht"
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
ms.date: 09/08/2017
ms.author: mihart
ms.openlocfilehash: 37161fab1e19e6ce00eb0f02c96b6e5cbdd60f18
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2017
---
# <a name="change-how-a-chart-is-sorted-in-a-power-bi-report"></a>Ändern der Sortierung eines Diagramms in einem Power BI-Bericht
In Power BI können Sie Diagramme alphabetisch nach den Namen der Kategorien im Diagramm oder nach den numerischen Werten jeder Kategorie sortieren. In diesem Diagramm wird z. B. nach Geschäftsnamen sortiert.

![](media/power-bi-report-change-sort/pbi_chartsortcategory.png)

Es ist ganz leicht, es stattdessen vom höchsten zum niedrigsten Umsatz pro Quadratfuß zu sortieren.

1. Wählen Sie die Auslassungspunkte (...) und dann **Sortieren nach Sales Per Sq Ft** aus.
2. Aktivieren Sie bei Bedarf das Sortiersymbol ![](media/power-bi-report-change-sort/sorticon.png), um auf **Absteigend** zu wechseln.
   
   ![](media/power-bi-report-change-sort/sortby.gif)
   
   **Hinweis**: Nicht alle Visualisierungen können sortiert werden.  Beispielsweise können die folgenden Visuals nicht sortiert werden: Treemaps, Karten, Flächenkartogramme, Punktdiagramme, Tachometerdiagramme, Kartendiagramme, mehrzeilige Kartendiagramme, Wasserfalldiagramme.

## <a name="sorting-using-other-criteria"></a>Sortieren mithilfe anderer Kriterien
Zuweilen möchten Sie Ihre Visualisierung anhand eines anderen Felds oder anderer Kriterien sortieren,  beispielsweise nach Monat (anstatt in alphabetischer Reihenfolge) oder nach ganzen Zahlen anstatt nach Ziffer (z. B. 0, 1, 9, 20 und nicht 0, 1, 20, 9).  

In einigen Fällen können Sie möglicherweise das visuelle Element so sortieren, wie Sie möchten, z.B. nach Monat.  Wenn dies jedoch nicht möglich ist, kann die Ursache sein, dass das dem Bericht zugrunde liegende Dataset optimiert werden muss. Hierfür gibt es mehrere Lösungen:

* Verwenden Sie in Power BI Desktop [die Registerkarte „Datenmodellierungstools“, um nach einer anderen Spalte zu sortieren](desktop-sort-by-column.md).
* Wenn Sie das Dataset besitzen, fügen Sie in Excel eine neue Spalte hinzu, die Monatsname und Anzahl verkettet. Anschließend können Sie das Dataset aktualisieren oder erneut importieren, um die neue Spalte im Bereich „Felder“ anzuzeigen.
* Stellen Sie in Excel sicher, dass Ihre numerischen Spalten mit „Ganze Zahl“ oder „Dezimal“ und nicht mit „Text“ markiert sind.

## <a name="next-steps"></a>Nächste Schritte
Weitere Informationen zu [Visualisierungen in Power BI-Berichten](power-bi-report-visualizations.md).

[Power BI – Grundkonzepte](service-basic-concepts.md)

Weitere Fragen? [Wenden Sie sich an die Power BI-Community](http://community.powerbi.com/)

