---
title: Wo befindet sich mein Power BI-Mandant?
description: Hier erfahren Sie, wo sich der Power BI-Mandant befindet und wie dieser Ort ausgewählt wird. Dies ist wichtig, da der Ort Auswirkungen auf Interaktionen mit dem Dienst hat.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-admin
ms.topic: conceptual
ms.date: 08/10/2017
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: c0c6de63292d3087aaa78dd97b73f868ef9d804e
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2018
ms.locfileid: "34293649"
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

