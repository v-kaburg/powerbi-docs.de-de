---
title: Erfassen von zusätzlichen Diagnoseinformationen
description: Diese Anweisungen bieten zwei mögliche Optionen für die manuelle Erfassung von zusätzlichen Diagnoseinformationen aus dem Webclient von Power BI.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 04/25/2019
ms.author: mblythe
ms.custom: seodec18
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 710fb4cdcf9efb051434966d47c2eaced17ac9ba
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2019
ms.locfileid: "65100230"
---
# <a name="capture-additional-diagnostic-information-for-power-bi"></a>Erfassen von zusätzlichen Diagnoseinformationen für Power BI

Dieser Artikel enthält Anweisungen für die manuelle Erfassung von zusätzlichen Diagnoseinformationen aus dem Power BI-Web-Client.

1. Navigieren Sie zu [Power BI](https://app.powerbi.com) mit Microsoft Edge oder InternetExplorer.

1. Drücken Sie **F12** zu den Microsoft Edge-Entwicklertools zu öffnen.

   ![Screenshot des Microsoft Edge-Entwickler-Tools-Elemente-Registerkarte.](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-developer-tools.png)

1. Wählen Sie die Registerkarte **Network** (Netzwerk) aus. Es wird der Datenverkehr aufgelistet, der bereits erfasst wurde.

   ![Screenshot des Microsoft Edge-Entwickler-Tools-Registerkarte ("Netzwerk".](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-network-tab.png)

    Sie können:

    * Navigieren Sie im Fenster, und reproduzieren Sie ggf. vorhandene Probleme, die Sie möglicherweise stoßen.

    * Ausblenden und Anzeigen des Entwicklers Fenster zu einem beliebigen Zeitpunkt während der Sitzung durch Drücken von F12.

1. Sie können das rote Quadrat auf auswählen, um die Profilerstellungssitzung zu beenden, die **Netzwerk** Registerkarte des Entwicklers tools Bereich.

   ![Screenshot des Microsoft Edge Developer Tools Registerkarte "Netzwerk" mit einem Aufruf aus der Schaltfläche "Beenden".](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-network-tab-stop.png)

1. Wählen Sie das Diskettensymbol, um die Daten als HTTP-Archiv (HAR)-Datei zu exportieren.

   ![Screenshot des Microsoft Edge Developer Tools Registerkarte "Netzwerk" in einer Legende aus, der das Diskettensymbol.](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-network-tab-save.png)

1. Geben Sie einen Dateinamen ein, und speichern Sie die HAR-Datei.

    Die HAR-Datei enthält alle Informationen über netzwerkanforderungen zwischen dem Browserfenster und Power BI einschließlich:

    * Die Aktivitäts-IDs für jede Anforderung.

    * Der genaue Zeitstempel für jede Anforderung.

    * Alle Fehlerinformationen, die an den Client zurückgegeben wird.

    Diese Ablaufverfolgung enthält außerdem die Daten, die zum Füllen der auf dem Bildschirm angezeigten visuellen Objekte verwendet werden.

1. Sie können die HAR-Datei angeben, um die Überprüfung zu unterstützen.

Weitere Fragen? [Stellen Sie Ihre Frage in der Power BI-Community.](http://community.powerbi.com/)
