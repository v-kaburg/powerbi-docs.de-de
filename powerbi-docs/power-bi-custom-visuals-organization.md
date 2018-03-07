---
title: "Verwenden von benutzerdefinierten Visuals für Organisationen in Power BI"
description: "Verwenden, Verwalten und Erstellen von benutzerdefinierten Visuals für Organisationen in Power BI"
services: powerbi
documentationcenter: 
author: markingmyname
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
ms.date: 02/06/2018
ms.author: maghan
LocalizationGroup: Visualizations
ms.openlocfilehash: 6f7827f7804fcd52e7d922ebc8ffad5a8036b33c
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/24/2018
---
# <a name="using-organization-custom-visuals-in-power-bi-preview"></a>Verwenden von benutzerdefinierten Visuals für Organisationen in Power BI (Vorschau)

Sie können benutzerdefinierte Visuals in Power BI verwenden, um ein einzigartiges Visual zu erstellen, das auf Sie oder die Einblicke in Daten, die Sie übermitteln möchten, angepasst ist. Diese benutzerdefinierten Visuals werden häufig von Entwicklern erstellt. Der Grund dafür ist oft, dass die Visuals, die in Power BI enthalten sind, deren Anforderungen nicht erfüllen. 

In einigen Organisationen sind benutzerdefinierte Visuals sogar noch wichtiger, da sie notwendig sein können, um bestimmte Daten oder Einsichten zu übermitteln, die für die Organisation einzigartig sind. Sie können ebenfalls spezielle Anforderungen für Daten enthalten oder private Geschäftsmethoden hervorheben. Solche Organisationen müssen benutzerdefinierte Visuals entwickeln, diese innerhalb der Organisation freigeben und sicherstellen, dass sie ordnungsgemäß verwaltet werden. Durch benutzerdefinierte Power BI-Visuals (jetzt in der Vorschau) können Organisationen dies erreichen. 

Die folgende Abbildung stellt den Prozess dar, den benutzerdefinierte Visuals für Organisationen (Vorschau) in Power BI durchlaufen. Dieser beginnt beim Administrator, wird in der Entwicklung und Verwaltung fortgesetzt und endet beim Datenanalysten.

![](media/power-bi-custom-visuals-organizational/custom-visual-org-01.jpg)

## <a name="how-to-enable-organizational-custom-visuals-preview"></a>Aktivieren von benutzerdefinierten Visuals für Organisationen (Vorschau)

Benutzerdefinierte Visuals für Organisationen befinden sich derzeit in der Vorschauversion, darum müssen Sie das Feature in Power BI Desktop aktivieren. Aktivieren Sie dieses Vorschaufeature, indem Sie im Menüband auf „Datei > Optionen und Einstellungen > Optionen“ und dann im linken Bereich auf „Vorschaufeatures“ klicken. Aktivieren Sie dann wie in der folgenden Abbildung dargestellt das Kontrollkästchen neben dem benutzerdefinierten Visual „My organization“.

![](media/power-bi-custom-visuals-organizational/custom-visual-org-02.jpg)

Visuals für Organisationen werden vom Power BI-Administrator über das Verwaltungsportal bereitgestellt und verwaltet. Nach der Bereitstellung im Repository der Organisation können die Benutzer in der Organisation diese benutzerdefinierten Visuals für Organisationen einfach ermitteln und direkt über Power BI Desktop in ihre Berichte importieren.

## <a name="using-organizational-custom-visuals"></a>Verwenden von benutzerdefinierten Visuals für Organisationen

Weitere Informationen zur Verwendung von benutzerdefinierten Visuals für Organisationen in den von Ihnen erstellten Berichten finden Sie im Artikel [Power BI-Verwaltungsportal](power-bi-custom-visuals.md).
 
## <a name="administering-organizational-custom-visuals"></a>Verwalten von benutzerdefinierten Visuals für Organisationen

Weitere Informationen zum Verwalten und Bereitstellen von benutzerdefinierten Visuals für Organisationen innerhalb Ihrer Organisation finden Sie im Artikel [Power BI-Verwaltungsportal](https://go.microsoft.com/fwlink/?linkid=866790).

> [!WARNING]
> Ein benutzerdefiniertes Visual kann Code mit Sicherheits- oder Datenschutzrisiken enthalten. Stellen Sie sicher, dass Sie dem Autor und der Quelle eines benutzerdefinierten Visuals vertrauen können, bevor Sie dieses für das Repository der Organisation bereitstellen. 
> 

## <a name="considerations-and-limitations"></a>Überlegungen und Einschränkungen
 
Da sich die benutzerdefinierten Visuals für Organisationen noch in der Vorschauversion befinden, gibt es einige Überlegungen und Einschränkungen, die Sie beachten müssen.
 
Administrator:

* Veraltete benutzerdefinierte Visuals (z.B. benutzerdefinierte Visuals, die nicht mit den neuen API-Versionen erstellt wurden) werden nicht unterstützt.

* Direkte Updates werden noch nicht unterstützt. Sie müssen eine neue Version des Visuals in das Repository der Organisation hochladen (stellen Sie sicher, dass die ID des Visuals in der PBIVIZ-Datei übereinstimmt), um ein Visual zu aktualisieren. Berichtsautoren können die neue Version dann in ihren Bericht importieren und eine direkte Ersetzung der aktuellen Version des Visuals im Bericht vornehmen.

* Wenn ein benutzerdefiniertes Visual aus dem Repository gelöscht wird, wird das Rendern aller vorhandenen Berichte beendet, die das gelöschte Visual verwenden. Das Löschen des Visuals aus dem Repository kann nicht rückgängig gemacht werden.
 
Benutzer:

* Das Verwenden des gleichen Visuals (d.h. von Visuals mit identischer ID) vom öffentlichen Marketplace (AppSource) und aus dem Repository der Organisation wird nicht unterstützt. In diesem Fall wird das Visual verwendet, das zuletzt importiert wurde.

* Die externe Freigabe von Visuals für Organisationen in Dashboards und Berichten wird nicht unterstützt. Wenn Benutzer außerhalb der Organisation ein Dashboard mit einem benutzerdefinierten Visual für Organisationen anzeigen, wird diesen ein leeres Visual angezeigt. 

* Die Power BI-Arbeitsbereichssammlung wird für Visuals für Organisationen nicht unterstützt.

* Benutzerdefinierte Visuals für Organisationen werden nicht gerendert, wenn sie sich in Berichten befinden, die im Web veröffentlicht werden.

* Visio-Visuals, PowerApps-Visuals und GlobeMap-Visuals aus dem AppSource-Marketplace werden nicht gerendert, wenn diese über das Repository der Organisation bereitgestellt wurden.

* Wenn der Administrator ein benutzerdefiniertes Visual aus dem Repository löscht und dieses in einem Bericht verwendet wird, wird das Rendern des Visuals beendet werden. Das Visual muss aus dem Bericht entfernt werden, damit dieser gespeichert werden kann.