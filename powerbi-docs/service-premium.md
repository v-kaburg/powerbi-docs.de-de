---
title: "Power BI Pro-Inhalt – was ist das?"
description: "Power BI Premium bietet dedizierte Kapazität für Ihre Organisation oder Ihr Team, sodass Sie von verlässlicherer Leistung und größeren Datenmengen profitieren, ohne Benutzerlizenzen kaufen zu müssen."
services: powerbi
documentationcenter: 
author: guyinacube
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: get-started-article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/10/2017
ms.author: asaxton
ms.openlocfilehash: 816f1151b6f49ace8151f1c26aee18a8c746ff08
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2017
---
# <a name="power-bi-premium---what-is-it"></a>Power BI Premium – Beschreibung
Power BI Premium bietet dedizierte Ressourcen für die Ausführung des Power BI-Diensts für Ihre Organisation oder Ihr Team, sodass Sie von verlässlicherer Leistung und größeren Datenmengen profitieren. Premium ermöglicht darüber hinaus die breit gestreute Verteilung von Inhalten, ohne dass Sie für Benutzer mit schreibgeschütztem Zugriff Pro-Benutzer-Lizenzen erwerben müssen.

Sie können Power BI Premium nutzen, indem Sie Arbeitsbereiche einer Premium-Kapazität zuordnen. *Premium-Kapazität* stellt eine für Ihre Organisation dedizierte Ressource dar. Arbeitsbereiche, die keiner Premium-Kapazität zugeordnet sind, werden in einer gemeinsam genutzten Kapazität ausgeführt.

*Gemeinsam genutzte Kapazität* ist die gewohnte Erfahrung bei Power BI, bei der Ihre Workloads auf Computerressourcen ausgeführt werden, die Sie gemeinsam mit anderen Kunden nutzen. Bei der gemeinsam genutzten Kapazität werden für Einzelbenutzer stärkere Einschränkungen durchgesetzt, um für alle Benutzer eine gute Nutzungsqualität sicherzustellen.

[!INCLUDE [powerbi-premium-illustration](./includes/powerbi-premium-illustration.md)]

<iframe width="560" height="315" src="https://www.youtube.com/embed/lNQDkN0GXzU?rel=0&amp;showinfo=0" frameborder="0" allowfullscreen></iframe>

## <a name="capacity-tiers"></a>Kapazitätsstufen
Für Power BI sind zwei verschiedene Arten von Kapazität verfügbar. Gemeinsam genutzte Kapazität und Power BI Premium-Kapazität. Aus dieser Auflistung sind die Unterschiede zwischen beiden ersichtlich.

|  | Gemeinsam genutzte Kapazität | Power BI Premium-Kapazität |
| --- | --- | --- |
| **Aktualisierungsrate** |8/Tag |Unbeschränkt |
| **Isolation mit dedizierter Hardware** |![](media/service-premium/not-available.png "Nicht verfügbar") |![](media/service-premium/available.png "Verfügbar") |
| **Enterprise-Verteilung an** ***alle Benutzer*** | | |
| Apps |![](media/service-premium/not-available.png "Nicht verfügbar") |![](media/service-premium/available.png "Verfügbar")<sup>1</sup> |
| Eingebettete API und Steuerelemente |![](media/service-premium/not-available.png "Nicht verfügbar") |![](media/service-premium/available.png "Verfügbar")<sup>2</sup> |
| **Lokale Veröffentlichung von Power BI-Berichten** |![](media/service-premium/not-available.png "Nicht verfügbar") |![](media/service-premium/available.png "Verfügbar") |

*<sup>1</sup> Kostenlose Nutzung durch Benutzer in Apps, einschließlich der Anzeige von Inhalten in Web- und mobilen Versionen, Nutzung von F&A, Quick Insights, Cortana, Export nach CSV, Excel und PowerPoint.*  
*<sup>2</sup> Zukünftige Erweiterungen, die nach der allgemeinen Verfügbarkeit von Power BI Premium eingeführt werden.*

### <a name="premium-capacity"></a>Premium-Kapazität
Um mit der Verwendung einer Power BI Premium-Kapazität zu beginnen, müssen Sie einer Kapazität einen Arbeitsbereich zuordnen. Weitere Informationen zum Zuordnen eines Arbeitsbereichs zu einer Premium-Kapazität finden Sie unter [Verwalten von Power BI Premium](service-admin-premium-manage.md).

Wenn ein Arbeitsbereich durch Premium-Kapazität gestützt wird, kommen Sie in den Genuss der Vorteile von Power BI Premium.

* Geplante Aktualisierungen: Benutzer waren bisher beim Planen von Aktualisierungen für importierte Modelle auf 8 Aktualisierungen am Tag beschränkt. Diese Einschränkung ist für Datasets in Premium-Arbeitsbereichen aufgehoben. Dies betrifft nicht die Einstellungen für geplante Cacheaktualisierungen für DirectQuery. Diese bleiben zwischen Premium-Kapazität und gemeinsam genutzter Kapazität unverändert.
* Isolation mithilfe von dedizierter Hardware: Es liegt in der Natur von gemeinsam genutzter Kapazität, dass die Leistung Ihrer Berichte und Dashboards durch die Ressourcenanforderungen anderer Workloads in der Kapazität beeinträchtigt werden kann, trotz unserer Sicherheitsvorkehrungen, die dies verhindern sollen. Dagegen bietet Premium durch die Isolation von nicht zugehörigen Workloads einheitlichere, verlässlichere Leistung für Ihre Workloads.

Wenn eine App durch Premium-Kapazität gestützt wird (d.h. sie wurde aus einem App-Arbeitsbereich veröffentlicht, der aktuell Premium zugeordnet ist), kann die veröffentlichte App anschließend von jedem Benutzer in Ihrer Organisation verwendet werden, unabhängig von dem Lizenzschlüssel, der dem Benutzer zugeordnet ist. Dies bedeutet, dass selbst Benutzer von Power BI Free diese veröffentlichten Apps verwenden können.

### <a name="shared-capacity"></a>Gemeinsam genutzte Kapazität
Standardmäßig wird Ihr Arbeitsbereich mit gemeinsam genutzter Kapazität betrieben. Dies schließt Ihren persönlichen *Mein Arbeitsbereich* ebenso ein wie die App-Arbeitsbereiche. Gemeinsam genutzte Kapazität ist die gewohnte Erfahrung bei Power BI, bei der Ihre Workloads auf Computerressourcen ausgeführt werden, die Sie gemeinsam mit anderen Kunden nutzen.

<a name="premiumskus"/>

### <a name="premium-capacity-nodes"></a>Knoten für Premium-Kapazität
Power BI Premium steht in Knotenkonfigurationen mit abweichenden V-Kernkapazitäten zur Verfügung. Weitere Informationen zu bestimmten SKU-Angeboten und Kosten, finden Sie unter [Power BI-Preise](https://powerbi.microsoft.com/pricing/). Darüber hinaus ist ein [Kostenrechner](https://powerbi.microsoft.com/calculator/) verfügbar. Informationen zur Kapazitätsplanung für die eingebettete Analyse finden Sie unter [Planning a Power BI Enterprise Deployment whitepaper (Whitepaper zum Planen einer Unternehmensbereitstellung von Power BI)](https://aka.ms/pbienterprisedeploy).

* P-Knoten können für eingebettete oder Dienstbereitstellungen verwendet werden
* EM-Knoten können nur für eingebettete Bereitstellungen verwendet werden

| Kapazitätsknoten | Gesamtzahl der Kerne<br/>*(Back-End + Front-End)* | Back-End-Kerne | Front-End-Kerne | Grenzwerte für DirectQuery/Liveverbindung | Höchstzahl an Seitenladevorgängen zu Spitzenzeiten | Verfügbarkeit |
| --- | --- | --- | --- | --- | --- | --- |
| [EM3 (monatlich)](https://portal.office.com/SubscriptionDetails?OfferId=4004702D-749C-4F74-BF47-3048F1833780&adminportal=1) |4 V-Kerne |2 Kerne, 10 GB RAM |2 Kerne | |601–1.200 |Verfügbarkeit |
| [P1](https://portal.office.com/SubscriptionDetails?OfferId=b3ec5615-cc11-48de-967d-8d79f7cb0af1&adminportal=1) |8 V-Kerne |4 Kerne, 25 GB RAM |4 Kerne |30 pro Sekunde |1.201–2.400 |Verfügbar (auch [monatlich](https://portal.office.com/SubscriptionDetails?OfferId=E4C8EDD3-74A1-4D42-A738-C647972FBE81&adminportal=1)) |
| [P2](https://portal.office.com/SubscriptionDetails?OfferId=062F2AA7-B4BC-4B0E-980F-2072102D8605&adminportal=1) |16 V-Kerne |8 Kerne, 50 GB RAM |8 Kerne |60 pro Sekunde |2.401–4.800 |Verfügbarkeit |
| [P3](https://portal.office.com/SubscriptionDetails?OfferId=40c7d673-375c-42a1-84ca-f993a524fed0&adminportal=1) |32 V-Kerne |16 Kerne, 100 GB RAM |16 Kerne |120 pro Sekunde |4.801–9600 |Verfügbarkeit |

* Die Front-End-Kerne sind für den Webdienst, die Verwaltung von Dashboard und Berichtsdokumenten, die Zugriffsrechteverwaltung, Zeitplanung, APIs, Uploads und Downloads und allgemein für alles zuständig, das mit der Benutzererfahrung zusammenhängt.
* Die Back-End-Kerne übernehmen die Schwerarbeit: Abfrageverarbeitung, Cacheverwaltung, Ausführen von R-Servern, Datenaktualisierung, Verarbeitung von natürlicher Sprache, Echtzeitfeeds und serverseitiges Laden von Berichten und Bildern. Zusammen mit den Back-End-Kernen wird auch eine bestimmte Menge Arbeitsspeicher reserviert. Die Verfügbarkeit einer ausreichend großen Arbeitsspeichermenge ist insbesondere dann wichtig, wenn große Datenmodelle oder Modelle mit einer großen Anzahl aktiver Datasets verarbeitet werden müssen.

## <a name="power-bi-report-server"></a>Power BI-Berichtsserver
Power BI Premium beinhaltet das Recht zur lokalen Ausführung von Power BI-Berichtsserver. Weitere Informationen finden Sie unter [Erste Schritte mit Power BI-Berichtsserver](report-server/get-started.md).

## <a name="next-steps"></a>Nächste Schritte
[Power BI Premium – Häufig gestellte Fragen (FAQ)](service-premium-faq.md)  
[Power BI Premium – Anmerkungen zu dieser Version](service-premium-release-notes.md)  
[Erwerben von Power BI Premium](service-admin-premium-purchase.md)  
[Verwalten von Power BI Premium](service-admin-premium-manage.md)  
[Microsoft Power BI Premium-Whitepaper](https://aka.ms/pbipremiumwhitepaper)  
[Whitepaper zum Planen der Unternehmensbereitstellung von Power BI](https://aka.ms/pbienterprisedeploy)  
[Verwalten von Power BI in Ihrer Organisation](service-admin-administering-power-bi-in-your-organization.md)  

Weitere Fragen? [Stellen Sie Ihre Frage in der Power BI-Community.](https://community.powerbi.com/)

