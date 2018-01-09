---
title: "Integrieren einer Power BI-Kachel in eine App für Ihre Organisation"
description: Exemplarische Vorgehensweise zum Integrieren einer Kachel in eine App, Beispielcode
services: powerbi
documentationcenter: 
author: guyinacube
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: get-started-article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 12/19/2017
ms.author: asaxton
ms.openlocfilehash: 0b2e0208814fdd68ef7c6f0bcc1cf6ffa1fe42da
ms.sourcegitcommit: a658b1c936e382f46a19eeb9cc26016cd7b1d756
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/20/2017
---
# <a name="integrate-a-tile-into-an-app-user-owns-data"></a>Integrieren einer Kachel in eine App (Benutzer ist Besitzer der Daten)
Hier erfahren Sie, wie Sie mithilfe von REST-API-Aufrufen zusammen mit der Power BI-JavaScript-API eine Kachel in eine Web-App integrieren bzw. einbetten, wenn das Einbetten für Ihre Organisation erfolgt.

![Eingebettete Kachel in Webanwendung](media/integrate-tile/powerbi-embedded-tile.png)

Für diese exemplarische Vorgehensweise benötigen Sie ein **Power BI**-Konto. Wenn Sie kein Konto haben, können Sie [sich für ein kostenloses Power BI-Konto registrieren](../service-self-service-signup-for-power-bi.md), oder Sie können Ihren eigenen [Azure Active Directory-Mandanten](create-an-azure-active-directory-tenant.md) für Testzwecke erstellen.

> [!NOTE]
> Möchten Sie stattdessen mit einem Einbettungstoken eine Kachel für Ihre Kunden einbetten? Weitere Informationen hierzu finden Sie unter [Integrieren eines Dashboards, einer Kachel oder eines Berichts in die Anwendung (die App ist Besitzer der Daten)](embed-sample-for-customers.md).
> 
> 

Zum Integrieren einer Kachel in eine Web-App verwenden Sie die **Power BI**-REST-API oder das Power BI-C#-SDK sowie ein **Zugriffstoken** für die AD-Autorisierung (Azure Active Directory), um eine Kachel abzurufen. Dann laden Sie die Kachel mithilfe desselben Zugriffstokens. Die **Power BI**-API bietet programmgesteuerten Zugriff auf bestimmte **Power BI**-Ressourcen. Weitere Informationen finden Sie unter [Übersicht über Power BI-REST-API](https://msdn.microsoft.com/library/dn877544.aspx) und [Power BI-JavaScript-API](https://github.com/Microsoft/PowerBI-JavaScript).

## <a name="download-the-sample"></a>Beispiel herunterladen
Diesem Artikel liegt der im [Beispiel zum Integrieren einer Kachel in eine Web-App – integrate-tile-web-app](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-tile-web-app) auf GitHub verwendete Code zugrunde. Laden Sie das Beispiel herunter, um die exemplarische Vorgehensweise nachvollziehen zu können.

## <a name="step-1---register-an-app-in-azure-ad"></a>Schritt 1 – Registrieren einer App in Azure AD
Sie müssen Ihre Anwendung bei Azure AD registrieren, um REST-API-Aufrufe ausführen zu können. Weitere Informationen finden Sie unter [Registrieren einer Azure AD-App zum Einbetten von Power BI-Inhalten](register-app.md).

Wenn Sie das [Beispiel zum Integrieren einer Kachel in eine Web-App – integrate-tile-web-app](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-tile-web-app) heruntergeladen haben, verwenden Sie die **Client-ID** und den **geheimen Clientschlüssel**, die Sie nach der Registrierung erhalten haben, damit das Beispiel in Azure AD authentifiziert werden kann. Ändern Sie zum Konfigurieren des Beispiels die **Client-ID** und das **Clientgeheimnis** in der Datei *cloud.config*.

![](media/integrate-tile/powerbi-embed-dashboard-register-app4.png)

## <a name="step-2---get-an-access-token-from-azure-ad"></a>Schritt 2: Abrufen eines Zugriffstokens aus Azure AD
In der Anwendung müssen Sie zunächst ein **Zugriffstoken** aus Azure AD abrufen, ehe Sie die Power BI-REST-API aufrufen können. Weitere Informationen finden Sie unter [Authentifizieren von Benutzern und Abrufen eines Azure AD-Zugriffstokens für die Power BI-App](get-azuread-access-token.md).

## <a name="step-3---get-a-tile"></a>Schritt 3: Abrufen einer Kachel
Zum Abrufen einer **Power BI**-Kachel verwenden Sie den Vorgang [Get Tiles](https://msdn.microsoft.com/library/mt465741.aspx) (Kacheln abrufen), um eine Liste der **Power BI**-Kacheln für ein bestimmtes Dashboard abzurufen. Der Liste der Kacheln können Sie eine Kachel-ID und eine Einbettungs-URL entnehmen.

Zunächst muss eine Dashboard-ID abgerufen werden, ehe Sie die Kachel abrufen können. Weitere Informationen zum Abrufen eines Dashboards finden Sie unter [Integrieren eines Dashboards in eine App (Benutzer ist Besitzer der Daten)](integrate-dashboard.md).

### <a name="get-tiles-using-an-access-token"></a>Abrufen von Kacheln mithilfe eines Zugriffstokens
Mit dem **Zugriffstoken**, das Sie in [Schritt 2](#step-2-get-an-access-token-from-azure-ad) abgerufen haben, können Sie den Vorgang [Get Tiles](https://msdn.microsoft.com/library/mt465741.aspx) (Kacheln abrufen) aufrufen. Der Vorgang [Get Tiles](https://msdn.microsoft.com/library/mt465741.aspx) (Kacheln abrufen) gibt eine Liste der Kacheln zurück. Sie können eine einzelne Kachel aus der Liste der Kacheln abrufen. Im Folgenden finden Sie eine vollständige C#-Methode zum Abrufen einer Kachel. Beispiele zum Verwenden der Power BI-REST-API finden Sie unter [Power BI-REST-API in APIARY](http://docs.powerbi.apiary.io/).

Zum Ausführen des REST-API-Aufrufs müssen Sie einen *Autorisierungsheader* im Format *Träger {Zugriffstoken}* einschließen.

#### <a name="get-tiles-with-the-rest-api"></a>Abrufen von Kacheln mit der REST-API
**Default.aspx.cs**

```
using Newtonsoft.Json;

//Get a tile from a dashboard. In this sample, you get the first tile.
protected void GetTile(string dashboardId, int index)
{
    //Configure tiles request
    System.Net.WebRequest request = System.Net.WebRequest.Create(
        String.Format("{0}Dashboards/{1}/Tiles",
        baseUri,
        dashboardId)) as System.Net.HttpWebRequest;

    request.Method = "GET";
    request.ContentLength = 0;
    request.Headers.Add("Authorization", String.Format("Bearer {0}", accessToken.Value));

    //Get tiles response from request.GetResponse()
    using (var response = request.GetResponse() as System.Net.HttpWebResponse)
    {
        //Get reader from response stream
        using (var reader = new System.IO.StreamReader(response.GetResponseStream()))
        {
            //Deserialize JSON string
            PBITiles tiles = JsonConvert.DeserializeObject<PBITiles>(reader.ReadToEnd());

            //Sample assumes at least one Dashboard with one Tile.
            //You could write an app that lists all tiles in a dashboard
            if (tiles.value.Length > 0)
                tileEmbedUrl.Text = tiles.value[index].embedUrl;
        }
    }
}

//Power BI Tiles used to deserialize the Get Tiles response.
public class PBITiles
{
    public PBITile[] value { get; set; }
}
public class PBITile
{
    public string id { get; set; }
    public string title { get; set; }
    public string embedUrl { get; set; }
}
```

#### <a name="get-tiles-using-the-net-sdk"></a>Abrufen von Kacheln mit dem .NET-SDK
Mithilfe des .NET-SDK können Sie eine Liste der Dashboards abrufen und müssen die REST-API nicht direkt aufrufen.

```
using Microsoft.IdentityModel.Clients.ActiveDirectory;
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

var tokenCredentials = new TokenCredentials(<ACCESS TOKEN>, "Bearer");

// Create a Power BI Client object. It will be used to call Power BI APIs.
using (var client = new PowerBIClient(new Uri(ApiUrl), tokenCredentials))
{
    // Get a list of dashboards your "My Workspace"
    ODataResponseListDashboard tiles = client.Dashboards.GetDashboards();

    // Get a list of dashboards from a group (app workspace)
    ODataResponseListDashboard dashboards = client.Dashboards.GetDashboardsInGroup(groupId);

    Dashboard dashboard = dashboards.Value.FirstOrDefault();

    // Get the first tile from the above dashbaord
    ODataResponseListTile tiles = client.Dashboards.GetTiles(dashboard.Id);

    Tile tile = tiles.Value.FirstOrDefault();
}
```

## <a name="step-4---load-a-tile-using-javascript"></a>Schritt 4: Laden einer Kachel mit JavaScript
Sie können mithilfe von JavaScript eine Kachel in ein div-Element auf Ihrer Webseite laden.

**Default.aspx**

```
<!-- Embed Tile-->
<div> 
    <asp:Panel ID="PanelEmbed" runat="server" Visible="true">
        <div>
            <div><b class="step">Step 3</b>: Embed a tile</div>

            <div>Enter an embed url for a tile from Step 2 (starts with https://):</div>
            <input type="text" id="tb_EmbedURL" style="width: 1024px;" />
            <br />
            <input type="button" id="bEmbedTileAction" value="Embed Tile" />
        </div>

        <div id="tileContainer"></div>
    </asp:Panel>
</div>
```

**Site.master**

```
window.onload = function () {
    // client side click to embed a selected tile.
    var el = document.getElementById("bEmbedTileAction");
    if (el.addEventListener) {
        el.addEventListener("click", updateEmbedTile, false);
    } else {
        el.attachEvent('onclick', updateEmbedTile);
    }

    // handle server side post backs, optimize for reload scenarios
    // show embedded tile if all fields were filled in.
    var accessTokenElement = document.getElementById('MainContent_accessTokenTextbox');
    if (accessTokenElement !== null) {
        var accessToken = accessTokenElement.value;
        if (accessToken !== "")
            updateEmbedTile();
    }
};

// update embed tile
function updateEmbedTile() {

    // check if the embed url was selected
    var embedUrl = document.getElementById('tb_EmbedURL').value;
    if (embedUrl === "")
        return;

    // get the access token.
    accessToken = document.getElementById('MainContent_accessTokenTextbox').value;

    // Embed configuration used to describe the what and how to embed.
    // This object is used when calling powerbi.embed.
    // You can find more information at https://github.com/Microsoft/PowerBI-JavaScript/wiki/Embed-Configuration-Details.
    var config = {
        type: 'tile',
        accessToken: accessToken,
        embedUrl: embedUrl
    };

    // Grab the reference to the div HTML element that will host the tile.
    var tileContainer = document.getElementById('tileContainer');

    // Embed the tile and display it within the div container.
    var tile = powerbi.embed(tileContainer, config);

    // tile.on will add an event handler which prints to Log window.
    tile.on("error", function (event) {
        var logView = document.getElementById('logView');
        logView.innerHTML = logView.innerHTML + "Error<br/>";
        logView.innerHTML = logView.innerHTML + JSON.stringify(event.detail, null, "  ") + "<br/>";
        logView.innerHTML = logView.innerHTML + "---------<br/>";
    });
}
```

Wenn Sie das [Beispiel zum Integrieren einer Kachel in eine Web-App – integrate-tile-web-app](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-tile-web-app) heruntergeladen und ausgeführt haben, sieht das Beispiel ähnlich wie das folgende aus.

![Eingebettete Kachel in Webanwendung](media/integrate-tile/powerbi-embedded-tile.png)

## <a name="working-with-groups-app-workspaces"></a>Arbeiten mit Gruppen (App-Arbeitsbereiche)
Zum Einbetten einer Kachel aus einer Gruppe (App-Arbeitsbereich) müssen Sie die Liste aller verfügbaren Kacheln im Dashboard einer Gruppe mit dem folgenden REST-API-Aufruf abrufen. Weitere Informationen zu diesem REST-API-Aufruf finden Sie unter [Get Tiles](https://msdn.microsoft.com/library/mt465741.aspx) (Kacheln abrufen). Sie benötigen Berechtigungen in der Gruppe, damit die Anforderung Ergebnisse zurückgibt.

```
https://api.powerbi.com/v1.0/myorg/groups/{groupId}/dashboards/{dashboard_id}/tiles
```

Die oben genannte API gibt die Liste der verfügbaren Kacheln zurück. Jede Kachel verfügt über eine EmbedUrl-Eigenschaft, die bereits so konstruiert ist, dass das Einbetten aus Gruppen unterstützt wird.

```
https://app.powerbi.com/embed?dashboardId={dashboard_id}&tileId={tile_id}&groupId={group_id}
```

## <a name="next-steps"></a>Nächste Schritte
[Tile Embed](https://github.com/Microsoft/PowerBI-JavaScript/wiki/Tile-Embed) im Wiki zu PowerBI-JavaScript

[Power BI-JavaScript-API](https://github.com/Microsoft/PowerBI-JavaScript)

Beispiel zu [integrate-tile-web-app](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-tile-web-app) in GitHub.

Weitere Fragen? [Stellen Sie Ihre Frage in der Power BI-Community.](http://community.powerbi.com/)

