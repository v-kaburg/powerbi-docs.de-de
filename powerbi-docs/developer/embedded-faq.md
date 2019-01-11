---
title: Häufig gestellte Fragen zu Power BI Embedded
description: Durchsuchen Sie die Liste der häufig gestellten Fragen und Antworten zu Power BI Embedded.
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-developer
ms.topic: conceptual
ms.date: 12/20/2018
ms.openlocfilehash: 3971651caf9be7e754f4232ffec8b4e4dbfdfe6d
ms.sourcegitcommit: 750f0bfab02af24c8c72e6e9bbdd876e4a7399de
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/04/2019
ms.locfileid: "54008417"
---
# <a name="frequently-asked-questions-about-power-bi-embedded"></a>Häufig gestellte Fragen zu Power BI Embedded

* Wenn Sie weitere Fragen haben, [stellen Sie sie in der Power BI-Community](http://community.powerbi.com/).
* Treten weiterhin Probleme auf? Besuchen Sie die [Supportseite für Power BI](https://powerbi.microsoft.com/support/).

## <a name="general"></a>Allgemein

### <a name="what-is-power-bi-embedded"></a>Was ist Power BI Embedded?

Mit Microsoft Power BI Embedded (PBIE) können Anwendungsentwickler ansprechende, vollständig interaktive Berichte in Anwendungen einbetten, ohne selbst Datenvisualisierungen und Steuerelemente von Grund auf neu erstellen zu müssen.

### <a name="who-is-the-target-audience-for-power-bi-embedded"></a>Für wen ist Power BI Embedded gedacht?

Entwickler und Softwarehersteller, die als unabhängige Softwarehersteller (ISVs) eigene Anwendungen entwickeln.

### <a name="how-is-power-bi-embedded-different-from-power-bi-the-service"></a>Worin unterscheidet sich Power BI Embedded vom Power BI-Dienst?

Power BI Embedded richtet sich an ISVs oder Entwickler, die Anwendungen erstellen und in diese Anwendungen Visuals einbetten möchten, um ihren Kunden Entscheidungen zu erleichtern, ohne eine Analyselösung von Grund auf entwickeln zu müssen. Eingebettete Datenanalysen ermöglichen Geschäftskunden den Zugriff auf Unternehmensdaten und die Ausführung von Abfragen, um anhand dieser Daten in der Anwendung Erkenntnisse zu gewinnen.

Power BI ist eine Software-as-a-Service-Analyselösung, die Organisationen eine zentrale Ansicht ihrer wichtigsten Geschäftsdaten bietet.

### <a name="what-is-the-difference-between-power-bi-premium-and-power-bi-embedded"></a>Worin unterscheidet sich Power BI Premium von Power BI Embedded?

Power BI Premium unterstützt Kapazitäten, wie sie von Unternehmen benötigt werden, die eine umfassende BI-Lösung mit einer zentralen Ansicht ihrer Organisation, ihrer Partner, Kunden und Zulieferer suchen. Power BI Premium unterstützt Ihr Unternehmen bei der Entscheidungsfindung. Power BI Premium ist ein SaaS-Produkt und ermöglicht Benutzern die Verarbeitung von Inhalten über das Power BI-Portal, die mobile App und intern entwickelte Apps.

Power BI Embedded ist für ISVs und Entwickler gedacht, die Anwendungen erstellen, in die Visuals eingebettet werden sollen. Power BI Embedded unterstützt Ihre Kunden bei der Entscheidungsfindung, und da Power BI Embedded auf Anwendungsentwickler ausgerichtet ist, können diese Kunden der Anwendung und beliebige Benutzer innerhalb und außerhalb der Organisation Inhalte verarbeiten, die in der Power BI Embedded-Kapazität gespeichert sind. Inhalte in der Power BI Embedded-Kapazität können nicht einfach per Mausklick im Web oder auf SharePoint veröffentlicht werden. SSRS-Berichte werden ebenfalls nicht unterstützt.

### <a name="what-is-the-microsoft-recommendation-for-when-a-customer-should-buy-power-bi-premium-vs-power-bi-embedded"></a>Welche Empfehlungen gibt Microsoft Kunden für die Entscheidung zwischen Power BI Premium und Power BI Embedded?

Microsoft empfiehlt, dass Unternehmen Power BI Premium kaufen – eine für Unternehmen entwickelte Cloud-BI-Lösung mit Self-Service. ISVs sollten sich für die cloudgestützten eingebetteten Analysekomponenten von Power BI Embedded entscheiden. Es gibt jedoch keine Einschränkungen für Kunden beim Kauf eines der Produkte.

In bestimmten Fällen empfiehlt sich eine P-SKU für einen (in der Regel großen) ISV, um von den Vorteilen des vorkonfigurierten Power BI-Diensts in seiner Organisation sowie von der Möglichkeit der Einbettung in eigene Anwendungen profitieren zu können. Einige Unternehmen entscheiden sich für A-SKUs in Azure, wenn sie nur Branchenanwendungen erstellen und Analysefunktionen in diese einbetten möchten und kein Interesse daran haben, den vorkonfigurierten Power BI-Dienst zu nutzen.

### <a name="how-many-embed-tokens-can-i-create"></a>Wie viele Einbettungstokens kann ich erstellen?

Da Einbettungstokens mit einer PRO-Lizenz nur für Bereitstellungen und das Testen von Bereitstellungen vorgesehen sind, ist die Anzahl von Einbettungstokens limitiert, die ein Power BI-Hauptkonto generieren kann. Sie müssen [eine Kapazität erwerben](#technical), um Einbettungen in einer Produktionsumgebung vornehmen zu können. Wenn eine Kapazität erworben wird, gibt es keine Einschränkungen hinsichtlich der Anzahl von Einbettungstokens, die generiert werden können. Verwenden Sie die Vorgänge zum Abrufen [verfügbarer Features](https://docs.microsoft.com/rest/api/power-bi/availablefeatures), um den Auslastungswert zu überprüfen, der die derzeit eingebettete Auslastung in Prozent angibt.

## <a name="technical"></a>Technische Fragen

### <a name="what-is-the-difference-between-the-a-skus-in-azure-and-the-em-skus-in-office-365"></a>Worin unterscheiden sich die A-SKUs in Azure von den EM-SKUs in Office 365?

PowerBI.com ist eine Unternehmenslösung, die eine Vielzahl von Funktionen in einem Software-as-a-Service-Produkt zusammenfasst, z.B. Zusammenarbeit im sozialen Netzwerk und E-Mail-Abonnements.

Power BI Embedded umfasst eine Reihe von APIs, mit der Entwickler eine eingebettete Analyselösung in einem Platform-as-a-Service-Produkt erstellen können. Im Embedded-Analyseszenario sollten ISVs und Entwickler PowerBI.com heranziehen, um die Inhalte der eingebetteten Analyselösung und Einstellungen auf Mandantenebene zu verwalten.

Es folgt eine Liste mit einer Auswahl der Unterschiede.

| Ausgewählt | Power BI Embedded | Power BI Premium-Kapazität | Power BI Premium-Kapazität |
|----------------------------------------------------------------------------------|-------------------|---------------------------|---------------------------|
|   | (A-SKUs) | (EM-SKUs) | (P-SKUs) |
| Artefakte aus Power BI-App-Arbeitsbereich einbetten | Azure-Kapazität | Office 365-Kapazität | Office 365-Kapazität |
| Power BI-Berichte in einer Embedded-Anwendung nutzen | Ja | Ja | Ja |
| Power BI-Berichte in SharePoint nutzen | Nein | Ja | Ja |
| Power BI-Berichte in Dynamics nutzen | Nein | Ja | Ja |
| Power BI-Berichte in Teams nutzen (keine mobile App) | Nein | Ja | Ja |
| Mit einer kostenlosen Power BI-Lizenz auf Inhalte unter Powerbi.com und Power BI Mobile zugreifen | Nein | Nein | Ja |
| Mit einer kostenlosen Power BI-Lizenz auf in Microsoft Office-Apps eingebettete Inhalte zugreifen | Nein | Ja | Ja |

### <a name="power-bi-now-offers-three-skus-for-embedding-a-skus-em-skus-and-p-skus-which-one-should-i-purchase-for-my-scenario"></a>Power BI bietet jetzt drei SKUs für die Einbettung: A-SKUs, EM-SKUs und P-SKUs. Welche SKU ist für mein Szenario optimal?

|  |A-SKU (Power BI Embedded)  |EM-SKU (Power BI Premium)  |P-SKU (Power BI Premium)  |
|---------|---------|---------|---------|
|Purchase  |Azure-Portal |Office |Office |
|Anwendungsfälle | Einbetten von Inhalten in Ihre eigene Anwendung | <li> Einbetten von Inhalten in Ihre eigene Anwendung <br><br></br> <li> Einbetten von Inhalten in MS Office-Anwendungen: <br> - [SharePoint](https://powerbi.microsoft.com/blog/integrate-power-bi-reports-in-sharepoint-online/) <br> - [Teams (keine mobile App)](https://powerbi.microsoft.com/blog/power-bi-teams-up-with-microsoft-teams/) <br> - [Dynamics 365](https://docs.microsoft.com/dynamics365/customer-engagement/basics/add-edit-power-bi-visualizations-dashboard) | <li> Einbetten von Inhalten in Ihre eigene Anwendung <br><br></br> <li> Einbetten von Inhalten in MS Office-Anwendungen: <br> - [SharePoint](https://powerbi.microsoft.com/blog/integrate-power-bi-reports-in-sharepoint-online/) <br> - [Teams (keine mobile App)](https://powerbi.microsoft.com/blog/power-bi-teams-up-with-microsoft-teams/) <br> - [Dynamics 365](https://docs.microsoft.com/dynamics365/customer-engagement/basics/add-edit-power-bi-visualizations-dashboard) <br><br></br> <li> Freigeben von Inhalten für Benutzer von Power BI über den [Power BI-Dienst](https://powerbi.microsoft.com/en-us/)  |
|Abrechnung |Stündlich |Monatlich |Monatlich |
|Vertragsbindung  |Keine Vertragsbindung |Jährlich  |Monatlich/jährlich |
|Differenzierung |Vollständige Elastizität: vertikale Skalierung, Anhalten/Fortsetzen von Ressourcen im Azure-Portal oder über die API  |Möglichkeit zum Einbetten von Inhalten in SharePoint Online und Microsoft Teams (keine mobile App) |Kombination von Einbettung in Anwendungen und Verwendung des Power BI-Diensts mit der gleichen Kapazität |

### <a name="what-are-the-prerequisites-to-create-a-pbie-capacity-in-azure"></a>Was sind die Voraussetzungen zum Erstellen einer PBIE-Kapazität in Azure?

* Sie müssen sich bei Ihrem Organisationsverzeichnis anmelden (MSA-Konten werden nicht unterstützt).
* Sie müssen über einen Power BI-Mandanten verfügen, d.h. mindestens ein Benutzer in Ihrem Verzeichnis muss bei Power BI registriert sein. 
* Sie müssen über ein Azure-Abonnement in Ihrem Organisationsverzeichnis verfügen.

### <a name="how-can-i-monitor-power-bi-embedded-capacity-consumption"></a>Überwachen der Kapazitätsnutzung von Power BI Embedded

* Verwenden Sie dazu das [Power BI Admin-Portal](../service-admin-portal.md#power-bi-embedded).

* Herunterladen der [Metrik-App](https://review.docs.microsoft.com/power-bi/service-admin-premium-monitor-capacity) in Power BI.

* Mithilfe von [Azure-Diagnoseprotokollierung](azure-pbie-diag-logs.md).

### <a name="will-my-capacity-scale-automatically-to-adjust-to-the-consumption-of-my-app"></a>Wird meine Kapazität automatisch an die Nutzung meiner App angepasst?

Derzeit wird zwar keine automatische Skalierung unterstützt, für alle APIs ist jedoch jederzeit eine Skalierung verfügbar.

### <a name="why-creatingscalingresuming-a-capacity-results-in-putting-the-capacity-into-a-suspended-state"></a>Weshalb führt das Erstellen/Skalieren/Fortsetzen einer Kapazität dazu, dass die Kapazität suspendiert wird?

Die Bereitstellung einer Kapazität (Skalieren/Fortsetzen/Erstellen) kann fehlschlagen. Der Aufrufer eines Bereitstellungsaufrufs sollte den Bereitstellungsstatus einer Kapazität mit der API für Details prüfen: [Kapazitäten: Abrufen von Details](https://docs.microsoft.com/rest/api/power-bi-embedded/capacities/getdetails).

### <a name="why-can-i-only-create-pbie-in-a-specific-region"></a>Warum kann ich Power BI Embedded-Kapazitäten nur in einer spezifischen Region erstellen?

Sie können Power BI Embedded-Kapazitäten nur für die Region Ihres Power BI-Mandanten erstellen.

### <a name="how-can-i-find-what-is-my-pbi-tenant-region"></a>Wie finde ich meine Power BI-Region heraus?

Über das Power BI-Portal können Sie erfahren, was Ihrer Power BI-Region ist.

Navigieren Sie zu https://app.powerbi.com/ > ? > Info

![Info](media/embedded-faq/about-01.png)
![Mandanten-Region](media/embedded-faq/tenant-location-01.png)

### <a name="what-is-supported-with-the-cloud-solution-provider-csp-channel"></a>Wofür kann ich den Cloud Solution Provider-Kanal (CSO) nutzen?

* Sie können die Power BI Embedded-Kapazität für Ihren Mandanten mit einem CSP-Abonnement erstellen.
* Partnerkonten können sich beim Kundenmandanten anmelden, Power BI Embedded für diesen erwerben und einen Kundenmandanten als Administrator der Power BI-Kapazität festlegen.

### <a name="why-do-i-get-an-unsupported-account-message"></a>Weshalb erhalte ich eine Meldung, die besagt, dass mein Konto nicht unterstützt wird?

Sie müssen sich in Power BI mit einem Unternehmenskonto anmelden. Eine Anmeldung bei Power BI mit einem Microsoft-Konto wird nicht unterstützt.

### <a name="can-i-use-apis-to-create--manage-azure-capacities"></a>Kann ich Azure-Kapazitäten mit APIs erstellen und verwalten?

Ja, es gibt PowerShell-Cmdlets und Azure Resource Manager-APIs, mit denen Sie Power BI Embedded-Ressourcen erstellen und verwalten können.

* REST-APIs: https://docs.microsoft.com/rest/api/power-bi-embedded/
* PowerShell-Cmdlets: https://docs.microsoft.com/powershell/module/azurerm.powerbiembedded/

### <a name="what-is-the-pbi-embedded-dedicated-capacity-role-in-a-pbi-embedded-solution"></a>Was ist die Power BI Embedded-Rolle „Dedizierte Kapazität“ in einer Power BI Embedded-Lösung?

Zur [Höherstufung Ihrer Lösung in die Produktion](https://docs.microsoft.com/power-bi/developer/embedding-content#step-3-promote-your-solution-to-production) muss der Power BI-Inhalt (der App-Arbeitsbereich, den Sie in Ihrer Anwendung verwenden) einer Power BI Embedded-Kapazität (A-SKU) zugewiesen werden.

### <a name="what-are-the-azure-regions-pbi-embedded-is-available"></a>In welchen Azure-Regionen ist Power BI Embedded verfügbar?

[PAM](https://ecosystemmanager.azurewebsites.net/home) (EcoManager): Weitere Informationen im Manager zur Produktverfügbarkeit

Verfügbare Regionen (16, die gleichen Regionen wie Power BI)

* USA (6): USA, Osten; USA, Osten 2; USA, Norden-Mitte; USA, Süden-Mitte; USA, Westen; USA, Westen 2
* Europa (2): Europa, Norden; Europa, Westen
* Asien-Pazifik (2): Asien, Südosten; Asien, Osten
* Brasilien (1): Brasilien, Süden
* Japan (1): Japan, Osten
* Australien (1): Australien, Südosten
* Indien (1): Indien, Westen
* Kanada (1): Kanada, Mitte
* Vereinigtes Königreich (1): Vereinigtes Königreich, Süden

### <a name="what-is-the-authentication-model-for-power-bi-embedded"></a>Welches Authentifizierungsmodell wird für Power BI Embedded verwendet?

Für Power BI Embedded wird weiterhin Azure AD für die Authentifizierung des Masterbenutzers (ein designierter Benutzer mit Power BI Pro-Lizenz) verwendet, der die Anwendung in Power BI authentifiziert.

Authentifizierung und Autorisierung der Anwendungsbenutzer werden vom ISV implementiert. Der ISV kann für seine Anwendungen eigene Authentifizierungsfunktionen implementieren.

Wenn Sie bereits über einen Azure AD-Mandanten verfügen, können Sie das vorhandene Verzeichnis verwenden oder einen neuen Azure AD-Mandanten zum Schutz der Inhalte in der Embedded-Anwendung erstellen.

Um ein AAD-Token abzurufen, können Sie eine der Azure Active Directory-Authentifizierungsbibliotheken verwenden: https://docs.microsoft.com/azure/active-directory/develop/active-directory-authentication-libraries. Es sind Clientbibliotheken für mehrere Plattformen verfügbar.

### <a name="my-application-already-uses-aad-for-user-authentication-how-can-we-use-this-identity-when-authenticating-to-power-bi-in-an-user-owns-data-scenario"></a>Meine Anwendung verwendet bereits AAD für die Benutzerauthentifizierung Wie kann ich diese Identität bei der Authentifizierung in Power BI in einem Szenario einsetzen, in dem der Benutzer die Daten besitzt?

In einem standardmäßigen OAuth-Flow im Namen des Benutzers (https://docs.microsoft.com/azure/active-directory/develop/active-directory-authentication-scenarios#web-application-to-web-api). Die Anwendung muss so konfiguriert sein, dass sie Berechtigungen des Power BI-Diensts (für die erforderlichen Bereiche) erfordert. Sobald Sie ein Benutzerzugriffstoken für Ihre App haben, führen Sie mit diesem Token einen Aufruf an ADAL API AcquireTokenAsync durch und geben die Power BI-Ressourcen-URL als Ressourcen-ID an. Unten sehen Sie einen Codeausschnitt, der dies veranschaulicht:

```csharp
var context = new AD.AuthenticationContext(authorityUrl);
var userAssertion = new AD.UserAssertion(userAccessToken);
var clientAssertion = new AD.ClientAssertionCertificate(MyAppId, MyAppCertificate)
var authenticationResult = await context.AcquireTokenAsync(resourceId, clientAssertion, userAssertion);
```

### <a name="how-is-power-bi-embedded-different-from-other-azure-services"></a>Worin unterscheidet sich Power BI Embedded von anderen Azure-Diensten?

Der ISV/Entwickler benötigt vor dem Kauf von Power BI Embedded in Azure ein Power BI-Konto. Ihre Power BI Embedded-Bereitstellungsregion richtet sich nach Ihrem Power BI-Konto. Verwalten Sie Ihre Power BI Embedded-Ressource in Azure:

* Vertikale Skalierung
* Hinzufügen von Kapazitätsadministratoren
* Anhalten/Fortsetzen des Diensts

Verwenden Sie powerbi.com, um Ihrer Power BI Embedded-Kapazität Arbeitsbereiche zuzuweisen bzw. die Zuweisung aufzuheben.

### <a name="what-deploy-regions-are-supported"></a>Welche Bereitstellungsregionen werden unterstützt?

Australien, Südosten; Brasilien, Süden; Kanada, Mitte; USA, Osten 2; Indien, Westen; Japan, Osten; USA, Norden-Mitte; Europa, Norden; USA, Süden-Mitte; Asien, Südosten; Vereinigtes Königreich, Süden; Europa, Westen; USA, Westen; USA, Westen 2.

### <a name="what-type-of-content-pack-data-can-be-embedded"></a>Welche Art von Inhaltspaketdaten kann eingebettet werden?

Aus Inhaltspaket-Datasets erstellte **Dashboards** und **Kacheln** *können nicht* integriert werden; jedoch**können** aus einem Inhaltspaket-Dataset erstellte *Berichte* integriert werden.

### <a name="what-is-the-difference-between-using-rls-vs-javascript-filters"></a>Worin besteht der Unterschied zwischen der Verwendung von RLS und JavaScript-Filtern?

Zuweilen herrscht Verwirrung darüber, wann RLS und wann JavaScript-Filter verwendet werden sollten. Bei der einen Methode wird gesteuert, was ein bestimmter Benutzer sehen darf, bei der anderen geht es um die Optimierung der Ansicht des Benutzers.

Bei RLS steuert der ISV-Entwickler die Datenfilterung im Rahmen der Modellerstellung und Generierung des Einbettungstokens. Der Endbenutzer sieht nur die Daten, deren Anzeige der ISV dem Benutzer gestattet. In diesem Fall kann der Benutzer zwar weniger Daten anzeigen als durch den Filter zulässig, aber er kann die RLS-Konfiguration nicht umgehen und mehr Daten anzeigen als erlaubt.

Bei der clientseitigen Filterung (JavaScript) kann der ISV entscheiden, welche Daten dem Benutzer in der anfänglichen Ansicht angezeigt werden, der ISV kann aber nicht die Änderungen steuern, die der Endbenutzer selbst auf die Ansicht anwendet. Auch wenn die Datenfilterung im Back-End erfolgen kann, wird sie durch JavaScript-Clientcode ausgelöst und kann daher durch einen Endbenutzer geändert werden. Aus diesem Grund kann diese Methode nicht als sicher betrachtet werden.

Weitere Details finden Sie unter [Verwenden von RLS im Vergleich zu JavaScript-Filtern](embedded-row-level-security.md#using-rls-vs-javascript-filters).

## <a name="licensing"></a>Lizenzierung

### <a name="how-do-i-purchase-power-bi-embedded"></a>Wie erwerbe ich Power BI Embedded?

Power BI Embedded ist über Azure erhältlich.

### <a name="what-happens-if-i-already-purchased-power-bi-premium-and-now-i-want-some-of-the-benefits-of-power-bi-embedded-in-azure"></a>Was geschieht, wenn ich Power BI Premium bereits erworben und jetzt einige der Vorteile von Power BI Embedded in Azure nutzen möchte?

Kunden zahlen bis zum Ende der Laufzeit ihrer aktuellen Vereinbarung weiterhin für erworbene Power BI Premium-Lizenzen und können dann ihre Power BI Premium-Lizenzen nach Bedarf umstellen.

### <a name="do-i-still-have-to-buy-power-bi-premium-to-get-access-to-power-bi-embedded"></a>Muss ich Power BI Premium trotzdem erwerben, um auf Power BI Embedded zugreifen zu können?

Nein, Power BI Embedded umfasst die auf Azure basierende Kapazität, die Sie zum Bereitstellen und Verteilen Ihrer Lösung für Kunden benötigen.

### <a name="whats-the-purchase-commitment-for-power-bi-embedded"></a>Welche Verpflichtung ist mit dem Kauf von Power BI Embedded verbunden?

Kunden können ihre Nutzung auf Stundenbasis anpassen. Es gibt keine monatliche oder jährliche Verpflichtung für den Power BI Embedded-Dienst.

### <a name="how-does-the-usage-of-power-bi-embedded-show-up-on-my-bill"></a>Wie wird die Nutzung von Power BI Embedded auf meiner Rechnung aufgeführt?

Power BI Embedded wird nach einem feststehenden Stundensatz abgerechnet, der vom Typ der bereitgestellten Knoten abhängt. Solange eine Ressource aktiv ist, fallen Kosten an, auch wenn Sie die Ressource nicht nutzen. Sie müssen Ihre Ressource manuell anhalten, damit keine Kosten mehr anfallen.

### <a name="who-needs-a-power-bi-pro-license-for-power-bi-embedded-and-why"></a>Wer benötigt aus welchen Gründen eine Power BI Pro-Lizenz für Power BI Embedded?

Alle Analytiker, die Berichte einem Power BI-Arbeitsbereich hinzufügen müssen, alle Entwickler, die REST-APIs verwenden müssen, alle Mandantenadministratoren, die den Power BI-Mandanten und die entsprechende Kapazität verwalten müssen, benötigen eine Power BI Pro-Lizenz.

Da Power BI Embedded die Verwendung des Power BI-Portals zum Verwalten und Überprüfen eingebetteter Inhalte erlaubt, ist die Power BI Pro-Lizenz erforderlich, um die App auf powerbi.com zu authentifizieren und um Zugriff auf die Berichte in den richtigen Repositorys zu erhalten.

Allerdings benötigt der Endbenutzer keine Pro-Lizenz, um in Ihrer eigenen Anwendung [eingebettete Berichte erstellen oder bearbeiten](https://github.com/Microsoft/PowerBI-JavaScript/wiki/Create-Report-in-Embed-View) zu können, da er kein Power BI-Benutzer sein muss.

### <a name="can-i-get-started-for-free"></a>Ist ein kostenloser Einstieg möglich?

Ja, Sie können eine [Azure-Gutschrift](https://azure.microsoft.com/free/) für Power BI Embedded verwenden.

### <a name="can-i-get-a-trial-experience-for-power-bi-embedded-in-azure"></a>Ist eine Testversion von Power BI Embedded in Azure erhältlich?

Da Power BI Embedded Teil von Azure ist, können Sie den Dienst mit der [bei der Registrierung bei Azure erhaltenen 200-USD-Gutschrift](https://azure.microsoft.com/free/) verwenden.

### <a name="is-power-bi-embedded-available-for-sovereign-clouds-us-government-germany-china"></a>Ist Power BI Embedded für unabhängige Clouds (US-Behörden, Deutschland, China) verfügbar?

Power BI Embedded ist für einige [unabhängige Clouds](embed-sample-for-customers-sovereign-clouds.md) verfügbar. Es ist noch **NICHT** für die China-Cloud verfügbar.

### <a name="is-power-bi-embedded-available-for-non-profits-and-educational"></a>Ist Power BI Embedded für Non-Profit-Organisationen und Bildungseinrichtungen erhältlich?

Non-Profit-Organisationen und Bildungseinrichtungen können Azure erwerben. Für diese Arten von Kunden gibt es in Azure keine Sonderpreise.

## <a name="power-bi-workspace-collection"></a>Power BI-Arbeitsbereichssammlung

### <a name="what-is-power-bi-workspace-collection"></a>Was ist eine Power BI-Arbeitsbereichssammlung?

**Power BI-Arbeitsbereichssammlung** (**Power BI Embedded** Version 1) ist eine Lösung, die auf der Azure-Ressource **Power BI-Arbeitsbereichssammlung** basiert. Mit dieser Lösung können Sie **Power BI Embedded**-Anwendungen für Ihre Kunden erstellen. Dabei verwenden Sie Power BI-Inhalte in der Lösung **Power BI-Arbeitsbereichssammlung**, dedizierte APIs und Schlüssel für die Arbeitsbereichssammlung, um die Anwendung bei Power BI zu authentifizieren.

### <a name="can-i-migrate-from-power-bi-workspace-collection-to-power-bi-embedded"></a>Kann ich eine Power BI-Arbeitsbereichssammlung zu Power BI Embedded migrieren?

1. Sie können das Migrationstool verwenden, um Inhalte einer **Power BI-Arbeitsbereichssammlung** in Power BI zu klonen: https://docs.microsoft.com/power-bi/developer/migrate-from-powerbi-embedded#content-migration.

2. Beginnen Sie mit dem Anwendungs-PoC für **Power BI Embedded**, der Power BI-Inhalte verwendet.

3. Wenn Sie bereits sind für den Produktionsbetrieb, erwerben Sie eine dedizierte **Power BI Embedded**-Kapazität und weisen Sie dieser Ihre Power BI-Inhalte (Arbeitsbereich) zu.

> [!Note]
> Sie können die **Power BI-Arbeitsbereichssammlung** weiter nutzen, während Sie parallel eine **Power BI Embedded**-Lösung für die Entwicklung verwenden. Sobald Sie bereit sind, können Sie Ihren Kunden zur neuen **Power BI Embedded**-Lösung verlagern und die **Power BI-Arbeitsbereichssammlung** außer Betrieb nehmen.

Weitere Informationen dazu finden Sie unter [Migrieren von Inhalten aus der Power BI-Arbeitsbereichssammlung zu Power BI Embedded](https://docs.microsoft.com/power-bi/developer/migrate-from-powerbi-embedded).

### <a name="is-power-bi-workspace-collection-on-a-path-to-be-deprecated"></a>Werden Power BI-Arbeitsbereichssammlungen demnächst eingestellt?

Ja, aber Kunden, die bereits eine **Power BI-Arbeitsbereichssammlung** verwenden, können diese weiter nutzen, bis sie eingestellt wird. Kunden können auch neue Arbeitsbereichssammlungen sowie **Power BI Embedded**-Anwendungen erstellen, die weiterhin die Lösung **Power BI-Arbeitsbereichssammlung** verwenden.

Allerdings werden **Power BI-Arbeitsbereichssammlungen** keine neuen Features mehr hinzugefügt, und Kunden sollten ihre Migration zur neuen **Power BI Embedded**-Lösung planen.

### <a name="when-will-power-bi-workspace-collection-support-be-discontinued"></a>Wann wird der Support für Power BI-Arbeitsbereichssammlung eingestellt?

Kunden, die die Lösung **Power BI-Arbeitsbereichssammlungen** bereits nutzen, können diese bis Ende Juni 2018 oder bis zum Ende ihrer Supportvereinbarung weiterhin verwenden.

### <a name="in-what-regions-can-pbi-workspace-collection-be-created"></a>In welchen Regionen können Power BI-Arbeitsbereichssammlungen erstellt werden?

Folgende Regionen sind verfügbar: Australien, Südosten; Brasilien, Süden; Kanada, Mitte; USA, Osten 2; Japan, Osten; USA, Norden-Mitte; Europa, Norden; USA, Süden-Mitte; Asien, Südosten; Vereinigtes Königreich, Süden; Europa, Westen; Indien, Westen und USA, Westen.

### <a name="why-should-i-migrate-from-pbi-workspace-collection-to-power-bi-embedded"></a>Warum sollte ich eine Power BI-Arbeitsbereichssammlung zu Power BI Embedded migrieren?

In der **Power BI Embedded**-Lösung wurden neue Features und Funktionen eingeführt, die in der **Power BI-Arbeitsbereichssammlung** nicht verfügbar sind.

Dies sind einige dieser Features:

* Alle Power BI-Datenquellen werden unterstützt. In einer **Power BI-Arbeitsbereichssammlung** werden dagegen nur zwei Datenquellen unterstützt. 
* Neue Features wie Q&A, Aktualisieren, Lesezeichen, Einbetten von Dashboards und Kacheln, benutzerdefinierte Menüs usw. werden nur in der Lösung **Power BI Embedded** unterstützt.
* Kapazitätsbasiertes Abrechnungsmodell.

## <a name="embedding-setup-tool"></a>Einbettungssetuptool

### <a name="what-is-the-embedding-setup-tool"></a>Was ist das Einbettungssetuptool?

Mit dem [Einbettungssetuptool](https://aka.ms/embedsetup) können Sie schnell einsteigen und eine Beispielanwendung herunterladen, um mit dem Einbetten mit Power BI zu beginnen.

### <a name="which-solution-should-i-choose"></a>Welche Lösung soll ich verwenden?

* Das [Einbetten für Ihre Kunden](embedding.md#embedding-for-your-customers) bietet die Möglichkeit, Dashboards und Berichte für Benutzer einzubetten, die nicht über ein Konto für Power BI verfügen. Führen Sie die Lösung [Einbetten für Ihre Kunden](https://aka.ms/embedsetup/AppOwnsData) aus.
* Das [Einbetten für Ihre Organisation](embedding.md#embedding-for-your-organization) ermöglicht Ihnen das Erweitern des Power BI-Diensts. Führen Sie die Lösung [Einbetten für Ihre Organisation](https://aka.ms/embedsetup/UserOwnsData) aus.

### <a name="ive-downloaded-the-sample-app-which-solution-do-i-choose"></a>Ich habe die Beispiel-App heruntergeladen. Welche Lösung soll ich verwenden?

Wenn Sie mit dem Szenario **Einbetten für Ihre Kunden arbeiten**, speichern und entzippen Sie die Datei *PowerBI-Developer-Samples.zip*. Öffnen Sie anschließend den Ordner *PowerBI-Developer-Samples-master\App Owns Data*, und führen Sie die Datei *PowerBIEmbedded_AppOwnsData.sln* aus.

Wenn Sie mit dem Szenario **Einbetten für Ihre Organisation arbeiten**, speichern und entzippen Sie die Datei *PowerBI-Developer-Samples.zip*. Öffnen Sie dann den Ordner *PowerBI-Developer-Samples-master\User Owns Data\integrate-report-web-app*, und führen Sie die Datei *pbi-saas-embed-report.sln* aus.

### <a name="how-can-i-edit-my-registered-application"></a>Wie kann ich meine registrierte Anwendung bearbeiten?

[Hier](https://docs.microsoft.com/azure/active-directory/develop/active-directory-integrating-applications#updating-an-application) lernen Sie, wie Sie mit AAD registrierte Anwendungen bearbeiten können.

### <a name="how-can-i-edit-my-power-bi-user-profile-or-data"></a>Wie kann ich mein Power BI-Benutzerprofil bzw. meine Power BI-Benutzerdaten bearbeiten?

[Hier](https://docs.microsoft.com/power-bi/service-basic-concepts) erfahren Sie, wie Sie Ihre Power BI-Daten bearbeiten.

Weitere Informationen finden Sie unter [Problembehandlung bei Embedded-Anwendungen](embedded-troubleshoot.md).

Weitere Fragen? [Wenden Sie sich an die Power BI-Community](http://community.powerbi.com/)

### <a name="what-are-the-best-practices-to-improve-performance"></a>Welche bewährten Methoden zur Verbesserung der Leistung gibt es?

[Leistung von Power BI Embedded](embedded-performance-best-practices.md)