---
title: Herstellen einer Verbindung mit Microsoft Azure Consumption Insights mithilfe von Power BI
description: Microsoft Azure Consumption Insights für Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggies
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 05/20/2019
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 089f8c31a0b1eb11f6871268f2f848949be95d9b
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2019
ms.locfileid: "66222120"
---
# <a name="connect-to-microsoft-azure-consumption-insights-with-power-bi"></a>Herstellen einer Verbindung mit Microsoft Azure Consumption Insights mithilfe von Power BI
Untersuchen und überwachen Sie Ihre Microsoft Azure-Nutzungsdaten in Power BI mit dem Power BI-Inhaltspaket. Die Daten werden automatisch einmal täglich aktualisiert.

Stellen Sie eine Verbindung mit dem [Microsoft Azure Consumption Insights-Inhaltspaket](https://app.powerbi.com/getdata/services/azureconsumption) für Power BI her.

## <a name="how-to-connect"></a>Herstellen der Verbindung
1. Wählen Sie unten im linken Navigationsbereich **Daten abrufen** aus.
   
    ![](media/service-connect-to-azure-consumption-insights/getdata.png)
2. Wählen Sie im Feld **Dienste** die Option **Abrufen**aus.
   
   ![](media/service-connect-to-azure-consumption-insights/services.png)
3. Wählen Sie **Microsoft Azure Consumption Insights** \> **jetzt**. 
   
   ![](media/service-connect-to-azure-consumption-insights/mazureconsumption.png)
4. Geben Sie die Anzahl der Monate, für die Sie Daten importieren möchten, und Ihre Azure Enterprise-Registrierungsnummer ein. Nachstehend finden Sie weitere Informationen zum [Suchen dieser Parameter](#FindingParams).
   
    ![](media/service-connect-to-azure-consumption-insights/azureconsumptionparams.png)
5. Geben Sie zum Herstellen der Verbindung Ihren Zugriffsschlüssel ein. Sie finden Ihre Schlüssel für die Registrierung im Azure EA-Portal. 
   
    ![](media/service-connect-to-azure-consumption-insights/msazureconsumptioncreds.png)
6. Der Importvorgang startet automatisch. Nach Abschluss des Vorgangs werden Sie im Navigationsbereich ein neues Dashboard, Bericht und Modell angezeigt. Wählen Sie das Dashboard aus, um die importierten Daten anzuzeigen.
   
   ![](media/service-connect-to-azure-consumption-insights/msazureconsumptiondashboard.png)

**Was nun?**

* Versuchen Sie, am oberen Rand des Dashboards [im Q&A-Feld eine Frage zu stellen](consumer/end-user-q-and-a.md).
* [Ändern Sie die Kacheln](service-dashboard-edit-tile.md) im Dashboard.
* [Wählen Sie eine Kachel aus](consumer/end-user-tiles.md), um den zugrunde liegenden Bericht zu öffnen.
* Während das Dataset aktualisieren täglich geplant ist, können Sie jedoch das Aktualisierungsintervall ändern oder aktualisieren sie bei Bedarf mit **jetzt aktualisieren**

## <a name="whats-included"></a>Inhalt
Das Microsoft Azure Consumption Insights-Inhaltspaket enthält monatliche Berichtsdaten für den Monatsbereich, die, den Sie beim Herstellen einer Verbindung angegeben haben. Der Bereich ist ein bewegliches Fenster, sodass die enthaltenen Datumsangaben aktualisiert werden, da das Dataset aktualisiert.

## <a name="system-requirements"></a>Systemanforderungen
Das Inhaltspaket erfordert Zugriff auf die Enterprise-Features im Azure-Portal. 

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>Suchen von Parametern
Power BI-berichterstellung steht für direkte EA, Partner und indirekte Kunden zur Verfügung, die Abrechnungsinformationen anzeigen können. Unten finden Sie Informationen zum Suchen aller Werte, die der Verbindung erforderlichen erwartet wird.

**Anzahl Monate**

* Die Anzahl der Monate (1 und 36) von Daten von heute, die Sie importieren möchten.

**Registrierungsnummer**

* Ihre Azure Enterprise-Registrierungsnummer, finden Sie unter den [Azure Enterprise Portal](https://ea.azure.com/) home-Bildschirm unter **Registrierungsdetails**.
  
    ![](media/service-connect-to-azure-consumption-insights/params2.png)

**Zugriffsschlüssel**

* Sie finden den Zugriffsschlüssel im Azure Enterprise-Portal unter **Nutzung herunterladen** > **API-Zugriffsschlüssel**.
  
    ![](media/service-connect-to-azure-consumption-insights/creds2.png)

**Zusätzliche Hilfe**

* Für zusätzliche Hilfe bei der Einrichtung der Azure Enterprise Power BI-Paket, melden Sie sich beim Azure Enterprise Portal, und zeigen Sie die API-Hilfedatei unter **Hilfe**. Sie erhalten auch weitere Anweisungen unter **Berichte** -> **Nutzung herunterladen** -> **API-Zugriffsschlüssel**.

## <a name="next-steps"></a>Nächste Schritte
[Erste Schritte mit Power BI](service-get-started.md)

[Abrufen von Daten in Power BI](service-get-data.md)

