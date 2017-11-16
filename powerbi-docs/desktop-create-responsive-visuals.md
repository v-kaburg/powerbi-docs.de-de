---
title: "Optimieren eines Power BI-Visuals für eine beliebige Größe"
description: "Hier erfahren Sie, wie Sie in Power BI Desktop und im Power BI-Dienst Visuals für die Power BI-Smartphone-Apps optimieren."
services: powerbi
documentationcenter: 
author: maggiesMSFT
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
ms.date: 10/13/2017
ms.author: maggies
ms.openlocfilehash: a059c01d6e9e08851434f71a1f36ac096054e291
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2017
---
# <a name="optimize-a-power-bi-visual-for-any-size"></a>Optimieren eines Power BI-Visuals für eine beliebige Größe
Sie können Visuals in einem Dashboard oder Bericht auf *dynamisch* festlegen, damit bei jeder Bildschirmgröße automatisch möglichst viele Daten und Informationen angezeigt werden.

Wenn Sie die Größe des Visuals ändert, hat die Datenansicht in Power BI die höchste Priorität. Beispielsweise wird automatisch die Auffüllung entfernt und die Legende über das Visual verschoben, damit es auch bei einer Verkleinerung relevant bleibt. Dynamik ist insbesondere bei Visuals in der mobilen Power BI-App auf Smartphones nützlich.

![Größenänderung eines dynamischen Visuals](media/desktop-create-responsive-visuals/power-bi-responsive-visual.gif)

Sie können die Dynamik für jedes Visual mit X- und Y-Achsen sowie Slicern aktivieren.

## <a name="turn-on-responsiveness-in-power-bi-desktop"></a>Aktivieren der Dynamik in Power BI Desktop
1. Vergewissern Sie sich in Power BI Desktop auf der Registerkarte **Ansicht**, dass Sie sich im **Desktoplayout** befinden.
   
    ![Symbol „Desktoplayout“](media/desktop-create-responsive-visuals/power-bi-desktop-layout.png)
2. Wählen Sie ein Visual aus. Wählen Sie dann im Bereich **Visualisierungen** den Abschnitt **Format** aus.
3. Erweitern Sie **Allgemein**, und stellen Sie den Schieberegler **Dynamisch** auf **Ein**.
   
    ![„Dynamisch“ aktivieren](media/desktop-create-responsive-visuals/power-bi-turn-responsive-on.png)
   
     Wenn Sie jetzt einen [für Smartphones optimierten Bericht erstellen](desktop-create-phone-report.md) und dieses Visual hinzufügen, wird dessen Größe automatisch dynamisch angepasst.

## <a name="turn-on-responsiveness-in-the-power-bi-service"></a>Aktivieren der Dynamik im Power BI-Dienst
Die Dynamik für ein Visual in einem Bericht wird im Power BI-Dienst aktiviert. Dazu müssen Sie berechtigt sein, den Bericht zu bearbeiten.

1. Wählen Sie in einem Bericht im Power BI-Dienst ([https://powerbi.com](https://powerbi.com)) die Option **Bericht bearbeiten** aus.
2. Wählen Sie ein Visual aus. Wählen Sie dann im Bereich **Visualisierungen** den Abschnitt **Format** aus.
3. Erweitern Sie **Allgemein**, und stellen Sie den Schieberegler **Dynamisch** auf **Ein**.
   
    ![„Dynamisch“ aktivieren](media/desktop-create-responsive-visuals/power-bi-turn-responsive-on.png)
   
     Wenn Sie jetzt eine [Smartphoneansicht eines Dashboards erstellen](service-create-dashboard-mobile-phone-view.md) und dieses Visual hinzufügen, wird dessen Größe automatisch dynamisch angepasst.

## <a name="next-steps"></a>Nächste Schritte
* [Erstellen von Berichten, die für die Power BI-Smartphone-Apps optimiert sind](desktop-create-phone-report.md)
* [Erstellen einer Telefonansicht eines Dashboards in Power BI](service-create-dashboard-mobile-phone-view.md)
* [Anzeigen von Power BI-Berichten, die für das Smartphone optimiert sind](mobile-apps-view-phone-report.md)
* Weitere Fragen? [Stellen Sie Ihre Frage in der Power BI-Community.](http://community.powerbi.com/)

