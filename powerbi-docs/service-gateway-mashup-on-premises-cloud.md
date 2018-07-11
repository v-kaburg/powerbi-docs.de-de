---
title: Zusammenführen oder Anfügen von lokalen und Clouddatenquellen
description: Verwenden Sie das lokale Datengateway, um lokale und Clouddatenquellen in derselben Abfrage zusammenzuführen oder daran anzufügen.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-gateways
ms.topic: conceptual
ms.date: 06/06/2018
ms.author: mblythe
LocalizationGroup: Gateways
ms.openlocfilehash: 2547be7f7bdadb7f991db54230d4fd791941838d
ms.sourcegitcommit: 127df71c357127cca1b3caf5684489b19ff61493
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2018
ms.locfileid: "37600065"
---
# <a name="merge-or-append-on-premises-and-cloud-data-sources"></a>Zusammenführen oder Anfügen von lokalen und Clouddatenquellen

Mit dem lokalen Datengateway können Sie lokale und Clouddatenquellen in derselben Abfrage zusammenführen oder daran anfügen. Dies ist hilfreich, wenn Sie Daten aus mehreren Quellen in derselben Abfrage kombinieren möchten.

## <a name="prerequisites"></a>Voraussetzungen

- Ein [auf einem lokalen Computer installiertes Gateway](service-gateway-install.md)
- Eine Power BI Desktop-Datei mit Abfragen, die lokale und Clouddatenquellen enthält.

1. Klicken Sie in der oberen rechten Ecke des Power BI-Diensts auf das Zahnradsymbol ![Zahnradsymbol für Einstellungen](media/service-gateway-mashup-on-premises-cloud/icon-gear.png) und dann auf **Gateways verwalten**.

    ![Gateways verwalten](media/service-gateway-mashup-on-premises-cloud/manage-gateways.png)

2. Wählen Sie das Gateway aus, das Sie konfigurieren möchten.

3. Klicken Sie unter **Gatewayclustereinstellungen** auf die Optionen **Ermöglichen Sie die Aktualisierung der Clouddatenquellen des Benutzers über diesen Gatewaycluster** > **Übernehmen**.

    ![Über dieses Gatewaycluster aktualisieren](media/service-gateway-mashup-on-premises-cloud/refresh-gateway-cluster.png)

4. Fügen Sie unter diesem Gatewaycluster alle [lokalen Datenquellen](service-gateway-enterprise-manage-scheduled-refresh.md#add-a-data-source) hinzu, die in Ihren Abfragen verwendet werden. Die Clouddatenquellen müssen hier nicht hinzugefügt werden.

5. Laden Sie die Power BI Desktop-Datei mit den Abfragen, die lokale und Clouddatenquellen enthalten, zu Power BI hoch.

6. Gehen Sie auf der Seite **Dataseteinstellungen** für das neue Dataset folgendermaßen vor:

   - Wählen Sie für die lokale Quelle das Gateway aus, das dieser Datenquelle zugeordnet ist.

   - Bearbeiten Sie unter **Datenquellen-Anmeldeinformationen** die Clouddatenquellen-Anmeldeinformationen nach Bedarf.

     ![Dataseteinstellungen](media/service-gateway-mashup-on-premises-cloud/dataset-settings.png)

7. Wenn Sie die Cloudanmeldeinformationen festgelegt haben, können Sie das Dataset mithilfe der Option **Jetzt aktualisieren** aktualisieren oder eine Aktualisierung in regelmäßigen Abständen planen.


## <a name="next-steps"></a>Nächste Schritte

Weitere Informationen zu Datenaktualisierung für Gateways finden Sie unter [Verwenden der Datenquelle für geplanten Aktualisierungen](service-gateway-enterprise-manage-scheduled-refresh.md#using-the-data-source-for-scheduled-refresh).