---
title: Integrieren eines Dashboards in eine App für Ihre Organisation
description: Hier erfahren Sie, wie Sie mit den Power BI-APIs ein Dashboard in eine Web-App integrieren bzw. einbetten.
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-developer
ms.topic: conceptual
ms.date: 02/13/2018
ms.author: maghan
ms.openlocfilehash: 979b76350b9867bbc684a70bd89a82f88993e625
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2018
ms.locfileid: "34290267"
---
# <a name="integrate-a-dashboard-into-an-app-for-your-organization"></a>Integrieren eines Dashboards in eine App für Ihre Organisation
Hier erfahren Sie, wie Sie mithilfe von REST-API-Aufrufen zusammen mit der Power BI-JavaScript-API ein Dashboard in eine Web-App integrieren bzw. einbetten, wenn das Einbetten für Ihre Organisation erfolgt.

![Eingebettetes Dashboard](media/integrate-dashboard/powerbi-embed-dashboard.png)

Für diese exemplarische Vorgehensweise benötigen Sie ein **Power BI**-Konto. Wenn Sie kein Konto haben, können Sie [sich für ein kostenloses Power BI-Konto registrieren](../service-self-service-signup-for-power-bi.md), oder Sie können Ihren eigenen [Azure Active Directory-Mandanten](create-an-azure-active-directory-tenant.md) für Testzwecke erstellen.

> [!NOTE]
> Möchten Sie stattdessen mit einem Einbettungstoken ein Dashboard für Ihre Kunden einbetten? Weitere Informationen hierzu finden Sie unter [Integrieren eines Dashboards, einer Kachel oder eines Berichts in die Anwendung (die App ist Besitzer der Daten)](embed-sample-for-customers.md).
> 
> 

Zum Integrieren eines Dashboards in eine Web-App verwenden Sie die **Power BI**-REST-API oder das Power BI-C#-SDK sowie ein **Zugriffstoken** für die AD-Autorisierung (Azure Active Directory), um ein Dashboard abzurufen. Dann laden Sie das Dashboard mithilfe desselben Zugriffstokens. Die **Power BI**-API bietet programmgesteuerten Zugriff auf bestimmte **Power BI**-Ressourcen. Weitere Informationen finden Sie unter [Übersicht über Power BI-REST-API](https://msdn.microsoft.com/library/dn877544.aspx) und [Power BI-JavaScript-API](https://github.com/Microsoft/PowerBI-JavaScript).

## <a name="download-the-sample"></a>Beispiel herunterladen
Diesem Artikel liegt der im [Beispiel zum Integrieren eines Dashboards in eine Web-App – integrate-dashboard-web-app](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-dashboard-web-app) auf GitHub verwendete Code zugrunde. Laden Sie das Beispiel herunter, um die exemplarische Vorgehensweise nachvollziehen zu können.

## <a name="step-1---register-an-app-in-azure-ad"></a>Schritt 1 – Registrieren einer App in Azure AD
Sie müssen Ihre Anwendung bei Azure AD registrieren, um REST-API-Aufrufe ausführen zu können. Weitere Informationen finden Sie unter [Registrieren einer Azure AD-App zum Einbetten von Power BI-Inhalten](register-app.md).

Wenn Sie das [Beispiel zum Integrieren eines Dashboards](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-dashboard-web-app) heruntergeladen haben, verwenden Sie die **Client-ID** und das **Clientgeheimnis**, das Sie nach der Registrierung erhalten haben, damit das Beispiel in Azure AD authentifiziert werden kann. Ändern Sie zum Konfigurieren des Beispiels die **Client-ID** und das **Clientgeheimnis** in der Datei *cloud.config*.

![](media/integrate-dashboard/powerbi-embed-dashboard-register-app4.png)

## <a name="step-2---get-an-access-token-from-azure-ad"></a>Schritt 2: Abrufen eines Zugriffstokens aus Azure AD
In der Anwendung müssen Sie zunächst ein **Zugriffstoken** aus Azure AD abrufen, ehe Sie die Power BI-REST-API aufrufen können. Weitere Informationen finden Sie unter [Authentifizieren von Benutzern und Abrufen eines Azure AD-Zugriffstokens für die Power BI-App](get-azuread-access-token.md).

## <a name="step-3---get-a-dashboard"></a>Schritt 3: Abrufen eines Dashboards
Zum Abrufen eines **Power BI**-Dashboards verwenden Sie den Vorgang [Get Dashboards](https://msdn.microsoft.com/library/mt465739.aspx) (Dashboards abrufen), um eine Liste der **Power BI**-Dashboards abzurufen. Aus dieser Dashboardliste können Sie dann eine Dashboard-ID abrufen.

![](media/integrate-dashboard/powerbi-embed-dashboard-get-dashboards.png)

### <a name="get-dashboards-using-an-access-token"></a>Abrufen von Dashboards mit einem Zugriffstoken
Mit dem **Zugriffstoken**, das Sie in [Schritt 2](#step-2-get-an-access-token-from-azure-ad) abgerufen haben, können Sie den Vorgang [Get Dashboards](https://msdn.microsoft.com/library/mt465739.aspx) (Dashboards abrufen) aufrufen. Der Vorgang [Get Dashboards](https://msdn.microsoft.com/library/mt465739.aspx) (Dashboards abrufen) gibt eine Liste von Dashboards zurück. Sie können aus dieser Liste von Dashboards dann ein einzelnes Dashboard abrufen. Im Folgenden finden Sie eine vollständige C#-Methode zum Abrufen eines Dashboards. 

Zum Ausführen des REST-API-Aufrufs müssen Sie einen *Autorisierungsheader* im Format *Träger {Zugriffstoken}* einschließen.

#### <a name="get-dashboards-with-the-rest-api"></a>Abrufen von Dashboards mit der REST-API
**Default.aspx.cs**

```
protected void getDashboardsButton_Click(object sender, EventArgs e)
{
    string responseContent = string.Empty;

    //Configure dashboards request
    System.Net.WebRequest request = System.Net.WebRequest.Create(String.Format("{0}dashboards", baseUri)) as System.Net.HttpWebRequest;
    request.Method = "GET";
    request.ContentLength = 0;
    request.Headers.Add("Authorization", String.Format("Bearer {0}", authResult.AccessToken));

    //Get dashboards response from request.GetResponse()
    using (var response = request.GetResponse() as System.Net.HttpWebResponse)
    {
        //Get reader from response stream
        using (var reader = new System.IO.StreamReader(response.GetResponseStream()))
        {
            responseContent = reader.ReadToEnd();

            //Deserialize JSON string
            PBIDashboards PBIDashboards = JsonConvert.DeserializeObject<PBIDashboards>(responseContent);

            if (PBIDashboards != null)
            {
                var gridViewDashboards = PBIDashboards.value.Select(dashboard => new {
                    Id = dashboard.id,
                    DisplayName = dashboard.displayName,
                    EmbedUrl = dashboard.embedUrl
                });

                this.GridView1.DataSource = gridViewDashboards;
                this.GridView1.DataBind();
            }
        }
    }
}

//Power BI Dashboards used to deserialize the Get Dashboards response.
public class PBIDashboards
{
    public PBIDashboard[] value { get; set; }
}
public class PBIDashboard
{
    public string id { get; set; }
    public string displayName { get; set; }
    public string embedUrl { get; set; }
    public bool isReadOnly { get; set; }
}
```

#### <a name="get-dashboards-using-the-net-sdk"></a>Abrufen von Dashboards mit dem .NET-SDK
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
    ODataResponseListDashboard dashboards = client.Dashboards.GetDashboards();

    // Get a list of dashboards from a group (app workspace)
    ODataResponseListDashboard dashboards = client.Dashboards.GetDashboardsInGroup(groupId);

    Dashboard dashboard = dashboards.Value.FirstOrDefault();

    var embedUrl = dashboard.EmbedUrl
}
```

## <a name="step-4---load-a-dashboard-using-javascript"></a>Schritt 4: Laden eines Dashboards mit JavaScript
Sie können mithilfe von JavaScript ein Dashboard in ein div-Element auf Ihrer Webseite laden.

**Default.aspx**

```
<!-- Embed Dashboard-->
<div> 
    <asp:Panel ID="PanelEmbed" runat="server" Visible="true">
        <div>
            <div><b class="step">Step 3</b>: Embed a dashboard</div>

            <div>Enter an embed url for a dashboard from Step 2 (starts with https://):</div>
            <input type="text" id="tb_EmbedURL" style="width: 1024px;" />
            <br />
            <input type="button" id="bEmbedDashboardAction" value="Embed Dashboard" />
        </div>

        <div id="dashboardContainer"></div>
    </asp:Panel>
</div>
```

**Site.master**

```
window.onload = function () {
    // client side click to embed a selected dashboard.
    var el = document.getElementById("bEmbedDashboardAction");
    if (el.addEventListener) {
        el.addEventListener("click", updateEmbedDashboard, false);
    } else {
        el.attachEvent('onclick', updateEmbedDashboard);
    }

    // handle server side post backs, optimize for reload scenarios
    // show embedded dashboard if all fields were filled in.
    var accessTokenElement = document.getElementById('MainContent_accessTokenTextbox');
    if (accessTokenElement !== null) {
        var accessToken = accessTokenElement.value;
        if (accessToken !== "")
            updateEmbedDashboard();
    }
};

// update embed dashboard
function updateEmbedDashboard() {

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
        type: 'dashboard',
        accessToken: accessToken,
        embedUrl: embedUrl
    };

    // Grab the reference to the div HTML element that will host the dashboard.
    var dashboardContainer = document.getElementById('dashboardContainer');

    // Embed the dashboard and display it within the div container.
    var dashboard = powerbi.embed(dashboardContainer, config);

    // dashboard.on will add an event handler which prints to Log window.
    dashboard.on("tileClicked", function (event) {
        var logView = document.getElementById('logView');
        logView.innerHTML = logView.innerHTML + "Tile Clicked<br/>";
        logView.innerHTML = logView.innerHTML + JSON.stringify(event.detail, null, "  ") + "<br/>";
        logView.innerHTML = logView.innerHTML + "---------<br/>";
    });

    // dashboard.on will add an event handler which prints to Log window.
    dashboard.on("error", function (event) {
        var logView = document.getElementById('logView');
        logView.innerHTML = logView.innerHTML + "Error<br/>";
        logView.innerHTML = logView.innerHTML + JSON.stringify(event.detail, null, "  ") + "<br/>";
        logView.innerHTML = logView.innerHTML + "---------<br/>";
    });
}
```

Wenn Sie das [Beispiel zum Integrieren eines Dashboards](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-dashboard-web-app) heruntergeladen und ausgeführt haben, ähnelt das Beispiel dem in der folgenden Abbildung.

![](media/integrate-dashboard/powerbi-embed-dashboard.png)

## <a name="tile-clicked-events"></a>TileClicked-Ereignisse
Im Beispiel oben haben Sie möglicherweise festgestellt, dass Sie Ereignisse behandeln können, wenn auf die Kachel im Dashboard geklickt wird. Weitere Informationen zu Ereignissen finden Sie unter [Behandeln von Ereignissen in der JavaScript-API](https://github.com/Microsoft/PowerBI-JavaScript/wiki/Handling-Events).

```
// dashboard.on will add an event handler which prints to Log window.
dashboard.on("tileClicked", function (event) {
    var logView = document.getElementById('logView');
    logView.innerHTML = logView.innerHTML + "Tile Clicked<br/>";
    logView.innerHTML = logView.innerHTML + JSON.stringify(event.detail, null, "  ") + "<br/>";
    logView.innerHTML = logView.innerHTML + "---------<br/>";
});

// dashboard.on will add an event handler which prints to Log window.
dashboard.on("error", function (event) {
    var logView = document.getElementById('logView');
    logView.innerHTML = logView.innerHTML + "Error<br/>";
    logView.innerHTML = logView.innerHTML + JSON.stringify(event.detail, null, "  ") + "<br/>";
    logView.innerHTML = logView.innerHTML + "---------<br/>";
});
```

Wenn Sie das [Beispiel zum Integrieren eines Dashboards](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/PowerBI.com%20Integrate/integrate-dashboard-web-app) heruntergeladen und ausgeführt haben, wird beim Klicken auf eine Kachel Text unter dem Dashboard ausgegeben. Der Text sollte ungefähr wie folgt aussehen. Dies ermöglicht es Ihnen, das Klicken auf eine Kachel zu protokollieren und den Benutzer an die entsprechende Adresse weiterzuleiten.

```
Tile Clicked
{ "event": "TileClick", "reportEmbedUrl": "", "navigationUrl": "https://app.powerbi.com/dashboards/fcff76f9-15ff-4a8e-8242-275ac9c25b90/qna?q=count%20of%20new%20hires%20from%20July%202014%20to%20December%202014", "tileId": "0e99b45c-9b53-4920-b239-cee7d37d2369" }
---------
Tile Clicked
{ "event": "TileClick", "reportEmbedUrl": "https://app.powerbi.com/reportEmbed?reportId=ab199308-80b1-4626-9823-43a84623bd9c", "navigationUrl": "https://app.powerbi.com/reports/ab199308-80b1-4626-9823-43a84623bd9c/ReportSection1", "tileId": "ffc30447-674a-4511-944f-79e182d719de", "pageName": "ReportSection1" }
---------
```

## <a name="working-with-groups-app-workspaces"></a>Arbeiten mit Gruppen (App-Arbeitsbereiche)
Zum Einbetten eines Dashboards aus einer Gruppe (App-Arbeitsbereich) muss die Liste aller verfügbaren Dashboards in einer Gruppe durch den folgenden REST-API-Aufruf abgerufen werden. Weitere Informationen zu diesem REST-API-Aufruf finden Sie unter [Abrufen von Dashboards](https://msdn.microsoft.com/library/mt465739.aspx). Sie benötigen Berechtigungen in der Gruppe, damit die Anforderung Ergebnisse zurückgibt.

```
https://api.powerbi.com/v1.0/myorg/groups/{groupId}/dashboards
```

Die oben genannte API gibt die Liste der verfügbaren Dashboards zurück. Jedes Dashboard verfügt über eine EmbedUrl-Eigenschaft, die bereits so konstruiert ist, dass das Einbetten aus Gruppen unterstützt wird.

```
https://app.powerbi.com/dashboardEmbed?dashboardId={dashboardId}&groupId={groupId}
```

## <a name="limitations"></a>Einschränkungen
* Die Endbenutzer, die auf die eingebetteten Dashboards zugreifen, müssen über ein Power BI-Konto und Zugriff auf das Dashboard verfügen. Das heißt, entweder sind sie Besitzer des Dashboards oder das Dashboard wurde für den betreffenden Benutzer freigegeben.
* Q&A wird derzeit in eingebetteten Dashboards nicht unterstützt.
* Zudem gilt eine vorübergehende Einschränkung: Beim gemeinsamen Nutzen eines Dashboards mit Sicherheitsgruppen müssen Benutzer zunächst die Dashboards auf „PowerBI.com“ aufrufen, um das eingebettete Dashboard zu sehen.

## <a name="next-steps"></a>Nächste Schritte
Eine Beispielanwendung können Sie auf GitHub einsehen. Die obigen Beispiele basieren auf diesem Beispiel. Weitere Informationen finden Sie im [Beispiel zum Integrieren eines Dashboards in eine Web-App – integrate-dashboard-web-app](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-dashboard-web-app).

Weitere Informationen sind für die JavaScript-API verfügbar; siehe [Power BI-JavaScript-API](https://github.com/Microsoft/PowerBI-JavaScript).

Weitere Fragen? [Stellen Sie Ihre Frage in der Power BI-Community.](http://community.powerbi.com/)

