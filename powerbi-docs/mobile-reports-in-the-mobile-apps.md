---
title: Durchsuchen von Berichten in den mobilen Power BI-Apps
description: Hier erfahren Sie, wie Sie in den mobilen Power BI-Apps auf Ihrem Telefon oder Tablet Berichte anzeigen und mit diesen interagieren. Erstellen Sie Berichte im Power BI-Dienst oder in Power BI Desktop, und verwenden Sie sie anschließend in den mobilen Apps.
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-mobile
ms.topic: conceptual
ms.date: 08/17/2018
ms.author: maggies
ms.openlocfilehash: eee7c4989c4856ab86cb4883f8004198da00e4fd
ms.sourcegitcommit: 23bb84cd3e80ba7f03d559e48db322774d1a6fe0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/20/2018
ms.locfileid: "40257006"
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
Autoren von Power BI-Berichten können ein für Telefone optimiertes Berichtslayout erstellen. Für Smartphones optimierte Berichtsseiten bieten zusätzliche Funktionalität: Beispielsweise können Sie in Visuals Drilldowns und Sortierungen durchführen, und Sie haben Zugriff auf die [Filter, die der Autor des Berichts der Berichtsseite hinzugefügt hat](mobile-apps-view-phone-report.md#filter-the-report-page-on-a-phone). Der Bericht wird auf Ihrem Smartphone geöffnet, und es werden die im Web gefilterten Werte zusammen mit einer Meldung angezeigt, dass die Seite aktive Filter enthält. Sie können die Filtereinstellungen auf Ihrem Smartphone ändern.

Ein optimierter Bericht ist in einer Liste mit Berichten durch das Symbol ![Symbol für Smartphonebericht](media/mobile-reports-in-the-mobile-apps/power-bi-phone-report-icon.png)gekennzeichnet:

![Smartphonebericht öffnen](media/mobile-reports-in-the-mobile-apps/power-bi-android-phone-report.png)

Wenn Sie diesen Bericht auf einem Telefon anzeigen, wird er im Hochformat geöffnet.

![Bericht im Hochformat](media/mobile-reports-in-the-mobile-apps/07-power-bi-phone-report-portrait.png)

 Ein Bericht kann eine Mischung aus für Telefone optimierten Seiten und aus nicht für Telefone optimierten Seiten enthalten. Wenn dies der Fall ist, wechselt beim Durchblättern des Berichts die Ansicht für jede nicht optimierte Seite vom Hochformat zum Querformat.

Weitere Informationen über [Berichte, die für die Smartphoneansicht optimiert sind](mobile-apps-view-phone-report.md).

## <a name="use-slicers-to-filter-a-report"></a>Verwenden von Datenschnitten zum Filtern eines Berichts
Beim Entwerfen eines Berichts in Power BI Desktop oder dem Power BI-Dienst, ist es von Vorteil, [einer Berichtsseite Datenschnitte hinzuzufügen](power-bi-visualization-slicers.md). Sie und Ihre Kollegen können Datenschnitte verwenden, um die Seite in einem Browser und in den mobilen Apps zu filtern. Wenn Sie den Bericht auf einem Smartphone betrachten, können Sie die Datenschnitte im Querformat und auf einer für das Hochformat des Geräts optimierten Seite sehen und mit ihnen interagieren. Wenn Sie einen Wert in einem Slicer oder Filter im Browser auswählen, wird der Wert auch beim Anzeigen der Seite in der mobilen App ausgewählt. Es wird eine Meldung angezeigt, dass die Seite aktive Filter enthält.  

* Wenn Sie auf der Berichtsseite einen Wert in einem Datenschnitt auswählen, werden die anderen Visuals auf der Seite entsprechend gefiltert.
  
  ![Berichtsdatenschnitt](media/mobile-reports-in-the-mobile-apps/power-bi-android-tablet-report-slicer.png)
  
  In dieser Abbildung filtert der Datenschnitt das Säulendiagramm nach Juli-Werten.

## <a name="cross-filter-and-highlight-a-report"></a>Kreuzfiltern und Hervorheben eines Berichts
Wenn Sie einen Wert in einem Visual auswählen, werden die anderen Visuals nicht nach diesem gefiltert. Jedoch werden die entsprechenden Werte in den anderen Visuals hervorgehoben.

* Tippen Sie auf einen Wert in einem Visual.
  
  ![Seite kreuzfiltern](media/mobile-reports-in-the-mobile-apps/power-bi-android-tablet-report-highlight.png)
  
  Wenn Sie in einem Visual auf die große Säule klicken, werden verwandte Werte in den anderen Visuals hervorgehoben. 

## <a name="sort-a-visual-on-an-ipad-or-a-tablet"></a>Sortieren eines Visuals auf einem iPad oder Tablet
* Tippen Sie auf das Diagramm, tippen Sie auf die Auslassungspunkte (**...**), und tippen Sie auf den Feldnamen.
  
   ![Visual sortieren](media/mobile-reports-in-the-mobile-apps/power-bi-android-tablet-report-sort.png)
* Um die Sortierreihenfolge umzukehren, tippen Sie erneut auf die Auslassungspunkte (**...**), und tippen Sie dann erneut auf den gleichen Feldnamen.

## <a name="drill-down-and-up-in-a-visual"></a>Durchführen eines Drilldowns und Drillups in einem Visual
Wenn ein Berichtsautor die Drilldownfunktion einem Visual hinzugefügt hat, können Sie einen Drilldown in einem Visual durchführen, um die Werte anzuzeigen, aus denen ein Teil des Visuals besteht. Sie können in Power BI Desktop und im Power BI-Dienst [einem Visual die Drill-Down-Funktion hinzufügen](power-bi-visualization-drill-down.md). 

* Tippen Sie auf einen bestimmten Balken oder Punkt in einem Visual, und halten Sie diesen, um die zugehörige QuickInfo anzuzeigen. Wenn ein Drilldown möglich ist, können Sie am unteren Rand der QuickInfo auf Pfeile tippen. 
  
  ![Durchführen von Drilldown in einem visuellen Element](media/mobile-reports-in-the-mobile-apps/power-bi-mobile-drill-down-tooltip.png)

* Um per Drillup zurückzugelangen, tippen Sie auf den Aufwärtspfeil in der QuickInfo.
  
  ![Drillup](media/mobile-reports-in-the-mobile-apps/power-bi-mobile-drill-up-tooltip.png)

* Sie können auch einen Drilldown für alle Datenpunkte in einem Visual durchführen. Öffnen Sie es im Fokusmodus, tippen Sie auf das Symbol „Durchsuchen“, und klicken Sie dann auf „Nächste Ebene anzeigen“, oder erweitern Sie das Visual, sodass die aktuelle und die nächste Ebene angezeigt wird.

   ![Drilldown für alle Datenpunkte in Power BI](media/mobile-reports-in-the-mobile-apps/power-bi-drill-down-all.png)

## <a name="drill-through-from-one-page-to-another"></a>Drillthrough von einer Seite zu einer anderen

Wenn Sie beim *Drillthrough* auf einen bestimmten Teil eines Visual tippen, gelangen Sie zu einer anderen Berichtsseite, die nach dem Wert gefiltert ist, auf den Sie getippt haben. Der Autor eines Berichts kann mindestens eine Drillthroughoption festlegen, durch die Sie auf eine andere Seite weitergeleitet werden. In diesem Fall können Sie entscheiden, auf welche Seite Sie einen Drillthrough durchführen möchten. In folgendem Beispiel können Sie zwischen **spent by business area** und **planning by business area** wählen, wenn Sie auf einen Wert auf dem Messgerät tippen.

![Power BI Mobile: Drillthrough für einen Bericht](media/mobile-reports-in-the-mobile-apps/power-bi-mobile-drill-through-it-spent-report.png)

Wenn Sie einen Drillthrough durchführen, gelangen Sie über die Schaltfläche „Zurück“ auf die vorherige Berichtsseite.

Erfahren Sie, wie Sie [Drillthrough in Power BI Desktop verwenden](desktop-drillthrough.md).

## <a name="next-steps"></a>Nächste Schritte
* [Anzeigen von und Interagieren mit Power BI-Berichten, die für das Smartphone optimiert sind](mobile-apps-view-phone-report.md)
* [Erstellen einer für Smartphones optimierten Version eines Berichts](desktop-create-phone-report.md)
* Haben Sie Fragen? [Stellen Sie Ihre Frage in der Power BI-Community.](http://community.powerbi.com/)

