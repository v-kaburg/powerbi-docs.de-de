---
title: PowerShell-Cmdlets, REST-APIs und das .NET SDK für die Power BI-Verwaltung
description: Erfahren Sie, wie Sie Power BI mit Skripts und durch das Programmieren von APIs verwalten können.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-admin
ms.topic: overview
ms.date: 06/25/2018
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: ffb2ae077add5756af63f07d8f3da830e075e0b4
ms.sourcegitcommit: 2a7bbb1fa24a49d2278a90cb0c4be543d7267bda
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2018
ms.locfileid: "36945294"
---
# <a name="powershell-cmdlets-rest-apis-and-net-sdk-for-power-bi-administration"></a>PowerShell-Cmdlets, REST-APIs und das .NET SDK für die Power BI-Verwaltung
Mit Power BI können Administratoren für häufige Tasks mit PowerShell-Cmdlets Skripts erstellen. Außerdem stellt es REST-APIs zur Verfügung und bietet ein .NET SDK zum Entwickeln von Verwaltungslösungen. In diesem Thema finden Sie eine Liste von Cmdlets und dazugehörigen SDK-Methoden und REST-API-Endpunkten. Weitere Informationen finden Sie unter:

  - [PowerShell-Download](https://www.powershellgallery.com/packages/MicrosoftPowerBIMgmt/) und [PowerShell-Dokumentation](https://docs.microsoft.com/powershell/power-bi/overview?view=powerbi-ps)
  - [REST-API-Dokumentation](https://docs.microsoft.com/rest/api/power-bi/admin)
  - [.NET SDK-Download](https://www.nuget.org/packages/Microsoft.PowerBI.Api/) 


| **Name des Cmdlet** | **SDK-Methode** | **REST-API-Endpunkt** | **Beschreibung** |
| --- | --- | --- | --- |
| **Get-PowerBIDatasource** | Datasets\_GetDataSourcesAsAdmin | /v1.0/myorg/admin/datasets/{datasetkey}/datasources | Ruft die Datenquellen eines angegebenen Datasets ab |
| **Get-PowerBIDataset** | Datasets\_GetDatasetsAsAdmin | /v1.0/myorg/admin/datasets | Ruft die Liste aller Datasets im Power BI-Mandanten ab |
| **Get-PowerBIWorkspace** | Groups\_GetGroupsAsAdmin | /v1.0/myorg/admin/groups | Ruft die Liste aller Arbeitsbereiche im Power BI-Mandanten ab |
| **Add-PowerBIWorkspaceUser** | Groups\_AddUserAsAdmin | /v1.0/myorg/admin/groups/{groupId}/users | Fügt einen Benutzer einem angegeben Arbeitsbereich als Mitglied hinzu |
| **Remove-PowerBIWorkspaceUser** | Groups\_DeleteUserAsAdmin | /v1.0/myorg/admin/groups/{groupId}/users/{user} | Entfernt die Mitgliedschaft eines Benutzers aus einem angegebenen Arbeitsbereich |
| **Restore-PowerBIWorkspace** | Groups\_RestoreDeletedGroupAsAdmin | /v1.0/myorg/admin/groups/{groupId}/restore | Stellt einen gelöschten Arbeitsbereich wieder her |
| **Set-PowerBIWorkspace** | Groups\_UpdateGroupAsAdmin | /v1.0/myorg/admin/groups/{groupId} | Aktualisiert die Eigenschaften eines angegebenen Arbeitsbereichs |
| **Get-PowerBIDataset -WorkspaceId** | Groups\_GetDatasetsAsAdmin | /v1.0/myorg/admin/groups/{group\_id}/datasets | Ruft die Datasets in einem Arbeitsbereich ab |
| **Export-PowerBIReport** | Reports\_ExportReportAsAdmin | N/V | Exportiert einen angegebenen Bericht in eine lokale Datei |
| **Get-PowerBIReport** | Reports\_GetReportsAsAdmin | /v1.0/myorg/admin/reports | Ruft die Liste aller Berichte im Power BI-Mandanten ab |
| **Get-PowerBIDashboard** | Dashboards\_GetDashboardsAsAdmin | /v1.0/myorg/admin/dashboards | Ruft die Liste aller Dashboard im Power BI-Mandanten ab |
| **Get-PowerBIDashboard -WorkspaceId** | Groups\_GetDashboardsAsAdmin | /v1.0/myorg/admin/groups/{group\_id}/dashboards | Ruft die Dashboards in einem angegebenen Arbeitsbereich ab |
| **Get-PowerBITile -DashboardId** | Dashboards\_GetTilesAsAdmin | /v1.0/myorg/admin/dashboards/{dashboard\_id}/tiles | Ruft die Kacheln eines angegebenen Dashboards ab |
| **Get-PowerBIReport -WorkspaceId** | Groups\_GetReportsAsAdmin | /v1.0/myorg/admin/groups/{group\_id}/reports | Ruft die Berichte in einem angegebenen Arbeitsbereich ab |
| **Get-PowerBIImport** | Imports\_GetImportsAsAdmin | /v1.0/myorg/admin/imports | Ruft die Liste aller Importe im Power BI-Mandanten ab |
| **Connect-PowerBIServiceAccount** | N/V | N/V | Anmelden bei Power BI und Starten einer Sitzung |
| **Disconnect-PowerBIServiceAccount** | N/V | N/V | Abmelden von Power BI und Beenden der laufenden Sitzung |
| **Invoke-PowerBIRestMethod** | N/V | N/V | Senden willkürlicher REST-API-Aufrufe an Power BI |
| **Get-PowerBIAccessToken** | N/V | N/V | Abrufen des Power BI-Zugriffschlüssels in einer Sitzung |
| **Resolve-PowerBIError** | N/V | N/V | Abrufen ausführlicher Fehlerinformationen zu Cmdlet-Aufrufen, die mit einem Fehler abgeschlossen wurden |