---
title: Einbetten mit Power BI
description: Power BI bietet APIs zum Einbetten von Dashboards und Berichten in Anwendungen.
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-developer
ms.topic: overview
ms.date: 07/20/2018
ms.author: maghan
ms.openlocfilehash: ac7d31ed35bd6b58d19864b3476db4852a92e66b
ms.sourcegitcommit: 3a287ae4ab16d1e76caed651bd8ae1a1738831cd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/19/2018
ms.locfileid: "39157169"
---
# <a name="embedding-with-power-bi"></a>Einbetten mit Power BI
Der Power BI-Dienst (SaaS) und der Power BI Embedded-Dienst in Azure (PaaS) verfügen über APIs zum Einbetten Ihrer Dashboards und Berichte. Dies bedeutet, dass Ihnen eine ganze Reihe von Funktionen und Zugriff auf die neuesten Power BI-Features – z.B. Dashboards, Gateways und App-Arbeitsbereiche – zur Verfügung stehen, wenn Sie Inhalte einbetten.

Sie können mit dem [Tool mit Onboardingfunktionen](https://aka.ms/embedsetup) schnell eine Beispielanwendung herunterladen und mit der Arbeit beginnen.

Wählen Sie die am besten für Sie geeignete Lösung aus:

* Das [Einbetten für Ihre Organisation](embedding.md#embedding-for-your-organization) ermöglicht Ihnen das Erweitern des Power BI-Diensts. Führen Sie die Lösung [Einbetten für Ihre Organisation](https://aka.ms/embedsetup/UserOwnsData) aus.
* Das [Einbetten für Ihre Kunden](embedding.md#embedding-for-your-customers) bietet die Möglichkeit, Dashboards und Berichte für Benutzer einzubetten, die nicht über ein Konto für Power BI verfügen. Führen Sie die Lösung [Einbetten für Ihre Kunden](https://aka.ms/embedsetup/AppOwnsData) aus.

![PBIE-Beispiel](media/what-can-you-do/what-can-you-do-02.png)

## <a name="using-apis"></a>Verwendung von APIs
Beim Einbetten von Power BI-Inhalten gibt es hauptsächlich zwei Szenarien.  Das Einbetten für Benutzer in Ihrer Organisation (die Lizenzen für Power BI haben) und das Einbetten für Benutzer und Kunden, ohne dass diese über Power BI-Lizenzen verfügen müssen. Die Power BI-REST-API ermöglicht beide Szenarien.

Für Kunden und Benutzer ohne Power BI-Lizenzen können Sie Dashboards und Berichte in Ihre benutzerdefinierte Anwendung einbetten und dabei für Ihre Organisation und Ihre Kunden die gleiche API verwenden. Die Kunden sehen so die Daten, die von der Anwendung verwaltet werden. Für Power BI-Benutzer in Ihrer Organisation besteht außerdem zusätzlich die Möglichkeit, *ihre Daten* direkt in Power BI oder im Kontext der eingebetteten Anwendung anzuzeigen. Sie können alle Funktionen der JavaScript- und REST-APIs für das Einbetten nutzen.

Ein Beispiel für die Funktionsweise der Einbettung finden Sie im [JavaScript-Einbettungsbeispiel](https://microsoft.github.io/PowerBI-JavaScript/demo/).

## <a name="embedding-for-your-organization"></a>Einbetten für Ihre Organisation
Das Einbetten für Ihre Organisation ermöglicht Ihnen das Erweitern des Power BI-Diensts. Dafür ist erforderlich, dass sich die Benutzer Ihrer Anwendung beim Power BI-Dienst anmelden, wenn sie ihre Inhalte anzeigen möchten. Nachdem sich ein Benutzer in Ihrer Organisation angemeldet hat, besitzt er nur Zugriff auf Dashboards und Berichte, deren Eigentümer er ist oder die für ihn im Power BI-Dienst freigegeben wurden.

*Beispiele für das Einbetten in Ihre Organisation umfassen interne Webanwendungen, das SharePoint Online-Webpart und die [Microsoft Teams-Integration (Sie müssen über Administratorrechte verfügen)](https://powerbi.microsoft.com/en-us/blog/power-bi-teams-up-with-microsoft-teams/).*

Informationen zum Einbetten für Ihre Organisation finden Sie in den folgenden Artikeln:

* [Integrieren eines Berichts in eine App](embed-sample-for-your-organization.md)

Self-Service-Funktionen, wie Bearbeiten, Speichern und mehr, stehen bei der Einbettung für Power BI-Benutzer über die [JavaScript-API](https://github.com/Microsoft/PowerBI-JavaScript) zur Verfügung.

Sie können sich mit dem [Tool mit Onboardingfunktionen](https://aka.ms/embedsetup/UserOwnsData) vertraut machen, um den Einstieg zu beschleunigen und eine Beispielanwendung herunterzuladen, die sie durch die Integration eines Berichts für Ihre Organisation führt.

## <a name="embedding-for-your-customers"></a>Einbetten für Ihre Kunden
Das Einbetten für Ihre Kunden bietet die Möglichkeit, Dashboards und Berichte für Benutzer einzubetten, die nicht über ein Konto für Power BI verfügen. Ihre Kunden brauchen gar nichts über Power BI zu wissen. Es wird mindestens ein Power BI Pro-Konto benötigt, um eine eingebettete Anwendung zu erstellen. Das Power BI Pro-Konto fungiert als Masterkonto für Ihre Anwendung. Stellen Sie es sich als eine Art Proxykonto vor. Mit dem Power BI Pro-Konto können Sie außerdem Einbettungstoken generieren, die Zugriff auf die Dashboards und Berichte im Power BI-Dienst bieten, die von Ihrer Anwendung verwaltet werden bzw. die diese besitzt.

*Ein Beispiel für das Einbetten für Ihre Kunden ist eine ISV-Anwendung, die an andere Unternehmen verkauft wird.*

![Flussdiagramm des Einbettens für Ihre Kunden](media/embedding/powerbi-embed-flow.png)

Zum Einbetten von Dashboards, Berichten und Kacheln verwenden Sie die gleichen APIs, die Sie zum Einbetten für Ihre Organisation verwenden würden.

> [!IMPORTANT]
> Beim Einbetten besteht zwar eine Abhängigkeit vom Power BI-Dienst, für Ihre Kunden besteht aber keine Abhängigkeit von Power BI. Sie müssen sich nicht für Power BI registrieren, um die eingebetteten Inhalte in der Anwendung anzuzeigen.

Wenn Sie bereit sind, in eine Produktionsumgebung zu wechseln, muss der Arbeitsbereichs Ihrer App einer dedizierten Kapazität zugewiesen werden. Power BI Embedded in Microsoft Azure bietet dedizierte Kapazitäten, die von Ihren Anwendungen genutzt werden können.

Details zur Einbettung finden Sie unter [Einbetten von Power BI-Dashboards, -Berichten und -Kacheln](embedding-content.md).

Sie können sich mit dem [Tool mit Onboardingfunktionen](https://aka.ms/embedsetup/AppOwnsData) vertraut machen, um Ihren Einstieg zu beschleunigen und eine Beispielanwendung herunterzuladen, die sie durch die Integration eines Berichts in Ihre Anwendung führt.

Wenn Sie bereits den Dienst Power BI-Arbeitsbereichssammlungen in Azure verwendet haben, finden Sie unter [Migrieren von Inhalten aus Power BI Embedded-Arbeitsbereichssammlungen zu Power BI](migrate-from-powerbi-embedded.md) Informationen zum Migrieren Ihrer Inhalte.

## <a name="next-steps"></a>Nächste Schritte
Nun können Sie mit der Einbettung von Power BI-Inhalten in eine Anwendung oder Power BI-Inhalten für Ihre Kunden loslegen.

> [!div class="nextstepaction"]
> [Embed for your organization (Einbetten für Ihre Organisation)](embed-sample-for-your-organization.md)

> [!div class="nextstepaction"]
>[Inhalte für Ihre Kunden einbetten](embed-sample-for-customers.md)

Weitere Fragen? [Stellen Sie Ihre Frage in der Power BI-Community.](http://community.powerbi.com/)