---
title: Wo befindet sich mein Power BI-Mandant?
description: Hier erfahren Sie, wo sich der Power BI-Mandant befindet und wie dieser Ort ausgewählt wird. Dies ist wichtig, da der Ort Auswirkungen auf Interaktionen mit dem Dienst hat.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 10/31/2018
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: 08536d412796b1516b689ed728af0126330edf93
ms.sourcegitcommit: 378265939126fd7c96cb9334dac587fc80291e97
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/07/2019
ms.locfileid: "57580134"
---
# <a name="where-is-my-power-bi-tenant-located"></a>Wo befindet sich mein Power BI-Mandant?

<iframe width="560" height="315" src="https://www.youtube.com/embed/0fOxaHJPvdM?showinfo=0" frameborder="0" allowfullscreen></iframe>

Hier erfahren Sie, wo sich der Power BI-Mandant befindet und wie dieser Ort ausgewählt wird. Die genaue Kenntnis des Orts ist wichtig, da dieser sich auf Ihre Interaktionen mit dem Dienst auswirken kann.

## <a name="how-to-determine-where-your-power-bi-tenant-is-located"></a>So bestimmen Sie, wo sich der Power BI-Mandant befindet

Um die Region zu suchen, in der sich Ihr Mandant befindet, führen Sie die folgenden Schritte aus.

1. Klicken Sie im Power BI-Dienst im oberen Menü auf das Hilfesymbol (**?**) und dann auf **Info zu Power BI**.

1. Betrachten Sie den Wert neben **Ihre Daten sind gespeichert in**. Dies ist die Region, in der sich Ihr Mandant befindet. Dies ist auch die Region, in der Ihre Daten gespeichert werden, sofern Sie nicht dedizierte Kapazitäten in verschiedenen Regionen für Ihre Arbeitsbereiche verwenden.

    ![Datenbereich](media/service-admin-where-is-my-tenant-located/power-bi-data-region.png)

## <a name="how-the-data-region-is-selected"></a>So wird der Datenbereich ausgewählt

Die Datenregion basiert auf dem Land, das Sie beim Erstellen des Mandanten auswählen. Dies gilt für die Registrierung für Office 365 sowie für Power BI, da diese Informationen gemeinsam verwendet werden. Wenn es sich um einen neuen Mandanten handelt, wählen Sie beim Registrieren das entsprechende Land aus der Liste aus.

![Auswahl des Landes](media/service-admin-where-is-my-tenant-located/sign-up-country-selection.png)

Power BI wählt eine Datenregion aus, die sich möglichst nah an dem ausgewählten Land befindet – damit wird festgelegt, wo die Daten für Ihren Mandanten gespeichert werden.

> [!IMPORTANT]
> Diese Auswahl kann nach Erstellung des Mandanten nicht geändert werden.

Weitere Fragen? [Wenden Sie sich an die Power BI-Community](http://community.powerbi.com/)

