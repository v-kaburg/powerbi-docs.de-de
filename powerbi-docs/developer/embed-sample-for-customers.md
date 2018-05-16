---
title: Einbetten von Power BI-Inhalten in eine Anwendung für Ihre Kunden
description: Hier erfahren Sie, wie Sie mit den Power BI-APIs ein Dashboard, eine Kachel oder einen Bericht für Ihre Kunden in eine Web-App integrieren bzw. einbetten.
services: powerbi
documentationcenter: ''
author: markingmyname
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: get-started-article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 01/11/2018
ms.author: maghan
ms.openlocfilehash: 779ae9a6df285b58c83021f87ed593af9ec0b3fb
ms.sourcegitcommit: 3f2f254f6e8d18137bae879ddea0784e56b66895
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="embed-a-power-bi-dashboard-tile-or-report-into-your-application"></a>Einbetten eines Dashboards, einer Kachel oder eines Berichts von Power BI in die Anwendung
Hier erfahren Sie, wie Sie mithilfe des Power BI-.NET-SDK und der Power BI-JavaScript-API ein Dashboard, eine Kachel oder einen Bericht in eine Web-App integrieren oder einbetten, wenn das Einbetten für Ihre Kunden erfolgt. Dies ist in der Regel das Szenario für ISVs.

![Eingebettetes Dashboard](media/embed-sample-for-customers/powerbi-embed-dashboard.png)

Für diese exemplarische Vorgehensweise benötigen Sie ein **Power BI Pro**-Konto. Wenn Sie kein Konto haben, können Sie sich [für ein kostenloses Power BI-Konto registrieren](../service-self-service-signup-for-power-bi.md) und anschließend für eine [Power BI Pro – Testversion](../service-self-service-signup-for-power-bi.md#in-service-power-bi-pro-60-day-trial) registrieren, oder Sie können einen eigenen [Azure Active Directory-Mandanten](create-an-azure-active-directory-tenant.md) für Testzwecke erstellen.

> [!NOTE]
> Möchten Sie stattdessen ein Dashboard für Ihre Organisation einbetten? Siehe [Integrieren eines Dashboards in eine App für Ihre Organisation](integrate-dashboard.md).
> 
> 

Zum Integrieren eines Dashboards in eine Web-App verwenden Sie die **Power BI**-API und ein **Zugriffstoken** für die Azure Active Directory (Azure AD)-Autorisierung, um ein Dashboard abzurufen. Anschließend laden Sie das Dashboard mit einem Einbettungstoken. Die **Power BI**-API bietet programmgesteuerten Zugriff auf bestimmte **Power BI**-Ressourcen. Weitere Informationen finden Sie unter [Übersicht über Power BI-REST-API](https://msdn.microsoft.com/library/dn877544.aspx), [Power BI-.NET-SDK](https://github.com/Microsoft/PowerBI-CSharp) und [Power BI-JavaScript-API](https://github.com/Microsoft/PowerBI-JavaScript).

## <a name="download-the-sample"></a>Beispiel herunterladen
Diesem Artikel liegt der im [Beispiel zum Einbetten für Ihre Organisation](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/App%20Owns%20Data) auf GitHub verwendete Code zugrunde. Laden Sie das Beispiel herunter, um die exemplarische Vorgehensweise nachvollziehen zu können.

## <a name="step-1---register-an-app-in-azure-ad"></a>Schritt 1 – Registrieren einer App in Azure AD
Sie müssen Ihre Anwendung bei Azure AD registrieren, um REST-API-Aufrufe ausführen zu können. Weitere Informationen finden Sie unter [Registrieren einer Azure AD-App zum Einbetten von Power BI-Inhalten](register-app.md).

Wenn Sie das [Beispiel zum Einbetten für Ihre Organisation](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/App%20Owns%20Data) heruntergeladen haben, verwenden Sie die **Client-ID**, die Sie nach der Registrierung erhalten haben, damit das Beispiel in Azure AD authentifiziert werden kann. Ändern Sie zum Konfigurieren des Beispiels die **clientId** in der Datei *web.config*.

## <a name="step-2---get-an-access-token-from-azure-ad"></a>Schritt 2: Abrufen eines Zugriffstokens aus Azure AD
In der Anwendung müssen Sie zunächst ein **Zugriffstoken** aus Azure AD abrufen, ehe Sie die Power BI-REST-API aufrufen können. Weitere Informationen finden Sie unter [Authentifizieren von Benutzern und Abrufen eines Azure AD-Zugriffstokens für die Power BI-App](get-azuread-access-token.md).

Beispiele hierfür finden Sie in den Aufgaben für die einzelnen Inhaltselemente in **Controllers\HomeController.cs**.

## <a name="step-3---get-a-content-item"></a>Schritt 3: Abrufen eines Inhaltselements
Zum Einbetten von Power BI-Inhalten müssen Sie einige Schritte ausführen, um sicherzustellen, dass der Vorgang ordnungsgemäß ausgeführt wird. Alle diese Schritte können zwar direkt mit der REST-API ausgeführt werden. Die Beispielanwendung und die hier angeführten Beispiele stützen sich jedoch auf das .NET SDK.

### <a name="create-the-power-bi-client-with-your-access-token"></a>Erstellen des Power BI-Clients mit dem Zugriffstoken
Mit dem Zugriffstoken erstellen Sie das Power BI-Clientobjekt, über den Sie mit den Power BI-APIs interagieren können. Dies erfolgt durch Einschließen des AccessToken mit einem *Microsoft.Rest.TokenCredentials*-Objekt.

```
using Microsoft.IdentityModel.Clients.ActiveDirectory;
using Microsoft.Rest;
using Microsoft.PowerBI.Api.V2;

var tokenCredentials = new TokenCredentials(authenticationResult.AccessToken, "Bearer");

// Create a Power BI Client object. It will be used to call Power BI APIs.
using (var client = new PowerBIClient(new Uri(ApiUrl), tokenCredentials))
{
    // Your code to embed items.
}
```

### <a name="get-the-content-item-you-want-to-embed"></a>Abrufen des einzubettenden Inhaltselements
Rufen Sie mit dem Power BI-Clientobjekt einen Verweis auf das Element ab, das eingebettet werden soll. Sie können Dashboards, Kacheln und Berichte einbetten. Im folgenden Beispiel wird veranschaulicht, wie Sie das erste Dashboard, die erste Kachel oder den ersten Bericht aus einem bestimmten Arbeitsbereich abrufen.

Ein Beispiel hierfür finden Sie in **Controllers\HomeController.cs** im [Beispiel zu Daten im App-Besitz](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/App%20Owns%20Data).

**Dashboards**

```
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

// You will need to provide the GroupID where the dashboard resides.
ODataResponseListDashboard dashboards = client.Dashboards.GetDashboardsInGroup(GroupId);

// Get the first report in the group.
Dashboard dashboard = dashboards.Value.FirstOrDefault();
```

**Kachel**

```
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

// To retrieve the tile, you first need to retrieve the dashboard.

// You will need to provide the GroupID where the dashboard resides.
ODataResponseListDashboard dashboards = client.Dashboards.GetDashboardsInGroup(GroupId);

// Get the first report in the group.
Dashboard dashboard = dashboards.Value.FirstOrDefault();

// Get a list of tiles from a specific dashboard
ODataResponseListTile tiles = client.Dashboards.GetTilesInGroup(GroupId, dashboard.Id);

// Get the first tile in the group.
Tile tile = tiles.Value.FirstOrDefault();
```

**Bericht**

```
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

// You will need to provide the GroupID where the dashboard resides.
ODataResponseListReport reports = client.Reports.GetReportsInGroupAsync(GroupId);

// Get the first report in the group.
Report report = reports.Value.FirstOrDefault();
```

### <a name="create-the-embed-token"></a>Erstellen des Einbettungstokens
Es muss ein Einbettungstoken generiert werden, das aus der JavaScript-API verwendet werden kann. Das Einbettungstoken ist spezifisch für das eingebettete Element. Das heißt, dass Sie bei jedem Einbetten eines Power BI-Inhaltselements dafür ein neues Einbettungstoken erstellen müssen. Weitere Informationen hierzu, u.a. zum erforderlichen **accessLevel**, finden Sie unter [GenerateToken-API](https://msdn.microsoft.com/library/mt784614.aspx).

> [!IMPORTANT]
> Da Einbettungstokens nur für das Testen von Bereitstellungen vorgesehen sind, ist die Anzahl von Einbettungstokens limitiert, die ein Power BI-Hauptkonto generieren kann. Es muss eine [Kapazität erworben werden](https://docs.microsoft.com/power-bi/developer/embedded-faq#technical), um Einbettungsszenarios für die Produktion verwenden zu können. Wenn eine Kapazität erworben wird, gibt es keine Einschränkungen bei der Generierung von Einbettungstokens. Informieren Sie sich unter [Verfügbare Features abrufen](https://msdn.microsoft.com/en-us/library/mt846473.aspx) darüber, wie viele kostenlose Einbettungstoken verwendet wurden.

Ein Beispiel hierfür finden Sie in **Controllers\HomeController.cs** im [Beispiel zum Einbetten für Ihre Organisation](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/App%20Owns%20Data).

Dabei wird angenommen, dass eine Klasse für **EmbedConfig** und **TileEmbedConfig** erstellt wird. Ein Beispiel hierfür ist in **Models\EmbedConfig.cs** und **Models\TileEmbedConfig.cs** verfügbar.

**Dashboard**

```
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

// Generate Embed Token.
var generateTokenRequestParameters = new GenerateTokenRequest(accessLevel: "view");
EmbedToken tokenResponse = client.Dashboards.GenerateTokenInGroup(GroupId, dashboard.Id, generateTokenRequestParameters);

// Generate Embed Configuration.
var embedConfig = new EmbedConfig()
{
    EmbedToken = tokenResponse,
    EmbedUrl = dashboard.EmbedUrl,
    Id = dashboard.Id
};
```

**Kachel**

```
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

// Generate Embed Token for a tile.
var generateTokenRequestParameters = new GenerateTokenRequest(accessLevel: "view");
EmbedToken tokenResponse = client.Tiles.GenerateTokenInGroup(GroupId, dashboard.Id, tile.Id, generateTokenRequestParameters);

// Generate Embed Configuration.
var embedConfig = new TileEmbedConfig()
{
    EmbedToken = tokenResponse,
    EmbedUrl = tile.EmbedUrl,
    Id = tile.Id,
    dashboardId = dashboard.Id
};
```

**Bericht**

```
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

// Generate Embed Token.
var generateTokenRequestParameters = new GenerateTokenRequest(accessLevel: "view");
EmbedToken tokenResponse = client.Reports.GenerateTokenInGroup(GroupId, report.Id, generateTokenRequestParameters);

// Generate Embed Configuration.
var embedConfig = new EmbedConfig()
{
    EmbedToken = tokenResponse,
    EmbedUrl = report.EmbedUrl,
    Id = report.Id
};
```



## <a name="step-4---load-an-item-using-javascript"></a>Schritt 4: Laden eines Elements mit JavaScript
Sie können mithilfe von JavaScript ein Dashboard in ein div-Element auf Ihrer Webseite laden. Im Beispiel wird ein Modell „EmbedConfig/TileEmbedConfig“ mit Ansichten für ein Dashboard, eine Kachel oder einen Bericht verwendet. Ein komplettes Beispiel für die Verwendung der JavaScript-API ist im [Beispiel zu Microsoft Power BI Embedded](https://microsoft.github.io/PowerBI-JavaScript/demo) verfügbar.

Ein Anwendungsbeispiel hierfür ist im [Beispiel zum Einbetten für Ihre Organisation](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/App%20Owns%20Data) verfügbar.

**Views\Home\EmbedDashboard.cshtml**

```
<script src="~/scripts/powerbi.js"></script>
<div id="dashboardContainer"></div>
<script>
    // Read embed application token from Model
    var accessToken = "@Model.EmbedToken.Token";

    // Read embed URL from Model
    var embedUrl = "@Html.Raw(Model.EmbedUrl)";

    // Read dashboard Id from Model
    var embedDashboardId = "@Model.Id";

    // Get models. models contains enums that can be used.
    var models = window['powerbi-client'].models;

    // Embed configuration used to describe the what and how to embed.
    // This object is used when calling powerbi.embed.
    // This also includes settings and options such as filters.
    // You can find more information at https://github.com/Microsoft/PowerBI-JavaScript/wiki/Embed-Configuration-Details.
    var config = {
        type: 'dashboard',
        tokenType: models.TokenType.Embed,
        accessToken: accessToken,
        embedUrl: embedUrl,
        id: embedDashboardId
    };

    // Get a reference to the embedded dashboard HTML element
    var dashboardContainer = $('#dashboardContainer')[0];

    // Embed the dashboard and display it within the div container.
    var dashboard = powerbi.embed(dashboardContainer, config);
</script>
```

**Views\Home\EmbedTile.cshtml**

```
<script src="~/scripts/powerbi.js"></script>
<div id="tileContainer"></div>
<script>
    // Read embed application token from Model
    var accessToken = "@Model.EmbedToken.Token";

    // Read embed URL from Model
    var embedUrl = "@Html.Raw(Model.EmbedUrl)";

    // Read tile Id from Model
    var embedTileId = "@Model.Id";

    // Read dashboard Id from Model
    var embedDashboardeId = "@Model.dashboardId";

    // Get models. models contains enums that can be used.
    var models = window['powerbi-client'].models;

    // Embed configuration used to describe the what and how to embed.
    // This object is used when calling powerbi.embed.
    // This also includes settings and options such as filters.
    // You can find more information at https://github.com/Microsoft/PowerBI-JavaScript/wiki/Embed-Configuration-Details.
    var config = {
        type: 'tile',
        tokenType: models.TokenType.Embed,
        accessToken: accessToken,
        embedUrl: embedUrl,
        id: embedTileId,
        dashboardId: embedDashboardeId
    };

    // Get a reference to the embedded tile HTML element
    var tileContainer = $('#tileContainer')[0];

    // Embed the tile and display it within the div container.
    var tile = powerbi.embed(tileContainer, config);
</script>
```

**Views\Home\EmbedReport.cshtml**

```
<script src="~/scripts/powerbi.js"></script>
<div id="reportContainer"></div>
<script>
    // Read embed application token from Model
    var accessToken = "@Model.EmbedToken.Token";

    // Read embed URL from Model
    var embedUrl = "@Html.Raw(Model.EmbedUrl)";

    // Read report Id from Model
    var embedReportId = "@Model.Id";

    // Get models. models contains enums that can be used.
    var models = window['powerbi-client'].models;

    // Embed configuration used to describe the what and how to embed.
    // This object is used when calling powerbi.embed.
    // This also includes settings and options such as filters.
    // You can find more information at https://github.com/Microsoft/PowerBI-JavaScript/wiki/Embed-Configuration-Details.
    var config = {
        type: 'report',
        tokenType: models.TokenType.Embed,
        accessToken: accessToken,
        embedUrl: embedUrl,
        id: embedReportId,
        permissions: models.Permissions.All,
        settings: {
            filterPaneEnabled: true,
            navContentPaneEnabled: true
        }
    };

    // Get a reference to the embedded report HTML element
    var reportContainer = $('#reportContainer')[0];

    // Embed the report and display it within the div container.
    var report = powerbi.embed(reportContainer, config);
</script>
```

## <a name="next-steps"></a>Nächste Schritte
Eine Beispielanwendung können Sie auf GitHub einsehen. Die obigen Beispiele basieren auf diesem Beispiel. Weitere Informationen finden Sie im [Beispiel zum Einbetten für Ihre Organisation](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/App%20Owns%20Data).

Weitere Informationen sind für die JavaScript-API verfügbar; siehe [Power BI-JavaScript-API](https://github.com/Microsoft/PowerBI-JavaScript).

Weitere Fragen? [Stellen Sie Ihre Frage in der Power BI-Community.](http://community.powerbi.com/)

