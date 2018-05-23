---
title: Herstellen einer Verbindung mit ServiceNow mithilfe von Power BI
description: ServiceNow für Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 4b05fcc005f821c4fee24071f28651b5df57709c
ms.sourcegitcommit: 998b79c0dd46d0e5439888b83999945ed1809c94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/17/2018
---
# <a name="connect-to-servicenow-with-power-bi-for-incident-reporting"></a>Herstellen einer Verbindung mit ServiceNow mithilfe von Power BI für Berichte über Vorfälle
ServiceNow bietet mehrere Produkte und Lösungen für die Optimierung Ihres Unternehmens, u. a. Unternehmens-, Betriebs- und IT-Verwaltung. Dieses Inhaltspaket umfasst mehrere Berichte und Informationen zu offenen, kürzlich gelösten und kürzlich geschlossenen Vorfällen.  

Stellen Sie eine Verbindung mit dem Power BI-Inhaltspaket für [ServiceNow-Vorfälle](https://app.powerbi.com/getdata/services/servicenow) her.

## <a name="how-to-connect"></a>Herstellen der Verbindung
1. Wählen Sie unten im linken Navigationsbereich **Daten abrufen** aus.
   
   ![](media/service-connect-to-servicenow/pbi_getdata.png) 
2. Wählen Sie im Feld **Dienste** die Option **Abrufen**aus.
   
   ![](media/service-connect-to-servicenow/pbi_getservices.png) 
3. Wählen Sie **ServiceNow-Vorfälle** \> **Abrufen** aus.
   
   ![](media/service-connect-to-servicenow/connect.png)
4. Geben Sie die URL der ServiceNow-Instanz und den Bereich für die zu importierenden Tage/Datensätze ein. Beachten Sie, dass der Importvorgang beendet wird, sobald ein Grenzwert erreicht wird.
   
   ![](media/service-connect-to-servicenow/params.png)
5. Wenn Sie dazu aufgefordert werden, geben Sie Ihre ServiceNow-Anmeldeinformationen für die **Standardauthentifizierung** ein. Beachten Sie, dass das einmalige Anmelden zurzeit nicht unterstützt wird. Weitere Informationen zu den Systemanforderungen finden Sie unten.
   
   ![](media/service-connect-to-servicenow/creds.png)
6. Nach Abschluss der Anmeldung wird den Importvorgang gestartet. Nach Abschluss des Vorgangs werden im Navigationsbereich ein neues Dashboard, ein Bericht und ein Modell angezeigt. Wählen Sie das Dashboard aus, um die importierten Daten anzuzeigen.
   
    ![](media/service-connect-to-servicenow/dashboard.png)

**Was nun?**

* Versuchen Sie, am oberen Rand des Dashboards [im Q&A-Feld eine Frage zu stellen](power-bi-q-and-a.md).
* [Ändern Sie die Kacheln](service-dashboard-edit-tile.md) im Dashboard.
* [Wählen Sie eine Kachel aus](service-dashboard-tiles.md), um den zugrunde liegenden Bericht zu öffnen.
* Ihr Dataset ist auf eine tägliche Aktualisierung festgelegt. Sie können jedoch das Aktualisierungsintervall ändern oder es über **Jetzt aktualisieren** nach Bedarf aktualisieren.

## <a name="system-requirements"></a>Systemanforderungen
Zum Herstellen der Verbindung benötigen Sie Folgendes:  

* Ein Konto, das mit Standardauthentifizierung auf „IhreOrganisation.service-now.com“ zugreifen kann (einmaliges Anmelden wird in dieser Version nicht unterstützt)  
* Das Konto muss die Rolle „rest_service“ und Lesezugriff auf die Liste der Vorfälle haben.  

## <a name="troubleshooting"></a>Problembehandlung
Wenn beim Laden ein Fehler mit den Anmeldeinformationen auftritt, überprüfen Sie die unten aufgeführten Zugriffsanforderungen. Wenn Sie über die richtigen Berechtigungen verfügen und trotzdem Probleme auftreten, wenden Sie sich an Ihren ServiceNow-Administrator, um sicherzustellen, dass Sie über alle zusätzlichen Berechtigungen verfügen, die möglicherweise für Ihre benutzerdefinierte Instanz benötigt werden.

Überprüfen Sie bei langen Ladezeiten die Anzahl der Vorfälle und die Anzahl der Tage, die für die Verbindung angegeben wurden, und erwägen Sie, die Werte zu reduzieren.

## <a name="next-steps"></a>Nächste Schritte
[Erste Schritte mit Power BI](service-get-started.md)

[Power BI – Grundkonzepte](service-basic-concepts.md)

