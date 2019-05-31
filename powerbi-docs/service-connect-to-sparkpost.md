---
title: Herstellen einer Verbindung mit SparkPost mithilfe von Power BI
description: SparkPost für Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 48cdff67e613093c3ac473b0a505a6f0d57f4f2d
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2019
ms.locfileid: "61171629"
---
# <a name="connect-to-sparkpost-with-power-bi"></a>Herstellen einer Verbindung mit SparkPost mithilfe von Power BI
Das Power BI-Inhaltspaket für SparkPost ermöglicht Ihnen, wertvolle Datasets aus Ihrem SparkPost-Konto in ein aussagekräftiges Dashboard zu extrahieren. Mit dem SparkPost-Inhaltspaket können Sie Ihre gesamte E-Mail-Statistik visualisieren, einschließlich Domänen, Kampagnen und Kundenbindung nach Internetdienstanbieter.

Stellen Sie eine Verbindung mit dem [SparkPost-Inhaltspaket für Power BI](https://app.powerbi.com/getdata/services/spark-post) her.

## <a name="how-to-connect"></a>Herstellen der Verbindung
1. Wählen Sie unten im linken Navigationsbereich **Daten abrufen** aus.
   
   ![](media/service-connect-to-sparkpost/getdata.png)
2. Wählen Sie im Feld **Dienste** die Option **Abrufen**aus.
   
   ![](media/service-connect-to-sparkpost/services.png)
3. Wählen Sie das **SparkPost**-Inhaltspaket aus, und klicken Sie auf **Abrufen**. 
   
   ![](media/service-connect-to-sparkpost/sparkpost.png)
4. Wenn Sie dazu aufgefordert werden, geben Sie Ihren SparkPost-API-Schlüssel an, und wählen Sie „Anmelden“ aus. Nachstehend finden Sie weitere Informationen zum [Suchen dieser Parameter](#FindingParams).
   
   ![](media/service-connect-to-sparkpost/creds.png)
5. Das Laden Ihrer Daten beginnt. Je nach Größe Ihres Kontos kann dies einige Zeit dauern. Nachdem Power BI die Daten importiert hat, werden im linken Navigationsbereich das Standarddashboard, ein Bericht und ein Dataset mit Ihrer E-Mail-Statistik für die letzten 90 Tage angezeigt. Neue Elemente werden mit einem gelben Sternchen \* markiert.
   
   ![](media/service-connect-to-sparkpost/dashboard.png)

**Was nun?**

* Versuchen Sie, am oberen Rand des Dashboards [im Q&A-Feld eine Frage zu stellen](consumer/end-user-q-and-a.md).
* [Ändern Sie die Kacheln](service-dashboard-edit-tile.md) im Dashboard.
* [Wählen Sie eine Kachel aus](consumer/end-user-tiles.md), um den zugrunde liegenden Bericht zu öffnen.
* Zwar ist Ihr Dataset auf tägliche Aktualisierung festgelegt, jedoch können Sie das Aktualisierungsintervall ändern oder über **Jetzt aktualisieren** nach Bedarf aktualisieren.

## <a name="whats-included"></a>Inhalt
Das SparkPost-Inhaltspaket für Power BI enthält Informationen wie einmalige Klicks, die Anzahl akzeptierter Aufrufe, Absprungraten, die Anzahl verzögerter Aufrufe, die Anzahl abgelehnter Aufrufe und weitere.

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>Suchen von Parametern
Das Inhaltspaket verwendet einen API-Schlüssel, um Ihr SparkPost-Konto mit Power BI zu verbinden. Sie finden Ihren API-Schlüssel in Ihrem Konto unter „Konto“ \> „API und SMTP“ (weitere Informationen finden Sie [hier](https://support.sparkpost.com/customer/portal/articles/1933377-create-api-keys)). Es wird empfohlen, einen API-Schlüssel mit Berechtigungen für `Message Events: Read-only ` und `Metrics: Read-only` zu verwenden.

![](media/service-connect-to-sparkpost/sparkpost1.png)

