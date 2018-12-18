---
title: Ändern der Sortierung eines Diagramms in einem Power BI-Bericht
description: Ändern der Sortierung eines Diagramms in einem Power BI-Bericht
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: Conceptual
ms.date: 09/20/2018
ms.author: mihart
LocalizationGroup: Reports
ms.openlocfilehash: f4ca6633eb401e7df8041ea385284210c14995ad
ms.sourcegitcommit: 4f46d71ff6026c1c158f007425aefdcb501f48ee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/06/2018
ms.locfileid: "52979335"
---
# <a name="change-how-a-chart-is-sorted-in-a-power-bi-report"></a>Ändern der Sortierung eines Diagramms in einem Power BI-Bericht
In einem Power BI-Bericht können Sie die meisten Visualisierungen alphabetisch nach den Namen der Kategorien im Diagramm oder nach den numerischen Werten jeder Kategorie sortieren. In diesem Diagramm wird z.B. nach der Kategorie **Geschäftsname** sortiert.

![](media/end-user-change-sort/pbi_chartsortcategory.png)

Sie können ganz einfach statt nach einer Kategorie (Geschäftsname) nach einem Wert (Umsatz pro Quadratfuß) sortieren.

1. Wählen Sie die Auslassungspunkte (...) und dann **Sortieren nach > Sales Per Sq Ft** (Umsatz pro Quadratfuß) aus.
2. Wählen Sie bei Bedarf erneut die Auslassungspunkte und dann **Absteigend sortieren** aus.

   ![](media/end-user-change-sort/sort.gif)

   **HINWEIS**: Nicht alle Visuals können sortiert werden.  Beispielsweise können die folgenden Visuals nicht sortiert werden: Treemaps, Karten, Flächenkartogramme, Punktdiagramme, Tachometerdiagramme, Kartendiagramme, mehrzeilige Kartendiagramme, Wasserfalldiagramme.

## <a name="saving-changes-you-make-to-sort-order"></a>Speichern der Änderungen an der Sortierreihenfolge
Power BI-Berichte behalten die von Ihnen vorgenommenen Änderungen am Filter, Slicer, der Sortierung und anderen Datenansichten, bei. Wenn Sie also den Bericht verlassen und später zurückkehren, sind Ihre Änderungen gespeichert.  Wenn Sie Ihre Änderungen auf die Einstellungen des Berichterstellers zurücksetzen möchten, wählen Sie auf der oberen Menüleiste **Auf Standardwert zurücksetzen** aus. 

![Sortierung beibehalten](media/end-user-change-sort/power-bi-reset-to-default.png)

Wenn die Schaltfläche **Auf Standardwert zurücksetzen** ausgegraut ist, bedeutet das, dass der Berichtersteller die Option zum Speichern (Beibehalten) der Änderungen deaktiviert hat.

<a name="other"></a>
## <a name="sorting-using-other-criteria"></a>Sortieren mithilfe anderer Kriterien
Zuweilen möchten Sie Ihre Visualisierung anhand eines anderen Felds oder anderer Kriterien sortieren,  beispielsweise nach Monat (anstatt in alphabetischer Reihenfolge) oder nach ganzen Zahlen anstatt nach Ziffer (z. B. 0, 1, 9, 20 und nicht 0, 1, 20, 9).  

In einigen Fällen können Sie möglicherweise das visuelle Element so sortieren, wie Sie möchten, z.B. nach Monat.  Wenn dies jedoch nicht möglich ist, kann die Ursache sein, dass das dem Bericht zugrunde liegende Dataset optimiert werden muss. Bitten Sie den Berichtersteller, das Dataset zu aktualisieren.

## <a name="next-steps"></a>Nächste Schritte
Weitere Informationen zu [Visualisierungen in Power BI-Berichten](end-user-visualizations.md).

[Power BI – Grundkonzepte](end-user-basic-concepts.md)