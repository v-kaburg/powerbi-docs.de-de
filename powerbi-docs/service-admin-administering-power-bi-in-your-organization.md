---
title: Verwalten von Power BI in Ihrer Organisation
description: Verwalten von Power BI in Ihrer Organisation
services: powerbi
documentationcenter: 
author: markingmyname
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 11/28/2017
ms.author: maghan
ms.openlocfilehash: 0fd6226ca14a4b48c94e13eaae8b085381a5f9a6
ms.sourcegitcommit: 6e693f9caf98385a2c45890cd0fbf2403f0dbb8a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2018
---
# <a name="administering-power-bi-in-your-organization"></a>Verwalten von Power BI in Ihrer Organisation
Mit Microsoft Power BI können Benutzer Daten visualisieren, Erkenntnisse teilen und auf intuitive neue Art zusammenarbeiten. Weitere Informationen finden Sie unter [Erste Schritte mit Power BI](service-get-started.md).

Sie können Power BI an verschiedenen Orten verwalten. Dies sind zwei übliche Orte:

> [!NOTE]
> Ihr Konto muss in Office 365 oder Azure Active Directory als **Globaler Administrator** markiert oder der Power BI-Dienstadministratorrolle zugewiesen sein, damit Sie Zugriff auf das Power BI-Verwaltungsportal erhalten. Weitere Informationen zur Power BI-Dienstadministratorrolle finden Sie unter [Grundlegendes zur Power BI-Administratorrolle](service-admin-role.md).
> 
> 

* [Power BI-Verwaltungsportal](https://app.powerbi.com/admin-portal)
* [Office 365 Admin Center](https://portal.office.com/adminportal/home)

Weitere Informationen in Bezug auf die Power BI-Dienstadministratorrolle finden Sie unter [Grundlegendes zur Power BI-Administratorrolle](service-admin-role.md).

## <a name="whats-in-this-article"></a>Inhalt dieses Artikels
**Registrieren bei Power BI**

* [Wie können sich Benutzer für Power BI registrieren?](#how-do-users-sign-up-for-power-bi)
* [Wie können sich einzelne Benutzer aus meiner Organisation registrieren?](#how-do-individual-users-in-my-organization-sign-up)
* [Wie kann ich verhindern, dass Benutzer meinem vorhandenen Office 365-Mandanten beitreten?](#how-can-i-prevent-users-from-joining-my-existing-office-365-tenant)
* [Wie kann ich Benutzern erlauben, meinem vorhandenen Office 365-Mandanten beizutreten?](#how-can-i-allow-users-to-join-my-existing-office-365-tenant)
* [Wie überprüfe ich, ob eine Sperre im Mandanten vorliegt?](#how-do-i-verify-if-i-have-the-block-on-in-the-tenant)
* [Wie kann ich verhindern, dass vorhandene Benutzer mit der Nutzung von Power BI beginnen?](#how-can-i-prevent-my-existing-users-from-starting-to-use-power-bi)
* [Wie kann ich meinen vorhandenen Benutzern erlauben, sich für Power BI zu registrieren?](#how-can-i-allow-my-existing-users-to-sign-up-for-power-bi)

**Verwaltung von Power BI**

* [Wie ändert sich dadurch die Art und Weise, in der ich die Identitäten für Benutzer in meiner Organisation heute verwalte?](#how-will-this-change-the-way-i-manage-identities-for-users-in-my-organization-today)
* [Wie verwalte ich Power BI?](#how-do-we-manage-power-bi)
* [Was ist der Prozess zum Verwalten eines Mandanten, der von Microsoft für meine Benutzer erstellt wurde?](#what-is-the-process-to-manage-a-tenant-created-by-Microsoft-for-my-users)
* [Wenn ich mehrere Domänen habe, kann ich den Office 365-Mandanten steuern, dem Benutzer hinzugefügt werden?](#if-i-have-multiple-domains-can-i-control-the-office-365-tenant-that-users-are-added-to)
* [Wie entferne ich Power BI für Benutzer, die sich bereits registriert haben?](#how-do-i-remove-power-bi-for-users-that-already-signed-up)
* [Wie erfahre ich, wenn meinem Mandanten neue Benutzer beigetreten sind?](#how-do-i-know-when-new-users-have-joined-my-tenant)
* [Gibt es weitere Punkte, auf die ich vorbereitet sein sollte?](#are-there-any-additional-things-i-should-be-prepared-for)
* [Ist es kostenlos? Werden für diese Lizenzen Gebühren berechnet?](#is-this-free-will-i-be-charged-for-these-licenses)
* [Wo befindet sich mein Power BI-Mandant?](#where-is-my-power-bi-tenant-located)
* [Was ist das Power BI-SLA (Vereinbarung zum Servicelevel)?](#what-is-the-power-bi-sla)

**Sicherheit in Power BI**

* [Erfüllt Power BI nationale, regionale und branchenspezifische Anforderungen an die Konformität?](#does-power-bi-meet-national-regional-and-industry-specific-compliance-requirements)
* [Wie funktioniert die Sicherheit in Power BI?](#how-does-security-work-in-power-bi?)

## <a name="sign-up-for-power-bi"></a>Registrieren bei Power BI
### <a name="how-do-users-sign-up-for-power-bi"></a>Wie können sich Benutzer für Power BI registrieren?
Sie können sich auf der [Power BI-Website](https://powerbi.microsoft.com) für Power BI registrieren. Sie können auch über die Bestelldienstseite im Office 365 Admin Center registrieren. Wenn sich Administratoren für Power BI registrieren, können sie Benutzern, die Zugriff erhalten sollten, Benutzerlizenzen zuweisen.

Darüber hinaus können sich auch einzelne Benutzer in Ihrer Organisation auf der [Power BI-Website](https://powerbi.microsoft.com) für Power BI registrieren. Wenn sich ein Benutzer in Ihrer Organisation für Power BI registriert, wird diesem Benutzer automatisch eine Power BI-Lizenz zugewiesen. [Weitere Informationen](service-self-service-signup-for-power-bi.md)

### <a name="how-do-individual-users-in-my-organization-sign-up"></a>Wie können sich einzelne Benutzer aus meiner Organisation registrieren?
Es gibt drei Szenarien, die ggf. für die Benutzer in Ihrer Organisation in Betracht kommen:

Szenario 1: Ihre Organisation verfügt bereits über eine Office 365-Umgebung, und die Benutzer, die sich für Power BI registrieren, haben ein Office 365-Konto.
In diesem Szenario aktiviert Microsoft einfach den Plan für das Konto, wenn der Benutzer bereits über ein Firmen- oder Schulkonto für den Mandanten (z. B. contoso.com) verfügt, aber noch nicht auf Power BI zugreifen kann. Der Benutzer wird automatisch benachrichtigt, wie er den Power BI-Dienst verwenden kann.

Szenario 2: Ihre Organisation verfügt über eine Office 365-Umgebung, und die Benutzer, die sich für Power BI registrieren, haben noch kein Office 365-Konto.
In diesem Szenario besitzt der Benutzer eine E-Mail-Adresse in der Domäne Ihrer Organisation (z. B. „contoso.com“), jedoch noch kein Office 365-Konto. In diesem Fall kann sich der Benutzer für Power BI registrieren – er erhält dann automatisch ein Konto. Damit erhalten Benutzer Zugriff auf den Power BI-Dienst. Wenn beispielsweise eine Mitarbeiterin namens Nancy ihre geschäftliche E-Mail-Adresse (z.B. Nancy@contoso.com) für die Registrierung verwendet, fügt Microsoft Nancy automatisch der Office 365-Umgebung von Contoso als Benutzerin hinzu und aktiviert Power BI für dieses Konto.

Szenario 3: Ihre Organisation verfügt nicht über eine Office 365-Umgebung, die mit Ihrer E-Mail-Domäne verbunden ist.
Es gibt keine administrativen Aktionen, die Ihre Organisation unternehmen muss, um die Vorteile von Power BI zu nutzen. Benutzer werden einem neuen, ausschließlich cloudseitigen Benutzerverzeichnis hinzugefügt, und Sie haben die Möglichkeit, als Mandantenadministrator deren Verwaltung zu übernehmen.

> [!IMPORTANT]
> Wenn Ihre Organisation über mehrere E-Mail-Domänen verfügt und Sie alle E-Mail-Adresserweiterungen in demselben Mandanten zusammenfassen möchten, fügen Sie alle E-Mail-Adressdomänen einem Azure Active Directory-Mandanten hinzu, bevor sich die einzelnen Benutzer registrieren. Es gibt keine automatisierten Verfahren zum Verschieben von Benutzern zwischen Mandanten, nachdem sie erstellt wurden. Weitere Informationen zu diesem Vorgang finden Sie unter [Wenn ich mehrere Domänen habe, kann ich den Office 365-Mandanten steuern, dem Benutzer hinzugefügt werden?](#if-i-have-multiple-domains-can-i-control-the-office-365-tenant-that-users-are-added-to) weiter unten in diesem Artikel und online unter dem Thema zum [Hinzufügen Ihrer Domäne zu Office 365](https://support.office.com/article/Add-your-users-and-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).
> 
> 

### <a name="how-can-i-prevent-users-from-joining-my-existing-office-365-tenant"></a>Wie kann ich verhindern, dass Benutzer meinem vorhandenen Office 365-Mandanten beitreten?
Sie können als Administrator Schritte unternehmen, die verhindern, dass Benutzer Ihren vorhandenen Office 365-Mandanten beitreten. Wenn Sie dies blockieren, können sich keine Benutzer registrieren. Sie werden stattdessen an den Administrator ihrer Organisation weitergeleitet. Sie müssen diesen Vorgang nicht wiederholen, wenn Sie die automatische Verteilung von Lizenzen (z. B. Office 365 Education für Studenten, Bildungseinrichtungen und Lehrpersonal) bereits deaktiviert haben.

Diese Schritte erfordern die Verwendung von Windows PowerShell. Informationen zum Einstieg in Windows PowerShell finden Sie in den [ersten Schritten mit PowerShell](http://go.microsoft.com/fwlink/p/?LinkID=286814).

Um die folgenden Schritte ausführen zu können, müssen Sie die neueste 64-Bit-Version des [Azure Active Directory-Moduls für Windows PowerShell](http://go.microsoft.com/fwlink/p/?LinkID=236297) installieren.

Wählen Sie nach dem Klicken auf den Link **Ausführen** aus, um das Installationspaket auszuführen.

**Deaktivieren des automatischen Mandantenbeitritts:** Mit diesem Windows PowerShell-Befehl können Sie verhindern, dass neue Benutzer einem verwalteten Mandanten beitreten:

* So deaktivieren Sie den automatischen Mandantenbeitritt für neue Benutzer
  
    $msolcred = get-credential   connect-msolservice -credential $msolcred
  
    Set-MsolCompanySettings -AllowEmailVerifiedUsers $false
* So aktivieren Sie den automatischen Mandantenbeitritt für neue Benutzer
  
    $msolcred = get-credential   connect-msolservice -credential $msolcred
  
    Set-MsolCompanySettings -AllowEmailVerifiedUsers $true

> [!NOTE]
> Diese Blockierung verhindert, dass sich neue Benutzer aus Ihrer Organisation für Power BI registrieren. Benutzer, die sich vor dem Deaktivieren neuer Registrierungen für Ihre Organisation für Power BI registriert haben, behalten ihre Lizenzen jedoch. Im Abschnitt [Wie kann ich Lizenzen entfernen?] finden Sie Anweisungen zum Aufheben des Zugriffs auf Power BI durch Benutzer, die sich zu einem früheren Zeitpunkt für den Dienst registriert haben.
> 
> 

### <a name="how-can-i-allow-users-to-join-my-existing-office-365-tenant"></a>Wie kann ich Benutzern erlauben, meinem vorhandenen Office 365-Mandanten beizutreten?
Um Benutzern den Beitritt zu Ihrem Mandanten zu erlauben, führen Sie den entgegengesetzten Befehl wie in der Frage oben aus.

Um die folgenden Schritte ausführen zu können, müssen Sie die neueste 64-Bit-Version des [Azure Active Directory-Moduls für Windows PowerShell](http://go.microsoft.com/fwlink/p/?LinkID=236297) installieren.

    $msolcred = get-credential
    connect-msolservice -credential $msolcred

    Set-MsolCompanySettings -AllowEmailVerifiedUsers $true

### <a name="how-do-i-verify-if-i-have-the-block-on-in-the-tenant"></a>Wie überprüfe ich, ob eine Sperre im Mandanten vorliegt?
Verwenden Sie das folgende PowerShell-Skript.

Um die folgenden Schritte ausführen zu können, müssen Sie die neueste 64-Bit-Version des [Azure Active Directory-Moduls für Windows PowerShell](http://go.microsoft.com/fwlink/p/?LinkID=236297) installieren.

    $msolcred = get-credential
    connect-msolservice -credential $msolcred

    Get-MsolCompanyInformation | fl allow*

### <a name="how-can-i-prevent-my-existing-users-from-starting-to-use-power-bi"></a>Wie kann ich verhindern, dass vorhandene Benutzer mit der Nutzung von Power BI beginnen?
Sie können als Administrator Schritte unternehmen, die verhindern, dass sich Benutzer für Power BI registrieren. Wenn Sie dies blockieren, können sich keine Benutzer registrieren. Sie werden stattdessen an den Administrator ihrer Organisation weitergeleitet. Sie müssen diesen Vorgang nicht wiederholen, wenn Sie die automatische Verteilung von Lizenzen (z. B. Office 365 Education für Studenten, Bildungseinrichtungen und Lehrpersonal) bereits deaktiviert haben. [Weitere Informationen](service-admin-service-free-in-your-organization.md#enable-or-disable-individual-user-sign-up-in-azure-active-directory)

Die entsprechende AAD-Einstellung heißt **AllowAdHocSubscriptions**. Bei den meisten Mandanten ist diese Einstellung auf „true“ festgelegt. Das bedeutet, dass sie aktiviert ist. Wenn Sie Power BI über einen Partner erworben haben, kann die Einstellung jedoch standardmäßig auf „false“ festgelegt sein, was bedeutet, dass sie deaktiviert ist.

Um die folgenden Schritte ausführen zu können, müssen Sie die neueste 64-Bit-Version des [Azure Active Directory-Moduls für Windows PowerShell](http://go.microsoft.com/fwlink/p/?LinkID=236297) installieren.

1. Sie müssen sich zuerst mithilfe Ihrer Office 365-Anmeldeinformationen bei Azure Active Directory anmelden. In der ersten Zeile werden Sie zur Eingabe Ihrer Anmeldeinformationen aufgefordert. Die zweite Zeile stellt die Verbindung mit Azure Active Directory her.
   
     $msolcred = get-credential   connect-msolservice -credential $msolcred
2. Nachdem Sie sich angemeldet haben, können Sie mit dem folgenden Befehl feststellen, wie Ihr Mandant derzeit konfiguriert ist.
   
     Get-MsolCompanyInformation | fl AllowAdHocSubscriptions
3. Mit dem folgenden Befehl können Sie AllowAdHocSubscriptions aktivieren ($true) oder deaktivieren ($false).
   
     Set-MsolCompanySettings -AllowAdHocSubscriptions $true

> [!NOTE]
> Das Flag AllowAdHocSubscriptions wird verwendet, um verschiedene Benutzeroptionen in Ihrer Organisation zu steuern, einschließlich der Möglichkeit, dass Benutzer sich beim Azure Rights Management Service registrieren können. Das Ändern dieses Flags wirkt sich auf alle Benutzeroptionen aus.
> 
> 

### <a name="how-can-i-allow-my-existing-users-to-sign-up-for-power-bi"></a>Wie kann ich meinen vorhandenen Benutzern erlauben, sich für Power BI zu registrieren?
Damit sich vorhandene Benutzer für Power BI registrieren können, führen Sie den Befehl für die oben aufgeführte Frage aus, übergeben aber TRUE anstelle von FALSE.

Um die folgenden Schritte ausführen zu können, müssen Sie die neueste 64-Bit-Version des [Azure Active Directory-Moduls für Windows PowerShell](http://go.microsoft.com/fwlink/p/?LinkID=236297) installieren.

1. Sie müssen sich zuerst mithilfe Ihrer Office 365-Anmeldeinformationen bei Azure Active Directory anmelden. In der ersten Zeile werden Sie zur Eingabe Ihrer Anmeldeinformationen aufgefordert. Die zweite Zeile stellt die Verbindung mit Azure Active Directory her.
   
     $msolcred = get-credential   connect-msolservice -credential $msolcred
2. Nachdem Sie sich angemeldet haben, können Sie mit dem folgenden Befehl feststellen, wie Ihr Mandant derzeit konfiguriert ist.
   
     Get-MsolCompanyInformation | fl AllowAdHocSubscriptions
3. Mit dem folgenden Befehl können Sie AllowAdHocSubscriptions aktivieren ($true) oder deaktivieren ($false).
   
     Set-MsolCompanySettings -AllowAdHocSubscriptions $true

> [!NOTE]
> Das Flag AllowAdHocSubscriptions wird verwendet, um verschiedene Benutzeroptionen in Ihrer Organisation zu steuern, einschließlich der Möglichkeit, dass Benutzer sich beim Azure Rights Management Service registrieren können. Das Ändern dieses Flags wirkt sich auf alle Benutzeroptionen aus.
> 
> 

## <a name="administration-of-power-bi"></a>Verwaltung von Power BI
### <a name="how-will-this-change-the-way-i-manage-identities-for-users-in-my-organization-today"></a>Wie ändert sich dadurch die Art und Weise, in der ich die Identitäten für Benutzer in meiner Organisation heute verwalte?
Wenn Ihre Organisation bereits über eine Office 365-Umgebung verfügt und alle Benutzer in der Organisation über Office 365-Konten verfügen, ergeben sich keine Änderungen an der Identitätsverwaltung.

Verfügt Ihre Organisation bereits über eine Office 365-Umgebung, in der jedoch nicht alle Benutzer mit einem Office 365-Konten ausgestattet sind, erstellen wir einen Benutzer im Mandanten und weisen Lizenzen anhand der Firmen- oder Schul-E-Mail-Adresse des Benutzers zu. Dies bedeutet, dass die Anzahl der von Ihnen verwalteten Benutzer zu einem bestimmten Zeitpunkt größer wird, wenn sich Benutzer in Ihrer Organisation für den Dienst registrieren.

Wenn Sie Ihr Verzeichnis lokal verwalten und Active Directory Federation Services (AD FS) verwenden, fügt Microsoft Ihrem Mandanten keine Benutzer hinzu. Dann erhalten Benutzer, die Ihrem Mandanten beizutreten versuchen, eine Nachricht, dass sie sich mit dem Administrator Ihrer Organisation in Verbindung setzen sollen.

Wenn Ihre Organisation nicht über eine Office 365-Umgebung verfügt, die mit Ihrer E-Mail-Domäne verbunden ist, ändert sich die Verwaltung der Identität für Sie nicht. Benutzer werden einem neuen, ausschließlich cloudseitigen Benutzerverzeichnis hinzugefügt, und Sie haben die Möglichkeit, als Mandantenadministrator deren Verwaltung zu übernehmen.

### <a name="how-do-we-manage-power-bi"></a>Wie verwalte ich Power BI?
Power BI bietet ein Verwaltungsportal, über das Sie Statistiken zur Verwendung anzeigen können. Es enthält auch einen Link zum Office 365 Admin Center für die Verwaltung von Benutzern und Gruppen und die Möglichkeit zur Steuerung von Einstellungen, die für den gesamten Mandanten gelten. 

> [!NOTE]
> Ihr Konto muss in Office 365 oder Azure Active Directory als **Globaler Administrator** markiert sein, damit Sie Zugriff auf das Power BI-Verwaltungsportal erhalten.
> 
> 

Weitere Informationen finden Sie unter [Power BI – Verwaltungsportal](service-admin-portal.md).

### <a name="what-is-the-process-to-manage-a-tenant-created-by-microsoft-for-my-users"></a>Was ist der Prozess zum Verwalten eines Mandanten, der von Microsoft für meine Benutzer erstellt wurde?
Wenn ein Mandant von Microsoft erstellt wurde, können Sie diesen mit den folgenden Schritten übernehmen und verwalten:

1. Treten Sie dem Mandanten bei, indem Sie sich für Power BI registrieren und dabei eine E-Mail-Adressdomäne verwenden, die der zu verwaltenden Mandantendomäne entspricht. Wenn Microsoft z.B. den Mandanten „contoso.com“ erstellt, müssen Sie dem Mandanten mit einer E-Mail-Adresse beitreten, die auf @contoso.com endet.
2. Sie übernehmen die Administratorsteuerung durch Bestätigung des Domänenbesitzes: Sobald Sie sich im Mandanten befinden, können Sie sich selbst zur Rolle *Globaler Administrator* heraufstufen, indem Sie den Domänenbesitz bestätigen. Führen Sie hierfür die folgenden Schritte aus:
   
   1. Wechseln Sie zu [https://portal.office.com](https://portal.office.com).
   2. Wählen Sie das App-Startsymbol in der linken oberen Ecke und dann **Admin** aus.
   3. Lesen Sie die Anweisungen auf der Seite **Become the admin** (Administrator werden), und wählen Sie dann **Yes, I want to be the admin** (Ja, ich möchte Administrator werden) aus.
      
      > [!NOTE]
      > Wenn diese Option nicht angezeigt wird, wurde bereits ein Office 365-Administrator festgelegt.
      > 
      > 

### <a name="if-i-have-multiple-domains-can-i-control-the-office-365-tenant-that-users-are-added-to"></a>Wenn ich mehrere Domänen habe, kann ich den Office 365-Mandanten steuern, dem Benutzer hinzugefügt werden?
Wenn Sie nichts unternehmen, wird ein Mandant für jede E-Mail-Domäne und -Unterdomäne für Benutzer erstellt.

Wenn sich alle Benutzer unabhängig von ihren E-Mail-Adresserweiterungen in demselben Mandanten befinden sollen, gehen Sie folgendermaßen vor:

* Erstellen Sie im Vorfeld einen Mandanten, oder verwenden Sie einen vorhandenen Mandanten, und fügen Sie alle vorhandenen Domänen und Subdomänen hinzu, die Sie in diesem Mandanten zusammenfassen möchten. Dann treten alle Benutzer mit E-Mail-Adressen, die auf diese Domänen und Subdomänen enden, beim Registrieren automatisch diesem Zielmandanten bei.

> [!IMPORTANT]
> Es werden keine automatisierten Verfahren zum Verschieben von bereits erstellten Benutzern zwischen Mandanten unterstützt. Informationen zum Hinzufügen von Domänen zu einem einzelnen Office 365-Mandanten finden Sie unter dem Thema zum [Hinzufügen von Benutzern und Domänen zu Office 365](https://support.office.com/article/Add-your-users-and-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).
> 
> 

### <a name="how-do-i-remove-power-bi-for-users-that-already-signed-up"></a>Wie entferne ich Power BI für Benutzer, die sich bereits registriert haben?
Wenn ein Benutzer sich für Power BI registriert hat, Sie aber nicht möchten, dass diese Person weiterhin Zugriff auf Power BI hat, können Sie die Power BI-Lizenz für diesen Benutzer entfernen.

1. Navigieren Sie zum Office 365 Admin Center.
2. Wählen Sie in der linken Navigationsleiste **Benutzer** > **Aktive Benutzer** aus.
3. Suchen Sie den Benutzer, dessen Lizenz Sie entfernen möchten, und klicken Sie auf dessen Namen und dann auf **Bearbeiten**.
4. Klicken Sie auf der Detailseite zum Benutzer in der linken Navigationsleiste auf **Lizenzen**.
5. Deaktivieren Sie **Power BI (Free)** oder **Power BI Pro**, je nachdem, welche Lizenz für das Konto angewendet wird.
6. Wählen Sie **Speichern**.

> [!NOTE]
> Sie können auch eine Batchverwaltung von Benutzerlizenzen durchführen. Wählen Sie dazu mehrere Benutzer und dann **Bearbeiten** aus.
> 
> 

### <a name="how-do-i-know-when-new-users-have-joined-my-tenant"></a>Wie erfahre ich, wenn meinem Mandanten neue Benutzer beigetreten sind?
Benutzern, die Ihrem Mandanten im Rahmen dieses Programms beigetreten sind, wird eine eindeutige Lizenz zugewiesen, nach der Sie innerhalb Ihres aktiven Benutzerbereichs im Verwaltungsdashboard filtern können.

Um diese neue Ansicht in Office 365 Admin Center zu erstellen, wechseln Sie zu **Benutzer** > **Aktive Benutzer** und wählen im Menü **Ansicht auswählen** die Option **Neue Ansicht** aus. Benennen Sie die neue Ansicht, und wählen Sie unter **Zugewiesene Lizenz** die Option **Power BI (Free)** oder **Power BI Pro** aus. Sie können nur eine Lizenz pro Ansicht auswählen. Wenn Sie in Ihrer Organisation über beide Lizenzen **Power BI (Free)** und **Power BI Pro** verfügen, müssen Sie zwei Ansichten erstellen. Nachdem die neue Ansicht erstellt wurde, können Sie alle Benutzer in Ihrem Mandanten anzeigen, die in diesem Programm registriert sind.

### <a name="are-there-any-additional-things-i-should-be-prepared-for"></a>Gibt es weitere Punkte, auf die ich vorbereitet sein sollte?
Es kann häufiger zur Anfragen zur Kennwortrücksetzung kommen. Weitere Informationen zu diesem Vorgang finden Sie unter [Zurücksetzen eines Benutzerkennworts in Office 365](https://support.office.com/article/Reset-a-users-password-7a5d073b-7fae-4aa5-8f96-9ecd041aba9c).

Sie können einen Benutzer über den Standardprozess im Office 365 Admin Center aus Ihrem Mandanten entfernen. Wenn der Benutzer jedoch weiterhin über eine aktive E-Mail-Adresse aus Ihrer Organisation verfügt, kann er erneut beitreten, es sei denn, Sie sperren den Beitritt für alle Benutzer.

### <a name="is-this-free-will-i-be-charged-for-these-licenses"></a>Ist es kostenlos? Werden für diese Lizenzen Gebühren berechnet?
Die Lizenzen **Power BI (Free)** gelten für die kostenlose Version von Power BI. Wenn Sie zusätzliche Funktionen benötigen, sehen Sie sich die [Version Power BI Pro](service-premium.md) an.

### <a name="where-is-my-power-bi-tenant-located"></a>Wo befindet sich mein Power BI-Mandant?
Informationen zum Ermitteln des Standorts Ihres Power BI-Mandanten (auch als Datenbereich bezeichnet) finden Sie unter [Wo befindet sich mein Power BI-Mandant?](service-admin-where-is-my-tenant-located.md)

### <a name="what-is-the-power-bi-sla"></a>Was ist das Power BI-SLA?
Informationen zum Power BI-SLA (Vereinbarung zum Servicelevel) finden Sie im Artikel zu [Lizenzierungsbedingungen und Dokumentation](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=37) im Abschnitt zu **Lizenzierung** auf der Microsoft Licensing-Website.

## <a name="security-in-power-bi"></a>Sicherheit in Power BI
### <a name="does-power-bi-meet-national-regional-and-industry-specific-compliance-requirements"></a>Erfüllt Power BI nationale, regionale und branchenspezifische Anforderungen an die Konformität?
Weitere Informationen zur Power BI-Konformität finden Sie im [Microsoft Trust Center](http://go.microsoft.com/fwlink/?LinkId=785324).

### <a name="how-does-security-work-in-power-bi"></a>Wie funktioniert die Sicherheit in Power BI?
Power BI basiert auf der Grundlage von Office 365, das wiederum auf Azure-Diensten wie Azure Active Directory basiert. Eine Übersicht über die Power BI-Architektur finden Sie unter [Sicherheit in Power BI](service-admin-power-bi-security.md). 

## <a name="next-steps"></a>Nächste Schritte
[Power BI-Verwaltungsportal](service-admin-portal.md)  
[Grundlegendes zur Power BI-Administratorrolle](service-admin-role.md)  
[Self-Service-Registrierung für Power BI](service-self-service-signup-for-power-bi.md)  
[Power BI Free in Ihrer Organisation](service-admin-service-free-in-your-organization.md)  
[Erwerb von Power BI Pro](service-admin-purchasing-power-bi-pro.md)  
[Power BI Premium – Beschreibung](service-premium.md)  
[Erwerben von Power BI Premium](service-admin-premium-purchase.md)  
[Office 365-Benutzerkontenverwaltung](https://technet.microsoft.com/library/office-365-user-account-management.aspx)  
[Office 365-Gruppenverwaltung](https://support.office.com/Article/Find-help-about-Groups-in-Office-365-7a9b321f-b76a-4d53-b98b-a2b0b7946de1)  
[Verwalten Ihrer Gruppe in Power BI und Office 365](service-manage-app-workspace-in-power-bi-and-office-365.md)  
[Power BI Premium-Whitepaper](https://aka.ms/pbipremiumwhitepaper)  

Weitere Fragen? [Stellen Sie Ihre Frage in der Power BI-Community.](http://community.powerbi.com/)

