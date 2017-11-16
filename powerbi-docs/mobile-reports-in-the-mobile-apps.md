---
title: Durchsuchen von Berichten in den mobilen Power BI-Apps
description: "Hier erfahren Sie, wie Sie in den mobilen Power BI-Apps auf Ihrem Telefon oder Tablet Berichte anzeigen und mit diesen interagieren. Erstellen Sie Berichte im Power BI-Dienst oder in Power BI Desktop, und verwenden Sie sie anschließend in den mobilen Apps. "
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
ms.openlocfilehash: 3515a57f88db1c8a7b12706680c0aade8b2cdbfa
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2017
---
# <a name="explore-reports-in-the-power-bi-mobile-apps"></a>Durchsuchen von Berichten in den mobilen Power BI-Apps
Gilt für:

| ![iPhone](media/mobile-reports-in-the-mobile-apps/ios-logo-40-px.png) | ![iPad](media/mobile-reports-in-the-mobile-apps/ios-logo-40-px.png) | ![Android-Smartphone](media/mobile-reports-in-the-mobile-apps/android-logo-40-px.png) | ![Android-Tablet](media/mobile-reports-in-the-mobile-apps/android-logo-40-px.png) | ![Windows 10-Geräte](media/mobile-reports-in-the-mobile-apps/win-10-logo-40-px.png) |
|:--- |:--- |:--- |:--- |:--- |
| iPhones |iPads |Android-Telefone |Android-Tablets |Windows 10-Geräte |

Ein Power BI-Bericht ist eine interaktive Ansicht Ihrer Daten, und mit den darin enthaltenen Visuals werden unterschiedliche Ergebnisse und Erkenntnisse zu diesen Daten dargestellt. Das Anzeigen von Berichten in den mobilen Power BI-Apps ist der dritte Schritt in einem dreistufigen Prozess.

1. [Erstellen Sie Berichte in Power BI Desktop](desktop-report-view.md). Sie können in Power BI Desktop sogar [einen Bericht für Telefone optimieren](mobile-apps-view-phone-report.md). 
2. Veröffentlichen Sie diese Berichte im Power BI-Dienst [(https://powerbi.com)](https://powerbi.com) oder auf dem [Power BI-Berichtsserver](report-server/get-started.md).  
3. Anschließend können Sie in den mobilen Power BI-Apps mit diesen Berichten interagieren.

## <a name="open-a-power-bi-report-in-the-mobile-app"></a>Öffnen eines Power BI-Berichts in der mobilen App
Power BI-Berichte werden abhängig von ihrer Herkunft an verschiedenen Stellen in der mobilen App gespeichert. Sie können sich in „Apps“, „Für mich freigegeben“, „Arbeitsbereiche“ (einschließlich „Mein Arbeitsbereich“) oder auf einem Berichtsserver befinden. Manchmal müssen Sie einen Bericht in einem entsprechenden Dashboard suchen, und manchmal sind Berichte aufgelistet.

* Tippen Sie in einem Dashboard auf die Auslassungspunkte (...) in der rechten oberen Ecke einer Kachel, und wählen Sie dann **Bericht öffnen** aus.
  
  ![Bericht öffnen](media/mobile-reports-in-the-mobile-apps/power-bi-android-open-report-tile.png)
  
  Nicht alle Kacheln verfügen über eine Option zum Öffnen als Bericht. Beispielsweise werden für Kacheln, die durch Stellen einer Frage im Q&A-Feld erstellt wurden, keine Berichte geöffnet, wenn Sie auf die Kachel tippen. 
  
  Auf einem Telefon wird der Bericht im Querformat geöffnet, es sei denn, er ist [für die Anzeige auf einem Telefon optimiert](mobile-reports-in-the-mobile-apps.md#view-reports-optimized-for-phones).
  
  ![Smartphonebericht im Querformat](media/mobile-reports-in-the-mobile-apps/power-bi-iphone-report-landscape.png)

## <a name="view-reports-optimized-for-phones"></a>Anzeigen von Berichten, die für Telefone optimiert sind
Autoren von Power BI-Berichten können ein für Telefone optimiertes Berichtslayout erstellen. Ein optimierter Bericht ist in einer Liste mit Berichten durch das Symbol ![Symbol für Smartphonebericht](media/mobile-reports-in-the-mobile-apps/power-bi-phone-report-icon.png)gekennzeichnet:

![Smartphonebericht öffnen](media/mobile-reports-in-the-mobile-apps/power-bi-android-phone-report.png)

Wenn Sie diesen Bericht auf einem Telefon anzeigen, wird er im Hochformat geöffnet.

![Bericht im Hochformat](media/mobile-reports-in-the-mobile-apps/07-power-bi-phone-report-portrait.png)

Ein Bericht kann eine Mischung aus für Telefone optimierten Seiten und aus nicht für Telefone optimierten Seiten enthalten. Wenn dies der Fall ist, wechselt beim Durchblättern des Berichts die Ansicht für jede nicht optimierte Seite vom Hochformat zum Querformat.

Weitere Informationen über [Berichte, die für die Smartphoneansicht optimiert sind](mobile-apps-view-phone-report.md).

## <a name="use-slicers-to-filter-a-report-page"></a>Verwenden von Datenschnitten zum Filtern einer Berichtsseite
Beachten Sie beim Entwerfen eines Berichts im Power BI-Dienst[(https://powerbi.com)](https://powerbi.com), dass auf einem Telefon der Bereich „Filter“ nicht angezeigt wird. Sie können jedoch [Datenschnitte auf einer Berichtsseite anzeigen](power-bi-visualization-slicers.md). Fügen Sie einem Bericht Datenschnitte hinzu, damit Sie und Ihre Kollegen die Seite auf einem Telefon mithilfe der Datenschnitte filtern können.

* Wenn Sie auf der Berichtsseite einen Wert in einem Datenschnitt auswählen, werden die anderen Visuals auf der Seite entsprechend gefiltert.
  
  ![Berichtsdatenschnitt](media/mobile-reports-in-the-mobile-apps/power-bi-android-tablet-report-slicer.png)
  
  In dieser Abbildung filtert der Datenschnitt das Säulendiagramm nach Juli-Werten.

## <a name="cross-filter-and-highlight-a-power-bi-report-page"></a>Kreuzfiltern und Hervorheben einer Power BI-Berichtsseite
Wenn Sie einen Wert in einem Visual auswählen, werden die anderen Visuals nicht nach diesem gefiltert. Jedoch werden die entsprechenden Werte in den anderen Visuals hervorgehoben.

* Tippen Sie auf einen Wert in einem Visual.
  
  ![Seite kreuzfiltern](media/mobile-reports-in-the-mobile-apps/power-bi-android-tablet-report-highlight.png)
  
  Wenn Sie in einem Visual auf die große Säule klicken, werden verwandte Werte in den anderen Visuals hervorgehoben. 

## <a name="sort-a-visual-on-an-ipad-or-a-tablet"></a>Sortieren eines Visuals auf einem iPad oder Tablet
* Tippen Sie auf das Diagramm, tippen Sie auf die Auslassungspunkte (**...**), und tippen Sie auf den Feldnamen.
  
   ![Visual sortieren](media/mobile-reports-in-the-mobile-apps/power-bi-android-tablet-report-sort.png)
* Um die Sortierreihenfolge umzukehren, tippen Sie erneut auf die Auslassungspunkte (**...**), und tippen Sie dann erneut auf den gleichen Feldnamen.

## <a name="drill-down-and-up-in-a-visual-on-an-ipad-or-a-tablet"></a>Ausführen von Drilldown und Drillup in einem Visual auf einem iPad oder Tablet
Wenn ein Berichtsautor diese Funktion zu einem Visual hinzugefügt hat, können Sie auf einem iPad oder Tablet einen Drilldown in einem Visual ausführen, um die Werte anzuzeigen, aus denen ein Teil des Visuals besteht. Sie können in Power BI Desktop und im Power BI-Dienst [einem Visual die Drill-Down-Funktion hinzufügen](power-bi-visualization-drill-down.md). 

> [!NOTE]
> Derzeit können auf einem iPad oder Tablet keine Drilldowns für Karten ausgeführt werden.
> 
> 

* Tippen Sie auf ein visuelles Element. Wenn das Element in den oberen Ecken Aufwärtspfeile und Abwärtspfeile ![Symbole für Drillup und Drilldown](media/mobile-reports-in-the-mobile-apps/power-bi-mobile-drill-up-down.png)enthält, kann ein Drilldown ausgeführt werden. Um einen Drilldown auf einen Wert durchzuführen, tippen Sie auf den Pfeil in der oberen rechten Ecke, und tippen Sie dann auf einen Wert im Visual – in diesem Fall auf die dunkelblaue Blase „FD-04“.
  
  ![Durchführen von Drilldown in einem visuellen Element](media/mobile-reports-in-the-mobile-apps/power-bi-mobile-drill-down-one.png)
* Um per Drillup zurückzugelangen, tippen Sie auf den Aufwärtspfeil links oben.
  
  ![Drillup](media/mobile-reports-in-the-mobile-apps/power-bi-mobile-drill-up.png)

## <a name="go-back-to-my-workspace"></a>Zurückkehren zu „Mein Arbeitsbereich“
* Tippen Sie auf den Pfeil neben dem Berichtsnamen, und tippen Sie dann auf **Mein Arbeitsbereich**.
  
  ![Zurückkehren](media/mobile-reports-in-the-mobile-apps/power-bi-iphone-report-back.png)

## <a name="next-steps"></a>Nächste Schritte
* [Anzeigen von und Interagieren mit Power BI-Berichten, die für das Smartphone optimiert sind](mobile-apps-view-phone-report.md)
* [Erstellen einer für Smartphones optimierten Version eines Berichts](desktop-create-phone-report.md)
* Haben Sie Fragen? [Stellen Sie Ihre Frage in der Power BI-Community.](http://community.powerbi.com/)

