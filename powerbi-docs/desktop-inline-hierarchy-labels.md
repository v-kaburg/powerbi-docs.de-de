---
title: Verwenden von Inlinehierarchiebeschriftungen in Power BI Desktop
description: Verwenden von Inlinehierarchiebeschriftungen in Power BI Desktop
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
ms.date: 09/06/2017
ms.author: davidi
ms.openlocfilehash: 470b25af4ee59542d010d3e649d25da7305319ad
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2017
---
# <a name="use-inline-hierarchy-labels-in-power-bi-desktop"></a>Verwenden von Inlinehierarchiebeschriftungen in Power BI Desktop
**Power BI Desktop** unterstützt die Verwendung von **Inlinehierarchiebeschriftungen**. Dies ist das erste von zwei Features, die die Ermittlung hierarchischer Details verbessern sollen. Das zweite Feature, das derzeit entwickelt wird, ist die Fähigkeit, geschachtelte Hierarchiebeschriftungen zu verwenden (achten Sie auf weitere Updates).   

## <a name="how-inline-hierarchy-labels-work"></a>Funktionsweise von Inlinehierarchiebeschriftungen
Mit Inlinehierarchiebeschriftungen werden bei der Erweiterung von Visualisierungen mit dem Feature **Alle erweitern** Hierarchiebeschriftungen angezeigt. Ein großer Vorteil dieser Hierarchiebeschriftungen ist, dass Sie diese beim Erweitern der Hierarchiedaten auch **sortieren** können.

### <a name="using-the-built-in-expand-all-feature-without-sorting-by-hierarchy-labels"></a>Verwenden des integrierten Features „Alle erweitern“ (ohne Sortierung nach Hierarchiebeschriftungen)
Bevor wir uns Inlinehierarchiebeschriftungen in Aktion ansehen, werfen wir einen Blick auf das Verhalten des Standardfeatures **Alle erweitern**. Dies verdeutlicht, wie nützlich Inlinehierarchiebeschriftungen sein können

Die folgende Abbildung zeigt ein visuelles Balkendiagramm für den Jahresumsatz. Wenn Sie mit der rechten Maustaste klicken, können Sie **Alle erweitern** auswählen.

![](media/desktop-inline-hierarchy-labels/inlinehierarchy_4.png)

Nachdem Sie **Alle erweitern** ausgewählt haben, wird die Datenhierarchie in der Visualisierung von *Jahr* zu *Quartal* erweitert, wie in der folgenden Abbildung dargestellt.

![](media/desktop-inline-hierarchy-labels/inlinehierarchy_5.png)

Die Beschriftungen *Jahr* und *Quartal* werden dabei jeweils in einer Zeile angezeigt. Dieses Beschriftungsschema setzt sich fort, wenn Sie bis zum Ende der Hierarchie weiter **Alle erweitern** auswählen.

![](media/desktop-inline-hierarchy-labels/inlinehierarchy_6.png)

Dies ist die Verhaltensweise der integrierten Hierarchie für *Datum* in Verbindung mit Feldern mit dem Datentyp *Datum/Uhrzeit*. Gehen wir zum nächsten Abschnitt, in dem erläutert wird, was bei der neuen Feature für Inlinehierarchiebeschriftungen anders ist.

### <a name="using-inline-hierarchy-labels"></a>Verwenden von Inlinehierarchiebeschriftungen
Sehen wir uns jetzt ein anderes Diagramm an. Dieses enthält Daten mit einer informellen Hierarchie. In der folgenden Visualisierung wird ein Balkendiagramm für den **SalesAmount** mit *Color* als Achse angezeigt. In diesen Daten bilden *Color* und *Class* eine informelle Hierarchie. Von hier aus können Sie erneut *Alle erweitern* auswählen, um einen Drilldown in der Hierarchie durchzuführen.

![](media/desktop-inline-hierarchy-labels/inlinehierarchy_7.png)

Durch Auswahl von **Alle erweitern** wird die nächste Ebene mit der Inlineanzeige von Hierarchiebeschriftungen angezeigt. Standardmäßig werden Inlinehierarchien nach Measurewert sortiert – in diesem Fall **SalesAmount**. Wenn Sie Inlinehierarchiebeschriftungen aktivieren, können Sie diese Daten auch nach Hierarchie sortiere. Klicken Sie hierfür rechts oben die Auslassungszeichen (**...**), und wählen Sie dann **Sortieren nach > Color Class**, wie in der folgenden Abbildung dargestellt.

![](media/desktop-inline-hierarchy-labels/inlinehierarchy_8.png)

Sobald **Color Class** ausgewählt ist, werden die Daten nach der informellen Hierarchieauswahl sortiert, wie in der folgenden Abbildung dargestellt.

![](media/desktop-inline-hierarchy-labels/inlinehierarchy_9.png)

> [!NOTE]
> Mit dem Feature für Inlinehierarchiebeschriftungen kann die integrierte Zeithierarchie noch nicht nach Wert, sondern nur nach hierarchischer Reihenfolge sortiert werden.
> 
> 

## <a name="troubleshooting"></a>Problembehandlung
Es kann vorkommen, dass Ihre Visualisierungen in einer erweiterten Inlinehierarchieebene hängenbleiben. Möglicherweise stellen Sie fest, dass Ihre Visualisierungen in dem Modus hängenbleiben, in dem sie erweitert wurden. Ein Drillup funktioniert in diesem Fall nicht. Dies kann passieren, wenn Sie die folgenden Schritte ausführen (die Lösung finden Sie *unter* diesen Schritten):

Schritte, bei denen Ihre Visualisierungen in einem erweiterten Zustand hängenbleiben können:

1. Sie aktivieren das Feature für **Inlinehierarchiebeschriftung**.
2. Sie erstellen Visualisierungen mit Hierarchien.
3. Anschließend wählen Sie **Alle erweitern** und speichern die Datei.
4. *Deaktivieren* Sie als Nächstes das Feature für die **Inlinehierarchiebeschriftung**, und starten Sie Power BI Desktop neu.
5. Öffnen Sie erneut Ihre Datei.

Wenn Sie diese Schritte ausführen und Ihre Visualisierungen im erweiterten Modus hängenbleiben, können Sie dies wie folgt lösen:

1. Aktivieren Sie erneut das Feature für die **Inlinehierarchiebeschriftung**, und starten Sie Power BI Desktop neu.
2. Öffnen Sie Ihre Datei erneut, und führen Sie einen Drillup zum Anfang der betroffenen Visualisierungen durch.
3. Speichern Sie die Datei.
4. Deaktivieren Sie das Feature für **Inlinehierarchiebeschriftungen**, und starten Sie Power BI Desktop anschließend neu.
5. Öffnen Sie erneut Ihre Datei.

Sie können Ihre Visualisierung auch löschen und neu erstellen.

