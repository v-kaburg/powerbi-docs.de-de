---
title: Bearbeiten von Parametereinstellungen im Power BI-Dienst
description: Abfrageparameter werden in Power BI Desktop erstellt, können jedoch im Power BI-Dienst geprüft und aktualisiert werden.
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 11/21/2018
ms.author: maggies
LocalizationGroup: Create reports
ms.openlocfilehash: 8db6f106ecc2285cb66ff980bc72fa666456f81a
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2019
ms.locfileid: "61225981"
---
# <a name="edit-parameter-settings-in-the-power-bi-service"></a>Bearbeiten von Parametereinstellungen im Power BI-Dienst
Abfrageparameter werden in Power BI Desktop von Berichtserstellern hinzugefügt. Mit Parametern können sie Teile von Berichten von mindestens einem *Parameterwert* abhängig machen. Ein Berichtsersteller kann z.B. einen Parameter erstellen, der die Daten auf ein Land bzw. eine Region einschränkt, oder einen Parameter, der das akzeptierte Format von Feldern (z.B. für Datumsangaben, Uhrzeitangaben und Text) definiert.

![Registerkarte „Start“ mit der Option „Parameter verwalten“ in Power BI Desktop](media/service-parameters/power-bi-manage-parameters.png)

## <a name="review-and-edit-parameters-in-power-bi-service"></a>Überprüfen und Bearbeiten von Parametern im Power BI-Dienst

Berichtsersteller definieren Parameter in Power BI Desktop. Wenn sie diesen Bericht dann [im Power BI-Dienst veröffentlichen](desktop-upload-desktop-files.md), werden die Parametereinstellungen und -auswahl übernommen. Einige Parametereinstellungen können im Power BI-Dienst geprüft und bearbeitet werden. Dies gilt nicht für Parameter, die die verfügbaren Daten einschränken, sondern nur für diejenigen, die akzeptierte Werte definieren und beschreiben.

1. Klicken Sie im Power BI-Dienst auf das Zahnradsymbol ![Zahnradsymbol](media/service-parameters/power-bi-cog.png), um die **Einstellungen** zu öffnen.

2. Klicken Sie auf die Registerkarte **Datasets**, und wählen Sie ein Dataset in der Liste aus. 
    
    ![Fenster „Einstellungen“ mit der Registerkarte „Datasets“](media/service-parameters/power-bi-select-dataset2.png)

3. Erweitern Sie **Parameter**.  Wenn das ausgewählte Dataset keine Parameter aufweist, wird eine Meldung mit einem Link anzeigt, unter dem Sie mehr zu Abfrageparameter erfahren können. Wenn das Dataset über Parameter verfügt, werden diese beim Erweitern von **Parameter** angezeigt. 

    ![Fenster „Einstellungen“ mit erweiterter Option „Parameter“](media/service-parameters/power-bi-settings.png)

    Prüfen Sie die Parametereinstellungen, und nehmen Sie bei Bedarf Änderungen vor. Ausgegraute Felder können nicht bearbeitet werden. 


## <a name="next-steps"></a>Nächste Schritte
Sie können Parameter im Handumdrehen hinzuzufügen, indem Sie [die URL modifizieren](service-url-filters.md).