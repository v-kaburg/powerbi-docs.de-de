---
title: Authentifizieren von Benutzern und Abrufen eines Azure AD-Zugriffstokens für die Anwendung
description: Erfahren Sie, wie Sie eine Anwendung zum Einbetten von Power BI-Inhalten in Azure Active Directory registrieren können.
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 08/11/2017
ms.author: maghan
ms.openlocfilehash: f585d5a48ab38124d17110049cd7dd7d5da45164
ms.sourcegitcommit: a36f82224e68fdd3489944c9c3c03a93e4068cc5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/31/2019
ms.locfileid: "55428760"
---
# <a name="authenticate-users-and-get-an-azure-ad-access-token-for-your-power-bi-app"></a>Authentifizieren von Benutzern und Abrufen eines Azure AD-Zugriffstokens für Ihre Power BI-App
Hier erfahren Sie, wie Sie Benutzer in Ihrer Power BI-Anwendung authentifizieren und ein Zugriffstoken für die Verwendung mit der REST-API abrufen.

Bevor Sie die Power BI-REST-API aufrufen können, müssen Sie ein Azure Active Directory-**Authentifizierungszugriffstoken** (Azure AD-Zugriffstoken) abrufen. Über ein **Zugriffstoken** erhält Ihre App Zugriff auf **Power BI**-Dashboards, -Kacheln und -Berichte. Weitere Informationen zum Azure Active Directory-Flow (Azure AD) für **Zugriffstoken** finden Sie unter [Authorization Code Grant-Flow](https://msdn.microsoft.com/library/azure/dn645542.aspx).

Je nachdem, wie Sie Inhalte einbetten, wird das Zugriffstoken auf andere Weise abgerufen. In diesem Artikel werden zwei unterschiedliche Ansätze erläutert.

## <a name="access-token-for-power-bi-users-user-owns-data"></a>Zugriffstoken für Power BI-Benutzer (Benutzer ist Besitzer der Daten)
Dieses Beispiel ist auf eine Situation ausgelegt, in der sich Ihre Benutzer mit ihren Organisationsanmeldeinformationen manuell bei Azure AD anmelden. Dieser Ansatz wird verwendet, wenn Inhalte für Power BI-Benutzer eingebettet werden, die innerhalb des Power BI-Dienstes auf Inhalte zugreifen, für die sie über die entsprechenden Zugriffsberechtigungen verfügen.

### <a name="get-an-authorization-code-from-azure-ad"></a>Abrufen eines Autorisierungscodes von Azure AD
Der erste Schritt beim Abrufen eines **Zugriffstokens** ist das Abrufen eines Autorisierungscodes von **Azure AD**. Zu diesem Zweck erstellen Sie eine Abfragezeichenfolge mit den folgenden Eigenschaften und leiten diese weiter an **Azure AD**.

**Abfragezeichenfolge für den Autorisierungscode**

```
var @params = new NameValueCollection
{
    //Azure AD will return an authorization code. 
    //See the Redirect class to see how "code" is used to AcquireTokenByAuthorizationCode
    {"response_type", "code"},

    //Client ID is used by the application to identify themselves to the users that they are requesting permissions from. 
    //You get the client id when you register your Azure app.
    {"client_id", Properties.Settings.Default.ClientID},

    //Resource uri to the Power BI resource to be authorized
    // https://analysis.windows.net/powerbi/api
    {"resource", Properties.Settings.Default.PowerBiAPI},

    //After user authenticates, Azure AD will redirect back to the web app
    {"redirect_uri", "http://localhost:13526/Redirect"}
};
```

Nachdem Sie eine Abfragezeichenfolge erstellt haben, leiten Sie diese weiter an **Azure AD**, um einen **Autorisierungscode** abzurufen.  Im Folgenden finden Sie eine vollständige C#-Methode zum Erstellen einer Abfragezeichenfolge für den **Autorisierungscode** und leiten diese an **Azure AD** weiter. Wenn Sie über den Autorisierungscode verfügen, erhalten Sie ein **Zugriffstoken** mithilfe des **Autorisierungscodes**.

In „redirect.aspx.cs“ wird dann [AuthenticationContext.AcquireTokenByAuthorizationCode](https://msdn.microsoft.com/library/azure/dn479531.aspx) aufgerufen, um das Token zu generieren.

**Abrufen des Autorisierungscodes**

```
protected void signInButton_Click(object sender, EventArgs e)
{
    //Create a query string
    //Create a sign-in NameValueCollection for query string
    var @params = new NameValueCollection
    {
        //Azure AD will return an authorization code. 
        //See the Redirect class to see how "code" is used to AcquireTokenByAuthorizationCode
        {"response_type", "code"},

        //Client ID is used by the application to identify themselves to the users that they are requesting permissions from. 
        //You get the client id when you register your Azure app.
        {"client_id", Properties.Settings.Default.ClientID},

        //Resource uri to the Power BI resource to be authorized
        // https://analysis.windows.net/powerbi/api
        {"resource", Properties.Settings.Default.PowerBiAPI},

        //After user authenticates, Azure AD will redirect back to the web app
        {"redirect_uri", "http://localhost:13526/Redirect"}
    };

    //Create sign-in query string
    var queryString = HttpUtility.ParseQueryString(string.Empty);
    queryString.Add(@params);

    //Redirect authority
    //Authority Uri is an Azure resource that takes a client id to get an Access token
    // AADAuthorityUri = https://login.microsoftonline.net/common/
    string authorityUri = Properties.Settings.Default.AADAuthorityUri;
    var authUri = String.Format("{0}?{1}", authorityUri, queryString);
    Response.Redirect(authUri);
}
```

### <a name="get-an-access-token-from-authorization-code"></a>Abrufen eines Zugriffstokens aus dem Autorisierungscode
Sie verfügen nun über einen Autorisierungscode von Azure AD. Nach der Weiterleitung durch **Azure AD** mit einem **Autorisierungscode** an Ihre Web-App verwenden Sie den **Autorisierungscode**, um ein Zugriffstoken abzurufen. Unten finden Sie ein C#-Beispiel, das Sie auf Ihrer Umleitungsseite verwenden können, sowie das Page_Load-Ereignis für Ihre Seite „default.aspx“.

Der Namespace **Microsoft.IdentityModel.Clients.ActiveDirectory** kann aus dem NuGet-Paket [Active Directory Authentication Library](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/) abgerufen werden.

```
Install-Package Microsoft.IdentityModel.Clients.ActiveDirectory
```

**Redirect.aspx.cs**

```
using Microsoft.IdentityModel.Clients.ActiveDirectory;

protected void Page_Load(object sender, EventArgs e)
{
    //Redirect uri must match the redirect_uri used when requesting Authorization code.
    string redirectUri = String.Format("{0}Redirect", Properties.Settings.Default.RedirectUrl);
    string authorityUri = Properties.Settings.Default.AADAuthorityUri;

    // Get the auth code
    string code = Request.Params.GetValues(0)[0];

    // Get auth token from auth code
    TokenCache TC = new TokenCache();

    AuthenticationContext AC = new AuthenticationContext(authorityUri, TC);
    ClientCredential cc = new ClientCredential
        (Properties.Settings.Default.ClientID,
        Properties.Settings.Default.ClientSecret);

    AuthenticationResult AR = AC.AcquireTokenByAuthorizationCode(code, new Uri(redirectUri), cc);

    //Set Session "authResult" index string to the AuthenticationResult
    Session[_Default.authResultString] = AR;

    //Redirect back to Default.aspx
    Response.Redirect("/Default.aspx");
}
```

**Default.aspx**

```
using Microsoft.IdentityModel.Clients.ActiveDirectory;

protected void Page_Load(object sender, EventArgs e)
{

    //Test for AuthenticationResult
    if (Session[authResultString] != null)
    {
        //Get the authentication result from the session
        authResult = (AuthenticationResult)Session[authResultString];

        //Show Power BI Panel
        signInStatus.Visible = true;
        signInButton.Visible = false;

        //Set user and token from authentication result
        userLabel.Text = authResult.UserInfo.DisplayableId;
        accessTokenTextbox.Text = authResult.AccessToken;
    }
}
```

## <a name="access-token-for-non-power-bi-users-app-owns-data"></a>Zugriffstoken für Benutzer, die kein Power BI verwenden (App ist Besitzer der Daten)
Dieser Ansatz wird normalerweise für Anwendungen vom Typ ISV verwendet, bei denen die App Besitzer des Zugriffs auf die Daten ist. Bei den Benutzern handelt es sich nicht unbedingt um Power BI-Benutzer, und die Anwendung steuert die Authentifizierung und den Zugriff für die Endbenutzer.

Bei diesem Ansatz verwenden Sie ein einziges *Hauptkonto*, das einen Power BI Pro-Benutzer darstellt. Die Anmeldeinformationen für dieses Konto werden zusammen mit der Anwendung gespeichert. Die Anwendung authentifiziert sich mit diesen gespeicherten Anmeldeinformationen bei Azure AD. Der Beispielcode unten stammt aus dem [Beispiel zu Daten im Besitz der App](https://github.com/guyinacube/PowerBI-Developer-Samples/tree/master/App%20Owns%20Data)

**HomeController.cs**

```
using Microsoft.IdentityModel.Clients.ActiveDirectory;

// Create a user password cradentials.
var credential = new UserPasswordCredential(Username, Password);

// Authenticate using created credentials
var authenticationContext = new AuthenticationContext(AuthorityUrl);
var authenticationResult = await authenticationContext.AcquireTokenAsync(ResourceUrl, ClientId, credential);

if (authenticationResult == null)
{
    return View(new EmbedConfig()
    {
        ErrorMessage = "Authentication Failed."
    });
}

var tokenCredentials = new TokenCredentials(authenticationResult.AccessToken, "Bearer");
```

Informationen zum Verwenden von **await** finden Sie unter [await (C#-Referenz)](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/await)

## <a name="next-steps"></a>Nächste Schritte
Nun verfügen Sie über das Zugriffstoken und können die Power BI-REST-API aufrufen, um Inhalte einzubetten. Weitere Informationen zum Einbetten von Inhalten finden Sie unter [Wie soll ich Power BI-Dashboards, -Berichte und -Kacheln einbetten?](embed-sample-for-customers.md#embed-your-content-within-your-application).

Weitere Fragen? [Stellen Sie Ihre Frage in der Power BI-Community.](http://community.powerbi.com/)