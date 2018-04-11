---
title: Konfigurieren mobiler Apps mit Microsoft Intune
description: Informationen zum Konfigurieren der mobilen Power BI-Apps mit Microsoft Intune Dies umfasst das Hinzufügen und Bereitstellen der Anwendung sowie das Erstellen der Richtlinie für mobile Anwendungen zum Kontrollieren der Sicherheit.
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
ms.tgt_pltfrm: na
ms.workload: powerbi
ms.date: 06/28/2017
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: c33fcbdfa93e38283e17b0842e1242634664be7a
ms.sourcegitcommit: 8552a34df8e6141eb704314c1a019992901d6e78
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2018
---
# <a name="configure-mobile-apps-with-microsoft-intune"></a>Konfigurieren mobiler Apps mit Microsoft Intune
Microsoft Intune ermöglicht Organisationen das Verwalten von Geräten und Anwendungen. Die mobilen Power BI-Anwendungen für iOS und Android lassen sich in Intune integrieren, damit Sie die Anwendung auf Ihren Geräten verwalten und die Sicherheit kontrollieren können. Über Konfigurationsrichtlinien können Sie Einstellungen steuern, z. B. eine Zugriffs-PIN anfordern, festlegen, wie Daten von der Anwendung verarbeitet werden, und sogar Anwendungsdaten verschlüsseln, wenn die App nicht genutzt wird.

<iframe width="560" height="315" src="https://www.youtube.com/embed/9HF-qsdQvHw?list=PLv2BtOtLblH1nPVPU2etFzTNmpz49dwXm" frameborder="0" allowfullscreen></iframe>

## <a name="general-mobile-device-management-configuration"></a>Allgemeine Konfiguration für die Mobilgerätverwaltung
Dieser Artikel dient nicht als vollständiges Konfigurationshandbuch für Microsoft Intune. Wenn Sie dabei sind, die Integration in Intune zu aktivieren, gibt es einige Dinge, die eingerichtet sein sollten. [Weitere Informationen](https://technet.microsoft.com/library/jj676587.aspx)

Microsoft Intune und die Mobilgerätverwaltung (Mobile Device Management, MDM) in Office 365 können parallel genutzt werden. [Weitere Informationen](https://blogs.technet.microsoft.com/configmgrdogs/2016/01/04/microsoft-intune-co-existence-with-mdm-for-office-365/)

In diesem Artikel wird davon ausgegangen, dass Intune ordnungsgemäß konfiguriert ist und Geräte bei Intune registriert sind. Bei paralleler Nutzung mit MDM wird das Gerät als bei MDM registriert angezeigt, steht aber zum Verwalten in Intune zur Verfügung.

> [!NOTE]
> Nachdem Ihre Organisation Microsoft Intune MAM konfiguriert hat, ist die Datenaktualisierung im Hintergrund bei Verwendung der mobilen Power BI-App auf einem iOS- oder Android-Gerät deaktiviert. Power BI aktualisiert die Daten über den Power BI-Dienst im Web, wenn Sie das nächste Mal die App aufrufen.
> 
> 

## <a name="step-1-get-the-url-for-the-application"></a>Schritt 1: Abrufen der URL der Anwendung
Bevor wir die Anwendung in Intune erstellen, müssen wir die URLs der Apps abrufen. Für iOS erfolgt dies über iTunes. Für Android können Sie die URL von der mobilen Power BI-Seite abrufen.

Speichern Sie die URL, da Sie sie benötigen, wenn wir die Anwendung erstellen.

### <a name="ios"></a>iOS
Die App-URL für iOS müssen wir aus iTunes abrufen.

1. Öffnen Sie iTunes.
2. Suchen Sie nach *Power BI*.
3. **Microsoft Power BI** sollte unter **iPhone-Apps** und **iPad-Apps**aufgeführt sein. Sie können beide Varianten verwenden, da Sie die gleiche URL erhalten.
4. Wählen Sie die Dropdownliste **Abrufen** und dann **Link kopieren**aus.
   
    ![](media/service-admin-mobile-intune/itunes-url.png)

Die Ansicht sollte ungefähr wie folgt aussehen.

    https://itunes.apple.com/us/app/microsoft-power-bi/id929738808?mt=8

### <a name="android"></a>Android
Sie rufen die URL zu Google Play von der [mobilen Power BI-Website](https://powerbi.microsoft.com/mobile/) ab. Durch Klicken auf das Symbol **Von Google Play herunterladen** gelangen Sie zur Seite „App“. Kopieren Sie die URL aus der Adressleiste des Browsers. Die Ansicht sollte ungefähr wie folgt aussehen.

    https://play.google.com/store/apps/details?id=com.microsoft.powerbim

## <a name="step-2-create-a-mobile-application-management-policy"></a>Schritt 2: Erstellen einer Richtlinie für die Verwaltung mobiler Anwendungen
Die Richtlinie für die Verwaltung mobiler Anwendungen ermöglicht Ihnen das Erzwingen von Einstellungen, z. B. einer Zugriffs-PIN. Sie können eine im Intune-Portal erstellen. 

Sie können zunächst die Anwendung oder die Richtlinie erstellen. Die Reihenfolge des Hinzufügens spielt keine Rolle. Beide müssen vorhanden sein, damit der Bereitstellungsschritt erfolgen kann.

1. Wählen Sie **Richtlinie** > **Konfigurationsrichtlinien** aus.
   
    ![](media/service-admin-mobile-intune/intune-policy.png)
2. Wählen Sie **Hinzufügen**aus.
3. Unter **Software** können Sie die Mobilgeräteverwaltung (MDM) entweder für Android oder iOS auswählen. Für den Schnelleinstieg können Sie **Richtlinie mit den empfohlenen Einstellungen erstellen**  auswählen. Sie können auch eine benutzerdefinierte Richtlinie erstellen.
4. Bearbeiten Sie die Richtlinie, indem Sie die gewünschten Einschränkungen für die Anwendung konfigurieren.

## <a name="step-3-create-the-application"></a>Schritt 3: Erstellen der Anwendung
Die Anwendung ist ein Verweis oder Paket, der/das für die Bereitstellung in Intune gespeichert wird. Wir müssen eine Anwendung erstellen und auf die App-URL verweisen, die wir von Google Play oder iTunes erhalten haben.

Sie können zunächst die Anwendung oder die Richtlinie erstellen. Die Reihenfolge des Hinzufügens spielt keine Rolle. Beide müssen vorhanden sein, damit der Bereitstellungsschritt erfolgen kann.

1. Wählen Sie im Intune-Portal im linken Menü **Apps** aus.
2. Wählen Sie **App hinzufügen**aus. Hierdurch wird die Anwendung **Software hinzufügen** gestartet.

### <a name="ios"></a>iOS
1. Wählen Sie in der Dropdownliste **Verwaltete iOS-App aus dem App Store** aus.
2. Geben Sie die App-URL ein, die wir aus [Schritt 1](#step-1-get-the-url-for-the-application) erhalten haben, und wählen Sie **Weiter** aus.
   
    ![](media/service-admin-mobile-intune/intune-add-software-ios1.png)
3. Füllen Sie die Felder **Herausgeber**, **Name** und **Beschreibung**aus. Sie können optional ein **Symbol**bereitstellen. Die **Kategorie** ist für die Unternehmensportal-App gedacht. Sobald Sie fertig sind, wählen Sie **Weiter**aus.
4. Sie können entscheiden, ob Sie die Anwendung als **Alle** (Standard), **iPad** oder **iPhone**veröffentlichen möchten. **Alle** wird standardmäßig angezeigt und funktioniert für beide Gerätetypen. Die URL der Power BI-App ist für iPhone und iPad identisch. Wählen Sie **Weiter**aus.
5. Wählen Sie **Hochladen**aus.

> [!NOTE]
> Die App wird ggf. erst nach einem Aktualisieren der Seite in der App-Liste angezeigt. Sie können auf **Übersicht** und dann wieder auf **Apps** klicken, um die Seite neu zu laden.
> 
> 

![](media/service-admin-mobile-intune/intune-add-software-ios2.png)

### <a name="android"></a>Android
1. Wählen Sie in der Dropdownliste **Externer Link** aus.
2. Geben Sie die App-URL ein, die wir aus [Schritt 1](#step-1-get-the-url-for-the-application) erhalten haben, und wählen Sie **Weiter** aus.
   
    ![](media/service-admin-mobile-intune/intune-add-software-android1.png)
3. Füllen Sie die Felder **Herausgeber**, **Name** und **Beschreibung**aus. Sie können optional ein **Symbol**bereitstellen. Die **Kategorie** ist für die Unternehmensportal-App gedacht. Sobald Sie fertig sind, wählen Sie **Weiter**aus.
4. Wählen Sie **Hochladen**aus.

> [!NOTE]
> Die App wird ggf. erst nach einem Aktualisieren der Seite in der App-Liste angezeigt. Sie können auf **Übersicht** und dann wieder auf **Apps** klicken, um die Seite neu zu laden.
> 
> 

![](media/service-admin-mobile-intune/intune-add-software-android2.png)

## <a name="step-4-deploy-the-application"></a>Schritt 4: Bereitstellen der Anwendung
Nachdem Sie die Anwendung hinzugefügt haben, müssen Sie sie bereitstellen, damit sie Endbenutzern zur Verfügung steht. In diesem Schritt stellen Sie die Bindung mit der Richtlinie her, die Sie mit der App erstellt haben.

### <a name="ios"></a>iOS
1. Wählen Sie auf dem Bildschirm „Apps“ die App aus. Wählen Sie dann den Link **Bereitstellung verwalten** aus.
   
    ![](media/service-admin-mobile-intune/intune-deploy-ios1.png)
2. Auf dem Bildschirm **Gruppen auswählen** können Sie wählen, welchen Gruppen Sie diese App bereitstellen möchten. Wählen Sie **Weiter**aus.
3. Auf dem Bildschirm **Bereitstellungsaktion** können Sie wählen, wie Sie diese App bereitstellen möchten. Bei Auswahl von **Verfügbare Installation**oder **Erforderliche Installation**wird die App Benutzern für eine bedarfsabhängige Installation im Unternehmensportal zur Verfügung gestellt. Wenn Sie Ihre Auswahl getroffen haben, wählen Sie **Weiter**aus.
   
    ![](media/service-admin-mobile-intune/intune-deploy-ios2.png)
4. Auf dem Bildschirm **Mobile App-Verwaltung** können Sie die Verwaltungsrichtlinie für mobile Apps auswählen, die wir in [Schritt 2](#step-2-create-a-mobile-application-management-policy) erstellt haben. Falls dies die einzige verfügbare iOS-Richtlinie ist, wird sie standardmäßig ausgewählt. Wählen Sie **Weiter**aus.
   
    ![](media/service-admin-mobile-intune/intune-deploy-ios3.png)
5. Auf dem Bildschirm **VPN-Profil** können Sie eine Richtlinie auswählen, falls es eine für Ihre Organisation gibt. Der Standardwert lautet **Keine**. Wählen Sie **Weiter**aus.
6. Auf dem Bildschirm **Mobile App-Konfiguration** können Sie eine **App-Konfigurationsrichtlinie** auswählen, sofern Sie eine erstellt haben. Der Standardwert lautet **Keine**. Dies ist nicht erforderlich. Wählen Sie **Fertig stellen**aus.

Nachdem Sie die App bereitgestellt haben, sollte auf der Seite „Apps“ für „Bereitgestellt“ **Ja** angezeigt werden.

### <a name="android"></a>Android
1. Wählen Sie auf dem Bildschirm „Apps“ die App aus. Wählen Sie dann den Link **Bereitstellung verwalten** aus.
   
    ![](media/service-admin-mobile-intune/intune-deploy-android1.png)
2. Auf dem Bildschirm **Gruppen auswählen** können Sie wählen, welchen Gruppen Sie diese App bereitstellen möchten. Wählen Sie **Weiter**aus.
3. Auf dem Bildschirm **Bereitstellungsaktion** können Sie wählen, wie Sie diese App bereitstellen möchten. Bei Auswahl von **Verfügbare Installation**oder **Erforderliche Installation**wird die App Benutzern für eine bedarfsabhängige Installation im Unternehmensportal zur Verfügung gestellt. Wenn Sie Ihre Auswahl getroffen haben, wählen Sie **Weiter**aus.
   
    ![](media/service-admin-mobile-intune/intune-deploy-android2.png)
4. Auf dem Bildschirm **Mobile App-Verwaltung** können Sie die Verwaltungsrichtlinie für mobile Apps auswählen, die wir in [Schritt 2](#step-2-create-a-mobile-application-management-policy) erstellt haben. Falls dies die einzige verfügbare Android-Richtlinie ist, wird sie standardmäßig ausgewählt. Wählen Sie **Fertig stellen**aus.
   
    ![](media/service-admin-mobile-intune/intune-deploy-android3.png)

Nachdem Sie die App bereitgestellt haben, sollte auf der Seite „Apps“ für „Bereitgestellt“ **Ja** angezeigt werden.

## <a name="step-5-install-the-application-on-a-device"></a>Schritt 5: Installieren der Anwendung auf einem Gerät
Sie installieren die Anwendung über die Unternehmensportal-App. Wenn Sie das Unternehmensportal nicht installiert haben, können Sie es über den App Store für entweder die iOS- oder die Android-Plattform abrufen. Sie melden sich mit den Anmeldeinformationen Ihrer Organisation am Unternehmensportal an.

1. Öffnen Sie die Unternehmensportal-App.
2. Wenn die Power BI-App nicht als empfohlene App angezeigt wird, wählen Sie **Unternehmens-Apps**aus.
   
    ![](media/service-admin-mobile-intune/intune-companyportal1.png)
3. Wählen Sie die Power BI-App aus, die Sie bereitgestellt haben.
   
    ![](media/service-admin-mobile-intune/intune-companyportal2.png)
4. Wählen Sie **Installieren**aus.
   
    ![](media/service-admin-mobile-intune/intune-companyportal3.png)
5. Wenn Sie iOS nutzen, wird die App per Push für Sie übertragen. Wählen Sie im Dialogfeld „Push“ **Installieren** aus.
   
    ![](media/service-admin-mobile-intune/intune-companyportal5.png)

Nachdem sie installiert ist, wird Sie als **Von Ihrem Unternehmen verwaltet**angezeigt. Wenn Sie in der Richtlinie den Zugriff per PIN aktiviert haben, wird Folgendes angezeigt.

![](media/service-admin-mobile-intune/intune-powerbi-pin.png)

## <a name="next-steps"></a>Nächste Schritte
[Konfigurieren und Bereitstellen von Richtlinien zur Verwaltung mobiler Anwendungen in der Microsoft Intune-Konsole](https://technet.microsoft.com/library/dn878026.aspx)  
[Power BI-Apps für mobile Geräte](mobile-apps-for-mobile-devices.md)  

Weitere Fragen? [Stellen Sie Ihre Frage in der Power BI-Community.](http://community.powerbi.com/)

