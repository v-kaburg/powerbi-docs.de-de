---
title: Herstellen einer Verbindung zu Daten, die von Power BI-Dataflows in Power BI Desktop (Vorschauversion) erstellt wurden
description: Einfaches Verbinden mit und Verwenden von Dataflows in Power BI Desktop
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 09/10/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: f3964b96f8f282772f6d511c9c412e0caabd1d00
ms.sourcegitcommit: c51461690e8faa121a1325957ca79b7a3975e8b8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2018
ms.locfileid: "44512913"
---
# <a name="connect-to-data-created-by-power-bi-dataflows-in-power-bi-desktop-preview"></a>Herstellen einer Verbindung zu Daten, die von Power BI-Dataflows in Power BI Desktop (Vorschauversion) erstellt wurden
In **Power BI Desktop** können Sie eine Verbindung mit Daten herstellen, die von **Power BI-Dataflows** wie alle anderen Datenquellen in Power BI Desktop erstellt wurden.

![Verbinden mit Dataflows](media/desktop-connect-dataflows/connect-dataflows_01.png)

Mit dem Connector **Power BI-Dataflows (Vorschauversion)** können Sie eine Verbindung zu Entitäten herstellen, die von Dataflows im Power BI-Dienst erstellt wurden. Da sich Dataflows in der Vorschauphase befinden, müssen Sie einige Schritte ausführen, um den Dataflows-Connector auf Ihrem System verfügbar zu machen. 


## <a name="download-and-enable-the-power-bi-dataflows-connector-preview"></a>Herunterladen und Aktivieren des Power BI-Dataflows-Connectors (Vorschauversion)

Sie müssen eine Kopie des **Power BI-Dataflows**-Connectors herunterladen und diese dann an einen bestimmten Speicherort auf Ihrem Computer kopieren. In einem zukünftigen monatlichen Update für Power BI Desktop ist der Connector automatisch in der Liste von Datenconnectors enthalten. Dann sind die genannten Schritte nicht mehr vonnöten.

Sie können den **Power BI-Dataflows-Connector** hier herunterladen: [Power BI-Dataflows-Connector](https://visuals.azureedge.net/cds-analytics/PublicPreview/CDSA.mez)

Mit den folgenden Schritten können Sie den **Power BI-Dataflows**-Connector (Vorschauversion) auf Ihrem Computer verfügbar machen.

1. Laden Sie eine Kopie der MEZ-Datei (Datenconnectordatei) herunter. Kunden der privaten Vorschau erhalten die Downloadinformationen für die MEZ-Datei direkt von Microsoft.

2. Legen Sie die heruntergeladene Datenconnectordatei im folgenden Ordner auf Ihrem Computer ab: **Dokumente > Power BI Desktop > Ordner „Benutzerdefinierte Connectors“**.

3. Wechseln Sie in Power BI Desktop zu **Datei > Optionen und Einstellungen > Optionen**, und wählen Sie dann im linken Bereich **Vorschaufeatures** aus.

    ![Aktivieren der benutzerdefinierten Connectors](media/desktop-connect-dataflows/connect-dataflows_02.png)

4. Aktivieren Sie das Feld **Benutzerdefinierte Datenconnectors**, falls es nicht schon aktiviert ist. 

5. Starten Sie **Power BI Desktop** neu, damit der Connector angezeigt wird.

## <a name="use-the-power-bi-dataflows-connector-preview"></a>Verwenden des Power BI-Dataflows-Connectors (Vorschauversion)
Sobald **Power BI Desktop** neu gestartet wurde, wird der Connector als verfügbare Datenquelle angezeigt. Klicken Sie wie in der folgenden Abbildung gezeigt auf **Daten abrufen > Onlinedienste > Power BI-Dataflows (Beta)**, um eine Verbinden mit dem Datenpool herzustellen.

![Verbinden mit Dataflows](media/desktop-connect-dataflows/connect-dataflows_01.png)

## <a name="considerations-and-limitations"></a>Überlegungen und Einschränkungen

Damit Sie diese Vorschauversion des **Power BI-Dataflows-Connectors** verwenden können, müssen Sie die neueste Version von **Power BI Desktop** ausführen. Sie können [Power BI Desktop jederzeit herunterladen](desktop-get-the-desktop.md) und auf Ihrem Computer installieren, um sicherzustellen, dass Sie über die neueste Version verfügen.  

Hinweis: Wenn der Power BI-Dataflows-Connector in einem zukünftigen monatlichen Update für **Power BI Desktop** erscheint, *müssen* Sie die heruntergeladene MEZ-Datei aus dem Ordner unter **Dokumente > Power BI Desktop > Benutzerdefinierte Connectors** löschen, um Konflikte zu vermeiden. 


## <a name="next-steps"></a>Nächste Schritte
Mit Power BI-Datenverbindungen können Sie viele interessante Aktionen durchführen. In den Artikeln zu **Power BI Desktop** erhalten Sie weitere nützliche Informationen:

* [Datenquellen in Power BI Desktop](desktop-data-sources.md)
* [Strukturieren und Kombinieren von Daten mit Power BI Desktop](desktop-shape-and-combine-data.md)
* [Eingeben von Daten direkt in Power BI Desktop](desktop-enter-data-directly-into-desktop.md)   

