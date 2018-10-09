---
title: Verwenden von benutzerdefinierten Datenconnectors mit dem lokalen Datengateway
description: Sie können benutzerdefinierte Datenconnectors mit dem lokalen Datengateway verwenden.
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-gateways
ms.topic: conceptual
ms.date: 08/08/2018
LocalizationGroup: Gateways
ms.openlocfilehash: 2536ea34cadae5f348e619d713420787db4c467a
ms.sourcegitcommit: f6360934b9af20bd630e2d3cb88398e3f5794090
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "48799044"
---
# <a name="use-custom-data-connectors-with-the-on-premises-data-gateway"></a>Verwenden von benutzerdefinierten Datenconnectors mit dem lokalen Datengateway

Mithilfe der Datenconnectors für Power BI können Sie eine Verbindung zu Daten einer App, eines Diensts oder einer Datenquelle herstellen und auf diese zugreifen. Sie können benutzerdefinierte Datenconnectors entwickeln und diese in Power BI Desktop verwenden.

Weitere Informationen zum Entwickeln benutzerdefinierter Datenconnectors für Power BI finden Sie [in unserer Dokumentation](http://aka.ms/dataconnectors).

Wenn Sie Berichte in Power BI Desktop erstellen, die benutzerdefinierte Datenconnectors nutzen, können Sie das lokale Datengateway dazu verwenden, diese Berichte aus dem Power BI-Dienst zu aktualisieren.

## <a name="here-is-a-guide-on-how-to-enable-and-use-this-capability"></a>Anleitung zum Aktivieren und Verwenden dieser Funktion

Wenn Sie die Version vom Juli 2018 oder eine höhere Version des lokalen Datengateways installieren, wird im Konfigurator die Registerkarte „Connectors“ mit der Option, einen Ordner auszuwählen, aus dem benutzerdefinierte Connectors geladen werden sollen, angezeigt. Wählen Sie einen Ordner aus, auf den der Benutzer, der den Gatewaydienst (standardmäßig „NT SERVICE\PBIEgwService”) ausführt, zugreifen kann. Das Gateway lädt automatisch die benutzerdefinierten Connectordateien in diesem Ordner, die dann in der Liste der Datenconnectors angezeigt werden sollten.

![Benutzerdefinierter Connector 1](media/service-gateway-custom-connectors/gateway-onprem-customconnector1.png)

Wenn Sie die persönliche Version des lokalen Datengateways verwenden, sollten Sie an dieser Stelle Ihren Power BI-Bericht im Power BI-Dienst hochladen können und das Gateway zum Aktualisieren verwenden.

Für die Enterpriseversion des Gateways müssen Sie immer noch eine Datenquelle für Ihren benutzerdefinierten Connector erstellen. Auf der Seite „Gatewayeinstellungen“ im Power BI-Dienst sollte eine neue Option angezeigt werden, wenn Sie dem Gatewaycluster erlauben, benutzerdefinierte Connectors mit diesem Cluster zu verwenden. Vergewissern Sie sich, dass für alle Gateways im Cluster das Update vom Juli 2018 oder höher installiert ist, damit diese Option verfügbar ist. Wählen Sie nun diese Option aus, um das Verwenden von benutzerdefinierten Connectors mit diesem Cluster zu aktivieren.

![Benutzerdefinierter Connector 2](media/service-gateway-custom-connectors/gateway-onprem-customconnector2.png)

Wenn diese Option aktiviert ist, werden Ihre benutzerdefinierten Connectors als verfügbare Datenquellen angezeigt, die Sie in diesem Gatewaycluster erstellen können. Nach dem Erstellen einer Datenquelle mit Ihrem neuen benutzerdefinierten Connector können Sie die Power BI-Berichte aktualisieren, die diesen benutzerdefinierten Connector im Power BI-Dienst verwenden.

![Benutzerdefinierter Connector 3](media/service-gateway-custom-connectors/gateway-onprem-customconnector3.png)

## <a name="considerations-and-limitations"></a>Überlegungen und Einschränkungen

* Stellen Sie sicher, dass der erstellte Ordner für den Gatewaydienst im Hintergrund zugänglich ist. In der Regel ist der Zugriff auf Ordner unter Windows-Ordnern oder Systemordnern Ihres Benutzers nicht möglich. Der Gatewaykonfigurator zeigt eine Nachricht an, wenn der Ordner nicht zugänglich ist (gilt nicht für die persönliche Version des Gateways).
* Damit benutzerdefinierte Connectors mit dem lokalen Datengateway verwendet werden können, muss in deren Code ein „TestConnection“-Abschnitt implementiert werden. Dies ist nicht erforderlich, wenn benutzerdefinierte Connectors mit Power BI Desktop verwendet werden. Sie können einen benutzerdefinierten Connector nutzen, der zwar mit Power BI Desktop, aber nicht mit dem Gateway verwendet werden kann. Weitere Informationen zur Implementierung eines „TestConnection“-Abschnitts finden Sie in [dieser Dokumentation](https://github.com/Microsoft/DataConnectors/blob/master/docs/m-extensions.md#implementing-testconnection-for-gateway-support).

## <a name="next-steps"></a>Nächste Schritte

* [Verwalten Ihrer Datenquelle – Analysis Services](service-gateway-enterprise-manage-ssas.md)  
* [Verwalten Ihrer Datenquelle –SAP HANA](service-gateway-enterprise-manage-sap.md)  
* [Verwalten Ihrer Datenquelle – SQL Server](service-gateway-enterprise-manage-sql.md)  
* [Verwalten der Datenquelle – Oracle](service-gateway-onprem-manage-oracle.md)  
* [Verwalten der Datenquelle – Import/Geplante Aktualisierung](service-gateway-enterprise-manage-scheduled-refresh.md)  
* [Ausführliche Informationen zum lokalen Datengateway](service-gateway-onprem-indepth.md)  
* [Lokales Datengateway (persönlicher Modus)](service-gateway-personal-mode.md)
* [Konfigurieren von Proxyeinstellungen für das lokale Datengateway](service-gateway-proxy.md)  
* [Use Kerberos for SSO (single sign-on) from Power BI to On-premises data sources (Verwenden von Kerberos für SSO (Single Sign-On, Einmaliges Anmelden) bei Power BI für lokale Datenquellen)](service-gateway-kerberos-for-sso-pbi-to-on-premises-data.md)  

Weitere Fragen? [Wenden Sie sich an die Power BI-Community](http://community.powerbi.com/)
