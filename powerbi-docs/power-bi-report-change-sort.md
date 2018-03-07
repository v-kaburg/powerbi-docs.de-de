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
ms.date: 01/20/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 8160011a30b54345d446f352148665e3840323d9
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/24/2018
---
# <a name="change-how-a-chart-is-sorted-in-a-power-bi-report"></a>Ändern der Sortierung eines Diagramms in einem Power BI-Bericht
In einem Power BI-Bericht können Sie die meisten Visualisierungen alphabetisch nach den Namen der Kategorien im Diagramm oder nach den numerischen Werten jeder Kategorie sortieren. In diesem Diagramm wird z. B. nach Geschäftsnamen sortiert.

![](media/power-bi-report-change-sort/pbi_chartsortcategory.png)

Sie können ganz einfach statt nach einer Kategorie (Geschäftsname) nach einem Wert (Umsatz pro Quadratfuß) sortieren.

1. Wählen Sie die Auslassungspunkte (...) und dann **Sortieren nach Sales Per Sq Ft** aus.
2. Aktivieren Sie bei Bedarf das Sortiersymbol ![](media/power-bi-report-change-sort/sorticon.png), um auf **Absteigend** zu wechseln.

   ![](media/power-bi-report-change-sort/sortby.gif)

   **Hinweis**: Nicht alle Visualisierungen können sortiert werden.  Beispielsweise können die folgenden Visuals nicht sortiert werden: Treemaps, Karten, Flächenkartogramme, Punktdiagramme, Tachometerdiagramme, Kartendiagramme, mehrzeilige Kartendiagramme, Wasserfalldiagramme.

<a name="other"></a>
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
