---
title: "Reduzieren der Größe einer Excel-Arbeitsmappe für die Anzeige in Power BI"
description: "Reduzieren der Größe einer Excel-Arbeitsmappe für die Anzeige in Power BI"
services: powerbi
documentationcenter: 
author: davidiseminger
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 12/06/2017
ms.author: davidi
ms.openlocfilehash: 9ee4dba473cf757f23a757c44d5c3ebdd887fdfc
ms.sourcegitcommit: d91436de68a0e833ecff18d976de9d9431bc4121
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/06/2017
---
# <a name="reduce-the-size-of-an-excel-workbook-to-view-it-in-power-bi"></a>Reduzieren der Größe einer Excel-Arbeitsmappe für die Anzeige in Power BI
Sie können jede Excel-Arbeitsmappe, die kleiner als 1 GB ist, in Power BI hochladen. Eine Excel-Arbeitsmappe kann aus zwei Teilen bestehen: einem Datenmodell und dem Rest des Berichts – den Arbeitsblatt-Kerninhalten. Wenn der Bericht die folgenden Größenanforderungen erfüllt, können Sie ihn auf **OneDrive for Business** speichern, von Power BI aus eine Verbindung damit herstellen und ihn in Excel Online anzeigen:

* Die Arbeitsmappe als Ganzes darf bis zu 1 GB groß sein.
* Die Arbeitsblatt-Kerninhalte können eine Größe von bis zu 10 MB haben.

## <a name="what-makes-core-worksheet-contents-larger-than-10-mb"></a>Gründe dafür, warum Arbeitsblatt-Kerninhalte größer als 10 MB sind
Hier sind einige Faktoren aufgeführt, die bewirken können, dass die Arbeitsblatt-Kerninhalte größer als 10 MB sind:

* Bilder
* Schattierte Zellen. [Entfernen Sie ein Format für die Zellenschattierung](https://support.office.com/article/Add-or-change-the-background-color-of-cells-ac10f131-b847-428f-b656-d65375fb815e).
* Farbige Arbeitsblätter. [Entfernen Sie einen Hintergrund](https://support.office.com/en-US/article/add-or-remove-a-sheet-background-3577a762-8450-4556-96a2-cc265abc00a8).
* Textfelder
* ClipArt

Erwägen Sie, diese Elemente nach Möglichkeit zu entfernen. 

Wenn der Bericht ein Datenmodell aufweist, bestehen darüber hinaus weitere Optionen: 

* Entfernen Sie Daten aus den Excel-Arbeitsblättern, und speichern Sie sie stattdessen im Datenmodell. Details hierzu finden Sie unten unter „Entfernen von Daten aus Arbeitsblättern“. 
* [Erstellen eines speichereffizienten Datenmodells](https://support.office.com/article/Create-a-memory-efficient-Data-Model-using-Excel-2013-and-the-Power-Pivot-add-in-951c73a9-21c4-46ab-9f5e-14a2833b6a70) zum Reduzieren der Gesamtgröße des Berichts.

Sie müssen die Arbeitsmappe in Excel bearbeiten, um diese Änderungen vorzunehmen.

Weitere Informationen finden Sie unter [Dateigrößenbeschränkungen für Arbeitsmappen in SharePoint Online](https://support.office.com/article/File-size-limits-for-workbooks-in-SharePoint-Online-9e5bc6f8-018f-415a-b890-5452687b325e).

## <a name="remove-data-from-worksheets"></a>Entfernen von Daten aus Arbeitsblättern
Wenn Sie Daten über die Registerkarte „Power Query“ oder die Registerkarte „Excel-Daten“ in Excel importieren, kann die Arbeitsmappe dieselben Daten in einer Excel-Tabelle und im Datenmodell enthalten. Große Tabellen in Excel-Arbeitsblättern können dazu führen, dass die Arbeitsblatt-Kerninhalte 10 MB übersteigen. Indem Sie die Tabelle in Excel entfernen und die Daten im Datenmodell beibehalten, können Sie den Umfang der Arbeitsblatt-Kerninhalte des Berichts deutlich reduzieren. 

Beachten Sie diese Tipps, wenn Sie Daten in Excel importieren:

* **In Power Query**: Deaktivieren Sie das Kontrollkästchen **In Arbeitsblatt laden** .
  
  Die Daten werden nur in das Datenmodell importiert, ohne Daten in Excel-Arbeitsblättern.
* **Auf der Registerkarte „Excel-Daten“**: Falls Sie im Import-Assistenten die Option **Tabelle** aktiviert haben, navigieren Sie zu **Vorhandene Verbindungen**\>, klicken Sie auf die Verbindung, und wählen Sie \>**Nur Verbindung erstellen**. Löschen Sie die ursprünglichen Tabellen, die Sie während des ersten Importvorgangs erstellt haben.
* **Auf der Registerkarte „Excel-Daten“**: Achten Sie darauf, dass die Option **Tabelle** im Feld **Daten importieren** nicht aktiviert ist.

## <a name="workbook-size-optimizer"></a>Workbook Size Optimizer
Wenn die Arbeitsmappe ein Datenmodell enthält, können Sie den Workbook Size Optimizer ausführen, um die Größe Ihrer Arbeitsmappe zu verringern. [Workbook Size Optimizer herunterladen](https://www.microsoft.com/en-us/download/details.aspx?id=38793).

## <a name="related-info"></a>Verwandte Informationen
[Erstellen eines speichereffizienten Datenmodells](https://support.office.com/article/Create-a-memory-efficient-Data-Model-using-Excel-2013-and-the-Power-Pivot-add-in-951c73a9-21c4-46ab-9f5e-14a2833b6a70)

[Verwenden von OneDrive for Business-Links in Power BI Desktop](desktop-use-onedrive-business-links.md)

