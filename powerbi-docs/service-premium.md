---
title: Was ist Microsoft Power BI Premium?
description: Power BI Premium bietet dedizierte Kapazität für Ihre Organisation oder Ihr Team, sodass Sie von verlässlicherer Leistung und größeren Datenmengen profitieren, ohne Benutzerlizenzen kaufen zu müssen.
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 10/21/2018
ms.custom: seodec18
LocalizationGroup: Premium
ms.openlocfilehash: 1749fc932b3aa6cfb86de87bc9ecd71f78d92af5
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/15/2019
ms.locfileid: "54281963"
---
# <a name="what-is-microsoft-power-bi-premium"></a>Was ist Microsoft Power BI Premium?

Microsoft Power BI Premium bietet dedizierte Ressourcen für die Ausführung des Power BI-Diensts für Ihre Organisation, sodass Sie von verlässlicherer Leistung und größeren Datenmengen profitieren. Premium ermöglicht darüber hinaus die weite Verteilung von Inhalten, ohne dass Sie für jeden einzelnen Benutzer des Inhalts Power BI Pro-Lizenzen erwerben müssen. Weitere Informationen zum Erwerb finden Sie unter [How to purchase Power BI Premium (Erwerben von Power BI Premium)](service-admin-premium-purchase.md).

<iframe width="560" height="315" src="https://www.youtube.com/embed/lNQDkN0GXzU?rel=0&amp;showinfo=0" frameborder="0" allowfullscreen></iframe>

## <a name="premium-capacity-and-shared-capacity"></a>Premium-Kapazitäten und gemeinsam genutzte Kapazitäten

Nutzen Sie die Vorteile von Power BI Premium, indem Sie Arbeitsbereiche einer *Premium-Kapazität* zuweisen. Eine Premium-Kapazität stellt eine für Ihre Organisation dedizierte Ressource dar. Arbeitsbereiche, die keiner Premium-Kapazität zugewiesen sind, werden in einer *gemeinsam genutzten Kapazität* ausgeführt. Mit gemeinsam genutzten Kapazitäten werden Ihre Workloads auf Computeressourcen ausgeführt, die gemeinsam von anderen Kunden genutzt werden.

Auf der folgenden Abbildung wird die Beziehung zwischen Premium-Kapazitäten und gemeinsam genutzten Kapazitäten veranschaulicht. Hierfür wird die Organisation „Contoso“ als Beispiel verwendet.

![Illustration von Power BI Premium](media/service-premium/premium-chart.png)

| Fläche | Beschreibung |
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
| **Isolation mit dedizierter Hardware** |![Nicht verfügbar](media/service-premium/not-available.png) |![Verfügbar](media/service-premium/available.png) |
| **Enterprise-Verteilung an** _**alle Benutzer**_ | | |
| Apps und Freigabe |![Nicht verfügbar](media/service-premium/not-available.png) |![Verfügbar](media/service-premium/available.png) |
| Eingebettete API und Steuerelemente |![Nicht verfügbar](media/service-premium/not-available.png) |![Verfügbar](media/service-premium/available.png)<sup>2</sup> |
| **Lokale Veröffentlichung von Power BI-Berichten** |![Nicht verfügbar](media/service-premium/not-available.png) |![Verfügbar](media/service-premium/available.png) |
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

| Kapazitätsknoten | Gesamtzahl an V-Kernen<br/>*(Back-End + Front-End)* | Back-End-V-Kerne | Front-End-V-Kerne | Grenzwerte für DirectQuery/Liveverbindung | Verfügbarkeit |
| --- | --- | --- | --- | --- | --- | --- |
| [EM1 (monatlich)](https://portal.office.com/SubscriptionDetails?OfferId=4004702D-749C-4F74-BF47-3048F1833780&adminportal=1) |1 V-Kern |0,5 V-Kerne, 2,5 GB RAM |0,5 V-Kerne |3,75 pro Sekunde |Verfügbar |
| [EM2 (monatlich)](https://portal.office.com/SubscriptionDetails?OfferId=4004702D-749C-4F74-BF47-3048F1833780&adminportal=1) |2 V-Kerne |1 V-Kern, 5 GB RAM |1 V-Kern |7,5 pro Sekunde |Verfügbar |
| [EM3 (monatlich)](https://portal.office.com/SubscriptionDetails?OfferId=4004702D-749C-4F74-BF47-3048F1833780&adminportal=1) |4 V-Kerne |2 V-Kerne, 10 GB RAM |2 V-Kerne | |Verfügbar |
| [P1](https://portal.office.com/SubscriptionDetails?OfferId=b3ec5615-cc11-48de-967d-8d79f7cb0af1&adminportal=1) |8 V-Kerne |4 V-Kerne, 25 GB RAM |4 V-Kerne |30 pro Sekunde |Verfügbar (auch [monatlich](https://portal.office.com/SubscriptionDetails?OfferId=E4C8EDD3-74A1-4D42-A738-C647972FBE81&adminportal=1)) |
| [P2](https://portal.office.com/SubscriptionDetails?OfferId=062F2AA7-B4BC-4B0E-980F-2072102D8605&adminportal=1) |16 V-Kerne |8 V-Kerne, 50 GB RAM |8 V-Kerne |60 pro Sekunde |Verfügbar |
| [P3](https://portal.office.com/SubscriptionDetails?OfferId=40c7d673-375c-42a1-84ca-f993a524fed0&adminportal=1) |32 V-Kerne |16 V-Kerne, 100 GB RAM |16 V-Kerne |120 pro Sekunde |Verfügbar |
| | | | | | | |

* Die Front-End-V-Kerne sind für den Webdienst, die Verwaltung von Dashboard und Berichtsdokumenten, die Zugriffsrechteverwaltung, Zeitplanung, APIs, Uploads und Downloads und allgemein für alles zuständig, das mit der Benutzererfahrung zusammenhängt.

* Die Back-End-V-Kerne übernehmen den Hauptteil der Arbeit: Abfrageverarbeitung, Cacheverwaltung, Ausführen von R-Servern, Datenaktualisierung, Verarbeitung von natürlicher Sprache, Echtzeitfeeds und serverseitiges Laden von Berichten und Bildern. Zusammen mit den Back-End-V-Kernen wird auch eine bestimmte Menge Arbeitsspeicher reserviert. Die Verfügbarkeit einer ausreichend großen Arbeitsspeichermenge ist insbesondere dann wichtig, wenn große Datenmodelle oder Modelle mit einer großen Anzahl aktiver Datasets verarbeitet werden müssen.

## <a name="workloads-in-premium-capacity"></a>Workloads in Premium-Kapazität

Stellen Sie sich eine Workload in Power BI als einen der vielen Dienste vor, die Sie Benutzern zur Verfügung stellen können. Standardmäßig unterstützen **Power BI Premium**- und **Power BI Embedded**-Kapazitäten nur die Workload, die mit der Ausführung von Power BI-Abfragen in der Cloud verbunden ist.

Nun werden zwei weitere Workloads in der Vorschauversion unterstützt: **Paginierte Berichte** und **Dataflows**. Sie aktivieren diese Workloads im Power BI-Verwaltungsportal oder über die Power BI-REST-API. Sie legen auch den maximalen Arbeitsspeicherverbrauch für jede Workload fest. So können Sie steuern, wie sich die verschiedenen Workloads gegenseitig beeinflussen. Weitere Informationen finden Sie unter [Konfigurieren von Workloads](service-admin-premium-manage.md#configure-workloads).

### <a name="default-memory-settings"></a>Standardeinstellungen für den Arbeitsspeicher

Die folgende Tabelle zeigt die Standard- und Mindestwerte für den Arbeitsspeicher, basierend auf den verschiedenen verfügbaren [Kapazitätsknoten](#premium-capacity-nodes). Der Arbeitsspeicher wird Dataflows dynamisch zugeordnet, ist paginierten Berichten jedoch statisch zugeordnet. Weitere Informationen finden Sie im nächsten Abschnitt [Überlegungen zu paginierten Berichten](#considerations-for-paginated-reports).

#### <a name="microsoft-office-skus-for-software-as-a-service-saas-scenarios"></a>Microsoft Office-SKUs für Software-as-a-Service-Szenarios (SaaS)

|                     | EM3                      | P1                       | P2                      | P3                       |
|---------------------|--------------------------|--------------------------|-------------------------|--------------------------|
| Paginierte Berichte | N/V | 20 % Standard, mindestens 10 % | 20 % Standard, mindestens 5 % | 20 % Standard, mindestens 2,5 % |
| Dataflows | 20 % Standard, mindestens 8 %  | 20 % Standard, mindestens 4 %  | 20 % Standard, mindestens 2 % | 20 % Standard, mindestens 1 %  |
| | | | | |

#### <a name="microsoft-azure-skus-for-platform-as-a-service-paas-scenarios"></a>Microsoft Azure-SKUs für Plattform-as-a-Service-Szenarios (PaaS)

|                  | A1                       | A2                       | A3                      | A4                       | A5                      | A6                        |
|-------------------|--------------------------|--------------------------|-------------------------|--------------------------|-------------------------|---------------------------|
| Paginierte Berichte | N/V                      | N/V                      | N/V                     | 20 % Standard, mindestens 10 % | 20 % Standard, mindestens 5 % | 20 % Standard, mindestens 2,5 % |
| Dataflows         | 27 % Standard, mindestens 27 % | 20 % Standard, mindestens 16 % | 20 % Standard, mindestens 8 % | 20 % Standard, mindestens 4 %  | 20 % Standard, mindestens 2 % | 20 % Standard, mindestens 1 %   |

### <a name="considerations-for-paginated-reports"></a>Überlegungen zu paginierten Berichten

Wenn Sie die Workload für paginierte Berichte verwenden, beachten Sie die folgenden Aspekte.

* **Speicherbelegung in paginierten Berichten:** Mit paginierten Berichten können Sie Ihren eigenen Code beim Rendern eines Berichts ausführen (z. B. dynamisches Ändern der Textfarbe basierend auf dem Inhalt). Vor diesem Hintergrund wird die Power BI Premium-Kapazität gesichert, indem paginierte Berichte in einem Bereich innerhalb der Kapazität ausgeführt werden. Diesem Bereich wird der maximale Arbeitsspeicher zugewiesen, den Sie angeben, unabhängig davon, ob die Workload aktiv ist. Wenn Sie Power BI-Berichte oder Dataflows in der gleichen Kapazität verwenden, legen Sie den Arbeitsspeicher für paginierte Berichte so niedrig fest, dass er die anderen Workloads nicht beeinträchtigt.

* **Paginierte Berichte sind nicht verfügbar:** In seltenen Fällen kann es vorkommen, dass die Workload von paginierten Berichten nicht verfügbar ist. In diesem Fall zeigt die Workload einen Fehlerstatus im Verwaltungsportal an, und den Benutzern werden Timeouts für das Rendern von Berichten angezeigt. Um dieses Problem zu beheben, deaktivieren Sie die Workload, und aktivieren Sie sie dann erneut.

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
