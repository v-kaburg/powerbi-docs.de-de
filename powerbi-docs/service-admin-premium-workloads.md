---
title: Konfigurieren von Workloads in Power BI Premium
description: Hier erfahren Sie, wie Sie Workloads in einer Power BI Premium-Kapazität konfigurieren.
author: minewiskan
ms.author: owend
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 02/26/2019
LocalizationGroup: Premium
ms.openlocfilehash: 5b9bec67fef672d219b11bf3b3750959e72410b6
ms.sourcegitcommit: 364ffa1178cdfb0a20acffc0fd79922ebc892d72
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/02/2019
ms.locfileid: "57226064"
---
# <a name="configure-workloads-in-a-premium-capacity"></a>Konfigurieren von Workloads in einer Premium-Kapazität

In diesem Artikel erfahren Sie, wie Sie Workloads für Power BI Premium-Kapazitäten aktivieren und konfigurieren. Kapazitäten unterstützen standardmäßig nur die Workload für die Ausführung von Power BI-Abfragen. Abfrageworkloads sind für Ressourcen optimiert und durch Ressourcen beschränkt, die durch Ihre Premium-Kapazitäts-SKU bestimmt werden. Premium-Kapazitäten unterstützen auch zusätzliche Workloads, die Kapazitätsressourcen nutzen können.

## <a name="configure-workloads"></a>Konfigurieren von Workloads

Sie können zusätzliche Workloads für [Dataflows](service-dataflows-overview.md#dataflow-capabilities-on-power-bi-premium) und [paginierte Berichte](paginated-reports-save-to-power-bi-service.md) aktivieren und konfigurieren. Arbeitsspeicher-Standardwerte für diese Workloads basieren auf den Kapazitätsknoten, die für Ihre SKU zur Verfügung stehen. Die Einstellungen für maximalen Arbeitsspeicher sind nicht kumulativ. Für Dataflows wird Arbeitsspeicher dynamisch bis zum angegebenen Maximalwert zugeordnet. Für paginierte Berichte ist die Zuordnung dagegen statisch. 

### <a name="to-configure-workloads-in-the-power-bi-admin-portal"></a>So konfigurieren Sie Workloads im Power BI-Verwaltungsportal

1. Wählen Sie unter **Kapazitätseinstellungen** > **PREMIUM-KAPAZITÄTEN** eine Kapazität aus.

1. Erweitern Sie unter **Weitere Optionen** **Workloads**.

1. Aktivieren Sie mindestens eine Workload, und legen Sie einen Wert für **Maximaler Arbeitsspeicher** fest.   

    
    ![Aktivieren von Workloads](media/service-admin-premium-workloads/admin-portal-workloads.png)

1. Klicken Sie auf **Übernehmen**.

> [!NOTE]
> Wenn Sie die Workload für paginierte Berichte aktivieren, können Sie beim Rendern eines Berichts Ihren eigenen Code ausführen (beispielsweise dynamisches Ändern der Textfarbe basierend auf dem Inhalt). Power BI Premium führt paginierte Berichte in einem Bereich innerhalb der Kapazität aus. Der angegebene maximale Arbeitsspeicher wird unabhängig davon verwendet, ob die Workload aktiv ist. Wenn Sie Power BI-Berichte oder Dataflows in der gleichen Kapazität verwenden, legen Sie den Arbeitsspeicher für paginierte Berichte so niedrig fest, dass er die anderen Workloads nicht beeinträchtigt. In seltenen Fällen kann es vorkommen, dass die Workload von paginierten Berichten nicht verfügbar ist. In diesem Fall zeigt die Workload einen Fehlerstatus im Verwaltungsportal an, und den Benutzern werden Timeouts für das Rendern von Berichten angezeigt. Um dieses Problem zu beheben, deaktivieren Sie die Workload, und aktivieren Sie sie dann erneut.


### <a name="rest-api"></a>REST-API

Workloads können mithilfe der REST-APIs vom Typ [Capacities](https://docs.microsoft.com/rest/api/power-bi/capacities) aktiviert und einer Kapazität zugewiesen werden.


## <a name="next-steps"></a>Nächste Schritte

[Verwaltung und Optimierung der Microsoft Power BI Premium-Kapazitätsressource](service-premium-understand-how-it-works.md)   
[Self-Service-Datenaufbereitung in Power BI (Vorschau)](service-dataflows-overview.md)   
[Was sind paginierte Berichte in Power BI Premium? (Vorschau)](paginated-reports-report-builder-power-bi.md)   

Weitere Fragen? [Fragen an die Power BI-Community](http://community.powerbi.com/)