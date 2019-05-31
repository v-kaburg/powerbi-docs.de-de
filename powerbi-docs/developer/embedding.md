---
title: Embedded Analytics mit Power BI
description: Power BI bietet APIs zum Verwenden von Embedded Analytics für Ihre Dashboards und Berichte in Anwendungen. In diesem Artikel erfahren Sie mehr über das Einbetten mit Power BI in einer PaaS-Umgebung und in einer SaaS-Umgebung unter Verwendung von Embedded Analytics-Software, Embedded Analytics-Tools oder eingebetteten Business Intelligence-Tools.
author: rkarlin
ms.author: rkarlin
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: overview
helpviewer_keywords:
- embedded analytics
- embedding
- Power BI embedding
- app owns data
- user owns data
- Power BI APIs
ms.custom: seodec18
ms.date: 05/15/2019
ms.openlocfilehash: a212691f2af877e3b86e021a4f48644f4fa6e8e3
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2019
ms.locfileid: "66051068"
---
# <a name="embedded-analytics-with-power-bi"></a>Embedded Analytics mit Power BI

Der Power BI-Dienst (SaaS) und der Power BI Embedded-Dienst in Azure (PaaS) verfügen über APIs zum Einbetten Ihrer Dashboards und Berichte. Beim Einbetten von Inhalten, haben Sie Zugriff auf die neuesten Power BI-Funktionen wie z. B. Dashboards, Gateways und app-Arbeitsbereiche.

Sie können mit dem [Einbettungssetuptool](https://aka.ms/embedsetup) schnell eine Beispielanwendung herunterladen und mit der Arbeit beginnen.

Wählen Sie die am besten für Sie geeignete Lösung aus:

* Das [Einbetten für Ihre Organisation](embedding.md#embedding-for-your-organization) ermöglicht Ihnen das Erweitern des Power BI-Diensts. Implementieren Sie zu diesem Zweck die [einbetten für Ihre Organisation](https://aka.ms/embedsetup/UserOwnsData) Lösung.
* [Einbetten für Ihre Kunden](embedding.md#embedding-for-your-customers) können Sie zum Einbetten von Dashboards und Berichte für Benutzer, die kein Power BI-Konto besitzen. Implementieren Sie zu diesem Zweck die [einbetten für Ihre Kunden](https://aka.ms/embedsetup/AppOwnsData) Lösung.

![PBIE-Beispiel](media/what-can-you-do/what-can-you-do-02.png)

## <a name="use-apis"></a>Verwenden von APIs

Es gibt zwei Hauptszenarien, für die Einbettung von Power BI-Inhalten:
- Einbetten für Benutzer in Ihrer Organisation (die Power BI-Lizenzen haben). 
 
- Einbetten für Ihre Benutzer und Kunden, die Power BI-Lizenzen nicht benötigen. 

Die [Power BI-REST-API](https://docs.microsoft.com/rest/api/power-bi/) ermöglicht beide Szenarien.

Für Kunden und Benutzer ohne Power BI-Lizenzen können Sie Dashboards und Berichte in Ihre benutzerdefinierte Anwendung einbetten und dabei für Ihre Organisation und Ihre Kunden die gleiche API verwenden. Ihre Kunden finden Sie unter der Anwendung verwaltet werden. Power BI-Benutzer Ihres Unternehmens haben außerdem zusätzliche Optionen zum Anzeigen von *ihre Daten* direkt in Power BI oder im Kontext der eingebetteten Anwendung. Sie können alle Funktionen der JavaScript- und REST-APIs für das Einbetten nutzen.

Zum Verständnis der Funktionsweise der Einbettung finden Sie unter den [JavaScript-einbettungsbeispiel](https://microsoft.github.io/PowerBI-JavaScript/demo/).

## <a name="embedding-for-your-organization"></a>Einbetten für Ihre Organisation

Das **Einbetten für Ihre Organisation** ermöglicht Ihnen das Erweitern des Power BI-Diensts. Einbetten von diesem erfordert Ihrer Anwendung Benutzer anmelden, in den Power BI-Dienst, um den Inhalt anzuzeigen. Nachdem sich ein Benutzer in Ihrer Organisation angemeldet hat, hat er nur Zugriff auf Dashboards und Berichte, deren Eigentümer er ist oder die für ihn im Power BI-Dienst freigegeben wurden.

Organisation einbetten Beispiele hierfür sind interne Anwendungen wie z. B. [SharePoint Online](https://powerbi.microsoft.com/blog/integrate-power-bi-reports-in-sharepoint-online/), [Microsoft Teams-Integration (Sie benötigen Administratorrechte)](https://powerbi.microsoft.com/blog/power-bi-teams-up-with-microsoft-teams/), und [Microsoft Dynamics](https://docs.microsoft.com/dynamics365/customer-engagement/basics/add-edit-power-bi-visualizations-dashboard).

Zum Einbetten für Ihre Organisation finden Sie unter [Lernprogramm: Einbetten von Power BI-Inhalten in eine Anwendung für Ihre Organisation](embed-sample-for-your-organization.md).

Self-Service-Funktionen wie Bearbeiten, Speichern usw. stehen bei der Einbettung für Power BI-Benutzer über die [JavaScript-API](https://github.com/Microsoft/PowerBI-JavaScript) zur Verfügung.

Können Sie die [Embedding Setuptool](https://aka.ms/embedsetup/UserOwnsData) zu beginnen, und Laden eine beispielanwendung, die Sie integrieren eines Berichts für Ihre Organisation erläutert.

## <a name="embedding-for-your-customers"></a>Einbetten für Ihre Kunden

**Einbetten für Ihre Kunden** ermöglicht Ihnen das Einbetten von Dashboards und Berichte für Benutzer, die kein Power BI-Konto besitzen. Ist diese einbetten, auch bekannt als *Power BI Embedded*.

[Power BI Embedded](azure-pbie-what-is-power-bi-embedded.md) ist eine **Microsoft Azure** Dienst mit dem unabhängige Softwarehersteller (ISVs) und Entwickler können schnell Visuals, Berichte und Dashboards in eine Anwendung einbetten. Einbetten von diesem erfolgt über ein kapazitätsbasiertes, stündlich gemessenen-Modell.

![Flussdiagramm des Einbettens für Ihre Kunden](media/embedding/powerbi-embed-flow.png)

Power BI Embedded bietet Vorteile für unabhängige Softwarehersteller, Entwickler und Kunden. Beispielsweise können unabhängige Softwarehersteller mit Power BI Desktop kostenlos Visuals erstellen. Durch Minimieren des Entwicklungsaufwands für visuelle Analyse, unabhängige Softwarehersteller, erreichen Sie eine schnellere markteinführung und abheben von Wettbewerbern mit differenzierten Datennutzung von Ihren. ISVs können auch entscheiden, um einen Aufpreis für den zusätzlichen Wert zu berechnen, die mit embedded Analytics erstellt.

Mit Power BI Embedded müssen Ihre Kunden gar nichts über Power BI wissen. Sie können zwei verschiedene Methoden zum Erstellen einer eingebetteten Anwendung verwenden:
- Power BI Pro-Konto 
- Dienstprinzipal 

Das Power BI Pro-Konto fungiert als Ihrer Anwendung Hauptkonto (Denken Sie dazu als ein Proxykonto an). Dieses Konto können Sie generieren embed-Token, die Zugriff auf Power BI-Dashboards und Berichte von Ihrer Anwendungsverzeichnis bereitstellen.

Der [Dienstprinzipal](embed-service-principal.md) kann Power BI-Inhalte mithilfe eines Tokens **nur für Anwendungen** in eine Anwendung einbetten. Außerdem können Sie zum Generieren embed-Token, die Zugriff auf Power BI-Dashboards und Berichte von Ihrer Anwendungsverzeichnis bereitstellen.

Entwickler, die mit Power BI Embedded können konzentriert sich auf die Erstellung ihrer Anwendung Kernfunktionen statt Ausgabenlimit Entwicklung von Visualisierungen und Analysen befassen. Sie können schnell Berichts- und kundenanforderungen zu erfüllen und die Einbettung wird durch dokumentierte APIs und SDKs. Durch das benutzerfreundliche Durchsuchen von Daten in Apps ermöglichen unabhängige Softwarehersteller ihren Kunden schnelle und datengesteuerte Entscheidungen – von jedem Gerät aus und kontextbezogen.

> [!IMPORTANT]
> Beim Einbetten von Power BI-Dienst erfordert, müssen Ihre Kunden nicht über ein Power BI-Konto Ihrer Anwendung eingebetteten Inhalt anzeigen verfügen. 

Wenn Sie bereit sind, in eine Produktionsumgebung zu wechseln, muss der Arbeitsbereich Ihrer App einer dedizierten Kapazität zugeordnet werden. Power BI Embedded in Microsoft Azure bietet [dedizierte Kapazitäten](azure-pbie-create-capacity.md), die von Ihren Anwendungen genutzt werden können.

Einbetten von Details, finden Sie unter [zum Einbetten von Power BI-Inhalten](embed-sample-for-customers.md).

## <a name="next-steps"></a>Nächste Schritte

Nun können Sie mit der Einbettung von Power BI-Inhalten in eine Anwendung oder Power BI-Inhalten für Ihre Kunden loslegen.

> [!div class="nextstepaction"]
> [Embed for your organization (Einbetten für Ihre Organisation)](embed-sample-for-your-organization.md)

> [!div class="nextstepaction"]
> [Was ist Power BI Embedded?](azure-pbie-what-is-power-bi-embedded.md)

> [!div class="nextstepaction"]
>[Inhalte für Ihre Kunden einbetten](embed-sample-for-customers.md)

Weitere Fragen? [Stellen Sie Ihre Frage in der Power BI-Community.](http://community.powerbi.com/)
