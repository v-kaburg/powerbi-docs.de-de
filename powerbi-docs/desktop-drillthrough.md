---
title: Verwenden der Drillthroughfunktion in Power BI Desktop
description: Erfahren Sie, wie Sie auf einer neuen Berichtsseite in Power BI Desktop Drilldowns in Daten ausführen.
services: powerbi
documentationcenter: ''
author: davidiseminger
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 05/08/2018
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: d0c78643d285099f7b7856704ac7ee350ff9f93a
ms.sourcegitcommit: 509be8852ba7595b9441c9479224f9dca298b26d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/09/2018
---
# <a name="use-drillthrough-in-power-bi-desktop"></a>Verwenden der Drillthroughfunktion in Power BI Desktop
Mithilfe des **Drillthroughs** können Sie in **Power BI Desktop** in Ihrem Bericht eine Seite erstellen, die sich auf eine bestimmte Entität konzentriert, z.B. auf einen Lieferanten, einen Kunden oder einen Hersteller. Wenn eine solche fokussierte Berichtsseite vorhanden ist, können Benutzer mit der rechten Maustaste auf einen Datenpunkt in anderen Berichtsseiten klicken und einen Drillthrough zu der fokussierten Seite ausführen, um Details zu erhalten, die entsprechend diesem Kontext gefiltert sind.

![Verwenden der Drillthroughfunktion](media/desktop-drillthrough/drillthrough_01.png)

## <a name="using-drillthrough"></a>Verwenden der Drillthroughfunktion
1. Erstellen Sie zum Verwenden der **Drillthroughfunktion** eine Berichtsseite mit Visuals, die für den Entitätstyp angezeigt werden sollen, für die Sie den Drillthrough bereitstellen. 

    Wenn Sie z.B. Drillthrough für Hersteller bereitstellen möchten, können Sie eine Drillthroughseite mit Visuals erstellen, die den Gesamtumsatz, die Summe der versandten Einheiten, den Umsatz nach Kategorie, den Umsatz nach Region usw. anzeigen. Wenn Sie dann einen Drillthrough auf diese Seite ausführen, werden die spezifischen Visuals für den Hersteller angezeigt, den Sie ausgewählt haben.

2. Ziehen Sie dann auf dieser Drillthroughseite im Abschnitt **Felder** des Bereichs **Visualisierungen** das Feld, für das Sie einen Drillthrough ausführen möchten, in den Bereich **Drillthroughfilter**.

    ![Bereich „Drillthrough“](media/desktop-drillthrough/drillthrough_02.png)

    Wenn Sie dem Bereich **Drillthroughfilter** ein Feld hinzufügen, wird in **Power BI Desktop** automatisch ein *Zurück*-Schaltflächenvisual erstellt. Dieses Visual wird eine Schaltfläche in veröffentlichten Berichten, mit der Benutzer, die Ihren Bericht im **Power BI-Dienst** verwenden, einfach zu der Berichtsseite zurückkehren können, die Sie zuvor geöffnet hatten (die Seite, auf der sie die Drillthroughfunktion ausgewählt haben).

    ![Drillthroughbild](media/desktop-drillthrough/drillthrough_03.png)

## <a name="use-your-own-image-for-a-back-button"></a>Verwenden eines eigenen Bildes für die Schaltfläche „Zurück“    
 Da die Schaltfläche „Zurück“ ein Bild ist, können Sie das Bild dieses Visuals durch jedes gewünschte Bild ersetzen, und es erfüllt weiterhin seine Funktion, Benutzer des Berichts zurück zur ursprünglichen Seite zurückzuleiten.

1. Klicken Sie auf der Registerkarte **Home** (Start) auf **Image** (Bilder). Suchen Sie anschließend Ihr Bild, und platzieren Sie es auf der Seite „Drillthrough“.
2. Wählen Sie das neue Bild auf der Seite „Drillthrough“ aus. Ziehen Sie anschließend im Abschnitt „Bild formatieren“ den Schieberegler **Link** auf die Position „Aus“, und legen Sie als **Typ** den Wert **Back** (Zurück) fest. Jetzt funktioniert das Bild als Schaltfläche „Zurück“.

    ![Verwenden eines Bilds für „Zurück“](media/desktop-drillthrough/drillthrough_05.png)

    Wenn die **Drillthroughseite** fertiggestellt ist und Benutzer mit der rechten Maustaste auf einen Datenpunkt im Bericht klicken, in dem das Feld verwendet wird, das Sie dem Bereich **Drillthroughfilter** hinzugefügt haben, wird ein Kontextmenü angezeigt, das den Drillthrough auf dieser Seite unterstützt.

    ![Menü für Drillthrough](media/desktop-drillthrough/drillthrough_04.png)

    Wenn Leser des Berichts einen Drillthrough ausführen, wird die Seite gefiltert, sodass sie Informationen über den Datenpunkt anzeigt, auf den mit der rechten Maustaste geklickt wurde. Wenn sie z.B. mit der rechten Maustaste auf einen Datenpunkt über Contoso (ein Hersteller) geklickt und die Drillthroughfunktion ausgewählt haben, wird die daraufhin angezeigte Drillthroughseite nach Contoso gefiltert.

## <a name="pass-all-filters-in-drillthrough"></a>Übergeben aller Filter an Drillthrough

Ab der Version Mai 2018 von **Power BI Desktop** können Sie alle angewendeten Filter an das Drillthroughfenster übergeben. Angenommen, Sie haben nur eine bestimmte Produktkategorie ausgewählt, die Visuals nach dieser Kategorie gefiltert und wählen dann Drillthrough. Es interessiert Sie vielleicht, wie dieser Drillthrough mit all diesen angewendeten Filtern aussieht.

Um alle angewendeten Filter beizubehalten, legen Sie im Fenster **Visualisierungen** im Abschnitt **Drillthrough** den Schalter **Alle Filter beibehalten** auf **Ein** fest. 

![Alle Filter beibehalten](media/desktop-drillthrough/drillthrough_06.png)

In Versionen von **Power BI Desktop** vor Mai 2018 entspricht das Verhalten der Festlegung dieses Schalters auf **Aus**.

Beim anschließenden Drillthrough auf ein Visual können Sie sehen, welche Filter angewendet wurden, weil auf das Quellvisual temporäre Filter angewendet wurden. Im Drillthroughfenster werden diese vorübergehenden Filter kursiv dargestellt. 

![Vorübergehende Filter in Kursivschrift](media/desktop-drillthrough/drillthrough_07.png)

Beachten Sie, dass Sie dies mit QuickInfo-Seiten erreichen könnten, aber das wäre eine seltsame Erfahrung (da das QuickInfo scheinbar nicht richtig funktioniert). Daher ist es nicht empfehlenswert, mit QuickInfos zu arbeiten.

Das ist bereits alles, was Sie über das Verwenden der **Drillthroughfunktion** in Berichten wissen müssen. Sie bietet eine hervorragende Möglichkeit, eine erweiterte Ansicht der Entitätsinformationen zu erhalten, die Sie für den Drillthroughfilter auswählen.

## <a name="next-steps"></a>Nächste Schritte

Folgende Artikel könnten Sie ebenfalls interessieren:

* [Verwenden von Slicern in Power BI Desktop](desktop-slicers.md)

