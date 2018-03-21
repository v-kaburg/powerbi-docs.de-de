---
title: "Häufig gestellte Fragen zu Power BI Embedded"
description: "Durchsuchen Sie die Liste der häufig gestellten Fragen und Antworten zu Power BI Embedded."
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
ms.date: 03/07/2018
ms.author: maghan
ms.openlocfilehash: 52ff1095c063be867354a23e0e8e4908a4b4e1d7
ms.sourcegitcommit: ee5d044db99e253c27816e0ea6bdeb9e39a2cf41
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/08/2018
---
# <a name="frequently-asked-questions-about-power-bi-embedded"></a>Häufig gestellte Fragen zu Power BI Embedded

* Wenn Sie weitere Fragen haben, [stellen Sie sie in der Power BI-Community](http://community.powerbi.com/).
* Treten weiterhin Probleme auf? Weitere Informationen finden Sie auf der [Supportseite für Power BI](https://powerbi.microsoft.com/support/).

## <a name="general"></a>Allgemein

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

Da Einbettungstokens mit einer PRO-Lizenz nur für Bereitstellungen und das Testen von Bereitstellungen vorgesehen sind, ist die Anzahl von Einbettungstokens limitiert, die ein Power BI-Hauptkonto generieren kann. Sie müssen [eine Kapazität erwerben](https://docs.microsoft.com/power-bi/developer/embedded-faq#technical), um Einbettungen in einer Produktionsumgebung vornehmen zu können. Wenn eine Kapazität erworben wird, gibt es keine Einschränkungen dafür, wie viele Einbettungstokens generiert werden können.

### <a name="when-will-power-bi-embedded-be-available-in-azure"></a>Ab wann ist Power BI Embedded in Azure verfügbar?

Power BI Embedded ist heute schon verfügbar.

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

### <a name="how-power-bi-embedded-be-metered"></a>Wie wird die Nutzung von Power BI Embedded gemessen?

Power BI Embedded wird nach Stunden abgerechnet.

### <a name="how-does-the-usage-of-power-bi-embedded-show-up-on-my-bill"></a>Wie wird die Nutzung von Power BI Embedded auf meiner Rechnung aufgeführt?

Power BI Embedded wird nach einem feststehenden Stundensatz abgerechnet, der vom Typ der bereitgestellten Knoten abhängt. Beachten Sie, dass Kosten anfallen, solange eine Ressource aktiv ist, auch wenn Sie diese nicht nutzen. Sie müssen Ihre Ressource manuell anhalten, damit keine Kosten mehr anfallen. Das Anhalten kann über Azure oder ARM-APIs erfolgen.

### <a name="what-happens-if-i-already-purchased-power-bi-premium-and-now-i-want-some-of-the-benefits-of-power-bi-embedded-in-azure"></a>Was geschieht, wenn ich Power BI Premium bereits erworben und jetzt einige der Vorteile von Power BI Embedded in Azure nutzen möchte?

Kunden zahlen bis zum Ende der Laufzeit ihrer aktuellen Vereinbarung weiterhin für erworbene Power BI Premium-Lizenzen und können dann ihre Power BI Premium-Lizenzen nach Bedarf umstellen.

### <a name="do-i-still-have-to-buy-power-bi-premium-to-get-access-to-power-bi-embedded"></a>Muss ich Power BI Premium trotzdem erwerben, um auf Power BI Embedded zugreifen zu können?

Nein, Power BI Embedded umfasst die auf Azure basierende Kapazität, die Sie zum Bereitstellen und Verteilen Ihrer Lösung für Kunden benötigen.

### <a name="who-needs-a-power-bi-pro-license-for-power-bi-embedded-and-why"></a>Wer benötigt aus welchen Gründen eine Power BI Pro-Lizenz für Power BI Embedded?

Alle Analytiker, die Berichte einem Power BI-Arbeitsbereich hinzufügen müssen, alle Entwickler, die REST-APIs verwenden müssen, alle Mandantenadministratoren, die den Power BI-Mandanten und die entsprechende Kapazität verwalten müssen, benötigen eine Power BI Pro-Lizenz.

Da Power BI Embedded die Verwendung des Power BI-Portals zum Verwalten und Überprüfen eingebetteter Inhalte erlaubt, ist die Power BI Pro-Lizenz erforderlich, um die App auf powerbi.com zu authentifizieren und um Zugriff auf die Berichte in den richtigen Repositorys zu erhalten.

### <a name="can-i-get-started-for-free"></a>Ist ein kostenloser Einstieg möglich?

Ja, Sie können eine [Azure-Gutschrift](https://azure.microsoft.com/free/) für Power BI Embedded verwenden.

### <a name="can-i-get-a-trial-experience-for-power-bi-embedded-in-azure"></a>Ist eine Testversion von Power BI Embedded in Azure erhältlich?

Da Power BI Embedded Teil von Azure ist, können Sie den Dienst mit der [bei der Registrierung bei Azure erhaltenen 200-$-Gutschrift](https://azure.microsoft.com/free/) verwenden.

### <a name="whats-the-purchase-commitment-for-power-bi-embedded"></a>Welche Verpflichtung ist mit dem Kauf von Power BI Embedded verbunden? 

Kunden können ihre Nutzung auf Stundenbasis anpassen. Es gibt keine monatliche oder jährliche Verpflichtung für den Power BI Embedded-Dienst.

### <a name="where-is-power-bi-embedded-available-us-government-germany-china-what-is-the-timing"></a>Wo erhalte ich Power BI Embedded? US-Behörden? Deutschland? China? Was sieht der Zeitplan aus?

Power BI Embedded ist in kommerziellen Clouds von Azure und in der Cloud der US-Regierung verfügbar.  Die Verfügbarkeit von Sovereign Cloud in Deutschland und China folgt zu einem späteren Zeitpunkt.

### <a name="is-power-bi-embedded-available-for-non-profits-and-educational"></a>Ist Power BI Embedded für Non-Profit-Organisationen und Bildungseinrichtungen erhältlich?

Non-Profit-Organisationen und Bildungseinrichtungen können Azure erwerben. Für diese Arten von Kunden gibt es in Azure keine Sonderpreise.

Weitere Fragen? [Wenden Sie sich an die Power BI-Community](http://community.powerbi.com/)
