---
title: Öffnen eines Berichts in der Leseansicht oder Bearbeitungsansicht im Power BI-Dienst
description: Öffnen eines Power BI-Berichts in der Leseansicht oder der Bearbeitungsansicht
services: powerbi
documentationcenter: ''
author: mihart
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
ms.date: 03/01/2018
ms.author: mihart
ms.openlocfilehash: c5177f4ccce8e8e274944cdcb539ca65a8f87ca8
ms.sourcegitcommit: 5e1f7d2673efe25c47b9b9f315011055bfe92c8f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2018
---
# <a name="open-a-report-in-power-bi-service-apppowerbicom"></a>Öffnen Sie einen Bericht im Power BI-Dienst (app.powerbi.com).
Berichte sind im Power BI-Dienst, in Power BI Desktop, in der mobilen Power BI-Version und sogar in Power BI Embedded verfügbar. Dieser Artikel beschreibt das Öffnen von Berichten im ***Power BI-Dienst***.

Im Power BI-Dienst stehen zwei Modi bereit, um Berichte anzuzeigen und mit ihnen zu interagieren: [die Leseansicht und die Bearbeitungsansicht](service-reading-view-and-editing-view.md). Die Leseansicht ist für alle Benutzer verfügbar und speziell für die *Benutzer* von Berichten konzipiert, während die Bearbeitungsansicht nur für *Berichtersteller* und -besitzer zur Verfügung steht. 

## <a name="open-a-report-from-a-workspace-via-the-reports-content-view-list"></a>Öffnen eines Berichts aus einem Arbeitsbereich (über die Inhaltsansichtsliste **Berichte**)

1. Beginnen Sie in einem Arbeitsbereich, und wählen Sie die Registerkarte **Berichte**, um alle Berichte in diesem Arbeitsbereich anzuzeigen.  
   
   ![Registerkarte "Berichte" eines Arbeitsbereichs](media/service-report-open/power-bi-open-report.png)
2. Wählen Sie den Berichtsnamen aus, um ihn in der Leseansicht zu öffnen.  
   
    ![Bericht in der Leseansicht](media/service-report-open/power-bi-reading-view.png)
3. Die Leseansicht bietet [zahlreiche Möglichkeiten](service-reading-view-and-editing-view.md).  Dieser Beispielbericht umfasst mehrere Seiten. Wählen Sie also zunächst die einzelnen Registerkarten im unteren Bereich des Berichtszeichenbereichs aus. 

## <a name="open-a-report-from-a-dashboard"></a>Öffnen eines Berichts aus einem Dashboard
Es gibt viele andere Möglichkeiten zum Öffnen eines Berichts. Sie können z.B. in einem Dashboard beginnen und eine Kachel auswählen, die aus einem Bericht erstellt wurde.  Durch die Auswahl der Kachel wird der Bericht in der Leseansicht geöffnet. Um die Schritte selbst nachzuvollziehen, öffnen Sie das [Dashboard zum Analysebeispiel für Vertrieb und Marketing](sample-datasets.md).

1. Öffnen Sie ein Dashboard, und wählen Sie eine Kachel aus.

   Wenn Sie eine Kachel auswählen, die [mit Q&A erstellt wurde](service-dashboard-pin-tile-from-q-and-a.md), wird der Q&A-Bildschirm geöffnet. Wenn Sie eine Kachel auswählen, die [mit dem Widget **Kachel hinzufügen** in einem Dashboard erstellt wurde](service-dashboard-add-widget.md), wird der Assistent zum Bearbeiten dieses Widgets geöffnet.  

2.  In diesem Beispiel wurde die Kachel „Total Units YTD...“ ausgewählt.

    ![Dashboard mit ausgewählter Kachel](media/service-report-open/power-bi-dashboard.png)

3.  Der entsprechende Bericht wird in der Leseansicht geöffnet. Beachten Sie, dass die Seite „YTD Category“ angezeigt wird. Dies ist die Berichtseite, die das im Dashboard ausgewählte Säulendiagramm enthält.

    ![Bericht in „Leseansicht“ öffnen](media/service-report-open/power-bi-report.png)

4. Bleiben Sie in der Leseansicht, oder wählen Sie **Bericht bearbeiten** aus, um den Bericht in der Bearbeitungsansicht zu öffnen. Denken Sie daran, dass nur Benutzer mit Bearbeitungsberechtigungen für diesen Bericht ihn in der Bearbeitungsansicht öffnen können.

    ![Der Berichts-Editor zeigt das Symbol „Bericht bearbeiten“ an.](media/service-report-open/power-bi-edit-report.png)

## <a name="create-a-brand-new-report-from-a-dataset"></a>Erstellen eines neuen Berichts aus einem Dataset
Eine weitere Möglichkeit besteht darin, einen Bericht aus einem Dataset zu öffnen. Wenn Sie mit einem Dataset beginnen, ist der Zeichenbereich des Berichts leer. Dieses Verfahren wird daher für *Ersteller* von Berichten empfohlen, die einen neuen Bericht auf Grundlage eines Datasets erstellen möchten, dessen Besitzer sie sind. Wenn Sie die Schritte selbst ausführen möchten, laden Sie wie für das obige Beispiel die [Beispiel-App für Vertrieb und Marketing herunter](sample-datasets.md).

1. Beginnen Sie in dem Arbeitsbereich mit dem Dataset, das Sie als Grundlage für einen Bericht verwenden möchten.

   ![Der linke Navigationsbereich zeigt App-Arbeitsbereiche an.](media/service-report-open/power-bi-workspace.png)

2. Wählen Sie die Registerkarte **Datasets** aus, um eine Liste aller Datasets in diesem Arbeitsbereich anzuzeigen. Dies wird als die Inhaltsansichtsliste **Datasets** bezeichnet.
   
   ![Liste von Datasets](media/service-report-open/power-bi-dataset.png)

1. Suchen Sie das Dataset, und wählen Sie das Symbol **Bericht erstellen** aus, um das Dataset in der Bearbeitungsansicht zu öffnen. Wenn Sie keine Bearbeitungsberechtigungen für ein Dataset haben, können Sie es nicht öffnen. 
   
    ![Datasets mit dem Symbol „Bericht erstellen“](media/service-report-open/power-bi-create-report.png)

3. Das Dataset wird im Berichts-Editor geöffnet. Rechts werden die Datenfelder angezeigt, sodass sie direkt anfangen können, sie zu untersuchen und Visualisierungen zu erstellen. 

   ![dem Zeichenbereich für den Bericht](media/service-report-open/power-bi-blank-canvas.png)

##  <a name="still-more-ways-to-open-a-report"></a>Weitere Möglichkeiten zum Öffnen eines Berichts
Wie Sie mit der Navigation im Power BI-Dienst besser vertraut sind, werden Sie feststellen, welche Arbeitsabläufe für Sie am besten geeignet sind. Weitere Möglichkeiten zum Zugriff auf Berichte:
- Über den linken Navigationsbereich mit **Favoriten**, **Zuletzt verwendet**, **Apps* und **Für mich freigegeben**. 
- Mit [Verwandte Inhalte anzeigen](service-related-content.md)
- Über eine E-Mail, wenn jemand [einen Bericht für Sie freigibt](service-share-reports.md) oder Sie [eine Benachrichtigung](service-set-data-alerts.md) festgelegt haben.    
- Über die [Mitteilungszentrale](service-notification-center.md)    
- usw.

## <a name="next-steps"></a>Nächste Schritte
Erfahren Sie mehr über [Berichte in Power BI](service-reports.md).

Weitere Fragen? [Wenden Sie sich an die Power BI-Community](http://community.powerbi.com/)  

