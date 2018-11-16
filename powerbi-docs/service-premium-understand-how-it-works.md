---
title: Nutzung und Optimierung des Power BI Premium-Kapazitätsspeichers
description: Lernen Sie Verwaltung und Optimierung des Power BI Premium-Kapazitätsspeichers kennen.
ms.date: 10/18/2018
ms.topic: conceptual
ms.service: powerbi
ms.component: powerbi-admin
ms.author: mblythe
ms.reviewer: mblythe
author: mgblythe
manager: kfile
ms.openlocfilehash: 534c06c66d561a04dbffc04412095d6924c92781
ms.sourcegitcommit: b23fdcc0ceff5acd2e4d52b15b310068236cf8c7
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2018
ms.locfileid: "51266068"
---
# <a name="microsoft-power-bi-premium-capacity-resource-management-and-optimization"></a>Verwaltung und Optimierung der Microsoft Power BI Premium-Kapazitätsressource

In diesem Artikel wird beschrieben, wie Power BI Premium Ressourcen verwaltet. Außerdem sind Beispiele und Vorschläge zur Problembehandlung enthalten. Eine Übersicht finden Sie unter [Was ist Power BI Premium?](service-premium.md).

## <a name="premium-capacity-memory-management"></a>Verwaltung des Premium-Kapazitätsspeichers

 Premium-Kapazitätsspeicher wird verbraucht durch:

* Die Datasets, die in den Arbeitsspeicher geladen sind
* Die Datasetaktualisierung (geplant und bedarfsgesteuert)
* Von der Kapazität unterstützte Workloads
* Berichtsabfragen

Wenn eine Anforderung an ein veröffentlichtes Dataset in Ihrer Kapazität ausgegeben wird, wird das Dataset aus dem permanenten Speicher in den Arbeitsspeicher geladen (dies wird auch als Ladevorgang bezeichnet). Wenn das Dataset im Arbeitsspeicher geladen bleibt, erleichtert dies die schnelle Reaktion auf zukünftige Abfragen dieses Datasets. Abgesehen von dem Speicherplatz, der benötigt wird, um das Dataset im Arbeitsspeicher geladen zu halten, verbrauchen Berichtsabfragen und Datasetaktualisierungen zusätzlichen Arbeitsspeicher.

### <a name="dataset-memory-estimation"></a>Schätzung des Datasetarbeitsspeichers

Beim Versuch, ein Dataset in den Arbeitsspeicher zu laden, schätzt Power BI ein, wieviel Arbeitsspeicher dieses Dataset benötigt, um den angeforderten Befehl auszuführen. Im Arbeitsspeicher sind Datasets tendenziell umfangreicher, als wenn sie auf dem Datenträger gespeichert werden. Während der Aktualisierung eines Datasets erfordert Power BI mindestens doppelt so viel Arbeitsspeicher als während des Leerlaufs des Datasets.

### <a name="overcommitting-capacity-eviction-and-reloading-of-datasets"></a>Überlastung der Kapazität, Entfernung und erneutes Laden von Datasets

Power BI Premium bietet Ihnen den Vorteil, dass Sie Ihre Kapazität *überlasten* können. Beispielsweise können Sie mehr Datasets veröffentlichen, als Ihre Kapazität aufnehmen kann. Wenn die veröffentlichten Datasets mehr Arbeitsspeicher benötigen als in der Kapazität verfügbar ist, werden einige Datasets separat im permanenten Speicher gespeichert. Der permanente Speicher ist Teil des Speichers von 100 TB, der all Ihren Kapazitäten zugeordnet ist.

Welche Datasets werden also im Arbeitsspeicher beibehalten, und was geschieht mit den anderen Datasets? Wie bereits beschrieben, wird ein Dataset in den Arbeitsspeicher geladen (Imageladevorgang), wenn eine Anforderung daran gerichtet wird. Die Anforderung könnte eine Berichtsabfrage oder ein Aktualisierungsvorgang sein. Da Sie Ihre Kapazität jedoch überlasten können, kann in der Kapazität auch eine Speicherauslastung auftreten. Wenn eine Kapazität Arbeitsspeicherauslastung unterliegt, *entfernt* der Knoten mindestens ein Dataset aus dem Arbeitsspeicher. Datasets, die inaktiv sind (ohne derzeit ausgeführten Abfrage- oder Aktualisierungsvorgang), werden zuerst entfernt. Anschließend orientiert sich die Entfernungsreihenfolge an den „am seltensten verwendeten“ Datasets. Wenn neue Befehle an das entfernte Dataset gerichtet werden, versucht der Dienst, dieses erneut in den Speicher zu laden, wobei möglicherweise andere Datasets entfernt werden. Dieses Verhalten ermöglicht eine effizientere Nutzung, indem die Kapazität mehr Datasets bedienen als ihr Speicher aufnehmen kann.

Das Laden eines Datasets in den Arbeitsspeicher ist ein relativ kostspieliger Vorgang. Je nach Größe des Datasets kann es von wenigen Sekunden für kleine Datasets bis zu Vielfachen von zehn Sekunden oder sogar Minuten für große Datasets wie Datasets mit einer Größe von etwa 10 GB dauern. Premium-Kapazität versucht, die erforderliche Anzahl der Ladungen der Kapazität zu reduzieren, indem die selten verwendeten Datasets solange wie möglich im Arbeitsspeicher gehalten werden. Wenn zusätzlicher Speicher benötigt wird, müssen einige Datasets entfernt werden, und das System versucht, dasjenige auszuwählen, das sich am geringsten auf die Benutzerfreundlichkeit auswirkt. Wenn zusätzlicher Speicher benötigt wird, müssen einige Datasets entfernt werden, und das System versucht, dasjenige auszuwählen, das sich am geringsten auf die Benutzerfreundlichkeit auswirkt. Beispielsweise vermeidet das System, Datasets zu entfernen, die in den letzten Minuten aktiv verwendet wurden. Es ist wahrscheinlich, dass diese Datasets bald wieder abgefragt werden.

Die Entfernung selbst ist ein schneller Vorgang. Wenn das Dataset zum Zeitpunkt der Entfernung nicht aktiv verwendet wird, wird der Benutzer die Entfernung kaum wahrnehmen. Wenn jedoch zu viele Datasets gleichzeitig aktiv verwendet werden, und der Arbeitsspeicher nicht ausreicht, um alle aufzunehmen, können viele Entfernungen auftreten. Zu viele aktive Datasets können zu einer Überlastungssituation führen, bei der Datasets ständig entfernt und neu geladen werden. Außerdem wären Benutzer dann erheblichen verlängerten Antwortzeiten und Leistungsabfällen ausgesetzt.

### <a name="dataset-refresh-memory-requirement-competing-with-an-active-dataset-memory-requirement"></a>Arbeitsspeicherbedarf einer Datasetaktualisierung in Konkurrenz zum Arbeitsspeicherbedarf eines aktiven Datasets

Datasets können nach einem Zeitplan oder bei Bedarf durch Benutzer aktualisiert werden. Wie bereits beschrieben, erfordern vollständige Aktualisierungen mindestens das Doppelte an Speichergröße der geladenen und im Leerlauf befindlichen Datasets. Vor Beginn der Aktualisierung wird der Arbeitsspeicherbedarf für die Aktualisierung geschätzt. Wenn der gesamte Arbeitsspeicherbedarf den in der Kapazität verfügbaren Speicher überschreitet, werden einige Datasets entfernt. Auch in diesem Szenario basiert die Entfernungsreihenfolge auf den am seltensten verwendeten Datasets.

Wenn der erforderliche Arbeitsspeicher trotz Entfernung nicht verfügbar ist, wird die Aktualisierung zur Wiederholung in die Warteschlange gestellt. Der Dienst unternimmt bis zum erfolgreichen Abschluss oder zum Beginn einer neuen Aktualisierung neue Versuche.

Wenn eine interaktive Abfrage an ein Dataset in der Kapazität gerichtet wird und aufgrund einer laufenden Aktualisierung nicht genügend Arbeitsspeicher verfügbar ist, gilt diese Anforderung als nicht erfolgreich und muss vom Benutzer wiederholt werden.

### <a name="workloads"></a>Arbeitsauslastungen

Standardmäßig unterstützen **Power BI Premium**- und **Power BI Embedded**-Kapazitäten nur die Workload, die mit der Ausführung von Power BI-Abfragen in der Cloud verbunden ist. Nun werden zwei weitere Workloads in der Vorschau unterstützt: **Paginierte Berichte** und **Dataflows**. Wenn diese aktiviert sind, können sie die Speicherauslastung in Ihrer Kapazität beeinträchtigen. Weitere Informationen finden Sie unter [Konfigurieren von Workloads](service-admin-premium-manage.md#configure-workloads).

## <a name="cpu-resource-management-in-premium-capacity"></a>CPU-Ressourcenverwaltung in Premium-Kapazität

Es gibt zwei primäre Nutzer von CPU-Ressourcen:

* Abfragen von Berichten
* Aktualisierung (Verarbeitung)

### <a name="queries-from-reports"></a>Abfragen von Berichten

Berichtsabfragen nutzen CPU-Ressourcen in Ihrer Kapazität. Berichte mit ineffizienten Abfragen oder vielen gleichzeitigen Benutzern können viele CPU-Ressourcen beanspruchen. Ihre vorhandene Kapazität ist möglicherweise nicht ausreichend, um die Last zu bewältigen.

### <a name="refresh-parallelization-policy"></a>Richtlinie zum Aktualisieren der Parallelisierung

Der Speicher ist nicht die einzige Ressource, die die Datasetaktualisierung einschränken kann. Die Anzahl der virtuellen Kerne eines Servers kann auch ein Faktor sein. Da jeder Aktualisierungsvorgang eine bestimmte Anzahl virtueller Kerne erfordert, besteht eine Grenze für die Anzahl paralleler Aktualisierungen. Die folgende Tabelle informiert Sie ausführlich über den Grenzwert pro SKU. Weitere Aktualisierungen, die diese Grenzwerte überschreiten, werden in die Warteschlange eingereiht.

 | SKU | Back-End-V-Kerne | Aktualisierungsparallelität nach Modell |
 | --- | --- | --- |
 | A1  | 0,5  | 1  |
 | A2  | 1  | 2  |
 | A3  | 2  | 3  |
 | A4  | 4  | 6  |
 | A5  | 8  | 12  |
 | A6  | 16  | 24  |
 | EM1  | 0,5  | 1  |
 | EM2  | 1  | 2  |
 | EM3  | 2  | 3  |
 | P1  | 4  | 6  |
 | P2  | 8  | 12  |
 | P3  | 16  | 24  |
 | P4  | 32  | 48  |
 | P5  | 64  | 96  |

 > [!TIP]
> Wenn Ihre Aktualisierungen verzögert werden, überprüfen Sie die Anzahl paralleler Aktualisierungen, die Ihre Kapazität unterstützt.

## <a name="example-scenarios"></a>Beispielszenarien

Im Folgenden werden einige häufig auftretende Szenarios und die vom Dienst ausgeführten Aktionen beschrieben:

**Zwanzig geplante Aktualisierungen werden zur gleichen Zeit übermittelt**. Power BI versucht, die ersten *x* Aktualisierungen zur gleichen Zeit zu starten. Der Wert für *x* richtet sich nach der Richtlinie zum Aktualisieren der Parallelisierung für diese SKU. Wenn Power BI durch Entfernen inaktiver Datasets (nicht vor kurzem verwendeter Datasets) nicht genügend Arbeitsspeicher abrufen kann, werden nicht alle *x* Aktualisierungen zur selben Zeit gestartet. Jede Aktualisierung, die nicht gestartet werden kann, wird bis sie gestartet werden kann, in die Warteschlange eingereiht.

**Zwei Aktualisierungen werden zur gleichen Zeit ausgeführt, und es steht nur genügend Speicher zur Verfügung, um eine fertig zu stellen**. Die, die fertig gestellt werden kann, wird gestartet. Die andere wird später erneut versucht.

**Eine große Anzahl von Datasets wird abgefragt, und zur gleichen Zeit werden mehrere Datasets aktualisiert**. Wenn nicht ausreichend Arbeitsspeicher verfügbar ist, versucht Power BI alle aktiven Aktualisierungen zu beenden, um interaktiven Abfragen Vorrang zu gewähren. Dies führt zu Leistungseinbußen bei der Aktualisierung.

**Ein Dataset erfordert zu viel Arbeitsspeicher, um bei der aktuellen Kapazitätsgröße aktualisiert werden zu können**. Die Aktualisierung schlägt fehl. Es werden keine Versuche unternommen, mehr Arbeitsspeicher durch Entfernung abzurufen.

**Eine Aktualisierung eines einzelnen Datasets löst eine große Spitze im Arbeitsspeicher aus**. Wenn die Auslastungsspitze den Arbeitsspeicher überschreitet, der durch das Entfernen inaktiver Datasets abgerufen werden kann, wird später erneut versucht, die Aktualisierung auszuführen, bis ausreichend Arbeitsspeicher zum Verarbeiten der Sammlung vorhanden ist.

**Eine Abfrage wird für ein Dataset ausgeführt, das nicht genügend Arbeitsspeicher durch Entfernen aller inaktiven Datasets und Aktualisierungen abrufen kann**. Diese Abfragen schlagen fehl. Für derartige Workloadanforderungen sollte höhere Kapazität erworben werden.

## <a name="troubleshooting-and-testing"></a>Problembehandlung und Tests

Wenn Berichte langsam verlaufen oder nicht reagieren, starten Sie, indem Sie einen einzigen Benutzer in Ihrem Bericht testen. Beginnen Sie dann, die Auslastung mit gleichzeitigen Benutzern zu erhöhen, um den Grenzwert zu ermitteln. In vielen Fällen kann das Optimieren Ihrer DAX-Abfragen die Leistung Ihrer Berichte maßgeblich verändern. Durch das Optimieren von Abfragen wird auch die Anzahl gleichzeitiger Benutzer erhöht, die von Ihrer Kapazität unterstützt werden. [Überwachen Sie Ihre Kapazität](service-admin-premium-monitor-capacity.md), um potenzielle Leistungsprobleme zu identifizieren.

Verwenden Sie Power BI Embedded-Kapazität in Azure, um verschiedene SKUs zu testen und die beste Premium-SKU für die erwartete Workload zu bestimmen. Die Power BI Embedded-A4-SKU entspricht P1, A5 = P2 und A6 = P3. In Azure können Sie einfach durch Skalierung nach oben oder unten im Azure-Portal zwischen SKUs wechseln. Wenn Sie die ideale SKU für Ihre Workload gefunden und die Tests abgeschlossen haben, können Sie die SKU löschen.

In einigen Fällen erhalten Sie ausführliche Informationen zu diesem Problem, wenn Sie eine PBIX-Datei (Power BI Desktop) des Modells auf Ihrem Computer öffnen und Arbeitsspeicher- und CPU-Auslastung überprüfen. Dies eignet sich nicht für sehr große, aber für einige kleinere Modelle – versuchen Sie, das Modell von Ihrem Computer zu öffnen, zu aktualisieren und abzufragen. Überprüfen Sie Modellgröße, Arbeitsspeicher und CPU-Nutzung, wenn Sie das Modell öffnen. Versuchen Sie, zu aktualisieren und abzufragen. Verwenden Sie den Task-Manager, um die CPU- und Arbeitsspeicherauslastung der lokalen Datei zu überprüfen. In einigen Fällen können diese Metriken auf Ihrem Computer selbst feststellen, dass eine niedrigere Premium-Kapazität wie P1/P2 möglicherweise nicht für Ihre Lösung funktioniert.

## <a name="next-steps"></a>Nächste Schritte

[Verwalten von Kapazitäten in Power BI Premium und Power BI Embedded](service-admin-premium-manage.md)