---
title: Was ist Microsoft Power BI Premium?
description: Power BI Premium bietet dedizierte Kapazität für Ihre Organisation oder Ihr Team, sodass Sie von verlässlicherer Leistung und größeren Datenmengen profitieren, ohne Benutzerlizenzen kaufen zu müssen.
author: minewiskan
ms.author: owend
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 02/28/2019
ms.custom: seodec18
LocalizationGroup: Premium
ms.openlocfilehash: cb9280f47f1f2d28ce6fabda2dbc173fbdc837ac
ms.sourcegitcommit: 364ffa1178cdfb0a20acffc0fd79922ebc892d72
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/02/2019
ms.locfileid: "57226133"
---
# <a name="what-is-microsoft-power-bi-premium"></a>Was ist Microsoft Power BI Premium?

> [!NOTE]
> Dieser Artikel wird gerade mit Beschreibungen neuer Features und ausführlicheren Informationen aktualisiert. Außerdem wird die Lesbarkeit verbessert. Die neuesten Informationen finden Sie unter [Deploying and Managing Power BI Premium Capacities](whitepaper-powerbi-premium-deployment.md) (Bereitstellen und Verwalten von Power BI Premium-Kapazitäten).

Power BI Premium bietet dedizierte Ressourcen für die Ausführung des Power BI-Diensts für Ihre Organisation, sodass Sie von verlässlicherer Leistung und größeren Datenmengen profitieren. Premium ermöglicht darüber hinaus die weite Verteilung von Inhalten, ohne dass Sie für jeden einzelnen Benutzer des Inhalts Power BI Pro-Lizenzen erwerben müssen.  

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

In der folgenden Tabelle finden Sie eine Zusammenfassung der Unterschiede zwischen einer gemeinsam genutzten Kapazität und der Premium-Kapazität:

|  | Gemeinsam genutzte Kapazität | Power BI Premium-Kapazität |
| --- | --- | --- |
| **Aktualisierungsrate** |8/Tag |48/Tag |
| Isolation mit dedizierter Hardware |![Nicht verfügbar](media/service-premium/not-available.png) |![](media/service-premium/available.png) |
| Unternehmensverteilung an *alle Benutzer* | | |
| Apps und Freigabe |![Nicht verfügbar](media/service-premium/not-available.png) |![](media/service-premium/available.png) |
| Eingebettete API und Steuerelemente |![Nicht verfügbar](media/service-premium/not-available.png) |![](media/service-premium/available.png)<sup>[1](#fnt1)</sup> |
| Lokale Veröffentlichung von Power BI-Berichten |![Nicht verfügbar](media/service-premium/not-available.png) |![](media/service-premium/available.png) |
| | | |

<a name="fnt1">1</a> Zukünftige Verbesserungen, die in Power BI Premium eingeführt werden.



### <a name="premium-capacity-nodes"></a>Knoten für Premium-Kapazität

Power BI Premium steht in Knotenkonfigurationen mit abweichenden V-Kernkapazitäten zur Verfügung. Weitere Informationen zu bestimmten SKU-Angeboten und Kosten finden Sie unter [Power BI-Preise](https://powerbi.microsoft.com/pricing/). Darüber hinaus ist ein [Kostenrechner](https://powerbi.microsoft.com/calculator/) verfügbar. Informationen zur Kapazitätsplanung für die eingebettete Analyse finden Sie unter [Planning a Power BI Enterprise Deployment whitepaper (Whitepaper zum Planen einer Unternehmensbereitstellung von Power BI)](https://aka.ms/pbienterprisedeploy). Zusammenfassung:

* P-Knoten können für eingebettete Bereitstellungen oder Dienstbereitstellungen verwendet werden.

* EM-Knoten können nur für eingebettete Bereitstellungen verwendet werden. EM-Knoten haben keinen Zugriff auf Premium-Funktionen, z.B. die Freigabe von Apps für Benutzer, die keine Power BI Pro-Lizenz besitzen.

| Kapazitätsknoten | Gesamtzahl an V-Kernen<br/>*(Back-End + Front-End)*  | Back-End-V-Kerne <sup>[1](#fn1)</sup> | Front-End-V-Kerne <sup>[2](#fn2)</sup> | Grenzwerte für DirectQuery/Liveverbindung | Maximale Anzahl gleichzeitiger Aktualisierungen |  Verfügbarkeit
| --- | --- | --- | --- | --- | --- | --- | --- |
| EM1 (monatlich) |1 V-Kern |0,5 V-Kerne, 2,5 GB RAM |0,5 V-Kerne |3,75 pro Sekunde |  1 | Verfügbarkeit |
| EM2 (monatlich) |2 V-Kerne |1 V-Kern, 5 GB RAM |1 V-Kern |7,5 pro Sekunde |  2 | Verfügbarkeit |
| EM3 (monatlich) |4 V-Kerne |2 V-Kerne, 10 GB RAM |2 V-Kerne | | 3 |  Verfügbarkeit |
| P1 |8 V-Kerne |4 V-Kerne, 25 GB RAM |4 V-Kerne |30 pro Sekunde | 6 | Verfügbar (auch monatlich) |
| P2 |16 V-Kerne |8 V-Kerne, 50 GB RAM |8 V-Kerne |60 pro Sekunde | 12 | Verfügbarkeit |
| P3 |32 V-Kerne |16 V-Kerne, 100 GB RAM |16 V-Kerne |120 pro Sekunde | 24 | Verfügbarkeit |
| | | | | | | |

<a name="fn1">1</a>: Front-End-V-Kerne sind für den Webdienst verantwortlich. Hierzu gehören beispielsweise die Verwaltung von Dashboard und Berichtsdokumenten, die Zugriffsrechteverwaltung, Zeitplanung, APIs, Uploads und Downloads sowie allgemein alle Aufgaben in Bezug auf die Benutzeroberfläche. 

<a name="fn2">2</a>: Back-End-V-Kerne übernehmen den Hauptteil der Arbeit: Abfrageverarbeitung, Cacheverwaltung, Ausführen von R-Servern, Datenaktualisierung, Verarbeitung von natürlicher Sprache, Echtzeitfeeds und serverseitiges Laden von Berichten und Bildern. Zusammen mit den Back-End-V-Kernen wird auch eine bestimmte Menge Arbeitsspeicher reserviert. Die Verfügbarkeit einer ausreichend großen Arbeitsspeichermenge ist insbesondere dann wichtig, wenn große Datenmodelle oder Modelle mit einer großen Anzahl aktiver Datasets verarbeitet werden müssen.

## <a name="workloads-in-premium-capacity"></a>Workloads in Premium-Kapazität

Standardmäßig unterstützen **Power BI Premium**- und **Power BI Embedded**-Kapazitäten nur die Workload, die mit der Ausführung von Power BI-Abfragen in der Cloud verbunden ist. Premium unterstützt auch zusätzliche Workloads für **KI**, **Dataflows** und **paginierte Berichte**. Sie aktivieren diese Workloads im Power BI-Verwaltungsportal oder über die Power BI-REST-API. Sie legen auch den maximalen Arbeitsspeicherverbrauch für jede Workload fest. So können Sie steuern, wie sich die verschiedenen Workloads gegenseitig beeinflussen. Weitere Informationen finden Sie unter [Konfigurieren von Workloads in einer Premium-Kapazität](service-admin-premium-workloads.md).

### <a name="default-memory-settings"></a>Standardeinstellungen für den Arbeitsspeicher

Die folgende Tabelle zeigt die Standard- und Mindestwerte für den Arbeitsspeicher, basierend auf den verschiedenen verfügbaren [Kapazitätsknoten](#premium-capacity-nodes). Der Arbeitsspeicher wird Dataflows dynamisch zugeordnet, ist paginierten Berichten jedoch statisch zugeordnet. Weitere Informationen finden Sie im nächsten Abschnitt [Überlegungen zu paginierten Berichten](#considerations-for-paginated-reports).

#### <a name="microsoft-office-skus-for-software-as-a-service-saas-scenarios"></a>Microsoft Office-SKUs für Software-as-a-Service-Szenarios (SaaS)

|                     | EM3                      | P1                       | P2                      | P3                       |
|---------------------|--------------------------|--------------------------|-------------------------|--------------------------|
| Paginierte Berichte | – | 20 % Standard, mindestens 10 % | 20 % Standard, mindestens 5 % | 20 % Standard, mindestens 2,5 % |
| Dataflows | 20 % Standard, mindestens 8 %  | 20 % Standard, mindestens 4 %  | 20 % Standard, mindestens 2 % | 20 % Standard, mindestens 1 %  |
| | | | | |

#### <a name="microsoft-azure-skus-for-platform-as-a-service-paas-scenarios"></a>Microsoft Azure-SKUs für Plattform-as-a-Service-Szenarios (PaaS)

|                  | A1                       | A2                       | A3                      | A4                       | A5                      | A6                        |
|-------------------|--------------------------|--------------------------|-------------------------|--------------------------|-------------------------|---------------------------|
| Paginierte Berichte | –                      | N/V                      | –                     | 20 % Standard, mindestens 10 % | 20 % Standard, mindestens 5 % | 20 % Standard, mindestens 2,5 % |
| Dataflows         | 27 % Standard, mindestens 27 % | 20 % Standard, mindestens 16 % | 20 % Standard, mindestens 8 % | 20 % Standard, mindestens 4 %  | 20 % Standard, mindestens 2 % | 20 % Standard, mindestens 1 %   |

### <a name="considerations-for-paginated-reports"></a>Überlegungen zu paginierten Berichten

Beachten Sie bei Verwendung der Workload für paginierte Berichte Folgendes: Mit paginierten Berichten können Sie beim Rendern eines Berichts Ihren eigenen Code ausführen (z.B. dynamisches Ändern der Textfarbe basierend auf dem Inhalt). Vor diesem Hintergrund wird die Power BI Premium-Kapazität gesichert, indem paginierte Berichte in einem Bereich innerhalb der Kapazität ausgeführt werden. Diesem Bereich wird der maximale Arbeitsspeicher zugewiesen, den Sie angeben, unabhängig davon, ob die Workload aktiv ist. Wenn Sie Power BI-Berichte oder Dataflows in der gleichen Kapazität verwenden, legen Sie den Arbeitsspeicher für paginierte Berichte so niedrig fest, dass er die anderen Workloads nicht beeinträchtigt.

In seltenen Fällen kann es vorkommen, dass die Workload von paginierten Berichten nicht verfügbar ist. In diesem Fall zeigt die Workload einen Fehlerstatus im Verwaltungsportal an, und den Benutzern werden Timeouts für das Rendern von Berichten angezeigt. Um dieses Problem zu beheben, deaktivieren Sie die Workload, und aktivieren Sie sie dann erneut.

## <a name="power-bi-report-server"></a>Power BI-Berichtsserver

Power BI Premium enthält auch die Funktion zum lokalen Ausführen von Power BI-Berichtsserver in Ihrem Unternehmen. Weitere Informationen finden Sie unter [Erste Schritte mit Power BI-Berichtsserver](report-server/get-started.md).

## <a name="next-steps"></a>Nächste Schritte

[Deploying and Managing Power BI Premium Capacities](whitepaper-powerbi-premium-deployment.md)  (Bereitstellen und Verwalten von Power BI Premium-Kapazitäten)  
[Erwerben von Power BI Premium](service-admin-premium-purchase.md)   
[Power BI Premium – Häufig gestellte Fragen (FAQ)](service-premium-faq.md)   



Weitere Fragen? [Stellen Sie Ihre Frage in der Power BI-Community.](https://community.powerbi.com/)
