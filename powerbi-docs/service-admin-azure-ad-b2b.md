---
title: Verteilen von Power BI-Inhalten an externe Gastbenutzer mit Azure AD B2B
description: Power BI ist in Azure Active Directory Business-to-Business (Azure AD B2B) integriert, um die sichere Verteilung von Power BI-Inhalten an Gastbenutzer außerhalb der Organisation zu ermöglichen.
services: powerbi
documentationcenter: ''
author: mgblythe
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 03/02/2018
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: 16820050ad879b128482af5754bc53973449f982
ms.sourcegitcommit: 8552a34df8e6141eb704314c1a019992901d6e78
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2018
---
# <a name="distribute-power-bi-content-to-external-guest-users-with-azure-ad-b2b"></a>Verteilen von Power BI-Inhalten an externe Gastbenutzer mit Azure AD B2B

Power BI ist in Azure Active Directory Business-to-Business (Azure AD B2B) integriert, um die sichere Verteilung von Power BI-Inhalten an Gastbenutzer außerhalb der Organisation zu ermöglichen und dabei die Kontrolle über die internen Daten zu behalten.

> [!VIDEO https://www.youtube.com/embed/xxQWEQ1NnlY]

> [!NOTE]
> Bevor Sie Gastbenutzer einladen können, müssen Sie das Feature [Einstellungen für Export und Freigabe](service-admin-portal.md#export-and-sharing-settings) in den Mandanteneinstellungen des Power BI-Verwaltungsportals **aktivieren**.

> [!NOTE]
> Diese Funktion ist für die mobilen Power BI-Apps derzeit nicht verfügbar. Auf Mobilgeräten können Sie die freigegebenen Power BI-Inhalte über Azure AD B2B im Browser anzeigen. 

## <a name="who-can-you-invite"></a>Wen können Sie einladen?

Sie können Gastbenutzer einladen, die eine E-Mail-Adresse mit einem privaten Konto verwenden, wie z.B. gmail.com, outlook.com oder hotmail.com. Dies wird in Azure B2B „soziale ID“ genannt. Weitere Informationen finden Sie unter [Azure B2B](https://docs.microsoft.com/en-us/azure/active-directory/active-directory-b2b-what-is-azure-ad-b2b).

## <a name="invite-guest-users"></a>Einladen von Gastbenutzern

Es gibt zwei Möglichkeiten, Gastbenutzer Ihres Power BI-Mandanten einzuladen: geplante Einladungen oder Ad-hoc-Einladungen. Einladungen sind nur erforderlich, wenn ein externer Benutzer zum ersten Mal in Ihre Organisation eingeladen wird.

### <a name="planned-invites"></a>Geplante Einladungen

Eine geplante Einladung erfolgt im Microsoft Azure-Portal in Azure AD oder mithilfe von PowerShell. Diese Option sollten Sie verwenden, wenn Sie wissen, welche Benutzer eingeladen werden müssen. 

**Zum Erstellen der Gastbenutzer im Azure AD-Portal müssen Sie ein Mandantenadministrator sein.**

1. Navigieren Sie zum [Azure-Portal](https://portal.azure.com), und wählen Sie **Azure Active Directory** aus.

2. Navigieren Sie zu **Benutzer und Gruppen** > **Alle Benutzer** > **Neuer Gastbenutzer**.

    ![Azure AD-Portal – Neuer Gastbenutzer](media/service-admin-azure-ad-b2b/azuread-portal-new-guest-user.png)

3. Geben Sie die **E-Mail-Adresse** und eine **persönliche Nachricht** ein.

    ![Azure AD-Portal – Nachricht zum Einladen eines neuen Gastbenutzers](media/service-admin-azure-ad-b2b/azuread-portal-invite-message.png)

4. Wählen Sie **Einladen** aus.

Verwenden Sie PowerShell, um mehrere Gastbenutzer einzuladen. Weitere Informationen finden Sie unter [Azure Active Directory B2B-Zusammenarbeit: Code- und PowerShell-Beispiele](https://docs.microsoft.com/azure/active-directory/active-directory-b2b-code-samples).

Der Gastbenutzer muss in der empfangenen E-Mail-Einladung **Erste Schritte** auswählen. Anschließend wird der Gastbenutzer dem Mandanten hinzugefügt.

![E-Mail-Einladung für Gastbenutzer](media/service-admin-azure-ad-b2b/guest-user-invite-email.png)

### <a name="ad-hoc-invites"></a>Ad-hoc-Einladungen

Um eine Einladung zu einem beliebigen Zeitpunkt auszuführen, fügen Sie den externen Benutzer über die freigegebene Benutzeroberfläche dem Dashboard oder dem Bericht hinzu, bzw. fügen Sie den externen Benutzer über die Zugriffsseite Ihrer App hinzu.

Das folgende Beispiel zeigt, wie Sie einen externen Benutzer zur Verwendung einer App einladen.
![Der App-Zugriffsliste hinzugefügter externer Benutzer](media/service-admin-azure-ad-b2b/power-bi-app-access.png)

Der Gastbenutzer empfängt eine E-Mail mit der Mitteilung, dass die App für ihn freigegeben wurde.

![E-Mail mit der Mitteilung, dass die App für den Gastbenutzer freigegeben wurde](media/service-admin-azure-ad-b2b/guest-user-invite-email2.png)

Der Gastbenutzer muss sich mit seiner Organisations-E-Mail-Adresse anmelden. Nach dem Anmelden wird er aufgefordert, die Einladung anzunehmen. Der Gastbenutzer wird nach dem Anmelden zu den App-Inhalten umgeleitet. Um zur App zurückzukehren, speichern Sie den Link als Lesezeichen, oder speichern Sie die E-Mail.

## <a name="licensing"></a>Lizenzierung

Der Gastbenutzer benötigt eine entsprechende Lizenz, um die freigegebene App anzuzeigen. Es gibt drei Möglichkeiten, dies zu erreichen.

### <a name="use-power-bi-premium"></a>Verwenden von Power BI Premium

Durch Zuweisen des App-Arbeitsbereichs zu Power BI Premium-Kapazität kann der Gastbenutzer die App verwenden, ohne dass eine Power BI Pro-Lizenz erforderlich ist. Mithilfe von Power BI Premium können Apps zudem weitere Funktionen nutzen, z.B. höhere Aktualisierungsraten, dedizierte Kapazität und große Modelle.

![Verwenden von Power BI Premium](media/service-admin-azure-ad-b2b/license-approach1.png)

### <a name="assign-power-bi-pro-license-to-guest-user"></a>Zuweisen einer Power BI Pro-Lizenz zu einem Gastbenutzer

Wenn Sie im Mandanten dem Gastbenutzer eine Power BI Pro-Lizenz zuweisen, kann dieser die Inhalte anzeigen.

> [!NOTE]
> Eine Power BI Pro-Lizenz aus dem Mandanten gilt für Gastbenutzer nur bei deren Zugriff auf Inhalte im Mandanten.

![Zuweisen der Pro-Lizenz aus dem Mandanten](media/service-admin-azure-ad-b2b/license-approach2.png)

### <a name="guest-user-brings-their-own-power-bi-pro-license"></a>Der Gastbenutzer verfügt über eine eigene Power BI Pro-Lizenz.

Dem Gastbenutzer ist in seinem Mandanten bereits eine Power BI Pro-Lizenz zugewiesen.

![Der Gastbenutzer verfügt über eine eigene Lizenz.](media/service-admin-azure-ad-b2b/license-approach3.png)

## <a name="considerations-and-limitations"></a>Überlegungen und Einschränkungen

* Wenn Sie Gastbenutzer mit privaten E-Mail-Konten, wie z.B. gmail.com, outlook.com oder hotmail.com, einladen möchten, können Sie in diesem [eingebetteten Video](https://docs.microsoft.com/en-us/azure/active-directory/active-directory-b2b-redemption-experience) sehen, wie sich ein Benutzer registriert.
* Externe B2B-Gäste können lediglich Inhalte abrufen. Externe B2B-Gäste können Apps, Dashboards und Berichte anzeigen, Daten exportieren und E-Mail-Abonnements für Dashboards und Berichte erstellen. Der Zugriff auf Arbeitsbereiche und die Veröffentlichung eigener Inhalte sind hingegen nicht möglich.
* Diese Funktion ist für die mobilen Power BI-Apps derzeit nicht verfügbar. Auf Mobilgeräten können Sie die freigegebenen Power BI-Inhalte über Azure AD B2B im Browser anzeigen.
* In unabhängigen Clouds (Behörden) werden bei Power BI keine Gastbenutzer unterstützt.

## <a name="next-steps"></a>Nächste Schritte

Ausführlichere Informationen, darunter zur Funktionsweise von Sicherheit auf Zeilenebene, finden Sie im [Whitepaper](https://aka.ms/powerbi-b2b-whitepaper).

Informationen zu Azure Active Directory B2B finden Sie unter [Was ist die Azure AD B2B-Zusammenarbeit?](https://docs.microsoft.com/azure/active-directory/active-directory-b2b-what-is-azure-ad-b2b)
