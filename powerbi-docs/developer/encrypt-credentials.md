---
title: Verschlüsseln von Anmeldeinformationen
description: 'Exemplarische Vorgehensweise: Verschlüsseln von Anmeldeinformationen für lokale Gateway-Datenquellen'
author: mahirdiab
ms.author: madia
manager: eligr
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 02/04/2019
ms.openlocfilehash: 0952867ef9660a9dab6fc532df055ed619bf47fc
ms.sourcegitcommit: 81ba3572531cbe95ea0b887b94e91f94050f3129
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2019
ms.locfileid: "66750922"
---
# <a name="encrypt-credentials"></a>Verschlüsseln von Anmeldeinformationen

Wenn Sie [Create Datasource](https://docs.microsoft.com/rest/api/power-bi/gateways/createdatasource) (Datenquelle erstellen) oder [Update Datasource](https://docs.microsoft.com/rest/api/power-bi/gateways/updatedatasource) (Datenquelle aktualisieren) in einem **lokalen Unternehmensgateway** mit der [Power BI-REST-API](https://docs.microsoft.com/rest/api/power-bi/) aufrufen, müssen die Werte für die Anmeldeinformationen mithilfe des öffentlichen Schlüssels des Gateways verschlüsselt werden.

Im folgenden Codebeispiel wird gezeigt, wie die Anmeldeinformationen in .NET verschlüsselt werden.

Anmeldeinformationen, die an die EncodeCredentials-Methode übergeben werden, sollten je nach Anmeldeinformationstyp eines der folgenden Formate aufweisen:

**Einfache/Windows-Anmeldeinformationen**

```csharp
var credentials = "{\"credentialData\":[{\"name\":\"username\", \"value\":\"john\"},{\"name\":\"password\", \"value\":\"*****\"}]}";
```

**Wichtige Anmeldeinformationen**

```csharp
var credentials = "{\"credentialData\":[{\"name\":\"key\", \"value\":\"ec....LA=\"}]}";
```

**OAuth2-Anmeldeinformationen**

```csharp
var credentials = "{\"credentialData\":[{\"name\":\"accessToken\", \"value\":\"eyJ0....fwtQ\"}]}";
```

**Anonyme Anmeldeinformationen**

```csharp
var credentials = "{\"credentialData\":\"\"}";
```

**Verschlüsseln von Anmeldeinformationen**

```csharp
public static class AsymmetricKeyEncryptionHelper
{

    private const int SegmentLength = 85;
    private const int EncryptedLength = 128;

    public static string EncodeCredentials(string credentials, string publicKeyExponent, string publicKeyModulus)
    {
        using (RSACryptoServiceProvider rsa = new RSACryptoServiceProvider(EncryptedLength * 8))
        {
            var parameters = rsa.ExportParameters(false);
            parameters.Exponent = Convert.FromBase64String(publicKeyExponent);
            parameters.Modulus = Convert.FromBase64String(publicKeyModulus);
            rsa.ImportParameters(parameters);
            return Encrypt(credentials, rsa);
        }
    }

    private static string Encrypt(string plainText, RSACryptoServiceProvider rsa)
    {
        byte[] plainTextArray = Encoding.UTF8.GetBytes(plainText);

        // Split the message into different segments, each segment's length is 85. So the result may be 85,85,85,20.
        bool hasIncompleteSegment = plainTextArray.Length % SegmentLength != 0;

        int segmentNumber = (!hasIncompleteSegment) ? (plainTextArray.Length / SegmentLength) : ((plainTextArray.Length / SegmentLength) + 1);

        byte[] encryptedData = new byte[segmentNumber * EncryptedLength];
        int encryptedDataPosition = 0;

        for (var i = 0; i < segmentNumber; i++)
        {
            int lengthToCopy;

            if (i == segmentNumber - 1 && hasIncompleteSegment)
                lengthToCopy = plainTextArray.Length % SegmentLength;
            else
                lengthToCopy = SegmentLength;

            var segment = new byte[lengthToCopy];

            Array.Copy(plainTextArray, i * SegmentLength, segment, 0, lengthToCopy);

            var segmentEncryptedResult = rsa.Encrypt(segment, true);

            Array.Copy(segmentEncryptedResult, 0, encryptedData, encryptedDataPosition, segmentEncryptedResult.Length);

            encryptedDataPosition += segmentEncryptedResult.Length;
        }

        return Convert.ToBase64String(encryptedData);
    }
}
```