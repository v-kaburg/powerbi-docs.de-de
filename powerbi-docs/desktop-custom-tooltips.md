---
title: Anpassen von QuickInfos in Power BI Desktop
description: Erstellen Sie benutzerdefinierte QuickInfos für Visualisierungen mithilfe von Drag & Drop.
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/07/2019
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: d5259ba22287a8a2ade3107e4320c39713dcb45e
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2019
ms.locfileid: "65239746"
---
# <a name="customizing-tooltips-in-power-bi-desktop"></a>Anpassen von QuickInfos in Power BI Desktop
QuickInfos sind eine elegante Methode zum Bereitstellen von kontextbezogenen Informationen und Details zu Datenpunkten in einer Visualisierung. Die folgende Abbildung zeigt eine QuickInfo zu einem Diagramm in Power BI Desktop.

![Standard-QuickInfo](media/desktop-custom-tooltips/custom-tooltips-1.png)

Wenn eine Visualisierung erstellt wird, werden in der Standard-QuickInfo der Wert und die Kategorie Datenpunkts angezeigt. Es gibt viele Instanzen beim Anpassen der QuickInfo-Informationen nützlich ist, und kann zusätzlichen Kontext und Informationen für Benutzer, die die Visualisierung anzeigen bereitstellen. Mit QuickInfos können Sie zusätzliche Datenpunkte angeben, die als Teil der QuickInfo angezeigt werden.

## <a name="how-to-customize-tooltips"></a>Anpassen von QuickInfos
Zum Erstellen einer benutzerdefinierten QuickInfo in der **Felder** und die **Visualisierungen** Bereich ziehen ein Feld in der **QuickInfos** Bucket in der folgenden Abbildung dargestellt. In der folgenden Abbildung wurden zwei Felder im Bucket **QuickInfos** eingefügt.

![Hinzufügen von QuickInfo-Feldern](media/desktop-custom-tooltips/custom-tooltips-2.png)

Wenn QuickInfos zum Feldbereich hinzugefügt wurden und der Benutzer den Mauszeiger auf einen Datenpunkt in der Visualisierung hält, werden die Werte für diese Felder in der QuickInfo angezeigt.

![Benutzerdefinierte QuickInfo](media/desktop-custom-tooltips/custom-tooltips-3.png)

## <a name="customizing-tooltips-with-aggregation-or-quick-calcs"></a>Anpassen von QuickInfos mit Aggregation oder Schnellberechnungen
Sie können eine QuickInfo weiter anpassen, indem Sie eine Aggregationsfunktion oder eine *Schnellberechnung* auswählen. Klicken Sie hierfür auf den Pfeil neben dem Feld im Bucket **QuickInfos**, und wählen Sie eine der verfügbaren Optionen aus.

![QuickInfo mit Schnellberechnung](media/desktop-custom-tooltips/custom-tooltips-4.png)

Es gibt viele Möglichkeiten zum Anpassen **QuickInfos**, mit beliebigen Feldern im Dataset, um schnell Informationen und Einblicke für die Benutzer anzeigen, Ihre Dashboards oder Berichte zu übermitteln.

