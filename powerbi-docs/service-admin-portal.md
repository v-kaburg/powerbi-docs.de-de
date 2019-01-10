---
title: Power BI-Verwaltungsportal
description: Das Verwaltungsportal ermöglicht die Mandantenverwaltung von Power BI in Ihrer Organisation. Es enthält Elemente wie z. B. Nutzungsmetriken und Zugriff auf das Office 365 Admin Center und die Einstellungen.
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-admin
ms.topic: conceptual
ms.date: 10/30/2018
ms.custom: seodec18
LocalizationGroup: Administration
ms.openlocfilehash: e83c853ac1c3fc7c7d4d5e79c9f6be965d880361
ms.sourcegitcommit: c09241803664643e1b2ba0c150e525e1262ca466
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2019
ms.locfileid: "54072288"
---
# <a name="administering-power-bi-in-the-admin-portal"></a>Verwalten von Power BI im Verwaltungsportal

Mit dem Verwaltungsportal können Sie einen Power BI-*Mandanten* für Ihre Organisation verwalten. Das Portal stellt Elemente wie z.B. Nutzungsmetriken, Zugriff auf das Office 365 Admin Center und Einstellungen bereit.

Auf das vollständige Verwaltungsportal können alle Benutzer zugreifen, die globale Administratoren in Office 365 sind oder der Power BI-Dienstadministratorrolle zugewiesen wurden. Wenn Sie keiner dieser Rollen angehören, können Sie im Portal nur die **Kapazitätseinstellungen** anzeigen. Weitere Informationen zur Power BI-Dienstadministratorrolle finden Sie unter [Grundlegendes zur Power BI-Administratorrolle](service-admin-role.md).

## <a name="how-to-get-to-the-admin-portal"></a>Gewusst wie: Anzeigen des Verwaltungsportals

Ihr Konto muss in Office 365 oder Azure Active Directory als **Globaler Administrator** markiert oder der Power BI-Dienstadministratorrolle zugewiesen sein, damit Sie Zugriff auf das Power BI-Verwaltungsportal erhalten. Weitere Informationen zur Power BI-Dienstadministratorrolle finden Sie unter [Grundlegendes zur Power BI-Administratorrolle](service-admin-role.md). Führen Sie zum Zugreifen auf das Power BI-Verwaltungsportal die folgenden Schritte aus.

1. Wählen Sie das Zahnradsymbol für die Einstellungen oben rechts im Power BI-Dienst aus.

1. Wählen Sie **Verwaltungsportal** aus.

    ![Einstellungen im Verwaltungsportal](media/service-admin-portal/powerbi-admin-settings.png)

Das Portal umfasst sieben Registerkarten. In den verbleibenden Abschnitten dieses Artikels erhalten Sie Informationen zu jeder dieser Registerkarten.

![Navigation im Verwaltungsportal](media/service-admin-portal/powerbi-admin-landing-page.png)

* [Nutzungsmetriken](#usage-metrics)
* [Benutzer](#users)
* [Überwachungsprotokolle](#audit-logs)
* [Mandanteneinstellungen](#tenant-settings)
* [Premium-Einstellungen](#premium-settings)
* [Einbindungscodes](#embed-codes)
* [Visuals für Organisationen](#organization-visuals)

## <a name="usage-metrics"></a>Nutzungsmetriken

Mithilfe der **Nutzungsmetriken** können Sie die Power BI-Nutzung für Ihre Organisation überwachen. Außerdem können Sie darüber feststellen, welche Benutzer und Gruppen in Power BI für Ihre Organisation am aktivsten sind.

> [!NOTE]
> Beim ersten Zugriff auf das Dashboard oder beim Anzeigen des Dashboards nach einem längeren Zeitraum wird zunächst wahrscheinlich ein Ladebildschirm angezeigt, während das Dashboard geladen wird.

Nachdem das Dashboard geladen wurde, werden zwei Abschnitte mit Kacheln angezeigt. Der erste Abschnitt umfasst Nutzungsdaten für einzelne Benutzer, der zweite Abschnitt enthält ähnliche Informationen für die Gruppen in Ihrer Organisation.

Im Folgenden sehen Sie, was in den einzelnen Kacheln angezeigt wird:

* Anzahl der verschiedenen Dashboards, Berichte und Datasets im Arbeitsbereich eines Benutzers
  
    ![Anzahl der verschiedenen Dashboards, Berichte, Datasets](media/service-admin-portal/powerbi-admin-usage-metrics-number-tiles.png)

* Das am häufigsten verwendete Dashboard nach Anzahl von Benutzern, die darauf zugreifen können. Wenn Sie z.B. ein Dashboard für drei Benutzer freigegeben und dieses auch einem Inhaltspaket hinzugefügt haben, mit dem zwei weitere Benutzer verbunden sind, beträgt die Anzahl 6 (1 + 3 + 2).
  
    ![Am häufigsten verwendete Dashboards](media/service-admin-portal/powerbi-admin-usage-metrics-top-dashboards.png)

* Der beliebteste Inhalt, mit dem Benutzer Verbindungen herstellen. Dies kann alles sein, worauf Benutzer durch den Vorgang zum Abrufen von Daten zugreifen können, z. B. SaaS-Pakete, organisationsbezogene Inhaltspakete, Dateien oder Datenbanken.
  
    ![Am häufigsten verwendete Pakete](media/service-admin-portal/powerbi-admin-usage-metrics-top-connections.png)

* Eine Ansicht der aktivsten Benutzer basierend auf der Anzahl von Dashboards. Dies können von den Benutzern selbst erstellte Dashboards sein, aber auch Dashboards, die für sie freigegeben wurden.
  
    ![Aktivste Benutzer – Dashboards](media/service-admin-portal/powerbi-admin-usage-metrics-top-users-dashboards.png)

* Eine Ansicht der aktivsten Benutzer basierend auf der Anzahl von Berichten
  
    ![Aktivste Benutzer – Berichte](media/service-admin-portal/powerbi-admin-usage-metrics-top-users-reports.png)

Der zweite Abschnitt zeigt dieselben Informationen basierend auf Gruppen an. So können Sie sehen, welche Gruppen in Ihrer Organisation besonders aktiv sind und welche Art von Inhalten sie verwenden.

Anhand dieser Informationen gewinnen Sie wichtige Erkenntnisse zur Verwendung von Power BI in Ihrer Organisation. Außerdem können Sie ermitteln, welche Benutzer und Gruppen in Ihrer Organisation besonders aktiv sind.

## <a name="users"></a>Benutzer

Sie verwalten Power BI-Benutzer, -Gruppen und -Administratoren im Office 365 Admin Center. Die Registerkarte **Benutzer** umfasst einen Link zum Admin Center für Ihren Mandanten.

![O365 Admin Center aufrufen](media/service-admin-portal/powerbi-admin-manage-users.png)

## <a name="audit-logs"></a>Überwachungsprotokolle

Sie verwalten Power BI-Überwachungsprotokolle im Office 365 Security & Compliance Center. Die Registerkarte **Überwachungsprotokolle** umfasst einen Link zum Security & Compliance Center für Ihren Mandanten. [Weitere Informationen](service-admin-auditing.md)

Um Überwachungsprotokolle zu verwenden, stellen Sie sicher, dass die Einstellung [**Überwachungsprotokolle für interne Aktivitätsüberwachung und Compliance erstellen**](#create-audit-logs-for-internal-activity-auditing-and-compliance) aktiviert ist.

## <a name="tenant-settings"></a>Mandanteneinstellungen

Die Registerkarte **Mandanteneinstellungen** ermöglicht eine fein abgestufte Steuerung der Features, die für Ihre Organisation zur Verfügung stehen. Wenn Sie über vertrauliche Daten verfügen, die besonders geschützt werden müssen, sind einige der Features möglicherweise nicht für Ihre Organisation geeignet bzw. bestimmte Funktionen sollten nur für eine bestimme Gruppe bereitgestellt werden.

Die folgende Abbildung zeigt die ersten beiden Abschnitte der Registerkarte **Mandanteneinstellungen**.

![Mandanteneinstellungen](media/service-admin-portal/powerbi-admin-tenant-settings.png)

> [!NOTE]
> Es kann bis zu zehn Minuten dauern, bis eine Einstellungsänderung für alle Benutzer in Ihrem Mandanten wirksam wird.

Einstellungen können drei Zustände aufweisen:

* **Für die gesamte Organisation deaktiviert:** Keine Person in Ihrer Organisation kann dieses Feature verwenden.

    ![Einstellung für alle deaktiviert](media/service-admin-portal/powerbi-admin-tenant-settings-disabled.png)

* **Für die gesamte Organisation aktiviert:** Jede Person in Ihrer Organisation kann dieses Feature verwenden.

    ![Einstellung für alle aktiviert](media/service-admin-portal/powerbi-admin-tenant-settings-enabled.png)

* **Für eine Teilmenge der Organisation aktiviert:** Eine bestimmte Teilmenge der Benutzer oder Gruppen in Ihrer Organisation kann dieses Feature verwenden.

    Sie können das Feature für die gesamte Organisation mit Ausnahme einer bestimmten Gruppe von Benutzern aktivieren.

    ![Einstellung für eine Teilmenge aktiviert](media/service-admin-portal/powerbi-admin-tenant-settings-enabled-except.png)

    Sie können das Feature auch für eine bestimmte Gruppe von Benutzern aktivieren und gleichzeitig für eine Gruppe von Benutzern deaktivieren. So stellen Sie sicher, dass bestimmte Benutzer auch dann keinen Zugriff auf das Feature erhalten, wenn sie Mitglied der Gruppe sind, für die der Zugriff aktiviert ist.

    ![Einstellung mit Ausnahme aktivieren](media/service-admin-portal/powerbi-admin-tenant-settings-enabled-except2.png)

Die nächsten Abschnitte bieten einen Überblick über die verschiedenen Arten von Mandanteneinstellungen.

## <a name="workspace-settings"></a>Arbeitsbereichseinstellungen

### <a name="create-workspaces-preview"></a>Erstellen von Arbeitsbereichen (Vorschau)

Benutzer in der Organisation können App-Arbeitsbereiche erstellen, um gemeinsam an Dashboards, Berichten und anderen Inhalten zu arbeiten. [Weitere Informationen](service-create-the-new-workspaces.md)

## <a name="export-and-sharing-settings"></a>Einstellungen für Export und Freigabe

### <a name="share-content-to-external-users"></a>Freigeben von Inhalten für externe Benutzer

Benutzer in der Organisation können Dashboards für Benutzer außerhalb der Organisation freigeben. [Weitere Informationen](service-share-dashboards.md#share-a-dashboard-or-report-with-people-outside-your-organization)

![Einstellung für externe Benutzer](media/service-admin-portal/powerbi-admin-sharing-external-02.png)

Die folgende Abbildung zeigt die Meldung, die bei der Freigabe für einen externen Benutzer angezeigt wird.

![Freigabe für externen Benutzer](media/service-admin-portal/powerbi-admin-sharing-external.png)

### <a name="publish-to-web"></a>Im Web veröffentlichen

Benutzer in der Organisation können Berichte im Web veröffentlichen. [Weitere Informationen](service-publish-to-web.md)

Die folgende Abbildung zeigt das Menü **Datei** für einen Bericht an, wenn die Einstellung **Im Web veröffentlichen** aktiviert ist.

![Einstellung „Im Web veröffentlichen“](media/service-admin-portal/powerbi-admin-publish-to-web.png)

Den Benutzer werden basierend auf der Einstellung **Im Web veröffentlichen** unterschiedliche Optionen in der Benutzeroberfläche angezeigt.

|Ausgewählt |Für die gesamte Organisation aktiviert |Für die gesamte Organisation deaktiviert |Bestimmte Sicherheitsgruppen   |
|---------|---------|---------|---------|
|**Im Web veröffentlichen** im Menü **Datei** des Berichts.|Für alle aktiviert|Nicht für alle sichtbar|Nur für autorisierte Benutzer oder Gruppen sichtbar|
|**Einbindungscodes verwalten** unter **Einstellungen**|Für alle aktiviert|Für alle aktiviert|Für alle aktiviert<br><br>Option * **Löschen** nur für autorisierte Benutzer oder Gruppen<br>* **Codes abrufen** für alle aktiviert|
|**Einbindungscodes** im Verwaltungsportal|Es wird einer der folgenden Statuswerte angezeigt:<br>* Aktiv<br>* Nicht unterstützt<br>* Blockiert|Angezeigter Status **Deaktiviert**|Es wird einer der folgenden Statuswerte angezeigt:<br>* Aktiv<br>* Nicht unterstützt<br>* Blockiert<br><br>Wenn ein Benutzer gemäß den Mandanteneinstellungen nicht autorisiert ist, wird als Status **Verletzt** angezeigt.|
|Vorhandene veröffentlichte Berichte|Alle aktiviert|Alle deaktiviert|Berichte werden weiterhin für alle gerendert.|

### <a name="export-data"></a>Daten exportieren

Benutzer in der Organisation können Daten aus einer Kachel oder Visualisierung exportieren. [Weitere Informationen](visuals/power-bi-visualization-export-data.md)

Die folgende Abbildung zeigt die Option zum Exportieren von Daten aus einer Kachel.

![Exportieren von Daten aus einer Kachel](media/service-admin-portal/powerbi-admin-export-data.png)

> [!NOTE]
> Durch das Deaktivieren von **Daten exportieren** wird zudem verhindert, dass Benutzer das Feature **In Excel analysieren** sowie die Liveverbindung des Power BI-Diensts verwenden können.

### <a name="export-reports-as-powerpoint-presentations"></a>Berichte als PowerPoint-Präsentationen exportieren

Benutzer in der Organisation können Power BI-Berichte als PowerPoint-Dateien exportieren. [Weitere Informationen](consumer/end-user-powerpoint.md)

Die folgenden Abbildung zeigen das Menü **Datei** für einen Bericht, wenn die Einstellung **Berichte aus PowerPoint-Präsentationen exportieren** aktiviert ist.

![Berichte als PowerPoint-Präsentationen exportieren](media/service-admin-portal/powerbi-admin-powerpoint.png)

### <a name="print-dashboards-and-reports"></a>Dashboards und Berichte drucken

Benutzer in der Organisation können Dashboards und Berichte drucken. [Weitere Informationen](consumer/end-user-print.md)

Die folgende Abbildung zeigt die Option zum Drucken eines Dashboards.

![Dashboard drucken](media/service-admin-portal/powerbi-admin-print-dashboard.png)

Die folgende Abbildung zeigt das Menü **Datei** für einen Bericht, wenn die Einstellung **Dashboards und Berichte drucken** aktiviert ist.

![Bericht drucken](media/service-admin-portal/powerbi-admin-print-report.png)

## <a name="content-pack-and-app-settings"></a>Einstellungen für das Inhaltspaket und die App

### <a name="publish-content-packs-and-apps-to-the-entire-organization"></a>Inhaltspakete und Apps für die gesamte Organisation veröffentlichen

Benutzer in der Organisation können Inhaltspakete und Apps für die gesamte Organisation veröffentlichen, nicht nur für bestimmte Gruppen. [Weitere Informationen](service-organizational-content-pack-manage-update-delete.md)

Die folgende Abbildung zeigt die Option **Meine gesamte Organisation** beim Erstellen eines Inhaltspakets.

![Veröffentlichen von Inhaltspaketen für die Organisation](media/service-admin-portal/powerbi-admin-publish-entire-org.png)

### <a name="create-template-organizational-content-packs-and-apps"></a>Vorlagenpakete mit Organisationsinhalten und Apps erstellen

Benutzer in der Organisation können Vorlageninhaltspakete erstellen, die in Power BI Desktop erstellte Datasets verwenden. [Weitere Informationen](template-content-pack-authoring.md)

### <a name="push-apps-to-end-users"></a>Apps mithilfe von Push an Endbenutzer übertragen

Benutzer können Apps direkt und ohne Installation aus AppSource für Endbenutzer freigeben. [Weitere Informationen](service-create-distribute-apps.md)

## <a name="integration-settings"></a>Integrationseinstellungen

### <a name="ask-questions-about-data-using-cortana"></a>Stellen von Fragen zu Daten mithilfe von Cortana

Benutzer in der Organisation können mithilfe von Cortana Fragen zu ihren Daten stellen. [Weitere Informationen](service-cortana-enable.md)

> [!NOTE]
> Diese Einstellung gilt für die gesamte Organisation und kann nicht auf bestimmte Gruppen beschränkt werden.

### <a name="use-analyze-in-excel-with-on-premises-datasets"></a>Verwenden von In Excel analysieren mit lokalen Datasets

Benutzer in der Organisation können Excel verwenden, um lokale Power BI-Datasets anzuzeigen und mit ihnen zu interagieren. [Weitere Informationen](service-analyze-in-excel.md)

> [!NOTE]
> Durch das Deaktivieren von **Daten exportieren** wird außerdem verhindert, dass Benutzer das Feature **In Excel analysieren** verwenden.

### <a name="use-arcgis-maps-for-power-bi"></a>ArcGIS Maps for Power BI verwenden

Benutzer in der Organisation können die Visualisierung ArcGIS Maps for Power BI von Esri verwenden. [Weitere Informationen](power-bi-visualization-arcgis.md)

### <a name="use-global-search-for-power-bi-preview"></a>Verwenden der globalen Suche für Power BI (Vorschau)

Benutzer in der Organisation können externe Suchfeatures verwenden, die auf Azure Search basieren. Benutzer können beispielsweise Cortana zum Abrufen wichtiger Informationen direkt aus Power BI-Dashboards und -Berichten verwenden. [Weitere Informationen](service-cortana-intro.md)

## <a name="custom-visuals-settings"></a>Einstellungen für benutzerdefinierte Visuals

### <a name="enable-custom-visuals-for-the-entire-organization"></a>Aktivieren benutzerdefinierter Visuals für die gesamte Organisation

Benutzer in der Organisation können mit benutzerdefinierten Visuals interagieren und diese freigeben. [Weitere Informationen](power-bi-custom-visuals.md)

> [!NOTE]
> Diese Einstellung gilt für die gesamte Organisation und kann nicht auf bestimmte Gruppen beschränkt werden.

## <a name="r-visuals-settings"></a>Einstellungen für R-Visualisierungen

### <a name="interact-with-and-share-r-visuals"></a>Mit visuellen R-Elementen interagieren und diese freigeben

Benutzer in der Organisation können mit visuellen Elementen, die mit R-Skripts erstellt wurden, interagieren und diese freigeben. [Weitere Informationen](visuals/service-r-visuals.md)

> [!NOTE]
> Diese Einstellung gilt für die gesamte Organisation und kann nicht auf bestimmte Gruppen beschränkt werden.

## <a name="audit-and-usage-settings"></a>Überwachungs- und Nutzungseinstellungen

### <a name="create-audit-logs-for-internal-activity-auditing-and-compliance"></a>Überwachungsprotokolle für interne Aktivitätsüberwachung und Compliance erstellen

Benutzer in der Organisation können Aktionen überwachen, die in Power BI von anderen Benutzern in der Organisation ausgeführt werden. [Weitere Informationen](service-admin-auditing.md)

Diese Einstellung muss aktiviert sein, damit Überwachungsprotokolleinträge aufgezeichnet werden. Es kann bis zu 48 Stunden nach der Aktivierung der Überwachung dauern, bis Sie Überwachungsdaten einsehen können. Wenn Sie nicht umgehend Daten sehen, überprüfen Sie die Überwachungsprotokolle später noch einmal. Es kann zu einer ähnlichen Verzögerung kommen, nachdem Ihnen die Leseberechtigung für Überwachungsprotokolle erteilt wurde und bis Sie die Protokolle ansehen können.

> [!NOTE]
> Diese Einstellung gilt für die gesamte Organisation und kann nicht auf bestimmte Gruppen beschränkt werden.

### <a name="usage-metrics-for-content-creators"></a>Nutzungsmetriken für Inhaltsersteller

Benutzer in der Organisation können Nutzungsmetriken für von ihnen erstellte Dashboards und Berichte anzeigen. [Weitere Informationen](service-usage-metrics.md)

### <a name="per-user-data-in-usage-metrics-for-content-creators"></a>Benutzerspezifische Daten in Nutzungsmetriken für Inhaltsersteller

Nutzungsmetriken für Inhaltsersteller machen Anzeigenamen und E-Mail-Adressen von Benutzern verfügbar, die auf Inhalte zugreifen. [Weitere Informationen](service-usage-metrics.md)

Die benutzerspezifischen Daten sind standardmäßig für die Nutzungsmetriken aktiviert, und die Kontoinformationen vom Ersteller des Inhalts sind im Bericht zu den Nutzungsmetriken enthalten. Wenn Sie diese Informationen für einige oder alle Benutzer nicht miteinbeziehen möchten, deaktivieren Sie das Feature für angegebene Sicherheitsgruppen oder eine gesamte Organisation. Die Kontoinformationen werden im Bericht dann als *Unnamed* (Unbenannt) angezeigt.

## <a name="dashboard-settings"></a>Dashboardeinstellungen

### <a name="data-classification-for-dashboards"></a>Datenklassifizierung für Dashboards

Benutzer in der Organisation können Dashboards mit Klassifizierungen markieren, die Dashboardsicherheitsstufen angeben. [Weitere Informationen](service-data-classification.md)

> [!NOTE]
> Diese Einstellung gilt für die gesamte Organisation und kann nicht auf bestimmte Gruppen beschränkt werden.

## <a name="developer-settings"></a>Entwicklereinstellungen

### <a name="embed-content-in-apps"></a>Inhalt in Apps einbetten

Benutzer in der Organisation können Power BI-Dashboards und -Berichte in SaaS-Anwendungen (Software as a Service) einbetten. Ist diese Einstellung deaktiviert, können Benutzer die REST-APIs nicht dazu verwenden, um Power BI-Inhalt in ihre Anwendungen einzubetten. [Weitere Informationen](developer/embedding.md)

## <a name="workspaces-and-import-settings"></a>Arbeitsbereiche und Importeinstellungen

### <a name="author-content-in-workspaces"></a>Erstellen von Inhalten in Arbeitsbereichen

Benutzer in der Organisation können auf Arbeitsbereiche zugreifen, um Daten zu verknüpfen und Inhalte zu erstellen. [Weitere Informationen](service-create-the-new-workspaces.md)

### <a name="import-data-into-power-bi"></a>Importieren von Daten in Power BI

Benutzer in der Organisation können Daten in den Dienst importieren, z.B. durch Veröffentlichen von Berichten aus Power BI Desktop, durch Hochladen von Power BI-Berichtdateien und durch Verknüpfen von Daten direkt aus dem Dienst. [Weitere Informationen](desktop-upload-desktop-files.md)

## <a name="dataflow-settings-preview"></a>Datafloweinstellungen (Vorschau)

### <a name="create-and-use-dataflows-preview"></a>Erstellen und Verwenden von Dataflows (Vorschau)

Benutzer in der Organisation können Dataflows erstellen und verwenden. Weitere Informationen zu Dataflows finden Sie unter [Self-Service-Datenaufbereitung in Power BI (Vorschau)](service-dataflows-overview.md). Informationen zum Aktivieren von Dataflows in einer Premium-Kapazität finden Sie im Abschnitt „Konfigurieren von Workloads“ unter [Verwalten von Kapazitäten in Power BI Premium und Power BI Embedded](service-admin-premium-manage.md#configure-workloads).

> [!NOTE]
> Diese Einstellung gilt für die gesamte Organisation und kann nicht auf bestimmte Gruppen beschränkt werden.

## <a name="capacity-settings"></a>Kapazitätseinstellungen

### <a name="power-bi-premium"></a>Power BI Premium

Über die Registerkarte **Power BI Premium** können Sie jede Power BI Premium-Kapazität (EM- oder P-SKU) verwalten, die für Ihre Organisation erworben wurde. Alle Benutzer in Ihrer Organisation sehen die Registerkarte **Power BI Premium**, können deren Inhalt aber nur anzeigen, wenn sie entweder als *Kapazitätsadministrator* oder als Benutzer mit Zuweisungsberechtigungen konfiguriert sind. Hat ein Benutzer keine Berechtigungen, wird die folgende Meldung angezeigt.

![Kein Zugriff auf Premium-Einstellungen](media/service-admin-portal/premium-settings-no-access.png)

Weitere Informationen zum Verwalten von Premium-Einstellungen finden Sie unter [Verwalten von Power BI Premium](service-admin-premium-manage.md).

### <a name="power-bi-embedded"></a>Power BI Embedded

Auf der Registerkarte **Power BI Embedded** können Sie die Power BI Embedded-Kapazitäten (A-SKU) anzeigen, die Sie für Ihren Kunden erworben haben. Da es nur möglich ist, A-SKUs von Azure zu erwerben, können Sie [verwaltete Embedded-Kapazitäten in Azure](developer/azure-pbie-create-capacity.md) über das **Azure-Portal** verwalten.

Weitere Informationen zum Verwalten von Power BI Embedded-Einstellungen (A-SKU) finden Sie unter [Was ist Power BI Embedded?](developer/azure-pbie-what-is-power-bi-embedded.md).

## <a name="embed-codes"></a>Einbindungscodes

Als Administrator können Sie die Einbindungscodes anzeigen, die für Ihren Mandanten generiert werden. Sie können Codes auch widerrufen oder löschen. [Weitere Informationen](service-publish-to-web.md)

![Einbindungscodes innerhalb des Power BI-Verwaltungsportals](media/service-admin-portal/embed-codes.png)

## <a name="organizational-visuals"></a>Visuals für Organisationen

Auf der Registerkarte **Visuals für Organisationen** können Sie benutzerdefinierte Visuals in Ihrer Organisation bereitstellen und verwalten. Mit Organisationsvisuals können Sie ganz einfach proprietäre Visuals in Ihrer Organisation bereitstellen. Berichtsautoren können diese Visuals dann erkunden und in ihre Berichte in Power BI Desktop importieren. [Weitere Informationen](power-bi-custom-visuals-organization.md)

> [!WARNING]
> Ein benutzerdefiniertes Visual kann Code mit Sicherheits- oder Datenschutzrisiken enthalten. Stellen Sie sicher, dass Sie dem Autor und der Quelle des benutzerdefinierten Visuals vertrauen können, bevor Sie dieses im Repository der Organisation bereitstellen.

Die folgende Seite zeigt alle benutzerdefinierten Visuals an, die derzeit im Repository der Organisation bereitgestellt sind.

![Verwalten von Organisationsvisuals](media/service-admin-portal/power-bi-custom-visuals-organizational-admin-01.png)

### <a name="add-a-new-custom-visual"></a>Hinzufügen eines neuen benutzerdefinierten Visuals

Um der Liste ein neues benutzerdefiniertes Visual hinzufügen, führen Sie die folgenden Schritte aus. 

1. Wählen Sie auf der rechten Seite den Eintrag **Benutzerdefiniertes Visual hinzufügen**.

    ![Formular für benutzerdefiniertes Visual](media/service-admin-portal/power-bi-custom-visuals-organizational-admin-02.png)

1. Füllen Sie das Formular **Benutzerdefiniertes Visual hinzufügen** aus:

    * **PBIVIZ-Datei auswählen** (erforderlich): Wählen Sie eine benutzerdefinierte Visualdatei zum Hochladen aus. Nur benutzerdefinierte Visuals mit API-Versionsangabe werden unterstützt (lesen Sie hier nach, was dies bedeutet).

    Bevor Sie ein benutzerdefiniertes Visual hochladen, sollten Sie dieses auf Sicherheit und Datenschutz überprüfen, um sicherzustellen, dass das Visual die Standards Ihrer Organisation erfüllt.

    * **Benutzerdefiniertes Visual benennen** (erforderlich): Geben Sie dem Visual einen kurzen Titel, damit die Benutzer von Power BI Desktop den Zweck leichter nachvollziehen können.

    * **Symbol:** Die Symboldatei, die auf der Benutzeroberfläche von Power BI Desktop angezeigt wird.

    * **Beschreibung**: Eine kurze Beschreibung des Visuals, um den Benutzern zusätzlichen Kontext bereitzustellen

1. Klicken Sie auf **Hinzufügen**, um die Uploadanforderung zu initiieren. Wenn der Upload erfolgreich ist, wird das neue Element in der Liste angezeigt. Ist der Vorgang nicht erfolgreich, erhalten Sie eine entsprechende Fehlermeldung.

### <a name="delete-a-custom-visual-from-the-list"></a>Löschen eines benutzerdefinierten Visuals aus der Liste

Klicken Sie im Repository beim Visual auf das Papierkorbsymbol, um das Visual dauerhaft zu löschen.

> [!IMPORTANT]
> Der Löschvorgang ist nicht umkehrbar. Sobald das Visual gelöscht wurde, wird es in vorhandenen Berichten nicht mehr gerendert. Selbst wenn Sie das gleiche Visual erneut hochladen, ersetzt es nicht das vorherige Visual, das gelöscht wurde. Benutzer können jedoch das neue Visual erneut importieren und die Instanz in ihren Berichten ersetzen.

### <a name="disable-a-custom-visual-in-the-list"></a>Deaktivieren eines benutzerdefinierten Visuals in der Liste

Um das Visual im Organisationsspeicher zu deaktivieren, wählen Sie das Zahnradsymbol aus. Deaktivieren Sie das benutzerdefinierte Visual im Abschnitt **Zugriff**.

Nachdem Sie das Visual deaktiviert haben, wird es in vorhandenen Berichten nicht mehr gerendert, und es wird die nachstehende Fehlermeldung angezeigt.

*Dieses benutzerdefinierte Visual ist nicht mehr verfügbar. Wenden Sie sich an Ihren Administrator, um Einzelheiten zu erfahren.*

Visuals, für die ein Lesezeichen festgelegt wurde, funktionieren jedoch weiterhin.

Power BI Desktop-Benutzer müssen die Anwendung nach einem Update oder einer Administratoränderung neu starten oder den Browser im Power BI-Dienst aktualisieren, um die Aktualisierungen anzuzeigen.

### <a name="update-a-visual"></a>Aktualisieren eines Visuals

Um das Visual im Store der Organisation zu aktualisieren, wählen Sie das Zahnradsymbol aus. Suchen Sie nach einer neuen Version des Visuals, und laden Sie diese hoch.

Stellen Sie sicher, dass die Visual-ID unverändert bleibt. Die neue Datei ersetzt die vorherige Datei für alle Berichte in der gesamten Organisation. Wenn jedoch die neue Version des Visuals irgendeine Verwendung oder Datenstruktur der vorherigen Version des Visuals beeinträchtigen könnte, ersetzen Sie die vorherige Version nicht. Stattdessen sollten Sie einen neuen Eintrag für die neue Version des Visuals erstellen. Fügen Sie beispielsweise eine neue Versionsnummer (Version X.X) zum Titel des neuen gelisteten Visuals hinzu. Auf diese Weise wird deutlich, dass es sich nur um das gleiche Visual mit einer aktualisierten Versionsnummer handelt, sodass die Funktionalität bestehender Berichte nicht beeinträchtigt wird. Stellen Sie erneut sicher, dass die Visual-ID unverändert bleibt. Wenn die Benutzer das Repository der Organisation das nächste Mal über Power BI Desktop verwenden, können sie die neue Version importieren. Sie werden in diesem Fall aufgefordert, die aktuelle Version zu ersetzen, die sich im Bericht befindet.

Weitere Informationen finden Sie in den [häufig gestellten Fragen zu benutzerdefinierten Visuals in Organisationen](https://docs.microsoft.com/en-us/power-bi/power-bi-custom-visuals-faq#organizational-custom-visuals).

## <a name="dataflow-storage-preview"></a>Dataflowspeicher (Vorschau)

Mit Power BI verwendete Daten werden standardmäßig im internen Speicher von Power BI gespeichert. Mit der Integration von Dataflows und Azure Data Lake Storage Gen2 (ADLS Gen2) können Sie Ihre Dataflows im Azure Data Lake Storage Gen2-Konto Ihrer Organisation speichern. Weitere Informationen finden Sie unter [Dataflows und Azure Data Lake-Integration (Vorschauversion)](service-dataflows-azure-data-lake-integration.md).

## <a name="workspaces-preview"></a>Arbeitsbereiche (Vorschau)

Als Administrator können Sie die Arbeitsbereiche anzeigen, die in Ihrem Mandanten vorhanden sind. Sie können die Liste der Arbeitsbereiche sortieren und filtern und die Details zu jedem Arbeitsbereich anzeigen. Beachten Sie, dass die Tabellenspalten den von der [Power BI Admin-Rest-API](/rest/api/power-bi/admin) für Arbeitsbereiche zurückgegebenen Eigenschaften entsprechen. Persönliche Arbeitsbereiche weisen den Typ **PersonalGroup**, Legacy-Arbeitsbereiche den Typ **Group** und moderne Arbeitsbereiche den Typ **Workspace** auf. Weitere Informationen finden Sie unter [Erstellen der neuen Arbeitsbereiche (Vorschau) in Power BI](service-create-the-new-workspaces.md).

![Liste der Arbeitsbereiche](media/service-admin-portal/workspaces-list.png)

## <a name="next-steps"></a>Nächste Schritte

[Verwalten von Power BI in Ihrer Organisation](service-admin-administering-power-bi-in-your-organization.md) [Grundlegendes zur Power BI-Administratorrolle](service-admin-role.md)  
[Überwachen von Power BI in Ihrer Organisation](service-admin-auditing.md)  
[Verwalten von Power BI Premium](service-admin-premium-manage.md)  

Weitere Fragen? [Stellen Sie Ihre Frage in der Power BI-Community.](http://community.powerbi.com/)
