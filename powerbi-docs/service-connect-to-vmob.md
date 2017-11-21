---
title: Herstellen einer Verbindung mit VMob mithilfe von Power BI
description: "VMob für Power BI"
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
ms.openlocfilehash: fc0c8bc1ea177e20c25a614ed1de274f70056578
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2017
---
# <a name="connect-to-vmob-with-power-bi"></a>Herstellen einer Verbindung mit VMob mithilfe von Power BI
Das Nachverfolgen und Durchsuchen Ihrer VMob-Daten ist mit Power BI und dem VMob-Inhaltspaket problemlos möglich. Power BI ruft folgende Daten ab: Benutzerstatistik des Gesamtzeitraums sowie der letzten 30 Tage, Leistungskennzahlen Einzelhandel der letzten 30 Tage und Kampagnen-Leistung der letzten 30 Tage.

Stellen Sie die Verbindung zum [VMob-Inhaltspaket](https://app.powerbi.com/getdata/services/vmob) für Power BI her.

## <a name="how-to-connect"></a>Herstellen der Verbindung
1. Wählen Sie unten im linken Navigationsbereich **Daten abrufen** aus.
   
    ![](media/service-connect-to-vmob/getdata.png)
2. Wählen Sie im Feld **Dienste** die Option **Abrufen**aus.
   
   ![](media/service-connect-to-vmob/services.png)
3. Wählen Sie **VMob** \> **Abrufen** aus.
   
   ![](media/service-connect-to-vmob/vmob.png)
4. Geben Sie nach Aufforderung Ihre VMob-URL ein, und klicken Sie auf die Schaltfläche „Weiter“. Diese URL wird separat von VMob bereitgestellt.
   
    ![](media/service-connect-to-vmob/params.png)
5. Wählen Sie in der Dropdownliste für die Authentifizierungsmethode **Basic** aus, geben Sie den VMob-Benutzernamen und das Kennwort ein, und klicken Sie auf die Schaltfläche **Anmelden** .
   
    ![](media/service-connect-to-vmob/creds.png)
6. Der Importvorgang beginnt automatisch, und Power BI ruft die VMob-Daten ab, um ein vorgefertigtes Dashboard und einen Bericht zu erstellen.
   
   ![](media/service-connect-to-vmob/dashboard2.png)

**Was nun?**

* Versuchen Sie, am oberen Rand des Dashboards [im Q&A-Feld eine Frage zu stellen](service-q-and-a.md).
* [Ändern Sie die Kacheln](service-dashboard-edit-tile.md) im Dashboard.
* [Wählen Sie eine Kachel aus](service-dashboard-tiles.md), um den zugrunde liegenden Bericht zu öffnen.
* Ihr Dataset ist auf eine tägliche Aktualisierung festgelegt. Sie können jedoch das Aktualisierungsintervall ändern oder es über **Jetzt aktualisieren** nach Bedarf aktualisieren.

## <a name="next-steps"></a>Nächste Schritte
[Erste Schritte mit Power BI](service-get-started.md)

[Abrufen von Daten in Power BI](service-get-data.md)

