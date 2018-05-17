---
title: Lokales Datengateway
description: Dieser Artikel bietet einen Überblick über On-premises data gateway für Power BI. Mithilfe dieses Gateways können Sie mit DirectQuery-Datenquellen arbeiten. Sie können damit außerdem die Clouddatasets mit lokalen Daten aktualisieren.
services: powerbi
documentationcenter: ''
author: mgblythe
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: powerbi
ms.date: 03/26/2018
ms.author: mblythe
LocalizationGroup: Gateways
ms.openlocfilehash: e993a7ced826879e87b6f1d101f50e264fdc6854
ms.sourcegitcommit: 493f160d04ed411ff4741c599adc63ba1f65230f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="on-premises-data-gateway"></a>Lokales Datengateway

Das lokale Datengateway fungiert als Brücke, da es eine schnelle und sichere Datenübertragung zwischen lokalen Daten (Daten außerhalb der Cloud) und den Power BI-, Microsoft Flow-, Logic Apps- und PowerApps-Diensten bereitstellt.

Sie können ein einziges Gateway gleichzeitig für verschiedene Dienste verwenden. Wenn Sie sowohl Power BI als auch PowerApps verwenden, können Sie dasselbe Gateway für beide verwenden. Das ist von dem Konto abhängig, mit dem Sie sich anmelden.

> [!NOTE]
> Das lokale Datengateway implementiert Datenkomprimierung sowie Transportverschlüsselung in allen Modi.
> 
> 

<!-- Shared Requirements Include -->
[!INCLUDE [gateway-onprem-requirements-include](./includes/gateway-onprem-requirements-include.md)]

### <a name="limitations-of-analysis-services-live-connections"></a>Einschränkungen der Liveverbindungen von Analysis Services
Sie können eine Liveverbindung für tabellarische oder mehrdimensionale Instanzen verwenden.

| **Serverversion** | **Erforderliche SKU** |
| --- | --- |
| 2012 SP1 CU4 oder höher |Business Intelligence und Enterprise SKU |
| 2014 |Business Intelligence und Enterprise SKU |
| 2016 |Standard-SKU oder höher |

* Die Formatierung auf Zellenebene sowie Übersetzungsfunktionen werden nicht unterstützt.
* Aktionen und benannte Mengen werden nicht für Power BI verfügbar gemacht. Dennoch können Sie eine Verbindung mit mehrdimensionalen Cubes herstellen, die auch Aktionen oder benannte Mengen enthalten, und Sie können entsprechende Visualisierungen und Berichte erstellen.

<!-- Shared Install steps Include -->
[!INCLUDE [gateway-onprem-datasources-include](./includes/gateway-onprem-datasources-include.md)]

## <a name="download-and-install-the-on-premises-data-gateway"></a>Herunterladen und Installieren von On-premises Data Gateway
Klicken Sie im Menü „Downloads“ auf **Datengateway**, um das Gateway herunterzuladen. Laden Sie [On-premises data gateway](http://go.microsoft.com/fwlink/?LinkID=820925) herunter.

![](media/service-gateway-onprem/powerbi-download-data-gateway.png)

<!-- Shared Install steps Include -->
[!INCLUDE [gateway-onprem-install-include](./includes/gateway-onprem-install-include.md)]

## <a name="install-the-gateway-in-personal-mode"></a>Installieren Sie das Gateway im Modus „Persönliches Gateway“.
> [!NOTE]
> Der persönliche Modus funktioniert nur mit Power BI.
> 
> 

Nach der Installation des persönlichen Gateways müssen Sie den **Konfigurations-Assistenten für Power BI Gateway – Personal** starten.

![](media/service-gateway-onprem/personal-gateway-launch-configuration.png)

Sie müssen sich anschließend bei Power BI anmelden, um das Gateway bei dem Clouddienst zu registrieren.

![](media/service-gateway-onprem/personal-gateway-signin.png)

Sie müssen auch den Windows-Benutzernamen und das Windows-Kennwort angeben, die der Windows-Dienst verwenden wird. Sie können ein anderes Windows-Konto als Ihr eigenes angeben. Der Gatewaydienst wird mithilfe dieses Kontos ausgeführt.

![](media/service-gateway-onprem/personal-gateway-windows-service.png)

Nachdem die Installation abgeschlossen ist, müssen Sie Ihre Datasets in Power BI aufrufen und unbedingt die Anmeldeinformationen für Ihre lokalen Datenquellen eingeben.

<a name="credentials"></a>

## <a name="storing-encrypted-credentials-in-the-cloud"></a>Speichern von verschlüsselten Anmeldeinformationen in der Cloud
Beim Hinzufügen einer Datenquelle für das Gateway müssen Sie für diese Datenquelle Anmeldeinformationen angeben. Alle Abfragen der Datenquelle werden mithilfe dieser Anmeldeinformationen durchgeführt. Die Anmeldeinformationen werden mithilfe einer asymmetrischen Verschlüsselung vor der Speicherung in der Cloud sicher verschlüsselt, sodass sie in der Cloud nicht entschlüsselt werden können. Die Anmeldeinformationen werden an den lokalen Computer gesendet, der das Gateway ausführt, und auf diesem beim Zugriff auf die Daten entschlüsselt.

<!-- Account and Port information -->
[!INCLUDE [gateway-onprem-accounts-ports-more](./includes/gateway-onprem-accounts-ports-more.md)]

<!-- How the gateway works -->
[!INCLUDE [gateway-onprem-how-it-works-include](./includes/gateway-onprem-how-it-works-include.md)]

## <a name="limitations-and-considerations"></a>Einschränkungen und Überlegungen
* [Azure Information Protection](https://docs.microsoft.com/en-us/microsoft-365/enterprise/protect-files-with-aip
) wird derzeit nicht unterstützt.
* [Access Online](https://products.office.com/en-us/access) wird derzeit nicht unterstützt.

## <a name="tenant-level-administration"></a>Verwaltung auf Mandantenebene 

Derzeit können Mandantenadministratoren die Gateways, die andere Benutzer installiert und konfiguriert haben, nicht über einen zentralen Ort verwalten.  Mandantenadministratoren wird empfohlen, die Benutzer der Organisation darum zu bitten, sie zu jedem installierten Gateway als Administrator hinzuzufügen. Dadurch können alle Gateways der Organisation über die Seite „Gatewayeinstellungen“ oder über [PowerShell-Befehle](https://docs.microsoft.com/power-bi/service-gateway-high-availability-clusters#powershell-support-for-gateway-clusters) verwaltet werden. 


## <a name="troubleshooting"></a>Problembehandlung
Sollten beim Installieren und Konfigurieren eines Gateways Probleme auftreten, lesen Sie [Problembehandlung beim lokalen Datengateway](service-gateway-onprem-tshoot.md). Wenn Sie glauben, dass ein Problem bei Ihrer Firewall aufgetreten ist, lesen Sie den Abschnitt [Firewall or Proxy](service-gateway-onprem-tshoot.md#firewall-or-proxy) (Firewall oder Proxy) im Artikel zur Problembehandlung.

Wenn Sie der Meinung sind, dass Proxyprobleme mit dem Gateway vorliegen, finden Sie weitere Informationen unter [Konfigurieren von Proxyeinstellungen für Power BI-Gateways](service-gateway-proxy.md).

## <a name="next-steps"></a>Nächste Schritte
[Verwalten Ihrer Datenquelle – Analysis Services](service-gateway-enterprise-manage-ssas.md)  
[Verwalten Ihrer Datenquelle –SAP HANA](service-gateway-enterprise-manage-sap.md)  
[Verwalten Ihrer Datenquelle – SQL Server](service-gateway-enterprise-manage-sql.md)  
[Verwalten der Datenquelle – Oracle](service-gateway-onprem-manage-oracle.md)  
[Verwalten der Datenquelle – Import/Geplante Aktualisierung](service-gateway-enterprise-manage-scheduled-refresh.md)  
[Ausführliche Informationen zum lokalen Datengateway](service-gateway-onprem-indepth.md)  
[Lokales Datengateway (persönlicher Modus) – die neue Version des persönlichen Gateways](service-gateway-personal-mode.md)
[Konfigurieren von Proxyeinstellungen für das lokale Datengateway](service-gateway-proxy.md)  
Weitere Fragen? [Wenden Sie sich an die Power BI-Community](http://community.powerbi.com/)

