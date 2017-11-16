---
title: Anpassen von QuickInfos in Power BI Desktop
description: "Erstellen Sie benutzerdefinierte QuickInfos für Visualisierungen mithilfe von Drag & Drop."
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
ms.date: 09/06/2017
ms.author: davidi
ms.openlocfilehash: a54cc745cb341188efb511d66a71b185a7967212
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2017
---
# <a name="customizing-tooltips-in-power-bi-desktop"></a>Anpassen von QuickInfos in Power BI Desktop
QuickInfos sind eine elegante Methode zum Bereitstellen von kontextbezogenen Informationen und Details zu Datenpunkten in einer Visualisierung. Die folgende Abbildung zeigt eine QuickInfo zu einem Diagramm in Power BI Desktop.

![](media/desktop-custom-tooltips/custom-tooltips_1.png)

Wenn eine Visualisierung erstellt wird, werden in der Standard-QuickInfo der Wert und die Kategorie Datenpunkts angezeigt. Es gibt viele Fälle, in denen es hilfreich ist, die QuickInfo-Informationen anzupassen und mehr Kontext und Informationen für die Benutzer bereitzustellen, die die Visualisierung anzeigen. Mit QuickInfos können Sie zusätzliche Datenpunkte angeben, die als Teil der QuickInfo angezeigt werden.

## <a name="how-to-customize-tooltips"></a>Anpassen von QuickInfos
Zum Erstellen einer benutzerdefinierten QuickInfo ziehen Sie einfach im Bereich **Felder** unter **Visualisierungen** ein Feld in den Bucket **QuickInfos**, wie in der folgenden Abbildung dargestellt. In der folgenden Abbildung wurden vier Felder im Bucket **QuickInfos** platziert.

![](media/desktop-custom-tooltips/custom-tooltips_2.png)

Wenn QuickInfos zum Feldbereich hinzugefügt wurden und der Benutzer den Mauszeiger auf einen Datenpunkt in der Visualisierung hält, werden die Werte für diese Felder in der QuickInfo angezeigt.

![](media/desktop-custom-tooltips/custom-tooltips_3.png)

## <a name="customizing-tooltips-with-aggregation-or-quick-calcs"></a>Anpassen von QuickInfos mit Aggregation oder Schnellberechnungen
Sie können eine QuickInfo weiter anpassen, indem Sie eine Aggregationsfunktion oder eine *Schnellberechnung* auswählen. Klicken Sie hierfür auf den Pfeil neben dem Feld im Bucket **QuickInfos**, und wählen Sie eine der verfügbaren Optionen aus.

![](media/desktop-custom-tooltips/custom-tooltips_4.png)

Es gibt viele Methoden zum Anpassen von **QuickInfos** mit beliebigen Feldern im Dataset, um schnell Informationen und Einblicke für die Benutzer zu übermitteln, die Ihre Dashboards oder Berichte anzeigen.

