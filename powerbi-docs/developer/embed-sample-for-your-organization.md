---
title: Embedded Analytics für das Einbetten von Power BI-Inhalten in eine Anwendung für Ihre Organisation
description: Hier erfahren Sie, wie Sie mit den Power BI-APIs einen Bericht, ein Dashboard oder eine Kachel für Embedded Analytics für Ihre Organisation in eine Anwendung integrieren bzw. einbetten. Hier erfahren Sie, wie Sie Power BI mit Embedded Analytics-Software, Embedded Analytics-Tools oder eingebetteten Business Intelligence-Tools in Ihre Anwendung integrieren.
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-developer
ms.topic: tutorial
ms.custom: seodec18
ms.date: 12/10/2018
ms.openlocfilehash: 541e6e62ac075922cdb301343361ac328a3db28e
ms.sourcegitcommit: f25464d5cae46691130eb7b02c33f42404011357
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53180758"
---
# <a name="tutorial-embed-a-power-bi-report-dashboard-or-tile-into-an-application-for-your-organization"></a>Tutorial: Einbetten von Power BI-Berichten, -Dashboards oder -Kacheln in eine Anwendung für Ihre Organisation

In **Power BI** können Sie mit User Owns Data (Benutzer ist Besitzer der Daten) Berichte, Dashboards oder Kacheln in eine Anwendung einbetten. Mit **User Owns Data** (Benutzer ist Besitzer der Daten) kann Ihre Anwendung den Power BI-Dienst erweitern, um Embedded Analytics zu nutzen. Dieses Tutorial veranschaulicht die Vorgehensweise beim Integrieren eines Berichts in eine Anwendung. Verwenden Sie das Power BI .NET SDK mit der Power BI-JavaScript-API, um Power BI für Ihre Organisation in eine Anwendung einzubetten.

![Power BI Embed Report](media/embed-sample-for-your-organization/embed-sample-for-your-organization-035.png)

In diesem Tutorial lernen Sie Folgendes:
> [!div class="checklist"]
> * Registrieren einer Anwendung in Azure
> * Einbetten eines Power BI-Berichts in eine App

## <a name="prerequisites"></a>Voraussetzungen

Sie benötigen zunächst ein Power BI Pro-Konto und ein Microsoft Azure-Abonnement:

* Wenn Sie noch nicht bei Power BI Pro registriert sind, müssen Sie sich zuerst [für eine kostenlose Testversion registrieren](https://powerbi.microsoft.com/en-us/pricing/).
* Wenn Sie kein Azure-Abonnement besitzen, erstellen Sie ein [kostenloses Konto](https://azure.microsoft.com/free/?WT.mc_id=A261C142F), bevor Sie beginnen.
* Richten Sie Ihren eigenen [Azure Active Directory(Azure AD)-Mandanten](create-an-azure-active-directory-tenant.md) ein.
* Installieren Sie [Visual Studio](https://www.visualstudio.com/) ab Version 2013.

## <a name="set-up-your-embedded-analytics-development-environment"></a>Einrichten der Entwicklungsumgebung für eingebettete Analysen

Stellen Sie vor dem Einbetten von Berichten, Dashboards oder Kacheln in Ihre Anwendung sicher, dass Ihre Umgebung für Einbettungsvorgänge eingerichtet ist. Führen Sie im Rahmen der Einrichtung eine der folgenden Aktionen aus:

* Sie können sich mit dem [Setuptool für die Einbettung](https://aka.ms/embedsetup/UserOwnsData) vertraut machen, damit Sie schnell beginnen und eine Beispielanwendung herunterladen können. In dieser wird Ihnen ausführlich erläutert, wie Sie eine Umgebung erstellen und einen Bericht einbetten können.

* Führen Sie die Schritte in den folgenden Abschnitten aus, um die Umgebung manuell einzurichten.

### <a name="register-an-application-in-azure-active-directory"></a>Registrieren einer Anwendung in Azure Active Directory

Registrieren Sie Ihre Anwendung in Azure Active Directory, damit die Anwendung auf die Power BI-REST-APIs zugreifen kann. Anschließend können Sie eine Identität für Ihre Anwendung erstellen und Berechtigungen für Power BI-REST-Ressourcen angeben.

1. Akzeptieren Sie die [Nutzungsbedingungen für die Microsoft Power BI-API](https://powerbi.microsoft.com/api-terms).

2. Melden Sie sich beim [Azure-Portal](https://portal.azure.com) an.

    ![Azure-Dashboard](media/embed-sample-for-your-organization/embed-sample-for-your-organization-002.png)

3. Wählen Sie im Navigationsbereich auf der linken Seite die Option **Alle Dienste** und anschließend **App-Registrierungen** aus. Wählen Sie anschließend **Neue Anwendungsregistrierung** aus.

    ![App-Registrierung, Suche](media/embed-sample-for-your-organization/embed-sample-for-your-organization-003.png)</br>

    ![Neue App-Registrierung](media/embed-sample-for-your-organization/embed-sample-for-your-organization-004.png)

4. Folgen Sie den Anweisungen, und erstellen Sie eine neue Anwendung . Verwenden Sie bei **user owns data** (Benutzer ist Besitzer der Daten) für den **Anwendungstyp** die Option **Web-App/API**. Geben Sie eine **Anmelde-URL** an, die von Azure AD zur Rückgabe von Tokenantworten verwendet wird. Geben Sie einen für Ihre Anwendung spezifischen Wert ein. Ein Beispiel hierfür ist `http://localhost:13526/`.

    ![Erstellen einer App](media/embed-sample-for-your-organization/embed-sample-for-your-organization-005.png)

### <a name="apply-permissions-to-your-application-within-azure-active-directory"></a>Anwenden von Berechtigungen auf die Anwendung in Azure Active Directory

Aktivieren Sie neben den Einstellungen auf der App-Registrierungsseite zusätzliche Berechtigungen für Ihre Anwendung. Melden Sie sich zum Aktivieren von Berechtigungen mit einem globalen Administratorkonto an.

### <a name="use-the-azure-active-directory-portal"></a>Verwenden des Azure Active Directory-Portals

1. Navigieren Sie im Azure-Portal zu [App-Registrierungen](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ApplicationsListBlade), und wählen Sie die App aus, die Sie für die Einbettung verwenden.

    ![App auswählen](media/embed-sample-for-your-organization/embed-sample-for-your-organization-006.png)

2. Wählen Sie **Einstellungen**aus. Wählen Sie anschließend unter **API-Zugriff** die Option **Erforderliche Berechtigungen** aus.

    ![Erforderliche Berechtigungen](media/embed-sample-for-your-organization/embed-sample-for-your-organization-008.png)

3. Wählen Sie **Microsoft Azure Active Directory** aus. Stellen Sie anschließend sicher, dass **Hiermit greifen Sie als angemeldeter Benutzer auf das Verzeichnis zu** ausgewählt wurde. Wählen Sie **Speichern**.

    ![Microsoft Azure AD-Berechtigungen](media/embed-sample-for-your-organization/embed-sample-for-your-organization-011.png)

4. Wählen Sie **Hinzufügen**.

    ![Berechtigungen hinzufügen](media/embed-sample-for-your-organization/embed-sample-for-your-organization-012.png)

5. Wählen Sie **API auswählen** aus.

    ![API-Zugriff hinzufügen](media/embed-sample-for-your-organization/embed-sample-for-your-organization-013.png)

6. Wählen Sie **Power BI-Dienst** aus. Wählen Sie anschließend **Auswählen** aus.

    ![Power BI-Dienst auswählen](media/embed-sample-for-your-organization/embed-sample-for-your-organization-014.png)

7. Wählen Sie alle Berechtigungen unter **Delegierte Berechtigungen** aus. Wählen sie die Berechtigungen einzeln aus, um die Auswahl zu speichern. Wählen Sie **Speichern** aus, wenn Sie fertig sind.

    ![Delegierte Berechtigungen auswählen](media/embed-sample-for-your-organization/embed-sample-for-your-organization-015.png)

## <a name="set-up-your-power-bi-environment"></a>Einrichten der Power BI-Umgebung

### <a name="create-an-app-workspace"></a>App-Arbeitsbereich erstellen

Wenn Sie Berichte, Dashboards oder Kacheln für Ihre Kunden einbetten, müssen Sie Ihre Inhalte in einem App-Arbeitsbereich platzieren:

1. Erstellen Sie zunächst den Arbeitsbereich. Wählen Sie **Arbeitsbereiche** > **App-Arbeitsbereich erstellen** aus. In diesem Arbeitsbereich legen Sie die Inhalte ab, auf die Ihre Anwendung zugreifen muss.

    ![Erstellen eines Arbeitsbereichs](media/embed-sample-for-your-organization/embed-sample-for-your-organization-020.png)

2. Benennen Sie den Arbeitsbereich. Wenn die entsprechende **Arbeitsbereichs-ID** nicht verfügbar ist, geben Sie eine eindeutige ID ein. Dieser Name muss zudem mit dem Namen der App identisch sein.

    ![Benennen eines Arbeitsbereichs](media/embed-sample-for-your-organization/embed-sample-for-your-organization-021.png)

3. Sie können einige Optionen festlegen. Wenn Sie **Öffentlich** auswählen, können die Inhalte des Arbeitsbereichs von jedem Benutzer in der Organisation angezeigt werden. **Privat** bedeutet, dass die Inhalte des Arbeitsbereichs nur von dessen Mitgliedern angezeigt werden können.

    ![Auswählen von „Privat“ oder „Öffentlich“](media/embed-sample-for-your-organization/embed-sample-for-your-organization-022.png)

    Sie können die Einstellung „Öffentlich“ oder „Privat“ einer Gruppe nach deren Erstellung nicht mehr ändern.

4. Sie können auch auswählen, ob Mitglieder Inhalte bearbeiten können oder schreibgeschützten Zugriff haben sollen.

    ![Mitgliederzugriff auswählen](media/embed-sample-for-your-organization/embed-sample-for-your-organization-023.png)

5. Fügen Sie E-Mail-Adressen von Personen hinzu, die Zugriff auf den Arbeitsbereich haben sollen, und wählen Sie **Hinzufügen** aus. Sie können keine Gruppenaliase, sondern nur einzelne Personen hinzufügen.

6. Legen Sie für jede Person fest, ob sie Mitglied oder Administrator ist. Administratoren können den Arbeitsbereich selbst bearbeiten und weitere Mitglieder hinzufügen. Mitglieder können den Inhalt des Arbeitsbereichs bearbeiten, es sei denn, sie haben schreibgeschützten Zugriff. Sowohl Administratoren als auch Mitglieder können die App veröffentlichen.

    Jetzt können Sie den neuen Arbeitsbereich anzeigen. Der Arbeitsbereich wird in Power BI erstellt und geöffnet. Er wird in der Liste der Arbeitsbereiche angezeigt, deren Mitglied Sie sind. Da Sie Administrator sind, können Sie die Auslassungspunkte (...) auswählen, um zurückzukehren, und Änderungen vornehmen, neue Mitglieder hinzufügen oder deren Berechtigungen ändern.

    ![App-Arbeitsbereich erstellen](media/embed-sample-for-your-organization/embed-sample-for-your-organization-025.png)

### <a name="create-and-publish-your-reports"></a>Erstellen und Veröffentlichen von Berichten

Sie können Ihre Berichte und Datasets mit Power BI Desktop erstellen. Anschließend können Sie diese Berichte in einem App-Arbeitsbereich veröffentlichen. Der Benutzer, der die Berichte veröffentlicht, muss über eine Power BI Pro-Lizenz verfügen, damit er einen App-Arbeitsbereich veröffentlichen kann.

1. Laden Sie das Beispiel von GitHub herunter: [Blog-Demo](https://github.com/Microsoft/powerbi-desktop-samples).

    ![Herunterladen der Demoversion](media/embed-sample-for-your-organization/embed-sample-for-your-organization-026-1.png)

2. Öffnen Sie in Power BI Desktop den PBIX-Beispielbericht.

   ![Power BI Desktop-Beispielbericht](media/embed-sample-for-your-organization/embed-sample-for-your-organization-027.png)

3. Veröffentlichen Sie den Bericht im App-Arbeitsbereich.

   ![Veröffentlichen eines Power BI Desktop-Berichts](media/embed-sample-for-your-organization/embed-sample-for-your-organization-028.png)

    Jetzt können Sie den Bericht online im Power BI-Dienst anzeigen.

   ![Anzeigen eines Power BI Desktop-Berichts](media/embed-sample-for-your-organization/embed-sample-for-your-organization-029.png)

## <a name="embed-your-content-by-using-the-sample-application"></a>Einbetten von Inhalt mit der Beispielanwendung

Führen Sie die folgenden Schritte aus, um Ihren Inhalt in eine Beispielanwendung einzubetten:

1. Laden Sie das [User Owns Data](https://github.com/Microsoft/PowerBI-Developer-Samples)-Beispiel aus GitHub herunter, um zu beginnen. Es gibt drei verschiedene Beispielanwendungen: eine für [Berichte](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-report-web-app), eine für [Dashboards](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-dashboard-web-app) und eine für [Kacheln](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-tile-web-app). Dieser Artikel bezieht sich auf die Anwendung von **Berichten**.

    ![User Owns Data-Anwendungsbeispiel](media/embed-sample-for-your-organization/embed-sample-for-your-organization-026.png)

2. Öffnen Sie in der Beispielanwendung die Datei **Cloud.config**. Damit die Anwendung erfolgreich ausgeführt werden kann, müssen Sie einige Felder auffüllen: **ApplicationID** und **ApplicationSecret**.

    ![Datei „Cloud.config“](media/embed-sample-for-your-organization/embed-sample-for-your-organization-030.png)

    Geben Sie für **ApplicationID** die **Anwendungs-ID** aus Azure an. Die Anwendung identifiziert sich mithilfe der **ApplicationID** bei den Benutzern, von denen Sie Berechtigungen anfordern.

    Führen Sie die folgenden Schritte aus, um die **ApplicationID** abzurufen:

    1. Melden Sie sich beim [Azure-Portal](https://portal.azure.com) an.

       ![Dashboard im Azure-Portal](media/embed-sample-for-your-organization/embed-sample-for-your-organization-002.png)

    2. Wählen Sie im Navigationsbereich auf der linken Seite die Option **Alle Dienste** und anschließend **App-Registrierungen** aus.

       ![App-Registrierung, Suche](media/embed-sample-for-your-organization/embed-sample-for-your-organization-003.png)

    3. Wählen Sie die Anwendung aus, die **ApplicationID** verwenden muss.

       ![App auswählen](media/embed-sample-for-your-organization/embed-sample-for-your-organization-006.png)

    4. Ihnen müsste eine **Anwendungs-ID** angezeigt werden, die als GUID aufgeführt ist. Verwenden Sie diese **Anwendungs-ID** als **ApplicationID** für die Anwendung.

        ![ApplicationID](media/embed-sample-for-your-organization/embed-sample-for-your-organization-007.png)

    Geben Sie für **ApplicationSecret** die Informationen aus dem Abschnitt **Schlüssel** Ihres Abschnitts für **App-Registrierungen** in **Azure** ein.

    Führen Sie die folgenden Schritte aus, um **ApplicationSecret** abzurufen:

    1. Melden Sie sich beim [Azure-Portal](https://portal.azure.com) an.

       ![Azure-Portal](media/embed-sample-for-your-organization/embed-sample-for-your-organization-002.png)

    2. Wählen Sie im Navigationsbereich auf der linken Seite die Option **Alle Dienste** und anschließend **App-Registrierungen** aus.

       ![App-Registrierung, Suche](media/embed-sample-for-your-organization/embed-sample-for-your-organization-003.png)

    3. Wählen Sie die Anwendung aus, die **ApplicationSecret** verwenden muss.

       ![App auswählen](media/embed-sample-for-your-organization/embed-sample-for-your-organization-006.png)

    4. Wählen Sie **Einstellungen**aus.

       ![„Einstellungen“ auswählen](media/embed-sample-for-your-organization/embed-sample-for-your-organization-038.png)

    5. Klicken Sie auf **Schlüssel**.

       ![„Schlüssel“ auswählen](media/embed-sample-for-your-organization/embed-sample-for-your-organization-039.png)

    6. Geben Sie in das Feld **Beschreibung** einen Namen ein, und wählen Sie eine Dauer aus. Klicken Sie anschließend auf **Speichern**, um den **Wert** für Ihre Anwendung abzurufen. Wenn Sie den Bereich **Schlüssel** nach dem Speichern des Schlüsselwerts schließen, wird das Wertfeld nur als ausgeblendet angezeigt. An diesem Punkt können Sie den Schlüsselwert nicht abrufen. Wenn Sie den Schlüsselwert verlieren, müssen Sie im Azure-Portal einen neuen erstellen.

          ![Schlüsselwert](media/embed-sample-for-your-organization/embed-sample-for-your-organization-031.png)

    7. Geben Sie als **groupId** die App-Arbeitsbereichs-GUID aus Power BI ein.

       ![groupId eingeben](media/embed-sample-for-customers/embed-sample-for-customers-031.png)

    8. Geben Sie als **groupId** die Berichts-GUID aus Power BI ein.

       ![reportId eingeben](media/embed-sample-for-customers/embed-sample-for-customers-032.png)

3. Führen Sie die Anwendung aus:

    Wählen Sie in **Visual Studio** die Option **Ausführen** aus.

    ![Ausführen der Anwendung](media/embed-sample-for-your-organization/embed-sample-for-your-organization-033.png)

    Klicken Sie dann auf **Bericht abrufen**.

    ![Inhalt auswählen](media/embed-sample-for-your-organization/embed-sample-for-your-organization-034.png)

    Jetzt können Sie den Bericht in der Beispielanwendung anzeigen.

    ![Bericht in der Anwendung anzeigen](media/embed-sample-for-your-organization/embed-sample-for-your-organization-035.png)

## <a name="embed-your-content-within-your-application"></a>Einbetten von Inhalt in Ihre Anwendung

Auch wenn die Schritte zum Einbetten des Inhalts mit den [Power BI-REST-APIs](https://docs.microsoft.com/rest/api/power-bi/) durchgeführt werden können, werden die in diesem Artikel beschriebenen Beispielcodes mit dem .NET SDK erstellt.

Wenn Sie einen Bericht in eine Web-App integrieren möchten, müssen Sie die Power BI-REST-API oder das Power BI C# SDK verwenden. Zum Abrufen eines Berichts verwenden Sie zudem ein Azure Active-Zugriffstoken für die Autorisierung. Anschließend laden Sie den Bericht mithilfe desselben Zugriffstokens. Die Power BI-REST-API bietet programmgesteuerten Zugriff auf bestimmte Power BI-Ressourcen. Weitere Informationen finden Sie unter [Power BI-REST-API](https://docs.microsoft.com/rest/api/power-bi/) und [Power BI-JavaScript-API](https://github.com/Microsoft/PowerBI-JavaScript).

### <a name="get-an-access-token-from-azure-ad"></a>Abrufen eines Zugriffstokens aus Azure AD

In der Anwendung müssen Sie ein Zugriffstoken aus Azure AD abrufen, bevor Sie die Power BI-REST-API aufrufen können. Weitere Informationen finden Sie unter [Authentifizieren von Benutzern und Abrufen eines Azure AD-Zugriffstokens für die Power BI-App](get-azuread-access-token.md).

### <a name="get-a-report"></a>Abrufen eines Berichts

Zum Abrufen eines Power BI-Berichts müssen Sie den Vorgang [Berichte abrufen](https://docs.microsoft.com/rest/api/power-bi/reports/getreports) verwenden, um eine Liste der Power BI-Berichte abzurufen. Aus der Liste der Berichte können Sie eine Berichts-ID abrufen.

### <a name="get-reports-by-using-an-access-token"></a>Abrufen von Berichten mithilfe eines Zugriffstokens

Der Vorgang [Get Reports](https://docs.microsoft.com/rest/api/power-bi/reports/getreports) (Berichte abrufen) gibt eine Liste der Berichte zurück. Anhand der Liste der Berichte können Sie einen einzelnen Bericht abrufen.

Zum Ausführen des REST-API-Aufrufs müssen Sie einen *Autorisierungsheader* im Format *Träger {Zugriffstoken}* einschließen.

#### <a name="get-reports-with-the-rest-api"></a>Abrufen von Berichten mit der REST-API

Im Folgenden finden Sie ein Codebeispiel zum Abrufen von Berichten mit der **REST-API**:

> [!NOTE]  
> In der Datei **Default.aspx.cs** in der [Beispielanwendung](#embed-your-content-using-the-sample-application) ist ein Beispiel zum Abrufen eines Inhaltselements verfügbar, das eingebettet werden soll. Als Beispiele wird ein Bericht, ein Dashboard oder eine Kachel aufgeführt.

```csharp
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

#### <a name="get-reports-by-using-the-net-sdk"></a>Abrufen von Berichten mit dem .NET SDK

Mithilfe des .NET-SDK können Sie eine Liste der Berichte abrufen und müssen die REST-API nicht direkt aufrufen. Im folgenden Codebeispiel wird gezeigt, wie Sie Berichte auflisten können:

```csharp
using Microsoft.IdentityModel.Clients.ActiveDirectory;
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

var tokenCredentials = new TokenCredentials(<ACCESS TOKEN>, "Bearer");

// Create a Power BI Client object. It is used to call Power BI APIs.
using (var client = new PowerBIClient(new Uri(ApiUrl), tokenCredentials))
{
    // Get the first report all reports in that workspace
    ODataResponseListReport reports = client.Reports.GetReports();

    Report report = reports.Value.FirstOrDefault();

    var embedUrl = report.EmbedUrl;
}
```

### <a name="load-a-report-by-using-javascript"></a>Laden eines Berichts mit JavaScript

Sie können mithilfe von JavaScript einen Bericht in ein div-Element auf Ihrer Webseite laden. Im folgenden Codebeispiel wird gezeigt, wie ein Bericht aus einem bestimmten Arbeitsbereich abgerufen wird:

> [!NOTE]  
> In der Datei **Default.aspx** in der [Beispielanwendung](#embed-your-content-using-the-sample-application) ist ein Beispiel zum Laden eines Inhaltselements verfügbar, das eingebettet werden soll. Als Beispiele wird ein Bericht, ein Dashboard oder eine Kachel aufgeführt.

```javascript
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

#### <a name="sitemaster"></a>Site.master

```javascript
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
    }
  );
}
```

## <a name="using-a-power-bi-premium-dedicated-capacity"></a>Verwenden einer dedizierten Power BI Premium-Kapazität

Wenn Sie mit dem Entwickeln Ihrer Anwendung fertig sind, sollten Sie Ihren App-Arbeitsbereich durch eine dedizierte Kapazität absichern.

### <a name="create-a-dedicated-capacity"></a>Erstellen einer dedizierten Kapazität

Indem Sie eine dedizierte Kapazität erstellen, können Sie die dazugehörigen Vorteile für den Inhalt in Ihrem App-Arbeitsbereich verwenden. Sie können mit [Power BI Premium](../service-premium.md) eine dedizierte Kapazität erstellen.

In der folgenden Tabelle werden die verfügbaren Power BI Premium-SKUs in [Microsoft Office 365](../service-admin-premium-purchase.md) aufgelistet:

| Kapazitätsknoten | Gesamtanzahl virtueller Kerne<br/>(Back-End + Front-End) | virtuelle Back-End-Kerne | virtuelle Front-End-Kerne | Grenzwerte für DirectQuery/Liveverbindung | Höchstzahl an Seitenladevorgängen zu Spitzenzeiten |
| --- | --- | --- | --- | --- | --- |
| EM1 |1 virtueller Kern |0,5 virtuelle Kerne, 10 GB RAM |0,5 virtuelle Kerne |3,75 pro Sekunde |150–300 |
| EM2 |2 virtuelle Kerne |1 virtueller Kern, 10 GB RAM |1 virtueller Kern |7,5 pro Sekunde |301–600 |
| EM3 |4 virtuelle Kerne |2 virtuelle Kerne, 10 GB RAM |2 virtuelle Kerne |15 pro Sekunde |601–1.200 |
| P1 |8 virtuelle Kerne |4 virtuelle Kerne, 25 GB RAM |4 virtuelle Kerne |30 pro Sekunde |1.201–2.400 |
| P2 |16 virtuelle Kerne |8 virtuelle Kerne, 50 GB RAM |8 virtuelle Kerne |60 pro Sekunde |2.401–4.800 |
| P3 |32 virtuelle Kerne |16 virtuelle Kerne, 100 GB RAM |16 virtuelle Kerne |120 pro Sekunde |4.801 – 9.600 |
| P4 |64 virtuelle Kerne |32 virtuelle Kerne, 200 GB RAM |32 virtuelle Kerne |240 pro Sekunde |9.601 – 19.200 |
| P5 |128 virtuelle Kerne |64 virtuelle Kerne, 400 GB RAM |64 virtuelle Kerne |480 pro Sekunde |19.201 – 38.400 |

> [!NOTE]
> - Wenn Sie versuchen, Inhalte in Microsoft Office-Apps einzubetten, können Sie mithilfe von EM-SKUs mit einer kostenlosen Power BI-Lizenz auf diese Inhalte zugreifen. Wenn Sie Powerbi.com oder Power BI Mobile verwenden, können Sie jedoch nicht mit einer kostenlosen Power BI-Lizenz auf Inhalte zugreifen.
> - Wenn Sie versuchen, Inhalte mit Powerbi.com oder Power BI Mobile in Microsoft Office-Apps einzubetten, können Sie mit einer kostenlosen Power BI-Lizenz auf diese Inhalte zugreifen.

### <a name="assign-an-app-workspace-to-a-dedicated-capacity"></a>Zuweisen eines App-Arbeitsbereichs zu einer dedizierten Kapazität

Nachdem Sie eine dedizierte Kapazität erstellt haben, können Sie dieser Ihren App-Arbeitsbereich zuweisen. Führen Sie die folgenden Schritte durch, um diesen Vorgang abzuschließen:

1. Erweitern Sie im Power BI-Dienst Arbeitsbereiche, und klicken Sie auf die Auslassungspunkte neben dem Arbeitsbereich, den Sie zur Einbettung von Inhalten verwenden. Klicken Sie dann auf **Arbeitsbereich bearbeiten**.

    ![Arbeitsbereich bearbeiten](media/embed-sample-for-your-organization/embed-sample-for-your-organization-036.png)

2. Erweitern Sie **Erweitert**, und aktivieren Sie **Dedizierte Kapazität**. Wählen Sie die dedizierte Kapazität aus, die Sie erstellt haben. Klicken Sie auf **Speichern**.

    ![Zuweisen einer dedizierten Kapazität](media/embed-sample-for-your-organization/embed-sample-for-your-organization-024.png)

3. Nachdem Sie auf **Speichern** geklickt haben, sollte neben dem Namen des App-Arbeitsbereichs eine Raute angezeigt werden.

    ![An Kapazität gebundener App-Arbeitsbereich](media/embed-sample-for-your-organization/embed-sample-for-your-organization-037.png)

## <a name="admin-settings"></a>Administratoreinstellungen

Globale Administratoren oder Power BI-Dienstadministratoren können die Möglichkeit der Verwendung der REST-APIs für einen Mandanten aktivieren oder deaktivieren. Power BI-Administratoren können diese Einstellung für die gesamte Organisation oder für einzelne Sicherheitsgruppen festlegen. In der Standardeinstellung ist sie für die gesamte Organisation aktiviert. Sie können diese Änderungen im [Power BI-Verwaltungsportal](../service-admin-portal.md) vornehmen.

## <a name="next-steps"></a>Nächste Schritte

In diesem Tutorial haben Sie gelernt, wie Sie Power BI-Inhalte mithilfe Ihres Power BI-Organisationskontos in eine Anwendung einbetten. Sie können jetzt versuchen, Power BI-Inhalte mithilfe von Apps in eine Anwendung einzubetten. Sie können auch versuchen, Power BI-Inhalte für Ihre Kunden einzubetten:

> [!div class="nextstepaction"]
> [Embed from apps (Einbetten aus Apps)](embed-from-apps.md)

> [!div class="nextstepaction"]
>[Inhalte für Ihre Kunden einbetten](embed-sample-for-customers.md)

Wenn Sie weitere Fragen haben, [stellen Sie diese in der Power BI-Community](http://community.powerbi.com/).
