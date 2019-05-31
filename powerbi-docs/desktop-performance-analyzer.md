---
title: Verwenden von Performance Analyzer untersuchen der Leistung beim Element der Berichte in Power BI Desktop
description: Ermitteln der Leistung von Visuals und Berichtselemente im Hinblick auf die ressourcennutzung und Reaktionsfähigkeit
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/15/2019
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 1851e0a55bf01073a6591f64de43830a72eca89b
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2019
ms.locfileid: "65854411"
---
# <a name="use-performance-analyzer-to-examine-report-element-performance"></a>Verwenden von Performance Analyzer um berichtsleistung-Element zu untersuchen.

In **Power BI Desktop** finden Sie Out wie jede von Berichtselementen, wie z. B. Visuals und DAX-Formeln ausgeführt werden. Mithilfe der **Performance Analyzer**, sehen Sie und Datensatz-Protokolle, messen, wie jede von Berichtselementen ausführt, wenn der Benutzer mit ihnen interagieren und welche Aspekte der ihre Leistung sind die meisten (oder den niedrigsten) ressourcenintensiv.

![Leistungsanalyse](media/desktop-performance-analyzer/performance-analyzer-01.png)

Leistungsanalyse untersucht und zeigt die Dauer, die zum Aktualisieren oder aller visuellen Elemente erforderlich, Interaktionen der Benutzer initiiert, und werden die Informationen bereitgestellt, so können Sie anzeigen, Drilldown, und die Ergebnisse zu exportieren. Performance Analyzer können Sie visuelle Elemente, die die beeinträchtigen die Leistung Ihrer Berichte zu erkennen und identifizieren Sie die Gründe für die Auswirkungen.

## <a name="displaying-the-performance-analyzer-pane"></a>Im Bereich Performance Analyzer anzeigen

In **Power BI Desktop** wählen Sie die **Ansicht** Menüband. In der **anzeigen** Teil der **Ansicht** Menüband, Sie können das Kontrollkästchen neben **Performance Analyzer** Bereich Performance Analyzer angezeigt.

![Wählen Sie die Performance Analyzer in der Registerkarte "Ansicht"](media/desktop-performance-analyzer/performance-analyzer-02.png)

Nach der Auswahl wird die Performance Analyzer in einen eigenen Bereich rechts neben den Zeichenbereich des Berichts angezeigt.

## <a name="using-performance-analyzer"></a>Verwenden der Leistungsanalyse

Performance Analyzer Measures werden die Verarbeitungszeit (einschließlich der Zeit zum Erstellen oder aktualisieren eine Visualisierung) zum Aktualisieren von Berichtselementen, die als Ergebnis Eingreifen des Benutzers, das Ausführen einer Abfrage dazu initiiert erforderlich. Beispielsweise erfordert einen Slicer anpassen, die Slicer-Visualisierung, eine Abfrage senden, in das Datenmodell geändert werden, und die betroffenen visuellen Elemente, die durch die neuen Einstellungen aktualisiert werden müssen. 

Damit Performance Analyzer, die Aufzeichnung zu beginnen, wählen Sie einfach **Aufzeichnung starten**

![Aufzeichnung starten](media/desktop-performance-analyzer/performance-analyzer-03.png)

Alle Aktionen im Bericht werden angezeigt, und protokolliert im Bereich Performance Analyzer in der Reihenfolge, in die Visualisierung von Power BI geladen wird. Vielleicht haben Sie beispielsweise einen Bericht, den Benutzer sehr lange dauert behaupteten haben, um zu aktualisieren. Oder bestimmte Visuals in einem Bericht eine lange dauern angezeigt wird, wenn Sie ein Schieberegler angepasst wird. Leistungsanalyse erkennen Sie, dass Sie welches visuelle ist die Ursache und welche Aspekte des visuellen Elements identifiziert die längste Dauer verarbeiten ausgeführt werden. 

Nachdem Sie die Aufzeichnung starten die **Aufzeichnung starten** Schaltfläche ist abgeblendet Out (inaktiv, da Sie bereits eine Aufzeichnung dieser haben) und die **beenden** Schaltfläche ist aktiviert. 

Leistungsanalyse sammelt und zeigt die Messung Leistungsinformationen in Echtzeit. Damit jedes Mal, wenn Sie auf ein visuelles Element, klicken Sie auf einen Slicer zu verschieben, oder auf andere Weise interagieren zeigt Performance Analyzer die Ergebnisse sofort im Bereich an.

Verfügt im Bereich mehr Informationen als angezeigt werden kann, wird eine Bildlaufleiste angezeigt, um auf zusätzliche Informationen zu navigieren.

Jede Interaktion besitzt einen Abschnitt-Bezeichner im Bereich, beschreibt die Aktion, die die Protokolleinträge initiiert. In der folgenden Abbildung wurde die Interaktion an, dass die Benutzer einen Datenschnitt geändert.

![Abschnitte, die basierend auf den Typ der Interaktion](media/desktop-performance-analyzer/performance-analyzer-04.png)

Jedes visuellen Elements Protokollinformationen umfasst die Zeit (Dauer) um die folgenden Kategorien von Aufgaben ausführen:

* **DAX-Abfrage** – Wenn eine DAX-Abfrage benötigt wurde, ist dies die Zeit zwischen der Visualisierung, die die Abfrage gesendet und für Analysis Services werden die Ergebnisse zurückgegeben.
* **Visuelle Darstellung** -erforderliche Zeit für das visuelle Element zum Zeichnen auf dem Bildschirm, einschließlich der Zeit erforderlich, um alle Images für Web oder die geocodierung abzurufen. 
* **Andere** -Zeit, die von der Visualisierung für Abfragen wird vorbereitet, warten auf andere visuelle Elemente abgeschlossen oder andere Verarbeitung im Hintergrund ausführen erforderlich.

![Elemente von Protokollinformationen](media/desktop-performance-analyzer/performance-analyzer-06.png)

Nachdem Sie Berichtselemente Sie mit der Performance Analyzer messen möchten Interaktion haben, können Sie wählen die **beenden** Schaltfläche. Informationen zur Leistung bleibt nach der Auswahl im Bereich **beenden** für die Sie analysieren.

Wählen Sie zum Löschen Sie die Informationen im Bereich Performance Analyzer **löschen**. Alle Informationen werden gelöscht, und wird nicht gespeichert werden, bei der Auswahl **löschen**. Finden Sie im nächsten Abschnitt erfahren, wie Informationen in Protokollen gespeichert. 

## <a name="refreshing-visuals"></a>Aktualisieren von visuellen Elementen

Sie können auswählen, **Aktualisieren von visuellen Elementen** im Bereich "Performance Analyzer" alle Visualisierungen auf der aktuellen Seite des Berichts aktualisieren, und dadurch Performance Analyzer, die Informationen über alle visuellen Elemente zu erfassen.

Sie können auch einzelne visuelle Elemente aktualisieren. Wenn Performance Analyzer aufzeichnet, klicken Sie auf **Aktualisieren dieses visuelle Element** finden Sie in der oberen rechten Ecke jedes visuellen Elements, um diese Visualisierung zu aktualisieren und die Leistungsinformationen zu erfassen.

![Aktualisieren Sie ein einzelnes visuelles Element](media/desktop-performance-analyzer/performance-analyzer-07.png)

## <a name="saving-performance-information"></a>Speichern von Leistungsdaten

Sie können Informationen zur Performance Analyzer erstellt einen Bericht speichern, durch Auswählen der **exportieren** Schaltfläche. Auswählen von **exportieren** erstellt Sie eine JSON-Datei mit Informationen aus dem Bereich Performance Analyzer. 

![Speichern Sie die Protokolldatei für die Leistungsanalyse](media/desktop-performance-analyzer/performance-analyzer-05.png)


## <a name="next-steps"></a>Nächste Schritte
Weitere Informationen zu **Power BI Desktop** und den ersten Schritten finden Sie in den folgenden Artikeln.

* [Was ist Power BI Desktop?](desktop-what-is-desktop.md)
* [Übersicht zu Abfragen mit Power BI Desktop](desktop-query-overview.md)
* [Datenquellen in Power BI Desktop](desktop-data-sources.md)
* [Verbinden mit Daten in Power BI Desktop](desktop-connect-to-data.md)
* [Strukturieren und Kombinieren von Daten mit Power BI Desktop](desktop-shape-and-combine-data.md)
* [Allgemeine Abfrageaufgaben in Power BI Desktop](desktop-common-query-tasks.md)   

