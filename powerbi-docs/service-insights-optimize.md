---
title: "Optimieren von Daten für schnelle Einblicke in Power BI"
description: "Optimieren Sie Ihre Daten für schnelle Einblicke in Power BI. Wenn Power BI keine Einblicke in den Daten findet, finden Sie im Folgenden mögliche Lösungsansätze."
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
ms.date: 09/02/2017
ms.author: mihart
ms.openlocfilehash: 61901d0055c22540ec2f10bedbbb8cf641d606e9
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2017
---
# <a name="optimize-your-data-for-power-bi-quick-insights"></a>Optimieren von Daten für schnelle Einblicke in Power BI
Sie möchten die Ergebnisse der schnellen Einblicke verbessern?  Wenn Sie Besitzer eines Datasets sind, probieren Sie Folgendes:

* Blenden Sie Spalten im Dataset aus oder ein. Für schnelle Einblicke in Power BI werden ausgeblendete Spalten nicht durchsucht.  Blenden Sie daher doppelt vorhandene oder nicht benötigte Spalten aus, und blenden Sie relevante Spalten ein.
* Verwenden Sie eine Mischung aus Datentypen wie z. B. Namen, Uhrzeiten, Datumsangaben und Zahlen.
* Vermeiden Sie Spalten mit doppelt vorhandenen Informationen (oder blenden Sie sie aus).  Die Suche nach sinnvollen Mustern nimmt wertvolle Zeit in Anspruch.  Dies gilt z. B. für eine Spalte mit ausgeschriebenen Namen von Bundesstaaten und eine anderen Spalte mit Namen deren Abkürzungen.
* Erhalten Sie eine Fehlermeldung, die besagt, dass Ihre Daten statistisch nicht signifikant sind?  Dies kann mit Modellen geschehen, die entweder sehr einfach sind, die über wenige Daten verfügen oder keine Daten oder keine Datumsspalten oder numerische Spalten aufweisen. Ihr Dataset muss über mindestens eine Dimension und ein Measure verfügen, um Einblicke zu generieren.

### <a name="next-steps"></a>Nächste Schritte
[Schnelle Einblicke in Power BI](service-insights.md)

Weitere Fragen? [Wenden Sie sich an die Power BI-Community](http://community.powerbi.com/)

