---
title: Möglicherweise sind zusätzliche Käufe erforderlich. – Richtlinien für Power BI-Visuals
description: Erfahren Sie, wie Sie ein benutzerdefiniertes Visual in AppSource veröffentlichen, damit es von anderen gefunden und erworben werden kann.
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 11/26/2018
ms.openlocfilehash: 9ef7890c6f80845a9e6d1bd02e35778ed866ff54
ms.sourcegitcommit: 35d763dfc75c229204d36fd8b35c1e860786b707
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/27/2018
ms.locfileid: "52332157"
---
# <a name="guidelines-for-power-bi-visuals-with-additional-purchases"></a>Richtlinien für Power BI-Visuals mit zusätzlichen Käufen

Bis vor Kurzem wurden im **Marketplace (AppSource)** nur kostenlose Power BI-Visuals akzeptiert. Diese Richtlinie ändert sich, sodass Visuals mit dem Preistag „Möglicherweise sind zusätzliche Käufe erforderlich.“ auch an **AppSource** übermittelt werden können. Visuals, für die möglicherweise zusätzliche Käufe erforderlich sind, ähneln den Add-Ins mit In-App-Käufen, die im Office Store verfügbar sind. Entwickler können diese Visuals zudem zur Zertifizierung übermitteln, nachdem das **AppSource**-Team diese genehmigt hat und nachdem sichergestellt wurde, dass diese den Zertifizierungsanforderungen entsprechen. Dies wird im Artikel [Certified custom visuals (Zertifizierte benutzerdefinierte Visuals)](../power-bi-custom-visuals-certified.md) beschrieben.

> [!Note]
> Damit ein Visual zertifiziert werden kann, darf es nicht auf externe Dienste oder Ressourcen zugreifen.

## <a name="whats-changing-in-the-submission-process"></a>Was ändert sich am Übermittlungsprozess?

Entwickler laden ihre Visuals, die In-App-Käufe enthalten, genau wie kostenlose Visuals über das Seller-Dashboard in AppSource hoch. Damit deutlich ist, dass das übermittelte Visual In-App-Käufe enthält, sollten Entwickler im Seller-Dashboard den Verweis „Visual with in-app purchase.“ (Visual mit In-App-Käufen) hinzufügen. Entwickler müssen außerdem einen Lizenzschlüssel oder ein Token angeben, damit das entsprechende Team die In-App-Käufe überprüfen kann. Sobald das Visual überprüft und genehmigt wurde, wird in AppSource für das Visual der Hinweis „Möglicherweise sind zusätzliche Käufe erforderlich.“ in den Preisoptionen angezeigt.

## <a name="what-is-a-power-bi-visual-with-iap-features"></a>Was ist ein Power BI-Visual mit In-App-Käufen?

Bei einem Visual mit In-App-Käufen handelt es sich um ein kostenloses Visual mit kostenlosen Features handelt, für das jedoch zusätzliche Features erworben werden können. Die Benutzer müssen in der Beschreibung des Visuals darüber informiert werden, welche Features kostenpflichtig sind. Derzeit bietet Microsoft keine nativen Anwendungsprogrammierschnittstellen (APIs) an, die Käufe in Apps und Add-Ins unterstützen. Entwickler müssen ein Zahlungssystem von einem Drittanbieter für diese Käufe verwenden. Weitere Informationen finden Sie in unseren [Richtlinien für Stores](https://docs.microsoft.com/office/dev/store/validation-policies#2-apps-or-add-ins-can-display-certain-ads).

## <a name="logo-guidelines"></a>Richtlinien für Logos

In diesem Abschnitt werden die Spezifikationen für das Hinzufügen von Logos und Logotypen in Visuals erläutert.

> [!NOTE]
> Logos sind nur im Bearbeitungsmodus zulässig. Logos können im Anzeigemodus nicht dargestellt werden.

![Definitionen](media/office-store-in-app-purchase-visual-guidelines/definitions.png)

![Zu beachten](media/office-store-in-app-purchase-visual-guidelines/things-to-keep-in-mind.png)

![Zu vermeiden](media/office-store-in-app-purchase-visual-guidelines/things-to-avoid.png)

![Größe und Format ](media/office-store-in-app-purchase-visual-guidelines/size-and-format.png)

![Ränder und Größe](media/office-store-in-app-purchase-visual-guidelines/margins-and-sizes.png)

![Bearbeitungsmodus](media/office-store-in-app-purchase-visual-guidelines/logos-in-edit-mode.png)

## <a name="best-practices"></a>Bewährte Methoden

### <a name="visual-landing-page"></a>Startseite für Visuals

Verwenden Sie die Startseite, um den Benutzern zu verdeutlichen, wie sie Visuals verwenden und wo Lizenzen erworben werden können. Fügen Sie keine Videos ein, die automatisch abgespielt werden. Fügen Sie nur Inhalte hinzu, durch die die Verwendung benutzerfreundlicher wird, z.B. Informationen oder Links zu den Kaufdetails von Lizenzen und zum Einsatz von Features für In-App-Käufe.

### <a name="license-key-and-token"></a>Lizenzschlüssel und Token

Fügen Sie Felder für Lizenzschlüssel oder Token im oberen Teil des Formatierungsbereichs hinzu, sodass diese vom Benutzer leicht gefunden werden.

## <a name="next-steps"></a>Nächste Schritte

Erfahren Sie, wie Sie ein benutzerdefiniertes Visual in [AppSource](office-store.md) veröffentlichen, damit es von anderen gefunden und verwendet werden kann.
