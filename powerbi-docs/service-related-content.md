---
title: Anzeigen verwandter Inhalte im Power BI-Dienst
description: Vereinfachte Navigation zum Anzeigen verwandter Inhalte in Dashboards, Berichten und Datasets
author: mihart
manager: kfile
ms.reviewer: ''
featuredvideoid: B2vd4MQrz4M
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 03/01/2018
ms.author: mihart
LocalizationGroup: Get started
ms.openlocfilehash: 9aa0169f76515dd2f05a3e9debb8bc3d10cbdd07
ms.sourcegitcommit: 998b79c0dd46d0e5439888b83999945ed1809c94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/17/2018
---
# <a name="view-related-content-in-power-bi-service"></a>Anzeigen verwandter Inhalte im Power BI-Dienst
Im Bereich **verwandte Inhalte** sehen Sie, wie Ihre Inhalte im Power BI-Dienst (Dashboards, Berichte und Datasets) miteinander verbunden sind.  Außerdem können Sie in diesem Bereich allgemeine Aufgaben ausführen und beispielsweise Elemente aktualisieren oder umbenennen und Einblicke generieren. Wenn Sie einen verwandten Bericht oder ein verwandtes Dashboard auswählen, wird das ausgewählte Element in Ihrem Power BI-Arbeitsbereich geöffnet.   

Wie Sie wahrscheinlich bereits wissen, basieren Berichte auf Datasets, Berichtsvisualisierungen werden an Dashboards angeheftet, und visuelle Dashboardelemente sind wiederum mit Berichten verknüpft. Aber woher wissen Sie, welche Dashboards Visualisierungen aus Ihrem Marketingbericht hosten? Und wie finden Sie diese Dashboards? Basieren die Visualisierungen in Ihrem Beschaffungsdashboard auf mehreren Datasets? Und falls ja: Wie heißen sie, und wie können Sie sie öffnen und bearbeiten? Wird Ihr Personaldataset überhaupt in einem Bericht oder Dashboard verwendet oder kann es verschoben werden, ohne irgendwelche Links zu beschädigen? Fragen wie diese werden alle im Bereich **Verwandte Inhalte** beantwortet.  Der Bereich enthält nicht nur die verwandten Inhalte, sondern ermöglicht es auch, Aktionen auszuführen und komfortabel zwischen den verknüpften Inhalten zu navigieren.

![Verwandte Inhalte](media/service-related-content/power-bi-view-related-dashboard-new.png)

> [!NOTE]
> Das Feature „Verwandte Inhalte“ kann nicht für Streamingdatasets verwendet werden.
> 
> 

## <a name="view-related-content-for-a-dashboard"></a>Anzeigen verwandter Inhalte für ein Dashboard
Sehen Sie sich an, wie Will verwandte Inhalte für ein Dashboard anzeigt. Befolgen Sie dann die detaillierten Anweisungen unter dem Video, um es selbst mit dem Beispieldataset für die Beschaffungsanalyse auszuprobieren.

<iframe width="560" height="315" src="https://www.youtube.com/embed/B2vd4MQrz4M#t=3m05s" frameborder="0" allowfullscreen></iframe>


Zum Öffnen des Bereichs **Verwandte Inhalte** benötigen Sie mindestens *Anzeigeberechtigungen* für ein Dashboard. In diesem Beispiel verwenden wir das [Analysebeispiel für Beschaffung](sample-procurement.md).

**1. Methode**

Wählen Sie in einem Arbeitsbereich die Registerkarte **Dashboards** und anschließend das **Verwandte Inhalte**-Symbol ![Verwandte Inhalte anzeigen](media/service-related-content/power-bi-view-related-icon-new.png) aus.

![Registerkarte „Dashboard“](media/service-related-content/power-bi-view-related-dash-newer.png)

<br>

**2. Methode**

Wenn Sie ein Dashboard geöffnet haben, klicken Sie auf   ![„Verwandte Inhalte anzeigen“](media/service-related-content/power-bi-view-related-new.png) in der oberen Menüleiste.

Der Bereich **Verwandte Inhalte** wird geöffnet. Hier finden Sie alle Berichte, für die Visualisierungen an das Dashboard angeheftet sind, sowie die dazugehörigen Datasets. Für dieses Dashboard sind Visualisierungen aus drei verschiedenen Berichten angeheftet, und diese Berichte basieren auf drei verschiedenen Datasets.

![Bereich „Verwandte Inhalte“](media/service-related-content/power-bi-view-related-dashboard-new.png)

Von hier aus können Sie direkt Aktionen für die verwandten Inhalte ausführen.  Wählen Sie beispielsweise einen Berichtsnamen aus, um den entsprechenden Bericht zu öffnen.  Durch Auswählen eines Symbols für einen aufgeführten Bericht können Sie ihn [in Excel analysieren](service-analyze-in-excel.md), [umbenennen](service-rename.md) oder [Einblicke erhalten](service-insights.md). Für ein Dataset können Sie durch Auswählen eines Symbols [einen neuen Bericht erstellen](service-report-create-new.md), das Dataset [aktualisieren](refresh-data.md), umbenennen oder [in Excel analysieren](service-analyze-in-excel.md), [Einblicke erhalten](service-insights.md) oder das Fenster **Einstellungen** für das Dataset öffnen.  

## <a name="view-related-content-for-a-report"></a>Anzeigen verwandter Inhalte für einen Bericht
Zum Öffnen des Bereichs **Verwandte Inhalte** benötigen Sie mindestens *Anzeigeberechtigungen* für einen Bericht. In diesem Beispiel verwenden wir das [Analysebeispiel für Beschaffung](sample-procurement.md).

**1. Methode**

Wählen Sie in einem Arbeitsbereich die Registerkarte **Berichte** und anschließend das **Verwandte Inhalte anzeigen**-Symbol ![Symbol „Verwandte Inhalte anzeigen“](media/service-related-content/power-bi-view-related-icon-new.png) aus.

![Registerkarte „Berichte“](media/service-related-content/power-bi-view-related-report-newer.png)

<br>

**2. Methode**

Öffnen Sie den Bericht in der [Leseansicht](service-reading-view-and-editing-view.md), und wählen Sie in der oberen Menüleiste das Symbol ![Verwandte Inhalte anzeigen](media/service-related-content/power-bi-view-related-new.png) aus.

Der Bereich **Verwandte Inhalte** wird geöffnet. Hier finden Sie das zugeordnete Dataset sowie alle Dashboards mit mindestens einer angehefteten Kachel aus dem Bericht. Bei diesem Bericht sind Visualisierungen an zwei verschiedene Dashboards angeheftet.

![Bereich „Verwandte Inhalte“](media/service-related-content/power-bi-view-related-report.png)

Von hier aus können Sie direkt Aktionen für die verwandten Inhalte ausführen.  Wählen Sie beispielsweise einen Dashboardnamen aus, um das entsprechende Dashboard zu öffnen.  Für jedes Dashboard in der Liste können Sie durch Auswählen eines Symbols [das Dashboard für andere freigeben](service-share-dashboards.md) oder das Fenster **Einstellungen** für das Dashboard öffnen. Für das Dataset können Sie durch Auswählen eines Symbols [einen neuen Bericht erstellen](service-report-create-new.md), das Dataset [aktualisieren](refresh-data.md), umbenennen oder [in Excel analysieren](service-analyze-in-excel.md), [Einblicke erhalten](service-insights.md) oder das Fenster **Einstellungen** für das Dataset öffnen.  

## <a name="view-related-content-for-a-dataset"></a>Anzeigen verwandter Inhalte für ein Dataset
Zum Öffnen des Bereichs **Verwandte Inhalte** benötigen Sie mindestens *Anzeigeberechtigungen* für ein Dataset. In diesem Beispiel verwenden wir das [Analysebeispiel für Beschaffung](sample-procurement.md).

Wählen Sie in einem Arbeitsbereich die Registerkarte **Datasets** aus, und suchen Sie anschließend das **Verwandte Inhalte anzeigen**-Symbol ![Symbol „Verwandte Inhalte anzeigen“](media/service-related-content/power-bi-view-related-icon-new.png) aus.

![Registerkarte „Datasets“](media/service-related-content/power-bi-view-related-dataset-newer.png)

Wählen Sie das Symbol aus, um den Bereich **Verwandte Inhalte** zu öffnen.

![](media/service-related-content/power-bi-datasets.png)

Von hier aus können Sie direkt Aktionen für die verwandten Inhalte ausführen.  Wählen Sie beispielsweise einen Dashboard- oder Berichtsnamen aus, um das entsprechende Dashboard oder den entsprechenden Bericht zu öffnen.  Für jedes Dashboard in der Liste können Sie durch Auswählen eines Symbols [das Dashboard für andere freigeben](service-share-dashboards.md) oder das Fenster **Einstellungen** für das Dashboard öffnen. Durch Auswählen eines Symbols für einen Bericht können Sie ihn [in Excel analysieren](service-analyze-in-excel.md), [umbenennen](service-rename.md) oder [Einblicke erhalten](service-insights.md).  

## <a name="limitations-and-troubleshooting"></a>Einschränkungen und Problembehandlung
* Falls für Ihren Browser nicht genug Platz zur Verfügung steht, wird die Option **Verwandte Inhalte anzeigen** nicht angezeigt, aber das Verwandte Inhalte anzeigen-Symbol ![Symbol „Verwandte Inhalte anzeigen“](media/service-related-content/power-bi-view-related-icon-new.png) steht weiterhin zur Verfügung. Wählen Sie das Symbol aus, um den Bereich **Verwandte Inhalte** zu öffnen.
* Um verwandte Inhalte für einen Bericht öffnen zu können, müssen Sie sich in der [Leseansicht](service-reading-view-and-editing-view.md) befinden.
* In Power BI Desktop ist „Verwandte Inhalte“ nicht verfügbar.
* Das Feature „Verwandte Inhalte“ kann nicht für Streamingdatasets verwendet werden.

## <a name="next-steps"></a>Nächste Schritte
* [Erste Schritte mit dem Power BI-Dienst](service-get-started.md)
* Weitere Fragen? [Wenden Sie sich an die Power BI-Community](http://community.powerbi.com/)

