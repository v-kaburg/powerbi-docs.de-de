---
title: Herstellen einer Verbindung mit Adobe Analytics in Power BI Desktop (Vorschau)
description: Einfaches Verbinden mit und Verwenden von Adobe Analytics in Power BI Desktop
services: powerbi
documentationcenter: 
author: davidiseminger
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 03/09/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: efd6d066e2f98f86248730917c2f4aa0c8a39983
ms.sourcegitcommit: 4217430c3419046c3a90819c34f133ec7905b6e7
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2018
---
# <a name="connect-to-adobe-analytics-in-power-bi-desktop-preview"></a>Herstellen einer Verbindung mit Adobe Analytics in Power BI Desktop (Vorschau)
In **Power BI Desktop** können Sie eine Verbindung mit **Adobe Analytics** herstellen und die zugrunde liegenden Daten wie alle anderen Datenquellen in Power BI Desktop verwenden. 

![Abrufen von Daten aus Adobe Analytics](media/desktop-connect-adobe-analytics/connect-adobe-analytics_01.png)

## <a name="enable-the-adobe-analytics-connector-preview"></a>Aktivieren der Vorschau für Adobe Analytics-Connector 
Der **Adobe Analytics**-Connector ist derzeit als Vorschauversion verfügbar. Aktivieren Sie das Vorschaufeature, damit der Connector im Fenster **Daten abrufen** verfügbar ist. Wenn Sie das Connector-Vorschaufeature aktivieren möchten, wählen Sie in Power BI Desktop **Datei > Optionen und Einstellungen > Optionen > Vorschaufeatures** aus, und aktivieren Sie dann das Kontrollkästchen neben **Lesezeichen**. 

![Aktivieren der Vorschau für Adobe Analytics-Connector unter Optionen](media/desktop-connect-adobe-analytics/connect-adobe-analytics_02.png)

Zum Aktivieren der Vorschau für Adobe Analytics-Connector müssen Sie **Power BI Desktop** neu starten, nachdem Sie die Auswahl vorgenommen haben.

## <a name="connect-to-adobe-analytics-data"></a>Herstellen einer Verbindung mit Adobe Analytics-Daten
Wählen Sie in Power BI Desktop im Menüband **Start** die Option **Daten abrufen** aus, um eine Verbindung mit den **Adobe Analytics**-Daten herzustellen. Wählen Sie in den Kategorien auf der linken Seite **Onlinedienste** aus. Anschließend wird **Adobe Analytics-Connector** angezeigt.

![Abrufen von Daten aus Adobe Analytics](media/desktop-connect-adobe-analytics/connect-adobe-analytics_01.png)

Wählen Sie im angezeigten Fenster **Adobe Analytics** die Schaltfläche **Anmelden** aus, und geben Sie die Anmeldeinformationen für Ihr Adobe Analytics-Konto ein. Das Anmeldefenster für Adobe wird wie folgt angezeigt:

![Anmelden bei Adobe Analytics](media/desktop-connect-adobe-analytics/connect-adobe-analytics_03.png)

Wenn Sie dazu aufgefordert werden, geben Sie Ihren Benutzernamen und Ihr Kennwort ein. Nachdem die Verbindung hergestellt ist, werden mehrere Dimensionen und Measures im Power BI-Dialogfeld **Navigator** als Vorschau angezeigt, die Sie auswählen können, um eine einzelne tabellarische Ausgabe zu erstellen. Sie können auch alle Eingabeparameter angeben, die für die ausgewählten Elemente erforderlich sind. 

![Auswählen von Daten mit dem Navigator](media/desktop-connect-adobe-analytics/connect-adobe-analytics_04.png)

Sie können die ausgewählte Tabelle **laden**, um die gesamte Tabelle in **Power BI Desktop** zu importieren, oder Sie können die Abfrage **bearbeiten**. Wenn Sie „Bearbeiten“ auswählen, wird der **Abfrage-Editor** geöffnet, sodass Sie den Satz der zu verwendenden Daten filtern und aufbereiten können, um diesen aufbereiteten Satz von Daten anschließend in **Power BI Desktop** zu laden.

![Laden oder Bearbeiten von Daten im Navigator](media/desktop-connect-adobe-analytics/connect-adobe-analytics_05.png)


## <a name="next-steps"></a>Nächste Schritte
Sie können mithilfe von Power BI Desktop eine Verbindung mit Daten jeglicher Art herstellen. Weitere Informationen zu Datenquellen finden Sie in folgenden Ressourcen:

* [Erste Schritte mit Power BI Desktop](desktop-getting-started.md)
* [Datenquellen in Power BI Desktop](desktop-data-sources.md)
* [Strukturieren und Kombinieren von Daten mit Power BI Desktop](desktop-shape-and-combine-data.md)
* [Verbinden mit Excel in Power BI Desktop](desktop-connect-excel.md)   
* [Eingeben von Daten direkt in Power BI Desktop](desktop-enter-data-directly-into-desktop.md)   

