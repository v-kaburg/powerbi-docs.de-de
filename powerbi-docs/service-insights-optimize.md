---
title: Optimieren von Daten für schnelle Einblicke in Power BI
description: Optimieren Sie Daten für schnelle Einblicke in Power BI. Wenn Power BI keine Einblicke in den Daten findet, finden Sie im Folgenden mögliche Lösungsansätze.
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 03/02/2017
ms.author: maggies
LocalizationGroup: Dashboards
ms.openlocfilehash: 33d8911ee819bbc1ac37976f077edabee368f5aa
ms.sourcegitcommit: a186679e8dae85dce23f6365bf5c36d7f407f15b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/16/2018
ms.locfileid: "51850566"
---
# <a name="optimize-your-data-for-power-bi-quick-insights"></a>Optimieren von Daten für schnelle Einblicke in Power BI
Sie möchten die Ergebnisse der schnellen Einblicke verbessern?  Wenn Sie Besitzer eines Datasets sind, probieren Sie Folgendes:

* Blenden Sie Spalten im Dataset aus oder ein. Für schnelle Einblicke in Power BI werden ausgeblendete Spalten nicht durchsucht.  Blenden Sie daher doppelt vorhandene oder nicht benötigte Spalten aus, und blenden Sie relevante Spalten ein.
* Verwenden Sie eine Mischung aus Datentypen wie z. B. Namen, Uhrzeiten, Datumsangaben und Zahlen.
* Vermeiden Sie Spalten mit doppelt vorhandenen Informationen (oder blenden Sie sie aus).  Die Suche nach sinnvollen Mustern nimmt wertvolle Zeit in Anspruch.  Dies gilt z. B. für eine Spalte mit ausgeschriebenen Namen von Bundesstaaten und eine anderen Spalte mit Namen deren Abkürzungen.
* Erhalten Sie eine Fehlermeldung, die besagt, dass Ihre Daten statistisch nicht signifikant sind?  Dies kann mit Modellen geschehen, die entweder sehr einfach sind, die über wenige Daten verfügen oder keine Daten oder keine Datumsspalten oder numerische Spalten aufweisen. Ihr Dataset muss über mindestens eine Dimension und ein Measure verfügen, um Einblicke zu generieren.

### <a name="next-steps"></a>Nächste Schritte
[Schnelle Einblicke in Power BI](consumer/end-user-insights.md)

Weitere Fragen? [Wenden Sie sich an die Power BI-Community](http://community.powerbi.com/)

