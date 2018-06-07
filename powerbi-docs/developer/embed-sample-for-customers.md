---
title: Einbetten von Power BI-Inhalten in eine Anwendung für Ihre Kunden
description: Hier erfahren Sie, wie Sie mit den Power BI-APIs einen Bericht, ein Dashboard oder eine Kachel für Ihre Kunden in eine Web-App integrieren bzw. einbetten.
author: markingmyname
ms.author: maghan
ms.date: 05/25/2018
ms.topic: tutorial
ms.service: powerbi
ms.component: powerbi-developer
ms.custom: mvc
manager: kfile
ms.openlocfilehash: ae683dfbeb7b3848575ab766c33b695eb823d497
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2018
ms.locfileid: "34721039"
---
# <a name="tutorial-embed-a-power-bi-report-dashboard-or-tile-into-an-application-for-your-customers"></a>Tutorial: Einbetten von Power BI-Berichten, -Dashboards oder -Kacheln in eine Anwendung für Ihre Kunden
Mit **Power BI Embedded in Azure** können Sie mit **App Owns Data** (App ist Besitzer der Daten) Berichte, Dashboards oder Kacheln in eine Anwendung einbetten. Bei **App Owns Data** verwendet eine Anwendung Power BI als eingebettete Analyseplattform. Dies ist normalerweise in einem Szenario mit einem **ISV-Entwickler** der Fall. **ISV-Entwickler** können Power BI-Inhalt erstellen, der vollständig integrierte und interaktive Berichte, Dashboards oder Kacheln in einer Anwendung anzeigt, ohne dass die Benutzer der Anwendung über eine Power BI-Lizenz verfügen oder wissen müssen, dass Power BI im Hintergrund ausgeführt wird. Dieses Tutorial veranschaulicht, wie Sie einen Bericht in eine Anwendung integrieren, indem Sie das **Power BI** .NET SDK sowie die **Power BI**-JavaScript-API verwenden, wenn Sie **Power BI Embedded in Azure** für Ihre Kunden mit **App Owns Data** nutzen.

In diesem Tutorial erhalten Sie Informationen zu den folgenden Vorgängen:
>[!div class="checklist"]
>* Registrieren einer Anwendung in Azure
>* Einbetten eines Power BI-Berichts in eine App

## <a name="prerequisites"></a>Voraussetzungen
Sie benötigen ein **Power BI Pro-Konto** als **Hauptkonto** und ein **Microsoft Azure**-Abonnement.

* Wenn Sie noch nicht bei **Power BI Pro** registriert sind, [registrieren Sie sich für eine kostenlose Testversion](https://powerbi.microsoft.com/en-us/pricing/), bevor Sie beginnen.
* Wenn Sie kein Azure-Abonnement besitzen, erstellen Sie ein [kostenloses Konto](https://azure.microsoft.com/free/?WT.mc_id=A261C142F), bevor Sie beginnen.
* Sie müssen einen eigenen [Azure Active Directory-Mandanten](create-an-azure-active-directory-tenant.md) eingerichtet haben.
* [Visual Studio](https://www.visualstudio.com/) muss installiert sein (Version 2013 oder höher).

## <a name="setup-your-embedded-analytics-development-environment"></a>Einrichten der Entwicklungsumgebung für eingebettete Analysen

Bevor Sie mit dem Einbetten von Dashboards, Berichten und Kacheln in Ihre Anwendung beginnen, müssen Sie sicherstellen, dass Ihre Umgebung für Einbettungsvorgänge eingerichtet ist. Im Rahmen des Setups müssen Sie folgende Aktionen ausführen.

Sie können sich mit dem [Tool mit Onboardingfunktionen zur Einbettung](https://aka.ms/embedsetup/AppOwnsData) vertraut machen, damit Sie schnell beginnen und eine Beispielanwendung herunterladen können, die Ihnen beim Erstellen einer Umgebung und beim Einbetten eines Berichts helfen kann.

Wenn Sie jedoch die Umgebung manuell einrichten möchten, können Sie weiter unten fortfahren.
### <a name="register-an-application-in-azure-active-directory-azure-ad"></a>Registrieren einer Anwendung in Azure Active Directory (Azure AD)

Sie registrieren Ihre Anwendung in Azure Active Directory, damit die Anwendung auf die Power BI-REST-APIs zugreifen kann. Auf diese Weise können Sie eine Identität für Ihre Anwendung erstellen und Berechtigungen für Power BI-REST-Ressourcen angeben.

1. Akzeptieren Sie die [Nutzungsbedingungen für die Microsoft Power BI-API](https://powerbi.microsoft.com/api-terms).

2. Melden Sie sich beim [Azure-Portal](https://portal.azure.com) an.
 
    ![Hauptfenster des Azure-Portals](media/embed-sample-for-customers/embed-sample-for-customers-002.png)

3. Wählen Sie im Navigationsbereich auf der linken Seite **Alle Dienste**, dann **App-Registrierungen** und schließlich **Neue Anwendungsregistrierung** aus.
   
    ![App-Registrierung, Suche](media/embed-sample-for-customers/embed-sample-for-customers-003.png)</br>
    ![Neue App-Registrierung](media/embed-sample-for-customers/embed-sample-for-customers-004.png)

4. Folgen Sie den Anweisungen, und erstellen Sie eine neue Anwendung . Für „App Owns Data“ müssen Sie **Nativ** als Anwendungstyp verwenden. Sie müssen auch einen **Umleitungs-URI** angeben, den **Azure AD** zur Rückgabe von Tokenantworten verwendet. Geben Sie einen für Ihre Anwendung spezifischen Wert ein, z.B. http://localhost:13526/redirect).

    ![App erstellen](media/embed-sample-for-customers/embed-sample-for-customers-005.png)

### <a name="apply-permissions-to-your-application-within-azure-active-directory"></a>Anwenden von Berechtigungen auf die Anwendung in Azure Active Directory

Sie müssen neben den Einstellungen auf der App-Registrierungsseite zusätzliche Berechtigungen für die Anwendung aktivieren. Sie müssen mit dem *Hauptkonto* angemeldet sein, das zum Einbetten verwendet wird und ein globales Administratorkonto sein muss.

### <a name="use-the-azure-active-directory-portal"></a>Verwenden des Azure Active Directory-Portals

1. Navigieren Sie zu [App-Registrierungen](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ApplicationsListBlade) im Azure-Portal, und wählen Sie die App aus, die Sie für die Einbettung verwenden.
   
    ![Auswählen einer App](media/embed-sample-for-customers/embed-sample-for-customers-006.png)

2. Wählen Sie **Einstellungen** und danach unter **API-Zugriff** die Option **Erforderliche Berechtigungen** aus.
   
    ![Erforderliche Berechtigungen](media/embed-sample-for-customers/embed-sample-for-customers-008.png)

3. Wählen Sie **Windows Azure Active Directory** aus, und stellen Sie sicher, dass **Hiermit greifen Sie als angemeldeter Benutzer auf das Verzeichnis zu** ausgewählt ist. Wählen Sie **Speichern**.
   
    ![Microsoft Azure AD-Berechtigungen](media/embed-sample-for-customers/embed-sample-for-customers-011.png)

4. Wählen Sie **Hinzufügen**.

    ![Berechtigungen hinzufügen](media/embed-sample-for-customers/embed-sample-for-customers-012.png)

5. Klicken Sie auf **API auswählen**.

    ![API-Zugriff hinzufügen](media/embed-sample-for-customers/embed-sample-for-customers-013.png)

6. Klicken Sie auf **Power BI-Dienst** und dann auf **Auswählen**.

    ![Power BI-Dienste auswählen](media/embed-sample-for-customers/embed-sample-for-customers-014.png)

7. Wählen Sie alle Berechtigungen unter **Delegierte Berechtigungen** aus. Sie müssen sie einzeln auswählen, um die Auswahl zu speichern. Wählen Sie **Speichern** aus, wenn Sie fertig sind.
   
    ![Delegierte Berechtigungen auswählen](media/embed-sample-for-customers/embed-sample-for-customers-015.png)

8. Wählen Sie unter **Erforderliche Berechtigungen** die Option **Berechtigungen erteilen** aus.
   
    Die Aktion **Berechtigungen erteilen** wird für das *Hauptkonto* benötigt, damit keine Zustimmung von Azure AD abgefragt wird. Wenn es sich beim Konto, das diese Aktion ausführt, um das Konto eines globalen Administrators handelt, gewähren Sie allen Benutzern in der Organisation Berechtigungen für diese Anwendung. Wenn das Konto, unter dem diese Aktion ausgeführt ist, das *Hauptkonto* und nicht das Konto des globalen Administrators ist, gewähren Sie für diese Anwendung lediglich dem *Hauptkonto* Berechtigungen.
   
    ![Gewähren von Berechtigungen im Dialogfeld „Erforderliche Berechtigungen“](media/embed-sample-for-customers/embed-sample-for-customers-016.png)

## <a name="setup-your-power-bi-environment"></a>Einrichten Ihrer Power BI-Umgebung

### <a name="create-an-app-workspace"></a>Erstellen eines App-Arbeitsbereichs

Wenn Sie Berichte, Dashboards oder Kacheln für Ihre Kunden einbetten, müssen Sie Ihre Inhalte in einem App-Arbeitsbereich platzieren. Das *Hauptkonto* muss Administrator des App-Arbeitsbereichs sein.

1. Erstellen Sie zunächst den Arbeitsbereich. Wählen Sie **Arbeitsbereiche** > **App-Arbeitsbereich erstellen** aus. Hier werden die Inhalte abgelegt, auf die Ihre Anwendung zugreifen muss.

    ![Arbeitsbereich erstellen](media/embed-sample-for-customers/embed-sample-for-customers-020.png)

2. Benennen Sie den Arbeitsbereich. Wenn die entsprechende **Arbeitsbereichs-ID** nicht verfügbar ist, geben Sie eine eindeutige ID ein. Diese wird der Name der App sein.

    ![Arbeitsbereich benennen](media/embed-sample-for-customers/embed-sample-for-customers-021.png)

3. Sie können einige Optionen festlegen. Wenn Sie **Öffentlich** auswählen, können die Inhalte des Arbeitsbereichs von jedem Benutzer in der Organisation angezeigt werden. **Privat** bedeutet hingegen, dass die Inhalte des Arbeitsbereichs nur von dessen Mitgliedern angezeigt werden können.

    ![Privat/Öffentlich](media/embed-sample-for-customers/embed-sample-for-customers-022.png)

    Sie können die Einstellung „Öffentlich“ bzw. „Privat“ einer Gruppe nach deren Erstellung nicht mehr ändern.

4. Sie können auch auswählen, ob Mitglieder Inhalte **bearbeiten** können oder **schreibgeschützten** Zugriff haben.

    ![Mitglieder hinzufügen](media/embed-sample-for-customers/embed-sample-for-customers-023.png)

5. Fügen Sie E-Mail-Adressen von Personen hinzu, die Zugriff auf den Arbeitsbereich haben sollen, und wählen Sie **Hinzufügen** aus. Sie können keine Gruppenaliase, sondern nur einzelne Personen hinzufügen.

6. Legen Sie für jede Person fest, ob sie Mitglied oder Administrator ist. Administratoren können den Arbeitsbereich selbst bearbeiten und weitere Mitglieder hinzufügen. Mitglieder können den Inhalt des Arbeitsbereichs bearbeiten, es sei denn, sie haben schreibgeschützten Zugriff. Sowohl Administratoren als auch Mitglieder können die App veröffentlichen.

Jetzt können Sie den neuen Arbeitsbereich anzeigen. Der Arbeitsbereich wird in Power BI erstellt und geöffnet. Er wird in der Liste der Arbeitsbereiche angezeigt, deren Mitglied Sie sind. Da Sie Administrator sind, können Sie die Auslassungspunkte (...) auswählen, um zurückzukehren, und Änderungen vornehmen, neue Mitglieder hinzufügen oder deren Berechtigungen ändern.

   ![Neuer Arbeitsbereich](media/embed-sample-for-customers/embed-sample-for-customers-025.png)

### <a name="create-and-publish-your-reports"></a>Erstellen und Veröffentlichen von Berichten

Sie können Ihre Berichte und Datasets mit Power BI Desktop erstellen und diese Berichte dann in einem App-Arbeitsbereich veröffentlichen. Der Endbenutzer, der die Berichte veröffentlicht, muss über eine Power BI Pro-Lizenz verfügen, damit er einen App-Arbeitsbereich veröffentlichen kann.

1. Laden Sie das Beispiel von GitHub herunter: [Blog-Demo](https://github.com/Microsoft/powerbi-desktop-samples).

    ![Beispiel für Bericht](media/embed-sample-for-customers/embed-sample-for-customers-026-1.png)

2. Öffnen Sie den PBIX-Beispielbericht in **Power BI Desktop**.

   ![Power BI Desktop-Bericht](media/embed-sample-for-customers/embed-sample-for-customers-027.png)

3. Veröffentlichen Sie den Bericht im **App-Arbeitsbereich**.

   ![Power BI Desktop-Bericht](media/embed-sample-for-customers/embed-sample-for-customers-028.png)

    Jetzt können Sie den Bericht online im Power BI-Dienst anzeigen.

   ![Power BI Desktop-Bericht](media/embed-sample-for-customers/embed-sample-for-customers-029.png)

## <a name="embed-your-content"></a>Einbetten der Inhalte

Damit Kunden Einbettungen in der Anwendung vornehmen können, müssen Sie ein **Zugriffstoken** für Ihr Hauptkonto von **Azure AD** besorgen. Es ist erforderlich, dass Sie zunächst ein [Azure AD-Zugriffstoken](get-azuread-access-token.md#access-token-for-non-power-bi-users-app-owns-data) für Ihre Power BI-Anwendung mit App Owns Data besorgen, bevor Sie Aufrufe an die Power BI-API durchführen.

Führen Sie die folgenden Schritte durch, um Ihren Inhalt in eine Beispielanwendung zu implementieren.

1. Laden Sie das [App Owns Data](https://github.com/Microsoft/PowerBI-Developer-Samples)-Beispiel aus GitHub herunter, um zu beginnen.

    ![App Owns Data-Anwendungsbeispiel](media/embed-sample-for-customers/embed-sample-for-customers-026.png)

2. Öffnen Sie die Datei „Web.config“ in der Beispielanwendung. Damit die Anwendung erfolgreich ausgeführt werden kann, müssen Sie 5 Felder ausfüllen: die **clientID**, die **groupId**, die **reportId**, der **pbiUsername** und das **pbiPassword**.

      ![Web.config-Datei](media/embed-sample-for-customers/embed-sample-for-customers-030.png)

    * Geben Sie für **clientId** die **Anwendungs-ID** aus **Azure** an. Die Anwendung identifiziert sich mithilfe der **clientId** bei den Benutzern, von denen Sie Berechtigungen anfordern. Um die **clientId** abzurufen, führen Sie folgende Schritte aus:

    1. Melden Sie sich beim [Azure-Portal](https://portal.azure.com) an.

        ![Hauptfenster des Azure-Portals](media/embed-sample-for-customers/embed-sample-for-customers-002.png)

    2. Wählen Sie im Navigationsbereich auf der linken Seite **Alle Dienste** und dann **App-Registrierungen** aus.

        ![App-Registrierung, Suche](media/embed-sample-for-customers/embed-sample-for-customers-003.png)
    3. Wählen Sie die Anwendung aus, für die Sie die **clientId** abrufen möchten.

        ![Auswählen einer App](media/embed-sample-for-customers/embed-sample-for-customers-006.png)

    4. Sie sollten eine **Anwendungs-ID** sehen, die als GUID aufgeführt ist. Verwenden Sie diese **Anwendungs-ID** als **clientId** für die Anwendung.

        ![clientId](media/embed-sample-for-customers/embed-sample-for-customers-007.png)     

    * Geben Sie als **groupId** die **App-Arbeitsbereichs-GUID** aus Power BI an.

        ![groupId](media/embed-sample-for-customers/embed-sample-for-customers-031.png)

    * Geben Sie als **reportId** die **Berichts-GUID** aus Power BI an.

        ![reportId](media/embed-sample-for-customers/embed-sample-for-customers-032.png)    

    * Geben Sie als **pbiUsername** das Power BI-Hauptbenutzerkonto an.
    * Geben Sie als **pbiPassword** das Kennwort für das Power BI-Hauptbenutzerkonto an.

3. Führen Sie die Anwendung aus!

    Wählen Sie zunächst in **Visual Studio** die Option **Ausführen** aus.

    ![Ausführen der Anwendung](media/embed-sample-for-customers/embed-sample-for-customers-033.png)

    Wählen Sie dann **Bericht einbetten** aus. Wählen Sie die gewünschte Option in der Anwendung aus, je nachdem, mit welchem Inhalt Sie testen möchten: Berichte, Dashboards oder Kacheln.

    ![Inhalt auswählen](media/embed-sample-for-customers/embed-sample-for-customers-034.png)
 
    Jetzt können Sie den Bericht in der Beispielanwendung anzeigen.

    ![Anwendung anzeigen](media/embed-sample-for-customers/embed-sample-for-customers-035.png)

## <a name="move-to-production"></a>In die Produktionsphase wechseln

Wenn Sie mit dem Entwickeln Ihrer Anwendung fertig sind, sollten Sie Ihren App-Arbeitsbereich durch dedizierte Kapazität absichern. Dedizierte Kapazität ist erforderlich, um in die Produktionsphase wechseln zu können.

### <a name="create-a-dedicated-capacity"></a>Erstellen einer dedizierten Kapazität
Wenn Sie eine dedizierte Kapazität erstellen, können Sie Ihrem Kunden eine dedizierte Ressource zuweisen. Arbeitsbereiche, die keiner dedizierten Kapazität zugeordnet sind, werden in einer gemeinsam genutzten Kapazität ausgeführt. Sie können mit [der dedizierten Power BI Embedded-Kapazität](https://docs.microsoft.com/azure/power-bi-embedded/create-capacity) in Azure eine dedizierte Kapazität erstellen.

>[!Note]
>Da Einbettungstokens mit PRO-Lizenzen nur für Bereitstellungen und das Testen von Bereitstellungen vorgesehen sind, ist die Anzahl von Einbettungstokens limitiert, die ein Power BI-Hauptkonto generieren kann. Sie müssen eine dedizierte Kapazität erwerben, um Einbettungen in einer Produktionsumgebung vornehmen zu können. Sie können mit einer dedizierten Kapazität so viele eingebettete Token wie Sie möchten generieren. Wechseln Sie zu [Get Available Features](https://msdn.microsoft.com/library/mt846473.aspx) (Verfügbare Features abrufen), um den Nutzungswert zu überprüfen, der die aktuelle Nutzung der Einbettung in Prozent angibt.
>

### <a name="assign-app-workspace-to-dedicated-capacity"></a>Zuweisen des App-Arbeitsbereichs zur dedizierten Kapazität

Sobald Sie dedizierte Kapazität erstellt haben, weisen Sie der dedizierten Kapazität den App-Arbeitsbereich zu. Führen Sie die folgenden Schritte durch, um den Vorgang abzuschließen.

1. Erweitern Sie im **Power BI-Dienst** Arbeitsbereiche, und klicken Sie auf die Auslassungspunkte neben dem Arbeitsbereich, in den Sie Ihren Inhalt einbetten. Klicken Sie dann auf **Arbeitsbereich bearbeiten**.

    ![Arbeitsbereich bearbeiten](media/embed-sample-for-customers/embed-sample-for-customers-036.png)

2. Erweitern Sie **Erweitert**, aktivieren Sie **Dedizierte Kapazität**, und wählen Sie die dedizierte Kapazität aus, die Sie erstellt haben. Klicken Sie auf **Speichern**.

    ![Zuweisen der dedizierten Kapazität](media/embed-sample-for-customers/embed-sample-for-customers-024.png)

Ein komplettes Beispiel für die Verwendung der JavaScript-API ist im [Playground-Tool](https://microsoft.github.io/PowerBI-JavaScript/demo) verfügbar. Dies ist eine schnelle Möglichkeit, verschiedene Arten von Power BI Embedded-Beispielen auszuprobieren. Weitere Informationen zur JavaScript-API finden Sie auch auf der [Power BI-JavaScript-Wikiseite](https://github.com/Microsoft/powerbi-javascript/wiki).

Wenn Sie weitere Fragen zu Power BI Embedded haben, besuchen Sie die Seite mit den [häufig gestellten Fragen](embedded-faq.md).  Wenn Probleme mit Power Bi Embedded in Ihrer Anwendung auftreten, besuchen Sie die Seite für die [Problembehandlung](embedded-troubleshoot.md).

Weitere Fragen? [Stellen Sie Ihre Frage in der Power BI-Community.](http://community.powerbi.com/)