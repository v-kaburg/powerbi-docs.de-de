---
title: "Anzeigen von Power BI-Berichten, die für das Smartphone optimiert sind"
description: "Erfahren Sie, wie Sie mit Berichtsseiten interagieren, die für die Anzeige in Power BI-Smartphone-Apps optimiert sind."
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
ms.date: 12/06/2017
ms.author: maggies
ms.openlocfilehash: f3e02da2c0e793f3eb334c39852f5cd23534ad3f
ms.sourcegitcommit: 54da95f184dd0f7bb59bb0bc8775a1d93129b195
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/08/2017
---
# <a name="view-power-bi-reports-optimized-for-your-phone"></a>Anzeigen von Power BI-Berichten, die für das Smartphone optimiert sind
Wenn Sie in Power BI Desktop einen Power BI-Bericht erstellen, können Sie auch eine [zum Anzeigen in der Power BI-App auf einem Smartphone optimierte Version des Berichts](desktop-create-phone-report.md) erstellen.

Beim Öffnen eines Power BI-Berichts auf einem Smartphone erkennt Power BI, ob der Bericht für Smartphones optimiert wurde, und öffnet den optimierten Bericht automatisch im Hochformat.

![Bericht im Hochformat](media/mobile-apps-view-phone-report/07-power-bi-phone-report-portrait.png)

Wenn kein für das Smartphone optimierter Bericht vorhanden ist, wird der Bericht zwar geöffnet, jedoch in der nicht optimierten Querformatansicht. Auch wenn Sie bei einem für das Smartphone optimierten Bericht das Smartphone auf die Seite drehen, wird der Bericht in der nicht optimierten Ansicht mit dem ursprünglichen Berichtslayout geöffnet. Wenn nur einige Seiten optimiert sind, wird in der Hochformatansicht eine Meldung angezeigt, die Ihnen mitteilt, dass der Bericht im Querformat verfügbar ist.

![Nicht optimierte Berichtsseite](media/mobile-apps-view-phone-report/06-power-bi-phone-report-page-not-optimized.png)

In für das Smartphone optimierten Berichten werden alle anderen Features von Power BI-Berichten ausgeführt. Weitere Informationen über die Ihnen zur Verfügung stehenden Möglichkeiten finden Sie unter:

* [Berichte auf iPhones](mobile-reports-in-the-mobile-apps.md). 
* [Berichte auf Android-Smartphones](mobile-reports-in-the-mobile-apps.md).

## <a name="filter-the-report-page-on-a-phone"></a>Filtern der Berichtsseite auf einem Smartphone
Wenn bei einem für das Smartphone optimierten Bericht Filter definiert wurden, können Sie diese Filter beim Anzeigen des Berichts auf einem Smartphone verwenden. 

1. Tippen Sie auf das Symbol „Filter“ ![Symbol „Filter“ für Smartphone](media/mobile-apps-view-phone-report/power-bi-phone-filter-icon.png) am unteren Rand der Seite. 
2. Verwenden Sie die grundlegenden oder erweiterten Filter, um die Ergebnisse anzuzeigen, an denen Sie interessiert sind.
   
    ![Erweiterter Filter für Power BI-Smartphonebericht](media/mobile-apps-view-phone-report/power-bi-iphone-advanced-filter-toronto.gif)

## <a name="cross-highlight-visuals"></a>Kreuzhervorhebung visuelle Objekte
Die Kreuzhervorhebung visueller Elemente in Smartphoneberichten erfolgt auf die gleiche Weise wie im Power BI-Dienst und in Berichten auf Smartphones in der Querformatansicht: Wenn Sie Daten in einem visuellen Element auswählen, werden zugehörige Daten in den anderen visuellen Elementen auf dieser Seite hervorgehoben.

Erfahren Sie mehr über das [Filtern und Hervorheben in Power BI](power-bi-reports-filters-and-highlighting.md).

## <a name="select-visuals"></a>Auswählen visueller Elemente
Wenn Sie in Smartphoneberichten ein visuelles Element auswählen, wird dieses hervorgehoben, und es erhält den Fokus. Gesten für den Zeichenbereich werden unwirksam.

Sobald das visuelle Element ausgewählt ist, können Sie Aktionen in ihm ausführen, z. B. in ihm scrollen. Um die Auswahl eines visuellen Elements aufzuheben, tippen Sie auf eine beliebige Position außerhalb des visuellen Elements.

## <a name="open-visuals-in-focus-mode"></a>Öffnen visueller Elemente im Fokusmodus
Smartphoneberichte bieten zudem einen Fokusmodus. In diesem können Sie ein Visual in einer größeren Ansicht öffnen und analysieren sowie den Bericht genauer untersuchen.

* Tippen Sie in einem Smartphonebericht auf die Auslassungspunkte (**...**) in der oberen rechten Ecke eines visuellen Elements und dann auf **Auf Fokusmodus erweitern**.
  
    ![Auf Fokusmodus erweitern](media/mobile-apps-view-phone-report/power-bi-phone-report-focus-mode.png)

Ihre Aktionen im Fokusmodus werden im Berichtszeichenbereich übernommen und umgekehrt, um Untersuchungen ohne Unterbrechungen zu ermöglichen. Wenn Sie z. B. einen Wert in einem visuellen Element hervorheben und dann zum gesamten Bericht zurückkehren, wird der gesamte Bericht nach dem Wert gefiltert, den Sie im visuellen Element hervorgehoben haben.

Aufgrund der Einschränkungen durch die Bildschirmgröße können manche Aktionen nur im Fokusmodus ausgeführt werden:

* **Durchführen eines Drilldowns** auf die Informationen in einem visuellen Element. Weitere Informationen über das Durchführen von [Drilldown und Drillup](mobile-apps-view-phone-report.md#drill-down-in-a-visual) in einem Smartphonebericht finden Sie weiter unten.
* **Sortieren** der Werte im visuellen Element.
* **Zurücksetzen**: Löschen der Untersuchungsschritte, die Sie für ein visuelles Element durchgeführt haben, und Wiederherstellen der Definition, die bei der Erstellung des Berichts festgelegt wurde.
  
    Um alle Untersuchungsschritte aus einem visuellen Element zu löschen, tippen Sie auf die Auslassungspunkte (**...** ) und dann auf **Zurücksetzen**.
  
    ![Zurücksetzen](media/mobile-apps-view-phone-report/power-bi-phone-report-revert-levels.png)
  
    Die Option zum Zurücksetzen ist auf Berichtsebene verfügbar, wobei alle Untersuchungsschritte aus sämtlichen visuellen Elementen gelöscht werden, oder auf der Ebene des visuellen Elements. Dabei werden alle Untersuchungsschritte aus dem speziellen visuellen Element gelöscht.   

## <a name="drill-down-in-a-visual"></a>Durchführen von Drilldown in einem visuellen Element
Wenn in einem visuellen Element Hierarchieebenen definiert sind, können Sie einen Drilldown auf die Detailinformationen im visuellen Element durchführen und dann wieder zur höheren Ebene zurückkehren. Sie können im Power BI-Dienst und in Power BI Desktop [Drilldowns in einem Visual](power-bi-visualization-drill-down.md) ausführen. Drilldowns sind nur bei Power BI-Berichten möglich, die auf einem Smartphone angezeigt werden und für Smartphones optimiert wurden. 

1. Tippen Sie in einem Bericht auf einem Smartphone auf die Auslassungspunkte (**...**) in der oberen rechten Ecke und dann auf **Auf Fokusmodus erweitern**.
   
    ![Auf Fokusmodus erweitern](media/mobile-apps-view-phone-report/power-bi-phone-report-focus-mode.png)
   
    In diesem Beispiel zeigen die Balken die Werte für Bundesländer an.
2. Tippen Sie auf das Symbol „Durchsuchen“ ![Symbol „Durchsuchen“](media/mobile-apps-view-phone-report/power-bi-phone-report-explore-icon.png) in der unteren linken Ecke.
   
    ![Modus „Durchsuchen“](media/mobile-apps-view-phone-report/power-bi-phone-report-explore-mode.png)
3. Tippen Sie auf **Nächste Ebene anzeigen** oder **Auf nächste Ebene erweitern**.
   
    ![Auf nächste Ebene erweitern](media/mobile-apps-view-phone-report/power-bi-phone-report-expand-levels.png)
   
    Jetzt zeigen die Balken die Werte für Städte an.
   
    ![Erweiterte Ebenen](media/mobile-apps-view-phone-report/power-bi-phone-report-expanded-levels.png)
4. Wenn Sie auf den Pfeil in der oberen linken Ecke tippen, kehren Sie zum Smartphonebericht zurück, in dem die Werte noch auf die untere Ebene erweitert sind.
   
    ![Immer noch auf die untere Ebene erweitert](media/mobile-apps-view-phone-report/power-bi-back-to-phone-report-expanded-levels.png)
5. Um auf die ursprüngliche Ebene zurückzukehren, tippen Sie erneut auf die Auslassungspunkte (**...** ) und dann auf **Zurücksetzen**.
   
    ![Zurücksetzen](media/mobile-apps-view-phone-report/power-bi-phone-report-revert-levels.png)

## <a name="next-steps"></a>Nächste Schritte
* [Erstellen von Berichten, die für die Power BI-Smartphone-Apps optimiert sind](desktop-create-phone-report.md)
* [Erstellen einer Telefonansicht eines Dashboards in Power BI](service-create-dashboard-mobile-phone-view.md)
* [Erstellen von dynamischen Visuals, die für eine beliebige Größe optimiert sind](desktop-create-responsive-visuals.md)
* Weitere Fragen? [Stellen Sie Ihre Frage in der Power BI-Community.](http://community.powerbi.com/)

