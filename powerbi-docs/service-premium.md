---
title: Was ist Microsoft Power BI Premium?
description: Power BI Premium bietet dedizierte Kapazität für Ihre Organisation oder Ihr Team, sodass Sie von verlässlicherer Leistung und größeren Datenmengen profitieren, ohne Benutzerlizenzen kaufen zu müssen.
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-admin
ms.topic: conceptual
ms.date: 10/21/2018
LocalizationGroup: Premium
ms.openlocfilehash: 2ca75f191f27bd158b9fab67c7be6902154f8ac1
ms.sourcegitcommit: a764e4b9d06b50d9b6173d0fbb7555e3babe6351
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2018
ms.locfileid: "49641227"
---
# <a name="what-is-microsoft-power-bi-premium"></a>Was ist Microsoft Power BI Premium?

Microsoft Power BI Premium bietet dedizierte Ressourcen für die Ausführung des Power BI-Diensts für Ihre Organisation, sodass Sie von verlässlicherer Leistung und größeren Datenmengen profitieren. Premium ermöglicht darüber hinaus die weite Verteilung von Inhalten, ohne dass Sie für jeden einzelnen Benutzer des Inhalts Power BI Pro-Lizenzen erwerben müssen. Weitere Informationen zum Erwerb finden Sie unter [How to purchase Power BI Premium (Erwerben von Power BI Premium)](service-admin-premium-purchase.md).

<iframe width="560" height="315" src="https://www.youtube.com/embed/lNQDkN0GXzU?rel=0&amp;showinfo=0" frameborder="0" allowfullscreen></iframe>

## <a name="premium-capacity-and-shared-capacity"></a>Premium-Kapazitäten und gemeinsam genutzte Kapazitäten

Nutzen Sie die Vorteile von Power BI Premium, indem Sie Arbeitsbereiche einer *Premium-Kapazität* zuweisen. Eine Premium-Kapazität stellt eine für Ihre Organisation dedizierte Ressource dar. Arbeitsbereiche, die keiner Premium-Kapazität zugewiesen sind, werden in einer *gemeinsam genutzten Kapazität* ausgeführt. Mit gemeinsam genutzten Kapazitäten werden Ihre Workloads auf Computeressourcen ausgeführt, die gemeinsam von anderen Kunden genutzt werden.

Auf der folgenden Abbildung wird die Beziehung zwischen Premium-Kapazitäten und gemeinsam genutzten Kapazitäten veranschaulicht. Hierfür wird die Organisation „Contoso“ als Beispiel verwendet.

![Illustration von Power BI Premium](media/service-premium/premium-chart.png)

| Area | Beschreibung |
| --- | --- |
| **(1)** Elemente innerhalb einer Premium-Kapazität | <ul><li>Für das Zugreifen auf App-Arbeitsbereiche (als Mitglied oder Administrator) und das Veröffentlichen von Apps ist eine Power BI Pro-Lizenz erforderlich.<li>Das Freigeben einer App erfordert eine Pro-Lizenz, das Nutzen einer App jedoch nicht.<li>Alle Dashboardempfänger können unabhängig der ihnen zugewiesenen Lizenz Datenwarnungen festlegen.<li>REST-APIs zum Einbetten verwenden ein Dienstkonto mit einer Pro-Lizenz anstelle eines Benutzerkontos.</ul> |
| **(2)** Mein Arbeitsplatz in einer gemeinsam genutzten Kapazität | <ul><li>Sowohl die Freigabe und die Nutzung einer App erfordern eine Pro-Lizenz.</ul> |
| **(3)** App-Arbeitsbereiche in einer gemeinsam genutzten Kapazität | <ul><li>Für jede App-Nutzung ist eine Pro-Lizenz erforderlich.</ul>|
| | |

Bei der gemeinsam genutzten Kapazität setzt Power BI mehr Einschränkungen für einzelne Benutzer durch, um für alle Benutzer die gleiche Nutzungsqualität sicherzustellen. Ihr Arbeitsbereich befindet sich standardmäßig in einer gemeinsam genutzten Kapazität, einschließlich Ihres persönlichen *Arbeitsbereichs* und App-Arbeitsbereichen.

In der folgenden Tabelle finden Sie eine Zusammenfassung der Unterschiede zwischen einer gemeinsam genutzten Kapazität und der Premium-Kapazität.

|  | Gemeinsam genutzte Kapazität | Power BI Premium-Kapazität |
| --- | --- | --- |
| **Aktualisierungsrate** |8/Tag |48/Tag |
| **Isolation mit dedizierter Hardware** |![](media/service-premium/not-available.png "Nicht verfügbar") |![](media/service-premium/available.png "Verfügbar") |
| **Enterprise-Verteilung an** ***alle Benutzer*** | | |
| Apps und Freigabe |![](media/service-premium/not-available.png "Nicht verfügbar") |![](media/service-premium/available.png "Verfügbar")<sup>1</sup> |
| Eingebettete API und Steuerelemente |![](media/service-premium/not-available.png "Nicht verfügbar") |![](media/service-premium/available.png "Verfügbar")<sup>2</sup> |
| **Lokale Veröffentlichung von Power BI-Berichten** |![](media/service-premium/not-available.png "Nicht verfügbar") |![](media/service-premium/available.png "Verfügbar") |
| | | |

*<sup>1</sup> Weitere Informationen finden Sie unter [Features by license type (Power BI-Features nach Lizenztyp)](service-features-license-type.md).*  
*<sup>2</sup> Zukünftige Verbesserungen, die in Power BI Premium eingeführt werden.*

Weitere Informationen zum Zuordnen von Arbeitsbereichen zu einer Premium-Kapazität finden Sie unter [Verwalten von Power BI Premium](service-admin-premium-manage.md).

<a name="premiumskus"/>

### <a name="premium-capacity-nodes"></a>Knoten für Premium-Kapazität

Power BI Premium steht in Knotenkonfigurationen mit abweichenden V-Kernkapazitäten zur Verfügung. Weitere Informationen zu bestimmten SKU-Angeboten und Kosten finden Sie unter [Power BI-Preise](https://powerbi.microsoft.com/pricing/). Darüber hinaus ist ein [Kostenrechner](https://powerbi.microsoft.com/calculator/) verfügbar. Informationen zur Kapazitätsplanung für die eingebettete Analyse finden Sie unter [Planning a Power BI Enterprise Deployment whitepaper (Whitepaper zum Planen einer Unternehmensbereitstellung von Power BI)](https://aka.ms/pbienterprisedeploy). Zusammenfassung:

* P-Knoten können für eingebettete Bereitstellungen oder Dienstbereitstellungen verwendet werden.

* EM-Knoten können nur für eingebettete Bereitstellungen verwendet werden. EM-Knoten haben keinen Zugriff auf Premium-Funktionen, z.B. die Freigabe von Apps für Benutzer, die keine Power BI Pro-Lizenz besitzen.

>[!NOTE]
>Die Links in dieser Tabelle funktionieren nur für Benutzer, die über die Rolle „Globaler Office 365-Administrator“ verfügen. Andere erhalten einen 404-Fehler.

| Kapazitätsknoten | Gesamtzahl an V-Kernen<br/>*(Back-End + Front-End)* | Back-End-V-Kerne | Front-End-V-Kerne | Grenzwerte für DirectQuery/Liveverbindung | Höchstzahl an Seitenladevorgängen zu Spitzenzeiten | Verfügbarkeit |
| --- | --- | --- | --- | --- | --- | --- |
| [EM1 (monatlich)](https://portal.office.com/SubscriptionDetails?OfferId=4004702D-749C-4F74-BF47-3048F1833780&adminportal=1) |1 V-Kern |0,5 V-Kerne, 2,5 GB RAM |0,5 V-Kerne |3,75 pro Sekunde |150–300 |Verfügbar |
| [EM2 (monatlich)](https://portal.office.com/SubscriptionDetails?OfferId=4004702D-749C-4F74-BF47-3048F1833780&adminportal=1) |2 V-Kerne |1 V-Kern, 5 GB RAM |1 V-Kern |7,5 pro Sekunde |301–600 |Verfügbar |
| [EM3 (monatlich)](https://portal.office.com/SubscriptionDetails?OfferId=4004702D-749C-4F74-BF47-3048F1833780&adminportal=1) |4 V-Kerne |2 V-Kerne, 10 GB RAM |2 V-Kerne | |601–1.200 |Verfügbarkeit |
| [P1](https://portal.office.com/SubscriptionDetails?OfferId=b3ec5615-cc11-48de-967d-8d79f7cb0af1&adminportal=1) |8 V-Kerne |4 V-Kerne, 25 GB RAM |4 V-Kerne |30 pro Sekunde |1.201–2.400 |Verfügbar (auch [monatlich](https://portal.office.com/SubscriptionDetails?OfferId=E4C8EDD3-74A1-4D42-A738-C647972FBE81&adminportal=1)) |
| [P2](https://portal.office.com/SubscriptionDetails?OfferId=062F2AA7-B4BC-4B0E-980F-2072102D8605&adminportal=1) |16 V-Kerne |8 V-Kerne, 50 GB RAM |8 V-Kerne |60 pro Sekunde |2.401–4.800 |Verfügbarkeit |
| [P3](https://portal.office.com/SubscriptionDetails?OfferId=40c7d673-375c-42a1-84ca-f993a524fed0&adminportal=1) |32 V-Kerne |16 V-Kerne, 100 GB RAM |16 V-Kerne |120 pro Sekunde |4.801–9600 |Verfügbar |
| | | | | | | |

* Die Front-End-V-Kerne sind für den Webdienst, die Verwaltung von Dashboard und Berichtsdokumenten, die Zugriffsrechteverwaltung, Zeitplanung, APIs, Uploads und Downloads und allgemein für alles zuständig, das mit der Benutzererfahrung zusammenhängt.

* Die Back-End-V-Kerne übernehmen den Hauptteil der Arbeit: Abfrageverarbeitung, Cacheverwaltung, Ausführen von R-Servern, Datenaktualisierung, Verarbeitung von natürlicher Sprache, Echtzeitfeeds und serverseitiges Laden von Berichten und Bildern. Zusammen mit den Back-End-V-Kernen wird auch eine bestimmte Menge Arbeitsspeicher reserviert. Die Verfügbarkeit einer ausreichend großen Arbeitsspeichermenge ist insbesondere dann wichtig, wenn große Datenmodelle oder Modelle mit einer großen Anzahl aktiver Datasets verarbeitet werden müssen.

## <a name="power-bi-report-server"></a>Power BI-Berichtsserver

Power BI Premium enthält auch die Funktion zum lokalen Ausführen von Power BI-Berichtsserver in Ihrem Unternehmen. Weitere Informationen finden Sie unter [Erste Schritte mit Power BI-Berichtsserver](report-server/get-started.md).

## <a name="next-steps"></a>Nächste Schritte

[Power BI Premium – Häufig gestellte Fragen](service-premium-faq.md)
[Erwerben von Power BI Premium](service-admin-premium-purchase.md)
[Verwalten von Kapazitäten in Power BI Premium und Power BI Embedded](service-admin-premium-manage.md)
[Whitepaper zu Microsoft Power BI Premium](https://aka.ms/pbipremiumwhitepaper)
[Whitepaper zum Planen einer Unternehmensbereitstellung mit Power BI](https://aka.ms/pbienterprisedeploy)
[Was ist die Power BI-Verwaltung?](service-admin-administering-power-bi-in-your-organization.md)

Weitere Fragen? [Stellen Sie Ihre Frage in der Power BI-Community.](https://community.powerbi.com/)
