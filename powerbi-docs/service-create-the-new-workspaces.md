---
title: Erstellen der neuen Arbeitsbereiche (Vorschau) – Power BI
description: Erfahren Sie, wie Sie die neuen Arbeitsbereiche und Sammlungen aus Dashboards und Berichten erstellen, die zum Bereitstellen von Schlüsselmetriken für Ihre Organisation konzipiert wurden.
author: maggiesMSFT
manager: kfile
ms.reviewer: lukaszp
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 01/11/2019
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: eba4e740f6fd08ffd60b95dfc437551dfb95e7b8
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/15/2019
ms.locfileid: "54293698"
---
# <a name="create-the-new-workspaces-preview-in-power-bi"></a>Erstellen der neuen Arbeitsbereiche (Vorschau) in Power BI

In Power BI wird eine Vorschauversion für die neuen Arbeitsbereiche eingeführt. Arbeitsbereiche sind auch weiterhin ein Ort für die Zusammenarbeit mit Kollegen, um Sammlungen von Dashboards und Berichten zu erstellen, die Sie in *Apps* bündeln und an Ihre gesamte Organisation oder bestimmte Personen oder Gruppen verteilen können. 

![Vorschauversion der neuen Power BI-Arbeitsbereiche](media/service-create-the-new-workspaces/power-bi-new-workspaces-preview.png)

Mit den neuen Arbeitsbereichen (Vorschauversion) können Sie nun Folgendes durchführen:

- Arbeitsbereichsrollen Benutzergruppen zuweisen: Sicherheitsgruppen, Verteilerlisten, Office 365-Gruppen und Einzelpersonen.
- Einen Arbeitsbereich in Power BI erstellen, ohne eine Office 365-Gruppe zu erstellen.
- Genauere Arbeitsbereichsrollen für flexiblere Verwaltung von Berechtigungen in einem Arbeitsbereich verwenden.

Weitere Informationen finden Sie im Artikel [Neue Arbeitsbereiche (Vorschauversion)](service-new-workspaces.md).

## <a name="create-one-of-the-new-app-workspaces"></a>Erstellen eines neuen App-Arbeitsbereichs

1. Erstellen Sie zunächst den App-Arbeitsbereich. Wählen Sie **Arbeitsbereiche** > **App-Arbeitsbereich erstellen** aus.
   
     ![App-Arbeitsbereich erstellen](media/service-create-the-new-workspaces/power-bi-create-app-workspace.png)

2. Klicken Sie unter **Vorschau der verbesserten Arbeitsbereiche** auf **Jetzt testen**.
   
     ![Vorschau der verbesserten Arbeitsbereiche](media/service-create-the-new-workspaces/power-bi-preview-improved-workspaces.png)

2. Benennen Sie den Arbeitsbereich. Wenn der Name nicht verfügbar ist, geben Sie eine eindeutige ID ein.
   
     Die App wird den gleichen Namen wie der Arbeitsbereich haben.
   
1. Fügen Sie optional ein Bild hinzu. Die Dateigröße darf 45 KB nicht überschreiten.
 
    ![Benennen Sie den Arbeitsbereich, und fügen Sie ein Bild hinzu.](media/service-create-the-new-workspaces/power-bi-name-workspace.png)

1. Wählen Sie **Speichern**.

    Auf der **Willkommensseite** Ihres neuen Arbeitsbereichs können Sie Daten hinzufügen. 

    ![Willkommensseite des neuen Arbeitsbereichs](media/service-create-the-new-workspaces/power-bi-workspace-welcome-screen.png)

1. Klicken Sie beispielsweise auf **Beispiele** > **Customer Profitability Sample**.

    In der Inhaltsliste im Arbeitsbereich wird nun **Neue Arbeitsbereiche (Vorschau)** angezeigt. Da Sie über Administratorrechte verfügen, wird Ihnen auch die neue Aktion **Zugriff** angezeigt.

    ![Inhaltsliste der Vorschauversion für die neuen Arbeitsbereiche](media/service-create-the-new-workspaces/power-bi-workspaces-preview-content-list.png)

1. Klicken Sie auf **Zugriff**.

1. Fügen Sie diesen Arbeitsbereichen Sicherheitsgruppen, Verteilerlisten, Office 365-Gruppen oder Einzelpersonen als Mitglieder, Mitwirkende oder Administratoren hinzu. Eine Erläuterung der verschiedenen Rollen finden Sie unter [Rollen in den neuen Arbeitsbereichen](service-new-workspaces.md#roles-in-the-new-workspaces).

    ![Arbeitsbereiche: Hinzufügen von Mitgliedern, Administratoren und Mitwirkenden](media/service-create-the-new-workspaces/power-bi-access-add-members.png)

9. Klicken Sie auf **Hinzufügen** > **Schließen**.

1. Der Arbeitsbereich wird in Power BI erstellt und geöffnet. Er wird Ihnen in der Liste der Arbeitsbereiche angezeigt, deren Mitglied Sie sind. Da Sie Administrator sind, können Sie auf die Auslassungspunkte (...) klicken, um zurückzukehren, und Änderungen an Arbeitsbereichseinstellungen vornehmen, neue Mitglieder hinzufügen oder deren Berechtigungen ändern.

     ![Bearbeiten der Einstellungen und des Zugriffs für einen Arbeitsbereich](media/service-create-the-new-workspaces/power-bi-edit-workspace.png)

## <a name="add-content-to-your-app-workspace"></a>Hinzufügen von Inhalt zum App-Arbeitsbereich

Nachdem Sie einen neuen App-Arbeitsbereich erstellt haben, ist es Zeit, diesem Inhalte hinzuzufügen. Das Hinzufügen von Inhalt ist in den alten und neuen Arbeitsbereichen ähnlich, mit einer Ausnahme. Sie können in beiden Versionen von App-Arbeitsbereichen Dateien hochladen oder Verbindungen mit ihnen herstellen, wie Sie es in „Mein Arbeitsbereich“ tun würden. In den neuen Arbeitsbereichen können Sie keine Verbindung mit organisationsbezogenen Inhaltspaketen oder Inhaltspaketen von Drittanbietern herstellen, z.B. Microsoft Dynamics CRM, Salesforce oder Google Analytics. In den aktuellen Arbeitsbereichen können Sie eine Verbindung mit Inhaltspaketen herstellen.

Wenn Sie Inhalte in der Inhaltsliste eines App-Arbeitsbereichs anzeigen, wird der Name des Arbeitsbereichs als Besitzer aufgeführt.

### <a name="connecting-to-third-party-services-in-new-workspaces-preview"></a>Herstellen einer Verbindung mit Drittanbieterdiensten in neuen Arbeitsbereichen (Vorschau)

In den neuen Arbeitsbereichen rücken *Apps* in den Vordergrund. Apps für Drittanbieterdienste erleichtern es Benutzern, Daten von den Diensten abzurufen, die sie verwenden, z. B. Microsoft Dynamics CRM, Salesforce oder Google Analytics.
Organisationsbezogene Apps stellen Ihren Benutzern die internen Daten zur Verfügung, die sie benötigen. Es sind weitere Funktionen für organisationsbezogene Apps geplant, damit Benutzer den Inhalt anpassen können, den sie in den Apps finden. Mit dieser Funktion entfällt die Notwendigkeit von Inhaltspaketen. 

Mit der Vorschauversion der neuen Arbeitsbereiche können Sie keine organisationsbezogenen Inhaltspakete erstellen oder nutzen. Stattdessen können Sie die Apps verwenden, die zum Herstellen einer Verbindung mit Drittanbieterdiensten bereitgestellt werden, oder fordern Sie Ihre internen Teams dazu auf, Apps für Inhaltspakete bereitzustellen, die Sie derzeit verwenden. 

## <a name="distribute-an-app"></a>Verteilen einer App

Wenn der Inhalt bereit ist, können Sie auswählen, welche Dashboards und Berichte Sie veröffentlichen möchten. Anschließend veröffentlichen Sie diese als *App*. Sie können über jeden Arbeitsbereich eine App erstellen. Ihre Kollegen können Ihre App auf verschiedene Weise abrufen. Sie können sie automatisch in den Power BI-Konten Ihrer Kollegen installieren, wenn Ihr Power BI-Administrator Ihnen die Berechtigung dazu erteilt. Andernfalls können diese Ihre App über Microsoft AppSource finden und installieren, oder Sie können Ihren Kollegen einen direkten Link senden. Sie erhalten Updates automatisch, und Sie können steuern, wie oft die Daten aktualisiert werden. Ausführliche Informationen finden Sie unter [Veröffentlichen von Apps mit Dashboards und Berichten in Power BI](service-create-distribute-apps.md).

## <a name="convert-old-app-workspaces-to-new-app-workspaces"></a>Konvertieren alter App-Arbeitsbereiche in neue App-Arbeitsbereiche

Während der Vorschauphase können Sie ihre alten App-Arbeitsbereiche nicht automatisch in neue konvertieren. Sie können jedoch einen neuen App-Arbeitsbereich erstellen und Ihren Inhalt dort veröffentlichen. 

Wenn die neuen Arbeitsbereiche in die allgemeine Verfügbarkeit übergehen, können Sie die alten Arbeitsbereiche automatisch migrieren. Nach Eintritt der allgemeinen Verfügbarkeit müssen Sie sie migrieren.

## <a name="next-steps"></a>Nächste Schritte
* Weitere Informationen zum [Organisieren von Arbeit in den neuen Arbeitsbereichen (Vorschauversion) in Power BI](service-new-workspaces.md)
* [Create the current workspaces (Erstellen der aktuellen Arbeitsbereiche)](service-create-workspaces.md)
* [Installieren und Verwenden von Apps in Power BI](service-create-distribute-apps.md)
* Haben Sie Fragen? [Stellen Sie Ihre Frage in der Power BI-Community.](http://community.powerbi.com/)
