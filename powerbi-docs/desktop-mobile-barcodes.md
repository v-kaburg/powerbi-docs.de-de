---
title: "Markieren eines Barcodefelds in Power BI Desktop für die mobilen Apps"
description: "Wenn Sie in Ihrem Modell in Power BI Desktop ein Barcodefeld markieren, können Sie Daten für Barcodes in der Power-BI-App auf Ihrem iPhone automatisch filtern."
services: powerbi
documentationcenter: 
author: maggiesMSFT
manager: kfile
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 07/18/2017
ms.author: maggies
ms.openlocfilehash: 029d93df808163ab5ff3015161121dafbbfa175d
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2017
---
# <a name="tag-barcodes-in-power-bi-desktop-for-the-mobile-apps"></a>Markieren eines Barcodes in Power BI Desktop für die mobilen Apps
In Power BI Desktop können Sie in einer Spalte [Daten kategorisieren](desktop-data-categorization.md), damit Power BI Desktop weiß, wie Werte in Visualisierungen in einem Bericht behandelt werden sollen. Sie können auch eine Spalte als **Barcode** kategorisieren. Wenn Sie oder Ihre Kollegen [einen Barcode auf einem Produkt mit der Power BI-App scannen](mobile-apps-scan-barcode-iphone.md), finden Sie auf dem iPhone jeden Bericht, der diesen Barcode enthält. Wenn Sie den Bericht in der mobilen App öffnen, filtert Power BI im Bericht automatisch nach Daten, die mit diesem Barcode verknüpft sind.

1. Wechseln Sie in Power BI Desktop zur Datenansicht.
2. Wählen Sie eine Spalte mit Barcodedaten aus. Weiter unten finden Sie die Liste der [unterstützten Barcodeformate](#supported-barcode-formats).
3. Wählen Sie auf der Registerkarte **Modellierung** **Datenkategorie** > **Barcode** aus.
   
    ![Liste „Datenkategorie“](media/desktop-mobile-barcodes/power-bi-desktop-barcode.png)
4. Fügen Sie dieses Feld in der Berichtsansicht den Visualisierungen hinzu, die der Barcode filtern soll.
5. Speichern Sie den Bericht, und veröffentlichen Sie ihn im Power BI-Dienst.

Wenn Sie den Scanner nun in der [Power BI-App für das iPhone](mobile-ios-ipad-iphone-apps.md) öffnen und einen Barcode scannen, wird Ihnen in der Liste der Berichte dieser Bericht angezeigt. Wenn Sie den Bericht öffnen, werden die Visualisierungen von dem Produktbarcode gefiltert, den Sie gescannt haben.

## <a name="supported-barcode-formats"></a>Unterstützte Barcodeformate
Die folgenden Barcodes erkennt Power BI, wenn Sie sie in einem Power BI-Bericht markieren können: 

* UPCECode 
* Code39Code  
* A39Mod43Code 
* EAN13Code 
* EAN8Code  
* 93Code  
* 128Code 
* PDF417Code 
* Interleaved2of5Code 
* ITF14Code 

## <a name="next-steps"></a>Nächste Schritte
* [Scannen eines Barcodes mit der Power BI-App auf dem iPhone](mobile-apps-scan-barcode-iphone.md)
* [Probleme beim Scannen eines Barcodes](mobile-apps-scan-barcode-iphone.md#issues-with-scanning-a-barcode)
* [Datenkategorisierung in Power BI Desktop](desktop-data-categorization.md)  
* Haben Sie Fragen? [Stellen Sie Ihre Frage in der Power BI-Community.](http://community.powerbi.com/)

