---
title: Authentifizieren von Benutzern und Abrufen eines Azure AD-Zugriffstokens für die Anwendung
description: Erfahren Sie, wie Sie eine Anwendung zum Einbetten von Power BI-Inhalten in Azure Active Directory registrieren können.
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 02/05/2019
ms.openlocfilehash: 7b2249964f2fff26bc68fea19fd0010d8990110b
ms.sourcegitcommit: 0abcbc7898463adfa6e50b348747256c4b94e360
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2019
ms.locfileid: "55762534"
---
# <a name="get-an-azure-ad-access-token-for-your-power-bi-application"></a>Abrufen eines Azure AD-Zugriffstokens für Ihre Power BI-Anwendung

Hier erfahren Sie, wie Sie Benutzer in Ihrer Power BI-Anwendung authentifizieren und ein Zugriffstoken für die Verwendung mit der REST-API abrufen.

Bevor Sie die Power BI-REST-API aufrufen können, müssen Sie ein Azure Active Directory-**Authentifizierungszugriffstoken** (Azure AD-Zugriffstoken) abrufen. Über ein **Zugriffstoken** erhält Ihre App Zugriff auf **Power BI**-Dashboards, -Kacheln und -Berichte. Weitere Informationen zum Azure Active Directory-Flow (Azure AD) für **Zugriffstoken** finden Sie unter [Authorization Code Grant-Flow](https://msdn.microsoft.com/library/azure/dn645542.aspx).

Je nachdem, wie Sie Inhalte einbetten, wird das Zugriffstoken auf andere Weise abgerufen. In diesem Artikel werden zwei unterschiedliche Ansätze erläutert.

## <a name="access-token-for-power-bi-users-user-owns-data"></a>Zugriffstoken für Power BI-Benutzer (Benutzer ist Besitzer der Daten)

Dieses Beispiel ist auf eine Situation ausgelegt, in der sich Ihre Benutzer mit ihren Organisationsanmeldeinformationen manuell bei Azure AD anmelden. Diese Aufgabe wird verwendet, wenn Inhalte für Power BI-Benutzer eingebettet werden, die innerhalb des Power BI-Dienstes auf Inhalte zugreifen, für die sie über die entsprechenden Zugriffsberechtigungen verfügen.

### <a name="get-an-authorization-code-from-azure-ad"></a>Abrufen eines Autorisierungscodes von Azure AD

Der erste Schritt beim Abrufen eines **Zugriffstokens** ist das Abrufen eines Autorisierungscodes von **Azure AD**. Erstellen Sie eine Abfragezeichenfolge mit den folgenden Eigenschaften und leiten diese an **Azure AD** weiter.

#### <a name="authorization-code-query-string"></a>Abfragezeichenfolge für den Autorisierungscode

```csharp
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

In „redirect.aspx.cs“ wird [AuthenticationContext.AcquireTokenByAuthorizationCode](https://msdn.microsoft.com/library/azure/dn479531.aspx) aufgerufen, um das Token zu generieren.

#### <a name="get-authorization-code"></a>Abrufen des Autorisierungscodes

```csharp
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

```powershell
Install-Package Microsoft.IdentityModel.Clients.ActiveDirectory
```

#### <a name="redirectaspxcs"></a>Redirect.aspx.cs

```csharp
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

#### <a name="defaultaspx"></a>Default.aspx

```csharp
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

### <a name="access-token-with-a-master-account"></a>Zugriffstoken mit einem Masterkonto

Bei diesem Ansatz verwenden Sie ein einziges *Masterkonto*, das einen Power BI Pro-Benutzer darstellt. Die Anmeldeinformationen für dieses Konto werden zusammen mit der Anwendung gespeichert. Die Anwendung authentifiziert sich mit diesen gespeicherten Anmeldeinformationen bei Azure AD. Der Beispielcode unten stammt aus dem [Beispiel zu Daten im Besitz der App](https://github.com/guyinacube/PowerBI-Developer-Samples)

### <a name="access-token-with-service-principal"></a>Zugriffstoken mit Dienstprinzipal

Bei diesem Ansatz verwenden Sie einen [Dienstprinzipal](embed-service-principal.md), d.h. ein Token **nur für Anwendungen**. Die Anwendung authentifiziert sich mit einem Dienstprinzipal bei Azure AD. Der Beispielcode unten stammt aus dem [Beispiel zu Daten im Besitz der App](https://github.com/guyinacube/PowerBI-Developer-Samples)

#### <a name="embedservicecs"></a>EmbedService.cs

```csharp
var authenticationContext = new AuthenticationContext(AuthorityUrl);
       AuthenticationResult authenticationResult = null;
       if (AuthenticationType.Equals("MasterUser"))
       {
              // Authentication using master user credentials
              var credential = new UserPasswordCredential(Username, Password);
              authenticationResult = authenticationContext.AcquireTokenAsync(ResourceUrl, ApplicationId, credential).Result;
       }
       else
       {
             // Authentication using app credentials
             var credential = new ClientCredential(ApplicationId, ApplicationSecret);
             authenticationResult = await authenticationContext.AcquireTokenAsync(ResourceUrl, credential);
       }


m_tokenCredentials = new TokenCredentials(authenticationResult.AccessToken, "Bearer");
```

## <a name="next-steps"></a>Nächste Schritte

Nun verfügen Sie über das Zugriffstoken und können die Power BI-REST-API aufrufen, um Inhalte einzubetten. Weitere Informationen zum Einbetten von Inhalten finden Sie unter [Einbetten von Power BI-Inhalten](embed-sample-for-customers.md#embed-content-within-your-application).

Weitere Fragen? [Stellen Sie Ihre Frage in der Power BI-Community.](http://community.powerbi.com/)