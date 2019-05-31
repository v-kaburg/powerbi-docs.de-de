---
title: 'Tutorial: Erstellen eines Machine Learning-Modells in Power BI (Vorschau)'
description: In diesem Tutorial erstellen Sie ein Machine Learning-Modell in Power BI.
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.custom: connect-to-services
ms.topic: tutorial
ms.date: 03/29/2019
ms.author: davidi
LocalizationGroup: Connect to services
ms.openlocfilehash: 611d6f6c923e6cb68af94840c4266a0b6dee7651
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2019
ms.locfileid: "61406746"
---
# <a name="tutorial-build-a-machine-learning-model-in-power-bi-preview"></a>Tutorial: Erstellen eines Machine Learning-Modells in Power BI (Vorschau)

In diesem Tutorial Artikel verwenden Sie **automatisierte Machine Learning** erstellen und eine binäre Vorhersage-Modell in Power BI anwenden. Das Lernprogramm enthält Anleitungen zum Erstellen eines Power BI-Datenfluss, und mit den Entitäten im Datenfluss zu trainieren und überprüfen ein Machine learning-Modell direkt in Power BI definiert. Klicken Sie dann verwenden wir das Modell für die Bewertung, um vorhersagen zu generieren.

Zunächst erstellen Sie eine binäre Vorhersage Machine learning-Modell, um vorherzusagen, die Absicht Kauf von onlinekäufern, basierend auf einem Satz ihrer onlinesitzung Attribute. Ein Benchmark-Machine Learning-Dataset wird für diese Übung verwendet. Nachdem ein Modell trainiert ist, generiert Power BI automatisch eine Erläuterung der Modellergebnisse Überprüfungsbericht. Sie können dann überprüfen Sie den Überprüfungsbericht und das Modell anwenden, um Ihre Daten für die Bewertung.

In diesem Lernprogramm umfasst folgende Schritte aus:

> [!div class="checklist"]
> * Erstellen Sie einen Datenfluss mit der Eingabedaten
> * Erstellen und Trainieren von Machine Learning-Modellen
> * Überprüfen Sie den Modell-Überprüfungsbericht
> * Das Modell auf eine Entität Datenfluss anwenden
> * Verwenden die bewertete Ausgabe aus dem Modell in Power BI-Berichten

## <a name="create-a-dataflow-with-the-input-data"></a>Erstellen Sie einen Datenfluss mit der Eingabedaten

Der erste Teil dieses Lernprogramms ist die Erstellung von einem Datenfluss mit Eingabedaten. Dieser Prozess dauert einige Schritte, wie in den folgenden Abschnitten gezeigt Abrufen von Daten ab.

### <a name="get-data"></a>Daten abrufen

Der erste Schritt beim Erstellen von eines Datenfluss ist Ihre Datenquellen bereit. In unserem Fall verwenden wir ein Machine Learning-Dataset aus einer Reihe von online-Sitzungen, von denen einige in einen Kauf letztendlich zu. Das Dataset enthält einen Satz von Attributen zu diesen Sitzungen, die wir für das Trainieren des Modells verwenden.

Sie können das Dataset von der UC Irvine-Website herunterladen.  Wir haben auch diesem verfügbar sind, im Rahmen dieses Tutorials, mit dem folgenden Link: [online_shoppers_intention.csv](https://raw.githubusercontent.com/santoshc1/PowerBI-AI-samples/master/Tutorial_AutomatedML/online_shoppers_intention.csv).

### <a name="create-the-entities"></a>Erstellen von Entitäten

Um die Entitäten in Ihrem Dataflow zu erstellen, melden Sie sich beim Power BI-Dienst an, und navigieren Sie zu einem Arbeitsbereich Ihrer dedizierten Kapazität, in dem die KI-Vorschau aktiviert ist.

Wenn Sie bereits über einen Arbeitsbereich haben, können Sie erstellen dazu **Arbeitsbereiche** in in der Power BI-Dienst, und wählen im linken Navigationsmenü **app-Arbeitsbereich erstellen** am unteren Rand der Bereich, wird angezeigt. Daraufhin wird einen Bereich auf der rechten Seite Details des Arbeitsbereichs eingeben. Geben Sie einen Arbeitsbereichsnamen, und wählen Sie **erweitert**. Vergewissern Sie sich, dass der Arbeitsbereich wird verwendet, dedizierte Kapazität, die mit dem Optionsfeld und sie eine dedizierte Kapazität-Instanz zugewiesen ist, die die AI (Vorschauversion) aktiviert ist. Klicken Sie auf **Speichern**.

![Arbeitsbereich erstellen](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-01.png)

Der Arbeitsbereich erstellt wurde, wählen Sie **überspringen** in der unteren rechten Rand der Willkommensseite, wie in der folgenden Abbildung dargestellt.

![Überspringen Sie, wenn Sie einen Arbeitsbereich verfügen](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-02.png)

Wählen Sie die **Datenflüsse (Vorschau)** Registerkarte. Wählen Sie die **erstellen** oben rechts neben dem Arbeitsbereich, und wählen Sie dann die Schaltfläche **Datenfluss**.

![Erstellen von Datenfluss](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-03.png)

Wählen Sie **Neue Entitäten hinzufügen** aus. Dadurch wird eine **Power Query** -Editor in den Browser.

![Hinzufügen einer neuen Entität](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-04.png)

Wählen Sie **Text/CSV-Datei** als eine Datenquelle angezeigt werden soll, in der folgenden Abbildung.

![Ausgewählten Text/CSF-Datei](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-05.png)

In der **Herstellen einer Verbindung mit einer Datenquelle** , die neben angezeigt wird, fügen Sie den folgenden Link in der *online_shoppers_intention.csv* in die **Dateipfad oder URL** Feld, und wählen Sie dann auf  **Nächste**.

`https://raw.githubusercontent.com/santoshc1/PowerBI-AI-samples/master/Tutorial_AutomatedML/online_shoppers_intention.csv`

![Dateipfad](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-06.png)

Die Power Query-Editor zeigt eine Vorschau der Daten aus der CSV-Datei. Wählen Sie **Tabelle transformieren** in dem Befehl Menüband, und wählen Sie dann **erste Zeile als Header verwenden** aus dem Menü, das angezeigt wird. Dadurch wird die _höher gestufte Header_ Schritte der Abfrage in der **angewendeten Schritte** Abschnitt auf der rechten Seite des Bildschirms. Sie können die Abfrage einen aussagekräftigeren Namen umbenennen, durch Ändern des Werts in der **Namen** Feld finden Sie im rechten Bereich. Beispielsweise können Sie ändern, Namen der Abfrage in _Online Besucher_.

![Ändern Sie in einen Anzeigenamen](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-07.png)

Einige die Attribut-Datentypen in diesem Dataset sind _numerischen_ oder _booleschen_, obwohl diese möglicherweise als Zeichenfolgen nach interpretiert werden **Power Query**. Wählen Sie das Attribut Type-Symbol am oberen Rand der einzelnen Spaltenüberschriften so ändern Sie die nachfolgend aufgeführten, auf die folgenden Spalten:

* **Dezimalzahl:** Administrative_Duration; Informational_Duration; ProductRelated_Duration; BounceRates; ExitRates; PageValues; SpecialDay
* **True oder False:** Wochenende; Umsatz

![Ändern des Datentyps](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-08.png)

Die **binäre Vorhersage** Modell Trainieren Sie erfordert ein boolesches Feld als eine Bezeichnung, die die Ergebnisse aus der letzten Beobachtungen zu identifizieren. In diesem Dataset das _Umsatz_ -Attribut gibt an, Kauf, und dieses Attribut ist bereits als einen booleschen Wert zur Verfügung. Wir müssen also keine berechnete Spalte für die Bezeichnung hinzufügen. In anderen Datasets müssen Sie möglicherweise vorhandene Bezeichnungsattribute in einer booleschen Spalte zu transformieren.

Wählen Sie die **Fertig** , um Power Query-Editor zu schließen. Daraufhin wird eine Entitätenliste mit die _Online Besucher_ Daten, die wir hinzugefügt. Wählen Sie **speichern** in der oberen rechten Ecke, geben Sie einen Namen für den Datenfluss aus, und wählen Sie dann **speichern** klicken Sie im Dialogfeld wie in der folgenden Abbildung dargestellt.

![Speichern Sie den Datenfluss](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-09.png)

### <a name="refresh-the-dataflow"></a>Aktualisieren des Dataflows

Speichern der Datenfluss führt eine Benachrichtigung angezeigt wird die besagt, dass es sich bei Ihrem Datenfluss gespeichert wurde. Wählen Sie **jetzt aktualisieren** zum Erfassen von Daten aus der Quelle in den Datenfluss verwendet.

![Jetzt aktualisieren](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-10.png)

Wählen Sie **Schließen** in der oberen rechten Ecke aus, und warten Sie, bis die Aktualisierung des Dataflows abgeschlossen ist.

Sie können auch Ihre Datenfluss aktualisieren, mit der **Aktionen** Befehle. Der Datenfluss zeigt den Zeitstempel an, wenn die Aktualisierung abgeschlossen ist.

![Zeitstempel der Aktualisierung](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-11.png)

## <a name="create-and-train-a-machine-learning-model"></a>Erstellen und Trainieren von Machine Learning-Modellen

Wählen Sie den Datenfluss aus, nachdem die Aktualisierung abgeschlossen wurde. Wählen Sie zum Hinzufügen eines Machine Learning-Modells die **Anwenden von ML-Modell** Schaltfläche der **Aktionen** Liste für die Basis-Entität, die Ihr Training Daten und Bezeichnung enthält, und wählen Sie dann **Hinzufügen einer Machine Learning-Modells**.

![Machine Learning-Modell hinzufügen](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-12.png)

Der erste Schritt zum Erstellen von unseren Machine Learning-Modell wird zum Identifizieren der historischen Daten, einschließlich das Bezeichnungsfeld an, dem Sie vorhersagen möchten. Das Modell wird von Erkenntnisse aus diesen Daten erstellt werden.

Wenn das Dataset, das wir verwenden, dies ist die **Umsatz** Feld. Wählen Sie **Umsatz** als Wert für "Historische Ergebnisfeld" und wählen Sie dann **Weiter**.

![Wählen Sie Verlaufsdaten aus](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-13.png)

Als Nächstes müssen wir den Typ der Machine learning-Modell zum Erstellen auswählen. Powerbi analysiert die Werte in das Feld für Verlauf Ergebnis, das Sie angegeben haben und die Typen von Machine Learning-Modelle, die erstellt werden können, um vorherzusagen, dieses Feld vorgeschlagen.

Da wir ein binäres Ergebnisses Vorhersage sind der gibt an, ob ein Benutzer einen Kauf oder nicht tätigt, in diesem Fall wählen Sie **binäre Vorhersage** für den Typ des Modells ein, und wählen Sie dann neben.

![Binäre Vorhersage ausgewählt](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-14.png)

Als Nächstes wird Power BI ist eine vorläufige Überprüfung der Daten und schlägt die Eingaben, die das Modell verwenden können. Sie haben die Möglichkeit zum Anpassen der Felder für die Eingabe für das Modell verwendet. Wählen Sie in unserem geordneten Dataset um alle Felder auszuwählen, das Kontrollkästchen neben dem Namen der Entität ein. Wählen Sie **Weiter** , die Eingaben zu akzeptieren.

![Aktivieren Sie das nächste Kontrollkästchen](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-15.png)

Im letzten Schritt müssen wir bieten einen Namen für das Modell sowie die benutzerfreundlichen Beschriftungen für die Ergebnisse im automatisch generierten Bericht verwendet werden, die die Ergebnisse die modellvalidierung zusammengefasst werden. Als Nächstes haben wir das Modell benennen _Kauf Absicht Vorhersage_, sowie die Bezeichnungen "true" und "false" als _Kauf_ und _Nein-Purchase-_ . Klicken Sie auf **Speichern**.

![Speichern Sie das Modell](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-16.png)

Machine Learning-Modell ist jetzt bereit für das Training. Wählen Sie **jetzt aktualisieren** zu trainieren des Modells.

![Jetzt aktualisieren](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-17.png)

Des trainingsprozesses wird zunächst sampling und Ihre historischen Daten normalisieren und Teilen Ihr Dataset in zwei neue Entitäten *Kauf Absicht Vorhersagen Trainingsdaten* und *Kauf Absicht Vorhersage testen Daten*.

Abhängig von der Größe des Datasets kann das Training zu ein paar Minuten, ein paar Stunden dauern. An diesem Punkt sehen Sie das Modell in der **Machine learning-Modelle** Registerkarte Datenfluss. Die _bereit_ Status gibt an, dass das Modell wurde in die Warteschlange für das Training oder befindet sich unter dem Training.

![Bereit für das training](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-18.png)

Während das Modell trainieren ist, wird Sie nicht anzeigen oder bearbeiten den Datenfluss. Sie können bestätigen, dass das Modell wird trainiert und validiert, über den Status des Datenflusses. Dies wird als eine datenaktualisierung ausgeführt, in der **Datenflüsse** Registerkarte des Arbeitsbereichs.

![Im Prozess](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-19.png)

Nachdem das Modelltraining abgeschlossen ist, zeigt den Datenfluss eine aktualisierte Aktualisierungszeit an. Sie können bestätigen, dass das Modell trainiert ist, navigieren Sie zu, die **Machine learning-Modelle** Registerkarte im Datenfluss. Das Modell, das Sie erstellt haben, sollte Status anzeigen **angewiesen** und **Trainiertes letzte** Zeit sollte jetzt aktualisiert werden.

![Letzte trainiert](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-20.png)

## <a name="review-the-model-validation-report"></a>Überprüfen Sie den Modell-Überprüfungsbericht

Zum Überprüfen des Berichts für die Modell-Überprüfung im der **Machine Learning-Modellen, s** festlegen, ob die **Leistungsbericht anzeigen und das Modell anwenden** Schaltfläche der **Aktionen** Spalte für das Modell . Dieser Bericht zeigt, wie Ihr Machine Learning-Modell wahrscheinlich durchführen wird.

In der **Modellleistung** Seite des Berichts wählen **wichtige Einflussfaktoren** oberen prädiktoren für Ihr Modell an. Sie können auswählen, eine der prädiktoren angezeigt, wie die Ergebnis-Verteilung mit der diese Vorhersage verbunden werden sollen.

![Leistung des Modells](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-21.png)

Sie können die **Wahrscheinlichkeitsschwellenwert** Slicer auf der Seite für die Leistung des Modells aus, um den Einfluss auf die Genauigkeit und Rückruf für das Modell zu untersuchen.

![Wahrscheinlichkeitsschwellenwert](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-22.png)

Die anderen Seiten des Berichts werden die statistischen Leistungsmetriken für das Modell beschrieben.

Der Bericht enthält auch eine Schulungsdetails-Seite, die beschreibt die verschiedenen Iterationen, die ausgeführt wurden, wie die Features aus den Eingaben, und die hyperparameter für das endgültige Modell verwendet extrahiert wurden.

## <a name="apply-the-model-to-a-dataflow-entity"></a>Das Modell auf eine Entität Datenfluss anwenden

Wählen Sie die **übernehmen Modell** Schaltfläche am oberen Rand des Berichts auf dieses Modell aufgerufen wird, wenn der Datenfluss aktualisiert wird. In der **übernehmen** Dialogfeld können Sie angeben, die Zielentität, die Quelldaten verfügt, auf dem das Modell angewendet werden soll.

![Modell anwenden](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-23.png)

Wenn Sie dazu aufgefordert werden, müssen Sie **aktualisieren** dem Datenfluss eine Vorschau der Ergebnisse des Modells anzeigen.

Das Modell anwenden, wird eine neue Entität mit dem Suffix erstellt **erweitert < Model_name >** angefügt wird, auf die Entität, zu dem Sie das Modell angewendet. In unserem Fall die Anwendung des Modells, das die **OnlineShoppers** Entität erstellt **OnlineShoppers bereichert Kauf Absicht Vorhersage**, wozu die vorhergesagte Ausgabe aus dem Modell.

Anwenden eines Modells für binäre Vorhersage fügt drei Spalten mit vorhergesagte Ergebnis Wahrscheinlichkeits-Score und die wichtigsten Einflussfaktoren für datensatzspezifischen für die Vorhersage, jeweils mit dem angegebenen Spaltennamen als Präfix.

![Drei Spalten vom Ergebnis](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-24.png)

Aufgrund eines bekannten Problems sind die bewerteten Ausgabespalten in der erweiterten Entität nur aus Power BI Desktop zugegriffen werden kann. Um diese im Dienst der Vorschau anzuzeigen, müssen Sie eine spezielle Vorschau-Entität verwenden.

Die Datenfluss-Aktualisierung abgeschlossen ist, wählen Sie die **OnlineShoppers bereichert Kauf Absicht Vorhersage Vorschau** Entität, die die Ergebnisse anzuzeigen.

![Anzeigen der Ergebnisse](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-25.png)

## <a name="using-the-scored-output-from-the-model-in-a-power-bi-report"></a>Verwenden die bewertete Ausgabe aus dem Modell in Power BI-Berichten

Um die bewerteten aus Ihrer Machine learning-Modell zu verwenden, können Sie aus dem Power BI Desktop Ihre Datenfluss Verbinden mit dem Connector Datenflüsse. Die **OnlineShoppers bereichert Kauf Absicht Vorhersage** Entität kann jetzt verwendet werden, um die Vorhersagen aus Ihrem Modell in Power BI-Berichte zu integrieren.

## <a name="next-steps"></a>Nächste Schritte

In diesem Tutorial haben Sie erstellt und eine binäre Vorhersage-Modell in Power BI mit diesen Schritten angewendet:

* Erstellen Sie einen Datenfluss mit der Eingabedaten
* Erstellen und Trainieren von Machine Learning-Modellen
* Überprüfen Sie den Modell-Überprüfungsbericht
* Das Modell auf eine Entität Datenfluss anwenden
* Verwenden die bewertete Ausgabe aus dem Modell in Power BI-Berichten

Weitere Informationen zur Automatisierung von Machine Learning in Power BI finden Sie unter [automatisierte Machine Learning in Power BI (Vorschau)](service-machine-learning-automated.md).
