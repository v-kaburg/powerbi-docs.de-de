---
title: Nutzung und Optimierung des Power BI Premium-Kapazitätsspeichers
description: Lernen Sie Verwaltung und Optimierung des Power BI Premium-Kapazitätsspeichers kennen.
ms.date: 04/30/2018
ms.topic: conceptual
ms.service: powerbi
ms.component: powerbi-admin
ms.author: susuresh
ms.reviewer: susuresh
author: suds001
manager: kfile
ms.openlocfilehash: 03c5e56c5f516bb1f09f51463d4c533185fbb63c
ms.sourcegitcommit: 2a7bbb1fa24a49d2278a90cb0c4be543d7267bda
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2018
ms.locfileid: "34298456"
---
# <a name="power-bi-premium-capacity-resource-management-and-optimization"></a>Verwaltung und Optimierung der Power BI Premium-Kapazitätsressource

In diesem Artikel wird beschrieben, wie der Power BI-Premium-Dienst Ressourcen verwaltet, und er enthält Tipps zum Planen und Optimieren Ihrer Lösung.

## <a name="premium-capacity-memory-management"></a>Verwaltung des Premium-Kapazitätsspeichers

 Premium-Kapazitätsspeicher wird verbraucht durch:

* Von den geladenen Datasets belegtem Arbeitsspeicher
* Von der Datasetaktualisierung (geplant und bedarfsgesteuert) belegtem Arbeitsspeicher
* Von Berichtabfragen belegtem Arbeitsspeicher

Wenn eine Anforderung an ein veröffentlichtes Dataset in Ihrer Kapazität ausgegeben wird, wird das Dataset aus dem permanenten Speicher in den Arbeitsspeicher geladen (dies wird auch als Ladevorgang bezeichnet). Wenn das Dataset im Arbeitsspeicher geladen bleibt, erleichtert dies die schnelle Reaktion auf zukünftige Abfragen dieses Datasets. Abgesehen von dem Speicherplatz, der benötigt wird, um das Dataset im Arbeitsspeicher geladen zu halten, verbrauchen Berichtsabfragen und Datasetaktualisierungen zusätzlichen Arbeitsspeicher.

### <a name="dataset-memory-estimation"></a>Schätzung des Datasetarbeitsspeichers

Beim Versuch, ein Dataset in den Arbeitsspeicher zu laden, schätzt Power BI ein, wieviel Arbeitsspeicher dieses Dataset benötigt, um den angeforderten Befehl auszuführen. Im Arbeitsspeicher sind Datasets tendenziell umfangreicher, als wenn sie auf dem Datenträger gespeichert werden. Während der Aktualisierung eines Datasets erfordert die Arbeitsspeicherkapazität mindestens das Doppelte der im Leerlauf erforderlichen Menge an Arbeitsspeicher.

### <a name="overcommitting-capacity-eviction-and-reloading-of-datasets"></a>Überlastung der Kapazität, Entfernung und erneutes Laden von Datasets

Power BI Premium bietet Ihnen den Vorteil, dass Sie Ihre Kapazität überlasten können. Beispielsweise können Sie mehr Datasets veröffentlichen, als der Kapazitätsspeicher aufnehmen kann. Wenn die veröffentlichten Datasets in Ihrer Kapazität mehr Arbeitsspeicher benötigen, als die Kapazität aufnehmen kann, werden einige Datasets separat in einem permanenten Speicher gespeichert. Der permanente Speicher ist Teil eines 100-TB-Speichers, der allen Ihren Kapazitäten zugeordnet ist.

Welche Datasets bleiben also im Arbeitsspeicher, und was passiert mit den anderen Datasets? Wie bereits beschrieben, wird ein Dataset in den Arbeitsspeicher geladen (Imageladevorgang), wenn eine Anforderung daran gerichtet wird. Die Anforderung könnte eine Berichtsabfrage oder ein Aktualisierungsvorgang sein.

Da Sie Ihre Kapazität überlasten können, kann in Ihrer Kapazität auch eine Speicherauslastung auftreten. Wenn in der Kapazität eine Speicherauslastung auftritt (weil ein neues Dataset geladen werden muss oder die Abfragen einiger geladener Datasets den Speicherbedarf erhöhen), *entfernt der Knoten einen oder mehrere Datasets*, die den Kapazitätsspeicher belegen. Datasets, die inaktiv sind (d.h. es wird derzeit keine Abfrage/Aktualisierung ausgeführt), werden zuerst entfernt, und die Reihenfolge der Entfernung wird durch das „Selten verwendet“-Prinzip (Least Recently Used, LRU) bestimmt. Wenn neue Befehle an das entfernte Dataset gerichtet werden, versucht der Dienst, dies erneut in den Speicher zu laden, wobei potenziell andere Datasets entfernt werden. Dieses Verhalten ermöglicht eine effizientere Nutzung, indem die Kapazität mehr Datasets bedienen als ihr Speicher aufnehmen kann.

Das Laden eines Datasets in den Arbeitsspeicher ist ein relativ kostspieliger Vorgang. Je nach Größe des Datasets kann es von wenigen Sekunden für kleine Datasets bis zu Vielfachen von zehn Sekunden oder sogar Minuten für große Datasets wie Datasets mit einer Größe von etwa 10GB dauern. Premium-Kapazität versucht, die erforderliche Anzahl der Ladungen der Kapazität zu reduzieren, indem die selten verwendeten Datasets solange wie möglich im Arbeitsspeicher gehalten werden. Wenn zusätzlicher Speicher benötigt wird, müssen einige Datasets entfernt werden, und das System versucht, dasjenige auszuwählen, das sich am geringsten auf die Benutzerfreundlichkeit auswirkt. Wenn zusätzlicher Speicher benötigt wird, müssen einige Datasets entfernt werden, und das System versucht, dasjenige auszuwählen, das sich am geringsten auf die Benutzerfreundlichkeit auswirkt. Das System wird z.B. vermeiden, Datasets zu entfernen, die innerhalb der letzten Minuten aktiv verwendet wurden, da sie wahrscheinlich sehr bald wieder abgefragt werden.

Die Entfernung selbst ist ein schneller Vorgang. Wenn das Dataset zum Zeitpunkt der Entfernung nicht aktiv verwendet wird, wird der Benutzer die Entfernung kaum wahrnehmen. Wenn jedoch zu viele Datasets gleichzeitig aktiv verwendet werden, und der Arbeitsspeicher nicht ausreicht, um alle aufzunehmen, können viele Entfernungen auftreten. Dies kann zu einer Überlastungssituation führen, wobei Datasets ständig entfernt und erneut geladen werden, und Benutzer könnten verlängerte Antwortzeiten und einen Leistungsabfall feststellen.

### <a name="dataset-refresh-memory-requirement-competing-with-an-active-dataset-memory-requirement"></a>Arbeitsspeicherbedarf einer Datasetaktualisierung in Konkurrenz zum Arbeitsspeicherbedarf eines aktiven Datasets

Datasets können nach einem Zeitplan oder bei Bedarf durch Benutzer aktualisiert werden. Wie bereits beschrieben, erfordern vollständige Aktualisierungen mindestens das Doppelte der Speichergröße der geladen und im Leerlauf befindlichen Datasets. Vor Beginn der Aktualisierung wird der Arbeitsspeicherbedarf für die Aktualisierung geschätzt. Wenn der gesamte Arbeitsspeicherbedarf den in der Kapazität verfügbaren Speicher überschreitet, werden einige Datasets entfernt. Die Kandidaten für die Entfernung werden nach der Reihenfolge der selten verwendeten Datasets ausgewählt, d.h. der Dienst versucht, so viele zuletzt verwendete Datasets wie möglich im Arbeitsspeicher beizubehalten.

Wenn der erforderliche Arbeitsspeicher trotz Entfernung nicht verfügbar ist, wird die Aktualisierung zur Wiederholung in die Warteschlange gestellt. Der Dienst unternimmt bis zum erfolgreichen Abschluss oder zum Beginn einer neuen Aktualisierung neue Versuche.

Wenn eine interaktive Abfrage an ein Dataset in der Kapazität gerichtet wird und aufgrund einer laufenden Aktualisierung nicht genügend Arbeitsspeicher verfügbar ist, gilt diese Anforderung als nicht erfolgreich und muss vom Benutzer wiederholt werden.

## <a name="cpu-resource-management-in-premium-capacity"></a>CPU-Ressourcenverwaltung in Premium-Kapazität

Es gibt zwei primäre Nutzer von CPU-Ressourcen:

- Abfragen von Berichten
- Aktualisierung (Verarbeitung)

### <a name="queries-from-reports"></a>Abfragen von Berichten

Berichtsabfragen nutzen CPU-Ressourcen Ihrer Kapazität. Wenn Ihr Bericht einige ineffiziente Abfragen aufweist, oder Sie über viele gleichzeitige Benutzer verfügen, kann er viele CPU-Ressourcen beanspruchen, sodass Ihre vorhandene Kapazität möglicherweise nicht ausreicht, um die Auslastung zu bewältigen.

### <a name="refresh-parallelization-policy"></a>Richtlinie zum Aktualisieren der Parallelisierung

Speicher ist nicht die einzige Ressource, die das Aktualisieren von Datasets einschränken kann. Die Anzahl der virtuellen Kerne eines Servers kann auch ein Faktor sein. Da jeder Aktualisierungsvorgang eine bestimmte Anzahl virtueller Kerne erfordert, besteht eine Grenze für die Anzahl paralleler Aktualisierungen. Die folgende Tabelle informiert Sie ausführlich über den Grenzwert pro SKU. Zusätzliche, diese Grenzwerte überschreitende Aktualisierungen werden in die Warteschlange eingereiht.

 | SKU  | Back-End-V-Kerne  | Aktualisierungsparallelität nach Modell   |
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

Im Folgenden werden einige allgemeinen Szenarien und die vom Dienst ausgeführten Aktionen beschrieben:

 **Zwanzig geplante Aktualisierungen, die alle zur selben Zeit übermittelt werden**: Power BI versucht, die ersten *x* Aktualisierungen gleichzeitig zu starten. Der Wert für *x* richtet sich nach der Richtlinie zum Aktualisieren der Parallelisierung für diese SKU. Wenn Power BI durch Entfernen inaktiver Datasets (nicht vor kurzem verwendeter Datasets) nicht genügend Arbeitsspeicher abrufen kann, werden nicht alle *x* Aktualisierungen zur selben Zeit gestartet. Alle Aktualisierungen, die nicht gestartet werden können, werden in die Warteschlange gestellt, bis sie beginnen können.

 **Zwei Aktualisierungen, die zur gleichen Zeit ausgeführt werden, und es steht nur genügend Speicher zur Verfügung, um eine fertig zu stellen**: Diejenige startet, die abgeschlossen werden kann. Die andere wird später erneut versucht.

 **Große Anzahl von Datasets, die abgefragt wird, während mehrere Datasets aktualisiert werden**: Wenn nicht genügend Arbeitsspeicher zur Verfügung steht, versucht Power BI, aktive Aktualisierungen zu beenden, um interaktiven Abfragen Priorität einzuräumen. Dies führt zu Leistungseinbußen bei der Aktualisierung.

 **Dataset erfordert zu viel Arbeitsspeicher, um bei der aktuellen Kapazitätsgröße aktualisiert werden zu können**: Aktualisierung kann nicht ausgeführt werden. Es werden keine Versuche unternommen, mehr Arbeitsspeicher durch Entfernung abzurufen.

 **Aktualisieren eines einzelnen Datasets, der über eine große Sammlung im Arbeitsspeicher verfügt**: Wenn die Sammlung größer ist als der Arbeitsspeicher, der durch das Entfernen inaktiver Datasets abgerufen werden kann, wird später erneut versucht, die Aktualisierung auszuführen, bis ausreichend Arbeitsspeicher zum Verarbeiten der Sammlung vorhanden ist.

 **Abfrage wird für ein Dataset ausgeführt, das nicht genügend Arbeitsspeicher durch Entfernen aller inaktiven Datasets und Aktualisierungen abrufen kann**: Diese Abfragen sind nicht erfolgreich. Für derartige Workloadanforderungen sollte höhere Kapazität erworben werden.

## <a name="troubleshooting-and-testing"></a>Problembehandlung und Tests

Wenn Berichte langsam verlaufen oder nicht reagieren, starten Sie, indem Sie einen einzigen Benutzer in Ihrem Bericht testen. Beginnen Sie dann, die Auslastung mit gleichzeitigen Benutzern zu erhöhen, um den Grenzwert zu ermitteln. In vielen Fällen kann eine Optimierung Ihrer DAX (Berichtsabfragen) die Leistung Ihrer Berichte drastisch ändern (und die Anzahl von gleichzeitigen Benutzern erhöhen, die durch Ihre Kapazität unterstützt werden).

Verwenden Sie Power BI Embedded-Kapazität in Azure, um verschiedene SKUs zu testen und die beste Premium-SKU für die erwartete Workload zu bestimmen. Die Power BI Embedded-A4-SKU entspricht P1, A5 = P2 und A6 = P3. In Azure können Sie einfach durch Skalierung nach oben oder unten im Azure-Portal zwischen SKUs wechseln. Wenn Sie die ideale SKU für Ihre Workload gefunden und die Tests abgeschlossen haben, können Sie die SKU löschen.

In einigen Fällen erhalten Sie ausführliche Informationen zu diesem Problem, wenn Sie eine PBIX-Datei des Modells auf Ihrem Computer öffnen und Arbeitsspeicher- und CPU-Auslastung überprüfen. Dies eignet sich nicht für sehr große, aber für einige kleinere Modelle – versuchen Sie, das Modell von Ihrem Computer zu öffnen, zu aktualisieren und abzufragen. Überprüfen Sie Modellgröße, Arbeitsspeicher und CPU-Nutzung, wenn Sie das Modell öffnen. Versuchen Sie, zu aktualisieren und abzufragen. Überprüfen Sie mit dem Task-Manager die CPU- und Arbeitsspeicherauslastung für die lokale PBIX-Datei. In einigen Fällen können diese Metriken auf Ihrem Computer selbst feststellen, dass eine niedrigere Premium-Kapazität wie P1/P2 möglicherweise nicht für Ihre Lösung funktioniert.
