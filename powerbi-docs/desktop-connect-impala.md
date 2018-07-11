---
title: Herstellen einer Verbindung mit einer Impala-Datenbank in Power BI Desktop
description: Einfaches Verbinden mit und Verwenden von einer Impala-Datenbank in Power BI Desktop
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 04/24/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 7feb562c5d2d96c4d726b93393a0b4a26c658415
ms.sourcegitcommit: e8d924ca25e060f2e1bc753e8e762b88066a0344
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2018
ms.locfileid: "37134752"
---
# <a name="connect-to-an-impala-database-in-power-bi-desktop"></a>Herstellen einer Verbindung mit einer Impala-Datenbank in Power BI Desktop
In Power BI Desktop können Sie eine Verbindung mit einer **Impala**-Datenbank herstellen und die zugrunde liegenden Daten wie alle anderen Datenquellen in Power BI Desktop verwenden.

## <a name="connect-to-an-impala-database"></a>Herstellen einer Verbindung mit einer Impala-Datenbank
Wählen Sie in Power BI Desktop im Menüband **Start** die Option **Daten abrufen** aus, um eine Verbindung mit einer **Impala**-Datenbank herzustellen. Wählen Sie in den Kategorien auf der linken Seite **Datenbank** aus. Anschließend wird **Impala** angezeigt.

![](media/desktop-connect-impala/connect_impala_2.png)

Geben Sie im angezeigten Fenster **Impala** den Namen des Impala-Servers in das Feld ein, oder fügen Sie ihn ein, und klicken Sie auf **OK**. Sie können Daten entweder direkt in Power BI **importieren** oder **DirectQuery** verwenden. Weitere Informationen finden Sie unter [Verwendung von DirectQuery](desktop-use-directquery.md).

![](media/desktop-connect-impala/connect_impala_3a.png)

Wenn Sie dazu aufgefordert werden, geben Sie Ihre Anmeldeinformationen ein, oder stellen Sie anonym eine Verbindung her. Der Impala-Connector unterstützt die Authentifizierungen „Anonym“, „Basic“ (Benutzername + Kennwort) und „Windows“.

![](media/desktop-connect-impala/connect_impala_4.png)

> [!NOTE]
> Wenn Sie Ihren Benutzernamen und Ihr Kennwort für einen bestimmten **Impala**-Server eingefügt haben, werden von Power BI Desktop für anschließende Verbindungen die gleichen Anmeldeinformationen verwendet. Sie können diese Anmeldeinformationen unter **Datei > Optionen und Einstellungen > Datenquelleneinstellungen** ändern.
> 
> 

Nachdem die Verbindung erfolgreich hergestellt wurde, wird das Fenster **Navigator** mit den auf dem Server verfügbaren Daten angezeigt. Aus diesen können Sie ein oder mehrere Elemente auswählen, die importiert und in **Power BI Desktop** verwendet werden sollen.

![](media/desktop-connect-impala/connect_impala_5.png)

## <a name="considerations-and-limitations"></a>Überlegungen und Einschränkungen
Beim **Impala**-Connector sind einige Einschränkungen und Überlegungen zu beachten:

* Der Impala-Connector wird auf dem lokalen Datengateway mit einem der drei unterstützten Authentifizierungsmechanismen unterstützt.

## <a name="next-steps"></a>Nächste Schritte
Sie können mithilfe von Power BI Desktop eine Verbindung mit Daten jeglicher Art herstellen. Weitere Informationen zu Datenquellen finden Sie in folgenden Ressourcen:

* [Was ist Power BI Desktop?](desktop-what-is-desktop.md)
* [Datenquellen in Power BI Desktop](desktop-data-sources.md)
* [Strukturieren und Kombinieren von Daten mit Power BI Desktop](desktop-shape-and-combine-data.md)
* [Verbinden mit Excel in Power BI Desktop](desktop-connect-excel.md)   
* [Eingeben von Daten direkt in Power BI Desktop](desktop-enter-data-directly-into-desktop.md)   

