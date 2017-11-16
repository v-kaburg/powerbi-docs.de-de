---
title: Anzeigen lokaler Berichte und KPIs in den mobilen Power BI-Apps
description: "Die mobile Power BI-Apps bieten touchfähigen, mobilen Livezugriff auf Ihre lokalen Geschäftsdaten in SQL Server Reporting Services und Power BI-Berichtsserver."
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
ms.openlocfilehash: 99fceab5904deaa510edd213c349dcfb2e38ac28
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2017
---
# <a name="view-on-premises-report-server-reports-and-kpis-in-the-power-bi-mobile-apps"></a>Anzeigen lokaler Berichte und KPIs eines Berichtsservers in den mobilen Power BI-Apps
Gilt für:

| ![iPhone](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/iphone-logo-50-px.png) | ![iPad](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/ipad-logo-50-px.png) | ![Android-Smartphone](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/android-phone-logo-50-px.png) | ![Android-Tablet](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/android-tablet-logo-50-px.png) |
|:--- |:--- |:--- |:--- |
| iPhones |iPads |Android-Telefone |Android-Tablets |

Die mobilen Power BI-Apps bieten touchfähigen, mobilen Livezugriff auf Ihre lokalen Geschäftsdaten in Power BI-Berichtsserver und SQL Server 2016 Reporting Services (SSRS). 

 ![Report Server-Startseite in den mobilen Apps](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-ipad-pbi-report-server-home.png)

## <a name="first-things-first"></a>Das Wichtigste zuerst
**Die mobilen Apps dienen zum Anzeigen von Power BI-Inhalten und nicht zu deren Erstellung.**

* Sie und andere Berichtersteller in Ihrer Organisation können [Power BI-Berichte mit Power BI Desktop erstellen und dann im Webportal von Power BI-Berichtsserver veröffentlichen](report-server/quickstart-create-powerbi-report.md). 
* Sie können [KPIs direkt im Webportal](https://docs.microsoft.com/sql/reporting-services/working-with-kpis-in-reporting-services) erstellen, sie mithilfe von Ordnern organisieren und als Favoriten markieren, damit Sie sie später einfach wiederfinden. 
* [Erstellen Sie mobile Reporting Services-Berichte](https://docs.microsoft.com/sql/reporting-services/mobile-reports/create-mobile-reports-with-sql-server-mobile-report-publisher) mit dem SQL Server 2016 Enterprise Edition Mobile Report Publisher, und veröffentlichen Sie sie im [Reporting Services-Webportal](https://docs.microsoft.com/sql/reporting-services/web-portal-ssrs-native-mode).  

Stellen Sie dann in den mobilen Power BI-Apps eine Verbindung mit bis zu fünf Berichtsservern her, um die Power BI-Berichte und KPIs in Ordnern organisiert oder als Favoriten zusammengestellt anzuzeigen. 

## <a name="explore-samples-in-the-mobile-apps-without-a-server-connection"></a>Untersuchen von Beispielen in den mobilen Apps ohne Serververbindung
Auch wenn Sie keinen Zugriff auf ein Reporting Services-Webportal haben, können Sie trotzdem die Features von mobilen Reporting Services-Berichten und KPIs untersuchen. 

1. Tippen Sie auf die globale Navigationsschaltfläche ![Globale Navigationsschaltfläche](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-iphone-global-nav-button.png) in der linken oberen Ecke, und tippen Sie anschließend rechts oben auf das Zahnradsymbol ![Zahnradsymbol](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-ios-settings-icon.png).
2. Tippen Sie auf **Reporting Services-Beispiele**, und durchsuchen Sie diese, um mit den beispielhaften KPIs und mobilen Berichten zu interagieren.
   
   ![Beispiele für Reporting Services](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-iphone-ssrs-samples.png)

## <a name="connect-to-an-on-premises-server"></a>Herstellen einer Verbindung mit einem lokalen Server
In den mobilen Power BI-Apps können Sie lokale Power BI-Berichte, mobile Reporting Services-Berichte und KPIs anzeigen. 

1. Öffnen Sie auf Ihrem Mobilgerät die Power BI-App.
2. Wenn Sie sich noch nicht bei Power BI angemeldet haben, tippen Sie auf **Berichtsserver**.
   
   ![Anmelden bei einem Berichtsserver](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-connect-to-rs-login.png)
   
   Wenn Sie sich bereits bei der Power BI-App angemeldet haben, tippen Sie auf die globale Navigationsschaltfläche ![Globale Navigationsschaltfläche](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-iphone-global-nav-button.png), und tippen Sie anschließend auf das Zahnradsymbol ![Zahnradsymbol](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-ios-settings-icon.png) in der rechten oberen Ecke.
3. Tippen Sie auf **Mit Server verbinden**.
   
    ![Mit Server verbinden](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-android-server-sign-in.png)
4. Geben Sie die Adresse des Servers sowie Ihren Benutzernamen und das Kennwort ein. Verwenden Sie dieses Format für die Adresse des Servers:
   
     `http://<servername>/reports`
   
     OR
   
     `https://<servername>/reports`
   
   > [!NOTE]
   > Geben Sie vor der Verbindungszeichenfolge **http** oder **https** ein.
   > 
   > 
   
    ![Dialogfeld „Mit Server verbinden“](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-ios-connect-to-server-dialog.png)
5. (Optional) Unter **Erweiterte Optionen** können Sie einen Anzeigenamen für den Server eingeben.
6. Jetzt wird auf der linken Navigationsleiste der Server angezeigt – in diesem Beispiel lautet dessen Name „power bi report server“.
   
   ![Berichtsserver im linken Navigationsbereich](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-iphone-left-nav-report-server.png)

## <a name="view-power-bi-reports-and-kpis-in-the-power-bi-app"></a>Anzeigen von Power BI-Berichten und KPIs in der Power BI-App
Power BI-Berichte, mobile Reporting Services-Berichte und KPIs werden in den gleichen Ordnern wie im Reporting Services-Webportal angezeigt. 

* Tippen Sie auf einen Power BI-Bericht ![Symbol für Power BI-Bericht](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-rs-mobile-report-icon.png). Er wird im Querformat geöffnet, und Sie können in der Power BI-App mit ihm interagieren.
  
    ![Power BI-Bericht](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-iphone-report-server-report.png)
* In Power BI Desktop können die Besitzer von Berichten [einen Bericht für die mobilen Power BI-Apps optimieren](desktop-create-phone-report.md). Auf dem Mobiltelefon sind optimierte Berichte mit einem speziellen Symbol, ![Symbol für optimierten Power BI-Bericht](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-rs-mobile-optimized-icon.png) gekennzeichnet, und sie weisen ein besonderes Layout auf.
  
    ![Für Mobilgeräte optimierter Power BI-Bericht](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-rs-mobile-optimized-report.png)
* Tippen Sie auf einen KPI, um diesen im Fokusmodus anzuzeigen.
  
    ![KPI im Fokusmodus](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/pbi_ipad_ssmrp_tile.png)

## <a name="view-your-favorite-kpis-and-reports"></a>Anzeigen Ihrer bevorzugten KPIs und Berichte
Sie können KPIs und Berichte im Webportal als Favoriten markieren und dann bequem neben den als Favoriten gespeicherten Power BI-Dashboards in einem Ordner auf Ihrem Mobilgerät anzeigen.

* Tippen Sie auf **Favoriten**.
  
   ![Favoriten im linken Navigationsbereich](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-ipad-faves-pbi-report-server.png)
  
   Ihre bevorzugten KPIs und Berichte aus dem Webportal befinden sich zusammen mit Power BI-Dashboards im Power BI-Dienst alle auf dieser Seite:
  
   ![Power BI-Berichte und -Dashboard auf der Seite „Favoriten“](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-ipad-favorites.png)

## <a name="remove-a-connection-to-a-report-server"></a>Entfernen einer Verbindung mit einem Berichtsserver
1. Tippen Sie unten auf der linken Navigationsleiste auf **Einstellungen**.
2. Tippen Sie auf den Servernamen, dessen Verbindung Sie trennen möchten.
3. Tippen Sie auf **Server entfernen**.

## <a name="next-steps"></a>Nächste Schritte
* [Erste Schritte mit Power BI](service-get-started.md)  
* Haben Sie Fragen? [Stellen Sie Ihre Frage in der Power BI-Community.](http://community.powerbi.com/)

