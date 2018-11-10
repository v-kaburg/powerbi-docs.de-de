---
title: Wo befindet sich mein Power BI-Mandant?
description: Hier erfahren Sie, wo sich der Power BI-Mandant befindet und wie dieser Ort ausgewählt wird. Dies ist wichtig, da der Ort Auswirkungen auf Interaktionen mit dem Dienst hat.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-admin
ms.topic: conceptual
ms.date: 10/31/2018
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: b396b55304e468143fe28fb5ed46ed290bfb3812
ms.sourcegitcommit: 0611860a896e636ceeb6e30ce85243bfd8e7b61d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2018
ms.locfileid: "50909523"
---
# <a name="where-is-my-power-bi-tenant-located"></a>Wo befindet sich mein Power BI-Mandant?

<iframe width="560" height="315" src="https://www.youtube.com/embed/0fOxaHJPvdM?showinfo=0" frameborder="0" allowfullscreen></iframe>

Hier erfahren Sie, wo sich der Power BI-Mandant befindet und wie dieser Ort ausgewählt wird. Die genaue Kenntnis des Orts ist wichtig, da dieser sich auf Ihre Interaktionen mit dem Dienst auswirken kann.

## <a name="how-to-determine-where-your-power-bi-tenant-is-located"></a>So bestimmen Sie, wo sich der Power BI-Mandant befindet

Um die Region zu suchen, in der sich Ihr Mandant befindet, führen Sie die folgenden Schritte aus.

1. Klicken Sie im Power BI-Dienst im oberen Menü auf das Hilfesymbol (**?**) und dann auf **Info zu Power BI**.

1. Betrachten Sie den Wert neben **Ihre Daten sind gespeichert in**. Dies ist die Region, in der sich Ihr Mandant befindet.

    ![Datenregion](media/service-admin-where-is-my-tenant-located/power-bi-data-region.png)

## <a name="how-the-data-region-is-selected"></a>Auswahl der Datenregion

Die Datenregion basiert auf dem Land, das Sie beim Erstellen des Mandanten auswählen. Dies gilt für die Registrierung für Office 365 sowie für Power BI, da diese Informationen gemeinsam verwendet werden. Wenn es sich um einen neuen Mandanten handelt, wählen Sie beim Registrieren das entsprechende Land aus der Liste aus.

![Auswahl des Landes](media/service-admin-where-is-my-tenant-located/sign-up-country-selection.png)

Power BI wählt eine Datenregion aus, die sich möglichst nah an dem ausgewählten Land befindet – damit wird festgelegt, wo die Daten für Ihren Mandanten gespeichert werden.

> [!IMPORTANT]
> Diese Auswahl kann nach Erstellung des Mandanten nicht geändert werden.

Weitere Fragen? [Wenden Sie sich an die Power BI-Community](http://community.powerbi.com/)

