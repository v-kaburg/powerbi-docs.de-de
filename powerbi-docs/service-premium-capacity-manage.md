---
title: Microsoft Power BI Premium-Kapazitäten verwalten
description: Beschreibt, Verwaltungsaufgaben für Power BI Premium-Kapazitäten.
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 04/10/2019
ms.custom: seodec18
LocalizationGroup: Premium
ms.openlocfilehash: e4bb907e12d3c0b07408f069d9b238599756e8e0
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2019
ms.locfileid: "65565243"
---
# <a name="managing-premium-capacities"></a>Verwalten von Premium-Kapazitäten

Verwalten von Power BI Premium umfasst, erstellen, verwalten und Überwachen von Premium-Kapazitäten.

## <a name="creating-and-managing-capacities"></a>Erstellen und Verwalten von Kapazitäten

Die **Kapazitätseinstellungen** im Power BI-Verwaltungsportal auf der Seite zeigt die Anzahl der virtuellen Kerne erworben und Premium-Kapazitäten zur Verfügung. Die Seite ermöglicht globale Office 365-Administratoren oder Power BI-Dienstadministratoren zu Premium-Kapazitäten verfügbaren V-Kerne erstellen oder vorhandene Premium-Kapazitäten zu ändern.

Wenn Sie eine Premium-Kapazität zu erstellen, müssen Administratoren definieren:

- Kapazitätsname (eindeutig innerhalb des Mandanten).
- Kapazität Admin(s).
- Größe der Kapazität.
- Region für den Speicherort von Daten.

Es muss mindestens ein Kapazitätsadministrator zugewiesen werden. Sie können Benutzer, die als Kapazitätsadministratoren zugewiesen:

- Arbeitsbereiche für die Kapazität zuweisen.
- Verwalten von Benutzerberechtigungen, um zusätzliche Kapazitätsadministratoren oder Benutzer mit Zuweisungsberechtigungen (zur Aktivierung der sie die Kapazität Arbeitsbereiche zuweisen) hinzuzufügen.
- Verwalten von Workloads, um die maximale speicherauslastung für paginierte Berichte und Datenflüsse Workloads konfigurieren.
- Starten Sie die Kapazität, um alle Vorgänge aufgrund einer System-Überladung zurückzusetzen neu.

Kapazitätsadministratoren können nicht Arbeitsbereich Inhalte zugreifen, es sei denn, Sie explizit in den arbeitsbereichsberechtigungen zugewiesen. Sie auch haben keinen Zugriff auf alle Power BI-administrationsbereiche (sofern nicht explizit zugewiesen ist) wie z. B. nutzungsmetriken, Überwachungsprotokolle oder mandanteneinstellungen. Vor allem Kapazitätsadministratoren keine Berechtigungen, um neue Kapazitäten zu erstellen oder vorhandene Kapazitäten skalieren. Administratoren werden pro pro-Kapazität zugewiesen, die sicherstellen, dass sie können nur anzeigen und Verwalten von Kapazitäten, die sie zugewiesen sind.

Größe der Kapazität ist aus der verfügbaren Liste mit SKU-Optionen ausgewählt, die durch die Anzahl der verfügbaren V-Kerne im Pool beschränkt ist. Es ist möglich, mehrere Kapazitäten aus dem Pool zu erstellen, die von einem erstellt werden konnte, oder mehrere SKUs erworben. Beispielsweise eine P3-SKU (32 V-Kerne) verwendet werden, um drei Kapazitäten zu erstellen: eine P2 (16 virtuelle Kerne), und zwei P1 (2 x 8 virtuelle Kerne). Verbesserte Leistung und Skalierbarkeit erzielt werden, indem kleinere Größe Kapazitäten erstellen unter der [Optimieren von Premium-Kapazitäten](service-premium-capacity-optimize.md) Artikel. Die folgende Abbildung zeigt ein Beispiel-Setup für die fiktive Contoso-Organisation bestehend aus fünf Premium-Kapazitäten (3 x P1 "und" 2 x P3) mit einzelnen enthaltenden app-Arbeitsbereiche und mehrere Arbeitsbereiche in gemeinsam genutzten Kapazität.

![Ein Beispiel-Setup für die fiktive Contoso-Organisation](media/service-premium-capacity-manage/contoso-organization-example.png)

Eine Premium-Kapazität kann zu einer anderen Region als der Startbereich des Power BI-Mandanten, Multi-Geo Capabilities genannt zugewiesen werden. Multi-Geo Capabilities bietet die administrativen Kontrolle über die Rechenzentren in definierten geografischen Regionen, die Power BI-Inhalte befindet. Der Grund für eine Multi-Geo Capabilities-Bereitstellung ist in der Regel für Unternehmen oder Government-Compliance, anstatt der Leistung und Skalierung. Bericht und das Dashboard laden umfasst weiterhin Anforderungen an den Startbereich für Metadaten an. Weitere Informationen finden Sie unter [Multi-Geo-Unterstützung für Power BI Premium](service-admin-premium-multi-geo.md).

Power BI-Dienstadministratoren und globale Office 365-Administratoren können Premium-Kapazitäten ändern. Genauer gesagt können sie:

- Ändern Sie den kapazitätsumfang hochskalieren oder Herunterskalieren von Ressourcen.
- Hinzufügen oder Entfernen von Kapazitätsadministratoren.
- Fügen Sie hinzu oder entfernen Sie Benutzer mit zuweisungsberechtigung.
- Hinzufügen oder Entfernen von zusätzlichen Workloads.
- Ändern von Regionen.

Berechtigung zur kapazitätszuweisung sind erforderlich, eine bestimmte Premium-Kapazität einen Arbeitsbereich zuweisen. Die gesamte Organisation, bestimmte Benutzer oder Gruppen können die Berechtigungen gewährt werden.

Standardmäßig unterstützen Premium-Kapazitäten für Workloads, die mit der Ausführung von Abfragen mit Power BI. Premium-Kapazitäten unterstützen auch zusätzlicher Workloads: **Künstliche Intelligenz (Cognitive Services)** , **paginierte Berichte**, und **Datenflüsse**. Jede arbeitsauslastung erforderlich ist, konfigurieren den maximalen Arbeitsspeicher (als Prozentsatz des gesamten verfügbaren Arbeitsspeichers), der von der arbeitsauslastung verwendet werden kann. Es ist wichtig zu verstehen, dass die maximale speicherbelegung erhöhen die Anzahl der aktiven Modelle, die gehostet werden können und den Durchsatz von Aktualisierungen auswirken kann. 

Arbeitsspeicher wird dynamisch zugewiesen, um Datenflüsse, aber Sie paginierte Berichte statisch zugeordnet. Der Grund für die Zuweisung von statisch der maximale Arbeitsspeicher ist, dass paginierte Berichte in einem gesicherten enthaltenen Raum für die Kapazität ausgeführt. Wenn die Einstellung paginierten Berichte Speicher, da hierdurch von verfügbarem Speicher für das Laden von Modellen, sollte vorsichtig vorgenommen werden. Weitere Informationen finden Sie unter den [Arbeitsspeicher Standardeinstellungen](service-admin-premium-workloads.md#default-memory-settings).

Löschen einer Premium-Kapazität ist möglich und wird nicht zum Löschen der Arbeitsbereiche und Inhalt führen. Stattdessen werden alle zugewiesenen Arbeitsbereiche auf gemeinsam genutzte Kapazität verschoben. Bei der Premium-Kapazität in einer anderen Region erstellt wurde, wird der Arbeitsbereich in gemeinsam genutzte Kapazität der home-Region verschoben.

### <a name="assigning-workspaces-to-capacities"></a>Kapazität Arbeitsbereiche zuweisen

Können Arbeitsbereiche einer Premium-Kapazität im Power BI-Verwaltungsportal oder bei einem app-Arbeitsbereich zugewiesen werden, der **Arbeitsbereich** Bereich.

Kapazitätsadministratoren, sowie globale Office 365-Administratoren oder Power BI-Dienstadministratoren können Arbeitsbereiche im Power BI-Verwaltungsportal zuweisen massenimportieren. BULK zugewiesen, kann auf anwenden:

- **Arbeitsbereiche nach Benutzern** -alle Arbeitsbereiche, die im Besitz dieser Benutzer ab, einschließlich der persönlichen Arbeitsbereiche, die Premium-Kapazität zugewiesen sind. Dazu gehören die neuzuweisung von Arbeitsbereichen, wenn sie bereits einer anderen Premium-Kapazität zugewiesen werden. Darüber hinaus werden die Benutzer auch Berechtigungen für arbeitsbereichszuweisungen erteilt zugewiesen.

- **Bestimmte Arbeitsbereiche**
- **Arbeitsbereiche der gesamten Organisation** -alle Arbeitsbereiche, einschließlich der persönlichen Arbeitsbereiche, die Premium-Kapazität zugewiesen sind. Alle aktuellen und zukünftigen Benutzer werden Berechtigungen für arbeitsbereichszuweisungen erteilt zugewiesen. Dieser Ansatz wird nicht empfohlen. Es wird ein gezielterer Ansatz bevorzugt.

Kann ein Arbeitsbereich einer Premium-Kapazität hinzugefügt werden, mithilfe der **Arbeitsbereich** Bereich, sodass der Benutzer ist sowohl ein arbeitsbereichsadministrator und Zuweisungsberechtigungen hat.

![Verwenden im Arbeitsbereich einer Premium-Kapazität einen Arbeitsbereich zuweisen](media/service-premium-capacity-manage/assign-workspace-capacity.png)

Arbeitsbereichsadministratoren können einen Arbeitsbereich zu einer Kapazität (für gemeinsam genutzte Kapazität) entfernen, ohne erforderliche Zuweisung-Berechtigung. Entfernen von Arbeitsbereichen aus dedizierten Kapazitäten effektiv verschiebt den Arbeitsbereich auf gemeinsam genutzte Kapazität. Beachten Sie, dass einen Arbeitsbereich aus einer Premium-Kapazität entfernen negative Folgen, dies führt z. B. freigegebene Inhalte, die nicht verfügbar für Power BI Free kann lizenzierte Benutzer oder die Unterbrechung der geplanten Aktualisierung, wenn sie die zulässige Anzahl unterstützt überschreiten von gemeinsam genutzten Kapazitäten.

Im Power BI-Dienst wird ein Arbeitsbereich einer Premium-Kapazität zugewiesen ganz einfach durch das Rautensymbol identifiziert, der den Namen des Arbeitsbereichs erweitert.

![Der Identifizierung eines Arbeitsbereichs zu einer Premium-Kapazität zugewiesen](media/service-premium-capacity-manage/premium-diamond-icon.png)

## <a name="monitoring-capacities"></a>Überwachen von Kapazitäten

Überwachen von Premium-Kapazitäten bietet Administratoren einen Überblick über die Leistung von Kapazitäten. Kapazitäten können überwacht werden, mithilfe der Power BI-Verwaltungsportal oder die **Kapazitätsmetriken für Power BI Premium** -app (Power BI).

### <a name="power-bi-admin-portal"></a>Power BI-Verwaltungsportal

Im Admin-Portal für jede Kapazität der **Integrität** Registerkarte enthält eine Zusammenfassung der Metriken für die Kapazität und die Workloads der einzelnen aktiviert. Metriken zeigen die durchschnittlich in den letzten sieben Tagen.  

Metriken bauen auf der Ebene der Capacity aller aktivierten Workloads ist. die folgenden Metriken stehen zur Verfügung:

- **CPU-Auslastung** -durchschnittliche CPU-Auslastung als Prozentsatz der verfügbaren CPU-Gesamtzeit für die Kapazität enthält.  
- **SPEICHERAUSLASTUNG** – stellt die durchschnittliche arbeitsspeicherauslastung (in GB) als Summe des verfügbaren Arbeitsspeichers für die Kapazität. 

Für jede aktivierte arbeitsauslastung CPU-Auslastung und speicherauslastung, sowie eine Reihe von bestimmten workloadmetriken dienen. Z. B. für die arbeitsauslastung Datenfluss **Gesamtanzahl** zeigt insgesamt Aktualisierungen für jeden Datenfluss und **Durchschnittsdauer** zeigt die durchschnittliche Dauer der datenaktualisierung für den Datenfluss.

![Registerkarte "Capacity Integrität" im portal](media/service-premium-capacity-manage/admin-portal-health-dataflows.png)

Weitere Informationen zu allen verfügbaren Metriken für jede Workload, finden Sie unter [Kapazitäten im Verwaltungsportal Überwachen](service-admin-premium-monitor-portal.md).

Die Überwachungsfunktionen in der Power BI-Verwaltungsportal sind soll eine kurze Zusammenfassung der wichtigsten kapazitätsmetriken bereitstellen. Detaillierte Überwachung, es wird empfohlen, die **Kapazitätsmetriken für Power BI Premium** app.

### <a name="power-bi-premium-capacity-metrics-app"></a>Power BI Premium Kapazitätsmetriken-app

Die [Kapazitätsmetriken für Power BI Premium-app](https://appsource.microsoft.com/product/power-bi/pbi_pcmm.pbi-premiumcapacitymonitoring?tab=Overview) eine Power BI-app für kapazitätsadministratoren verfügbar ist und wie jede andere Power BI-app installiert ist. Sie enthält ein Dashboard und einen Bericht.

![Power BI Premium Kapazitätsmetriken-app](media/service-premium-capacity-manage/capacity-metrics-app.png)

Wenn die app geöffnet wird, wird das Dashboard geladen, um zahlreiche Kacheln Ausdrücken eine Aggregierte Ansicht über all Ihre Kapazitäten, von denen der Benutzer einen Kapazitätsadministrator. ist, vorhanden Das Dashboardlayout umfasst fünf Hauptbereiche gegliedert:

- **Übersicht über die** -App-Version, die Anzahl von Kapazitäten und Arbeitsbereiche
- **Systemübersicht** -Arbeitsspeicher und CPU-Metriken
- **Zusammenfassung des Datasets** : Gibt die Anzahl von Datasets, DQ/LC, Aktualisierung und abfragemetriken
- **Zusammenfassung der Datenfluss** : Gibt die Anzahl der Datenflüsse und Dataset-Metriken
- **Berichtszusammenfassung paginierten** – aktualisieren und Anzeigen von Metriken

Der zugrunde liegenden Bericht, der von dem die dashboardkacheln angeheftet wurden, kann durch Klicken auf eine beliebige dashboardkachel zugegriffen werden. Es enthält eine ausführlichere Ansicht der einzelnen Abschnitte Dashboard und interaktive Filterung unterstützt. 

Filterung kann durch Festlegen der Slicer nach Datumsbereich "," Kapazität "," Arbeitsbereich "und" Workload (Bericht, Dataset Datenfluss) erreicht werden, und durch Auswahl der Elemente im Bericht Visuals überschreiten Filtern der Berichtsseite. Kreuzfilterung ist eine leistungsstarke Technik zum eingrenzen, um bestimmte Zeiträume, Kapazitäten, Arbeitsbereiche, Datasets usw., und es kann sehr hilfreich sein, beim Durchführen der Analyse der Grundursache.

Ausführliche Informationen zu Metriken von Dashboard und einen Bericht in der app, finden Sie unter [Monitor Premium-Kapazitäten, mit der app](service-admin-premium-monitor-capacity.md).

### <a name="interpreting-metrics"></a>Interpretieren von Metriken

Metriken sollten überwacht werden, um einen Überblick über Baseline-Nutzung und Workload-ressourcenaktivität herzustellen. Wenn die Kapazität langsam ist, es ist wichtig zu verstehen, welche Metriken überwacht werden, und die Schlussfolgerungen, die Sie vornehmen können.

Im Idealfall sollten Abfragen führen Sie innerhalb einer Sekunde reaktionsfähige Benutzeroberflächen für die benutzerberichterstattung bereitzustellen und höhere abfragedurchsatz zu aktivieren. Es ist in der Regel weniger von Belang, wenn Hintergrundprozesse – einschließlich Aktualisierungen - längere Zeiträume abgeschlossen werden.

Im Allgemeinen können langsam Berichte ein Anzeichen für eine Überhitzung Kapazität sein. Wenn Berichte nicht geladen werden, ist dies ein Hinweis auf eine übermäßige auseinandersetzungen Kapazität. In beiden Situationen kann die Hauptursache auf vielen Faktoren ab, einschließlich zurückzuführen sein:

- **Abfragen mit Fehlern** sicherlich angeben arbeitsspeicherauslastung und, die ein Modell konnte nicht in den Arbeitsspeicher geladen werden. Power BI-Dienst versucht, die Laden eines Modells für 30 Sekunden, bevor ein Fehler auftritt.

- **Eine übermäßige Abfrage Wartezeiten** kann verschiedene Ursachen sein:
  - Die Notwendigkeit von Power BI-Dienst zum ersten Modelle entfernen, und Laden Sie das Modell bei-werden abgefragt (Beachten Sie, dass entfernungsraten mit höhere Dataset nur einen Überblick über die Kapazität Belastung nicht sind, es sei denn, begleitet durch lange Wartezeiten der Abfrage, die angeben, arbeitsspeicherüberlastung).
  - Laden des Modells Zeiten (vor allem die Wartezeit ein großen Modells in den Arbeitsspeicher zu laden).
  - Lang ausgeführte Abfragen.
  - Zu viele LC\DQ-Verbindungen (überschreiten von Grenzwerten für die Kapazität).
  - Die CPU-Auslastung.
  - Komplexer Bericht ist mit einer übermäßigen Anzahl von visuellen Elementen auf einer Seite (Beachten Sie, dass jedes visuelle Element um eine Abfrage handelt).

- **Lange Abfragen dauern** kann bedeuten, dass das Modell Entwürfe nicht optimiert sind, insbesondere, wenn mehrere Datasets in einer Kapazität aktiv sind, und nur ein Dataset lange abfragedauern erzeugt,. Dies deutet darauf hin, dass die Kapazität ausreichend Ressourcen zugewiesen ist und das Dataset in Frage suboptimale oder nur langsam ist. Abfragen mit langer kann problematisch sein, wie sie den Zugriff auf Ressourcen, die erforderlich sind, durch andere Prozesse blockieren können.
- **Aktualisieren Sie lange Wartezeiten** ein Hinweis auf nicht genügend Arbeitsspeicher aufgrund von vielen active Modelle Arbeitsspeicher belegen oder, dass eine Aktualisierung der problematische andere blockiert werden aktualisiert (größer als parallele Aktualisierung Grenzwerte).

Eine ausführlichere Erläuterung zur Verwendung der Metriken finden Sie in der [Optimieren von Premium-Kapazitäten](service-premium-capacity-optimize.md) Artikel.

## <a name="acknowledgements"></a>Bestätigungen

Dieser Artikel geschrieben wurde, indem Peter Myers, Data Platform MVP und unabhängige BI-Experte mit [bitweise Lösungen](https://www.bitwisesolutions.com.au/).

## <a name="next-steps"></a>Nächste Schritte

> [!div class="nextstepaction"]
> [Optimieren der Premium-Kapazitäten](service-premium-capacity-optimize.md)   
> [!div class="nextstepaction"]
> [Konfigurieren von Workloads in einer Premium-Kapazität](service-admin-premium-workloads.md)   

Weitere Fragen? [Stellen Sie Ihre Frage in der Power BI-Community.](https://community.powerbi.com/)

||||||
