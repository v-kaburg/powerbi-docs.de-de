---
title: 'Project Online: Verbinden mit Daten über Power BI Desktop'
description: 'Project Online: Verbinden mit Daten über Power BI Desktop'
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 12/06/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: a0888c09a9d92123ba08c8cbc27ff8614b8c142a
ms.sourcegitcommit: 72c9d9ec26e17e94fccb9c5a24301028cebcdeb5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/07/2018
ms.locfileid: "53025625"
---
# <a name="project-online-connect-to-data-through-power-bi-desktop"></a>Project Online: Verbinden mit Daten über Power BI Desktop
Sie können sich mit Daten in Project Online über Power BI Desktop verbinden.

## <a name="step-1-download-power-bi-desktop"></a>Schritt 1: Laden Sie Power BI Desktop herunter
1. [Laden Sie Power BI Desktop herunter](http://go.microsoft.com/fwlink/?LinkID=521662), und führen Sie das Installationsprogramm aus, um **Power BI Desktop** auf Ihrem Computer zu installieren.

## <a name="step-2-connect-to-project-online-with-odata"></a>Schritt 2: Verbinden mit Project Online mit OData
1. Öffnen Sie **Power BI Desktop**.
2. Klicken Sie auf der *Willkommensseite* auf **Daten abrufen**.
3. Wählen Sie **OData-Feed**, und klicken Sie auf **Verbinden**.
4. Geben Sie die Adresse des OData-Feeds in das URL-Feld ein und klicken Sie dann auf „OK“.
   
   Wenn die Adresse für die Project Web App-Website https://\<Mandantenname\>.sharepoint.com/sites/pwa ähnelt, lautet die Adresse, die Sie für den OData-Feed eingeben https://\<Mandantenname\>.sharepoint.com/sites/pwa/\_api/Projectdata.
   
   In unserem Beispiel verwenden wir https://contoso.sharepoint.com/sites/pwa/default.aspx
5. Power BI Desktop fordert Sie zur Authentifizierung mit Ihrem Office 365-Konto auf. Wählen Sie das Organisationskonto aus und geben Sie dann Ihre Anmeldeinformationen ein.
   
   ![](media/desktop-project-online-connect-to-data/image.png)

Bitte beachten Sie, dass das Konto, mit dem Sie sich mit dem OData-Feed verbinden, mindestens einen Portfoliobetrachterzugriff auf die Website der Project-Web-App haben muss. 

Von hier aus können Sie auswählen, zu welchen Tabellen Sie eine Verbindung herstellen und eine Abfrage erstellen möchten.  Sie möchten einen Überblick über die ersten Schritte?  Im folgenden Blogbeitrag wird gezeigt, wie ein Burndowndiagramm aus Ihren Project Online-Daten erstellt wird.  Im Blogbeitrag wird auf Power Query zum Verbinden mit Project Online verwiesen, wobei dies auch für Power BI Desktop gilt.

[Creating burndown charts for Project using Power Pivot and Power Query („Erstellen von Burndowndiagrammen für Project mithilfe von Power Pivot und Power Query“, auf Englisch)](http://blogs.office.com/2014/03/24/creating-burndown-charts-for-project-using-power-pivot-and-power-query/)

