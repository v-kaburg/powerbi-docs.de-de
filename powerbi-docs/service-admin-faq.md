---
title: Verwalten von Power BI – häufig gestellte Fragen (FAQ)
description: Erfahren Sie, die Antworten auf häufig gestellte Fragen zu Power BI-Registrierung, mandantenverwaltung und andere administrativen Aufgaben.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 11/16/2018
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: 2e51017333a940bd9d7838e6a903c1a66ce2e342
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2019
ms.locfileid: "65100781"
---
# <a name="administering-power-bi---frequently-asked-questions-faq"></a>Verwalten von Power BI – häufig gestellte Fragen (FAQ)

Dieser Artikel behandelt häufig gestellte Fragen zur Power BI-Verwaltung. Einen Überblick über die Power BI-Verwaltung finden Sie unter [Was ist die Power BI-Verwaltung?](service-admin-administering-power-bi-in-your-organization.md).

## <a name="whats-in-this-article"></a>Inhalt dieses Artikels

### <a name="sign-up-for-power-bi-section"></a>Registrieren bei Power BI

* [Verwenden von PowerShell](#using-powershell)
* [Wie können sich Benutzer für Power BI registrieren?](#how-do-users-sign-up-for-power-bi)
* [Wie können sich einzelne Benutzer aus meiner Organisation registrieren?](#how-do-individual-users-in-my-organization-sign-up)
* [Wie kann ich verhindern, dass Benutzer meinem vorhandenen Office 365-Mandanten beitreten?](#how-can-i-prevent-users-from-joining-my-existing-office-365-tenant)
* [Wie kann ich Benutzern erlauben, meinem vorhandenen Office 365-Mandanten beizutreten?](#how-can-i-allow-users-to-join-my-existing-office-365-tenant)
* [Wie überprüfe ich, wenn ich die Sperre im Mandanten vorliegt?](#how-do-i-check-if-i-have-the-block-on-in-the-tenant)
* [Wie kann ich verhindern, dass vorhandene Benutzer mit der Nutzung von Power BI beginnen?](#how-can-i-prevent-my-existing-users-from-starting-to-use-power-bi)
* [Wie kann ich meinen vorhandenen Benutzern erlauben, sich für Power BI zu registrieren?](#how-can-i-allow-my-existing-users-to-sign-up-for-power-bi)

### <a name="administration-of-power-bi-section"></a>Verwalten von Power BI

* [Wie ändert sich dadurch die Art und Weise, in der ich die Identitäten für Benutzer in meiner Organisation heute verwalte?](#how-will-this-change-the-way-i-manage-identities-for-users-in-my-organization-today)
* [Wie verwalte ich Power BI?](#how-do-we-manage-power-bi)
* [Was ist der Prozess zum Verwalten eines Mandanten, der von Microsoft für meine Benutzer erstellt wurde?](#what-is-the-process-to-manage-a-tenant-created-by-microsoft-for-my-users)
* [Wenn ich mehrere Domänen habe, kann ich Office 365-Mandanten steuern, dem Benutzer hinzugefügt zu erhalten?](#if-i-have-multiple-domains-can-i-control-the-office-365-tenant-that-users-get-added-to)
* [Wie entferne ich Power BI für Benutzer, die sich bereits registriert haben?](#how-do-i-remove-power-bi-for-users-that-already-signed-up)
* [Wie erfahre ich, wenn meinem Mandanten neue Benutzer beigetreten sind?](#how-do-i-know-when-new-users-have-joined-my-tenant)
* [Gibt es weitere Punkte, denen ich für vorbereitet werden soll?](#are-there-any-additional-things-i-should-prepare-for)
* [Wo befindet sich mein Power BI-Mandant?](#where-is-my-power-bi-tenant-located)
* [Was ist das Power BI-SLA (Vereinbarung zum Servicelevel)?](#what-is-the-power-bi-sla)
* [Wie handhabt Power BI Hochverfügbarkeit und Failovers?](#how-does-power-bi-handle-high-availability-and-failover)

### <a name="security-in-power-bi-section"></a>Sicherheit in Power BI

* [Erfüllt Power BI nationale, regionale und branchenspezifische Anforderungen an die Konformität?](#does-power-bi-meet-national-regional-and-industry-specific-compliance-requirements)
* [Wie funktioniert die Sicherheit in Power BI?](#how-does-security-work-in-power-bi)

## <a name="sign-up-for-power-bi"></a>Registrieren bei Power BI

### <a name="using-powershell"></a>Verwenden von PowerShell

Für einige der Verfahren in diesem Abschnitt sind Windows PowerShell-Skripts erforderlich. Wenn Sie mit PowerShell nicht vertraut sind, beginnen Sie am besten mit dem Leitfaden [Erste Schritte mit PowerShell](http://go.microsoft.com/fwlink/p/?LinkID=286814). Installieren Sie zum Ausführen der Skripts zunächst die neueste 64-Bit-Version der [Azure Active Directory PowerShell für Graph](/powershell/azure/active-directory/).

### <a name="how-do-users-sign-up-for-power-bi"></a>Wie können sich Benutzer für Power BI registrieren?

Als Administrator können Sie sich registrieren für Power BI über die [Power BI-Website](https://powerbi.microsoft.com) oder [Kaufdienste](https://admin.microsoft.com/AdminPortal/Home#/catalog) -Seite auf das Microsoft 365 Administrationscenter. Wenn ein Administrator für Power BI registrieren, können sie für Benutzer, die Zugriff haben sollten, Benutzerlizenzen zuweisen.

Darüber hinaus können sich auch einzelne Benutzer in Ihrer Organisation auf der [Power BI-Website](https://powerbi.microsoft.com) für Power BI registrieren. Wenn ein Benutzer in Ihrer Organisation für Power BI registrieren, weist der Dienst automatisch eine Power BI-Lizenz für den Benutzer. Weitere Informationen finden Sie unter [registrieren für Power BI als Einzelperson](service-self-service-signup-for-power-bi.md) und [Power BI in Ihrer Organisation Lizenzen](service-admin-licensing-organization.md).

### <a name="how-do-individual-users-in-my-organization-sign-up"></a>Wie können sich einzelne Benutzer aus meiner Organisation registrieren?

Es gibt drei Szenarien, die ggf. für die Benutzer in Ihrer Organisation in Betracht kommen:

* **Szenario 1**: Ihre Organisation verfügt bereits über eine Office 365-Umgebung, und der Benutzer, der sich für Power BI registriert, besitzt ein Office 365-Konto.
    In diesem Szenario wird aktiviert, wenn ein Benutzer über bereits ein Geschäfts- oder schulkonto im Mandanten (z.B. "contoso.com") jedoch noch nicht Power BI, Microsoft einfach den Plan für dieses Konto. Der Benutzer wird automatisch mit Informationen zur Verwendung von Power BI-Dienst benachrichtigt.

* **Szenario 2**: Ihre Organisation verfügt über eine Office 365-Umgebung, doch der Benutzer, der sich für Power BI registriert, besitzt noch kein Office 365-Konto.
    In diesem Szenario wird der Benutzer verfügt über eine e-Mail-Adresse in die Domäne Ihrer Organisation (z.B. "contoso.com"), aber noch keine Office 365-Konto. In diesem Fall kann sich der Benutzer für Power BI registrieren und erhält dann automatisch ein Konto. Auf diese Weise können die den Benutzerzugriff auf Power BI-Dienst. Z. B. wenn eine Mitarbeiterin namens Nancy verwendet ihre geschäftliche e-Mail-Adresse (z. B. nancy@contoso.com) zur Registrierung Microsoft fügt automatisch Nancy als Benutzer in der Umgebung von Contoso Office 365 und Power BI für dieses Konto aktiviert.

* **Szenario 3**: Ihre Organisation keine Office 365-Umgebung mit Ihrer e-Mail-Domäne verbunden sind.
    Es gibt keine administrativen Aktionen, die erforderlich sind, für Ihre Organisation zu Power BI nutzen. Der Dienst wird ein neues, nur-Cloud-Benutzerverzeichnis Benutzer hinzugefügt. Sie können auch als mandantenadministrator übernehmen und diese zu verwalten.

> [!IMPORTANT]
> Wenn Ihre Organisation über mehrere E-Mail-Domänen verfügt und Sie alle E-Mail-Adresserweiterungen in demselben Mandanten zusammenfassen möchten, fügen Sie alle E-Mail-Adressdomänen einem Azure Active Directory-Mandanten hinzu, bevor sich die einzelnen Benutzer registrieren. Wenn Sie Benutzer erstellt haben, gibt es keine automatisierten Verfahren zum Verschieben von Benutzern zwischen Mandanten. Weitere Informationen zu diesem Prozess finden Sie unter [Wenn ich mehrere Domänen habe, kann ich steuern die Office 365-Mandanten, dem Benutzer hinzugefügt zu erhalten?](#if-i-have-multiple-domains-can-i-control-the-office-365-tenant-that-users-get-added-to) weiter unten in diesem Artikel und [hinzufügen eine Domäne zu Office 365](/office365/admin/setup/add-domain/).

### <a name="how-can-i-prevent-users-from-joining-my-existing-office-365-tenant"></a>Wie kann ich verhindern, dass Benutzer meinem vorhandenen Office 365-Mandanten beitreten?

Sie können als Administrator Schritte unternehmen, die verhindern, dass Benutzer Ihren vorhandenen Office 365-Mandanten beitreten. Wenn Sie den Zugriff, Registrierungsversuche von Benutzern zum Registrieren des ausfallen, blockieren und eine Meldung angezeigt, weist diese dem Administrator ihrer Organisation kontaktieren Sie müssen diesen Vorgang zu wiederholen, wenn Sie bereits die automatische Verteilung von Lizenzen (z. B. über Office 365 Education für Schüler/Studenten, Lehrkräfte und Mitarbeiter) deaktiviert haben.

Verwenden Sie das folgende PowerShell-Skript, um zu verhindern, dass neue Benutzer einem verwalteten Mandanten beitreten. ([Hier erfahren Sie mehr über PowerShell][1].)

```powershell
$msolcred = get-credential
connect-msolservice -credential $msolcred

Set-MsolCompanySettings -AllowEmailVerifiedUsers $false
```

> [!NOTE]
> Die Zugriffssperre verhindert, dass sich neue Benutzer in Ihrer Organisation für Power BI registrieren. Benutzer, die sich für Power BI registriert haben, bevor Sie neue Registrierungen für Ihre Organisation deaktiviert haben, behalten ihre Lizenzen jedoch. Wie Sie Benutzer entfernen, erfahren Sie weiter unten in diesem Artikel unter [Wie entferne ich Power BI für Benutzer, die sich bereits registriert haben?](#how-do-i-remove-power-bi-for-users-that-already-signed-up).

### <a name="how-can-i-allow-users-to-join-my-existing-office-365-tenant"></a>Wie kann ich Benutzern erlauben, meinem vorhandenen Office 365-Mandanten beizutreten?

Verwenden Sie das folgende PowerShell-Skript, um neue Benutzer einen verwalteten Mandanten beitreten können. ([Hier erfahren Sie mehr über PowerShell][1].)

```powershell
$msolcred = get-credential
connect-msolservice -credential $msolcred

Set-MsolCompanySettings -AllowEmailVerifiedUsers $true
```

### <a name="how-do-i-check-if-i-have-the-block-on-in-the-tenant"></a>Wie überprüfe ich, wenn ich die Sperre im Mandanten vorliegt?

Verwenden Sie das folgende PowerShell-Skript, um Einstellungen zu überprüfen. *AllowEmailVerifiedUsers* muss auf FALSE festgelegt sein. ([Hier erfahren Sie mehr über PowerShell][1].)

```powershell
$msolcred = get-credential
connect-msolservice -credential $msolcred

Get-MsolCompanyInformation | fl allow*
```

### <a name="how-can-i-prevent-my-existing-users-from-starting-to-use-power-bi"></a>Wie kann ich verhindern, dass vorhandene Benutzer mit der Nutzung von Power BI beginnen?

Die entsprechende Azure AD-Einstellung ist **AllowAdHocSubscriptions**. Die meisten Mandanten haben dies auf True festgelegt, was bedeutet, dass es aktiviert ist. Wenn Sie Power BI über einen Partner erworben haben, kann dies auf "False" festgelegt werden dies bedeutet, dass er deaktiviert ist.

Verwenden Sie das folgende PowerShell-Skript, um Ad-hoc-Abonnements zu deaktivieren. ([Hier erfahren Sie mehr über PowerShell][1].)

1. Melden Sie sich mithilfe Ihrer Office 365-Anmeldeinformationen bei Azure Active Directory an. In der ersten Zeile des folgenden PowerShell-Skripts werden Sie aufgefordert, Ihre Anmeldeinformationen einzugeben. Die zweite Zeile stellt die Verbindung mit Azure Active Directory her.

    ```powershell
     $msolcred = get-credential
     connect-msolservice -credential $msolcred
    ```

   ![Screenshot des Azure Active Directory-Anmeldung über PowerShell](media/service-admin-licensing-organization/azure-ad-sign-in.png)

1. Einmal anmelden Sie führen den folgenden Befehl aus, um festzustellen, wie Ihr Mandant derzeit eingerichtet ist.

    ```powershell
     Get-MsolCompanyInformation | fl AllowAdHocSubscriptions
    ```

1. Führen Sie den folgenden Befehl zum Aktivieren (`$true`) oder zu deaktivieren (`$false`) **AllowAdHocSubscriptions**.

    ```powershell
     Set-MsolCompanySettings -AllowAdHocSubscriptions $false
    ```

> [!NOTE]
> Verwenden der **AllowAdHocSubscriptions** Flag, um verschiedene Benutzeroptionen in Ihrer Organisation, einschließlich der Möglichkeit für Benutzer zum Registrieren für den Azure Rights Management-Dienst steuern. Das Ändern dieses Flags wirkt sich auf all diese Optionen aus.

### <a name="how-can-i-allow-my-existing-users-to-sign-up-for-power-bi"></a>Wie kann ich meinen vorhandenen Benutzern erlauben, sich für Power BI zu registrieren?

Können Ihre vorhandenen Benutzer zum Registrieren für Power BI, führen Sie den Befehl aufgeführt, die für die vorherige Frage, übergeben Sie jedoch `$true` anstelle von `$false` im letzten Schritt.

## <a name="administration-of-power-bi"></a>Verwaltung von Power BI

### <a name="how-will-this-change-the-way-i-manage-identities-for-users-in-my-organization-today"></a>Wie ändert sich dadurch die Art und Weise, in der ich die Identitäten für Benutzer in meiner Organisation heute verwalte?

Es gibt drei Szenarien, die ggf. für die Benutzer in Ihrer Organisation in Betracht kommen:

* **Szenario 1**: Wenn Ihre Organisation verfügt bereits über ein Office 365-Umgebung, und alle Benutzer in Ihrer Organisation über Office 365-Konten verfügen, ist es keine Änderung in die Verwaltung der Identität.

* **Szenario 2**: Wenn Ihre Organisation verfügt bereits über ein Office 365-Umgebung, aber nicht alle Benutzer in Ihrer Organisation über Office 365-Konten verfügen, werden wir erstellen einen Benutzer im Mandanten und weisen Lizenzen anhand des Benutzers Geschäfts-, Schul- oder UNI-e-Mail-Adresse.

    Daher wächst die Anzahl der Benutzer, die Sie zu einem bestimmten Zeitpunkt verwalten, wenn sich Benutzer in Ihrer Organisation für den Dienst registrieren.

* **Szenario 3**: Wenn Ihre Organisation nicht über ein Office 365-Umgebung, die mit Ihrer e-Mail-Domäne verbunden verfügt, bleibt unverändert in die Verwaltung der Identität.

    Der Dienst wird ein neues, nur-Cloud-Benutzerverzeichnis Benutzer hinzugefügt. Sie können auch als mandantenadministrator übernehmen und diese verwalten.

### <a name="how-do-we-manage-power-bi"></a>Wie verwalte ich Power BI?

Powerbi bietet ein Verwaltungsportal, in dem Sie die Verwendungsstatistiken, anzeigen kann, enthält einen Link zum Microsoft 365 Administrationscenter zum Verwalten von Benutzern und Gruppen, und bietet die Möglichkeit zur Steuerung von mandantenweite Einstellungen.

Um das Power BI-Verwaltungsportal verwenden, müssen Sie Ihrem Konto als Markieren einer **globaler Administrator** in Office 365 oder Azure Active Directory oder ein Benutzer muss die Power BI-dienstadministratorrolle Ihr Benutzerkonto zuweisen. Weitere Informationen finden Sie unter [Grundlegendes zur Power BI-Administratorrolle](service-admin-role.md) und [Power BI-Verwaltungsportal](service-admin-portal.md).

### <a name="what-is-the-process-to-manage-a-tenant-created-by-microsoft-for-my-users"></a>Was ist der Prozess zum Verwalten eines Mandanten, der von Microsoft für meine Benutzer erstellt wurde?

Wenn ein Self-service-Benutzer für einen Clouddienst, die Azure AD verwendet registriert, der Dienst fügt sie in einem nicht verwalteten Azure AD-Verzeichnis anhand seiner e-Mail-Domäne. Können Sie beanspruchen und verwalten Sie den Mandanten, die eine Person unter Verwendung eines Prozesses erstellt als bezeichnet ein *administratorübernahme*. Hängt von der Typ der Übernahme, Sie tun, ob es eine vorhandene ist verwaltete Mandanten Ihrer Domäne zugeordnet:

* Verwenden Sie eine *interne Übernahme*, um einen neuen verwalteten Mandanten für die Domäne zu erstellen.

* Verwenden Sie eine *externe Übernahme*, um die Domäne zu einem vorhandenen verwalteten Mandanten zu verschieben.

Weitere Informationen finden Sie unter [Übernehmen eines nicht verwalteten Verzeichnisses als Administrator in Azure Active Directory](/azure/active-directory/users-groups-roles/domains-admin-takeover).

Wenn Sie eine externe Übernahme ausführen, der Dienst fügt Power BI Content, erstellt wurde, bevor Sie die Übernahme in einem [archivierten Arbeitsbereich in Power BI](service-admin-power-bi-archived-workspace.md). Sie müssen alle Inhalte, die Sie im neuen Mandanten verwenden möchten, manuell migrieren.

### <a name="if-i-have-multiple-domains-can-i-control-the-office-365-tenant-that-users-get-added-to"></a>Wenn ich mehrere Domänen habe, kann ich Office 365-Mandanten steuern, dem Benutzer hinzugefügt zu erhalten?

Wenn Sie nichts tun, werden vom Dienst ein Mandant für jede Benutzer-e-Mail-Domäne und-Unterdomäne erstellt. Wenn sich alle Benutzer unabhängig von ihren E-Mail-Adresserweiterungen in demselben Mandanten befinden sollen, gehen Sie folgendermaßen vor: Erstellen Sie einen zielmandanten, oder verwenden Sie einen vorhandenen Mandanten. Fügen Sie dann alle vorhandenen Domänen und Unterdomänen, die in diesem Mandanten konsolidiert werden sollen. Jeder Benutzer mit e-Mail-Adressen automatisch auf diese Domänen und Unterdomänen enden-Mandanten verknüpfen, wenn die Registrierung.

> [!IMPORTANT]
> Wenn Sie Benutzer erstellt haben, besteht keine automatisierten Verfahren zum Verschieben von Benutzern zwischen Mandanten. Informationen zum Hinzufügen von Domänen zu einem einzelnen Office 365-Mandanten finden Sie unter dem Thema zum [Hinzufügen von Benutzern und Domänen zu Office 365](/office365/admin/setup/add-domain/).

### <a name="how-do-i-remove-power-bi-for-users-that-already-signed-up"></a>Wie entferne ich Power BI für Benutzer, die sich bereits registriert haben?

Wenn sich ein Benutzer für Power BI registriert hat, Sie aber nicht möchten, dass er weiterhin auf Power BI zugreifen kann, können Sie die Power BI-Lizenz für diesen Benutzer entfernen.

1. Navigieren Sie zum [Microsoft 365 Admin Center](https://admin.microsoft.com/AdminPortal/Home#/homepage).

1. Wählen Sie in der linken Navigationsleiste **Benutzer** > **Aktive Benutzer** aus.

1. Suchen Sie den Benutzer, dessen Lizenz Sie entfernen möchten, und wählen Sie seinen Namen aus.

    Sie können auch eine Batchverwaltung von Benutzerlizenzen durchführen. Wählen Sie dazu mehrere Benutzer und dann **Produktlizenzen bearbeiten** aus.

1. Wählen Sie auf der Seite „Benutzerdetails“ neben **Produktlizenzen** **Bearbeiten** aus.

1. Je nachdem was Sie lizenzieren auf ihr Konto angewendet wird, legen Sie **Power BI (free)** oder **Power BI Pro** zu **aus**.

1. Wählen Sie **Speichern**.

### <a name="how-do-i-know-when-new-users-have-joined-my-tenant"></a>Wie erfahre ich, wenn meinem Mandanten neue Benutzer beigetreten sind?

Benutzer, die Ihren Mandanten im Rahmen dieses Programms beigetreten sind, erhalten eine eindeutige Lizenz zugewiesen, die Sie innerhalb Ihres aktiven Benutzerbereichs im Verwaltungsdashboard filtern können. Gehen Sie wie folgt vor, um diese neue Ansicht zu erstellen.

1. Navigieren Sie zum [Microsoft 365 Admin Center](https://admin.microsoft.com/AdminPortal/Home#/homepage).

1. Wählen Sie in der linken Navigationsleiste **Benutzer** > **Aktive Benutzer** aus.

1. Wählen Sie im Menü **Ansichten** die Option **Benutzerdefinierte Ansicht hinzufügen** aus.

1. Benennen Sie die neue Ansicht, und wählen Sie unter **Zugewiesene Produktlizenz** **Power BI Free** oder **Power BI Pro** aus.

    Sie können nur eine Lizenz pro Ansicht auswählen. Wenn Sie in Ihrer Organisation über die beide Lizenzen **Power BI Free** und **Power BI Pro** verfügen, können Sie zwei Ansichten erstellen.

1. Geben Sie alle anderen gewünschten Bedingungen ein, und wählen Sie dann **Hinzufügen** aus.

1. Nachdem Sie die neue Ansicht erstellt haben, es steht in der **Ansichten** Menü.

### <a name="are-there-any-additional-things-i-should-prepare-for"></a>Gibt es weitere Punkte, denen ich für vorbereitet werden soll?

Es kann häufiger zur Anfragen zur Kennwortrücksetzung kommen. Weitere Informationen zu diesem Prozess finden Sie unter [Zurücksetzen des Kennworts eines Benutzers](/office365/admin/add-users/reset-passwords).

Sie können einen Benutzer über den Standardprozess im Microsoft 365 Admin Center aus Ihrem Mandanten entfernen. Wenn der Benutzer jedoch weiterhin über eine aktive E-Mail-Adresse in Ihrer Organisation verfügt, kann er erneut beitreten, es sei denn, Sie sperren den Beitritt für alle Benutzer.

### <a name="where-is-my-power-bi-tenant-located"></a>Wo befindet sich mein Power BI-Mandant?

Informationen zu welcher Datenbereich Power BI-Mandanten wird, finden Sie unter [wo mein Power BI-Mandant befindet?](service-admin-where-is-my-tenant-located.md).

### <a name="what-is-the-power-bi-sla"></a>Was ist das Power BI-SLA?

Informationen über die Power BI-SLA (Vereinbarung zum Servicelevel) finden Sie in der [Lizenzierungsbedingungen und Dokumentation](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=37) Artikel der **Licensing** der Microsoft Licensing-Website.

### <a name="how-does-power-bi-handle-high-availability-and-failover"></a>Wie handhabt Power BI Hochverfügbarkeit und Failovers?

Weitere Informationen über hohe Verfügbarkeit und Failover, finden Sie unter [hohe Verfügbarkeit, Failover und Disaster-Recovery Power BI – häufig gestellte Fragen](service-admin-failover.md).

## <a name="security-in-power-bi"></a>Sicherheit in Power BI

### <a name="does-power-bi-meet-national-regional-and-industry-specific-compliance-requirements"></a>Erfüllt Power BI nationale, regionale und branchenspezifische Anforderungen an die Konformität?

Weitere Informationen zur Power BI-Konformität finden Sie im [Microsoft Trust Center](https://www.microsoft.com/TrustCenter/CloudServices/business-application-platform/default.aspx).

### <a name="how-does-security-work-in-power-bi"></a>Wie funktioniert die Sicherheit in Power BI?

Microsoft integriert Power BI. auf der Grundlage von Office 365, die wiederum auf Azure-Dienste wie Azure Active Directory basiert. Eine Übersicht über die Power BI-Architektur finden Sie unter [Sicherheit in Power BI](service-admin-power-bi-security.md).

## <a name="next-steps"></a>Nächste Schritte

[Power BI-Verwaltungsportal](service-admin-portal.md)  
[Grundlegendes zur Power BI-Administratorrolle](service-admin-role.md)  
[Self-Service-Registrierung für Power BI](service-self-service-signup-for-power-bi.md)  
[Erwerb von Power BI Pro](service-admin-purchasing-power-bi-pro.md)  
[Was ist Power BI Premium?](service-premium-what-is.md)  
[Wie Sie Power BI Premium kaufen](service-admin-premium-purchase.md)  
[Power BI Premium-Whitepaper](https://aka.ms/pbipremiumwhitepaper)  
[Verwalten Ihrer Gruppe in Power BI und Office 365](service-manage-app-workspace-in-power-bi-and-office-365.md)  
[Office 365-Benutzerkontenverwaltung](/office365/servicedescriptions/office-365-platform-service-description/user-account-management/)  
[Office 365-Gruppenverwaltung](/office365/admin/email/create-edit-or-delete-a-security-group/)  

Weitere Fragen? [Stellen Sie Ihre Frage in der Power BI-Community.](http://community.powerbi.com/)

[1]: https://docs.microsoft.com/powershell/scripting/overview