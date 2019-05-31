---
title: Automatische Installation Power BI-apps aus, wenn das Einbetten für Ihre Organisation
description: Informationen Sie zum Installieren von Powerbi-apps automatisch, wenn das Einbetten für Ihre Organisation.
ms.subservice: powerbi-developer
author: rkarlin
ms.author: rkarlin
manager: kfile
ms.topic: how-to
ms.service: powerbi
ms.custom: ''
ms.date: 04/16/2019
ms.openlocfilehash: bb9ba5531c2a23f15ccbf98261e246ab7080aecb
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2019
ms.locfileid: "61376202"
---
# <a name="auto-install-power-bi-apps-when-embedding-for-your-organization"></a>Power BI-apps automatisch installieren, wenn das Einbetten für Ihre Organisation

Zum Einbetten von Inhalten aus einer app, muss der Benutzer, das Einbetten ist haben [Zugriff auf die app](../service-create-distribute-apps.md). Wenn die app für den Benutzer installiert ist, arbeitet das Einbetten von klicken Sie dann nahtlos. Weitere Informationen finden Sie unter [Einbetten von Berichten oder Dashboards aus der app](embed-from-apps.md). Es ist möglich, definiert in "powerbi.com" alle apps werden [automatisch installiert,](https://powerbi.microsoft.com/blog/automatically-install-apps/). Allerdings wird diese Aktion erfolgt auf Mandantenebene und gilt für alle apps.

## <a name="auto-install-app-on-embedding"></a>Automatische Installation der app zum Einbetten

Wenn ein Benutzer Zugriff auf eine app hat, aber die app nicht installiert ist, dann einbetten ein Fehler auftritt. Damit Sie diese Fehler vermeiden, können Sie beim Einbetten von einer app können Sie die automatische Installation der app beim Einbetten von erlauben. Diese Aktion bedeutet, wenn die app, die der Benutzer versucht, betten Sie nicht installiert ist, es automatisch für Sie installiert ist. Der gewünschte Inhalt ruft also sofort, führt der Benutzer einer reibungslos funktionierende Umgebung eingebettet.

## <a name="embed-for-power-bi-users-user-owns-data"></a>Betten Sie für Power BI-Benutzer (Benutzer ist Besitzer der Daten ein)

Um die automatische Installation von apps für Ihre Benutzer zu ermöglichen, müssen Sie Ihre Anwendung die Berechtigung "Inhalts erstellen" erteilen beim [Registrierung Ihrer Anwendung](register-app.md#register-with-the-power-bi-application-registration-tool), oder fügen Sie es hinzu, wenn Sie Ihre app bereits registriert.

![App registrieren erstellt Inhalte](media/embed-auto-install-app/register-app-create-content.png)

Als Nächstes müssen Sie die app-ID in die einbettungs-URL angeben. Zum Bereitstellen der app-ID den Ersteller der app zuerst muss die app installieren und verwenden Sie eine der unterstützten [Power BI-Rest-API](https://docs.microsoft.com/rest/api/power-bi/) Aufrufe - [Get Reports](https://docs.microsoft.com/rest/api/power-bi/reports/getreports) oder [Get Dashboards](https://docs.microsoft.com/rest/api/power-bi/dashboards/getdashboards). Klicken Sie dann muss den Ersteller der app die einbettungs-URL aus der REST-API-Antwort. Die app-ID wird in der URL angezeigt, wenn der Inhalt aus einer app ist.  Nachdem Sie die einbettungs-URL haben, können Sie es verwenden, regelmäßig einbetten.

## <a name="secure-embed"></a>Sichere einbetten

Um die automatische Installation von apps zu verwenden, muss den Ersteller der app zunächst die app installieren und dann wechseln an die app auf "powerbi.com", navigieren Sie zum Bericht, und rufen Sie den Link auf übliche Weise. Alle anderen Benutzer mit Zugriff auf die app, die den Link verwenden können, können den Bericht einbetten.

## <a name="considerations-and-limitations"></a>Überlegungen und Einschränkungen

* Sie können nur Berichte und Dashboards für dieses Szenario einbetten.

* Dieses Feature wird derzeit nicht unterstützt, für die app ist Besitzer der Daten und SharePoint einbetten Szenarien.