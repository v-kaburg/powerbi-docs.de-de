---
title: "Integrieren eines Power BI-Berichts in eine App für Ihre Organisation"
description: Hier erfahren Sie, wie Sie mit den Power BI-APIs einen Bericht in eine Web-App integrieren bzw. einbetten.
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
ms.date: 10/05/2017
ms.author: asaxton
ms.openlocfilehash: 4dd18fba5b5e3da0f8973a77166551086cc3f3cf
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2017
---
# <a name="integrate-a-report-into-an-app-for-your-organization"></a>Integrieren eines Berichts in eine App für Ihre Organisation
Hier erfahren Sie, wie Sie mithilfe von REST-API-Aufrufen zusammen mit der Power BI-JavaScript-API einen Bericht in eine Web-App integrieren bzw. einbetten, wenn das Einbetten für Ihre Organisation erfolgt.

![Beispiel für eingebetteten Bericht](media/integrate-report/powerbi-embedded-report.png)

Für diese exemplarische Vorgehensweise benötigen Sie ein **Power BI**-Konto. Wenn Sie kein Konto haben, können Sie [sich für ein kostenloses Power BI-Konto registrieren](../service-self-service-signup-for-power-bi.md), oder Sie können Ihren eigenen [Azure Active Directory-Mandanten](create-an-azure-active-directory-tenant.md) für Testzwecke erstellen.

> [!NOTE]
> Möchten Sie stattdessen mit einem Einbettungstoken einen Bericht für Ihre Kunden einbetten? Weitere Informationen hierzu finden Sie unter [Integrieren eines Dashboards, einer Kachel oder eines Berichts in die Anwendung (die App ist Besitzer der Daten)](embed-sample-for-customers.md).
> 
> 

Zum Integrieren eines Berichts in eine Web-App verwenden Sie die **Power BI**-REST-API oder das Power BI-C#-SDK sowie ein **Zugriffstoken** für die AD-Autorisierung (Azure Active Directory), um einen Bericht abzurufen. Dann laden Sie den Bericht mithilfe desselben Zugriffstokens. Die **Power BI**-API bietet programmgesteuerten Zugriff auf bestimmte **Power BI**-Ressourcen. Weitere Informationen finden Sie unter [Übersicht über Power BI-REST-API](https://msdn.microsoft.com/library/dn877544.aspx) und [Power BI-JavaScript-API](https://github.com/Microsoft/PowerBI-JavaScript).

## <a name="download-the-sample"></a>Beispiel herunterladen
Diesem Artikel liegt der im [Beispiel zum Integrieren eines Berichts in eine Web-App – integrate-report-web-app](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-report-web-app) auf GitHub verwendete Code zugrunde. Laden Sie das Beispiel herunter, um die exemplarische Vorgehensweise nachvollziehen zu können.

## <a name="step-1---register-an-app-in-azure-ad"></a>Schritt 1 – Registrieren einer App in Azure AD
Sie müssen Ihre Anwendung bei Azure AD registrieren, um REST-API-Aufrufe ausführen zu können. Weitere Informationen finden Sie unter [Registrieren einer Azure AD-App zum Einbetten von Power BI-Inhalten](register-app.md).

Wenn Sie das [Beispiel zum Integrieren eines Berichts in eine Web-App – integrate-report-web-app](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-report-web-app) heruntergeladen haben, verwenden Sie die **Client-ID** und den **geheimen Clientschlüssel**, die Sie nach der Registrierung erhalten haben, damit das Beispiel in Azure AD authentifiziert werden kann. Ändern Sie zum Konfigurieren des Beispiels die **Client-ID** und das **Clientgeheimnis** in der Datei *cloud.config*.

![](media/integrate-report/powerbi-embed-dashboard-register-app4.png)

## <a name="step-2---get-an-access-token-from-azure-ad"></a>Schritt 2: Abrufen eines Zugriffstokens aus Azure AD
In der Anwendung müssen Sie zunächst ein **Zugriffstoken** aus Azure AD abrufen, ehe Sie die Power BI-REST-API aufrufen können. Weitere Informationen finden Sie unter [Authentifizieren von Benutzern und Abrufen eines Azure AD-Zugriffstokens für die Power BI-App](get-azuread-access-token.md).

## <a name="step-3---get-a-report"></a>Schritt 3: Abrufen eines Berichts
Zum Abrufen eines **Power BI**-Berichts verwenden Sie den Vorgang [Get Reports](https://msdn.microsoft.com/library/mt634543.aspx) (Berichte abrufen), um eine Liste der **Power BI**-Berichte abzurufen. Aus der Liste der Berichte können Sie eine Berichts-ID abrufen.

### <a name="get-reports-using-an-access-token"></a>Abrufen von Berichten mithilfe eines Zugriffstokens
Mit dem **Zugriffstoken**, das Sie in [Schritt 2](#step-2-get-an-access-token-from-azure-ad) abgerufen haben, können Sie den Vorgang [Get Reports](https://msdn.microsoft.com/library/mt634543.aspx) (Berichte abrufen) aufrufen. Der Vorgang [Get Reports](https://msdn.microsoft.com/library/mt634543.aspx) (Berichte abrufen) gibt eine Liste der Berichte zurück. Anhand der Liste der Berichte können Sie einen einzelnen Bericht abrufen. Im Folgenden finden Sie eine vollständige C#-Methode zum Abrufen eines Berichts. Beispiele zum Verwenden der Power BI-REST-API finden Sie unter [Power BI-REST-API in APIARY](http://docs.powerbi.apiary.io/).

Zum Ausführen des REST-API-Aufrufs müssen Sie einen *Autorisierungsheader* im Format *Träger {Zugriffstoken}* einschließen.

#### <a name="get-reports-with-the-rest-api"></a>Abrufen von Berichten mit der REST-API
**Default.aspx.cs**

```
using Newtonsoft.Json;

//Get a Report. In this sample, you get the first Report.
protected void GetReport(int index)
{
    //Configure Reports request
    System.Net.WebRequest request = System.Net.WebRequest.Create(
        String.Format("{0}/Reports",
        baseUri)) as System.Net.HttpWebRequest;

    request.Method = "GET";
    request.ContentLength = 0;
    request.Headers.Add("Authorization", String.Format("Bearer {0}", accessToken.Value));

    //Get Reports response from request.GetResponse()
    using (var response = request.GetResponse() as System.Net.HttpWebResponse)
    {
        //Get reader from response stream
        using (var reader = new System.IO.StreamReader(response.GetResponseStream()))
        {
            //Deserialize JSON string
            PBIReports Reports = JsonConvert.DeserializeObject<PBIReports>(reader.ReadToEnd());

            //Sample assumes at least one Report.
            //You could write an app that lists all Reports
            if (Reports.value.Length > 0)
            {
                var report = Reports.value[index];

                txtEmbedUrl.Text = report.embedUrl;
                txtReportId.Text = report.id;
                txtReportName.Text = report.name;
            }
        }
    }
}

//Power BI Reports used to deserialize the Get Reports response.
public class PBIReports
{
    public PBIReport[] value { get; set; }
}
public class PBIReport
{
    public string id { get; set; }
    public string name { get; set; }
    public string webUrl { get; set; }
    public string embedUrl { get; set; }
}
```

#### <a name="get-reports-using-the-net-sdk"></a>Abrufen von Berichten mit dem .NET-SDK
Mithilfe des .NET-SDK können Sie eine Liste der Berichte abrufen und müssen die REST-API nicht direkt aufrufen.

```
using Microsoft.IdentityModel.Clients.ActiveDirectory;
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

var tokenCredentials = new TokenCredentials(<ACCESS TOKEN>, "Bearer");

// Create a Power BI Client object. It will be used to call Power BI APIs.
using (var client = new PowerBIClient(new Uri(ApiUrl), tokenCredentials))
{
    // Get the first report all reports in that workspace
    ODataResponseListReport reports = client.Reports.GetReports();

    Report report = reports.Value.FirstOrDefault();

    var embedUrl = report.EmbedUrl;
}
```

## <a name="step-4---load-a-report-using-javascript"></a>Schritt 4: Laden eines Berichts mit JavaScript
Sie können mithilfe von JavaScript einen Bericht in ein div-Element auf Ihrer Webseite laden.

**Default.aspx**

```
<!-- Embed Report-->
<div> 
    <asp:Panel ID="PanelEmbed" runat="server" Visible="true">
        <div>
            <div><b class="step">Step 3</b>: Embed a report</div>

            <div>Enter an embed url for a report from Step 2 (starts with https://):</div>
            <input type="text" id="tb_EmbedURL" style="width: 1024px;" />
            <br />
            <input type="button" id="bEmbedReportAction" value="Embed Report" />
        </div>

        <div id="reportContainer"></div>
    </asp:Panel>
</div>
```

**Site.master**

```
window.onload = function () {
    // client side click to embed a selected report.
    var el = document.getElementById("bEmbedReportAction");
    if (el.addEventListener) {
        el.addEventListener("click", updateEmbedReporte, false);
    } else {
        el.attachEvent('onclick', updateEmbedReport);
    }

    // handle server side post backs, optimize for reload scenarios
    // show embedded report if all fields were filled in.
    var accessTokenElement = document.getElementById('MainContent_accessTokenTextbox');
    if (accessTokenElement !== null) {
        var accessToken = accessTokenElement.value;
        if (accessToken !== "")
            updateEmbedReport();
    }
};

// update embed report
function updateEmbedReport() {

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
        type: 'report',
        accessToken: accessToken,
        embedUrl: embedUrl
    };

    // Grab the reference to the div HTML element that will host the report.
    var reportContainer = document.getElementById('reportContainer');

    // Embed the report and display it within the div container.
    var report = powerbi.embed(reportContainer, config);

    // report.on will add an event handler which prints to Log window.
    report.on("error", function (event) {
        var logView = document.getElementById('logView');
        logView.innerHTML = logView.innerHTML + "Error<br/>";
        logView.innerHTML = logView.innerHTML + JSON.stringify(event.detail, null, "  ") + "<br/>";
        logView.innerHTML = logView.innerHTML + "---------<br/>";
    });
}
```

Wenn Sie das [Beispiel zum Integrieren eines Berichts in eine Web-App – integrate-report-web-app](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-report-web-app) heruntergeladen und ausgeführt haben, sieht das Beispiel ähnlich wie das folgende aus.

![Beispiel für eingebetteten Bericht](media/integrate-report/powerbi-embedded-report.png)

## <a name="working-with-groups-app-workspaces"></a>Arbeiten mit Gruppen (App-Arbeitsbereiche)
Zum Einbetten eines Berichts aus einer Gruppe (App-Arbeitsbereich) müssen Sie die Liste aller verfügbaren Berichte im Dashboard einer Gruppe mit dem folgenden REST-API-Aufruf abrufen. Weitere Informationen zu diesem REST-API-Aufruf finden Sie unter [Get Reports](https://msdn.microsoft.com/library/mt634543.aspx) (Berichte abrufen). Sie benötigen Berechtigungen in der Gruppe, damit die Anforderung Ergebnisse zurückgibt.

```
https://api.powerbi.com/v1.0/myorg/groups/{group_id}/reports
```

Die oben genannte API gibt die Liste der verfügbaren Berichte zurück. Jeder Bericht verfügt über eine EmbedUrl-Eigenschaft, die bereits so konstruiert ist, dass das Einbetten aus Gruppen unterstützt wird.

```
https://app.powerbi.com/reportEmbed?reportId={report_id}&groupId={group_id}
```

## <a name="next-steps"></a>Nächste Schritte
Eine Beispielanwendung können Sie auf GitHub einsehen. Weitere Informationen finden Sie im [Beispiel zum Integrieren eines Berichts in eine Web-App – integrate-report-web-app](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-report-web-app).

Weitere Informationen sind für die JavaScript-API verfügbar; siehe [Power BI-JavaScript-API](https://github.com/Microsoft/PowerBI-JavaScript).

Weitere Fragen? [Stellen Sie Ihre Frage in der Power BI-Community.](http://community.powerbi.com/)

