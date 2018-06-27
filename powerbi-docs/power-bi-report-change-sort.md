---
title: Ändern der Sortierung eines Diagramms in einem Power BI-Bericht
description: Ändern der Sortierung eines Diagramms in einem Power BI-Bericht
author: mihart
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 05/20/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 3c32fc3cc9dc2b16384016ca624d4dd3a773aacb
ms.sourcegitcommit: 2a7bbb1fa24a49d2278a90cb0c4be543d7267bda
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2018
ms.locfileid: "34561791"
---
# <a name="change-how-a-chart-is-sorted-in-a-power-bi-report"></a>Ändern der Sortierung eines Diagramms in einem Power BI-Bericht
In einem Power BI-Bericht können Sie die meisten Visualisierungen alphabetisch nach den Namen der Kategorien im Diagramm oder nach den numerischen Werten jeder Kategorie sortieren. In diesem Diagramm wird z. B. nach Geschäftsnamen sortiert.

![](media/power-bi-report-change-sort/pbi_chartsortcategory.png)

Sie können ganz einfach statt nach einer Kategorie (Geschäftsname) nach einem Wert (Umsatz pro Quadratfuß) sortieren.

1. Wählen Sie die Auslassungspunkte (...) und dann **Sortieren nach Sales Per Sq Ft** aus.
2. Aktivieren Sie bei Bedarf das Sortiersymbol ![](media/power-bi-report-change-sort/sorticon.png), um auf **Absteigend** zu wechseln.

   ![](media/power-bi-report-change-sort/sortby.gif)

   **Hinweis**: Nicht alle Visualisierungen können sortiert werden.  Beispielsweise können die folgenden Visuals nicht sortiert werden: Treemaps, Karten, Flächenkartogramme, Punktdiagramme, Tachometerdiagramme, Kartendiagramme, mehrzeilige Kartendiagramme, Wasserfalldiagramme.

## <a name="saving-changes-you-make-to-sort-order"></a>Speichern der Änderungen an der Sortierreihenfolge
Power BI-Berichte behalten die von Ihnen vorgenommenen Änderungen am Filter, Slicer, der Sortierung und anderen Datenansichten, bei. Wenn Sie also den Bericht verlassen und später zurückkehren, sind Ihre Änderungen gespeichert.  Wenn Sie Ihre Änderungen auf die Einstellungen des Berichtsautors zurücksetzen möchten, wählen Sie auf der oberen Menüleiste **Auf Standardwert zurücksetzen** aus. 

![Sortierung beibehalten](media/power-bi-report-change-sort/power-bi-reset-to-default.png)

Wenn die Schaltfläche **Auf Standardwert zurücksetzen** ausgegraut ist, bedeutet das, dass der Berichtsautor die Option, die Änderungen zu speichern (beizubehalten), deaktiviert hat.

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
