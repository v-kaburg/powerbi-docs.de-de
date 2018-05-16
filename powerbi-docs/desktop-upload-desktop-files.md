---
title: Veröffentlichen aus Power BI Desktop
description: Veröffentlichen aus Power BI Desktop
services: powerbi
documentationcenter: ''
author: davidiseminger
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: get-started-article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 05/02/2018
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: f70088d4b6b064a72603bc59e6ba1e07cdb5e1b0
ms.sourcegitcommit: f679c05d029ad0765976d530effde744eac23af5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="publish-from-power-bi-desktop"></a>Veröffentlichen aus Power BI Desktop
Wenn Sie eine **Power BI Desktop**-Datei für den **Power BI-Dienst** veröffentlichen, werden die Daten im Modell und alle Berichte, die Sie in der **Berichtsansicht** erstellt haben, in Ihrem Power BI-Arbeitsbereich veröffentlicht. Ein neues Dataset mit dem gleichen Namen und die jeweiligen Berichte werden im Navigationsbereich Ihres Arbeitsbereichs angezeigt.

Das Veröffentlichen aus **Power BI Desktop** hat die gleiche Auswirkung wie die Verwendung der Funktion **Abrufen von Daten** in Power BI, um eine Verbindung mit einer **Power BI Desktop**-Datei herzustellen und diese hochzuladen.

> [!NOTE]
> Alle von Ihnen an Power BI-Berichten vorgenommenen Änderungen, z.B. das Hinzufügen, Löschen oder Ändern von Visualisierungen in Berichten, werden nicht in der ursprünglichen **Power BI Desktop**-Datei gespeichert.
> 
> 

## <a name="to-publish-a-power-bi-desktop-dataset-and-reports"></a>So veröffentlichen Sie ein Power BI Desktop-Dataset und die zugehörigen Berichte
1. Wählen Sie in Power BI Desktop die Optionen \>**Datei**\>**Veröffentlichen**\>**In Power BI veröffentlichen**, oder klicken Sie im Menüband auf **Veröffentlichen**.  
   ![](media/desktop-upload-desktop-files/pbid_publish_publishbutton.png)
2. Melden Sie sich bei Power BI an.

Wenn der Vorgang abgeschlossen ist, erhalten Sie einen Link zum Öffnen des Berichts auf Ihrer Power BI-Website.  
    ![](media/desktop-upload-desktop-files/pbid_publish_success.png)

## <a name="re-publish-or-replace-a-dataset-published-from-power-bi-desktop"></a>Erneutes Veröffentlichen oder Ersetzen eines über Power BI Desktop veröffentlichten Datasets
Wenn Sie eine **Power BI Desktop**-Datei veröffentlichen, werden das Dataset und alle in **Power BI Desktop** erstellten Berichte auf Ihre Power BI-Website hochgeladen. Wenn Sie Ihre **Power BI Desktop**-Datei erneut veröffentlichen, wird das Dataset auf der Power BI-Website durch das aktualisierte Dataset aus der **Power BI Desktop**-Datei ersetzt.

Dies ist alles relativ einfach, aber Sie sollten über folgende Punkte Bescheid wissen:

* Das Veröffentlichen kann fehlschlagen, wenn Sie in Power BI bereits über zwei oder mehr Datasets verfügen, die den gleichen Namen wie die **Power BI Desktop**-Datei haben. Stellen Sie sicher, dass in Power BI nur ein Dataset mit dem gleichen Namen vorhanden ist. Sie können die Datei auch umbenennen und veröffentlichen, um ein neues Dataset mit dem gleichen Namen wie die Datei zu erstellen.
* Wenn Sie eine Spalte oder ein Measure umbenennen oder löschen, können Fehler für Visualisierungen auftreten, die in Power BI bereits mit diesem Feld vorhanden sind. 
* Power BI ignoriert einige Formatänderungen vorhandener Spalten. Beispiel: Sie ändern das Format einer Spalte von 0,25 in 25 %.
* Wenn Sie einen Aktualisierungszeitplan für Ihr vorhandenes Dataset in Power BI konfiguriert haben und Sie der Datei neue Datenquellen hinzufügen und dann erneut veröffentlichen müssen Sie hierfür unter *Datenquellen verwalten* vor der nächsten geplanten Aktualisierung eine Anmeldung durchführen.

