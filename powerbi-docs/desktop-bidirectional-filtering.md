---
title: Bidirektionale Kreuzfilterung in Power BI Desktop (Vorschau)
description: Aktivieren der Kreuzfilterung mithilfe von DirectQuery in Power BI Desktop
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
ms.openlocfilehash: 7946a9389897c4401e581482c0630547a764616d
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2017
---
# <a name="bidirectional-cross-filtering-using-directquery-in-power-bi-desktop-preview"></a>Bidirektionale Kreuzfilterung mithilfe von DirectQuery in Power BI Desktop (Vorschau)

Beim Filtern von Tabellen zum Erstellen der entsprechenden Anzeige von Daten stehen Berichtersteller (und Datenmodellierer) vor Herausforderungen, wenn sie festlegen, wie bei einem Bericht das Filtern angewendet wird. Der Filterkontext einer Tabelle besteht nur auf der einen Seite der Beziehung, jedoch nicht auf der anderen Seite. Dies erfordert oftmals komplexe DAX-Formeln, um die gewünschten Ergebnisse zu erzielen.

Mit der bidirektionalen Kreuzfilterung haben Berichtersteller (und Datenmodellierer) nun eine bessere Kontrolle darüber, wie bei der Arbeit mit verknüpften Tabellen Filter angewendet werden, indem es Filtern ermöglicht wird, auf *beide* Seiten einer Tabellenbeziehung angewendet zu werden. Dies wird erreicht, indem der Filterkontext auf eine zweite verknüpfte Tabelle auf der anderen Seite einer Tabellenbeziehung verteilt wird.

Es ist ein [detailliertes Whitepaper](http://download.microsoft.com/download/2/7/8/2782DF95-3E0D-40CD-BFC8-749A2882E109/Bidirectional%20cross-filtering%20in%20Analysis%20Services%202016%20and%20Power%20BI.docx) verfügbar, das die bidirektionale Kreuzfilterung in Power BI Desktop erklärt (das Whitepaper deckt auch SQL Server Analysis Services 2016 ab, da beide sich gleich verhalten).

* Herunterladen des Whitepapers [Bidirectional cross-filtering for Power BI Desktop](http://download.microsoft.com/download/2/7/8/2782DF95-3E0D-40CD-BFC8-749A2882E109/Bidirectional%20cross-filtering%20in%20Analysis%20Services%202016%20and%20Power%20BI.docx) (Bidirektionale Kreuzfilterung für Power BI Desktop)

### <a name="enabling-bidirectional-cross-filtering-for-directquery"></a>Aktivieren der bidirektionalen Kreuzfilterung für DirectQuery
Sie müssen die Kreuzfilterung für DirectQuery zunächst aktivieren, um sie verwenden zu können. Hierbei handelt es sich um eine Vorschaufunktion, d.h. die Verfügbarkeit und das Verhalten der Funktion unterliegt den Änderungen in zukünftigen Releases von Power BI Desktop.

Um die Kreuzfilterung für DirectQuery in Power BI Desktop zu aktivieren, wählen Sie **Datei > Optionen und Einstellungen > Optionen** aus, und aktivieren Sie anschließend das Kontrollkästchen neben **Kreuzfilterung in beide Richtungen für DirectQuery aktivieren**, wie in der folgenden Abbildung dargestellt.

![](media/desktop-bidirectional-filtering/bidirectional-filtering_1.png)

> [!NOTE]
> Verwenden Sie beim Erstellen von DAX-Formeln für die Kreuzfilterung in Power BI Desktop *UserPrincipalName* (oft mit der Anmeldung eines Benutzers, z.B. *joe@contoso.com*, identisch) anstelle von *UserName*. Daher müssen Sie möglicherweise eine verknüpfte Tabelle erstellen, die *UserPrincipleName* *UserName* (oder z.B. EmployeeID) zuordnet.
> 
> 

Folgendes muss ausgewählt sein, um die Kreuzfilterung im Dialogfeld **Beziehung bearbeiten** für eine Beziehung zu aktivieren:

* **Kreuzfilterrichtung** muss auf **Beide** festgelegt sein
* Die Option **Sicherheitsfilter in beide Richtungen anwenden** muss ebenfalls ausgewählt sein
  
  ![](media/desktop-bidirectional-filtering/bidirectional-filtering_2.png)

Weitere Informationen und Beispiele zur Funktionsweise der bidirektionalen Kreuzfilterung finden Sie in dem weiter oben in diesem Artikel genannten [Whitepaper](http://download.microsoft.com/download/2/7/8/2782DF95-3E0D-40CD-BFC8-749A2882E109/Bidirectional%20cross-filtering%20in%20Analysis%20Services%202016%20and%20Power%20BI.docx).

