---
title: Wo befindet sich mein Power BI-Mandant?
description: Hier erfahren Sie, wo sich der Power BI-Mandant befindet und wie dieser Ort ausgewählt wird. Dies ist wichtig, um zu erfahren, da sie Interaktionen mit dem Dienst haben Sie sich auswirken kann.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 05/03/2019
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: 06b7ba4bfc68358887af28bd2595b442df90d334
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2019
ms.locfileid: "65710505"
---
# <a name="where-is-my-power-bi-tenant-located"></a>Wo befindet sich mein Power BI-Mandant?

<iframe width="560" height="315" src="https://www.youtube.com/embed/0fOxaHJPvdM?showinfo=0" frameborder="0" allowfullscreen></iframe>

Hier erfahren Sie, wo sich der Power BI-Mandant befindet und wie dieser Ort ausgewählt wird. Lernen, dass der Speicherort wichtig, da sie die Interaktionen auswirken kann, müssen Sie mit dem Dienst.

## <a name="how-to-determine-where-your-power-bi-tenant-is-located"></a>So bestimmen Sie, wo sich der Power BI-Mandant befindet

Um die Region zu suchen, in der sich Ihr Mandant befindet, führen Sie die folgenden Schritte aus.

1. Klicken Sie im Power BI-Dienst im oberen Menü auf das Hilfesymbol ( **?** ) und dann auf **Info zu Power BI**.

1. Betrachten Sie den Wert neben **Ihre Daten sind gespeichert in**. Es ist die Region, wo sich Ihr Mandant befindet. Der Wert ist auch die Region, in dem Ihre Daten gespeichert werden, es sei denn, Sie dedizierte Kapazität für Ihre Arbeitsbereiche in verschiedenen Regionen verwenden.

    ![Datenbereich](media/service-admin-where-is-my-tenant-located/power-bi-data-region.png)

## <a name="how-the-data-region-is-selected"></a>So wird der Datenbereich ausgewählt

Die Datenregion basiert auf dem Land, das Sie beim Erstellen des Mandanten auswählen. Die Auswahl gilt für sowohl Office 365 und Power BI, registrieren Sie sich daran, dass diese Informationen freigegeben wird. Wenn es sich um einen neuen Mandanten handelt, wählen Sie beim Registrieren das entsprechende Land aus der Liste aus.

![Auswahl des Landes](media/service-admin-where-is-my-tenant-located/sign-up-country-selection.png)

Powerbi wählt ein Ihre Auswahl, die bestimmt, in dem Daten gespeichert werden, für Ihren Mandanten möglichst nahe gelegenen Datenbereich aus.

> [!IMPORTANT]
> Die Auswahl kann nicht geändert werden, nach der Erstellung des Mandantenverwaltungs.

Weitere Fragen? [Wenden Sie sich an die Power BI-Community](http://community.powerbi.com/)

