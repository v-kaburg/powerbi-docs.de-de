---
title: Szenarien für Microsoft Power BI Premium-Kapazität
description: Beschreibt häufige Szenarien von Power BI Premium-Kapazität.
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 04/09/2019
ms.custom: seodec18
LocalizationGroup: Premium
ms.openlocfilehash: 1d666a6702515a935d93549d026f207848f2bca8
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2019
ms.locfileid: "65565352"
---
# <a name="premium-capacity-scenarios"></a>Szenarien für Premium-Kapazität

Dieser Artikel beschreibt die reale Szenarien, in denen Power BI Premium-Kapazitäten implementiert wurden. Häufig auftretende Probleme und Herausforderungen beschrieben, außerdem Probleme zu identifizieren und lösen lassen:

- [Datasets auf dem neuesten Stand halten](#keeping-datasets-up-to-date)
- [Identifizieren langsame Reaktion datasets](#identifying-slow-responding-datasets)
- [Identifizieren von Ursachen für sporadisch langsam reagieren Datasets](#identifying-causes-for-sporadically-slow-responding-datasets)
- [Bestimmt, ob genügend Arbeitsspeicher](#determining-whether-there-is-enough-memory)
- [Bestimmt, ob genügend CPU](#determining-whether-there-is-enough-cpu)

Die Schritte, anhand von Beispielen, Diagramm und Tabelle stammen aus der **Kapazitätsmetriken für Power BI Premium-app** , dass ein Power BI-Administrator Zugriff zu erhalten.

## <a name="keeping-datasets-up-to-date"></a>Datasets auf dem neuesten Stand halten

In diesem Szenario wurde eine Untersuchung ausgelöst, wenn Benutzer sich darüber beschwert, dass Berichtsdaten wird manchmal "veraltete" werden angezeigt.

In der app interagiert der Administrator die **aktualisiert** visuelle Element, und Sortieren von Datasets durch die **Max. Wartezeit** Statistiken in absteigender Reihenfolge. Dieses visuelle Element können sie die Datasets, die mit der längsten Wartezeiten, gruppiert nach dem Namen des Arbeitsbereichs anzuzeigen.

![DataSet-Aktualisierungen, die maximale Wartezeit, gruppiert nach Arbeitsbereich absteigend sortiert](media/service-premium-capacity-scenarios/dataset-refreshes.png)

In der **stündlichen durchschnittliche aktualisieren warten Sie, wie oft** visual, sie feststellen, dass die Aktualisierung Wartezeiten konsistent rund um 16 Uhr täglich spitzenauslastung.

![Aktualisieren Sie wartet Spitze in regelmäßigen Abständen um 16 Uhr](media/service-premium-capacity-scenarios/peak-refresh-waits.png)

Es gibt mehrere mögliche Erklärungen für diese Ergebnisse:

- Zu viele Aktualisierungsversuchen können zur gleichen Zeit, auftreten überschreiten von Grenzwerten für die von der kapazitätsknoten definiert. In diesem Fall standardmäßig sechs gleichzeitige Aktualisierungen auf eine P1 mit speicherbelegung.

- Datasets aktualisiert werden, möglicherweise zu groß für verfügbare Speicher (und erfordert mindestens 2 x den erforderlichen Speicher für die vollständige Aktualisierung).
- Ineffiziente Power Query-Logik kann in eine Auslastungsspitze von Arbeitsspeicher während der Datasetaktualisierung resultierende sein. Für eine ausgelastete Kapazität erreichen dieser Spitze gelegentlich die physische Grenze, die Aktualisierung fehlschlägt, und möglicherweise Auswirkungen auf andere Vorgänge Bericht anzeigen, auf der Kapazität.
- Häufig abgefragte Datasets, die im Speicher verbleiben müssen, beeinträchtigen die Fähigkeit eines anderen Datasets, die aufgrund von begrenzt verfügbaren Arbeitsspeicher zu aktualisieren.

Power BI-Administrator kann damit untersuchen können, suchen Sie nach:

- Unzureichender Arbeitsspeicher zum Zeitpunkt der Daten aktualisiert wird, wenn der verfügbare Arbeitsspeicher auf weniger als 2 x die Größe des Datasets aktualisiert ist.
- Datasets, die nicht aktualisiert und noch nicht im Arbeitsspeicher vor der Aktualisierung, gestartet, um interaktive Datenverkehr während hohe Aktualisierungszeiten anzuzeigen. Um anzuzeigen, welche Datasets zu jedem Zeitpunkt in den Arbeitsspeicher geladen werden, kann ein Power BI-Administrator sehen Sie sich den Bereich "Datasets" des **Datasets** Registerkarte in der app. Der Administrator kann dann plattformübergreifend filtern, zu einem bestimmten Zeitpunkt durch Klicken auf einen Balken in den **stündlichen geladen Dataset zählt**. Eine lokale Spitze, die in der folgenden Abbildung dargestellt zeigt an, eine Stunde, wenn mehrere Datasets in den Arbeitsspeicher geladen wurden, der Anfang des geplanten Aktualisierungen verzögert werden kann.
- Erhöhte Dataset entfernungen dauert platzieren, wenn es sich bei datenaktualisierungen geplant sind, um zu starten. Entfernungen können auf hohe speicherauslastung verursacht wurde, stellt viele verschiedene interaktive Berichte vor dem Zeitpunkt der Aktualisierung vorhanden hinweisen. Die **stündlichen Dataset Entfernungen und Arbeitsspeichernutzung** Visual kann Spitzen in der entfernungen eindeutig anzugeben.

Die folgende Abbildung zeigt eine lokale Spitze in der geladenen Datasets, das bedeutet, dass interaktive Abfragen verzögert Anfang aktualisiert. Wählen einen Zeitraum auf die **stündlichen geladen Dataset zählt** Visual kreuzt Filter die **Größe des Datasets beseitigt** visual.

![Eine lokale Spitze in der geladenen Datasets vorgeschlagen, interaktive Abfragen verzögerten Start von Aktualisierungen](media/service-premium-capacity-scenarios/hourly-loaded-dataset-counts.png)

Power BI-Administrator versuchen, das Problem zu beheben, indem Sie Schritte ausführen, um sicherzustellen, dass ausreichend Arbeitsspeicher für datenaktualisierungen zunächst verfügbar ist:

- Kontaktaufnahme mit dem Dataset aktualisieren Besitzer und aufgefordert, zu staffeln Daten trennen Zeitpläne.
- Verkleinern Datasets Kacheln durch Abfragen verursachte Last durch das Entfernen unnötiger Dashboards oder Dashboard, insbesondere über diejenigen, die Sicherheit auf Zeilenebene zu erzwingen.
- Beschleunigen der datenaktualisierungen durch Optimieren der Power Query-Logik. Verbessern Sie die Modellierung von berechneten Spalten oder Tabellen. Reduzieren Sie der Größe des Datasets beseitigt, oder konfigurieren Sie größere Datasets Durchführung inkrementeller datenaktualisierungen.

## <a name="identifying-slow-responding-datasets"></a>Identifizieren langsame Reaktion datasets

In diesem Szenario eine Untersuchung begonnen hat, wenn Benutzer sich darüber beschwert, dass bestimmte Berichte öffnen, zu lange gedauert hat und zuweilen mehr reagierte.

In der app kann der Power BI-Administrator mithilfe der **Abfragedauern** das visuelle Element an die schlechteste Leistung Datasets zu bestimmen, indem Sie das Sortieren von Datasets nach absteigender **Durchschnittsdauer**. Dieses visuelle Element wird auch Dataset Anzahl von Abfragen, damit Sie sehen, wie oft die Datasets abgefragt werden.

![Schlechteste Leistung datasets](media/service-premium-capacity-scenarios/worst-performing-datasets.png)

Der Administrator kann, finden Sie in der **Abfrage Dauerverteilung** Visualisierung zeigt ein gesamtverteilung von Buckets abfrageleistung (< = 30ms, 0 – 100 ms) für den gefilterten Zeitraum. Im Allgemeinen Abfragen akzeptieren einer Sekunde oder weniger werden von den meisten Benutzern reaktionsfähig berücksichtigt Abfragen, die länger dauern tendenziell eine Vorstellung von schlechte Leistung erstellen.

Die **Verteilung der Dauer für die stündliche Abfrage** Visual kann der Administrator Power BI ein-Stunden-Zeiträume zu identifizieren, wenn die Leistung der Kapazität kann haben wurde erkannt, die als schlechter. Je größer Segmente die Leiste der Abfrage darstellen Dauer von mehr als einer Sekunde, je größer das Risiko, dass Benutzer eine schlechte Leistung wahrgenommen werden.

Das visuelle Element ist interaktiv, und wenn ein Segment des Balkens aktiviert ist, den entsprechenden **Abfragedauern** tabellenvisual auf der Berichtsseite ist kreuzgefiltert Datasets angezeigt, dar. Power BI-Administrator auf einfache Weise identifizieren, die diese kreuzfilterung ermöglicht die Datasets langsam reagiert.

Die folgende Abbildung zeigt eine Visualisierung gefiltert nach **stündlichen Abfrage Dauer Verteilungen**die schlechteste Leistung Datasets in einer Stunde Buckets Schwerpunkt. 

![Gefilterte stündlichen Abfrage Dauer Verteilungen visual zeigt schlechteren zu kennzeichnen, die Datasets ausführen](media/service-premium-capacity-scenarios/hourly-query-duration-distributions.png)

Nachdem eine schlechte Leistung Dataset in einer bestimmten einstündigen Zeitspanne identifiziert wurde, kann Power BI-Administrator überprüfen Sie, ob eine schlechte Leistung, wenn eine überladene Kapazität verursacht wird oder aufgrund einer fehlerhaft, Dataset oder Bericht entwickelt. Sie können den beziehen sich auf die **Abfrage warten Sie, wie oft** Visual und Sortieren von Datasets nach absteigender Durchschnittliche Abfragewartezeit. Wenn Sie ein großer Prozentsatz der Abfragen im Wartezustand befindet, ist ein hoher Bedarf an, für das Dataset wahrscheinlich die Ursache für viele Abfrage wartet. Die durchschnittliche Zeit "Abfragewartezeit" ist eine wesentliche (> 100 ms), könnte nicht Schaden, überprüfen das Dataset und den Bericht, um festzustellen, ob Optimierungen vorgenommen werden können. Z. B. weniger Visuals auf Berichtsseiten oder eine Optimierung der DAX-Ausdruck angegeben.

![Die Abfrage warten Sie, wie oft Visualisierung hilft zu schlechter Leistung Datasets anzeigen](media/service-premium-capacity-scenarios/query-wait-times.png)

Es gibt mehrere mögliche Ursachen für die Abfrage warten Zeit ansammeln in Datasets:

- Eine suboptimale Modellentwurf, Measureausdrücke oder sogar den Berichtsentwurf - alle Umstände, die über mitwirkungsrechte lang andauernde Abfragen, die hohe CPU nutzen. Dies erzwingt, dass neue Abfragen warten, bis die CPU-Threads verfügbar, und erstellen einen Konvoi-Effekt (Stellen Sie sich datenverkehrsstau), während der Hauptgeschäftszeiten häufig gesehen. Die **Abfragewartevorgänge** Seite werden die Haupt-Ressourcenskriptdatei zu bestimmen, ob die Datasets hohe durchschnittliche abfragewartezeiten enthalten.
- Eine hohe Anzahl von gleichzeitigen Kapazität Benutzer (Hunderte oder Tausende) nutzen, den gleichen Bericht oder Dataset. Sogar ausgereifte Datasets können einen Schwellenwert für die Parallelität ausführen. Dies wird in der Regel durch ein einzelnes Dataset einen deutlich höheren Wert angezeigt, für die Abfrage als andere Datasets anzeigen zählt angegeben (z. B. Abfragen von 300 KB für ein Dataset gegenüber < 30 KB-Abfragen für alle anderen Datasets). Zu einem bestimmten Zeitpunkt die Abfrage wartet für dieses Dataset gestartet wird, um staffeln, der in angezeigt werden kann die **Abfragedauern** visual.
- Viele verschiedene Datasets gleichzeitig abgefragt speicherüberlastung verursachen, da Datasets häufig in den Arbeitsspeicher durchlaufen. Dies führt dazu, dass Benutzer, die Leistungseinbußen auftreten, wenn das Dataset in den Arbeitsspeicher geladen wird. Um zu bestätigen, Power BI-Administrator kann finden Sie unter den **stündlichen Dataset Entfernungen und Arbeitsspeichernutzung** visual, die möglicherweise eine große Anzahl von Datasets in den Arbeitsspeicher geladen wird wiederholt entfernt werden.

## <a name="identifying-causes-for-sporadically-slow-responding-datasets"></a>Identifizieren von Ursachen für sporadisch langsam reagieren Datasets

In diesem Szenario wurde eine Untersuchung gestartet, wenn Benutzer beschrieben, dass berichtsvisuals manchmal wurden nur langsam reagiert, oder können nicht mehr reagiert, aber in anderen Fällen diese Auswirkung in akzeptabler Weise reagiert wurden.

Innerhalb der app die **Abfragedauern** Abschnitt wurde verwendet, um die Ursache Dataset wie folgt suchen:

- In der **Abfragedauern** visual der Administrator gefilterte Dataset von Dataset (beginnend mit dem obersten abgefragte Datasets) und untersucht die übergreifende gefilterte Balken in den **stündlichen Abfrage Verteilungen** visual.
- Wenn ein einstündigen Balken bedeutende Änderungen des Verhältnisses zwischen allen Abfragegruppen Dauer im Vergleich zu anderen Balken, eine Stunde für dieses Dataset wurde (z. B. das Verhältnis zwischen der Farben, ändert sich erheblich), es bedeutet, dass dieses Dataset veranschaulicht eine sporadische Änderung die Leistung.
- Zeigt einen unregelmäßigen Teil der Abfragen mit schlechter Leistung, eine Stunde Balken angezeigt ein TimeSpan-Objekt, in denen das Dataset durch einen konkurrierenden Effekt, durch andere Datasets Aktivitäten verursacht betroffen war.

Die folgende Abbildung zeigt eine Stunde am 30. Januar mit erheblichen preisgünstiger leistungsregression eines Datasets Fehler, angegeben durch die Größe des "(3,10s]"Ausführung Dauer Buckets. Klicken Sie auf diese Leiste einstündigen zeigt alle Datasets in den Arbeitsspeicher geladen werden, während dieser Zeit möglich, verursacht die konkurrierenden Auswirkungen Datasets anzeigen.

![Leiste mit der schlechtesten Leistung durch einen großen Teil](media/service-premium-capacity-scenarios/worst-performing-queries.png)

Sobald ein problematisch TimeSpan-Objekt (z. B. während 30. Januar in der Abbildung oben) gekennzeichnet ist kann Power BI-Administrator entfernen Sie alle datasetfilter anschließend filtern Sie nur nach dieser Zeitspanne, um zu bestimmen, welche Datasets während dieser Zeit aktiv abgefragt wurden. Das Dataset Ursache für den noisy-Neighbor-Effekt ist normalerweise auf, des oberen abgefragte Datasets oder die Woche mit die längste durchschnittliche Abfragedauer.

Eine Lösung für dieses Problem könnte sein, um die Ursache zu verteilen, die Datasets, die über unterschiedliche Arbeitsbereiche auf verschiedenen Premium-Kapazitäten oder gemeinsam genutzte Kapazität, wenn der Datasetgröße, Verbrauch Anforderungen und Daten aktualisieren Muster unterstützt werden.

Das Gegenteil könnte auch "true" sein. Power BI-Administrator konnte identifizieren Mal, wenn ein Dataset-abfrageleistung erheblich verbessert, und suchen Sie nach, was nicht mehr vorhanden. Wenn bestimmte Informationen an diesem Punkt fehlt, können, die um auf das Problem zu verweisen.

## <a name="determining-whether-there-is-enough-memory"></a>Bestimmt, ob genügend Arbeitsspeicher

Bestimmt, ob genügend für die Kapazität Arbeitsspeicher um seine Workloads abzuschließen, Power BI-Administrator kann finden Sie unter den **Arbeitsspeicherprozentsätze verbraucht** in visual die **Datasets** Registerkarte der app. **Alle** (gesamt) Arbeitsspeicher darstellt, die speicherbelegungen, die durch Datasets, die in den Arbeitsspeicher, unabhängig davon, ob diese aktiv abgefragt oder verarbeitet werden geladen. **Aktive** Arbeitsspeicher darstellt, die speicherbelegungen, die durch Datasets, die aktiv verarbeitet werden.

In einer fehlerfreien Kapazität das visuelle Element aussehen wird, zeigt eine Lücke zwischen allen (gesamt) und den aktiven Arbeitsspeicher:

![Eine fehlerfreie Kapazität wird eine Lücke zwischen allen (gesamt) angezeigt und aktiven Arbeitsspeichers](media/service-premium-capacity-scenarios/memory-healthy-capacity.png)

In einer Kapazität arbeitsspeicherauslastung auftritt zeigt dasselbe visuelle deutlich aktiven Arbeitsspeicher und Gesamtarbeitsspeicher konvergieren, was bedeutet, dass es nicht möglich, weitere Datasets klicken Sie dann in den Arbeitsspeicher geladen ist. In diesem Fall kann die Power BI-Administrator klicken **Kapazität neu starten** (in **erweiterte Optionen** der Bereich "Kapazität Einstellungen" des Verwaltungsportals). Neu starten die Ergebnisse für die Kapazität wird für alle Datasets aus dem Speicher geleert und ermöglicht ihnen, in den Arbeitsspeicher gemäß der Vorgabe (Abfrage- oder datenaktualisierungsanforderungen) neu zu laden.

![** Aktiv ** Arbeitsspeicher mit konvergieren ** alle ** Arbeitsspeicher](media/service-premium-capacity-scenarios/memory-unhealthy-capacity.png)

## <a name="determining-whether-there-is-enough-cpu"></a>Bestimmt, ob genügend CPU

Im Allgemeinen sollte eine Kapazität für die durchschnittliche CPU-Auslastung unter 80 % bleiben. Diesen Wert überschreiten, bedeutet, dass die Kapazität annähert, die die CPU-Auslastung ist.

Auswirkungen der CPU-Auslastung werden durch Vorgänge dauert länger, als sie aufgrund der Kapazität, die viele CPU-Kontexten-Schalter ausführen sollten, da es versucht, alle Vorgänge zu verarbeiten, angegeben. In einer Premium-Kapazität mit einer hohen Anzahl gleichzeitiger Abfragen wird dies durch hohe abfragewartezeiten angezeigt. Eine Folge von hohem Wartezeiten ist langsamer Reaktionsfähigkeit als üblich. Power BI-Administrator kann ganz einfach ermitteln, wenn die CPU Kapazität, anhand erschöpft ist der **stündlichen Abfrage warten Zeit Verteilungen** visual. Periodische Spitzen der Abfrage die Wartezeit Anzahl potenzieller die CPU-Auslastung angeben.

![Periodische Spitzen Abfrage Wartezeit Anzahl potenzieller die CPU-Auslastung angeben](media/service-premium-capacity-scenarios/peak-query-wait-times.png)

Ein ähnliches Muster kann manchmal in Hintergrundvorgänge erkannt werden, wenn sie auf die CPU-Auslastung beitragen. Ein Power BI-Administrator finden für ein periodischer Anstieg in der Aktualisierungen auf Zeiten für ein bestimmtes Dataset, der die CPU-Auslastung, die zum Zeitpunkt, (wahrscheinlich aufgrund von anderen laufenden Dataset aktualisiert und/oder interaktive Abfragen angeben kann). In diesem Fall auf die **System** Ansicht der app nicht unbedingt ergibt möglicherweise, dass die CPU bei 100 % liegt. Die **System** zeigt stündlichen Durchschnittswerte, jedoch die CPU kann werden ausgelastet mehrere Minuten lang, der intensive Vorgänge, die wird als Spitzen im Wartezeiten.

Es gibt weitere Details in Bezug auf die Auswirkungen der CPU-Auslastung anzeigen. Während die Anzahl der Abfragen, die warten wichtig ist, wird Abfragewartezeit immer zu einem gewissen Grad ausgeführt, ohne dass eine Verringerung der wahrnehmbaren Leistung. Einige Datasets (mit längere Durchschnittliche Abfragezeit, der angibt, Komplexität oder Größe), sind anfälliger für die Auswirkungen der CPU-Auslastung als andere. Um diese Datasets ganz einfach identifizieren zu können, sehen sich Power BI-Administrator für die Änderungen in der Zusammensetzung der Farbe der Balken in den **pro Stunde warten Verteilung** visual. Nach dem Ermitteln einer Leiste Ausreißer, können sie die Datasets, die Abfrage wartet, während dieser Zeit musste suchen und betrachten Sie auch die Durchschnittliche Abfragewartezeit verglichen, um die durchschnittliche Abfragedauer. Wenn diese beiden Metriken von der gleichen Größe werden und die abfragearbeitsauslastung für das Dataset nicht trivial ist, ist es wahrscheinlich, dass das Dataset nicht genügend CPU-Nutzung beeinträchtigt wird.

Dieser Effekt kann besonders offensichtlich sein, wenn ein Dataset in kurze Bursts sehr häufig Abfragen von mehreren Benutzern (z. B. in einer Schulung), wodurch die CPU-Auslastung während jeder Burst-genutzt wird. In diesem Fall können erhebliche abfragewartezeiten für dieses Dataset auftreten können, sowie für andere Datasets in der Kapazität (Auswirkung noisy-Neighbor) beeinträchtigt wird.

In einigen Fällen können Power BI-Administratoren fordern Sie die Besitzer von Datasets einen weniger Erstellung flüchtige abfragearbeitsauslastung durch Erstellen eines Dashboards (welche Abfragen regelmäßig mit der ein Dataset aktualisieren für zwischengespeicherte Kacheln) anstelle eines Berichts. Dies kann helfen, Spitzen zu verhindern, wenn das Dashboard geladen wird. Diese Lösung möglicherweise immer möglich, dass die angegebene geschäftsanforderungen, nicht jedoch eine effektive Möglichkeit, um die CPU-Auslastung zu vermeiden, ohne dass auf das Dataset ändern können.

## <a name="acknowledgements"></a>Bestätigungen

Dieser Artikel geschrieben wurde, indem Peter Myers, Data Platform MVP und unabhängige BI-Experte mit [bitweise Lösungen](https://www.bitwisesolutions.com.au/).

## <a name="next-steps"></a>Nächste Schritte

> [!div class="nextstepaction"]
> [Premium-Kapazitäten, mit der app überwachen](service-admin-premium-monitor-capacity.md)    
> [!div class="nextstepaction"]
> [Überwachen von Kapazitäten im Verwaltungsportal](service-admin-premium-monitor-portal.md)   

Weitere Fragen? [Stellen Sie Ihre Frage in der Power BI-Community.](https://community.powerbi.com/)

||||||