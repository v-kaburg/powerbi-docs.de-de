---
title: PowerShell-Cmdlets, REST-APIs und das .NET SDK für Administratoren
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
ms.openlocfilehash: 1ed4298e4ed4cddcdf965bd427c654cab6adf1e6
ms.sourcegitcommit: 46f1ba3f972f6e64bce05ad0fd527b27c49aedd6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/20/2018
ms.locfileid: "52157009"
---
# <a name="powershell-cmdlets-rest-apis-and-net-sdk-for-power-bi-administration"></a>PowerShell-Cmdlets, REST-APIs und das .NET SDK für die Power BI-Verwaltung
Mit Power BI können Administratoren für häufige Tasks mit PowerShell-Cmdlets Skripts erstellen. Außerdem stellt es REST-APIs zur Verfügung und bietet ein .NET SDK zum Entwickeln von Verwaltungslösungen. In diesem Thema finden Sie eine Liste von Cmdlets und dazugehörigen SDK-Methoden und REST-API-Endpunkten. Weitere Informationen finden Sie unter:

- [PowerShell-Download](https://www.powershellgallery.com/packages/MicrosoftPowerBIMgmt/) und [PowerShell-Dokumentation](https://docs.microsoft.com/powershell/power-bi/overview?view=powerbi-ps)
- [REST-API-Dokumentation](https://docs.microsoft.com/rest/api/power-bi/admin)
- [.NET SDK-Download](https://www.nuget.org/packages/Microsoft.PowerBI.Api/)

| **Name des Cmdlet** | **Aliase** | **SDK-Methode** | **REST-API-Endpunkt** | **Beschreibung** |
| --- | --- | --- | --- | --- |
| **Get-PowerBIDatasource** | N/V | Datasets\_GetDataSourcesAsAdmin | /v1.0/myorg/admin/datasets/{datasetkey}/datasources | Ruft die Datenquellen eines angegebenen Datasets ab |
| **Get-PowerBIDataset** | N/V | Datasets\_GetDatasetsAsAdmin | /v1.0/myorg/admin/datasets | Ruft die Liste aller Datasets im Power BI-Mandanten ab |
| **Get-PowerBIWorkspace** | **Get-PowerBIGroup** | Groups\_GetGroupsAsAdmin | /v1.0/myorg/admin/groups | Ruft die Liste aller Arbeitsbereiche im Power BI-Mandanten ab |
| **Add-PowerBIWorkspaceUser** | **Add-PowerBIGroupUser** |Groups\_AddUserAsAdmin | /v1.0/myorg/admin/groups/{groupId}/users | Fügt einen Benutzer einem angegeben Arbeitsbereich als Mitglied hinzu |
| **Remove-PowerBIWorkspaceUser** | **Remove-PowerBIGroupUser** | Groups\_DeleteUserAsAdmin | /v1.0/myorg/admin/groups/{groupId}/users/{user} | Entfernt die Mitgliedschaft eines Benutzers aus einem angegebenen Arbeitsbereich |
| **Restore-PowerBIWorkspace** |**Restore-PowerBIGroup** | Groups\_RestoreDeletedGroupAsAdmin | /v1.0/myorg/admin/groups/{groupId}/restore | Stellt einen gelöschten Arbeitsbereich wieder her |
| **Set-PowerBIWorkspace** |**Set-PowerBIGroup** | Groups\_UpdateGroupAsAdmin | /v1.0/myorg/admin/groups/{groupId} | Aktualisiert die Eigenschaften eines angegebenen Arbeitsbereichs |
| **Get-PowerBIDataset -WorkspaceId** | N/V | Groups\_GetDatasetsAsAdmin | /v1.0/myorg/admin/groups/{group\_id}/datasets | Ruft die Datasets in einem Arbeitsbereich ab |
| **Export-PowerBIReport** | N/V | Reports\_ExportReportAsAdmin | N/V | Exportiert einen angegebenen Bericht in eine lokale Datei |
| **Get-PowerBIReport** | N/V | Reports\_GetReportsAsAdmin | /v1.0/myorg/admin/reports | Ruft die Liste aller Berichte im Power BI-Mandanten ab |
| **Get-PowerBIDashboard** | N/V | Dashboards\_GetDashboardsAsAdmin | /v1.0/myorg/admin/dashboards | Ruft die Liste aller Dashboard im Power BI-Mandanten ab |
| **Get-PowerBIDashboard** | N/V | Groups\_GetDashboardsAsAdmin | /v1.0/myorg/admin/groups/{group\_id}/dashboards | Ruft die Dashboards in einem angegebenen Arbeitsbereich ab |
| **Get-PowerBITile** | **Get-PowerBIDashboardTile** | Dashboards\_GetTilesAsAdmin | /v1.0/myorg/admin/dashboards/{dashboard\_id}/tiles | Ruft die Kacheln eines angegebenen Dashboards ab |
| **Get-PowerBIReport** | N/V | Groups\_GetReportsAsAdmin | /v1.0/myorg/admin/groups/{group\_id}/reports | Ruft die Berichte in einem angegebenen Arbeitsbereich ab |
| **Get-PowerBIImport** | N/V | Imports\_GetImportsAsAdmin | /v1.0/myorg/admin/imports | Ruft die Liste aller Importe im Power BI-Mandanten ab |
| **Connect-PowerBIServiceAccount** | **Login-PowerBI** &  **Login-PowerBIServiceAccount** | N/V | N/V | Anmelden bei Power BI und Starten einer Sitzung |
| **Disconnect-PowerBIServiceAccount** | **Logout-PowerBI** & **Logout-PowerBIServiceAccount** | N/V | N/V | Abmelden von Power BI und Beenden der laufenden Sitzung |
| **Invoke-PowerBIRestMethod**| N/V | N/V | N/V | Senden willkürlicher REST-API-Aufrufe an Power BI |
| **Get-PowerBIAccessToken**| N/V | N/V | N/V | Abrufen des Power BI-Zugriffschlüssels in einer Sitzung |
| **Resolve-PowerBIError**| N/V | N/V | N/V | Abrufen ausführlicher Fehlerinformationen zu Cmdlet-Aufrufen, die mit einem Fehler abgeschlossen wurden |