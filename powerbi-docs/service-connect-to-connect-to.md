---
title: Herstellen einer Verbindung mit comScore Digital Analytix mithilfe von Power BI
description: comScore Digital Analytix für Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: bc9a8637416bdea50e955c1aea73bbcfeed51bb6
ms.sourcegitcommit: 2a7bbb1fa24a49d2278a90cb0c4be543d7267bda
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2018
ms.locfileid: "34242999"
---
# <a name="connect-to-comscore-digital-analytix-with-power-bi"></a>Herstellen einer Verbindung mit comScore Digital Analytix mithilfe von Power BI
Visualisieren und durchsuchen Sie Ihre comScore Digital Analytix-Daten in Power BI mit dem Power BI-Inhaltspaket. Die Daten werden automatisch einmal täglich aktualisiert.

Stellen Sie eine Verbindung mit dem [comScore-Inhaltspaket](https://app.powerbi.com/getdata/services/comscore) für Power BI her.

>[!NOTE]
>Zum Herstellen einer Verbindung zum Inhaltspaket benötigen Sie ein comScore DAx-Benutzerkonto und Zugriff auf die comScore-API. Weitere [Details](#Requirements) finden Sie unten.

## <a name="how-to-connect"></a>Herstellen der Verbindung
1. Wählen Sie unten im linken Navigationsbereich „Daten abrufen“ aus.
   
   ![](media/service-connect-to-connect-to/getdata.png)
2. Wählen Sie im Feld **Dienste** die Option **Abrufen**aus.
   
   ![](media/service-connect-to-connect-to/services.png)
3. Wählen Sie **comScore Digital Analytix** \> **Abrufen** aus.
   
   ![](media/service-connect-to-connect-to/comscore.png)
4. Geben Sie das Datacenter, die comScore-Client-ID und die Website an, mit denen Sie eine Verbindung herstellen möchten. Details dazu, wie Sie diese Werte finden, finden Sie unten unter [Ermitteln Ihrer comScore-Parameter](#FindingParams).
   
   ![](media/service-connect-to-connect-to/parameters.png)
5. Geben Sie Ihren comScore-Benutzernamen und das Kennwort ein, um die Verbindung herzustellen. Einzelheiten zum Ermitteln dieses Werts finden Sie unten.
   
   ![](media/service-connect-to-connect-to/creds.png)
6. Der Importvorgang startet automatisch. Nach Abschluss des Vorgangs werden im Navigationsbereich ein neues Dashboard, ein Bericht und ein Modell angezeigt. Wählen Sie das Dashboard aus, um die importierten Daten anzuzeigen.

**Was nun?**

* Versuchen Sie, am oberen Rand des Dashboards [im Q&A-Feld eine Frage zu stellen](power-bi-q-and-a.md).
* [Ändern Sie die Kacheln](service-dashboard-edit-tile.md) im Dashboard.
* [Wählen Sie eine Kachel aus](service-dashboard-tiles.md), um den zugrunde liegenden Bericht zu öffnen.
* Ihr Dataset ist auf eine tägliche Aktualisierung festgelegt. Sie können jedoch das Aktualisierungsintervall ändern oder es über **Jetzt aktualisieren** nach Bedarf aktualisieren.

<a name="Requirements"></a>

## <a name="system-requirements"></a>Systemanforderungen
Ein comScore DAx-Benutzerkonto und Zugriff auf die comScore DAx-API sind für das Herstellen der Verbindung erforderlich. Wenden Sie sich an Ihren comScore DAx-Administrator, um Ihr Konto zu bestätigen.

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>Suchen von Parametern
Details zum Ermitteln Ihrer einzelnen comScore-Parameter finden Sie unten.

**Rechenzentrum**

Das Rechenzentrum, mit dem Sie eine Verbindung herstellen, wird durch die URL bestimmt, zu der Sie in comScore navigieren.

Wenn Sie https://dax.comscore.com, verwenden, geben Sie „US“ ein, wenn Sie https://dax.comscore.eu verwenden, geben Sie „EU“ ein.

![](media/service-connect-to-connect-to/comscore_url.png) 

**Client**

Der Client ist der gleiche, den Sie auch bei der Anmeldung bei comScore DAx übergeben.

![](media/service-connect-to-connect-to/comscore_signin.png) 

**Website**

Die comScore-Website bestimmt die Website, deren Daten verwendet werden. Die Liste der Websites können Sie in Ihrem comScore-Konto finden.

![](media/service-connect-to-connect-to/comscore_sites.png)

## <a name="next-steps"></a>Nächste Schritte
[Erste Schritte mit Power BI](service-get-started.md)

[Abrufen von Daten in Power BI](service-get-data.md)

