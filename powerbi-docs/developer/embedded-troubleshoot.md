---
title: Problembehandlung bei Embedded-Anwendungen
description: In diesem Artikel werden einige häufige Probleme erläutert, die beim Einbetten von Inhalten aus Power BI auftreten können.
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-developer
ms.topic: conceptual
ms.date: 04/23/2018
ms.author: maghan
ms.openlocfilehash: fa142a34da003328ef509c319faf24d556023440
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2018
ms.locfileid: "34720809"
---
# <a name="troubleshooting-your-embedded-application"></a>Problembehandlung bei Embedded-Anwendungen

In diesem Artikel werden einige häufige Probleme erläutert, die beim Einbetten von Inhalten aus Power BI auftreten können.

## <a name="tools-for-troubleshooting"></a>Tools zur Problembehandlung

### <a name="fiddler-trace"></a>Ablaufverfolgung mit Fiddler

[Fiddler](http://www.telerik.com/fiddler) ist ein kostenloses Tool von Telerik, mit dem HTTP-Verkehr überwacht werden kann.  Sie können den Datenaustausch zwischen den Power BI-APIs und dem Clientcomputer verfolgen. So können Sie Fehler und ähnliche Informationen anzeigen.

![Ablaufverfolgung mit Fiddler](../includes/media/gateway-onprem-tshoot-tools-include/fiddler.png)

### <a name="f12-in-browser-for-front-end-debugging"></a>F12 im Browser zum Debuggen des Front-Ends

F12 startet das Entwicklerfenster im Browser. Dies ermöglicht es, den Netzwerkdatenverkehr und andere Informationen zu überprüfen.

![Debuggen im Browser mit F12](media/embedded-troubleshoot/browser-f12.png)

### <a name="extracting-error-details-from-power-bi-response"></a>Extrahieren von Fehlerdetails aus einer Power BI-Antwort

Dieser Codeausschnitt veranschaulicht, wie Sie die Fehlerdetails aus der HTTP-Ausnahme extrahieren:

```
public static string GetExceptionText(this HttpOperationException exc)
{
    var errorText = string.Format("Request: {0}\r\nStatus: {1} ({2})\r\nResponse: {3}",
    exc.Request.Content, exc.Response.StatusCode, (int)exc.Response.StatusCode, exc.Response.Content);
    if (exc.Response.Headers.ContainsKey("RequestId"))
    {
        var requestId = exc.Response.Headers["RequestId"].FirstOrDefault();
        errorText += string.Format("\r\nRequestId: {0}", requestId);
    }

    return errorText;
}
```
Es wird empfohlen, die Anforderungs-IDs (und die Fehlerdetails für die Problembehandlung) zu protokollieren.
Bitte geben Sie die Anforderungs-ID an, wenn Sie sich an den Microsoft-Support wenden.

## <a name="app-registration"></a>App-Registrierung

**Fehler bei der App-Registrierung**

In Fehlermeldungen im Azure-Portal oder auf der Registrierungsseite für die Power BI-App werden nicht ausreichende Berechtigungen erwähnt. Um eine Anwendung zu registrieren, müssen Sie Administrator im Azure AD-Mandanten sein oder Anwendungsregistrierungen müssen für Benutzer ohne Administratorrechte aktiviert sein.

**Power BI-Dienst wird beim Registrieren einer neuen App im Azure-Portal nicht aufgeführt**

Mindestens ein Benutzer muss bei Power BI registriert sein. Wenn der **Power BI-Dienst** nicht in der API-Liste aufgeführt wird, ist kein Benutzer für Power BI registriert.

## <a name="rest-api"></a>REST-API

**API-Aufruf gibt 401 zurück**

Zur genaueren Prüfung muss möglicherweise eine Fiddler-Überwachung ausgeführt werden. Möglicherweise fehlt der erforderliche Berechtigungsbereich für die registrierte Anwendung in Azure AD. Stellen Sie sicher, dass der erforderliche Bereich innerhalb der App-Registrierung für Azure AD im Azure-Portal vorhanden ist.

**API-Aufruf gibt 403 zurück**

Zur genaueren Prüfung muss möglicherweise eine Fiddler-Überwachung ausgeführt werden. Ein Fehler 403 kann verschiedene Ursachen haben.

* Die Benutzer haben die Anzahl der Einbettungstoken überschritten, die mit einer gemeinsam genutzten Kapazität generiert werden können. Sie müssen weitere Azure-Kapazitäten erwerben und den Arbeitsbereich dieser Kapazität zuweisen, um weitere Einbettungstoken generieren zu können. Weitere Informationen finden Sie unter [Einrichten von Power BI Embedded-Kapazität im Azure-Portal](https://docs.microsoft.com/azure/power-bi-embedded/create-capacity).
* Das Azure AD-Auth-Token ist abgelaufen.
* Der authentifizierte Benutzer ist kein Mitglied der Gruppe (App-Arbeitsbereich).
* Der authentifizierte Benutzer ist kein Administrator der Gruppe (App-Arbeitsbereich).
* Der Autorisierungsheader wird möglicherweise nicht ordnungsgemäß aufgeführt. Stellen Sie sicher, dass keine Rechtschreibfehler enthalten sind.

Das Back-End der Anwendung muss das Auth-Token möglicherweise vor dem Aufrufen von GenerateToken aktualisieren.

```
    GET https://wabi-us-north-central-redirect.analysis.windows.net/metadata/cluster HTTP/1.1
    Host: wabi-us-north-central-redirect.analysis.windows.net
    ...
    Authorization: Bearer eyJ0eXAiOi...
    ...
 
    HTTP/1.1 403 Forbidden
    ...
     
    {"error":{"code":"TokenExpired","message":"Access token has expired, resubmit with a new access token"}}
```

**Fehler beim Generieren des Tokens bei der Bereitstellung der effektiven Identität**

Bei GenerateToken kann bei Angabe einer effektiven Identität aus verschiedenen Gründen ein Fehler auftreten.

* Das Dataset unterstützt keine effektiven Identitäten.
* Der Benutzername wurde nicht angegeben.
* Die Rolle wurde nicht angegeben.
* DatasetId wurde nicht angegeben.
* Der Benutzer verfügt nicht über die richtigen Berechtigungen.

Um den Fehler zu ermitteln, versuchen Sie Folgendes:

* Führen Sie [get dataset](https://msdn.microsoft.com/library/mt784653.aspx) aus. Hat die Eigenschaft IsEffectiveIdentityRequired den Wert „true“?
* Der Benutzername ist für jede EffectiveIdentity obligatorisch.
* Wenn IsEffectiveIdentityRolesRequired „true“ ist, ist die Rolle erforderlich.
* DatasetId ist für jede EffectiveIdentity obligatorisch.
* Bei Analysis Services muss der Masterbenutzer auch Gatewayadministrator sein.

## <a name="data-sources"></a>Datenquellen

**ISV möchte unterschiedliche Anmeldeinformationen für die gleiche Datenquelle verwenden**

Eine Datenquelle kann für einen Masterbenutzer eine einzelne Kombination von Anmeldeinformation besitzen. Wenn Sie verschiedene Anmeldeinformationen verwenden möchten, erstellen Sie zusätzliche Masterbenutzer. Anschließend weisen Sie die anderen Anmeldeinformationen im Kontext jedes einzelnen Masterbenutzer zu, und betten sie mit dem Azure AD-Token des entsprechenden Benutzers ein.

## <a name="content-rendering"></a>Inhaltsrendering

**Fehler oder Timeout beim Rendering oder Verarbeiten eingebetteter Inhalte**

Stellen Sie sicher, dass das Einbettungs-Token nicht abgelaufen ist. Überprüfen Sie den Ablauf des Einbettungs-Tokens, und aktualisieren Sie dieses. Weitere Informationen finden Sie unter [Aktualisieren von Token mit dem JavaScript-SDK](https://github.com/Microsoft/PowerBI-JavaScript/wiki/Refresh-token-using-JavaScript-SDK-example).

**Bericht oder Dashboard wird nicht geladen**

Wenn der Benutzer den Bericht oder das Dashboard nicht finden kann, stellen Sie sicher, dass der Bericht oder das Dashboard auf powerbi.com ordnungsgemäß geladen wird. Der Bericht bzw. das Dashboard funktioniert in Ihrer Anwendung nicht, wenn es auf powerbi.com nicht geladen werden kann.

**Bericht oder Dashboard reagiert langsam**

Öffnen Sie die Datei in Power BI Desktop oder auf powerbi.com, und vergewissern Sie sich, dass die Leistung zufriedenstellend ist, um Probleme in Ihrer Anwendung oder mit den Einbettungs-APIs auszuschließen.

## <a name="onboarding-experience-tool-for-embedding"></a>Tool mit Onboardingfunktionen zur Einbettung

Sie können mit dem [Tool mit Onboardingfunktionen](https://aka.ms/embedsetup) schnell eine Beispielanwendung herunterladen. Anschließend können Sie Ihre Anwendung mit dem Beispiel vergleichen.

### <a name="prerequisites"></a>Voraussetzungen

Überprüfen Sie, ob Sie alle Voraussetzungen erfüllen, bevor Sie das Tool mit Onboardingfunktionen verwenden. Sie benötigen ein **Power BI Pro**-Konto und ein **Microsoft Azure**-Abonnement.

* Wenn Sie noch nicht bei **Power BI Pro** registriert sind, [registrieren Sie sich für eine kostenlose Testversion](https://powerbi.microsoft.com/en-us/pricing/), bevor Sie beginnen.
* Wenn Sie kein Azure-Abonnement besitzen, erstellen Sie ein [kostenloses Konto](https://azure.microsoft.com/free/?WT.mc_id=A261C142F), bevor Sie beginnen.
* Sie müssen einen eigenen [Azure Active Directory-Mandanten](create-an-azure-active-directory-tenant.md) eingerichtet haben.
* [Visual Studio](https://www.visualstudio.com/) muss installiert sein (Version 2013 oder höher).

### <a name="common-issues"></a>Häufige Probleme

Es gibt einige häufige Probleme, die auftreten können, wenn Sie das Tool mit Onboardingfunktionen testen:

#### <a name="using-the-embed-for-your-customers-sample-application"></a>Verwenden der Beispielanwendung „Einbetten für Ihre Kunden“

Wenn Sie mit **Einbetten für Ihre Kunden arbeiten**, speichern und entzippen Sie die Datei *PowerBI-Developer-Samples.zip*. Öffnen Sie anschließend den Ordner *PowerBI-Developer-Samples-master\App Owns Data*, und führen Sie die Datei *PowerBIEmbedded_AppOwnsData.sln* aus.

Wenn Sie **Berechtigungen erteilen** (der Schritt „Berechtigung erteilen“) ausführen, wird folgender Fehler ausgegeben:

    AADSTS70001: Application with identifier <client ID> was not found in the directory <directory ID>

Sie beheben das Problem, indem Sie das Popupfenster schließen, ein paar Sekunden warten, und es dann nochmal versuchen. Möglicherweise müssen Sie diese Aktion ein paar Mal durchführen. Der Fehler durch das Zeitintervall verursacht, das vom Registrierungsprozess der Anwendung bis zur Verfügbarkeit für externe APIs eingestellt ist.

Die folgende Fehlermeldung wird angezeigt, wenn Sie die Beispiel-App ausführen:

    Password is empty. Please fill password of Power BI username in web.config.

Dieser Fehler wird ausgelöst, da der einzige Wert, der nicht in die Beispielanwendung eingeführt wird, Ihr Benutzerkennwort ist. Öffnen Sie die Web.config-Datei in der Lösung, und geben Sie das Kennwort Ihres Benutzers in das Feld „pbiPassword“ ein.

#### <a name="using-the-embed-for-your-organization-sample-application"></a>Verwenden der Beispielanwendung „Einbetten für Ihre Organisation“

Wenn Sie mit **Einbetten für Ihre Organisation arbeiten**, speichern und entzippen Sie die Datei *PowerBI-Developer-Samples.zip*. Öffnen Sie dann den Ordner *PowerBI-Developer-Samples-master\User Owns Data\integrate-report-web-app*, und führen Sie die Datei *pbi-saas-embed-report.sln* aus.

Wenn Sie die Beispiel-App **Einbetten für Ihre Organisation** ausführen, wird folgender Fehler ausgegeben:

    AADSTS50011: The reply URL specified in the request does not match the reply URLs configured for the application: <client ID>

Das liegt daran, dass die Umleitungs-URL, die für die Webserveranwendung angegeben ist, sich von der URL des Beispiels unterscheidet. Wenn Sie die Beispielanwendung registrieren möchten, verwenden Sie also *http://localhost:13526/* als Umleitungs-URL.

Wenn Sie die registrierte Anwendung bearbeiten möchten, lernen Sie, wie Sie die [mit AAD registrierte Anwendung](https://docs.microsoft.com/azure/active-directory/develop/active-directory-integrating-applications#updating-an-application) bearbeiten, damit die Anwendung Zugriff auf die Web-APIs bereitstellen kann.

Wenn Sie Ihr Power BI-Benutzerprofil oder Ihre Daten bearbeiten möchten, lernen Sie, wie Sie Ihre [Power BI-Daten](https://docs.microsoft.com/en-us/power-bi/service-basic-concepts) bearbeiten können.

Weitere Informationen finden Sie unter [Häufig gestellte Fragen zu Power BI Embedded](embedded-faq.md).

Weitere Fragen? [Wenden Sie sich an die Power BI-Community](http://community.powerbi.com/)