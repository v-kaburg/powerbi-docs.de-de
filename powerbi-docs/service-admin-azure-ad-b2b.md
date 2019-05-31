---
title: Verteilen von Inhalten an externe Gastbenutzer mit Azure AD B2B
description: Power BI ist in Azure Active Directory Business-to-Business (Azure AD B2B) integriert, um die sichere Verteilung von Power BI-Inhalten an Gastbenutzer außerhalb der Organisation zu ermöglichen.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 04/25/2019
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: 2d1e9e32fcec67647bb75ac14ed872e6c51fef96
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2019
ms.locfileid: "65101714"
---
# <a name="distribute-power-bi-content-to-external-guest-users-with-azure-ad-b2b"></a>Verteilen von Power BI-Inhalten an externe Gastbenutzer mit Azure AD B2B

Power BI ist in Azure Active Directory Business-to-Business (Azure AD B2B) integriert, um die sichere Verteilung von Power BI-Inhalten an Gastbenutzer außerhalb Ihrer Organisation zu ermöglichen, während Sie weiterhin die Kontrolle über die internen Daten zu behalten.  

Des Weiteren können Sie Gastbenutzern außerhalb Ihrer Organisation das Bearbeiten und Verwalten von Inhalten in Ihrer Organisation ermöglichen.

## <a name="enable-access"></a>Aktivieren des Zugriffs

Aktivieren Sie die [Inhalte für externe Benutzer freigeben,](service-admin-portal.md#export-and-sharing-settings) -Funktion in der Power BI-Verwaltungsportal, bevor Sie Gastbenutzer einladen.

Sie können auch die [externe Gastbenutzer zum Bearbeiten und Verwalten von Inhalt in der Organisation können](service-admin-portal.md#allow-external-guest-users-to-edit-and-manage-content-in-the-organization) Feature. Sie können wählen, welche Guest-Benutzer finden Sie unter und Inhalt in Arbeitsbereichen, einschließlich Durchsuchen Ihrer Organisation Power BI erstellen kann.

## <a name="who-can-you-invite"></a>Wen können Sie einladen?

Sie können Gastbenutzer mit einer e-Mail-Adresse, einschließlich Persönliche Konten wie gmail.com und outlook.com, hotmail.com, einladen. Azure AD B2B ruft diese Adressen *Identitäten sozialer Netzwerke*.

## <a name="invite-guest-users"></a>Einladen von Gastbenutzern

Gastbenutzer erfordern Einladungen nur bei der erstmaligen, die Sie in Ihrer Organisation eingeladen werden. Es gibt zwei Möglichkeiten, Benutzer einzuladen: geplante Einladungen und ad-hoc-Einladungen.

### <a name="planned-invites"></a>Geplante Einladungen

Verwenden Sie eine geplante Einladung, wenn Sie wissen, welche Benutzer Sie einladen möchten. Sie können die Einladung über das Azure-Portal oder PowerShell senden. Sie müssen Mandantenadministrator sein, um Personen einzuladen.

Führen Sie die folgenden Schritte aus, um eine Einladung über das Azure-Portal zu senden.

1. Wählen Sie im [Azure-Portal](https://portal.azure.com) **Azure Active Directory** aus.

1. Klicken Sie unter **verwalten**Option **Benutzer** > **alle Benutzer** > **neuer Gastbenutzer**.

    ![Screenshot des Azure-Portal die Option für neue Gast hingewiesen.](media/service-admin-azure-ad-b2b/azure-ad-portal-new-guest-user.png)

1. Geben Sie eine **E-Mail-Adresse** und eine **persönliche Nachricht** ein.

    ![Screenshot des Dialogfelds Azure AD-Portal neue Guest-Benutzer.](media/service-admin-azure-ad-b2b/azure-ad-portal-invite-message.png)

1. Wählen Sie **Einladen** aus.

Verwenden Sie PowerShell, um mehrere Gastbenutzer einzuladen. Weitere Informationen finden Sie unter [Azure Active Directory B2B-Zusammenarbeit: Code- und PowerShell-Beispiele](/azure/active-directory/b2b/code-samples/).

Der Gastbenutzer muss in der empfangenen E-Mail-Einladung **Erste Schritte** auswählen. Anschließend wird der Gastbenutzer dem Mandanten hinzugefügt.

![Screenshot der Gast e-Mail-Einladung.](media/service-admin-azure-ad-b2b/guest-user-invite-email.png)

### <a name="ad-hoc-invites"></a>Ad-hoc-Einladungen

Um einen externen Benutzer zu einem beliebigen Zeitpunkt einzuladen, können fügen Sie zu Ihrem Dashboard oder Bericht über die freigegebene Benutzeroberfläche oder Ihrer-app über die Seite hinzu. Das folgende Beispiel zeigt, wie Sie einen externen Benutzer zur Verwendung einer App einladen.

![Screenshot des externen Benutzers App-Zugriffsliste in Power BI hinzugefügt.](media/service-admin-azure-ad-b2b/power-bi-app-access.png)

Der Guest-Benutzer erhalten eine e-Mail, die angibt, dass Sie die app für sie freigegeben.

![Screenshot der e-Mail-Adresse für die app, die für den Gastbenutzer freigegeben](media/service-admin-azure-ad-b2b/guest-user-invite-email-2.png)

Der Gastbenutzer muss sich mit seiner Organisations-E-Mail-Adresse anmelden. Sie erhalten eine Aufforderung zum Annehmen der Einladung nach der Anmeldung. Nach dem Anmelden öffnet die app für den Guest-Benutzer. Um zur App zurückzukehren, kann der Benutzer den Link als Lesezeichen festlegen oder die E-Mail speichern.

## <a name="licensing"></a>Lizenzierung

Der Guest-Benutzer muss die entsprechende Lizenz um den Inhalt anzuzeigen, den Sie freigegeben haben. Es gibt drei Möglichkeiten, um sicherzustellen, dass der Benutzer hat eine gültige Lizenz: Verwenden Sie Power BI Premium, weisen Sie eine Power BI Pro-Lizenz oder des Gasts Power BI Pro-Lizenz.

Wenn das Feature [Externen Gastbenutzern das Bearbeiten und Verwalten von Inhalten in der Organisation erlauben](service-admin-portal.md#allow-external-guest-users-to-edit-and-manage-content-in-the-organization) verwendet wird, benötigen Gastbenutzer, die Inhalte in Arbeitsbereichen beisteuern oder Inhalte für Andere freigeben, eine Power BI Pro-Lizenz.

### <a name="use-power-bi-premium"></a>Verwenden von Power BI Premium

Zuweisen von app-Arbeitsbereich zu [Power BI Premium-Kapazität](service-premium-what-is.md) können den Guest-Benutzer, die die app zu verwenden, ohne dass eine Power BI Pro-Lizenz. Power BI Premium können apps, die andere Funktionen, z.B. höhere Aktualisierungsraten, dedizierte Kapazität und große Modelle nutzen.

![Diagramm des Gast-Benutzeroberfläche mit Power BI Premium.](media/service-admin-azure-ad-b2b/license-approach-1.png)

### <a name="assign-a-power-bi-pro-license-to-guest-user"></a>Zuweisen einer Power BI Pro-Lizenz zu einem Gastbenutzer

Der Guest-Benutzer in Ihrem Mandanten eine Power BI Pro-Lizenz zuweisen kann, Gast Ansichtsinhalt für Benutzer im Mandanten.

![Diagramm des Gast-Benutzeroberfläche mit weisen Sie Pro-Lizenz aus Ihrem Mandanten.](media/service-admin-azure-ad-b2b/license-approach-2.png)

### <a name="guest-user-brings-their-own-power-bi-pro-license"></a>Der Gastbenutzer verfügt über eine eigene Power BI Pro-Lizenz.

Dem Gastbenutzer ist in seinem Mandanten bereits eine Power BI Pro-Lizenz zugewiesen.

![Diagramm des Gast-benutzererfahrung, wenn sie über eine eigene Lizenz bringen.](media/service-admin-azure-ad-b2b/license-approach-3.png)

## <a name="guest-users-who-can-edit-and-manage-content"></a>Gastbenutzer, die Inhalte bearbeiten und verwalten können. 

Bei Verwendung der [externe Gastbenutzer zum Bearbeiten und Verwalten von Inhalt in der Organisation können](service-admin-portal.md#allow-external-guest-users-to-edit-and-manage-content-in-the-organization) Funktion angegebenen Gastbenutzer erhalten Sie Zugriff auf Ihrer Organisation Power BI. Sie können alle Inhalte sehen, zu dem sie die Berechtigung haben. Sie können Zugriff auf die Startseite, durchsuchen Arbeitsbereiche, apps installieren, finden Sie unter, wo sie auf der Zugriffssteuerungsliste sind und Inhalt in Arbeitsbereichen beitragen. Sie können einen Administrator für Arbeitsbereiche erstellen, der die neue Arbeitsbereichsoberfläche verwendet, oder sie können selbst ein Administrator für diese Bereiche sein. Es gelten einige Einschränkungen. Abschnitt mit Überlegungen und Einschränkungen sind diese Beschränkungen aufgeführt.
 
Damit diese Benutzer bei Power BI anmelden können, stellen sie die Mandanten-URL. Gehen Sie wie folgt vor, um die Mandanten-URL zu finden:

1. Klicken Sie im Power BI-Dienst im oberen Menü auf das Hilfesymbol ( **?** ) und dann auf **Info zu Power BI**.

2. Suchen Sie nach dem Wert neben **Tenant URL** (Mandanten-URL). Der Wert ist die Mandanten-URL, die Sie für Ihre Gastbenutzer freigeben können.

    ![Screenshot der Informationen zu Power BI-Dialogfeld mit Guest-Benutzer-Mandanten, die Url hingewiesen.](media/service-admin-azure-ad-b2b/power-bi-about-dialog.png)

## <a name="considerations-and-limitations"></a>Überlegungen und Einschränkungen

* Standardmäßig beschränkt externe Azure AD B2B Gäste Inhalte nur an. Externe Azure AD B2B-Gäste können apps, Dashboards und Berichte anzeigen, Exportieren von Daten und e-Mail-Abonnements für Dashboards und Berichte erstellen. Der Zugriff auf Arbeitsbereiche und die Veröffentlichung eigener Inhalte sind hingegen nicht möglich. Jedoch diese Einschränkungen gelten nicht für Gastbenutzer, die Zugriff über die [externe Gastbenutzer zum Bearbeiten und Verwalten von Inhalt in der Organisation können](service-admin-portal.md#allow-external-guest-users-to-edit-and-manage-content-in-the-organization) Feature.

* Für Gastbenutzer über aktiviert werden, die [externe Gastbenutzer zum Bearbeiten und Verwalten von Inhalt in der Organisation können](service-admin-portal.md#allow-external-guest-users-to-edit-and-manage-content-in-the-organization) Feature einige Umgebungen werden nicht zur Verfügung. Zum Aktualisieren oder Veröffentlichen von Berichten müssen sie die Webbenutzeroberfläche des Power BI-Diensts verwenden, einschließlich des Befehls „Daten abrufen“ zum Hochladen von Power BI Desktop-Dateien.  Die folgenden Möglichkeiten werden nicht unterstützt:
    * Direktes Veröffentlichen aus Power BI Desktop im Power BI-Dienst
    * Gastbenutzer können nicht Power BI Desktop verwenden, um die Verbindung mit Dienst-Datasets in Power BI-Dienst
    * Klassische Arbeitsbereiche, die mit Office 365-Gruppen verknüpft sind:
        * Gastbenutzer kann nicht erstellt oder werden von Administratoren diese Arbeitsbereiche
        * Gastbenutzer können Mitglieder sein.
    * Ad-hoc-Einladungen senden wird nicht für die Zugriffssteuerungslisten für Arbeitsbereich unterstützt.
    * Power BI Publisher für Excel wird nicht für Gastbenutzer unterstützt.
    * Gastbenutzer können keiner Power BI Gateway installieren und verbinden Sie es in Ihrer Organisation
    * Gastbenutzer können nicht installiert werden. apps, die für die gesamte Organisation veröffentlichen
    * Gastbenutzer können nicht verwenden, erstellen, aktualisieren, oder Installieren von organisationsbezogenen Inhaltspaketen
    * Gastbenutzer können nicht in Excel analysieren verwenden.
    * Gastbenutzer nicht @mentioned in kommentieren
    * Gastbenutzer können keine Abonnements
    * Gastbenutzer, die diese Funktion verwenden, sollten ein Geschäfts-, Schul- oder Unikonto besitzen. Gastbenutzer mit persönlichen Konten treten mehr Einschränkungen aufgrund Einschränkungen anmelden.

* Dieses Feature ist derzeit verfügbar ist, mit dem Power BI SharePoint Online Berichts-Webpart nicht.

* Es sind Active Directory-Einstellungen, die externe Gastbenutzer in Ihrer gesamten Organisation Möglichkeiten einschränken können. Das gilt auch für Ihre Power BI-Umgebung zu finden. In der folgenden Dokumentation werden die Einstellungen erläutert:
    * [Manage External Collaboration Settings](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations#control-who-can-invite) (Einstellungen für externe Zusammenarbeit verwalten)
    * [Zulassen oder Blockieren von Einladungen für B2B-Benutzer von bestimmten Organisationen](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)  

## <a name="next-steps"></a>Nächste Schritte

Ausführlichere Informationen sehen einschließlich wie Zeilenebene Sicherheit funktioniert, Sie sich das Whitepaper: [Verteilen von Power BI-Inhalten an externe Gastbenutzer mit Azure AD B2B](https://aka.ms/powerbi-b2b-whitepaper).

Weitere Informationen zu Azure AD B2B finden Sie unter [Neuigkeiten von Azure AD B2B-Zusammenarbeit?](/azure/active-directory/active-directory-b2b-what-is-azure-ad-b2b/).
