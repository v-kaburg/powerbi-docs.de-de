---
title: Erstellen eines Links zu einer bestimmten Stelle in den mobilen Power BI-Apps
description: Erfahren Sie, wie Sie mit einem URI (Uniform Resource Identifier) einen Deep-Link zu einem bestimmten Dashboard, einer bestimmten Kachel oder einem bestimmten Bericht in der mobilen Power BI-App erstellen.
author: mshenhav
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-mobile
ms.topic: conceptual
ms.date: 04/24/2019
ms.author: mshenhav
ms.openlocfilehash: 4e09b10e38b018f8e5572343b343a243ace3bf81
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2019
ms.locfileid: "64906531"
---
# <a name="create-a-link-to-a-specific-location-in-the-power-bi-mobile-apps"></a>Erstellen eines Links zu einer bestimmten Stelle in den mobilen Power BI-Apps
Sie können Links verwenden, auf bestimmte Elemente in Power BI direkt zugreifen: Berichte, Dashboards und Kacheln.

Es sind hauptsächlich zwei Szenarien für die Verwendung von Links in Power BI von Mobilgeräten: 

* Öffnen Sie Power BI aus **außerhalb der app**, und Speichern der bestimmter Inhalte (Bericht/Dashboard/app). Dies ist ein Integrationsszenario, in der Regel auf, wenn Sie Power BI Mobile von anderen app öffnen möchten. 
* Um **navigieren** in Power BI. Dies ist in der Regel, wenn Sie eine benutzerdefinierte Navigation im Power BI erstellen möchten.


## <a name="use-links-from-outside-of-power-bi"></a>Verwenden Sie die Links von außerhalb von Power BI
Wenn Sie eine Verknüpfung von außerhalb von Power BI-app verwenden, möchten Sie sicherstellen, dass es von der Anwendung geöffnet wird und wenn die app nicht auf dem Gerät aus, und klicken Sie dann den Benutzer Informationen zur Installation angeboten installiert ist. Wir haben einen speziellen Link-Format erstellt, um genau diesen Zweck, zu unterstützen. Dieses LinkFormat stellt sicher, dass das Gerät der app beim Öffnen des Links mithilfe wird, und wenn die app nicht auf dem Gerät installiert ist, es den Benutzer bietet, wechseln in den Store, um sie zu erhalten.

Der Link sollte mit folgendem beginnen.  
```html
https://app.powerbi.com/Redirect?[**QUERYPARAMS**]
```

> [!IMPORTANT]
> Wenn Ihr Inhalt in speziellen Datencenter wie Regierung, China usw. gehostet wird. Der Link sollte mit der richtigen Adresse für Power BI beginnen, z. B. `app.powerbigov.us` oder `app.powerbi.cn`.   
>


Die **Abfrage PARAMS** sind:
* **Aktion** (obligatorisch) = OpenApp / OpenDashboard / OpenTile / OpenReport
* **AppId** = sollten Sie Öffnen eines Berichts oder Dashboards, die Teil einer App 
* **GroupObjectId** = sollten Sie Öffnen eines Berichts oder Dashboards, die Teil des Arbeitsbereichs (aber nicht Mein Arbeitsbereich)
* **DashboardObjectId** Dashboardobjekt-ID =, (wenn es sich um eine Aktion OpenDashboard oder OpenTile ist.)
* **ReportObjectId** Berichtsobjekt-ID =, (wenn es sich um eine Aktion OpenReport ist.)
* **TileObjectId** Kachel-Objekt-ID =, (wenn es sich um eine Aktion OpenTile ist.)
* **ReportPage** = sollten Sie bestimmte Berichtsabschnitt öffnen (falls es sich um eine Aktion OpenReport ist.)
* **CtId** = Element Organisations-ID (für B2B-Szenario relevant. Dies kann ausgelassen werden, wenn das Element zur Organisation des Benutzers gehört).

**Beispiele:**

* Öffnen der app-link 
  ```html
  https://app.powerbi.com/Redirect?action=OpenApp&appId=appidguid&ctid=organizationid
  ```

* Dashboard öffnen, die Teil einer App 
  ```html
  https://app.powerbi.com/Redirect?action=OpenDashboard&appId=**appidguid**&dashboardObjectId=**dashboardidguid**&ctid=**organizationid**
  ```

* Bericht öffnen, die Teil eines Arbeitsbereichs
  ```html
  https://app.powerbi.com/Redirect?Action=OpenReport&reportObjectId=**reportidguid**&groupObjectId=**groupidguid**&reportPage=**ReportSectionName**
  ```

### <a name="how-to-get-the-right-link-format"></a>Das LinkFormat der richtige abrufen

#### <a name="links-of-apps-and-items-in-app"></a>Links von apps und Elemente in der app

Für **apps und Berichte und Dashboards, die Teil einer app**, wechseln zu den app-Arbeitsbereich, und wählen "App aktualisieren" ist die einfachste Möglichkeit, den Link. Dadurch wird die Benutzeroberfläche "App veröffentlichen" geöffnet, und finden Sie in der Registerkarte "Datenzugriff" einen **Links** Abschnitt. Erweitern im Abschnitt, und Sie die Liste der app sehen und seinen gesamten Inhalt verknüpft ist, kann verwendet werden, darauf direkt zugreifen.

![Powerbi Veröffentlichen der app-links ](./media/mobile-apps-links/mobile-link-copy-app-links.png)

#### <a name="links-of-items-not-in-app"></a>Links von Elementen, die nicht in-app 

Für Berichte und Dashboards, die nicht Teil einer app sind, müssen Sie die IDs von der Element-URL zu extrahieren.

Um beispielsweise die 36 Zeichen suchen **Dashboard** Objekt-ID, navigieren Sie zum betreffenden Dashboard im Power BI-Dienst 

```html
https://app.powerbi.com/groups/me/dashboards/**dashboard guid comes here**?ctid=**organization id comes here**`
```

Um die 36 Zeichen lange finden **Bericht** Objekt-ID, navigieren Sie zu den Bericht im Power BI-Dienst.
Dies ist ein Beispiel für Bericht über "Mein Arbeitsbereich"

```html
https://app.powerbi.com/groups/me/reports/**report guid comes here**/ReportSection3?ctid=**organization id comes here**`
```
Die obige URL enthält auch bestimmte Berichtsseite **"ReportSection3"** .

Dies ist ein Beispiel eines Berichts aus einem Arbeitsbereich (nicht Mein Arbeitsbereich)

```html
https://app.powerbi.com/groups/**groupid comes here**/reports/**reportid comes here**/ReportSection1?ctid=**organizationid comes here**
```

## <a name="use-links-inside-power-bi"></a>Verwenden Sie die Links in Power BI

Links in Power BI arbeiten in den mobilen apps genau wie in Power BI-Dienst.

Wenn Sie möchten die Verknüpfung zum Bericht hinzufügen, die auf einem anderen Power BI-Element verweist, können Sie nur diese Element-URL aus der Adressleiste des Browsers kopieren. Erfahren Sie mehr über [wie Sie einen Link zu einem Textfeld in einem Bericht hinzufügen](https://docs.microsoft.com/power-bi/service-add-hyperlink-to-text-box).

## <a name="use-report-url-with-filter"></a>Verwenden Sie Berichts-URL mit filter
Wie Power BI-Dienst, unterstützt Power BI Mobile apps auch Berichts-URL, die eine Filter-Abfrage Parameter enthält. Sie können die Öffnen eines Berichts in Power BI Mobile-app und in bestimmten Status filtern. Beispielsweise diese URL wird der Sales-Bericht geöffnet, und Filtern sie nach Gebiet

```html
https://app.powerbi.com/groups/me/reports/**report guid comes here**/ReportSection3?ctid=**organization id comes here**&filter=Store/Territory eq 'NC'
```

Weitere Informationen zum [erstellen Sie die Abfrage Parameter zum Filtern von Berichten](https://docs.microsoft.com/power-bi/service-url-filters).

## <a name="next-steps"></a>Nächste Schritte
Ihr Feedback hilft uns zu entscheiden, welche Features wir künftig realisieren. Geben Sie deshalb Ihr Votum ab, welche Features Sie sich in den mobilen Power BI-Apps wünschen. 

* [Power BI-Apps für mobile Geräte](mobile-apps-for-mobile-devices.md)
* Folgen Sie @MSPowerBI auf Twitter
* Werden Sie Teil der [Power BI-Community](http://community.powerbi.com/), um sich mit den Mitgliedern auszutauschen
* [Was ist Power BI?](../../power-bi-overview.md)

