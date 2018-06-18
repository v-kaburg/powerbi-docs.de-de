---
title: Abrufen eines Authentifizierungszugriffstokens
description: Exemplarische Vorgehensweise zum Übertragen von Daten per Push – Abrufen eines Authentifizierungszugriffstokens
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-developer
ms.topic: conceptual
ms.date: 08/10/2017
ms.author: maghan
ms.openlocfilehash: 238d068e5083c8f46ac3299faddd4e0872f0654d
ms.sourcegitcommit: 8ee0ebd4d47a41108387d13a3bc3e7e2770cbeb8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2018
ms.locfileid: "34812627"
---
# <a name="step-2-get-an-authentication-access-token"></a>Schritt 2: Abrufen eines Authentifizierungszugriffstokens
Dieser Artikel ist Teil einer Anleitung zum [Übertragen von Daten in ein Dataset per Push](walkthrough-push-data.md).

In **Schritt 1** von „Übertragen von Daten in ein Dataset per Push“ haben Sie unter [Registrieren der App bei Azure AD](walkthrough-push-data-register-app-with-azure-ad.md) eine Client-App in Azure AD registriert. In diesem Schritt rufen Sie ein Authentifizierungszugriffstoken ab. Power BI-Apps sind in **Azure AD** integriert, um eine sichere Anmeldung und Autorisierung Ihrer App zu ermöglichen. Sie verwenden ein Token für die Authentifizierung bei **Azure AD** und den Zugriff auf Power BI-Ressourcen.

Nachstehend wird das Abrufen eines Authentifizierungszugriffstokens erläutert.

## <a name="get-an-authentication-access-token"></a>Abrufen eines Authentifizierungszugriffstokens
> **HINWEIS:** Wichtig ist, dass Sie zuvor die vorangegangenen Schritten der exemplarischen Vorgehensweise [Übertragen von Daten in ein Dataset per Push](walkthrough-push-data.md) ausgeführt haben.
> 
> 

1. Erstellen Sie in Visual Studio 2015 ein Projekt des Typs **Konsolenanwendung** .
2. Installieren Sie das [NuGet-Paket mit der Azure AD-Authentifizierungsbibliothek für .NET](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/). Verwenden Sie dieses Paket, um ein Authentifizierungssicherheitstoken in einer .NET-App abzurufen. Das Paket wird so installiert:
   
     a. Wählen Sie in Visual Studio 2015 **Tools** > **NuGet-Paket-Manager** > **Paket-Manager-Konsole**.
   
     b. Geben Sie der **Paket-Manager-Konsole**„Install-Package Microsoft.IdentityModel.Clients.ActiveDirectory-Version 2.21.301221612“ ein.
3. Fügen Sie den folgenden Code „class Program {...}“ hinzu.
4. Ersetzen Sie „{ClientID}“ durch die **Client-ID,** die Sie beim Registrieren der App erhalten haben. Siehe [Registrieren einer App in Azure AD](walkthrough-push-data-register-app-with-azure-ad.md).
5. Fügen Sie nach der Installation des Pakets „Microsoft.IdentityModel.Clients.ActiveDirectory“ **using Microsoft.IdentityModel.Clients.ActiveDirectory;** zur Datei „Program.cs“ hinzu.
6. Führen Sie die Konsolen-App aus, und melden Sie sich bei Ihrem Power BI-Konto an. Daraufhin sollte im Konsolenfenster eine Tokenzeichenfolge angezeigt werden.

**Beispielcode zum Abrufen des Authentifizierungssicherheitstokens**

Fügen Sie diesen Code „Program {...}“ hinzu.

* Eine Tokenvariable zum Aufrufen von Vorgängen:
  
  ```
  private static string token = string.Empty;
  
  static void Main(string[] args)
  {
  }
  ```
* In „static void Main(string[]args)“:
  
  ```
  static void Main(string[] args)
  {
    //Get an authentication access token
    token = GetToken();
  }
  ```
* Eine „GetToken()“-Methode hinzu:

```
       #region Get an authentication access token
       private static string GetToken()
       {
           // TODO: Install-Package Microsoft.IdentityModel.Clients.ActiveDirectory -Version 2.21.301221612
           // and add using Microsoft.IdentityModel.Clients.ActiveDirectory

           //The client id that Azure AD created when you registered your client app.
           string clientID = "{Client_ID}";

           //RedirectUri you used when you register your app.
           //For a client app, a redirect uri gives Azure AD more details on the application that it will authenticate.
           // You can use this redirect uri for your client app
           string redirectUri = "https://login.live.com/oauth20_desktop.srf";

           //Resource Uri for Power BI API
           string resourceUri = "https://analysis.windows.net/powerbi/api";

           //OAuth2 authority Uri
           string authorityUri = "https://login.windows.net/common/oauth2/authorize";

           //Get access token:
           // To call a Power BI REST operation, create an instance of AuthenticationContext and call AcquireToken
           // AuthenticationContext is part of the Active Directory Authentication Library NuGet package
           // To install the Active Directory Authentication Library NuGet package in Visual Studio,
           //  run "Install-Package Microsoft.IdentityModel.Clients.ActiveDirectory" from the nuget Package Manager Console.

           // AcquireToken will acquire an Azure access token
           // Call AcquireToken to get an Azure token from Azure Active Directory token issuance endpoint
           AuthenticationContext authContext = new AuthenticationContext(authorityUri);
           string token = authContext.AcquireToken(resourceUri, clientID, new Uri(redirectUri)).AccessToken;

           Console.WriteLine(token);
           Console.ReadLine();

           return token;
       }

       #endregion
```

Nach dem Abruf eines Authentifizierungstokens können Sie sämtliche Power BI-Vorgänge aufrufen. Im nächsten Schritt erfahren Sie, wie Sie den Vorgang [PostDataset](https://docs.microsoft.com/rest/api/power-bi/pushdatasets) aufrufen, um ein Dataset zum Übertragen von Daten in ein Dashboard per Push zu erstellen.

Im nächsten Schritt wird das [Erstellen eines Datasets in Power BI](walkthrough-push-data-create-dataset.md) erläutert.

Nachstehend finden Sie die [vollständige Codeliste](#code).

<a name="code"/>

## <a name="complete-code-listing"></a>Vollständige Codeliste
    using System;
    using Microsoft.IdentityModel.Clients.ActiveDirectory;

    namespace walkthrough_push_data
    {
        class Program
        {
            private static string token = string.Empty;

            static void Main(string[] args)
            {

                //Get an authentication access token
                token = GetToken();

            }

            #region Get an authentication access token
            private static string GetToken()
            {
                // TODO: Install-Package Microsoft.IdentityModel.Clients.ActiveDirectory -Version 2.21.301221612
                // and add using Microsoft.IdentityModel.Clients.ActiveDirectory

                //The client id that Azure AD created when you registered your client app.
                string clientID = "{Client_ID}";

                //RedirectUri you used when you register your app.
                //For a client app, a redirect uri gives Azure AD more details on the application that it will authenticate.
                // You can use this redirect uri for your client app
                string redirectUri = "https://login.live.com/oauth20_desktop.srf";

                //Resource Uri for Power BI API
                string resourceUri = "https://analysis.windows.net/powerbi/api";

                //OAuth2 authority Uri
                string authorityUri = "https://login.windows.net/common/oauth2/authorize";

                //Get access token:
                // To call a Power BI REST operation, create an instance of AuthenticationContext and call AcquireToken
                // AuthenticationContext is part of the Active Directory Authentication Library NuGet package
                // To install the Active Directory Authentication Library NuGet package in Visual Studio,
                //  run "Install-Package Microsoft.IdentityModel.Clients.ActiveDirectory" from the nuget Package Manager Console.

                // AcquireToken will acquire an Azure access token
                // Call AcquireToken to get an Azure token from Azure Active Directory token issuance endpoint
                AuthenticationContext authContext = new AuthenticationContext(authorityUri);
                string token = authContext.AcquireToken(resourceUri, clientID, new Uri(redirectUri)).AccessToken;

                Console.WriteLine(token);
                Console.ReadLine();

                return token;
            }

            #endregion

        }
    }


[Nächster Schritt >](walkthrough-push-data-create-dataset.md)

## <a name="next-steps"></a>Nächste Schritte
[Erstellen eines Datasets in Power BI](walkthrough-push-data-create-dataset.md)  
[Registrieren einer App in Azure AD](walkthrough-push-data-register-app-with-azure-ad.md)  
[NuGet-Paket mit der Azure AD-Authentifizierungsbibliothek für .NET](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/)  
[Übertragung von Daten in ein Power BI-Dataset per Push](walkthrough-push-data.md)  
[Übersicht über Power BI-REST-API](overview-of-power-bi-rest-api.md)  
[Referenz zur Power BI-REST-API](https://docs.microsoft.com/rest/api/power-bi/)  
Weitere Fragen? [Wenden Sie sich an die Power BI-Community](http://community.powerbi.com/)

