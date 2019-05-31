---
title: Exportieren von Daten aus einem Power BI-Visual
description: Exportieren von Daten aus einer berichtsvisualisierung und die Dashboard-visuelle und in Excel anzeigen.
author: mihart
manager: kvivek
ms.reviewer: ''
featuredvideoid: jtlLGRKBvXY
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 4/9/2019
ms.author: mihart
LocalizationGroup: Consumers
ms.openlocfilehash: d4384db8e05a69b138e76377e7c7b845867fa881
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2019
ms.locfileid: "61063728"
---
# <a name="export-data-from-visual"></a>Exportieren von Daten aus visual
Wenn Sie möchten, um die Daten anzuzeigen, die verwendet wird, zum Erstellen einer Visualisierung, [können Sie diese Daten in Power BI anzeigen](end-user-show-data.md) oder die Daten nach Excel exportieren. Die Option zum Exportieren der Daten erfordert einen bestimmten Typ oder die Lizenz und Berechtigungen auf den Inhalt bearbeiten. Wenn Sie nicht exportieren können, wenden Sie sich an den Power BI-Administrator. 

## <a name="from-a-visual-on-a-power-bi-dashboard"></a>Aus einem visuellen Element in einem Power BI-dashboard

1. Starten Sie auf der Power BI-Dashboard. Hier verwenden wir das Dashboard über die ***Marketing- und Vertriebsabteilung Beispiel*** app. Sie können [diese app aus AppSource.com herunterladen](https://appsource.microsoft.com/en-us/product/power-bi/microsoft-retail-analysis-sample.salesandmarketingsample-preview?flightCodes=e2b06c7a-a438-4d99-9eb6-4324ce87f282).

    ![](media/end-user-export/power-bi-dashboard.png)

2. Zeigen Sie auf eine Visualisierung aus, um die Auslassungspunkte (...) anzuzeigen, und klicken Sie auf, um das Aktionsmenü anzuzeigen.

    ![](media/end-user-export/power-bi-dashboard-export-visual.png)

3. Wählen Sie **nach Excel exportieren**.

4. Was als Nächstes geschieht, hängt ab, welchen Browser Sie verwenden. Sie möglicherweise aufgefordert, speichern Sie die Datei oder Ihrem Mai ein Link angezeigt, die exportierte Datei am unteren Rand der Browser. 

    ![](media/end-user-export/power-bi-export-browser.png)

5. Öffnen Sie die Datei in Excel.  

    ![](media/end-user-export/power-bi-excel.png)


## <a name="from-a-visual-in-a-report"></a>Aus einem visuellen Element in einem Bericht
Sie können Daten aus einem visuellen Element in einem Bericht als CSV- oder .xlsx (Excel) exportieren Format. 

1. Wählen Sie auf dem Dashboard eine Kachel, um den zugrunde liegenden Bericht zu öffnen.  In diesem Beispiel wählen wir das gleiche visual wie oben, *gesamte Einheiten seit Jahresbeginn*. 

    ![](media/end-user-export/power-bi-export-report.png)

    Seit der Erstellung dieser Kachel aus der *Vertriebs- und Marketingbeispiel* Bericht, die der Bericht, der geöffnet wird. Und es öffnet die Seite, die die ausgewählten Kachel-Visualisierung enthält. 

2. Wählen Sie die Kachel im Bericht. Beachten Sie, dass die **Filter** rechts. Dieses visuelle Element verfügt über Filter angewendet. Weitere Informationen zu Filtern finden Sie unter [verwenden Sie Filter in einem Bericht](end-user-report-filter.md).

    ![](media/end-user-export/power-bi-export-filters.png)


3. Wählen Sie die Auslassungszeichen in der rechten oberen Ecke der Visualisierung aus. Wählen Sie **Exportieren von Daten**.

    ![](media/end-user-export/power-bi-export-report2.png)

4. Optionen zum Exportieren der Zusammenfassung oder zugrunde liegender Daten angezeigt. Bei Verwendung der *Vertriebs- und marketingbeispiel* app **zugrunde liegende Daten** wird deaktiviert. Jedoch treten ggf. die Berichte, in denen beide Optionen aktiviert sind. Hier wird beschrieben, der den Unterschied.

    **Zusammengefasste Daten**: Wählen Sie diese Option aus, wenn Sie Daten für die Anzeige im visuellen Element exportieren möchten.  Dieser Typ des Exports erfahren Sie, nur die Daten, die zum Erstellen der Visualisierung verwendet wurde. Wenn die Visualisierung angewendeten Filter aufweist, werden die Daten, die Sie exportieren auch gefiltert werden. So umfasst der Export für dieses visuelle Element, z. B. nur Daten für 2014 und die Region "Mitte", und nur Daten für vier der Hersteller: VanArsdel, Natura, Aliqui und Prirum.
  

    **Zugrunde liegende Daten**: Wählen Sie diese Option aus, wenn Sie Daten für die Anzeige im visuellen Element exportieren möchten **plus** zusätzliche Daten aus dem zugrunde liegenden Dataset.  Dadurch kann die Daten enthalten, die im Dataset enthalten ist, aber nicht in der Visualisierung verwendet. 

    ![](media/end-user-export/power-bi-export-report3.png)

5. Was als Nächstes geschieht, hängt ab, welchen Browser Sie verwenden. Sie möglicherweise aufgefordert, speichern Sie die Datei oder Ihrem Mai ein Link angezeigt, die exportierte Datei am unteren Rand der Browser. 

    ![](media/end-user-export/power-bi-export-edge.png)


7. Öffnen Sie die Datei in Excel. Vergleichen Sie die Menge der Daten, die exportiert werden, auf die Daten, die wir aus der gleichen Visualisierung auf dem Dashboard exportiert. Der Unterschied besteht darin, dass dieser Export enthält **zugrunde liegende Daten**. 

    ![](media/end-user-export/power-bi-underlying.png)

