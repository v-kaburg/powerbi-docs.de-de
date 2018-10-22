---
title: Barrierefreiheit in Power BI Desktop-Berichten
description: Funktionen und Vorschläge zum Erstellen von barrierefreien Power BI Desktop-Berichten
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 10/15/2018
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 525a7e45a804d9f82f4d06cf8618d790e140699f
ms.sourcegitcommit: b8461c1876bfe47bf71c87c7820266993f82c0d3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2018
ms.locfileid: "49336873"
---
# <a name="accessibility-in-power-bi-desktop-reports"></a>Barrierefreiheit in Power BI Desktop-Berichten
Power BI verfügt über Features, die von Personen mit Behinderungen für die leichtere Nutzung von und Interaktion mit Power BI-Berichten verwendet werden können. Zu diesen Funktionen gehört die Möglichkeit, einen Bericht mithilfe der Tastatur oder einer Sprachausgabe zu verwenden, den Fokus per TAB-Taste auf die verschiedenen Objekte auf einer Seite zu verlagern und Marker in Visualisierungen sinnvoll einzusetzen.

![Verwenden Sie für Linien- und Flächendiagramme verschiedene Marker, um die Barrierefreiheit zu verbessern](media/desktop-accessibility/accessibility_01.png)

> [!NOTE]
> Diese Barrierefreiheitsfunktionen stehen im **Power BI Desktop**-Release von Juni 2017 und späteren Releases zur Verfügung. Weitere Barrierefreiheitsfunktionen sind für kommende Releases geplant.
> 
> 

## <a name="consuming-a-power-bi-desktop-report-with-a-keyboard-or-screen-reader"></a>Nutzen eines Power BI Desktop-Berichts mit Tastatur oder Sprachausgabe
Ab der im September 2017 veröffentlichten Version von **Power BI Desktop** können Sie die **?**-Taste drücken, um ein Fenster anzuzeigen, in dem die in **Power BI Desktop** verfügbaren Tastenkombinationen für Barrierefreiheit beschrieben werden.

![Drücken Sie in Power BI Desktop die ?-Taste , um Tastenkombinationen für Barrierefreiheit anzuzeigen.](media/desktop-accessibility/accessibility_03.png)

Mit den Erweiterungen für die Barrierefreiheit können Sie einen Power BI-Bericht mithilfe der folgenden Techniken mit Tastatur oder Sprachausgabe nutzen:

Sie können den Fokus zwischen den Seitenregisterkarten von Berichten oder den Objekten auf einer bestimmten Berichtsseite mithilfe von **STRG+F6** wechseln.

* Verwenden der *TAB*-Taste oder der *PFEILTASTEN* zum Bewegen des Fokus von einer Berichtsseite zur nächsten, wenn sich der Fokus auf *Seitenregisterkarten des Berichts* befindet. Der Titel der Berichtsseite und ihr aktueller Auswahlstatus werden von der Sprachausgabe vorgelesen. Um die Berichtsseite zu laden, die aktuell den Fokus hat, können die *EINGABETASTE* oder die *LEERTASTE* verwendet werden.
* Wenn der Fokus auf einer geladenen *Berichtsseite* liegt, verwenden Sie die *TAB*-Taste, um den Fokus auf die einzelnen Objekte auf der Seite zu bewegen. Zu diesen zählen alle Textfelder, Bilder, Formen und Diagramme. Die Sprachausgabe liest den Typ des Objekts und sofern vorhanden den Titel und die Beschreibung des Objekts. 

Beim Navigieren zwischen Visuals können Sie weitere Aktionen ausführen. Sie können **ALT+UMSCHALT+F10** drücken, um den Visualheader zu fokussieren, der verschiedene Optionen enthält, dazu gehört das Sortieren, das Exportieren der Daten hinter dem Diagramm und der Fokusmodus. 

![Drücken Sie in Power BI Desktop ALT+UMSCHALT+F10, um den Fokus auf den Visualheader zu verschieben.](media/desktop-accessibility/accessibility_08.png)

Sie können **ALT+UMSCHALT+F11** drücken, um eine barrierefreie Version des Fensters *Daten anzeigen* zu öffnen. Dadurch können Sie die im Visual verwendeten Daten in einer HTML-Tabelle untersuchen, und dabei die gleichen Tastenkombinationen verwenden, die Sie normalerweise mit der Sprachausgabe verwenden. 

![Drücken Sie in Power BI Desktop ALT+UMSCHALT+F11, um eine barrierefreie Version des Fensters „Daten anzeigen“ für ein Visual zu öffnen.](media/desktop-accessibility/accessibility_04.png)

> [!NOTE]
> Das Feature „Daten anzeigen“ ist nur über diese Tastenkombination für die Sprachausgabe verfügbar. Wenn Sie das Fenster „Daten anzeigen“ über die Option im Visualheader öffnen, kann die Sprachausgabe nicht darauf zugreifen.

Ab dem **Power BI Desktop**-Release von Juli 2018 verfügen Slicer auch über integrierte Barrierefreiheitsfunktionen. Wenn Sie einen Slicer auswählen, verwenden Sie zum Anpassen des Werts die STRG- und die NACH-RECHTS-TASTE, um die verschiedenen Steuerelemente im Slicer zu durchlaufen. Wenn Sie z.B. am Anfang die STRG- und die NACH-RECHTS-TASTE drücken, befindet sich der Fokus auf dem Radierer. Das Drücken der LEERTASTE entspricht dem Klicken auf die Schaltfläche „Radierer“, wodurch alle Werte im Slicer gelöscht werden. 

Mithilfe der TABULATORTASTE können Sie alle Steuerelemente in einem Slicer durchlaufen. Wenn der Radierer aktiv ist, verschieben Sie den Fokus durch Drücken der TABULATORTASTE auf die Dropdown-Schaltfläche. Wenn Sie die TABULATORTASTE erneut drücken, verschieben Sie den Fokus auf den ersten Slicerwert (sofern mehrere Werte für den Slicer vorhanden sind, z.B. ein Bereich). 

![Drücken Sie in Power BI Desktop die STRG- und die NACH-RECHTS-TASTE, um Elemente oder Werte in einem Slicer anzupassen. Drücken Sie die LEERTASTE, um ein Element auszuwählen und seinen Wert anzupassen.](media/desktop-accessibility/accessibility_07.png)

Diese zusätzlichen Barrierefreiheitsfunktionen wurden entwickelt, damit Benutzer Power BI-Berichte per Sprachausgabe und Tastaturnavigation umfassend verwenden können.

## <a name="tips-for-creating-accessible-reports"></a>Tipps zum Erstellen barrierefreier Berichte
Die folgenden Tipps können Ihnen beim Erstellen von **Power BI Desktop**-Berichten mit besserer Barrierefreiheit helfen.

### <a name="general-tips-for-accessible-reports"></a>Allgemeine Tipps zum Erstellen barrierefreier Berichte

* Aktivieren Sie für **Liniendiagramm**-, **Flächendiagramm**- und **Kombinationsdiagramm**-Visuals sowie für **Punktdiagramm**- und **Blasendiagramm**-Visuals Marker, und verwenden Sie für jede Linie eine andere *Markerform*.
  
  * Um *Marker* zu aktivieren, wählen Sie im Bereich **Visualisierungen** den Abschnitt **Format** aus, erweitern Sie den Abschnitt **Formen**, scrollen Sie dann nach unten bis zum Ein-/Ausschalter **Marker**, und schalten Sie ihn *Ein*.
  * Wählen Sie anschließend im Dropdownfeld im Abschnitt **Formen** den Namen jeder Linie (oder Fläche bei einem **Flächendiagramm**) aus. Unterhalb des Dropdownfelds können Sie anschließend viele Aspekte des für die ausgewählte Linie verwendeten Markers anpassen, einschließlich dessen Form, Farbe und Größe.
  
  ![Verwenden Sie für Linien- und Flächendiagramme verschiedene Marker, um die Barrierefreiheit zu verbessern](media/desktop-accessibility/accessibility_01.png)
  
  * Die Verwendung einer anderen *Markierungsform* für jede Linie macht es den Nutzern des Berichts leichter, die Linien (oder Flächen) voneinander zu unterscheiden.
* Verwenden Sie zum Übermitteln von Informationen nicht nur Farbmarkierungen. Zusätzlich zur Verwendung von Formen in Linien- und Punktdiagrammen sollten Sie sich nicht auf die bedingte Formatierung verlassen, um Einblicke in Tabellen und Matrizen zu gewähren. 
* Wählen Sie eine Sortierreihenfolge für jedes Visual in Ihrem Bericht mit Bedacht aus. Wenn Benutzer der Sprachausgabe zu den Daten hinter dem Diagramm navigieren, wird die gleiche Sortierreihenfolge wie beim Visual verwendet.
* Wählen Sie im Designkatalog ein *Design* mit hohem Kontrast aus, das für Farbenblinde geeignet ist, und importieren Sie es mithilfe der [**Design**-Vorschaufunktion](desktop-report-themes.md).
* Geben Sie zu jedem Objekt in einem Bericht *Alternativtext* an. Auf diese Weise stellen Sie sicher, dass Personen, die Ihren Bericht verwenden, verstehen, was Sie mit einem visuellen Element kommunizieren möchten, selbst wenn sie das visuelle Element, das Bild, die Form oder das Textfeld nicht sehen können. Sie können zu jedem Objekt in einem *Power BI Desktop*-Bericht **Alternativtext** angeben, indem Sie das Objekt (wie etwa ein Visual, eine Form usw.) auswählen und im Bereich **Visualisierungen** den Bereich **Format** auswählen, **Allgemein** erweitern, dann nach unten scrollen und das Textfeld **Alternativtext** ausfüllen.
  
  ![Alternativtext kann für jedes Objekt in einem Bericht im Feld „Visualisierungen > Format > Allgemein > Alternativtext“ hinzugefügt werden.](media/desktop-accessibility/accessibility_02.png)
* Stellen Sie sicher, dass in Ihren Berichten ein ausreichender Kontrast zwischen Text- und Hintergrundfarben vorhanden ist. Es gibt verschiedene Tools, die Sie zum Überprüfen der Farben in Ihrem Bericht verwenden können, z.B. [Colour Contrast Analyser](https://developer.paciellogroup.com/resources/contrastanalyser/). 
* Verwenden Sie Textgrößen und -schriftarten, die leicht lesbar sind. Kleine Textgrößen oder -schriftarten, die schwierig zu lesen sind, verringern die Barrierefreiheit.
* Schließen Sie in alle Visuals einen Titel, Achsenbezeichnungen und Datenbezeichnungen ein.
* Verwenden Sie aussagekräftige Titel für alle Seiten des Berichts.
* Vermeiden Sie, wenn möglich, die Verwendung dekorativer Formen und Bilder im Bericht, da diese in der Registerkartenreihenfolge des Berichts enthalten sind. Wenn Sie dekorative Objekte in Ihren Bericht einfügen müssen, aktualisieren Sie den alternativen Text des Objekts, um Benutzer der Sprachausgabe wissen zu lassen, dass es zur Dekoration dient.

### <a name="arranging-items-in-field-buckets"></a>Anordnen von Elementen in Feld-Buckets
Ab der Oktober 2018-Version von **Power BI Desktop** kann mit der Tastatur im **Felder**-Bereich navigiert werden, und der Bereich interagiert auch mit Sprachausgaben. 

Um den Prozess der Erstellung von Berichten mit Sprachausgaben zu verbessern, ist ein Kontextmenü verfügbar, um das Verschieben von Feldern innerhalb des Bereichs nach oben oder unten in der Liste **Felder** zu ermöglichen bzw. das Verschieben des Felds in andere Bereiche, wie z. B. **Legende**, **Wert** oder andere.

![Mit dem Kontextmenü im Bereich „Felder“ können Sie Felder nach oben, unten oder in einen anderen Bereich verschieben.](media/desktop-accessibility/accessibility_09.png)

## <a name="high-contrast-support-for-reports"></a>Unterstützung für hohen Berichtskontrast

Wenn Sie unter Windows einen der Modi für hohen Kontrast verwenden, gelten die ausgewählten Einstellungen und die Palette auch für Berichte in **Power BI Desktop**. 

![Windows-Einstellungen für hohen Kontrast](media/desktop-accessibility/accessibility_05.png)

**Power BI Desktop** erkennt automatisch, welches Design für hohen Kontrast unter Windows verwendet wird, und wendet diese Einstellungen auf Ihre Berichte an. Der Bericht ist auch nach der Veröffentlichung im Power BI-Dienst oder einem anderen Dienst in diesen kontrastreichen Farben gehalten.

![Windows-Einstellungen für hohen Kontrast](media/desktop-accessibility/accessibility_05b.png)

Der Power BI-Dienst versucht auch, die für Windows ausgewählten Kontrasteinstellungen zu erkennen. Wie effektiv und genau diese Erkennung ist, hängt jedoch von dem Browser ab, in dem der Power BI-Dienst verwendet wird. Wenn Sie das Design im Power BI-Dienst manuell festlegen möchten, klicken Sie auf **Ansicht > Farben mit hohem Kontrast**, und wählen Sie dann das Design aus, das Sie auf den Bericht anwenden möchten.

![Festlegen eines hohen Kontrasts im Power BI-Dienst](media/desktop-accessibility/accessibility_06.png)

In **Power BI Desktop** spiegeln einige Bereiche, z.B. die Felder **Visualisierungen** und **Felder**, nicht die Auswahl des Windows-Farbschemas mit hohem Kontrast wider.


## <a name="considerations-and-limitations"></a>Überlegungen und Einschränkungen
Es gibt einige bekannte Probleme und Einschränkungen bei den Barrierefreiheitsfeatures. Diese werden in der folgenden Liste beschrieben:

* Wenn Sie die Sprachausgabe mit **Power BI Desktop** verwenden, erzielen Sie die bestmögliche Leistung, wenn Sie die Sprachausgabe Ihrer Wahl starten, bevor Sie Dateien in Power BI Desktop öffnen.
* Wenn Sie die Sprachausgabe von Microsoft verwenden, gibt es einige Einschränkungen beim Anzeigen von Daten als HTML-Tabelle.

## <a name="next-steps"></a>Nächste Schritte
* [Verwenden von Berichtdesigns in Power BI Desktop (Vorschau)](desktop-report-themes.md)

