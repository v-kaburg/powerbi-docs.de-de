---
title: Erstellen eines Datasets
description: "Exemplarische Vorgehensweise – Übertragen von Daten in ein Dataset per Push – Erstellen eines Datasets in Power BI"
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
ms.date: 08/10/2017
ms.author: asaxton
ms.openlocfilehash: 92409e447bf9bc32b83c22650d5b41aef6bb4414
ms.sourcegitcommit: 7517c068db806f12bb0b953e9a1bd4249ca12da5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/05/2018
---
# <a name="step-3-create-a-dataset-in-power-bi"></a>Schritt 3: Erstellen eines Datasets in Power BI
Dieser Artikel ist Teil einer Anleitung zum [Übertragen von Daten in ein Dataset per Push](walkthrough-push-data.md).

In **Schritt 2** von „Übertragen von Daten in ein Dataset per Push“ ([Abrufen eines Authentifizierungszugriffstokens](walkthrough-push-data-get-token.md)) haben Sie ein Token für die Authentifizierung bei **Azure AD** abgerufen. In diesem Schritt verwenden Sie das Token zum Aufrufen des Vorgangs [Dataset erstellen](https://msdn.microsoft.com/library/mt203562.aspx).

Um einen Aufruf einer anderen Ressource zu erstellen, verwenden Sie eine URL zum Bestimmen der Ressource und senden eine JSON-Zeichenfolge (JavaScript Object Notation), die das Dataset beschreibt, an die Power BI-Dienstressource. Eine REST-Ressource gibt den Teil des Power BI-Diensts an, mit dem Sie arbeiten möchten. Beim Übertragen von Daten per Push in das Dataset ist die Zielressource ein **Dataset**. Die URL zum Identifizieren eines Datasets lautet https://api.PowerBI.com/v1.0/myorg/datasets. Wenn Sie Daten per Push innerhalb einer Gruppe übertragen, lautet die URL https://api.PowerBI.com/v1.0/myorg/groups/{Gruppen_ID}/datasets.

Zum Authentifizieren eines Power BI-REST-Vorgangs fügen Sie das unter [Abrufen eines Authentifizierungszugriffstokens](walkthrough-push-data-get-token.md) abgerufene Token einem Anforderungsheader hinzu:

Durch Aufrufen des Vorgangs [Dataset erstellen](https://msdn.microsoft.com/library/mt203562.aspx) wird ein neues Dataset erstellt. 

![](media/walkthrough-push-data-create-dataset/powerbi-developer-create-dataset.png)

Im Folgenden wird das Erstellen eines Datasets in Power BI erläutert.

## <a name="create-a-dataset-in-power-bi"></a>Erstellen eines Datasets in Power BI
> [!NOTE]
> Wichtig ist, dass Sie zuvor die vorangegangenen Schritte der exemplarischen Vorgehensweise [Übertragen von Daten in ein Dataset per Push](walkthrough-push-data.md) ausgeführt haben.
> 
> 

1. Im Konsolenanwendungsprojekt, das Sie in [Schritt 2: Abrufen eines Authentifizierungszugriffstokens](walkthrough-push-data-get-token.md) erstellt haben, fügen Sie der Datei „Program.cs“ die Einträge **using System.Net;** und **using System.IO;** hinzu.
2. Fügen Sie „Program.cs“ den folgenden Code hinzu.
3. Führen Sie die Konsolen-App aus, und melden Sie sich bei Ihrem Power BI-Konto an. Daraufhin sollte im Konsolenfenster **Dataset erstellt** angezeigt werden. Sie können sich auch bei Power BI anmelden, um das neue Dataset anzuzeigen.

**Beispiel für das Übertragen von Daten in ein Dataset per Push**

Fügen Sie diesen Code der Datei „Program.cs“ hinzu.

* In „static void Main(string[]args)“:
  
    ```
    static void Main(string[] args)
    {
        //Get an authentication access token
        token = GetToken();
  
        //Create a dataset in Power BI
        CreateDataset();
    }
    ```
* Fügen Sie eine „CreateDataset()“-Methode hinzu:
  
    ```
    #region Create a dataset in Power BI
    private static void CreateDataset()
    {
        //TODO: Add using System.Net and using System.IO
  
        string powerBIDatasetsApiUrl = "https://api.powerbi.com/v1.0/myorg/datasets";
        //POST web request to create a dataset.
        //To create a Dataset in a group, use the Groups uri: https://api.PowerBI.com/v1.0/myorg/groups/{group_id}/datasets
        HttpWebRequest request = System.Net.WebRequest.Create(powerBIDatasetsApiUrl) as System.Net.HttpWebRequest;
        request.KeepAlive = true;
        request.Method = "POST";
        request.ContentLength = 0;
        request.ContentType = "application/json";
  
        //Add token to the request header
        request.Headers.Add("Authorization", String.Format("Bearer {0}", token));
  
        //Create dataset JSON for POST request
        string datasetJson = "{\"name\": \"SalesMarketing\", \"tables\": " +
            "[{\"name\": \"Product\", \"columns\": " +
            "[{ \"name\": \"ProductID\", \"dataType\": \"Int64\"}, " +
            "{ \"name\": \"Name\", \"dataType\": \"string\"}, " +
            "{ \"name\": \"Category\", \"dataType\": \"string\"}," +
            "{ \"name\": \"IsCompete\", \"dataType\": \"bool\"}," +
            "{ \"name\": \"ManufacturedOn\", \"dataType\": \"DateTime\"}" +
            "]}]}";
  
        //POST web request
        byte[] byteArray = System.Text.Encoding.UTF8.GetBytes(datasetJson);
        request.ContentLength = byteArray.Length;
  
        //Write JSON byte[] into a Stream
        using (Stream writer = request.GetRequestStream())
        {
            writer.Write(byteArray, 0, byteArray.Length);
  
            var response = (HttpWebResponse)request.GetResponse();
  
            Console.WriteLine(string.Format("Dataset {0}", response.StatusCode.ToString()));
  
            Console.ReadLine();
        }
    }
    #endregion
    ```

Im nächsten Schritt erfahren Sie, wie Sie ein [Dataset zum Hinzufügen von Zeilen zu einer Power BI-Tabelle abrufen](walkthrough-push-data-get-datasets.md).

Nachstehend finden Sie die [vollständige Codeliste](#code).

<a name="code"/>

## <a name="complete-code-listing"></a>Vollständige Codeliste
    using System;
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    using System.Net;
    using System.IO;

    namespace walkthrough_push_data
    {
        class Program
        {
            private static string token = string.Empty;

            static void Main(string[] args)
            {

                //Get an authentication access token
                token = GetToken();

                //Create a dataset in Power BI
                CreateDataset();

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


            #region Create a dataset in Power BI
            private static void CreateDataset()
            {
                //TODO: Add using System.Net and using System.IO

                string powerBIDatasetsApiUrl = "https://api.powerbi.com/v1.0/myorg/datasets";
                //POST web request to create a dataset.
                //To create a Dataset in a group, use the Groups uri: https://api.PowerBI.com/v1.0/myorg/groups/{group_id}/datasets
                HttpWebRequest request = System.Net.WebRequest.Create(powerBIDatasetsApiUrl) as System.Net.HttpWebRequest;
                request.KeepAlive = true;
                request.Method = "POST";
                request.ContentLength = 0;
                request.ContentType = "application/json";

                //Add token to the request header
                request.Headers.Add("Authorization", String.Format("Bearer {0}", token));

                //Create dataset JSON for POST request
                string datasetJson = "{\"name\": \"SalesMarketing\", \"tables\": " +
                    "[{\"name\": \"Product\", \"columns\": " +
                    "[{ \"name\": \"ProductID\", \"dataType\": \"Int64\"}, " +
                    "{ \"name\": \"Name\", \"dataType\": \"string\"}, " +
                    "{ \"name\": \"Category\", \"dataType\": \"string\"}," +
                    "{ \"name\": \"IsCompete\", \"dataType\": \"bool\"}," +
                    "{ \"name\": \"ManufacturedOn\", \"dataType\": \"DateTime\"}" +
                    "]}]}";

                //POST web request
                byte[] byteArray = System.Text.Encoding.UTF8.GetBytes(datasetJson);
                request.ContentLength = byteArray.Length;

                //Write JSON byte[] into a Stream
                using (Stream writer = request.GetRequestStream())
                {
                    writer.Write(byteArray, 0, byteArray.Length);

                    var response = (HttpWebResponse)request.GetResponse();

                    Console.WriteLine(string.Format("Dataset {0}", response.StatusCode.ToString()));

                    Console.ReadLine();
                }
            }
            #endregion
        }
    }


[Nächster Schritt >](walkthrough-push-data-get-datasets.md)

## <a name="next-steps"></a>Nächste Schritte
[Abrufen eines Datasets, um einer Power BI-Tabelle Zeilen hinzuzufügen](walkthrough-push-data-get-datasets.md)  
[Abrufen eines Authentifizierungszugriffstokens](walkthrough-push-data-get-token.md)  
[Create Dataset (Dataset erstellen)](https://msdn.microsoft.com/library/mt203562.aspx)  
[Übertragung von Daten in ein Power BI-Dashboard per Push](walkthrough-push-data.md)  
[Übersicht über Power BI-REST-API](overview-of-power-bi-rest-api.md)  
[Referenz zur Power BI-REST-API](https://msdn.microsoft.com/library/mt147898.aspx)  

Weitere Fragen? [Wenden Sie sich an die Power BI-Community](http://community.powerbi.com/)

