---
title: Bewährte Methoden für die Power BI-Leistung
description: Dieser Artikel enthält Informationen zum Erstellen schneller und zuverlässiger Berichte in Power BI.
author: MarkMcGeeAtAquent
ms.author: kfile
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 05/18/2018
LocalizationGroup: Reports
ms.openlocfilehash: f603a733c6c604a89b0b9608904acdf13b66b713
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2019
ms.locfileid: "61417635"
---
# <a name="power-bi-performance-best-practices"></a>Bewährte Methoden für die Power BI-Leistung

Dieser Artikel enthält Informationen zum Erstellen schneller und zuverlässiger Berichte in Power BI.  

## <a name="use-filters-to-limit-report-visuals-to-display-only-whats-needed"></a>Verwenden vom Filtern zum Einschränken von Berichtsvisuals auf die benötigten Informationen 

Je mehr Daten in einem Visual angezeigt werden müssen, umso länger dauert das Laden des Visuals. Auch wenn dieses Prinzip offensichtlich erscheint, gerät es leicht in Vergessenheit. Betrachten Sie beispielsweise ein großes Dataset. Darüber erstellen Sie einen Bericht mit einer Tabelle der Tabelle. Die Endbenutzer verwenden Datenschnitte auf der Seite, um die gewünschten Zeilen abzurufen – in der Regel sind sie nur an wenigen Dutzend Zeilen interessiert.

Ein häufiger Fehler besteht darin, dass die Standardansicht der Tabelle nicht gefiltert ist und alle Zeilen zeigt, in diesem Fall über 100 Millionen. Die Daten für diese Zeilen müssen in den Arbeitsspeicher geladen und bei jeder Aktualisierung dekomprimiert werden. Dies führt zu einer starken Auslastung des Arbeitsspeichers. Die Lösung: Verringern Sie die maximale Anzahl von Elementen, die in der Tabelle angezeigt werden, mit dem Filter „Top N“. Die maximale Anzahl von Elementen kann deutlich höher sein als die Menge, die die Benutzer benötigen, z.B. 10.000. Für den Endbenutzer ändert sich nichts, die Arbeitsspeicherauslastung durch den Bericht wird jedoch erheblich gesenkt und die Leistung entsprechend verbessert.

Ein ähnlicher Ansatz wird für alle Visuals in Ihren Berichten empfohlen. Fragen Sie sich, ob wirklich alle Daten in einem Visual benötigt werden. Gibt es Möglichkeiten, die Menge der angezeigten Daten im Visual durch Filter zu minimieren, ohne dass sich für den Endbenutzer viel ändert? Beachten Sie, dass insbesondere Tabellen ressourcenintensiv sein können.

## <a name="limit-visuals-on-report-pages"></a>Einschränken von Visuals auf Berichtsseiten

Das oben genannte Prinzip gilt genauso für die Anzahl von Visuals in einem bestimmten Bericht. Es wird dringend empfohlen, die Anzahl der Visuals in einem bestimmten Bericht auf die wirklich benötigten Elemente zu beschränken. Drillthroughseiten sind eine hervorragende Möglichkeit, um zusätzliche Informationen bereitzustellen, ohne dem Bericht weitere Visuals hinzuzufügen.  

## <a name="optimize-your-model"></a>Optimieren des Modells

Einige bewährte Methoden:

- Tabellen oder Spalten, die nicht verwendet werden, sollten nach Möglichkeit entfernt werden. 
- Vermeiden Sie Distinct Counts für Felder mit einer hohen Kardinalität – d.h. Millionen von unterschiedlichen Werten.  
- Führen Sie entsprechende Schritte aus, um Felder mit unnötig hoher Genauigkeit und hoher Kardinalität zu vermeiden. Sie können z.B. sehr eindeutige Datetime-Werte in separate Spalten wie Monat, Jahr, Datum usw. aufteilen. Wenn möglich können Sie auch durch Runden bei Feldern mit hoher Präzision die Kardinalität verringern (z.B. 13,29889 -> 13,3).
- Verwenden nach Möglichkeit anstelle von Zeichenfolgen ganze Zahlen.
- Gehen Sie vorsichtig bei DAX-Funktionen vor, die jede Zeile in einer Tabelle prüfen müssen, z.B. RANKX. Im schlimmsten Fall führen diese Funktionen dazu, dass die Laufzeit und Arbeitsspeicheranforderungen bei einer linearen Vergrößerung der Tabelle exponentiell steigen.
- Bei der Verknüpfung mit Datenquellen über DirectQuery sollten Sie Spalten indizieren, die häufig noch einmal gefiltert oder aufgeteilt werden. So wird die Reaktionsfähigkeit des Berichts deutlich verbessert.  

Weitere Informationen zum Optimieren von Datenquellen für DirectQuery finden Sie im Whitepaper [DirectQuery in SQL Server 2016 Analysis Services](https://blogs.msdn.microsoft.com/analysisservices/2017/04/06/directquery-in-sql-server-2016-analysis-services-whitepaper/) (in englischer Sprache).

## <a name="directquery-and-live-connection-understand-underlying-data-source-performance"></a>DirectQuery und Liveverbindung: Grundlagen zur Leistung der zugrunde liegenden Datenquelle

Wenn die Benutzer im Fall von DirectQuery oder einer Liveverbindung einen Power BI-Bericht öffnen, sendet Power BI in Echtzeit Abfragen an die zugrunde liegende Datenquelle. Wenn die Datenquelle die Abfragedaten zurückgibt, wird der Bericht gerendert. Die Leistung des Berichts hängt also in diesen Fällen zum größten Teil von der Leistung der zugrunde liegenden Datenquelle ab.

Daher müssen Sie die Leistung der zugrunde liegenden Datenquelle kennen. Die Abfrageleistung wird je nach Datenquelle mit unterschiedlichen Tools ermittelt. SQL Server und Azure SQL stellen z.B. den Abfragespeicher bereit, in dem ein Verlauf der Abfragen und ihrer Laufzeitstatistik erfasst wird.

Als Faustregel sollten Sie beim Bereitstellen von Power BI-Berichten, die basierend auf DirectQuery und Liveverbindungen erstellt werden, die gleichen Aktionen wie die Endbenutzer in Power BI Desktop ausführen. Wenn der Bericht nur sehr langsam in Power BI Desktop geladen wird, wird er mit hoher Wahrscheinlichkeit auch im Dienst für die Endbenutzer langsam geladen. 

## <a name="directquery-best-practices"></a>Bewährte Methoden für DirectQuery

Im folgenden Abschnitt werden allgemeine bewährte Methoden für die Herstellung einer Verbindung über DirectQuery beschrieben.
  
### <a name="db-design-guidance"></a>Leitfaden zum Datenbankentwurf

- Berechnete Spalten und Measures sollten möglichst in der Quelle gespeichert werden. Je geringer die Entfernung zur Datenquelle ist, desto höher ist die Wahrscheinlichkeit für eine gute Leistung.
- Optimieren! Vollziehen Sie die Ausführungspläne für Ihre Abfragen nach, fügen Sie Indizes für häufig gefilterte Spalten hinzu usw.

### <a name="modeling-guidance"></a>Leitfaden zur Modellierung

- Beginnen Sie in Power BI Desktop.
- Vermeiden Sie komplexe Abfragen im Abfrage-Editor.
- Verwenden Sie keine relative Datenfilterung im Abfrage-Editor.  
- Halten Sie Measures anfangs einfach, und steigern Sie die Komplexität inkrementell.
- Vermeiden Sie Beziehungen bei berechneten Spalten und Spalten mit eindeutigen Bezeichnern.
- Legen Sie versuchsweise „Referenzielle Integrität voraussetzen“ bei Beziehungen fest. In vielen Fällen kann hiermit die Abfrageleistung erheblich verbessert werden.  

### <a name="general"></a>Allgemein

- Wenden Sie zuerst Filter an.
- Überlegen Sie, ob Sie Interaktionen zwischen Visuals deaktivieren. So wird die Abfrageauslastung bei Kreuzhervorhebung durch die Benutzer reduziert.
- Schränken Sie die Anzahl der Visuals und die Daten für jedes Visual ein, wie oben beschrieben.
- Das Aktivieren der Sicherheit auf Zeilenebene kann zu erheblichen Änderungen bei der Leistung führen. Achten Sie darauf, verschiedene zeilenbasierte Sicherheitsrollen zu testen, die Ihre Benutzer verwenden werden.
- Der Dienst erzwingt Timeouts auf Abfrageebene, um sicherzustellen, dass lang andauernde Abfragen die Systemressourcen nicht exklusiv beanspruchen. Bei Abfragen, die länger als 225 Sekunden dauern, kommt es zu einem Timeout, und es wird ein Fehler auf Visualebene angezeigt.

## <a name="understand-dashboards-and-query-caches"></a>Grundlegendes zu Dashboards und Abfragecaches

An Dashboards angeheftete Visuals werden vom Abfragecache verarbeitet, wenn das Dashboard geladen wird. Im Gegensatz dazu werden Abfragen beim Öffnen eines Berichts dynamisch an die Datenquelle gesendet – an den Power BI-Dienst (beim Importieren) oder an die von Ihnen angegebene Datenquelle (bei DirectQuery oder Liveverbindung).  

> [!NOTE]
> Wenn Sie Liveberichtskacheln an ein Dashboard anheften, werden sie nicht aus dem Abfragecache verarbeitet – stattdessen verhalten sie sich ähnlich wie Berichte, und die Abfragen erfolgen dynamisch an Back-End-Kerne.

Wie der Name bereits vermuten lässt, bietet das Abrufen der Daten aus dem Abfragecache eine bessere und konsistentere Leistung als das Verwenden der Datenquelle. Eine Möglichkeit zum Nutzen dieser Funktionalität besteht darin, Dashboards als erste Landing Page für die Benutzer anzuzeigen. Heften Sie häufig verwendete und stark nachgefragte Visuals an die Dashboards an. Auf diese Weise werden Dashboards eine wertvolle „erste Abwehrlinie“ und bieten eine konsistente Leistung bei geringerer Beanspruchung der Kapazität. Die Benutzer können immer noch durch den Bericht klicken, um Details aufzurufen.  
 

Dieser Abfragecache wird bei DirectQuery und Liveverbindungen in regelmäßigen Abständen durch Abfragen der Datenquelle aktualisiert. Standardmäßig geschieht dies stündlich, der Zeitraum kann aber in den Dataseteinstellungen konfiguriert werden. Bei jeder Aktualisierung des Abfragecaches werden Abfragen an die zugrunde liegende Datenquelle gesendet, um den Cache zu aktualisieren. Die Anzahl der generierten Abfragen ist abhängig von der Anzahl der an Dashboards angehefteten Visuals, die diese Datenquelle benötigen. Beachten Sie, dass bei Aktivieren der Sicherheit auf Zeilenebene für jeden einzelnen Sicherheitskontext Abfragen generiert werden. Wenn es z.B. zwei Rollen für die Benutzer gibt, für die jeweils verschiedene Ansichten der Daten angezeigt werden, werden bei der Aktualisierung des Abfragecaches zwei Sätze von Abfragen generiert. 

## <a name="understand-custom-visual-performance"></a>Ermitteln der Leistung von benutzerdefinierten Visuals 

Achten Sie darauf, jedes benutzerdefinierte Visual zu analysieren, um eine hohe Leistung sicherzustellen. Schlecht optimierte benutzerdefinierte Visual können sich negativ auf die Leistung des gesamten Berichts auswirken. 

## <a name="deep-dive-into-query-performance-with-sql-profiler-and-power-bi-desktop"></a>Detaillierte Analyse der Abfrageleistung mit SQL Profiler und Power BI Desktop

Wenn Sie genauer ermitteln möchten, welche Visuals die meiste Zeit und Ressourcen in Anspruch nehmen, können Sie SQL Profiler mit Power BI Desktop verbinden und eine detaillierte Ansicht der Abfrageleistung abrufen.

> [!NOTE]
> Power BI Desktop unterstützt die Verbindung mit einem Diagnoseport. Der Diagnoseport erlaubt anderen Tools, eine Verbindung herzustellen und Überwachungen zu Diagnosezwecken durchzuführen. *Das Durchführen von Änderungen am Modell wird nicht unterstützt! Änderungen am Modell können zu Datenbeschädigung und Datenverlust führen.*

Anweisungen:
  
1. **Installieren von SQL Server Profiler und Ausführen von Power BI Desktop**

   SQL Server Profiler ist als Teil von SQL Server Management Studio verfügbar.

2. **Bestimmen des von Power BI Desktop verwendeten Ports**

   Führen Sie die Befehlszeile oder PowerShell mit Administratorrechten aus, und ermitteln Sie mit Netstat den Port, den Power BI Desktop für die Analyse verwendet:

   `> netstat -b -n`

   Bei der Ausgabe sollte es sich um eine Liste von Anwendungen und ihre geöffneten Ports handeln. Beispiel:  

   `TCP    [::1]:55786            [::1]:55830            ESTABLISHED`

   [msmdsrv.exe]

   Suchen Sie den von „msmdsrv.exe“ verwendeten Port, und notieren Sie die Nummer, da sie sie später benötigen. In diesem Fall verwenden Sie Port 55786.
3. **Verbinden von SQL Server Profiler mit Power BI Desktop**

   - Starten Sie SQL Server Profiler über das **Startmenü**.
   - Wählen Sie **Datei** > **Neue Ablaufverfolgung** aus.
   - Servertyp: Analysis Services
   - Servername: localhost:[oben ermittelte Portnummer]
   - Wählen Sie auf dem nächsten Bildschirm **Ausführen** aus.
   - SQL Profiler ist jetzt live und erstellt Profile für die von Power BI Desktop gesendeten Abfragen. 
   - Wenn Abfragen ausgeführt werden, können Sie die jeweilige Dauer und CPU-Zeiten verfolgen. Anhand dieser Informationen können Sie dann ermitteln, welche Abfragen zu Engpässen führen.  

Über SQL Profiler können Sie die Abfragen ermitteln, die die längste CPU-Zeit beanspruchen und daher wahrscheinlich zu Leistungsengpässen führen. Auf die Visuals, die diese Abfragen ausführen, sollten Sie dann den Schwerpunkt weiterer Optimierungen legen.

## <a name="gateway-best-practices"></a>Bewährte Methoden für Gateways

Das lokale Datengateway eignet sich hervorragend zum Herstellen einer Verbindung zwischen dem Power BI-Dienst und Ihren lokalen Daten. Bei schlechter Planung kann es aber auch zu einem Engpass bei der Berichtsleistung führen. Dies gilt vor allem für DirectQuery-/Liveverbindungsdatasets, bei denen alle Abfragen und Antworten auf Abfragen über das Gateway übermittelt werden. Im Folgenden finden Sie einige bewährte Methoden zum Sicherstellen einer hohen Leistung bei Gateways: 

- **Unternehmensmodus verwenden** und nicht den persönlichen Modus.
- **Empfohlene Hardware-Spezifikationen für das Gateway einhalten**: 8 CPU-Kerne, 16 GB RAM.
- **Überwachung einrichten**: Richten Sie die Leistungsüberwachung auf dem Gatewaycomputer ein, um zu sehen, ob das Gateway überlastet ist und zu einem Engpass wird. Weitere Informationen finden Sie unter [Problembehandlung beim lokalen Datengateway](service-gateway-onprem-tshoot.md).
- **Zentral hochskalieren oder horizontal hochskalieren**: Wenn das Gateway tatsächlich einen Engpass darstellt, sollten Sie eine zentrale Hochskalierung (d.h. das Platzieren des Gateways auf einem leistungsfähigeren Computer mit mehr CPU und RAM) oder eine horizontale Hochskalierung in Betracht ziehen (z.B. das Aufteilen von Datasets auf unterschiedliche Gateways). 
- **Import und DirectQuery trennen**: Beim horizontalen Hochskalieren sollten Sie die Gateways für den Import und die Gateways für DirectQuery voneinander trennen.

## <a name="network-latency"></a>Netzwerklatenz

Die Netzwerklatenz kann die Leistung eines Berichts beeinträchtigen, wenn es länger dauert, bis Anforderungen den Power BI-Dienst erreichen und Antworten übermittelt werden. Mandanten in Power BI werden einer bestimmten Region zugewiesen. Sie können die „Heimatregion“ Ihres Mandanten ermitteln, indem Sie zu „powerbi.com“ navigieren, in der oberen rechten Ecke ?** und dann **Info** auswählen. Wenn Benutzer von einem Mandanten aus auf den Power BI-Dienst zugreifen, werden ihre Anforderungen immer an diese Region weitergeleitet. Wenn die Anforderungen den Power BI-Dienst erreichen, kann der Dienst dann zusätzliche Anforderungen – z.B. an die zugrunde liegende Datenquelle oder das Gateway – senden, die ebenfalls der Netzwerklatenz unterliegen.

Tools wie [Azure Speed Test](http://azurespeedtest.azurewebsites.net/) bieten einen Überblick über die Netzwerklatenz zwischen dem Client und der Azure-Region. Im Allgemeinen sollten sich, um die Auswirkungen der Netzwerklatenz zu minimieren, Datenquellen, Gateways und der Power BI-Cluster in möglichst großer Nähe zueinander befinden. Wenn die Netzwerklatenz ein Problem darstellt, können Sie versuchen, Gateways und Datenquellen näher am Power BI-Cluster anzuordnen, indem Sie sie auf virtuellen Computern platzieren.

Um die Netzwerklatenz noch weiter zu verbessern, können Sie [Azure ExpressRoute](https://azure.microsoft.com/services/expressroute/) verwenden. Hiermit können schnellere und zuverlässigere Netzwerkverbindungen zwischen den Clients und Azure-Rechenzentren hergestellt werden.

## <a name="next-steps"></a>Nächste Schritte

- [Planen einer Power BI Enterprise-Bereitstellung](https://aka.ms/pbienterprisedeploy) mit umfassenden Informationen zu großen Power BI-Bereitstellungen
- [DirectQuery in SQL Server 2016 Analysis Services](https://blogs.msdn.microsoft.com/analysisservices/2017/04/06/directquery-in-sql-server-2016-analysis-services-whitepaper/)
- [[YouTube] Erstellen von schnellen und zuverlässigen Berichten in Power BI](https://www.youtube.com/watch?v=GhiJABR7XX0) (in englischer Sprache)
- [[YouTube] Power BI Enterprise-Bereitstellungen](https://www.youtube.com/watch?v=K-zEWICvICM) (in englischer Sprache)