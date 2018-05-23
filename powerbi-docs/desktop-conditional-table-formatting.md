---
title: Bedingte Tabellenformatierungen in Power BI Desktop
description: Wenden Sie benutzerdefinierte Formatierungen auf Tabellen an.
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 05/08/2018
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 9599b40940c9d9cca254bb2ed2e87c161cce371f
ms.sourcegitcommit: 638de55f996d177063561b36d95c8c71ea7af3ed
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/17/2018
---
# <a name="conditional-formatting-in-tables"></a>Bedingte Formatierung in Tabellen
Mithilfe der bedingten Formatierung für Tabellen können Sie benutzerdefinierte Zellhintergrundfarben basierend auf Zellwerten oder auf anderen Werten oder Feldern festlegen und Verlaufsfarben verwenden. Wählen Sie zum Zugriff auf die bedingte Formatierung im Bereich **Felder** des Bereichs **Visualisierungen** in Power BI Desktop den Dropdownpfeil neben dem Wert im Bereich **Werte** aus, den Sie formatieren möchten (oder klicken Sie mit der rechten Maustaste in das Feld). Sie können die bedingte Formatierung nur für Felder im Bereich **Werte** des Bereichs **Felder** verwalten.

![Bedingte Tabellenformatierung](media/desktop-conditional-table-formatting/table-formatting_1.png)

Im angezeigten Dialogfeld können Sie die Farbe sowie die Werte für *Minimum* und *Maximum* konfigurieren. Wenn Sie das Kontrollkästchen **Abweichend** aktivieren, können Sie auch einen optionalen Wert für *Zentriert* konfigurieren.

![Abweichende Farben](media/desktop-conditional-table-formatting/table-formatting_2.png)

Sie können den Farbverlauf auch auf einem Feld in Ihrem Datenmodell basieren lassen. Darüber hinaus können Sie den Aggregationstyp für das ausgewählte Feld angeben (das ausgewählte Feld wird im Feld **Farbe anwenden auf** angegeben, damit Sie den Überblick behalten können).

![Aus einem Feld basierende Grundfarben](media/desktop-conditional-table-formatting/table-formatting_2b.png)

Bei der Anwendung auf eine Tabelle überschreibt die mit den oben beschriebenen Schritten angewendete benutzerdefinierte Formatierung alle benutzerdefinierten Tabellenformatierungen, die auf die Zellen mit bedingter Formatierung angewendet wurden.

![Tabellenformatierung](media/desktop-conditional-table-formatting/table-formatting_3.png)

Sie können Text- und Datumsfelder auch bedingt formatieren, sofern Sie einen numerischen Wert als Grundlage für die Formatierung wählen. 

Wenn Sie eine bedingte Formatierung aus einer Visualisierung entfernen möchten, klicken Sie einfach mit der rechten Maustaste erneut auf das Feld, und wählen Sie **Bedingte Formatierung entfernen** aus.

![Tabellenformatierung entfernen](media/desktop-conditional-table-formatting/table-formatting_4.png)

