---
title: Erfassen von zusätzlichen Diagnoseinformationen
description: Erfassen von zusätzlichen Diagnoseinformationen
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 06/28/2017
ms.author: mblythe
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 76860e740d43a1907692a7cd4fed1a6df68c93d4
ms.sourcegitcommit: 998b79c0dd46d0e5439888b83999945ed1809c94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/17/2018
---
# <a name="capturing-additional-diagnostic-information"></a>Erfassen von zusätzlichen Diagnoseinformationen
## <a name="capturing-additional-diagnostic-information-for-power-bi"></a>Erfassen von zusätzlichen Diagnoseinformationen für Power BI
Diese Anweisungen bieten zwei mögliche Optionen für die manuelle Erfassung von zusätzlichen Diagnoseinformationen aus dem Webclient von Power BI.  Nur eine dieser Optionen muss angewendet werden.

## <a name="network-capture---edge--internet-explorer"></a>Netzwerkerfassung – Edge & Internet Explorer
1. Rufen Sie [Power BI](https://app.powerbi.com) mit Microsoft Edge oder Internet Explorer auf.
2. Öffnen Sie die Edge-Entwicklertools, indem Sie F12 drücken.
3. Daraufhin wird das Fenster „Entwicklungstools“ aufgerufen: 
   
   ![](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-developer-tools.png)
4. Wechseln Sie zur Registerkarte „Netzwerk“. Es wird der Datenverkehr aufgelistet, der bereits erfasst wurde. 
   
   ![](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-network-tab.png)
5. Sie können ihn Fenster durchsuchen und jedes Problem, das auftritt, reproduzieren. Sie können das Fenster „Entwicklertools“ während der Sitzung beliebig oft durch Drücken von F12 ausblenden und anzeigen.
6. Um die Aufzeichnung zu beenden, können Sie das rote Quadrat auf der Registerkarte „Netzwerk“ des Entwicklertoolbereichs auswählen.
   
   ![](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-network-tab-stop.png)
7. Klicken Sie auf das Diskettensymbol, um die Aufzeichnung **nach HAR zu exportieren**.
   
   ![](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-network-tab-save.png)
8. Geben Sie einen Dateinamen ein, und speichern Sie die HAR-Datei.
   
    Die HAR-Datei enthält alle Informationen über Netzwerkanforderungen zwischen dem Browserfenster und Power BI.  Dazu gehören die Aktivitäts-IDs für jede Anforderung, der genaue Zeitstempel für jede Anforderung sowie alle an den Client zurückgegebenen Fehlerinformationen.  Diese Ablaufverfolgung enthält außerdem die Daten, die zum Füllen der auf dem Bildschirm angezeigten visuellen Objekte verwendet werden.
9. Sie können die HAR-Datei angeben, um die Überprüfung zu unterstützen.

Weitere Fragen? [Stellen Sie Ihre Frage in der Power BI-Community.](http://community.powerbi.com/)

