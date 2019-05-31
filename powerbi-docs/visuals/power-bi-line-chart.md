---
title: Liniendiagramme in Power BI
description: Liniendiagramme in Power BI
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/07/2019
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 0654dccf55b1e13f26d8ecaabee0349f0e56afc6
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2019
ms.locfileid: "65535788"
---
# <a name="line-charts-in-power-bi"></a>Liniendiagramme in Power BI
Ein Liniendiagramm ist eine Reihe von Datenpunkten, die durch Punkte dargestellt und durch gerade Linien verbunden sind. Ein Liniendiagramm möglicherweise eine oder mehrere Zeilen. Liniendiagramme haben ein "X" und eine y-Achse. 

![einfaches Liniendiagramm](media/power-bi-line-charts/power-bi-line.png)

## <a name="create-a-line-chart"></a>Erstellen Sie ein Liniendiagramm
Diese Anweisungen verwenden die Verkäufe und die Marketing-Beispiel-app für die ein Liniendiagramm zu erstellen, die den diesjährigen Umsatz nach Kategorie anzeigt. Um folgen zu können, müssen rufen Sie die Beispiel-app aus appsource.com ab.

1. Beginnen Sie auf einer leeren Berichtsseite. Wenn Sie den Power BI-Dienst verwenden, achten Sie darauf, den Bericht in der [Bearbeitungsansicht](../service-interact-with-a-report-in-editing-view.md) zu öffnen.

2. Wählen Sie aus dem Bereich "Felder" **SalesFact** \> **Gesamteinheiten**, und wählen Sie **Datum** > **Monat**.  Powerbi erstellt ein Säulendiagramm Zeichenbereich des Berichts an.

    ![Wählen Sie aus dem Bereich "Felder"](media/power-bi-line-charts/power-bi-step1.png)

4. Konvertieren Sie in ein Liniendiagramm, durch Auswählen der Vorlage für die Zeile aus dem Bereich "Visualisierungen". 

    ![Konvertieren in Liniendiagramm](media/power-bi-line-charts/power-bi-convert-to-line.png)
   

4. Filtern Sie Ihre Liniendiagramm, um Daten in den Jahren 2012-2014 anzuzeigen. Wenn der Bereich "Filter" reduziert ist, erweitern Sie ihn jetzt an. Wählen Sie aus dem Bereich "Felder" **Datum** \> **Jahr** und ziehen Sie es in den Bereich "Filter". Legen Sie es unter der Überschrift **Filter für diese Visualisierung**. 
     
    ![Zeile neben dem Bereich "Felder"](media/power-bi-line-charts/power-bi-year-filter.png)

    Änderung **erweiterter Filter** zu **Standardfiltern** , und wählen Sie **2012**, **2013** und **2014**.

    ![Filter für Year](media/power-bi-line-charts/power-bi-filter-year.png)

6. Optional können Sie [die Textgröße und -farbe des Diagramms anpassen](power-bi-visualization-customize-title-background-and-legend.md). 

    ![Vergrößern Sie Schriftgrad und ändern Sie die Y-axisfont](media/power-bi-line-charts/power-bi-line-3years.png)

## <a name="add-additional-lines-to-the-chart"></a>Fügen Sie zusätzliche Zeilen für das Diagramm
Liniendiagramme können viele unterschiedliche Zeilen haben. Und in einigen Fällen können die Werte in den Zeilen also voneinander abweichende, dass sie gut zusammen anzeigen nicht sein. Wir sehen uns das Hinzufügen zusätzliche Zeilen mit unseren aktuellen "Diagrammeigenschaften", und erfahren Sie, wie unser Diagramm zu formatieren, wenn die Werte durch die Linien dargestellt sehr unterschiedlich sind. 

### <a name="add-additional-lines"></a>Fügen Sie zusätzliche Zeilen
Anstatt Gesamtanzahl der Einheiten für alle Regionen als einzelne Zeile im Diagramm, unterteilen Sie gesamte Einheiten nach Region. Fügen Sie zusätzliche Zeilen durch Ziehen von **geografische** > **Region** auf die Legende gut.

   ![Eine Zeile für jede region](media/power-bi-line-charts/power-bi-line-regions.png)


### <a name="use-two-y-axes"></a>Verwenden Sie zwei y-Achsen
Was geschieht, wenn Sie möchten den Gesamtumsatz und die Gesamtanzahl der Einheiten in einem Diagramm ansehen? Verkaufszahlen sind also sehr viel höher als Einheit Zahlen, wodurch das Liniendiagramm kann nicht verwendet werden. Tatsächlich scheint die rote Linie für die Gesamtanzahl der Einheiten 0 (null) sein.

   ![hoch Auseinanderlaufende Werte](media/power-bi-line-charts/power-bi-diverging.png)

Verwenden Sie ein Kombinationsdiagramm, um stark abweichende Werte in einem Diagramm anzuzeigen. Erfahren Sie alles über Kombinationsdiagramme lesen [Kombinationsdiagramme in Power BI](power-bi-visualization-combo-chart.md). Im folgenden Beispiel können wir sales und gesamte Einheiten zusammen in einem Diagramm anzeigen, indem eine zweite y-Achse hinzufügen. 

   ![hoch Auseinanderlaufende Werte](media/power-bi-line-charts/power-bi-dual-axes.png)

## <a name="considerations-and-troubleshooting"></a>Zu beachtende Aspekte und Problembehandlung
* Ein Liniendiagramm kann nicht mit zwei y-Achsen haben.  Sie müssen stattdessen ein Kombinationsdiagramm.
* In den obigen Beispielen wurden die Diagramme so formatiert, Schriftgrad vergrößern, Ändern von Schriftfarbe, Hinzufügen von Achsentiteln, zentrieren Sie den Diagrammtitel und die Legende, starten beide Achsen auf 0 (null) und vieles mehr. Der Formatierungsbereich (farbrollen-Symbol) verfügt über eine endlose Reihe von Optionen für das Herstellen von des Layout der Diagramme die gewünschte Weise zu. Die beste Möglichkeit, erfahren, werden von den Formatierungsbereich zu öffnen und zu durchsuchen.

## <a name="next-steps"></a>Nächste Schritte

[Visualisierungstypen in Power BI](power-bi-visualization-types-for-reports-and-q-and-a.md)


