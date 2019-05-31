---
title: Verwenden von Cross-Report-Drillthrough im Power BI Desktop
description: Erfahren Sie, wie Sie einen Bericht in eine andere in Power BI Desktop einen Drillthrough von
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 04/08/2019
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 45a7cdd3c7b5324f3d618eaba4bdb3968a9549a5
ms.sourcegitcommit: 8bf2419b7cb4bf95fc975d07a329b78db5b19f81
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2019
ms.locfileid: "66375187"
---
# <a name="use-cross-report-drillthrough-in-power-bi-desktop"></a>Verwenden von Cross-Report-Drillthrough im Power BI Desktop

Mit der Drillthroughfunktion Cross-Bericht in Power BI Desktop können Sie je nach Kontext aus einem Bericht mit einem anderen Bericht springen. Dies gilt, solange die Berichte innerhalb des gleichen Arbeitsbereich oder in Microsoft Power BI-Dienst-app sind. Verwenden von Drillthrough für Cross-Report-Verbindung von zwei oder mehr Berichte, die Inhalt verknüpft haben, und den Filterkontext zusammen mit der Verbindung mit der Cross-Berichtsserver zu übergeben. In diesem Artikel erfahren Sie, wie zum Einrichten eines Drillthroughberichts Cross-Bericht für Power BI-Berichten und was auftreten, wenn sie den Drillthrough Cross-Bericht für sich selbst verwenden.

![Screenshot von Power BI Desktop-Drillthrough-option](media/desktop-cross-report-drill-through/cross-report-drill-through-01.png)

Die folgenden Definitionen sind wichtig, zu verstehen, bevor wir beginnen das Einrichten und Verwenden von Cross-Bericht Drillthrough:

* **Quellvisual:** Das visuelle Element, das die Drillthrough-Aktion mit dem visuellen Kontext-Menü aufruft.
* **Der Quellbericht:** Der Bericht, der das visuelle Quellelement für den Drillthrough für Cross-Bericht enthält.
* **Zielseite:** Die Seite, die ein Benutzer zu gelangt, nach dem Initiieren einer Drillthroughaktion.
* **Zielbericht:** Der Bericht, der die Zielseite für den Drillthrough für Cross-Bericht enthält.

## <a name="enable-cross-report-drillthrough"></a>Aktivieren von Drillthrough für Cross-Bericht

Um einen Bericht auf das Ziel eines Drillthroughberichts Cross-Bericht zu aktivieren, müssen Sie die Funktion für diesen Bericht in Aktivieren der **Optionen** Fenster. Wechseln Sie zu **Datei** > **Optionen und Einstellungen** > **Optionen**, und navigieren Sie zu **Berichtseinstellungen** in der Nähe der unten auf der Seite auf der linken Seite.

Wählen Sie die **können Sie visuelle Elemente in diesem Bericht für die Verwendung von Drillthrough-Ziele, die von anderen Berichten** Kontrollkästchen, wie in der folgenden Abbildung dargestellt.

![Screenshot der Optionen angezeigt, klicken Sie mit Einstellungen für den hervorgehoben](media/desktop-cross-report-drill-through/cross-report-drill-through-02.png)

Drillthrough für Cross-Bericht ist jetzt aktiviert.

## <a name="set-up-cross-report-drillthrough"></a>Einrichten von Drillthrough für Cross-Bericht

Einrichten von Drillthrough für Cross-Bericht ähnelt das Einrichten von Drillthrough in einem Bericht. Drillthrough ist auf der Zielseite aktiviert, sodass andere Visualisierungen auf der Seite "aktiviert" für den Drillthrough abzielen. Die Schritte zum Erstellen von Drillthrough in einem einzelnen Bericht finden Sie unter [verwenden der Drillthroughfunktion in Power BI Desktop](desktop-drillthrough.md).

Um den Installationsvorgang zu starten, müssen Sie einige erste-Schritte ausführen:

* Richten Sie einen Drillthrough-Zielseite, die dann von anderen Berichten im Arbeitsbereich oder app zugegriffen werden kann.
* Können Sie einen Bericht, um Drillthrough-Seiten von außerhalb der eigenen Berichts anzuzeigen.

Suchoptionen Drillthrough in die **Felder** Teil der **Visualisierungen** Bereich, der in der folgenden Abbildung dargestellt.

![Screenshot des Bereichs "Visualisierungen", mit hervorgehobenen Drillthrough-Optionen](media/desktop-cross-report-drill-through/cross-report-drill-through-03.png)

Der erste Schritt beim Aktivieren von Drillthrough für eine Seite ist die Datenmodelle für die Quell- und Berichte zu überprüfen. Stellen Sie sicher, dass: 

* Felder, die Sie übergeben möchten, die in Datenmodellen vorhanden sind.
* Die Namen der Felder und die Namen der Tabellen, denen sie angehören, sind identisch (die Zeichenfolgen müssen ebenfalls übereinstimmen und Groß-/Kleinschreibung beachtet werden).

Wenn Sie einen Filter auf das Feld übergeben möchten z. B. *Land* in Tabelle *Geography*, beider Modelle müssen eine *Geography* Tabelle und eine *Land* Feld in der Tabelle. Wenn dies nicht der Fall ist, müssen Sie den Feldnamen oder den Tabellennamen in der zugrunde liegenden Modell aktualisieren. Aktualisieren einfach den Anzeigenamen der Felder funktioniert ordnungsgemäß für Cross-Report-Drillthrough nicht. (Beachten Sie, dass die Schemas in jedem Bericht nicht identisch sein.)

Um mit dem Setup beginnen, müssen Sie auf der Seite "Ziel" vorzubereiten. Klicken Sie in Power BI Desktop öffnen Sie die Seite, und stellen Sie sicher die **Cross-Bericht** Drillthrough ein-/ausschalten nastaven NA hodnotu **auf**. 

![Screenshot des Cross-Bericht ein-/ausschalten, die auf On festgelegt](media/desktop-cross-report-drill-through/cross-report-drill-through-03.png)

Ziehen Sie anschließend die Felder, die Sie als Ziel für Drillthrough auf die Canvas verwenden möchten. Wählen Sie, ob das Feld als eine Kategorie verwendet werden soll, oder zusammengefasst, wie ein Measure werden sollen. An diesem Punkt können Sie auswählen, ob Sie deaktivieren möchten die **alle Filter beibehalten** ein/aus, für das visuelle Element. Wenn Sie keine andere angewendete Filter aus der Quelle visual an Ihr Ziel-Drillthrough visual übergeben möchten, wählen Sie **aus**.

> [!NOTE]
> Wenn Sie die Seite für Cross-Report-Drillthrough nur verwenden, sollten Sie löschen die **wieder** Schaltfläche, die automatisch hinzugefügt wird. Die **wieder** Schaltfläche funktioniert nur für Nagivation in einem einzelnen Bericht. 

Nachdem Sie das visuelle Element konfiguriert haben, stellen Sie sicher, dass Sie den Bericht speichern, wenn Sie im Power BI-Dienst sind, oder speichern, und veröffentlichen Sie den Bericht aus, wenn Sie Power BI Desktop verwenden.

Im vorherigen Abschnitt beschrieben, wie Sie Drillthrough für Cross-Bericht für Power BI Desktop zu aktivieren (in der **Optionen** Fenster). Wenn Sie zum Erstellen von eines Ziels-Drillthrough für Cross-Bericht, um Cross-Report-Drillthrough zu aktivieren, Sie müssen, Power BI-Dienst verwenden: 

1. Wählen Sie den Arbeitsbereich, in dem sich Ihre Ziel und Quellbericht befinden.
2. Wählen Sie **Berichte**.
3. Wählen Sie die **Einstellungen** Symbol für Quellbericht einen Fehler verursacht.
4. Stellen Sie sicher, dass die Umschaltfläche Cross-Report-Drillthrough **auf**.
5. Speichern Sie den Bericht an.

Fertig! Ihr Bericht ist für die Cross-Report-Drillthrough-Oberfläche bereit. 

Im nächsten Abschnitt sehen wir, wie die aus Sicht des Benutzers.

## <a name="cross-report-drillthrough-experience"></a>Cross-Report-Drillthrough-Erfahrung

Wenn Sie die Cross-Report-Drillthrough-Erfahrung für einen Bericht konfigurieren, können Sie die Funktion zur einfügen.

Wählen Sie den Quellbericht in Power BI-Dienst, und wählen Sie dann auf eine Visualisierung, die verwendet werden, das Feld oder Felder in die Möglichkeit, die Sie beim Einrichten der Seite "Ziel" angegeben haben. Als Nächstes Maustaste einen Datenpunkt, um die visuellen Kontext-Menü zu öffnen, und wählen **Drillthrough**.

![Screenshot der Quellbericht in Power BI-Dienst, mit Drillthrough hervorgehoben](media/desktop-cross-report-drill-through/cross-report-drill-through-01.png)

Klicken Sie dann sehen die Ergebnisse in der Ziel-Cross-Report-drillthroughseite Sie genau, wie Sie sie richten Sie beim Erstellen des Ziels. Die Ergebnisse werden nach der Drillthrougheinstellungen gefiltert.

> [!IMPORTANT]
> Powerbi speichert Cross-Report-Drillthrough-Ziele. Wenn Sie Änderungen vornehmen, sollten Sie darauf achten Sie, dass Sie Ihren Browser aktualisieren, wenn Sie nicht die Drillthrough-Ziele wie erwartet angezeigt. 

Cross-Report-Ziele werden wie folgt formatiert: 

`Target Page Name [Target Report Name]`

Nachdem Sie auf der Seite "Ziel" auswählen, zum Ausführen eines Drillthroughs werden soll, wird Power BI zu dieser Seite. Filterkontext auf Grundlage der Einstellungen von der Seite "Ziel" übergibt. 

Filterkontext aus dem quellvisual kann Folgendes umfassen: 

* Bericht, Seiten- und Filter auf visueller Ebene Auswirkungen auf das visuelle Quellelement. 
* Kreuzfiltern und übergreifende Hervorhebung, die Auswirkungen auf das visuelle Quellelement aus. 
* Datenschnitte auf der Seite und der Slicer synchronisieren.
* URL-Parameter.

Wenn Sie auf dem Zielbericht für den Drillthrough zu verschieben, gilt die Power BI nur Filter für Felder, die für die festgestellt wird, entspricht genau der Zeichenfolge für das Feld und Tabellennamen. Powerbi anwenden nicht persistente Filter aus den Zielbericht. Der Fall ist, gelten diese Ihrer persönlichen Standardverzeichnis für Lesezeichen jedoch ggf. vorhandenen eigenschaftennamenparameter. Wenn Ihre persönliche Standardverzeichnis für Lesezeichen einen Filter auf Berichtsebene für enthält z. B. *Country = US*, Power BI wendet zunächst, dass der Filter vor dem Anwenden des filterkontexts aus dem quellvisual. 

Für den Drillthrough für Cross-Bericht übergibt Power BI den Filterkontext für alle standard-Seiten im Zielbericht an. Filterkontext für QuickInfo-Seiten, kann von Powerbi nicht übergeben werden, da der QuickInfo-Seiten basierend auf dem visual Source gefiltert werden, die die QuickInfo aufruft.

Wenn Sie nach dem die Cross-Report-Drillthrough-Aktion an den Quellbericht zurückkehren möchten, verwenden Sie im Browsers auf die **wieder** Schaltfläche. 

## <a name="next-steps"></a>Nächste Schritte

Folgende Artikel könnten Sie ebenfalls interessieren:

* [Verwenden von Slicern in Power BI Desktop](visuals/power-bi-visualization-slicers.md)
* [Verwenden der Drillthroughfunktion in Power BI Desktop](desktop-drillthrough.md)

