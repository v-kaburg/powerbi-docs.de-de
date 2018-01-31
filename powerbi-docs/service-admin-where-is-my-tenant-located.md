---
title: Wo befindet sich mein Power BI-Mandant?
description: "Hier erfahren Sie, wo sich der Power BI-Mandant befindet und wie dieser Ort ausgewählt wird. Dies ist wichtig, da der Ort Auswirkungen auf Interaktionen mit dem Dienst hat."
services: powerbi
documentationcenter: 
author: markingmyname
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
ms.date: 08/10/2017
ms.author: maghan
ms.openlocfilehash: 51d54d0ee8f21eec076389c1370f7bad415fa412
ms.sourcegitcommit: 6e693f9caf98385a2c45890cd0fbf2403f0dbb8a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2018
---
# <a name="where-is-my-power-bi-tenant-located"></a>Wo befindet sich mein Power BI-Mandant?
<iframe width="560" height="315" src="https://www.youtube.com/embed/0fOxaHJPvdM?showinfo=0" frameborder="0" allowfullscreen></iframe>

Hier erfahren Sie, wo sich der Power BI-Mandant befindet und wie dieser Ort ausgewählt wird. Dies ist wichtig, da der Ort Auswirkungen auf Interaktionen mit dem Dienst hat.

## <a name="how-to-determine-where-your-power-bi-tenant-is-located"></a>So bestimmen Sie, wo sich der Power BI-Mandant befindet
Sie können wie folgt vorgehen, um die Region zu ermitteln, in der sich der Mandant befindet.

1. Wählen Sie das **?** im Power BI-Dienst aus.
2. Wählen Sie **Info** aus.
3. Betrachten Sie den Wert neben **Ihre Daten sind gespeichert in**. Dies ist die Region, in der Sie sich befinden.

![](media/service-admin-where-is-my-tenant-located/power-bi-data-region.png)

## <a name="how-the-data-region-is-selected"></a>So wird der Datenbereich ausgewählt
Der Datenbereich ist abhängig von dem Land, das beim Erstellen des Mandanten ausgewählt wurde. Dies gilt für die Registrierung für Office 365 sowie für Power BI, da diese Informationen gemeinsam verwendet werden. Wenn es sich um einen neuen Mandanten handelt, wird eine Dropdownliste für das Land angezeigt.

![](media/service-admin-where-is-my-tenant-located/sign-up-country-selection.png)

Der hier ausgewählte Wert bestimmt den Ort, an dem Ihre Daten gespeichert werden. Power BI wählt einen dieser Auswahl möglichst nahe gelegenen Datenbereich aus.

> [!WARNING]
> Diese Auswahl kann nicht geändert werden.
> 
> 

Weitere Fragen? [Wenden Sie sich an die Power BI-Community](http://community.powerbi.com/)

