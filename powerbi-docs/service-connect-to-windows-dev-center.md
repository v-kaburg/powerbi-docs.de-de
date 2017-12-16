---
title: Herstellen einer Verbindung mit Windows Dev Center mithilfe von Power BI
description: "Windows Dev Center für Power BI"
services: powerbi
documentationcenter: 
author: joeshoukry
manager: kfile
backup: maggiesMSFT
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/16/2017
ms.author: yshoukry
ms.openlocfilehash: d88e10b4ee2e76444fccec0edabddd2a123d6b62
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2017
---
# <a name="connect-to-windows-dev-center-with-power-bi"></a>Herstellen einer Verbindung mit Windows Dev Center mithilfe von Power BI
Mit diesem Power BI-Inhaltspaket können Sie die Analysedaten von Windows Dev Center-Apps in Power BI untersuchen und überwachen. Die Daten werden automatisch einmal täglich aktualisiert.

Stellen Sie eine Verbindung mit dem [Windows Dev Center-Inhaltspaket](https://app.powerbi.com/getdata/services/devcenter) für Power BI her.

## <a name="how-to-connect"></a>Herstellen der Verbindung
1. Wählen Sie unten im linken Navigationsbereich **Daten abrufen** aus.
   
   ![](media/service-connect-to-windows-dev-center/getdata.png)
2. Wählen Sie im Feld **Dienste** die Option **Abrufen**aus.
   
   ![](media/service-connect-to-windows-dev-center/services.png)
3. Wählen Sie **Windows Dev Center** \> **Abrufen**.
   
   ![](media/service-connect-to-windows-dev-center/windowsdev.png)
4. Geben Sie die Anwendungs-ID einer in Ihrem Besitz befindlichen App ein, und klicken Sie auf „Weiter“. Unten finden Sie Einzelheiten zum [Suchen dieser Parameter](#FindingParams).
   
   ![](media/service-connect-to-windows-dev-center/params.png)
5. Wählen Sie als **Authentifizierungsmethode** die Option **oAuth2** \> **Anmelden** aus. Wenn Sie dazu aufgefordert werden, geben Sie die Azure Active Directory-Anmeldeinformationen ein, die Ihrem Windows Dev Center-Konto zugeordnet sind (weitere Informationen finden Sie unter [Systemanforderungen](#Requirements)).
   
    ![](media/service-connect-to-windows-dev-center/creds.png)
   
    ![](media/service-connect-to-windows-dev-center/creds2.png)
6. Nach der Genehmigung wird der Importvorgang automatisch gestartet. Nach Abschluss des Vorgangs werden im Navigationsbereich ein neues Dashboard, ein Bericht und ein Modell angezeigt. Wählen Sie das Dashboard zum Anzeigen der importierten Daten aus, und wählen Sie eine Kachel, um zu den zugrunde liegenden Berichten zu navigieren.
   
    ![](media/service-connect-to-windows-dev-center/dashboard.png)
   
    ![](media/service-connect-to-windows-dev-center/report.png)

**Was nun?**

* Versuchen Sie, am oberen Rand des Dashboards [im Q&A-Feld eine Frage zu stellen](service-q-and-a.md).
* [Ändern Sie die Kacheln](service-dashboard-edit-tile.md) im Dashboard.
* [Wählen Sie eine Kachel aus](service-dashboard-tiles.md), um den zugrunde liegenden Bericht zu öffnen.
* Ihr Dataset ist auf eine tägliche Aktualisierung festgelegt. Sie können jedoch das Aktualisierungsintervall ändern oder es über **Jetzt aktualisieren** nach Bedarf aktualisieren.

## <a name="whats-included"></a>Inhalt
Das Developer Center-Inhaltspaket für Power BI enthält Analysedaten für Ihre App und für IAP-Käufe (In-App-Produkte) sowie Bewertungen und Kritiken und außerdem Daten zur App-Integrität. Die Daten sind auf die letzte 3 Monate begrenzt. Der Bereich ist ein bewegliches Fenster, sodass die enthaltenen Datumsangaben bei Aktualisierung des Datasets aktualisiert werden.

<a name="Requirements"></a>

## <a name="system-requirements"></a>Systemanforderungen
Für dieses Inhaltspaket müssen Sie mindestens eine App im Windows Store veröffentlicht haben und über ein Windows Dev Center-Konto verfügen (weitere Informationen finden Sie [hier](https://msdn.microsoft.com/windows/uwp/publish/manage-account-users)).

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>Suchen von Parametern
Sie finden die Anwendungs-ID einer App, indem Sie unter „App-Verwaltung“ zur Seite „App-Identität“ wechseln.

Die Anwendungs-ID befindet sich am Ende der URL für den Windows 10 Store: https://www.microsoft.com/store/apps/ **{applicationId}**

## <a name="next-steps"></a>Nächste Schritte
[Erste Schritte mit Power BI](service-get-started.md)

[Abrufen von Daten in Power BI](service-get-data.md)

