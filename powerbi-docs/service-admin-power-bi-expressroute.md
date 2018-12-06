---
title: Power BI und ExpressRoute
description: Power BI und ExpressRoute
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-admin
ms.topic: conceptual
ms.date: 12/03/2018
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: 62289c974e25207f3a991e7f17a0ee965c729b8a
ms.sourcegitcommit: b03912343a5a214c6bb972aaa6aa051c2a5f4332
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2018
ms.locfileid: "52900127"
---
# <a name="power-bi-and-expressroute"></a>Power BI und ExpressRoute

**ExpressRoute** ist ein Azure-Dienst der Ihnen ermöglicht, private Verbindungen zwischen Azure-Datencentern (wo sich Power BI befindet) und Ihrer lokalen Infrastruktur herzustellen. Alternativ können Sie private Verbindungen zwischen Azure-Datencentern und dem Standort Ihres Servers bei Ihrem Internetdienstanbieter herstellen.

Mit **Power BI** und **ExpressRoute** können Sie auch eine private Netzwerkverbindung zwischen Ihrer Organisation oder dem Standort Ihres Servers bei Ihrem Internetdienstanbieter und Power BI einrichten. Dabei umgehen Sie das Internet, um Ihre sensiblen Power BI-Daten und Verbindungen besser zu schützen.

Weitere Informationen finden Sie unter [ExpressRoute-Übersicht](/azure/expressroute/expressroute-introduction). Power BI ist bis auf einige Ausnahmen zu ExpressRoute konform, bei denen Power BI Daten über das öffentliche Internet abruft oder verschickt. Eine Liste der URLs, die Power BI verwendet, finden Sie unter [Power BI-URLs](power-bi-whitelist-urls.md).

![ExpressRoute-Diagramm](media/service-admin-power-bi-expressroute/pbi_expressroute_1.png)