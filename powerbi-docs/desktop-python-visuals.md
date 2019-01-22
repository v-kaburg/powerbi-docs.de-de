---
title: Erstellen von Power BI-Visualisierungen mithilfe von Python
description: Erstellen von Power BI-Visualisierungen mithilfe von Python
author: otarb
manager: rajatt
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 06/18/2018
ms.author: otarb
LocalizationGroup: Create reports
ms.openlocfilehash: 7390f029144e5cb37830921071ad5c2c678b2d4d
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/15/2019
ms.locfileid: "54275477"
---
# <a name="create-power-bi-visuals-using-python"></a>Erstellen von Power BI-Visualisierungen mithilfe von Python
Mit **Power BI Desktop** können Sie **Python** zum Visualisieren Ihrer Daten verwenden.

## <a name="install-python"></a>Python installieren
**Power BI Desktop** enthält die **Python**-Engine nicht und stellt sie weder bereit noch installiert es sie. Um Python-Skripts in **Power BI Desktop** auszuführen, müssen Sie **Python** separat auf Ihrem lokalen Computer installieren. **Python** können Sie an vielen Stellen im Internet kostenlos herunterladen und installieren, u.a. von der [Offiziellen Python-Downloadseite](https://www.python.org/) und aus [Anaconda](https://anaconda.org/anaconda/python/). Die aktuelle Version der Python-Skripterstellung in Power BI Desktop unterstützt Unicode-Zeichen ebenso wie Leerzeichen (leere Zeichen) im Installationspfad.

## <a name="enable-python-visuals"></a>Aktivieren von visuellen Python-Elementen
Zum Aktivieren von Python-Visualisierungen wählen Sie **Datei > Optionen und Einstellungen > Optionen** aus. Stellen Sie anschließend sicher, dass auf der Seite **Optionen** im Abschnitt **Python-Skripterstellung** des Fensters **Optionen** die lokale Installation von Python angegeben ist, wie in der folgenden Abbildung dargestellt. In der folgenden Abbildung lautet der lokale Installationspfad von Python **C:\Python27**. Dieser Pfad ist im Textfeld explizit angegeben. Achten Sie darauf, dass der dort angezeigte Pfad die lokale Installation von Python, die von **Power BI Desktop** verwendet werden soll, richtig wiedergibt.
   
   ![](media/desktop-python-visuals/python-visuals-1.png)

Nachdem Sie Ihre Installation von Python angegeben haben, können Sie mit dem Erstellen von Python-Visualisierungen beginnen.

## <a name="create-python-visuals-in-power-bi-desktop"></a>Erstellen von visuellen Python-Elementen in Power BI Desktop
1. Wählen Sie zum Hinzufügen eines visuellen Python-Elements das Symbol **visuelle Python-Elemente** im Bereich **Visualisierung** aus, wie im folgenden Bild dargestellt.
   
   ![](media/desktop-python-visuals/python-visuals-2.png)

   Wenn Sie einem Bericht ein visuelles Python-Element hinzufügen, führt **Power BI Desktop** Folgendes aus:
   
   - Auf der Berichtzeichnungsfläche wird ein Platzhalterbild für ein visuelles Python-Element angezeigt.
   
   - Am unteren Rand des mittleren Bereichs wird der **Python-Skript-Editor** angezeigt.
   
   ![](media/desktop-python-visuals/python-visuals-3.png)

2. Fügen Sie anschließend wie in jeder anderen **Power BI Desktop**-Visualisierung dem Abschnitt **Werte** im Bereich **Felder** Felder hinzu, die im Python-Skript verwendet werden sollen. 
    
    Für Ihr Python-Skript sind nur Felder verfügbar, die dem Bereich **Felder** hinzugefügt wurden. Sie können im Bereich **Felder** neue Felder hinzufügen und nicht benötigte Felder entfernen, während Sie das Python-Skript im **Python-Skript-Editor von Power BI Desktop** bearbeiten. **Power BI Desktop** erkennt automatisch, welche Felder hinzugefügt oder entfernt wurden.
   
   > [!NOTE]
   > Der Standardaggregationstyp für visuelle Python-Elemente lautet *Nicht zusammenfassen*.
   > 
   > 
   
3. Jetzt können Sie die Daten verwenden, die Sie zum Erstellen einer Zeichnung ausgewählt haben. 

    Während Sie Felder auswählen, generiert der **Python-Skript-Editor** unterstützenden Python-Skript-Bindungscode, ausgehend von Ihrer Auswahl im grauen Abschnitt im oberen Bereich des Editors. Wenn Sie zusätzliche Felder auswählen oder entfernen, wird im Python-Skript-Editor automatisch Unterstützungscode entsprechend generiert bzw. entfernt.
   
   Im Beispiel in der folgenden Abbildung wurden drei Felder ausgewählt: „hp“, „gear“ und „drat“. Aufgrund dieser Auswahl generiert der Python-Skript-Editor den folgenden Bindungscode:
   
   * Ein Datenrahmen mit dem Namen **dataset** wurde erstellt.
     * Dieser Datenrahmen besteht aus den vom Benutzer ausgewählten Feldern.
   * Die Standardaggregation lautet *Nicht zusammenfassen*.
   * Ähnlich wie bei Tabellenvisualisierungen werden Felder gruppiert, und doppelte Zeilen werden nur einmal angezeigt.
   
   ![](media/desktop-python-visuals/python-visuals-4.png)
   
   > [!TIP]
   > In bestimmten Fällen sind Gruppierungen möglicherweise nicht erwünscht, oder es sollen alle Zeilen, einschließlich doppelter Zeilen, angezeigt werden. In diesem Fall können Sie dem Dataset ein Indexfeld hinzufügen, sodass alle Zeilen als eindeutig betrachtet werden und keine Gruppierung erfolgt.
   > 
   > 
   
   Der generierte Datensatz wird als **Dataset** bezeichnet, und Sie können auf die ausgewählten Spalten über ihre Namen zugreifen. Greifen Sie beispielsweise auf das Feld „gear“ zu, indem Sie *dataset["gear"]* in Ihr Python-Skript schreiben.

4. Mit dem Datenrahmen, der automatisch anhand der von Ihnen ausgewählten Felder generiert wurde, können Sie ein Python-Skript zum Erzeugen von Zeichnungen auf dem Python-Standardgerät schreiben. Wenn das Skript abgeschlossen ist, wählen Sie **Ausführen** auf der Titelleiste des **Python-Skript-Editors** aus (**Ausführen** befindet sich auf der rechten Seite der Titelleiste).
   
    Bei Auswahl von **Ausführen** identifiziert **Power BI Desktop** die Zeichnung und stellt sie im Zeichenbereich dar. Da der Vorgang in der lokalen Python-Installation ausgeführt wird, stellen Sie sicher, dass die erforderlichen Pakete installiert sind.
   
   **Power BI Desktop** zeichnet die Visualisierung neu, wenn eines der folgenden Ereignisse eintritt:
   
   * Wenn Sie auf der Titelleiste des **Python-Skript-Editors** **Ausführen** auswählen.
   * Bei jedem Ändern der Daten durch Aktualisieren, Filtern oder Hervorheben von Daten.

    Die folgende Abbildung zeigt ein Beispiel für den Korrelationszeichnungscode, wobei die Korrelationen zwischen Attributen verschiedener Autotypen gezeichnet werden.

    ![](media/desktop-python-visuals/python-visuals-5.png)

5. Um eine größere Ansicht der Visualisierungen zu erhalten, können Sie den **Python-Skript-Editor**minimieren. Selbstverständlich können Sie die Korrelationszeichnung wie andere Visuals in **Power BI Desktop** kreuzfiltern, indem Sie im Ringdiagrammvisual (im obigen Beispielbild die runden Visuals auf der rechten Seite) nur Sportwagen auswählen.

    ![](media/desktop-python-visuals/python-visuals-6.png)

6. Sie können auch das Python-Skript ändern, um die Visualisierung anzupassen, und die Funktionsvielfalt von Python nutzen, indem Sie dem Zeichenbefehl Parameter hinzufügen.

    Der ursprüngliche Zeichenbefehl lautete wie folgt:

    plt.matshow(dataset.corr('pearson'))

    Mit einigen Änderungen im Python-Skript lautet der Befehl jetzt folgendermaßen:

    plt.matshow(dataset.corr('kendall'))

    Das führt dazu, dass das visuelle Python-Element jetzt mithilfe des Kendall Tau-Rangkorrelationskoeffizienten gezeichnet wird, wie in der folgenden Abbildung dargestellt.

    ![](media/desktop-python-visuals/python-visuals-7.png)

    Wenn ein Python-Skript ausgeführt wird, das einen Fehler verursacht, wird das visuelle Python-Element nicht gezeichnet, und im Zeichenbereich wird eine Fehlermeldung angezeigt. Um Informationen zu dem Fehler zu erhalten, wählen Sie in der Fehlermeldung des visuellen Python-Elements **Details anzeigen** aus.

    ![](media/desktop-python-visuals/python-visuals-8.png)

    > **Sicherheit von Python-Skripts:** Visuelle Python-Elemente werden aus Python-Skripts erstellt, die Code mit Sicherheits- oder Datenschutzrisiken enthalten können. Wenn ein Benutzer ein visuelles Python-Element zum ersten Mal aufruft oder damit interagiert, wird eine Sicherheitswarnmeldung angezeigt. Aktivieren Sie visuelle Python-Elemente nur dann, wenn Sie dem Autor und der Quelle vertrauen, oder wenn Sie die zugehörigen Python-Skripts überprüft und nachvollzogen haben.
    > 
    > 

## <a name="known-limitations"></a>Bekannte Einschränkungen
Für visuelle Python-Elemente in **Power BI Desktop** ergeben sich einige Einschränkungen:

* Beschränkungen der Datengröße – die vom visuellen Python-Element zum Zeichnen verwendeten Daten sind auf 150.000 Zeilen beschränkt. Bei Auswahl von mehr als 150.000 Zeilen werden nur die oberen 150.000 Zeilen verwendet, und im Bild wird eine Meldung angezeigt.
* Beschränkung der Berechnungszeit: Wenn die Berechnung des visuellen Python-Elements 5 Minuten überschreitet, wird die Ausführung aufgrund der Zeitüberschreitung abgebrochen und eine Fehlermeldung angezeigt.
* Beziehungen – wie bei anderen Power BI Desktop-Visualisierungen tritt ein Fehler auf, wenn Datenfelder aus unterschiedlichen Tabellen ausgewählt werden, zwischen denen keine Beziehung definiert ist.
* Visuelle Python-Elemente werden aktualisiert, wenn Daten aktualisiert, gefiltert oder hervorgehoben werden. Das Bild selbst ist jedoch nicht interaktiv und kann nicht als Quelle für die Kreuzfilterung verwendet werden.
* Visuelle Python-Elemente reagieren auf das Hervorheben anderer Visualisierungen. Sie können jedoch nicht auf visuelle Python-Elemente klicken, um eine Kreuzfilterung anderer Elemente auszuführen.
* Nur auf dem Python-Standardanzeigegerät erzeugte Zeichnungen werden im Zeichenbereich ordnungsgemäß angezeigt. Verwenden Sie nicht explizit ein anderes Python-Anzeigegerät.

## <a name="next-steps"></a>Nächste Schritte
Betrachten Sie die folgenden zusätzlichen Informationen über Python in Power BI.

* [Ausführen von Python-Skripts in Power BI Desktop](desktop-python-scripts.md)
* [Verwenden einer externen Python-IDE mit Power BI](desktop-python-ide.md)

