---
title: Registrieren einer App zum Einbetten von Power BI-Inhalten
description: Erfahren Sie, wie Sie eine Anwendung zum Einbetten von Power BI-Inhalten in Azure Active Directory registrieren können.
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-developer
ms.topic: conceptual
ms.date: 11/26/2018
ms.openlocfilehash: f65b1b2cc07b2b1cfb50200b62feeb8248abfdf4
ms.sourcegitcommit: fdb54145f9bc93b312409c15c603749f3a4a876e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2018
ms.locfileid: "52452842"
---
# <a name="register-an-azure-ad-app-to-embed-power-bi-content"></a>Registrieren einer Azure AD-App zum Einbetten von Power BI-Inhalten

Erfahren Sie, wie Sie eine Anwendung zum Einbetten von Power BI-Inhalten in Azure Active Directory (Azure AD) registrieren können.

Sie registrieren Ihre Anwendung bei Azure AD, um der Anwendung den Zugriff auf die Power BI-REST-APIs zu ermöglichen. Nach dem Registrieren Ihrer Anwendung können Sie eine Identität für Ihre Anwendung erstellen und Berechtigungen für Power BI-REST-Ressourcen angeben.

> [!IMPORTANT]
> Um eine Power BI-App zu registrieren, benötigen Sie einen [Azure Active Directory-Mandanten und einen Organisationsbenutzer](create-an-azure-active-directory-tenant.md). Wenn Sie sich mit einem Benutzer in Ihrem Mandanten noch nicht für Power BI registriert haben, wird die Registrierung der App nicht ordnungsgemäß abgeschlossen.

Die Registrierung Ihrer Anwendung kann auf zweierlei Weise erfolgen. Erstens mithilfe des [Power BI-App-Registrierungstools](https://dev.powerbi.com/apps/), zweitens direkt im Azure-Portal. Das Power BI-App-Registrierungstool ist die einfachste Option, da nur wenige Felder ausgefüllt werden müssen. Wenn Sie Änderungen an der App vornehmen möchten, verwenden Sie das Azure-Portal.

## <a name="register-with-the-power-bi-app-registration-tool"></a>Registrieren mithilfe des Power BI-App-Registrierungs-Tools

Registrieren Sie Ihre Anwendung in **Azure Active Directory**, um eine Identität für Ihre Anwendung einzurichten und Berechtigungen für Power BI-REST-Ressourcen anzugeben. Wenn Sie eine Anwendung registrieren, etwa eine Konsolenanwendung oder eine Website, erhalten Sie einen Bezeichner, mit dem sich die Anwendung gegenüber den Benutzern identifiziert, bei denen diese Berechtigungen anfordert.

So registrieren Sie Ihre Anwendung mit dem Power BI-App-Registrierungs-Tool:

1. Öffnen Sie die Seite [dev.powerbi.com/apps](https://dev.powerbi.com/apps).
2. Wählen Sie **Mit vorhandenem Konto anmelden** aus.
3. Geben Sie einen **App-Namen** an.
4. Die Auswahl des App-Typs hängt vom Typ der verwendeten Anwendung ab.

   * Verwenden Sie **Native App** für Apps, die auf Clientgeräten ausgeführt werden. Wählen Sie **Native App** aus, wenn Sie Inhalte für Ihre Kunden einbetten, unabhängig von der tatsächlich verwendeten Anwendung. Dies gilt sogar für Webanwendungen.
   * Verwenden Sie **Serverseitige Web-App** für Web-Apps oder Web-APIs.

5. Geben Sie einen Wert für **Umleitungs-URL** und **URL der Startseite** ein. Jede gültige URL kann als **Umleitungs-URL** verwendet werden.

    **Home Page URL** (URL der Startseite) steht nur zur Verfügung, wenn Sie **Server-side Web app** (Serverseitige Web-App) als Anwendungstyp ausgewählt haben.

    Für die Beispiele *embedding for your customers* (Einbetten für Ihre Kunden) und *integrate-dashboard-web-app* (Integrieren eines Dashboards in eine Web-App) lautet die **Umleitungs-URL** `http://localhost:13526/Redirect`. Für das Beispiel zu Berichten und Kacheln lautet die **Umleitungs-URL** `http://localhost:13526/`.
6. Wählen Sie die APIs für die Anwendung aus, die Zugriff hat. Weitere Informationen zu Power BI-Zugriffsberechtigungen finden Sie unter [Power BI-Berechtigungen](power-bi-permissions.md).

    ![App-Registrierungs-APIs](media/register-app/app-registration-apis.png)
7. Wählen Sie **App registrieren** aus.

    Anschließend erhalten Sie eine **Client-ID**, und bei Auswahl von **Server-side Web app** erhalten Sie ein **Clientgeheimnis**. Die **Client-ID** kann bei Bedarf später aus dem Azure-Portal abgerufen werden. Wenn Sie das **Clientgeheimnis** verlieren, müssen Sie im Azure-Portal ein neues erstellen.

8. Navigieren Sie zu Azure, um **Berechtigungen erteilen** auszuwählen.

   > [!Note]
   > Benutzer im Mandanten benötigen Zugriff auf **_Berechtigungen erteilen_**, um diesen Schritt auszuführen.

* Wechseln Sie zu Azure.
* Suchen Sie die **App Registrierungen**, und wählen Sie sie aus.
* Wählen Sie Ihre App aus.
* Wählen Sie **Einstellungen**aus.
* Wählen Sie **Erforderliche Berechtigungen** aus.
* Wählen Sie **Power BI-Dienst** aus, um die Berechtigungen zu überprüfen, die Sie auf der App-Registrierungswebsite ausgewählt haben.
* Wählen Sie **Berechtigungen erteilen** aus.

Jetzt können Sie die registrierte Anwendung als Teil Ihrer benutzerdefinierten Anwendung verwenden, um die Interaktion mit dem Power BI-Dienst zu implementieren.

> [!IMPORTANT]
> Wenn Sie Inhalte für Ihre Kunden einbetten, müssen Sie im Azure-Portal zusätzliche Berechtigungen konfigurieren. Weitere Informationen finden Sie unter [Anwenden von Berechtigungen für die Anwendung](#apply-permissions-to-your-application).

## <a name="register-with-the-azure-portal"></a>Registrieren beim Azure-Portal

Die andere Möglichkeit zum Registrieren Ihrer Anwendung besteht direkt im Azure-Portal. Führen Sie die folgenden Schritte aus, um Ihre Anwendung zu registrieren.

1. Akzeptieren Sie die [Nutzungsbedingungen für die Microsoft Power BI-API](https://powerbi.microsoft.com/api-terms).
2. Melden Sie sich beim [Azure-Portal](https://portal.azure.com) an.
3. Wählen Sie Ihren Azure AD-Mandanten aus, indem Sie Ihr Konto in der oberen rechten Ecke der Seite auswählen.
4. Wählen Sie im Navigationsbereich auf der linken Seite **Weitere Dienste**, dann **App-Registrierungen** unter **Sicherheit und Identität** und schließlich **Neue Anwendungsregistrierung aus**.

    ![Neue App-Registrierung](media/register-app/azuread-new-app-registration.png)
5. Folgen Sie den Anweisungen, und erstellen Sie eine neue Anwendung .

   * Geben Sie für Webanwendungen die Anmelde-URL an. Dabei handelt es sich um die Basis-URL Ihrer App, mit der sich die Benutzer anmelden können, z. B. `http://localhost:13526`.
   * Geben Sie für native Anwendungen einen **Umleitungs-URI** an, den Azure AD zur Rückgabe von Tokenantworten verwendet. Vergewissern Sie sich, dass Sie einen für Ihre Anwendung spezifischen Wert eingeben (z.B. `http://myapplication/Redirect`).

Weitere Informationen zum Registrieren von Anwendungen in Azure Active Directory finden Sie unter [Integrieren von Anwendungen in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/develop/active-directory-integrating-applications)

## <a name="how-to-get-the-client-id"></a>Abrufen der Client-ID

Beim Registrieren einer Anwendung erhalten Sie eine **Client-ID**.  Die **Client-ID** fordert die Benutzer auf, der Anwendung zu gestatten, sich bei ihnen zu identifizieren.

So rufen Sie eine Client-ID ab:

1. Melden Sie sich beim [Azure-Portal](https://portal.azure.com) an.
2. Wählen Sie Ihren Azure AD-Mandanten aus, indem Sie Ihr Konto in der oberen rechten Ecke der Seite auswählen.
3. Wählen Sie im Navigationsbereich auf der linken Seite **Weitere Dienste** und dann **App-Registrierungen** aus.
4. Wählen Sie die Anwendung aus, deren Client-ID Sie abrufen möchten, die Sie benötigen.
5. Die **Anwendungs-ID** wird als GUID aufgeführt. Dies ist die Client-ID der Anwendung.

    ![Client-ID, die als Anwendungs-ID in der App-Registrierung aufgelistet ist](media/register-app/powerbi-embedded-app-registration-client-id.png)

## <a name="apply-permissions-to-your-application-within-azure-ad"></a>Anwenden von Berechtigungen für die Anwendung in Azure AD

> [!IMPORTANT]
> Dieser Abschnitt gilt nur für Anwendungen, die **Inhalte für Ihre Organisation einbetten**.

Aktivieren Sie neben den Einstellungen auf der App-Registrierungsseite zusätzliche Berechtigungen für die Anwendung. Dies ist über das Azure AD-Portal oder programmgesteuert möglich.

Sie können sich entweder mit dem *Masterkonto* (zur Einbettung von Inhalten) oder einem globalen Administratorkonto anmelden.

### <a name="using-the-azure-ad-portal"></a>Über das Azure AD-Portal

1. Navigieren Sie zu [App-Registrierungen](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ApplicationsListBlade) im Azure-Portal, und wählen Sie die App aus, die Sie für die Einbettung verwenden.

    ![Über Azure AD registrierte Apps](media/register-app/powerbi-embedded-azuread-registered-apps.png)
2. Wählen Sie unter **API-Zugriff** die Option **Erforderliche Berechtigungen** aus.

    ![Erforderliche Berechtigungen für Azure AD-App](media/register-app/powerbi-embedded-azuread-app-required-permissions.png)

3. Wählen Sie unter **Erforderliche Berechtigungen** die Option **Power BI-Dienst (Power BI)** aus.

    ![App-Berechtigungen 3](media/register-app/powerbi-embedded-azuread-app-permissions03.png)

   > [!NOTE]
   > Wenn Sie die App direkt im Azure AD-Portal erstellt haben, ist der **Power BI-Dienst (Power BI)** möglicherweise nicht vorhanden. Wenn dies der Fall ist, wählen Sie **+ Add** (+ Hinzufügen) und dann **1 Select an API** (API auswählen). Klicken Sie auf **Power BI Service** (Power BI-Dienst) in der API-Liste, und klicken Sie dann auf **Select** (Auswählen).  Wenn **Power BI Service (Power BI)** (Power BI-Dienst (Power BI)) in **+ Add** (+ Hinzufügen) nicht verfügbar ist, registrieren Sie sich mit mindestens einem Benutzer bei Power BI.

4. Wählen Sie alle Berechtigungen unter **Delegierte Berechtigungen** aus. Wählen sie die Berechtigungen einzeln aus, um die Auswahl zu speichern. Wählen Sie **Speichern** aus, wenn Sie fertig sind.

    ![App-Berechtigungen 4](media/register-app/powerbi-embedded-azuread-app-permissions04.png)
5. Wählen Sie unter **Erforderliche Berechtigungen** die Option **Berechtigungen erteilen** aus.

    Für die Aktion **Berechtigungen erteilen** wird das *Hauptkonto* benötigt, damit keine Zustimmung von Azure AD abgefragt wird. Wenn es sich beim Konto, das diese Aktion ausführt, um das Konto eines globalen Administrators handelt, gewähren Sie allen Benutzern in der Organisation Berechtigungen für diese Anwendung. Wenn das Konto, das diese Aktion ausführt, das *Masterkonto* und nicht das Konto des globalen Administrators ist, gewähren Sie für diese Anwendung lediglich dem *Masterkonto* Berechtigungen.

    ![Gewähren von Berechtigungen im Dialogfeld „Erforderliche Berechtigungen“](media/register-app/powerbi-embedded-azuread-app-grant-permissions.png)

### <a name="applying-permissions-programmatically"></a>Programmgesteuertes Anwenden von Berechtigungen

1. Sie müssen die vorhandenen Dienstprinzipale (Benutzer) in Ihrem Mandanten abrufen. Informationen hierzu finden Sie im [Artikel zu Get servicePrincipal](https://developer.microsoft.com/en-us/graph/docs/api-reference/beta/api/serviceprincipal_get).

    Sie können die API *Get servicePrincipal* ohne {id} aufrufen. So werden alle Dienstprinzipale innerhalb des Mandanten abgerufen.
2. Suchen Sie nach einem Dienstprinzipal mit Ihrer App-Client-ID als **appId**-Eigenschaft.

3. Erstellen Sie einen neuen Serviceplan, wenn für Ihre App keiner vorhanden ist.

    ```json
    Post https://graph.microsoft.com/beta/servicePrincipals
    Authorization: Bearer ey..qw
    Content-Type: application/json
    {
    "accountEnabled" : true,
    "appId" : "{App_Client_ID}",
    "displayName" : "{App_DisplayName}"
    }
    ```

4. Weisen Sie der Power BI-API App-Berechtigungen zu.

   Wenn Sie einen vorhandenen Mandanten verwenden und nicht allen Mandantenbenutzern Berechtigungen erteilen möchten, können Sie einem bestimmten Benutzer Berechtigungen gewähren, indem Sie den Wert von **consentType** durch **Principal** ersetzen.

   Der Wert für **consentType** kann entweder auf **AllPrincipals** oder **Principal** festgelegt werden.

   * Nur Mandantenadministratoren können mit **AllPrincipals** im Namen aller Benutzer im Mandanten Berechtigungen erteilen.
   * Mit **Principal** werden Berechtigungen im Namen eines bestimmten Benutzers gewährt. In diesem Fall sollte dem Anforderungstext eine zusätzliche Eigenschaft hinzugefügt werden: *principalId={User_ObjectId}*.

     Die Konfiguration über *Berechtigungen erteilen* ist für das Masterkonto erforderlich, damit von Azure AD keine Zustimmung abgefragt wird. Dies ist bei einer nicht interaktiven Anmeldung nicht möglich.

     ```json
     Post https://graph.microsoft.com/beta/OAuth2PermissionGrants
     Authorization: Bearer ey..qw
     Content-Type: application/json
     {
     "clientId":"{Service_Plan_ID}",
     "consentType":"AllPrincipals",
     "resourceId":"c78a3685-1ce7-52cd-95f7-dc5aea8ec98e",
     "scope":"Dataset.ReadWrite.All Dashboard.Read.All Report.Read.All Group.Read Group.Read.All Content.Create Metadata.View_Any Dataset.Read.All Data.Alter_Any",
     "expiryTime":"2018-03-29T14:35:32.4943409+03:00",
     "startTime":"2017-03-29T14:35:32.4933413+03:00"
     }
     ```

    Die **resourceId** *c78a3685-1ce7-52cd-95f7-dc5aea8ec98e* ist nicht allgemeingültig, sondern abhängig vom Mandanten. Dieser Wert entspricht der objectId der Anwendung „Power BI-Dienst“ im AAD-Mandanten.

    Der Benutzer kann diesen Wert ganz einfach im Azure-Portal abrufen:
    1. https://portal.azure.com/#blade/Microsoft_AAD_IAM/StartboardApplicationsMenuBlade/AllApps
    2. Suchen Sie über das Suchfeld nach „Power BI-Dienst“.

5. Erteilen Sie Azure Active Directory (AAD) App-Berechtigungen.

   Der Wert für **consentType** kann entweder auf **AllPrincipals** oder **Principal** festgelegt werden.

   * Nur Mandantenadministratoren können mit **AllPrincipals** im Namen aller Benutzer im Mandanten Berechtigungen erteilen.
   * Mit **Principal** werden Berechtigungen im Namen eines bestimmten Benutzers gewährt. In diesem Fall sollte dem Anforderungstext eine zusätzliche Eigenschaft hinzugefügt werden: *principalId={User_ObjectId}*.

   Die Konfiguration über *Berechtigungen erteilen* ist für das Masterkonto erforderlich, damit von Azure AD keine Zustimmung abgefragt wird. Dies ist bei einer nicht interaktiven Anmeldung nicht möglich.

   ```json
   Post https://graph.microsoft.com/beta/OAuth2PermissionGrants
   Authorization: Bearer ey..qw
   Content-Type: application/json
   { 
   "clientId":"{Service_Plan_ID}",
   "consentType":"AllPrincipals",
   "resourceId":"61e57743-d5cf-41ba-bd1a-2b381390a3f1",
   "scope":"User.Read Directory.AccessAsUser.All",
   "expiryTime":"2018-03-29T14:35:32.4943409+03:00",
   "startTime":"2017-03-29T14:35:32.4933413+03:00"
   }
   ```

## <a name="next-steps"></a>Nächste Schritte

Sie haben Ihre Anwendung in Azure AD registriert und müssen jetzt Benutzer in der Anwendung authentifizieren. Weitere Informationen hierzu finden Sie unter [Authentifizieren von Benutzern und Abrufen eines Azure AD-Zugriffstokens für Ihre Power BI-App](get-azuread-access-token.md).

Weitere Fragen? [Stellen Sie Ihre Frage in der Power BI-Community.](http://community.powerbi.com/)
