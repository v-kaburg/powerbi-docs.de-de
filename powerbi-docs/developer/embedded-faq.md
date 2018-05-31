---
title: Häufig gestellte Fragen zu Power BI Embedded
description: Durchsuchen Sie die Liste der häufig gestellten Fragen und Antworten zu Power BI Embedded.
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-developer
ms.topic: conceptual
ms.date: 04/23/2018
ms.author: maghan
ms.openlocfilehash: 255efac5d5bf73bca3126f869d4c7434d5c6ef0f
ms.sourcegitcommit: 638de55f996d177063561b36d95c8c71ea7af3ed
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/17/2018
ms.locfileid: "34289738"
---
# <a name="frequently-asked-questions-about-power-bi-embedded"></a>Häufig gestellte Fragen zu Power BI Embedded

* Wenn Sie weitere Fragen haben, [stellen Sie sie in der Power BI-Community](http://community.powerbi.com/).
* Treten weiterhin Probleme auf? Weitere Informationen finden Sie auf der [Supportseite für Power BI](https://powerbi.microsoft.com/support/).

## <a name="general"></a>General

### <a name="what-is-power-bi-embedded"></a>Was ist Power BI Embedded?

Mit Microsoft Power BI Embedded können Anwendungsentwickler ansprechende, vollständig interaktive Berichte, Dashboards und Kacheln in Anwendungen einbetten, ohne eigene Datenvisualisierungen und Steuerelemente von Grund auf erstellen zu müssen.

### <a name="who-is-the-target-audience-for-power-bi-embedded"></a>Für wen ist Power BI Embedded gedacht?

Entwickler und Softwarehersteller, die als unabhängige Softwarehersteller (ISVs) eigene Anwendungen entwickeln.

### <a name="how-is-power-bi-embedded-different-from-power-bi-the-service"></a>Worin unterscheidet sich Power BI Embedded vom Power BI-Dienst?

Power BI Embedded richtet sich an ISVs oder Entwickler, die Anwendungen erstellen und in diese Anwendungen Visuals einbetten möchten, um ihren Kunden Entscheidungen zu erleichtern, ohne eine Analyselösung von Grund auf entwickeln zu müssen. Eingebettete Datenanalysen ermöglichen Geschäftskunden den Zugriff auf Unternehmensdaten und die Ausführung von Abfragen, um anhand dieser Daten in der Anwendung Erkenntnisse zu gewinnen.

Power BI ist hingegen eine Software-as-a-Service-Analyselösung, die Organisationen eine zentrale Ansicht ihrer wichtigsten Geschäftsdaten bietet.

### <a name="what-is-the-difference-between-power-bi-premium-and-power-bi-embedded"></a>Worin unterscheidet sich Power BI Premium von Power BI Embedded?

Power BI Premium unterstützt Kapazitäten, wie sie von Unternehmen benötigt werden, die eine umfassende BI-Lösung mit einer zentralen Ansicht ihrer Organisation, ihrer Partner, Kunden und Zulieferer suchen. Power BI Premium unterstützt Ihr Unternehmen bei der Entscheidungsfindung. Power BI Premium ist ein SaaS-Produkt und ermöglicht Benutzern die Verarbeitung von Inhalten über das Power BI-Portal, die mobile App und intern entwickelte Apps.

Power BI Embedded ist für ISVs und Entwickler gedacht, die Anwendungen erstellen, in die Visuals eingebettet werden sollen. Power BI Embedded unterstützt Ihre Kunden bei der Entscheidungsfindung, und da Power BI Embedded auf Anwendungsentwickler ausgerichtet ist, können diese Kunden der Anwendung und beliebige Benutzer innerhalb und außerhalb der Organisation Inhalte verarbeiten, die in der Power BI Embedded-Kapazität gespeichert sind. Inhalte in der Power BI Embedded-Kapazität können nicht über einen einfachen Mausklick im Web oder auf SharePoint veröffentlicht werden. SSRS-Berichte werden ebenfalls nicht unterstützt.

### <a name="what-is-the-microsoft-recommendation-for-when-a-customer-should-buy-power-bi-premium-vs-power-bi-embedded"></a>Welche Empfehlungen gibt Microsoft Kunden für die Entscheidung zwischen Power BI Premium und Power BI Embedded?

Microsoft empfiehlt, dass Unternehmen Power BI Premium kaufen – eine für Unternehmen entwickelte Cloud-BI-Lösung mit Self-Service. ISVs sollten sich für die cloudgestützten eingebetteten Analysekomponenten von Power BI Embedded entscheiden. Es gibt jedoch keine Einschränkungen für Kunden beim Kauf eines der Produkte.

In bestimmten Fällen empfiehlt sich eine P-SKU für einen (in der Regel großen) ISV, um von den Vorteilen des vorkonfigurierten Power BI-Diensts in seiner Organisation sowie von der Möglichkeit der Einbettung in eigene Anwendungen profitieren zu können. Natürlich werden sich einige Unternehmen für A-SKUs in Azure entscheiden, wenn es ihr Hauptinteresse ist, Branchenanwendungen zu erstellen und Analysefunktionen in diese einzubetten, und weniger, den vorkonfigurierten Power BI-Dienst zu nutzen.

### <a name="how-many-embed-tokens-can-i-create"></a>Wie viele Einbettungstokens kann ich erstellen?

Da Einbettungstokens mit einer PRO-Lizenz nur für Bereitstellungen und das Testen von Bereitstellungen vorgesehen sind, ist die Anzahl von Einbettungstokens limitiert, die ein Power BI-Hauptkonto generieren kann. Sie müssen [eine Kapazität erwerben](#technical), um Einbettungen in einer Produktionsumgebung vornehmen zu können. Wenn eine Kapazität erworben wird, gibt es keine Einschränkungen dafür, wie viele Einbettungstokens generiert werden können. Wechseln Sie zu [Get Available Features](https://msdn.microsoft.com/library/mt846473.aspx) (Verfügbare Features abrufen), um den Nutzungswert zu überprüfen, der die aktuelle Nutzung der Einbettung in Prozent angibt.

## <a name="technical"></a>Technische Fragen

### <a name="what-is-the-difference-between-the-a-skus-in-azure-and-the-em-skus-in-office-365"></a>Worin unterscheiden sich die A-SKUs in Azure von den EM-SKUs in Office 365?

PowerBI.com ist eine Unternehmenslösung, die eine Vielzahl von Funktionen in einem Software-as-a-Service-Produkt zusammenfasst, z.B. Zusammenarbeit im sozialen Netzwerk und E-Mail-Abonnements.

Power BI Embedded umfasst eine Reihe von APIs, mit der Entwickler eine eingebettete Analyselösung in einem Platform-as-a-Service-Produkt erstellen können. Im Embedded-Analyseszenario sollten ISVs und Entwickler PowerBI.com heranziehen, um die Inhalte der eingebetteten Analyselösung und Einstellungen auf Mandantenebene zu verwalten.

Es folgt eine Liste mit einer Auswahl der Unterschiede.

|Ausgewählt  |Power BI Embedded<br>(A-SKUs) |Power BI Premium-Kapazität<br>(EM-SKUS)  | 
|---------|---------|---------|
|Einbetten von Artefakten aus Power BI-App-Arbeitsbereichen     |Azure-Kapazität |Office 365-Kapazität |
|Power BI-Lizenz erforderlich, um Berichte zu verarbeiten |Nein  |Ja |
|Power BI-Berichte in einer Embedded-Anwendung nutzen |Ja  |Ja |
|Power BI-Berichte in SharePoint nutzen |Nein |Ja |
|Power BI-Berichte in Teams nutzen |Nein |Ja |

### <a name="power-bi-now-offers-three-skus-for-embedding-a-skus-em-skus-and-p-skus-which-one-should-i-purchase-for-my-scenario"></a>Power BI bietet jetzt drei SKUs für die Einbettung: A-SKUs, EM-SKUs und P-SKUs. Welche SKU ist für mein Szenario optimal?

|  |A-SKU (Power BI Embedded)  |EM-SKU (Power BI Premium)  |P-SKU (Power BI Premium)  |
|---------|---------|---------|---------|
|Erwerben     |Azure-Portal |Office |Office |
|Anwendungsfälle |* Einbetten von Inhalten in Ihre eigene Anwendung |* Einbetten von Inhalten in Ihre eigene Anwendung<br>* Freigeben von Inhalten mit für Benutzer von Power BI FREE außerhalb von PowerBI.com und Einbetten in andere SaaS-Anwendungen (SharePoint, Teams) |* Einbetten von Inhalten in Ihre eigene Anwendung<br>* Freigeben von Inhalten mit für Benutzer von Power BI FREE außerhalb von PowerBI.com und Einbetten in andere SaaS-Anwendungen (SharePoint, Teams)<br>* Freigeben von Inhalten für Benutzer von Power BI FREE über PowerBI.com  |
|Abrechnung |Stündlich |Monatlich |Monatlich |
|Vertragsbindung  |Keine Vertragsbindung |Jährlich  |Monatlich/jährlich |
|Differenzierung |Vollständige Elastizität: vertikale Skalierung, Anhalten/Fortsetzen von Ressourcen im Azure-Portal oder über die API  |Möglichkeit der Einbettung von Inhalten in SharePoint Online und Microsoft Teams |Kombination von Einbettung in Anwendungen und Verwendung des Power BI-Diensts mit der gleichen Kapazität |

### <a name="what-are-the-prerequisites-to-create-a-pbie-capacity-in-azure"></a>Was sind die Voraussetzungen zum Erstellen einer PBIE-Kapazität in Azure?

- Sie müssen sich bei Ihrem Organisationsverzeichnis anmelden (MSA-Konten werden nicht unterstützt).
- Sie müssen über einen Power BI-Mandanten verfügen, d.h. mindestens ein Benutzer in Ihrem Verzeichnis muss bei Power BI registriert sein. 
- Sie müssen über ein Azure-Abonnement in Ihrem Organisationsverzeichnis verfügen.

### <a name="how-can-i-monitor-capacity-consumption"></a>Wie kann ich die Kapazitätsnutzung überwachen?

Die Überwachung über Azure ist für die nähere Zukunft geplant. Die Azure-Ressource Power BI Embedded wird die Überwachung von KPIs zu Systemzustand und Nutzung umfassen.

### <a name="will-my-capacity-scale-automatically-to-adjust-to-the-consumption-of-my-app"></a>Wird meine Kapazität automatisch an die Nutzung meiner App angepasst?

Derzeit wird zwar keine automatische Skalierung unterstützt, für alle APIs ist jedoch jederzeit eine Skalierung verfügbar.

### <a name="what-is-the-authentication-model-for-power-bi-embedded"></a>Welches Authentifizierungsmodell wird für Power BI Embedded verwendet?

Für Power BI Embedded wird weiterhin Azure AD für die Authentifizierung des Masterbenutzers (ein designierter Benutzer mit Power BI Pro-Lizenz) verwendet, der die Anwendung in Power BI authentifiziert.

Authentifizierung und Autorisierung der Anwendungsbenutzer werden vom ISV implementiert. Der ISV kann für seine Anwendungen eigene Authentifizierungsfunktionen implementieren.

Wenn Sie bereits über einen Azure AD-Mandanten verfügen, können Sie das vorhandene Verzeichnis verwenden oder einen neuen Azure AD-Mandanten zum Schutz der Inhalte in der Embedded-Anwendung erstellen.

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

Power BI Embedded wird nach einem feststehenden Stundensatz abgerechnet, der vom Typ der bereitgestellten Knoten abhängt. Beachten Sie, dass Kosten anfallen, solange eine Ressource aktiv ist, auch wenn Sie diese nicht nutzen. Sie müssen Ihre Ressource manuell anhalten, damit keine Kosten mehr anfallen.

### <a name="who-needs-a-power-bi-pro-license-for-power-bi-embedded-and-why"></a>Wer benötigt aus welchen Gründen eine Power BI Pro-Lizenz für Power BI Embedded?

Alle Analytiker, die Berichte einem Power BI-Arbeitsbereich hinzufügen müssen, alle Entwickler, die REST-APIs verwenden müssen, alle Mandantenadministratoren, die den Power BI-Mandanten und die entsprechende Kapazität verwalten müssen, benötigen eine Power BI Pro-Lizenz.

Da Power BI Embedded die Verwendung des Power BI-Portals zum Verwalten und Überprüfen eingebetteter Inhalte erlaubt, ist die Power BI Pro-Lizenz erforderlich, um die App auf powerbi.com zu authentifizieren und um Zugriff auf die Berichte in den richtigen Repositorys zu erhalten.

### <a name="can-i-get-started-for-free"></a>Ist ein kostenloser Einstieg möglich?

Ja, Sie können eine [Azure-Gutschrift](https://azure.microsoft.com/free/) für Power BI Embedded verwenden.

### <a name="can-i-get-a-trial-experience-for-power-bi-embedded-in-azure"></a>Ist eine Testversion von Power BI Embedded in Azure erhältlich?

Da Power BI Embedded Teil von Azure ist, können Sie den Dienst mit der [bei der Registrierung bei Azure erhaltenen 200-$-Gutschrift](https://azure.microsoft.com/free/) verwenden.

### <a name="is-power-bi-embedded-available-for-sovereign-clouds-us-government-germany-china"></a>Ist Power BI Embedded für unabhängige Clouds (US-Behörden, Deutschland, China) verfügbar?

Power BI Embedded ist für einige [unabhängige Clouds](embed-sample-for-customers-sovereign-clouds.md) verfügbar. Es ist noch **NICHT** für die China-Cloud verfügbar.

### <a name="is-power-bi-embedded-available-for-non-profits-and-educational"></a>Ist Power BI Embedded für Non-Profit-Organisationen und Bildungseinrichtungen erhältlich?

Non-Profit-Organisationen und Bildungseinrichtungen können Azure erwerben. Für diese Arten von Kunden gibt es in Azure keine Sonderpreise.

## <a name="power-bi-workspace-collection"></a>Power BI-Arbeitsbereichssammlung

### <a name="what-is-power-bi-workspace-collection"></a>Was ist eine Power BI-Arbeitsbereichssammlung?

**Power BI-Arbeitsbereichssammlung** (**Power BI Embedded** Version 1) ist eine Lösung, die auf der Azure-Ressource **Power BI-Arbeitsbereichssammlung** basiert. Mit dieser Lösung können Sie **Power BI Embedded**-Anwendungen für Ihre Kunden erstellen. Dabei verwenden Sie Power BI-Inhalte in der Lösung **Power BI-Arbeitsbereichssammlung**, dedizierte APIs und Schlüssel für die Arbeitsbereichssammlung, um die Anwendung bei Power BI zu authentifizieren.

### <a name="can-i-migrate-from-power-bi-workspace-collection-to-power-bi-embedded"></a>Kann ich eine Power BI-Arbeitsbereichssammlung zu Power BI Embedded migrieren?

1. Sie können das Migrationstool verwenden, um Inhalte einer **Power BI-Arbeitsbereichssammlung** in Power BI zu klonen: https://docs.microsoft.com/power-bi/developer/migrate-from-powerbi-embedded#content-migration.

2. Beginnen Sie mit dem Anwendungs-POC für **Power BI Embedded**, der Power BI-Inhalte verwendet.

3. Wenn Sie bereits sind für den Produktionsbetrieb, erwerben Sie eine dedizierte **Power BI Embedded**-Kapazität und weisen Sie dieser Ihre Power BI-Inhalte (Arbeitsbereich) zu.

>[!Note]
Sie können die **Power BI-Arbeitsbereichssammlung** weiter nutzen, während Sie parallel eine **Power BI Embedded**-Lösung für die Entwicklung verwenden. Sobald Sie bereit sind, können Sie Ihren Kunden zur neuen **Power BI Embedded**-Lösung verlagern und die **Power BI-Arbeitsbereichssammlung** außer Betrieb nehmen.

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
* Alle Power BI-Datenquellen werden unterstützt. In **Power BI Workspace Collection** werden dagegen nur 2 Datenquellen unterstützt. 
* Neue Features wie Q&A, Aktualisieren, Lesezeichen, Einbetten von Dashboards und Kacheln, benutzerdefiniertes Menü usw. werden nur in der Lösung **Power BI Embedded** unterstützt.
* Kapazitätsbasiertes Abrechnungsmodell.

Weitere Informationen finden Sie unter [Problembehandlung bei Embedded-Anwendungen](embedded-troubleshoot.md).

Weitere Fragen? [Wenden Sie sich an die Power BI-Community](http://community.powerbi.com/)