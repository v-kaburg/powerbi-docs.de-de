---
title: Grundlegendes zur Sicherheit auf Zeilenebene (Row-Level Security; RLS) mit Power BI Desktop
description: Erfahren Sie, wie Sie die Sicherheit auf Zeilenebene für importierte Datasets und DirectQuery in Power BI Desktop konfigurieren.
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 05/03/2018
ms.author: maghan
LocalizationGroup: Create reports
ms.openlocfilehash: 022668737f6bcce987b2923ba7a4416f4a08460a
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2018
ms.locfileid: "34287070"
---
# <a name="row-level-security-rls-with-power-bi-desktop"></a>Sicherheit auf Zeilenebene (row-level security; RLS) mit Power BI Desktop
Die Sicherheit auf Zeilenebene (row-level security; RLS) mit Power BI Desktop führt zu Einschränkungen des Datenzugriffs für bestimmte Benutzer. Filter beschränken die Daten auf Zeilenebene. Sie können Filter für Rollen definieren.

Sie können RLS jetzt für Datenmodelle konfigurieren, die mithilfe von Power BI Desktop in Power BI importiert wurden. Sie können auch RLS für Datasets konfigurieren, die DirectQuery verwenden, z. B. SQL Server. Bisher konnte RLS nur in lokalen Analysis Services-Modellen außerhalb von Power BI implementiert werden. Für Liveverbindungen von Analysis Services konfigurieren Sie RLS auf dem lokalen Modell. Die Sicherheitsoption wird nicht für Liveverbindungsdatasets angezeigt.

> [!IMPORTANT]
> Wenn Sie im Power BI-Dienst Rollen und Regeln definiert haben, müssen Sie diese Rollen in Power BI Desktop neu erstellen und den Bericht im Dienst veröffentlichen.
> 
> 

Erfahren Sie mehr über die Optionen für [RLS innerhalb des Power BI-Diensts](service-admin-rls.md).

[!INCLUDE [include-short-name](./includes/rls-desktop-define-roles.md)]

[!INCLUDE [include-short-name](./includes/rls-desktop-view-as-roles.md)]

[!INCLUDE [include-short-name](./includes/rls-limitations.md)]

[!INCLUDE [include-short-name](./includes/rls-faq.md)]

## <a name="next-steps"></a>Nächste Schritte
[Sicherheit auf Zeilenebene (row-level security; RLS) mit Power BI](service-admin-rls.md)  

Weitere Fragen? [Stellen Sie Ihre Frage in der Power BI-Community.](http://community.powerbi.com/)

