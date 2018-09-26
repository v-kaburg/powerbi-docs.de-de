---
title: Optimieren eines Power BI-Visuals für eine beliebige Größe
description: Hier erfahren Sie, wie Sie in bereits vorhandenen Berichten in Power BI Desktop und im Power BI-Dienst Visuals für Power BI-Smartphone-Apps optimieren können.
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 04/13/2018
ms.author: mihart
LocalizationGroup: Create reports
ms.openlocfilehash: 1260f2c69a4ab913f7451671ab7821ee250998c0
ms.sourcegitcommit: fb1885da7cf11367660edbf7b7346dc039ee9b5d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/26/2018
ms.locfileid: "47187235"
---
# <a name="optimize-a-power-bi-visual-for-any-size"></a>Optimieren eines Power BI-Visuals für eine beliebige Größe
Wenn Sie einen neuen Bericht erstellen, sind die Visuals standardmäßig *dynamisch*, d.h., sie ändern sich auf dynamische Weise, um unabhängig von der Bildschirmgröße die maximale Anzahl von Daten und Informationen anzuzeigen. Die Größe von Visuals älterer Berichte können Sie ebenfalls dynamisch anpassen.

Wenn Sie die Größe des Visuals ändert, hat die Datenansicht in Power BI die höchste Priorität. Beispielsweise wird automatisch die Auffüllung entfernt und die Legende über das Visual verschoben, damit es auch bei einer Verkleinerung relevant bleibt. Dynamik ist insbesondere bei Visuals in der mobilen Power BI-App auf Smartphones nützlich.

![Größenänderung eines dynamischen Visuals](media/desktop-create-responsive-visuals/power-bi-responsive-visual.gif)

Die Größe von sämtlichen Visuals mit X- und Y-Achsen sowie Slicern kann ebenfalls auf dynamische Weise geändert werden.

## <a name="turn-on-responsiveness-in-power-bi-desktop"></a>Aktivieren der Dynamik in Power BI Desktop
1. Vergewissern Sie sich bei älteren Berichten in Power BI Desktop auf der Registerkarte **Ansicht**, dass Sie sich im **Desktoplayout** befinden.
   
    ![Symbol „Desktoplayout“](media/desktop-create-responsive-visuals/power-bi-desktop-layout.png)
2. Wählen Sie ein Visual aus. Wählen Sie dann im Bereich **Visualisierungen** den Abschnitt **Format** aus.
3. Erweitern Sie **Allgemein**, und stellen Sie den Schieberegler **Dynamisch** auf **Ein**.
   
    ![„Dynamisch“ aktivieren](media/desktop-create-responsive-visuals/power-bi-turn-responsive-on.png)
   
     Wenn Sie jetzt einen [für Smartphones optimierten Bericht erstellen](../desktop-create-phone-report.md) und dieses Visual hinzufügen, wird dessen Größe automatisch dynamisch angepasst.

## <a name="turn-on-responsiveness-in-the-power-bi-service"></a>Aktivieren der Dynamik im Power BI-Dienst
Die Dynamik für ein Visual in einem Bericht kann im Power BI-Dienst aktiviert werden. Dazu müssen Sie berechtigt sein, den Bericht zu bearbeiten.

1. Klicken Sie in einem Bericht im Power BI-Dienst ([https://powerbi.com](https://powerbi.com)) auf **Bericht bearbeiten**.
2. Wählen Sie ein Visual aus. Wählen Sie dann im Bereich **Visualisierungen** den Abschnitt **Format** aus.
3. Erweitern Sie **Allgemein**, und stellen Sie den Schieberegler **Dynamisch** auf **Ein**.
   
    ![„Dynamisch“ aktivieren](media/desktop-create-responsive-visuals/power-bi-turn-responsive-on.png)
   
     Wenn Sie jetzt eine [Smartphoneansicht dieses Berichts erstellen](../desktop-create-phone-report.md) und dieses Visual hinzufügen, wird dessen Größe automatisch dynamisch angepasst.

## <a name="next-steps"></a>Nächste Schritte
* [Erstellen von Berichten, die für die Power BI-Smartphone-Apps optimiert sind](../desktop-create-phone-report.md)
* [Anzeigen von Power BI-Berichten, die für das Smartphone optimiert sind](../consumer/mobile/mobile-apps-view-phone-report.md)
* Weitere Fragen? [Stellen Sie Ihre Frage in der Power BI-Community.](http://community.powerbi.com/)

