---
title: 'Project Online: Verbinden mit Daten über Power BI Desktop'
description: 'Project Online: Verbinden mit Daten über Power BI Desktop'
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/08/2019
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: b0dc84d7b2d8da0df8a9e61a43f35898d197c188
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2019
ms.locfileid: "65513739"
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
   
   Wenn die Adresse für Ihre Website für Project Web App *https://\<"tenantname"\>.sharepoint.com/sites/pwa*, dann ist die Adresse, die Sie für den OData-Feed eingeben *https://\<"tenantname"\>.sharepoint.com/sites/pwa/\_-api/Projectdata*.
   
   In unserem Beispiel verwenden wir https://contoso.sharepoint.com/sites/pwa/default.aspx
5. Power BI Desktop fordert Sie zur Authentifizierung mit Ihrem Office 365-Konto auf. Wählen Sie das Organisationskonto aus und geben Sie dann Ihre Anmeldeinformationen ein.
   
   ![](media/desktop-project-online-connect-to-data/image.png)

Das Konto, das Sie verwenden, um eine Verbindung herstellen, mit dem OData-Feed mindestens verfügen muss portfoliobetrachterzugriff auf die Project Web App-Website. 

Von hier aus können Sie auswählen, zu welchen Tabellen Sie eine Verbindung herstellen und eine Abfrage erstellen möchten.  Sie möchten einen Überblick über die ersten Schritte?  Im folgenden Blogbeitrag veranschaulicht, wie eine brennen Sie das Diagramm aus Ihren Project Online-Daten zu erstellen.  Im Blogbeitrag wird auf Power Query zum Verbinden mit Project Online verwiesen, wobei dies auch für Power BI Desktop gilt.

[Brennen Sie die Diagramme erstellen für mithilfe von Power Pivot und Power Query-Projekt](http://blogs.office.com/2014/03/24/creating-burndown-charts-for-project-using-power-pivot-and-power-query/)

