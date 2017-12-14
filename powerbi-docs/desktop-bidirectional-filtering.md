---
title: Bidirektionale Kreuzfilterung in Power BI Desktop
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
ms.date: 12/06/2017
ms.author: davidi
ms.openlocfilehash: 59004a6d9baa0e83c94da7394e269bb50797d37b
ms.sourcegitcommit: d91436de68a0e833ecff18d976de9d9431bc4121
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/06/2017
---
# <a name="bidirectional-cross-filtering-using-directquery-in-power-bi-desktop"></a>Bidirektionale Kreuzfilterung mithilfe von DirectQuery in Power BI Desktop

Beim Filtern von Tabellen zum Erstellen der entsprechenden Anzeige von Daten stehen Berichtersteller (und Datenmodellierer) vor Herausforderungen, wenn sie festlegen, wie bei einem Bericht das Filtern angewendet wird. Der Filterkontext einer Tabelle besteht nur auf der einen Seite der Beziehung, jedoch nicht auf der anderen Seite. Dies erfordert oftmals komplexe DAX-Formeln, um die gewünschten Ergebnisse zu erzielen.

Mit der bidirektionalen Kreuzfilterung haben Berichtersteller (und Datenmodellierer) nun eine bessere Kontrolle darüber, wie bei der Arbeit mit verknüpften Tabellen Filter angewendet werden, indem es Filtern ermöglicht wird, auf *beide* Seiten einer Tabellenbeziehung angewendet zu werden. Dies wird erreicht, indem der Filterkontext auf eine zweite verknüpfte Tabelle auf der anderen Seite einer Tabellenbeziehung verteilt wird.

Es ist ein [detailliertes Whitepaper](http://download.microsoft.com/download/2/7/8/2782DF95-3E0D-40CD-BFC8-749A2882E109/Bidirectional%20cross-filtering%20in%20Analysis%20Services%202016%20and%20Power%20BI.docx) verfügbar, das die bidirektionale Kreuzfilterung in Power BI Desktop erklärt (das Whitepaper deckt auch SQL Server Analysis Services 2016 ab, da beide sich gleich verhalten).

* Herunterladen des Whitepapers [Bidirectional cross-filtering for Power BI Desktop](http://download.microsoft.com/download/2/7/8/2782DF95-3E0D-40CD-BFC8-749A2882E109/Bidirectional%20cross-filtering%20in%20Analysis%20Services%202016%20and%20Power%20BI.docx) (Bidirektionale Kreuzfilterung für Power BI Desktop)

### <a name="enabling-bidirectional-cross-filtering-for-directquery"></a>Aktivieren der bidirektionalen Kreuzfilterung für DirectQuery

Folgendes muss ausgewählt sein, um die Kreuzfilterung im Dialogfeld **Beziehung bearbeiten** für eine Beziehung zu aktivieren:

* **Kreuzfilterrichtung** muss auf **Beide** festgelegt sein
* Die Option **Sicherheitsfilter in beide Richtungen anwenden** muss ebenfalls ausgewählt sein
  
  ![](media/desktop-bidirectional-filtering/bidirectional-filtering_2.png)

> [!NOTE]
> Verwenden Sie beim Erstellen von DAX-Formeln für die Kreuzfilterung in Power BI Desktop *UserPrincipalName* (oft mit der Anmeldung eines Benutzers, z.B. *joe@contoso.com*, identisch) anstelle von *UserName*. Daher müssen Sie möglicherweise eine verknüpfte Tabelle erstellen, die *UserPrincipleName* *UserName* (oder z.B. EmployeeID) zuordnet.
> 
> 

Weitere Informationen und Beispiele zur Funktionsweise der bidirektionalen Kreuzfilterung finden Sie in dem weiter oben in diesem Artikel genannten [Whitepaper](http://download.microsoft.com/download/2/7/8/2782DF95-3E0D-40CD-BFC8-749A2882E109/Bidirectional%20cross-filtering%20in%20Analysis%20Services%202016%20and%20Power%20BI.docx).

