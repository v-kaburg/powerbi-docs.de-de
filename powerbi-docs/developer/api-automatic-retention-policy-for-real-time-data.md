---
title: Power BI-APIs mit automatischer Aufbewahrungsrichtlinie für Echtzeitdaten
description: Erfahren Sie mehr über die automatische Aufbewahrungsrichtlinie im Power BI-Dienst.
author: markingmyname
manager: kfile
ms.author: maghan
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 06/08/2018
ms.openlocfilehash: 9b5923c7bd92b1fe53ebb7ab9416aca8cece3cfa
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/15/2019
ms.locfileid: "54294378"
---
# <a name="automatic-retention-policy-for-real-time-data"></a>Automatische Beibehaltungsrichtlinie für Echtzeitdaten

Die automatische Beibehaltungsrichtlinie im Power BI-Dienst ist eine Abfragezeichenfolge, die eine standardmäßige Beibehaltungsrichtlinie zum automatischen Bereinigen veralteter Daten aktiviert, während ein konstanter Fluss neuer Daten in das Dashboard gewahrt bleibt. Die erste Aufbewahrungsrichtlinie wird als *Basis-FIFO* (First In, First Out) bezeichnet. Wenn diese Richtlinie aktiviert ist, werden die Daten in einer Tabelle gesammelt, bis max. 200.000 Zeilen erreicht sind. Sobald die Daten über 200.000 Zeilen hinausgehen, werden die ältesten Zeilen aus dem Dataset gelöscht. Dadurch werden zwischen 200.000 und 210.000 Zeilen mit ausschließlich den neuesten Daten beibehalten.  
  
<center>

![Beibehaltungsrichtlinie](media/api-Automatic-retention-policy-for-real-time-data/retention-policy.png) 

</center>

Die Beibehaltungsrichtlinien werden beim ersten Erstellen Ihrer Datasets aktiviert. Dazu müssen Sie Ihrem POST-Aufruf für Datasets lediglich den Abfrageparameter „defaultRetentionPolicy“ hinzufügen und ihn auf *basicFIFO* festlegen.  
  
    POST https://api.powerbi.com/v1.0/myorg/datasets?defaultRetentionPolicy={None | basicFIFO}