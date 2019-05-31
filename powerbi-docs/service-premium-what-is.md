---
title: Was ist Microsoft Power BI Premium?
description: Power BI Premium bietet dedizierte Kapazität für Ihre Organisation bietet Ihnen verlässlicherer Leistung und größeren Datenmengen, ohne dass Sie pro Benutzer erforderliche Lizenzen zu erwerben.
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 04/22/2019
ms.custom: seodec18
LocalizationGroup: Premium
ms.openlocfilehash: e5ffa624bf69cf470aade076c80ac37028a55456
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2019
ms.locfileid: "65565260"
---
# <a name="what-is-power-bi-premium"></a>Was ist Power BI Premium?

Power BI Premium bietet dedizierte und verbesserte Ressourcen zum Ausführen von Power BI-Dienst für Ihre Organisation. Beispiel:

- Eine größere Skalierung und Leistung
- Flexibilität mit Lizenz von Kapazität
- Vereinheitlichen der Self-Service und Unternehmens-BI
- Erweitern von lokalen BI mit Power BI-Berichtsserver
- Unterstützung für datenresidenz nach Region (Multi-Geo Capabilities)
- Freigeben Sie Daten für andere, ohne den Erwerb einer Lizenz pro Benutzer

In diesem Artikel ist nicht vorgesehen, um ausführliche Informationen über jedes Feature von Power BI Premium – in der Tat bereitzustellen, es wird nur die Oberfläche berührt. Bei Bedarf werden Links zu weiteren Artikeln mit ausführlicheren Informationen bereitgestellt.

## <a name="subscriptions-and-licensing"></a>Abonnements und Lizenzen

Power BI Premium ist ein auf Mandantenebene Office 365-Abonnement in zwei SKU (Stock Keeping Unit)-Familien verfügbar:

- **EM** SKUs (EM1-EM3) für das einbetten, erfordern eine jährliche Verpflichtung, monatlich in Rechnung gestellt.
- **P** SKUs (P1-P3) einbetten und Enterprise-Funktionen erfordern eine monatliche oder jährliche Verpflichtung monatlich in Rechnung gestellt, und enthält eine Lizenz für Power BI-Berichtsserver lokal installieren.

Ein alternativer Ansatz ist der Kauf einer **Azure Power BI Embedded** -Abonnement, das einem einzelnen **ein** nur zu Testzwecken (A1-A6) SKU-Familie für die Einbettung und Kapazitätstests durch. Alle SKUs bieten V-Kerne zum Erstellen von Kapazitäten, aber die EM-SKUs sind für Einbetten von kleineren Skalierung eingeschränkt. EM1 und EM2, A1 A2-SKUs mit weniger als vier V-Kerne werden für dedizierte Infrastruktur nicht ausgeführt.

Während der Schwerpunkt dieses Artikels auf der P-SKUs ist, sind viele der erläuterungen auch relevant für die A-SKUs. Im Gegensatz zu den Premium-Abonnement können Sie SKUs, die Azure-SKUs erfordern keine Zeitaufwand und abgerechnet wird. Sie bieten vollständige Skalierung aktivieren, um Flexibilität, zentral Herunterskalieren, Pause-, fortsetzen- und löschen. 

Azure Power BI Embedded wird im Rahmen dieses Artikels zum größten Teil, aber es wird beschrieben, der [testen Ansätze](service-premium-capacity-optimize.md#testing-approaches) Abschnitt des Artikels Optimieren von Premium-Kapazitäten als praktische und wirtschaftliche-Option von Tests und Messungen Workloads. Weitere Informationen zu Azure-SKUs finden Sie unter [Dokumentation zu Azure Power BI Embedded](https://azure.microsoft.com/services/power-bi-embedded/).

### <a name="purchasing"></a>Erwerb von

Power BI-Premium-Abonnements werden von Administratoren im Microsoft 365 Administrationscenter gekauft. Insbesondere können nur globale Office 365 oder Administratoren Abrechnung SKUs erwerben. Wenn erworben haben, erhält der Mandant keine entsprechende Anzahl von V-Kerne zum Zuweisen von Kapazitäten, bekannt als *V-Kern-pooling*. Beispielsweise stellt der Erwerb einer P3-SKU des Mandanten mit 32 V-Kerne. Weitere Informationen finden Sie unter [zum Erwerb von Power BI Premium](service-admin-premium-purchase.md).

## <a name="dedicated-capacities"></a>Dedizierte Kapazität

Mit Power BI Premium, erhalten Sie *dedizierten Kapazitäten*. Im Gegensatz zu einer gemeinsam genutzten Kapazität, wenn die Workloads auf Computerressourcen gemeinsam mit anderen Kunden ausführen, ist eine dedizierte Kapazität für die ausschließliche Verwendung von einer anderen Organisation ein. Es wurde mit dedizierten Compute-Ressourcen isoliert, die zuverlässige und konsistente Leistung für gehosteten Inhalt zu bieten. 

Arbeitsbereiche befinden sich in Kapazitäten. Jeder Power BI-Benutzer hat einen persönlichen Arbeitsbereich, bekannt als **Arbeitsbereich**. Zusätzliche Arbeitsbereiche können erstellt werden, um die Zusammenarbeit und die Bereitstellung zu ermöglichen, und diese werden als bezeichnet **App-Arbeitsbereiche**. Standardmäßig sind Arbeitsbereiche, einschließlich der persönlichen Arbeitsbereiche, die gemeinsam genutzte Kapazität erstellt. Wenn Sie Premium-Kapazitäten verfügen, können Premium-Kapazitäten sowohl Meine Arbeitsbereiche und App-Arbeitsbereichen zugewiesen werden.

### <a name="capacity-nodes"></a>Kapazität von Knoten

Siehe die [Subscriptions und Lizenzierung](#subscriptions-and-licensing) Abschnitt, gibt es zwei Power BI Premium-SKU-Familien: **EM** und **P**. Alle Power BI Premium-SKUs stehen als Kapazität *Knoten*, die jeweils die Ressourcen, die der Prozessor, Arbeitsspeicher und Speicher aus einen festgelegten Zeitraum darstellt. Zusätzlich zu den Ressourcen jede SKU hat funktionsbegrenzungen, auf die Anzahl von DirectQuery und Liveverbindung Verbindungen pro Sekunde und die Anzahl der parallelen Modell aktualisiert.

Verarbeitung erfolgt durch eine festgelegte Anzahl von V-Kerne, gleichmäßig zwischen Back-End- und Front-End unterteilt.

**Back-End-V-Kerne** sind verantwortlich für die Core-Power BI-Funktionen, einschließlich der abfrageverarbeitung, cacheverwaltung, Ausführen von R Services, Aktualisierung des Modells, die Verarbeitung natürlicher Sprache (Q & A) und serverseitiges Rendering von Berichten und Bildern. Back-End-V-Kerne werden eine feste Menge an Arbeitsspeicher die in erster Linie verwendet wird, der Host-Modellen, auch bekannt als aktiver Datasets zugewiesen werden.

**Front-End-V-Kerne** sind verantwortlich für die Web Service, Dashboard und Bericht dokumentverwaltung, zugriffsrechteverwaltung, zeitplanung, APIs, uploads downloads und Allgemein für alles im Zusammenhang mit der Benutzer hat.

Storage nastaven NA hodnotu **100 TB pro kapazitätsknoten**.

Die Ressourcen und die Grenzen der einzelnen Premium-SKU (und gleichermaßen Größe ein SKU) werden in der folgenden Tabelle beschrieben:

| Kapazität von Knoten | Gesamtzahl an V-Kernen | Back-End-V-Kerne | RAM (GB) | Front-End-V-Kerne | DirectQuery/Liveverbindung (pro Sekunde) | Modell aktualisieren Parallelität |
| --- | --- | --- | --- | --- | --- | --- |
| EM1/A1 | 1 | 0,5 | 2.5 | 0,5 | 3.75 | 1 |
| EM2/A2 | 2 | 1 | 5 | 1 | 7.5 | 2 |
| EM3/A3 | 4 | 2 | 10 | 2 | 15 | 3 |
| P1/A4 | 8 | 4 | 25 | 4 | 30 | 6 |
| P2/A5 | 16 | 8 | 50 | 8 | 60 | 12 |
| P3/A6 | 32 | 16 | 100 | 16 | 120 | 24 |
| | | | | | | |

### <a name="capacity-workloads"></a>Capacity-workloads

Capacity-Workloads sind Dienste, die Benutzern zur Verfügung gestellt. Premium- und Azure-Kapazitäten Unterstützung standardmäßig nur eine Dataset-Workload, die mit der Ausführung von Abfragen mit Power BI. Die Dataset-Workload kann nicht deaktiviert werden. Zusätzlicher Workloads können aktiviert werden, für die [AI (Cognitive Services)](https://powerbi.microsoft.com/blog/easy-access-to-ai-in-power-bi-preview/), [Datenflüsse](service-dataflows-overview.md#dataflow-capabilities-on-power-bi-premium), und [paginierte Berichte](paginated-reports-save-to-power-bi-service.md). Diese Workloads werden nur für Premium-Abonnements unterstützt. 

Jede zusätzliche Arbeitslast ermöglicht das Konfigurieren des maximalen Arbeitsspeichers (als Prozentsatz des gesamten verfügbaren Arbeitsspeichers), der von der arbeitsauslastung verwendet werden kann. Standardwerte für den maximalen Arbeitsspeicher werden nach SKU bestimmt. Sie können die Kapazität der verfügbaren Ressourcen maximieren, indem nur die zusätzlichen Workloads aktivieren, wenn sie verwendet werden. Und Sie können ändern, Arbeitsspeicher, dass Einstellungen nur, wenn Sie die Einstellungen der Standardrichtlinie ermittelt haben Ihre kapazitätsanforderungen für die Ressource nicht erfüllt werden. Arbeitsauslastungen aktiviert und für eine Kapazität von kapazitätsadministratoren mit konfiguriert werden können, **kapazitätseinstellungen** in die [-Verwaltungsportal](service-admin-portal.md) oder mithilfe der [Kapazitäten-REST-APIs](https://docs.microsoft.com/rest/api/power-bi/capacities).  

![Aktivieren von Workloads](media/service-admin-premium-workloads/admin-portal-workloads.png)

Weitere Informationen finden Sie unter [Konfigurieren von Workloads in einer Premium-Kapazität](service-admin-premium-workloads.md). 

### <a name="how-capacities-function"></a>Wie Kapazitäten-Funktion

AT wird immer im Power BI-Dienst kapazitätsressourcen beim Überschreiten von Grenzwerten für die Kapazität auferlegt nicht optimal nutzen.

Capacity-Vorgänge werden entweder als klassifiziert *interaktive* oder *Hintergrund*. Interaktive Vorgänge enthalten, Rendern von Anforderungen und die Reaktion auf Benutzerinteraktionen (filtern, Q & A-Abfragen usw.). Im Allgemeinen ist die Import-Modell abgefragt Arbeitsspeicher ressourcenintensiv, während Abfragen von Modellen für DirectQuery und Liveverbindung CPU-intensiv ist. Hintergrundvorgänge Datenfluss einschließen, und importieren Sie Modell aktualisiert und das Dashboard Abfrage Zwischenspeichern.

Es ist wichtig zu verstehen, dass interaktive Vorgänge immer über die Hintergrundvorgänge ausgeführt, um sicherzustellen, dass die bestmögliche benutzerumgebung priorisiert werden. Wenn nicht genügend Ressourcen vorhanden sind, werden die Hintergrundvorgänge hinzugefügt, an eine Warteschlange zur Verarbeitung, wenn Ressourcen frei. Hintergrundvorgänge, z.B. das Dataset aktualisiert, können beendet mitten von Power BI-Dienst und einer Warteschlange hinzugefügt.

Importmodelle müssen vollständig in den Arbeitsspeicher geladen werden, damit diese abgefragt oder aktualisiert werden können. Power BI-Dienst verwaltet Speicher der Nutzung von anspruchsvolle Algorithmen, um sicherzustellen, dass maximal verfügbaren Arbeitsspeicher nutzen, und committen die Kapazität zu verursachen kann: Es ist möglich, für eine Kapazität zum Speichern von vielen importieren (bis zu 100 TB pro Premium-Kapazität) modelliert, wenn die kombinierte Datenträgerspeicher überschreitet den unterstützten Speicher (zusätzlicher Speicher ist erforderlich, zum Abfragen und aktualisieren), können nicht diese alle an in den Speicher geladen werden gleichzeitig.

Importmodelle werden aus diesem Grund in geladen und aus dem Speicher entsprechend der Verwendung entfernt. Ein Modell importieren wird geladen, wenn es sich um abgefragten (interaktive Vorgang) ist und noch nicht im Arbeitsspeicher, oder wenn es aktualisiert werden (Vorgang im Hintergrund).

Das Entfernen eines Modells aus dem Arbeitsspeicher wird als bezeichnet *Entfernung*. Es ist ein Vorgang, den Power BI abhängig von der Größe der Modelle schnell ausführen können. Wenn die Kapazität jeder ungenügendem Arbeitsspeicher nicht auftreten, werden Modelle sind einfach in den Arbeitsspeicher geladen und bleiben dort. Wenn nicht genügend Arbeitsspeicher zum Laden eines Modells verfügbar ist, wird Power BI-Dienst zuerst Freigeben von Arbeitsspeicher müssen allerdings. Gibt Arbeitsspeicher frei, durch das Erkennen von Modellen, die inaktiv haben durch Suchvorgänge Modelle, die nicht in den letzten drei Minuten verwendet wurden \[ [1](#endnote-1)\], und klicken Sie dann entfernen sie. Wenn es keine inaktiven Modelle gibt zu entfernen, versucht Power BI-Dienst für Hintergrundoperationen geladene Modelle zu entfernen. Letzte Möglichkeit, nach 30 Sekunden nicht erfolgreicher Versuche \[ [1](#endnote-1)\], besteht darin, das interaktive fehl. In diesem Fall wird der Benutzer des Berichts bildschirmaufnahmedatei eine Empfehlung, versuchen es in Kürze informiert. In einigen Fällen können Modelle aus dem Arbeitsspeicher aufgrund von Dienstvorgängen entladen werden.

Es ist wichtig zu betonen, dass das Dataset Entfernung ein normales und erwartetes Verhalten ist. Es zielt darauf ab, zum Maximieren der speicherauslastung durch Laden und Entladen von Modellen, die zusammen mit verfügbaren Arbeitsspeicher überschreiten können. Dies ist beabsichtigt, und für Benutzer des Berichts vollständig transparent. Hohe entfernungsraten bedeuten nicht unbedingt, dass die Kapazität unzureichend Ressourcen zugewiesen ist. Sie können jedoch einem Problem werden, wenn die Abfrage oder Aktualisierung Reaktionsfähigkeit aufgrund hoher entfernungsraten warnungskontext.

Aktualisierungen von importmodelle sind immer Arbeitsspeicheraufwand hoch, wie Modelle in den Arbeitsspeicher geladen werden müssen. Zusätzlicher Speicher ist für die Verarbeitung erforderlich. Eine vollständige Aktualisierung kann ungefähr doppelt so viel Arbeitsspeicher, die das Modell benötigte eingabedatenschema verwenden. Dadurch wird sichergestellt, dass das Modell abgefragt werden kann, sogar während der Verarbeitung, da Abfragen für das vorhandene Modell, gesendet werden, bis die Aktualisierung abgeschlossen wurde und die neue Modelldaten verfügbar sind. Die inkrementelle Aktualisierung erfordert weniger Arbeitsspeicher und kann schneller ausgeführt werden kann und daher nicht genügend kapazitätsressourcen erheblich reduzieren. Aktualisierungen können auch die CPU-intensiv sein für Modelle, vor allem solche mit komplexen Power Query-Transformationen oder berechneten Tabellen/Spalten, die komplex sind oder für große Tabellen basieren.

Aktualisierungen, wie Abfragen, erfordern das Modell in den Arbeitsspeicher geladen werden. Wenn nicht genügend Arbeitsspeicher verfügbar ist, versucht Power BI-Dienst zum Löschen der inaktiv Modelle, und wenn dies nicht möglich ist (wie alle Modelle aktiv sind), der Aktualisierungsauftrag in die Warteschlange eingereiht. Aktualisierungen werden in der Regel CPU-intensiv, mehr dennoch als Abfragen. Aus diesem Grund stehen Kapazitätsgrenzen für die Anzahl der gleichzeitigen Aktualisierungen, legen Sie auf 1,5 Mal die Anzahl der Back-End-V-Kerne, die aufgerundet. Wenn zu viele gleichzeitige Aktualisierungen sind, wird eine geplante Aktualisierung in die Warteschlange eingereiht werden. Wenn diese Situationen auftreten, dauert es länger, bis die Aktualisierung abzuschließen. Bei Bedarf aktualisiert werden, z. B. durch eine benutzeranforderung ausgelöst wird, oder ein API-Aufruf wird dreimal wiederholt \[ [1](#endnote-1)\]. Wenn es immer noch nicht genügend Ressourcen, schlägt die Aktualisierung fehl.

Im Abschnitt Hinweise:   
<a name="endnote-1"></a>\[1\] vorbehalten.

### <a name="regional-support"></a>Unterstützung der Regionen

Beim Erstellen einer neuen Kapazität, globale Office 365 und Power BI-Dienstadministratoren angeben kann, befindet sich eine Region, in dem die Kapazität Arbeitsbereiche zugewiesen. Dies bezeichnet man als **Multi-Geo Capabilities**. Mit Multi-Geo Capabilities können Organisationen Daten vor-Ort-Anforderungen erfüllen durch Bereitstellung von Inhalten in Rechenzentren in einer bestimmten Region, auch wenn sie andere als die Region ist in dem sich das Office 365-Abonnement befindet. Weitere Informationen finden Sie unter [Multi-Geo-Unterstützung für Power BI Premium](service-admin-premium-multi-geo.md).

### <a name="capacity-management"></a>Das Capacity management

Verwalten von Premium-Kapazitäten umfasst, erstellen oder Löschen von Kapazitäten, Zuweisen von Administratoren, Zuweisen von Arbeitsbereichen, Konfigurieren von Workloads, Überwachung, und nehmen Anpassungen vor, um die Kapazität zu optimieren. 

Globale Administratoren von Office 365 und Power BI-Dienstadministratoren können Premium-Kapazitäten verfügbaren V-Kerne erstellen oder Ändern von vorhandenen Premium-Kapazitäten. Wenn eine Kapazität erstellt wird, kapazitätsumfang und geografischen Region angegeben sind, und mindestens ein kapazitätsadministrator zugewiesen wird. 

Wenn Kapazitäten erstellt werden, werden die meisten administrative Aufgaben abgeschlossen, der [Verwaltungsportal](service-admin-portal.md).

![Verwaltungsportal](media/service-premium-what-is/premium-admin-portal.png)

Kapazitätsadministratoren können die Kapazität Arbeitsbereiche zuweisen, Verwalten von Benutzerberechtigungen und andere Administratoren zuweisen. Kapazitätsadministratoren können auch Workloads, Anpassen der speicherbelegung, konfigurieren und bei Bedarf neu starten eine Kapazität, Zurücksetzen der Vorgänge bei einer Überladung der Kapazität.

![Verwaltungsportal](media/service-premium-what-is/premium-admin-portal-mgmt.png)

Kapazitätsadministratoren können außerdem stellen Sie sicher, dass eine Kapazität reibungslos ausgeführt wird. Sie können Kapazität Integrität rechts im Administratorportal oder mithilfe der Premium-Kapazität Metriken app überwachen.

Weitere Informationen zu Kapazitäten erstellen, Zuweisen von Administratoren und Zuweisen von Arbeitsbereichen finden Sie unter [Verwalten von Premium-Kapazitäten](service-premium-capacity-manage.md). Weitere Informationen zu Rollen finden Sie unter [Administratorrollen im Zusammenhang mit der Power BI](service-admin-administering-power-bi-in-your-organization.md#administrator-roles-related-to-power-bi).

### <a name="monitoring"></a>Monitoring

Überwachen von Premium-Kapazitäten bietet Administratoren einen Überblick über die Leistung von Kapazitäten. Kapazitäten über das Admin-Portal überwacht werden können und die [Kapazitätsmetriken für Power BI Premium-app](https://app.powerbi.com/groups/me/getapps/services/capacitymetrics).

Überwachen im Portal stellt einen schnellen Überblick mit allgemeinen Metriken, der angibt, lädt platziert und die Ressourcen, die von Ihrer Kapazität, gemittelt, über den letzten sieben Tagen genutzt werden. 

![Verwaltungsportal](media/service-premium-what-is/premium-admin-portal-health.png)

Die **Kapazitätsmetriken für Power BI Premium** app enthält, die am häufigsten ausführliche Informationen in die Leistung von Ihre Kapazitäten. Die app bietet ein Dashboard auf hoher Ebene und ausführlichere Berichte.

![Metrik-App-Dashboard](media/service-admin-premium-monitor-capacity/app-dashboard.png)

Die app Dashboard klicken Sie auf einer Metrik Zelle, um einen detaillierten Bericht zu öffnen. Berichte enthalten, die ausführliche Metriken und die Filterfunktion, um auf die wichtigsten Informationen Sie Detailinformationen benötigen, um Ihre Kapazitäten laufen zu halten.

![Periodische Spitzen Abfrage Wartezeit Anzahl potenzieller die CPU-Auslastung angeben](media/service-premium-capacity-scenarios/peak-query-wait-times.png)

Weitere Informationen zum Überwachen von Kapazitäten finden Sie unter [im Power BI-Verwaltungsportal Überwachen](service-admin-premium-monitor-portal.md) und [Überwachung mit der app für Power BI Premium-Kapazitätsmetriken](service-admin-premium-monitor-capacity.md).

### <a name="optimizing-capacities"></a>Optimieren von Kapazitäten

Die optimale Nutzung der Ihre Kapazitäten für die Sicherstellung der Benutzer der Leistungs wichtig ist, und Sie erhalten die Vorteile für Ihre Premium-Investition. Überwachung des Schlüsselmetriken können Administratoren ermitteln, wie sich Engpässe und erforderliche Maßnahmen. Weitere Informationen finden Sie unter [Optimieren von Premium-Kapazitäten](service-premium-capacity-optimize.md) und [Szenarien für Premium-Kapazität](service-premium-capacity-scenarios.md).

### <a name="capacities-rest-apis"></a>Kapazitäten REST-APIs

Die Power BI-REST-APIs enthalten eine Reihe von [Kapazitäten APIs](https://docs.microsoft.com/rest/api/power-bi/capacities). Mit den APIs können Administratoren programmgesteuert auf viele Aspekte der Ihre Premium-Kapazitäten, einschließlich aktivieren und Deaktivieren von Workloads und Zuweisen von Arbeitsbereichen zu einer Kapazität und vieles mehr verwalten.

## <a name="large-datasets"></a>Große datasets

Abhängig von der SKU, Power BI Premium unterstützt Power BI Desktop (.pbix) Modell Uploaddateien maximal **10 GB** Größe. Wenn geladen, kann das Modell mit einem Arbeitsbereich einer Premium-Kapazität zugewiesen veröffentlicht werden. Das Dataset kann dann aktualisiert werden, um bis zu **12 GB** Größe.

### <a name="size-considerations"></a>Überlegungen zu Größen

Große Modelle können ressourcenintensiv sein. Sie sollten mindestens eine P1-SKU für Modelle mit mehr als 1 GB verfügen. Obwohl veröffentlichen große Modelle mit Arbeitsbereichen, die von A-SKUs auf A3 unterstützt konnte nicht Arbeit aktualisiert wird.

In der folgenden Tabelle werden die empfohlenen SKUs für verschiedene PBIX-Größen aufgeführt:

   |SKU  |PBIX-Größe   |
   |---------|---------|
   |P1    | < 3 GB        |
   |P2    | < 6 GB        |
   |P3, P4, P5    | bis zu 10 GB   |

Die A4-SKU für Power BI Embedded entspricht der P1-SKU, A5 entspricht P2 und A6 entspricht P3. Beachten Sie, dass beim Veröffentlichen von großen Modellen in A- und EM-SKUs möglicherweise Fehler zurückgegeben werden, die sich nicht auf den Fehler zur Begrenzung der Modellgröße in der gemeinsam genutzten Kapazität beziehen. Aktualisierungsfehler bei großen Modellen in A- und EM-SKUs verweisen häufig auf Timeouts. 

Pbix-Dateien darstellen, Daten in einem *stark komprimiert Zustand*. Die Daten werden in den meisten Fällen beim Laden in den Speicher mehrmals größer, ebenso wie anschließend bei jeder Datenaktualisierung.

Geplante Aktualisierung von großen Datasets kann lange dauern und ressourcenintensiv sein. Es ist wichtig, die nicht zu viele parallele Aktualisierungen zu planen. Es empfiehlt sich [inkrementelle Aktualisierung](service-premium-incremental-refresh.md) konfiguriert ist, da sie schnelleren, zuverlässigeren und weniger Ressourcen beansprucht.

Den ersten Bericht laden umfangreicher Datasets kann lange dauern, wenn es eine Weile, da das letzte Mal wurde, die das Dataset verwendet wurde. Der Ladevorgang wird bei Berichten mit längerer Ladezeit in einer Statusanzeige angezeigt.

Während die pro Abfrage Arbeitsspeicher und die Zeit in Premium-Kapazität deutlich höher sind, empfiehlt es sich, dass Sie Filter und Slicer verwenden, um visuelle Elemente zum Anzeigen von wirklich benötigten zu beschränken.

## <a name="incremental-refresh"></a>Inkrementelle Aktualisierung

Die inkrementelle Aktualisierung bietet einen wesentlicher Bestandteil müssen, und warten große Datasets in Power BI Premium. Die inkrementelle Aktualisierung hat viele Vorteile, z. B. sind Aktualisierungen schneller, da nur Daten, die geänderten muss aktualisiert werden. Aktualisierungen sind zuverlässiger, da es nicht erforderlich ist, lang andauernden Verbindungen mit flüchtigen Datenquellen zu verwalten ist. Ressourcenverbrauch wird reduziert, da weniger Daten aktualisiert gesamte Verbrauch von Arbeitsspeicher und andere Ressourcen reduziert wird. Richtlinien für die inkrementelle Aktualisierung werden in definiert **Power BI Desktop**, angewendet, wenn in einem Arbeitsbereich in einer Premium-Kapazität veröffentlicht. 

![Details zur Aktualisierung](media/service-premium-incremental-refresh/refresh-details.png)

Weitere Informationen finden Sie unter [inkrementell zu aktualisieren, klicken Sie in Power BI Premium](service-premium-incremental-refresh.md).

## <a name="paginated-reports"></a>Paginierte Berichte

Paginierte Berichte, die auf P1-P3 und A4_A6-SKUs unterstützt basieren auf der Berichtsdefinitionssprache (Report Definition Language, RDL)-Technologie in SQL Server Reporting Services. Während auf RDL-Technologie basiert, ist es nicht identisch mit Power BI-Berichtsserver, die eine herunterladbare Berichtsplattform ist, die Sie lokal, auch mit Power BI Premium enthalten installieren können. Paginierte Berichte werden formatiert entsprechend auch auf einer Seite, die gedruckt bzw. gemeinsam genutzt werden können. Daten werden in einer Tabelle angezeigt, auch wenn die Tabelle über mehrere Seiten erstreckt. Mit der kostenlosen [ **Power BI-Berichts-Generator** ](https://go.microsoft.com/fwlink/?linkid=2086513) Windows-Desktop-Anwendung, Benutzer erstellen paginierter Berichte, und veröffentlichen Sie sie an den Dienst.

In Power BI Premium sind Paginated Reports eine arbeitsauslastung, die für eine Kapazität über das Administratorportal aktiviert werden muss. Kapazitätsadministratoren können aktivieren, und geben Sie dann die Größe des Speichers als Prozentsatz der Kapazität des insgesamt verfügbaren Speicherressourcen. Im Gegensatz zu anderen Arten von arbeitsauslastungen führt Premium paginierte Berichte in einem enthaltenen Bereich innerhalb der Kapazität. Der maximale Arbeitsspeicher, der für diesen Bereich verwendet wird, ob die Workload aktiv ist oder nicht angegeben ist. Der Standardwert ist 20 %. 

Weitere Informationen finden Sie unter [paginierte Berichte in Power BI Premium](paginated-reports-report-builder-power-bi.md). Weitere Informationen zum Aktivieren der Paginated Reports Workloads finden Sie unter [Konfigurieren von Workloads](service-admin-premium-workloads.md).

## <a name="power-bi-report-server"></a>Power BI-Berichtsserver
 
Mit Power BI Premium, Power BI-Berichtsserver umfasst einen *lokalen* Berichtsserver mit einer Web-Portal. Sie können Ihre BI-Umgebung lokal erstellen und verteilen Sie Berichte hinter der Firewall Ihrer Organisation. Berichtsserver bietet Benutzern Zugriff auf, um umfassende, interaktive und und Enterprise-Berichterstattungsfunktionen von SQL Server Reporting Services. Benutzer können visuelle Daten erkunden und schnell erkennen von Mustern, bessere, schnellere Entscheidungen zu treffen. Der Berichtsserver bietet Governance zu Ihren eigenen Bedingungen. Wenn die Zeit ist, erleichtert Power BI Report Server in die Cloud migrieren, wenn Ihre Organisation vollständig alle Power BI Premium-Funktionen nutzen kann.

Weitere Informationen finden Sie unter [Power BI-Berichtsserver](report-server/get-started.md).

## <a name="unlimited-content-sharing"></a>Unbegrenzte inhaltsfreigabe

Mit Premium können weiter, unabhängig davon, ob sie innerhalb oder außerhalb Ihrer Organisation anzeigen Ihrer Power BI-Inhalte, einschließlich paginierte und interaktive Berichte ohne einzelne Lizenzen erwerben. 

![Inhaltsfreigabe](media/service-premium-what-is/premium-sharing.png)

Premium ermöglicht weitreichende Verteilung von Inhalten von Pro-Benutzer, ohne dass Pro-Lizenzen für Empfänger, die den Inhalt anzuzeigen. Pro-Lizenzen sind für Inhaltsersteller erforderlich. Ersteller Verbinden mit Datenquellen, Modellieren von Daten, und erstellen Sie Berichte und Dashboards, die als Arbeitsbereich apps verpackt werden. 

Weitere Informationen finden Sie unter [Power BI-Lizenzierung](service-admin-licensing-organization.md).

## <a name="tool-connectivity-preview"></a>Tool-Verbindungen (Vorschau)

Hinter den Kulissen der bewährten Microsoft Enterprise **Analysis Services Vertipaq-Engine** eignet sich ideal für Power BI-Datasets. Analysis Services bietet Programmierbarkeit und die Clientanwendung und Tools unterstützen, durch die Client-Bibliotheken und APIs, die das Open-Standard-XMLA-Protokoll unterstützen. Power BI Premium-Datasets kann derzeit *schreibgeschützte* Vorgänge von Microsoft und Drittanbieter-Clientanwendungen und Tools über **XMLA-Endpunkte**. 

Microsoft-Tools wie SQL Server Management Studio und SQL Server Profiler und Drittanbieter-apps wie z. B. DAX-Studio, und datenvisualisierungsanwendungen, können Herstellen einer Verbindung mit und Abfragen von Premium-Datasets mithilfe von XMLA, DAX, MDX, DMVs und Ablaufverfolgungsereignisse. 

![SSMS](media/service-premium-what-is/connect-tools-ssms-dax.png)

Weitere Informationen finden Sie unter [Herstellen einer Verbindung mit Datasets mit Clientanwendungen und Tools](service-premium-connect-tools.md).

## <a name="acknowledgements"></a>Bestätigungen

Peter Myers, Data Platform MVP und unabhängige BI-Experte mit [bitweise Lösungen](https://www.bitwisesolutions.com.au/), und die Microsoft Power BI Customer Advisory Teams (CAT) sind wichtige Mitwirkende zu diesem Artikel.

## <a name="next-steps"></a>Nächste Schritte

> [!div class="nextstepaction"]
> [Verwalten von Premium-Kapazitäten](service-premium-capacity-manage.md)

Weitere Fragen? [Stellen Sie Ihre Frage in der Power BI-Community.](https://community.powerbi.com/)

||||||
