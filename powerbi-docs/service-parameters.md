---
title: Anzeigen und Bearbeiten von Datasetparametereinstellungen im Power BI-Dienst
description: Abfrageparameter werden in Power BI Desktop erstellt, können jedoch im Power BI-Dienst geprüft und aktualisiert werden.
author: mihart
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 06/26/2018
ms.author: mihart
LocalizationGroup: Create reports
ms.openlocfilehash: ac271e8013bce5824931153351a651644a716a2f
ms.sourcegitcommit: 5eb8632f653b9ea4f33a780fd360e75bbdf53b13
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2018
ms.locfileid: "36965157"
---
# <a name="what-is-a-query-parameter"></a>Was ist ein Abfrageparameter?
Abfrageparameter werden in Power BI Desktop von Berichtserstellern hinzugefügt. Mit Parametern können sie Teile von Berichten von mindestens einem *Parameterwert* abhängig machen. Ein Berichtsersteller kann z.B. einen Parameter erstellen, der die Daten auf ein Land bzw. eine Region einschränkt, oder einen Parameter, der das akzeptierte Format von Feldern (z.B. für Datumsangaben, Uhrzeitangaben und Text) definiert.

![Registerkarte „Start“ mit der Option „Parameter verwalten“ in Power BI Desktop](media/service-parameters/power-bi-manage-parameters.png)


## <a name="review-and-edit-parameters-in-power-bi-service"></a>Überprüfen und Bearbeiten von Parametern im Power BI-Dienst

Wenn die Parameter in Power BI Desktop definiert wurden, wenn dieser [Bericht im Power BI-Dienst veröffentlicht wird](desktop-upload-desktop-files.md), werden gleichzeitig auch die Parametereinstellungen und -optionen übertragen. Einige Parametereinstellungen können im Power BI-Dienst geprüft und bearbeitet werden. Dies gilt nicht für Parameter, die die verfügbaren Daten einschränken, sondern nur für diejenigen, die akzeptierte Werte definieren und beschreiben.

1. Klicken Sie im Power BI-Dienst auf das Zahnradsymbol ![Zahnradsymbol](media/service-parameters/power-bi-cog.png), um die **Einstellungen** zu öffnen.

2. Klicken Sie auf die Registerkarte **Datasets**, und wählen Sie ein Dataset in der Liste aus. 
    
    ![Fenster „Einstellungen“ mit der Registerkarte „Datasets“](media/service-parameters/power-bi-select-dataset2.png)

3. Erweitern Sie **Parameter**.  Wenn das ausgewählte Dataset keine Parameter aufweist, wird eine Meldung mit einem Link anzeigt, unter dem Sie mehr zu Abfrageparameter erfahren können. Wenn das Dataset über Parameter verfügt, werden diese beim Erweitern von **Parameter** angezeigt. 

    ![Fenster „Einstellungen“ mit erweiterter Option „Parameter“](media/service-parameters/power-bi-settings.png)

    Prüfen Sie die Parametereinstellungen, und nehmen Sie bei Bedarf Änderungen vor. Ausgegraute Felder können nicht bearbeitet werden. 


## <a name="next-steps"></a>Nächste Schritte
Sie können Parameter im Handumdrehen hinzuzufügen, indem Sie [die URL modifizieren](service-url-filters.md).