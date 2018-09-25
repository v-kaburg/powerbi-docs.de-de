---
title: Ändern der Größe einer Berichtsseite
description: Ändern der Anzeigeeinstellungen für eine Seite in einem Power BI-Bericht
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 01/24/2018
ms.author: mihart
LocalizationGroup: Reports
ms.openlocfilehash: c3e0fe7d469558a1800b7ce26b8b255fd8fa7a15
ms.sourcegitcommit: 70192daf070ede3382ac13f6001e0c8b5fb8d934
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2018
ms.locfileid: "46566186"
---
# <a name="change-the-size-of-a-report-page"></a>Ändern der Größe einer Berichtsseite
Im [vorherigen Artikel und Video](../power-bi-report-display-settings.md) haben Sie zwei unterschiedliche Arten zum Steuern der Seitenanzeige in Power BI-Berichten kennengelernt: **Ansicht** und **Seitengröße**. „Seitenansicht“ und „Seitengröße“ sind sowohl im Power BI-Dienst als auch in Power BI Desktop verfügbar, mit nahezu identischem Aussehen und Verhalten. Für dieses Tutorial verwenden wir jedoch den Power BI-Dienst.

### <a name="prerequisites"></a>Voraussetzungen
- Power BI-Dienst   
- [Bericht zum Analysebeispiel für den Einzelhandel](../sample-retail-analysis.md)

## <a name="first-lets-change-the-page-view-setting"></a>Ändern Sie zunächst die Einstellung für die Seitenansicht.

1. Öffnen Sie den Bericht in der Leseansicht oder Bearbeitungsansicht, und wählen Sie die Berichtsregisterkarte für **Neue Filialen** aus. Diese Berichtsseite wird standardmäßig mit der Einstellung **An Seite anpassen** angezeigt.  In diesem Fall zeigt „An Seite anpassen“ die Berichtsseite ohne Scrollleisten an, einige Details und Titel sind jedoch zu klein zum Lesen.

   ![](media/end-user-report-view/pbi_fit_to_page.png)
2. Stellen Sie sicher, dass im Zeichenbereich keine Visualisierungen ausgewählt sind. Wählen Sie **Ansicht** aus, und überprüfen Sie die Anzeigeoptionen.

   * In der Leseansicht wird dies angezeigt.

     ![](media/end-user-report-view/power-bi-page-view-menu-new.png)
   * Die Bearbeitungsansicht sieht wie folgt aus.

     ![](media/end-user-report-view/power-bi-view-editing-view.png)

3. So sieht die Seite mit der Einstellung **Tatsächliche Größe** aus.

   ![](media/end-user-report-view/power-bi-actal-size2.png)

   Allerdings hat das Dashboard jetzt zwei Bildlaufleisten.
4. Wechseln Sie zu **An Breite anpassen**.

   ![](media/end-user-report-view/pbi_fit_to_width.png)

   Das sieht besser aus. Nun sind zwar Scrollleisten vorhanden, aber die Details sind einfacher zu lesen.

## <a name="change-the-default-view-for-a-report-page"></a>Festlegen der Standardansicht für eine Berichtsseite
Wenn Sie der *Ersteller* des Berichts sind, können Sie die Standardansicht für die Berichtsseiten ändern. Wenn Sie den Bericht für andere Benutzer freigeben, werden die Berichtsseiten in der Ansicht geöffnet, die Sie festgelegt haben. *Nutzer* des Berichts können die Ansicht ändern, ihre Änderungen werden jedoch nicht gespeichert, nachdem sie den Bericht geschlossen haben.

1. Wechseln Sie auf der Seite **Neue Filialen** des Berichts zurück zur Ansicht **Tatsächliche Größe**.

   ![](media/end-user-report-view/power-bi-actual-size.png)

2. Legen Sie auf der Berichtsseite **Monatliche Verkäufe nach Region** „Ansicht“ auf **An Breite anpassen** fest.

3. Behalten Sie auf der Berichtsseite **Übersicht** die Standardeinstellung für „Ansicht“ bei.

4. Speichern Sie jetzt den Bericht, indem Sie **Datei > Speichern** auswählen. Wenn Sie den Bericht das nächste Mal öffnen, werden die Seiten mit den neuen Ansichtseinstellungen angezeigt. Sehen wir uns das einmal an.

   ![](media/end-user-report-view/power-bi-save.png)
3. Wählen Sie den Namen des aktuellen Arbeitsbereichs in der oberen Navigationsleiste aus, um zu diesem Arbeitsbereich zurückzuwechseln.  

   ![](media/end-user-report-view/power-bi-my-workspace.png)
4. Wählen Sie die Registerkarte **Berichte**, und wählen Sie den gleichen Bericht (Analysebeispiel für Einzelhandel) aus.

    ![](media/end-user-report-view/power-bi-new-report2.png)
5. Öffnen Sie jede Seite des Berichts, um die neuen Einstellungen anzuzeigen.

   ![](media/end-user-report-view/power-bi-page-view.gif)

## <a name="now-lets-explore-the-page-size-setting"></a>Betrachten wir nun die Einstellung *Seitengröße*.
Die Einstellungen für „Seitengröße“ sind nur in der [Bearbeitungsansicht](../service-interact-with-a-report-in-editing-view.md) verfügbar. Deshalb müssen Sie über Bearbeitungsberechtigungen (*Ersteller*) für den Bericht verfügen, um diese Einstellungen zu ändern. Wenn Sie eine Verbindung mit einem der [Beispiele](../sample-datasets.md) hergestellt haben, verfügen Sie über *Erstellerberechtigungen* für diese Berichte.

1. Öffnen Sie die Seite „Monatliche Verkäufe nach Region“ des [Analysebeispiels für den Einzelhandel](../sample-retail-analysis.md) in der Bearbeitungsansicht.
2. Stellen Sie sicher, dass im Zeichenbereich keine Visualisierungen ausgewählt sind.  Wählen Sie im Bereich **Visualisierungen** das Farbrollersymbol aus ![](media/end-user-report-view/power-bi-paintroller.png).
3. Wählen Sie **Seitengröße** &gt; **Typ** aus, um die Optionen für die Seitengröße anzuzeigen.

   ![](media/end-user-report-view/power-bi-page-size-menu-new.png)
4. Wählen Sie **Brief**.  Nur die Inhalte innerhalb des Formats 816 x 1056 Pixel (Letter-Format) werden im weißen Teil des Zeichenbereichs angezeigt.

   ![](media/end-user-report-view/power-bi-letter-new.png)
5. Wählen Sie **Seitengröße** und das Verhältnis **16:9** aus.

   ![](media/end-user-report-view/power-bi-16-to-9-new.png)

   Die Berichtsseite wird mit der Seitenbreite 16 im Verhältnis zur Höhe 9 angezeigt. Die tatsächlich verwendete Pixelgröße wird Ihnen in den abgeblendeten Feldern für Breite und Höhe angezeigt (1280 x 720). Um den Berichtszeichenbereich wird ein leerer Bereich angezeigt, da für die **Ansicht** zuvor „An Breite anpassen“ festgelegt wurde.
7. Lernen Sie die Optionen für **Seitengröße** genauer kennen.

## <a name="use-page-view-and-page-size-together"></a>Gemeinsame Verwendung der Optionen „Ansicht“ und „Seitengröße“
Verwenden Sie die Optionen „Ansicht“ und „Seitengröße“ gemeinsam, um einen Bericht zu erstellen, der besonders übersichtlich ist, wenn er für Kollegen freigegeben oder in eine andere Anwendung eingebettet wird.

In dieser Übung erstellen Sie eine Berichtsseite, die in einer Anwendung mit 500 Pixel Breite und 750 Pixel Höhe angezeigt wird.

Aus dem letzten Schritt wissen wir, dass unsere Berichtsseite derzeit mit einer Breite von 1280 Pixel und einer Höhe von 720 Pixel angezeigt wird. Wir müssen also die Größe verändern und die Daten neu anordnen, damit die Visualisierung Platz hat.

1. Ändern Sie die Größe und Position der Visualisierung, sodass sie mit weniger als der Hälfte an Platz verglichen mit dem derzeitigen Zeichenbereich auskommt.

    ![](media/end-user-report-view/power-bi-custom-view.gif)
2. Wählen Sie **Seitengröße** &gt; **Benutzerdefiniert**.
3. Legen Sie die Breite auf 500 und die Höhe auf 750 fest.

    ![](media/end-user-report-view/power-bi-custom-new.png)
4. Optimieren Sie die Berichtsseite für eine ideale Darstellung. Wechseln Sie zwischen **Ansicht > Tatsächliche Größe** und **Ansicht > An Seite anpassen**, während Sie die Anpassungen vornehmen.

    ![](media/end-user-report-view/power-bi-final-new.png)

## <a name="next-steps"></a>Nächste Schritte
[Erstellen von Berichten für Cortana](../service-cortana-answer-cards.md)

[Einstellungen für die Seitenanzeige in einem Power BI-Bericht](../power-bi-report-display-settings.md)

Weitere Fragen? [Wenden Sie sich an die Power BI-Community](http://community.powerbi.com/)
