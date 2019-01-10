---
title: Verwenden von Überwachung in der Organisation
description: Erfahren Sie, wie Sie mit der Überwachung in Power BI ergriffene Maßnahmen überwachen und untersuchen können. Sie können das Security & Compliance Center oder PowerShell verwenden.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-admin
ms.topic: conceptual
ms.date: 11/16/2018
ms.author: mblythe
ms.custom: seodec18
LocalizationGroup: Administration
ms.openlocfilehash: d9cf6255cfa57790c13ee1fc9d3201860552863b
ms.sourcegitcommit: c09241803664643e1b2ba0c150e525e1262ca466
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2019
ms.locfileid: "54072357"
---
# <a name="using-auditing-within-your-organization"></a>Verwenden von Überwachung in der Organisation

Es kann wichtig sein zu wissen, wer welche Aktion für welches Element im Power BI-Mandanten ausführt. Dies kann Ihrer Organisation bei der Einhaltung von Anforderungen helfen, was beispielsweise die Einhaltung gesetzlicher Bestimmungen und die Dokumentverwaltung betrifft. Verwenden Sie Power BI-Überwachung, um von Benutzern ausgeführte Aktionen wie „Bericht anzeigen“ und „Dashboard anzeigen“ zu überwachen. Sie können die Überwachung nicht dazu verwenden, Berechtigungen zu überwachen.

Sie arbeiten mit der Überwachung im Office 365 Security & Compliance Center oder verwenden PowerShell. Die Überwachung baut auf in Exchange Online enthaltener Funktionalität auf, die zur Unterstützung von Power BI automatisch bereitgestellt wird.

Sie können die Überwachungsdaten nach Datumsbereich, Benutzer, Dashboard, Bericht, Dataset und Aktivitätstyp filtern. Sie können die Aktivitäten auch als CSV-Datei (durch Trennzeichen getrennte Datei) herunterladen, um die Analyse offline durchzuführen.

## <a name="requirements"></a>Anforderungen

Die folgenden Anforderungen müssen erfüllt sein, um auf Überwachungsprotokolle zugreifen zu können:

* Sie müssen entweder globaler Administrator sein, oder Ihnen muss in Exchange Online die Rolle „Überwachungsprotokolle“ oder „Überwachungsprotokolle schreibgeschützt“ zugewiesen sein, damit Sie auf das Überwachungsprotokoll zugreifen können. Standardmäßig sind diese Rollen den Rollengruppen „Compliance Management“ und „Organisationsmanagement“ auf der Seite **Berechtigungen** im Exchange Admin Center.

    Um Nicht-Administratorkonten Zugriff auf die Überwachungsprotokolle zu geben, müssen Sie den Benutzer als Mitglied einer dieser Rollengruppen hinzufügen. Alternativ können Sie eine benutzerdefinierte Rollengruppe im Exchange Admin Center erstellen, dieser Gruppe die Rolle „Überwachungsprotokolle“ oder „Überwachungsprotokolle schreibgeschützt“ zuweisen und dann der neuen Rollengruppe das Nicht-Administratorkonto zuweisen. Weitere Informationen finden Sie unter [Verwalten von Rollengruppen in Exchange Online](/Exchange/permissions-exo/role-groups).

    Wenn Sie vom Office 365 Admin Center aus nicht auf das Exchange Admin Center zugreifen können, navigieren Sie zu https://outlook.office365.com/ecp, und melden Sie sich mit Ihren Anmeldeinformationen an.

* Wenn Sie Zugriff auf das Überwachungsprotokoll haben, aber kein globaler Administrator oder Power BI-Dienst-Administrator sind, haben Sie keinen Zugriff auf das Power BI-Verwaltungsportal. In diesem Fall müssen Sie einen direkten Link zum [Office 365 Security & Compliance Center](https://sip.protection.office.com/#/unifiedauditlog) verwenden.

## <a name="accessing-your-audit-logs"></a>Zugriff auf Überwachungsprotokolle

Um auf Protokolle zuzugreifen, stellen Sie zunächst sicher, dass die Protokollierung in Power BI aktiviert ist. Weitere Informationen finden Sie unter [Überwachungsprotokolle](service-admin-portal.md#audit-logs) in der Dokumentation zum Verwaltungsportal. Es kann bis zu 48 Stunden nach der Aktivierung der Überwachung dauern, bis Sie Überwachungsdaten einsehen können. Wenn Sie nicht umgehend Daten sehen, überprüfen Sie die Überwachungsprotokolle später noch einmal. Es kann zu einer ähnlichen Verzögerung kommen, nachdem Ihnen die Leseberechtigung für Überwachungsprotokolle erteilt wurde und bis Sie die Protokolle ansehen können.

Die Power BI-Überwachungsprotokolle sind direkt über das [Office 365 Security & Compliance Center](https://sip.protection.office.com/#/unifiedauditlog) verfügbar. Es steht auch ein Link aus dem Power BI-Verwaltungsportal zur Verfügung:

1. Wählen Sie rechts oben in Power BI das **Zahnradsymbol** und dann **Verwaltungsportal** aus.

   ![Verwaltungsportal](media/service-admin-auditing/powerbi-admin.png)

1. Wählen Sie **Azure-Überwachungsprotokolle** aus.

1. Wählen Sie **Zum O365 Admin Center wechseln** aus.

   ![O365 Admin Center aufrufen](media/service-admin-auditing/audit-log-o365-admin-center.png)

## <a name="search-only-power-bi-activities"></a>Nur nach Power BI-Aktivitäten suchen

Sie können die Ergebnisse mithilfe dieser Schritte auf Power BI-Aktivitäten einschränken. Eine Liste der Aktivitäten finden Sie in der [Liste der Aktivitäten, die von Power BI überwacht werden](#list-of-activities-audited-by-power-bi) weiter unten in diesem Artikel.

1. Wählen Sie auf der Seite **Überwachungsprotokollsuche** unter **Suche** die Dropdownliste für **Aktivitäten** aus.

2. Wählen Sie **Power BI-Aktivitäten** aus.

   ![Überwachungsprotokollsuche](media/service-admin-auditing/audit-log-search-filter-by-powerbi.png)

3. Klicken oder tippen Sie auf eine beliebige Stelle neben dem Auswahlfeld, um es zu schließen.

Bei Suchvorgängen werden jetzt ausschließlich Power BI-Aktivitäten berücksichtigt.

## <a name="search-the-audit-logs-by-date"></a>Überwachungsprotokolle nach Datum durchsuchen

Sie können die Protokolle mit den Feldern für das **Startdatum** und das **Enddatum** nach Datumsbereichen durchsuchen. Standardmäßig ist der Datumsbereich auf die letzten sieben Tage festgelegt. Datum und Uhrzeit werden in koordinierter Weltzeit (UTC) angezeigt. Der Datumsbereich kann maximal 90 Tage umfassen. 

Wenn der ausgewählte Datumsbereich größer als 90 Tage ist, wird ein Fehler angezeigt. Wenn Sie den maximalen Datumsbereich von 90 Tagen verwenden, wählen Sie die aktuelle Uhrzeit als **Startdatum** aus. Andernfalls erhalten Sie die Fehlermeldung, dass das Startdatum vor dem Enddatum liegt. Wenn Sie die Überwachung innerhalb der letzten 90 Tage aktiviert haben, kann der Datumsbereich nicht vor dem Datum beginnen, an dem die Überwachung aktiviert wurde.

![Nach Datum suchen](media/service-admin-auditing/search-audit-log-by-date.png)

## <a name="search-the-audit-logs-by-users"></a>Überwachungsprotokolle nach Benutzern durchsuchen

Sie können nach Einträgen im Überwachungsprotokoll suchen, die Aktivitäten bestimmter Benutzer betreffen. Geben Sie zu diesem Zweck mindestens einen Benutzernamen in das Feld **Benutzer** ein. Der Benutzername sieht wie eine E-Mail-Adresse aus. Es handelt such um das Konto, mit dem sich Benutzer bei Power BI anmelden. Lassen Sie dieses Feld leer, um Einträge für alle Benutzer (und Dienstkonten) in Ihrer Organisation abzurufen.

![Nach Benutzern suchen](media/service-admin-auditing/search-audit-log-by-user.png)

## <a name="view-search-results"></a>Anzeigen der Suchergebnisse

Nachdem Sie **Suche** ausgewählt haben, werden die Suchergebnisse geladen und nach wenigen Augenblicken unter **Ergebnisse** angezeigt. Dann wird auch die Anzahl der Ergebnisse angegeben. Es werden maximal 1.000 Ereignisse angezeigt. Wenn mehr als 1.000 Ereignisse den Suchkriterien entsprechen, werden die 1.000 neuesten Ereignisse angezeigt.

### <a name="view-the-main-results"></a>Anzeigen der wichtigsten Ergebnisse

Der Bereich **Ergebnisse** enthält die folgenden Informationen für jedes von der Suche zurückgegebene Ereignis. Wählen Sie unter **Ergebnisse** eine Spaltenüberschrift aus, um die Ergebnisse zu sortieren.

| **Spalte** | **Definition** |
| --- | --- |
| Datum (Date) |Datum und Uhrzeit des Ereignisses (im UTC-Format). |
| IP-Adresse |Die IP-Adresse des während der Erfassung verwendeten Geräts. Die IP-Adresse wird als IPv4- oder IPv6-Adresse angezeigt. |
| User |Der Benutzer (oder das Dienstkonto), der die Aktion ausgeführt hat, die das Ereignis ausgelöst hat. |
| Activity |Die Aktivität, die vom Benutzer ausgeführt wurde. Dieser Wert entspricht den Aktivitäten, die Sie in der Dropdownliste **Aktivitäten** ausgewählt haben. Bei Ereignissen aus dem Überwachungsprotokoll für Exchange-Administratoren ist der Wert in dieser Spalte ein Exchange-Cmdlet. |
| Item |Das Objekt, das durch die entsprechende Aktivität erstellt oder verändert wurde. Dies ist beispielsweise eine Datei, die angezeigt oder geändert wurde, oder ein Benutzerkonto, das aktualisiert wurde. Nicht alle Aktivitäten verfügen über einen Wert in dieser Spalte. |
| Detail |Weitere Details zu einer Aktivität. Auch hier besitzen nicht alle Aktivitäten einen Wert. |

### <a name="view-the-details-for-an-event"></a>Anzeigen von Ereignisdetails

Sie können weitere Details zu einem Ereignis anzeigen, indem Sie auf den Ereignisdatensatz in der Liste der Suchergebnisse klicken. Es wird eine Seite **Details** angezeigt, die die detaillierten Eigenschaften aus dem Ereignisdatensatz enthält. Welche Eigenschaften angezeigt werden, hängt von dem Office 365-Dienst ab, bei dessen Verwendung das Ereignis aufgetreten ist. 

Um diese Details anzuzeigen, wählen Sie **Weitere Informationen** aus. Alle Power BI-Einträge weisen einen Wert von 20 für die RecordType-Eigenschaft auf. Informationen zu weiteren Eigenschaften finden Sie unter [Detaillierte Eigenschaften im Überwachungsprotokoll](/office365/securitycompliance/detailed-properties-in-the-office-365-audit-log/).

   ![Überwachungsdetails](media/service-admin-auditing/audit-details.png)

## <a name="export-search-results"></a>Exportieren der Suchergebnisse

Um das Power BI-Überwachungsprotokoll in eine CSV-Datei zu exportieren, gehen Sie wie folgt vor.

1. Wählen Sie **Ergebnisse exportieren** aus.

1. Wählen Sie entweder **Geladene Ergebnisse speichern** oder **Alle Ergebnisse herunterladen** aus.

    ![Ergebnisse exportieren](media/service-admin-auditing/export-auditing-results.png)

## <a name="use-powershell-to-search-audit-logs"></a>Verwenden von PowerShell zum Suchen nach Überwachungsprotokollen

Sie können auch mit PowerShell basierend auf Ihrer Anmeldung auf die Überwachungsprotokolle zugreifen. Das folgende Beispiel zeigt, wie Sie eine Verbindung mit Exchange Online PowerShell herstellen und dann den Befehl [Search-UnifiedAuditLog](/powershell/module/exchange/policy-and-compliance-audit/search-unifiedauditlog?view=exchange-ps/) verwenden, um Power BI-Überwachungsprotokolleinträge abzurufen. Um das Skript auszuführen, müssen Ihnen die entsprechenden Berechtigungen zugeordnet sein, wie im Abschnitt [Anforderungen](#requirements) beschrieben.

```powershell
Set-ExecutionPolicy RemoteSigned

$UserCredential = Get-Credential

$Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection

Import-PSSession $Session
Search-UnifiedAuditLog -StartDate 9/11/2018 -EndDate 9/15/2018 -RecordType PowerBI -ResultSize 1000 | Format-Table | More
```

Weitere Informationen zum Verbinden mit Exchange Online finden Sie unter [Herstellen einer Verbindung mit Exchange Online mithilfe der Remote-PowerShell](/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell/). Ein weiteres Beispiel für die Verwendung von PowerShell mit Überwachungsprotokollen finden Sie unter [Verwenden des Power BI-Überwachungsprotokolls und von PowerShell zum Zuweisen von Power BI Pro-Lizenzen](https://powerbi.microsoft.com/blog/using-power-bi-audit-log-and-powershell-to-assign-power-bi-pro-licenses/).

## <a name="activities-audited-by-power-bi"></a>Von Power BI überwachte Aktivitäten

Die folgenden Aktivitäten werden von Power BI überwacht.

| Anzeigename                                     | Vorgangsname                              | Hinweise                                  |
|---------------------------------------------------|---------------------------------------------|------------------------------------------|
| Added Data source to Power BI gateway (Datenquelle zu Power BI-Gateway hinzugefügt)             | AddDatasourceToGateway                      |                                          |
| Added Power BI folder access (Ordnerzugriff für Power BI hinzugefügt)                      | AddFolderAccess                             | Derzeit nicht verwendet                       |
| Power BI-Gruppenmitglieder hinzugefügt                      | AddGroupMembers                             |                                          |
| Admin attached dataflow storage account to tenant (Administrator hat Dataflow-Speicherkonten zum Mandanten hinzugefügt) | AdminAttachedDataflowStorageAccountToTenant | Derzeit nicht verwendet                       |
| Analyzed Power BI dataset (Power BI-Dataset analysiert)                         | AnalyzedByExternalApplication               |                                          |
| Analyzed Power BI report (Power BI-Bericht analysiert)                          | AnalyzeInExcel                              |                                          |
| Binden von Power BI-Datasets an Gateways                | BindToGateway                               |                                          |
| Changed capacity state (Kapazitätsstatus geändert)                            | ChangeCapacityState                         |                                          |
| Changed capacity user assignment (Benutzerzuweisung für die Kapazität geändert)                  | UpdateCapacityUsersAssignment               |                                          |
| Changed Power BI dataset connections (Power BI-Verbindungen mit Datasets geändert)              | SetAllConnections                           |                                          |
| Changed Power BI gateway admins (Power BI-Gatewayadministratoren geändert)                   | ChangeGatewayAdministrators                 |                                          |
| Benutzer der Power BI-Gatewaydatenquelle geändert        | ChangeGatewayDatasourceUsers                |                                          |
| Power BI-Organisationsinhaltspaket erstellt      | CreateOrgApp                                |                                          |
| Created Power BI app (Power BI-App erstellt)                              | CreateApp                                   |                                          |
| Power BI-Dashboard erstellt                        | CreateDashboard                             |                                          |
| Created Power BI dataflow (Power BI-Dataflow erstellt)                         | CreateDataflow                              |                                          |
| Power BI-Dataset erstellt                          | CreateDataflow                               |                                          |
| Created Power BI email subscription (Power BI-E-Mail-Abonnement erstellt)               | CreateEmailSubscription                     |                                          |
| Created Power BI folder (Power BI-Ordner erstellt)                           | CreateFolder                                |                                          |
| Created Power BI gateway (Power BI-Gateway erstellt)                          | CreateGateway                               |                                          |
| Power BI-Gruppe erstellt                            | CreateGroup                                 |                                          |
| Power BI-Bericht erstellt                           | CreateReport                                |                                          |
| Dataflow migrated to external storage account (Dataflow in externes Speicherkonto migriert)     | DataflowMigratedToExternalStorageAccount    | Derzeit nicht verwendet                       |
| Dataflow-Berechtigungen hinzugefügt                        | DataflowPermissionsAdded                    | Derzeit nicht verwendet                       |
| Dataflow-Berechtigungen entfernt                      | DataflowPermissionsRemoved                  | Derzeit nicht verwendet                       |
| Deleted organizational Power BI content pack (Power BI-Organisationsinhaltspaket gelöscht)      | DeleteOrgApp                                |                                          |
| Deleted Power BI comment (Power BI-Kommentar gelöscht)                          | DeleteComment                               |                                          |
| Power BI-Dashboard gelöscht                        | DeleteDashboard                             | Derzeit nicht verwendet                       |
| Deleted Power BI dataflow (Power BI-Dataflow gelöscht)                         | DeleteDataflow                              | Derzeit nicht verwendet                       |
| Power BI-Dataset gelöscht                          | DeleteDataset                               |                                          |
| Deleted Power BI email subscription (Power BI-E-Mail-Abonnement gelöscht)               | DeleteEmailSubscription                     |                                          |
| Deleted Power BI folder (Power BI-Ordner gelöscht)                           | DeleteFolder                                |                                          |
| Deleted Power BI folder access (Ordnerzugriff für Power BI gelöscht)                    | DeleteFolderAccess                          | Derzeit nicht verwendet                       |
| Deleted Power BI gateway (Power BI-Gateway gelöscht)                          | DeleteGateway                               |                                          |
| Deleted Power BI group (Power BI-Gruppe gelöscht)                            | DeleteGroup                                 |                                          |
| Power BI-Bericht gelöscht                           | DeleteReport                                |                                          |
| Discovered Power BI dataset data sources (Datenquellen für Power BI-Datasets ermittelt)          | GetDatasources                              |                                          |
| Downloaded Power BI report (Power BI-Bericht herunterladen)                        | DownloadReport                              |                                          |
| Edited Power BI certification permission (Power BI-Zertifikatsberechtigung bearbeitet)          | EditCertificationPermission                 | Derzeit nicht verwendet                       |
| Power BI-Dashboard bearbeitet                         | EditDashboard                               | Derzeit nicht verwendet                       |
| Edited Power BI dataset (Power BI-Dataset bearbeitet)                           | EditDataset                                 |                                          |
| Edited Power BI dataset properties (Eigenschaften von Power BI-Datasets bearbeitet)                | EditDatasetProperties                       | Derzeit nicht verwendet                       |
| Power BI-Bericht bearbeitet                            | EditReport                                  |                                          |
| Exported Power BI dataflow (Power BI-Dataflow exportiert)                        | ExportDataflow                              |                                          |
| Visuelle Power BI-Berichtsdaten exportiert              | ExportReport                                |                                          |
| Power BI-Kacheldaten exportiert                       | ExportTile                                  |                                          |
| Failed to add dataflow permissions (Dataflow-Berechtigungen konnten nicht hinzugefügt werden)                | FailedToAddDataflowPermissions              | Derzeit nicht verwendet                       |
| Failed to remove dataflow permissions (Dataflow-Berechtigungen konnten nicht entfernt werden)             | FailedToRemoveDataflowPermissions           | Derzeit nicht verwendet                       |
| Generated Power BI dataflow SAS token (SAS-Token für Power BI-Dataflow generiert)             | GenerateDataflowSasToken                    |                                          |
| Generated Power BI Embed Token (Einbettungstoken für Power BI generiert)                    | GenerateEmbedToken                          |                                          |
| Imported file to Power BI (Datei in Power BI importiert)                         | Importieren                                      |                                          |
| Installed Power BI app (Power BI-App installiert)                            | InstallApp                                  |                                          |
| Migrated workspace to a capacity (Arbeitsbereich zu einer Kapazität migriert)                  | MigrateWorkspaceIntoCapacity                |                                          |
| Posted Power BI comment (Power BI-Kommentar veröffentlicht)                           | PostComment                                 |                                          |
| Power BI-Dashboard gedruckt                        | PrintDashboard                              |                                          |
| Power BI-Berichtseite gedruckt                      | PrintReport                                 |                                          |
| Published Power BI report to web (Power BI-Bericht im Web veröffentlicht)                  | PublishToWebReport                          |                                          |
| Received Power BI dataflow secret from Key Vault (Geheimnis für Power BI-Dataflow von Key Vault empfangen)  | ReceiveDataflowSecretFromKeyVault           | Derzeit nicht verwendet                       |
| Removed data source from Power BI gateway (Datenquelle aus Power BI-Gateway entfernt)         | RemoveDatasourceFromGateway                 |                                          |
| Removed Power BI group members (Power BI-Gruppenmitglieder entfernt)                    | DeleteGroupMembers                          |                                          |
| Removed workspace from a capacity (Arbeitsbereich aus einer Kapazität entfernt)                 | RemoveWorkspacesFromCapacity                |                                          |
| Renamed Power BI dashboard (Power BI-Dashboard umbenannt)                        | RenameDashboard                             |                                          |
| Requested Power BI dataflow refresh (Aktualisierung von Power BI-Dataflow angefordert)               | RequestDataflowRefresh                      | Derzeit nicht verwendet                       |
| Requested Power BI dataflow refresh (Aktualisierung von Power BI-Dataset angefordert)                | RefreshDataset                              |                                          |
| Retrieved Power BI workspaces (Power BI-Arbeitsbereiche abgerufen)                     | GetWorkspaces                               |                                          |
| Set scheduled refresh on Power BI dataflow (Geplante Aktualisierung des Power BI-Dataflow festgelegt)        | SetScheduledRefreshOnDataflow               |                                          |
| Set scheduled refresh on Power BI dataset (Geplante Aktualisierung des Power BI-Dataset festgelegt)         | SetScheduledRefresh                         |                                          |
| Power BI-Dashboard geteilt                         | ShareDashboard                              |                                          |
| Shared Power BI report (Power BI-Bericht geteilt)                            | ShareReport                                 |                                          |
| Started Power BI extended trial (Erweiterten Power BI-Test begonnen)                   | OptInForExtendedProTrial                    | Derzeit nicht verwendet                       |
| Power BI-Testversion gestartet                            | OptInForProTrial                            |                                          |
| Took over a Power BI datasource (Power BI-Datenquellen übernommen)                   | TakeOverDataset                          |                                          |
| Took over Power BI dataset (Power BI-Dataset übernommen)                        | TakeOverDataset                             |                                          |
| Unpublished Power BI app (Veröffentlichung der Power BI-App aufgehoben)                          | UnpublishApp                                |                                          |
| Update capacity resource governance settings (Governanceeinstellungen für Kapazitätsressourcen aktualisiert)      | UpdateCapacityResourceGovernanceSettings    | Derzeit nicht im Administratorportal für Office 365 |
| Updated capacity admin (Administrator der Kapazität aktualisiert)                            | UpdateCapacityAdmins                        |                                          |
| Updated capacity display name (Anzeigename der Kapazität aktualisiert)                     | UpdateCapacityDisplayName                   |                                          |
| Updated organization's Power BI settings (Power BI-Einstellungen der Organisation aktualisiert)          | UpdatedAdminFeatureSwitch                   |                                          |
| Updated Power BI app (Power BI-App aktualisiert)                              | UpdateApp                                   |                                          |
| Updated Power BI dataflow (Power BI-Dataflow aktualisiert)                         | UpdateDataflow                              |                                          |
| Updated Power BI dataset data sources (Datenquellen für Power BI-Datasets aktualisiert)             | UpdateDatasources                           |                                          |
| Updated Power BI dataset parameters (Parameter für Power BI-Datasets aktualisiert)               | UpdateDatasetParameters                     |                                          |
| Updated Power BI email subscription (Power BI-E-Mail-Abonnement aktualisiert)               | UpdateEmailSubscription                     |                                          |
| Updated Power BI folder (Power BI-Ordner aktualisiert)                           | UpdateFolder                                |                                          |
| Updated Power BI folder access (Ordnerzugriff für Power BI aktualisiert)                    | UpdateFolderAccess                          |                                          |
| Updated Power BI gateway data source credentials (Anmeldeinformationen der Power BI-Gatewaydatenquelle aktualisiert)  | UpdateDatasourceCredentials                 |                                          |
| Power BI-Dashboard angezeigt                         | ViewDashboard                               |                                          |
| Viewed Power BI dataflow (Power BI-Dataflow angezeigt)                          | ViewDataflow                                |                                          |
| Power BI-Bericht angezeigt                            | ViewReport                                  |                                          |
| Viewed Power BI tile (Power BI-Kachel angezeigt)                              | ViewTile                                    |                                          |
| Viewed Power BI usage metrics (Power BI-Nutzungsmetriken angezeigt)                     | ViewUsageMetrics                            |                                          |
|                                                   |                                             |                                          |

## <a name="next-steps"></a>Nächste Schritte

[Was ist die Power BI-Verwaltung?](service-admin-administering-power-bi-in-your-organization.md)  

[Power BI-Verwaltungsportal](service-admin-portal.md)  

Weitere Fragen? [Stellen Sie Ihre Frage in der Power BI-Community.](http://community.powerbi.com/)
