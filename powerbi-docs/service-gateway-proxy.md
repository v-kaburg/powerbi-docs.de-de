---
title: Konfigurieren von Proxyeinstellungen für das lokale Datengateway
description: Informationen zur Konfiguration von Proxyeinstellungen für das lokale Datengateway
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-gateways
ms.topic: conceptual
ms.date: 11/21/2017
ms.author: mblythe
LocalizationGroup: Gateways
ms.openlocfilehash: ab5afb36458d7e1b5271a356bb1532ba77de6408
ms.sourcegitcommit: 638de55f996d177063561b36d95c8c71ea7af3ed
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/17/2018
---
# <a name="configuring-proxy-settings-for-the-on-premises-data-gateway"></a>Konfigurieren von Proxyeinstellungen für das lokale Datengateway
Aufgrund Ihres Arbeitsumfelds ist es möglicherweise erforderlich, eine Internetverbindung über einen Proxy herzustellen. Dies kann eine Verbindung des lokalen Datengateways mit dem Dienst verhindern.

## <a name="does-your-network-use-a-proxy"></a>Verwenden Ihr Netzwerk einen Proxy?
Im folgende Beitrag auf superuser.com wird erläutert, wie Sie feststellen können, ob sich in Ihrem Netzwerk ein Proxy befindet.

[Wie weiß ich, welchen Proxyserver ich verwende? (SuperUser.com)](https://superuser.com/questions/346372/how-do-i-know-what-proxy-server-im-using)

## <a name="configuration-file-location-and-default-configuration"></a>Speicherort der Konfigurationsdatei und Standardkonfiguration
Proxy-Informationen werden in einer NET-Konfigurationsdatei konfiguriert. Der Pfad und der Dateiname sind je nach verwendetem Gateway unterschiedlich.

### <a name="on-premises-data-gateway"></a>Lokales Datengateway
Es gibt zwei Hauptkonfigurationsdateien für das lokale Datengateway.

**Konfiguration**

Die erste Datei bezieht sich auf die Konfigurationsbildschirme, mit denen das Gateway tatsächlich konfiguriert wird. Wenn beim Konfigurieren des Gateways Probleme auftreten, prüfen Sie diese Datei.

    C:\Program Files\On-premises data gateway\enterprisegatewayconfigurator.exe.config

**Windows-Dienst**

Die zweite bezieht sich auf den tatsächlichen Windows-Dienst, der mit dem Power BI-Dienst interagiert und die Anfragen verarbeitet.

    C:\Program Files\On-premises data gateway\Microsoft.PowerBI.EnterpriseGateway.exe.config

## <a name="configuring-proxy-settings"></a>Konfigurierung von Proxyeinstellungen
Die standardmäßige Proxykonfiguration lautet wie folgt.

    <system.net>
        <defaultProxy useDefaultCredentials="true" />
    </system.net>

Die Standardkonfiguration unterstützt die Windows-Authentifizierung. Wenn der Proxy eine andere Form der Authentifizierung verwendet, müssen Sie die Einstellungen zu ändern. Wenn Sie nicht sicher sind, wenden Sie sich an den Netzwerkadministrator.

Weitere Informationen über die Konfiguration der Proxy-Elemente für NET-Konfigurationsdateien finden Sie unter [<defaultProxy>-Element (Netzwerkeinstellungen)](https://msdn.microsoft.com/library/kd3cf2ex.aspx).

## <a name="changing-the-gateway-service-account-to-a-domain-user"></a>Ändern des Gateway-Dienstkontos in einen Domänenbenutzer
Wenn Sie die Proxyeinstellungen wie oben erläutert für die Verwendung von Standardanmeldeinformationen konfigurieren, können beim Proxy Authentifizierungsprobleme auftreten. Der Grund dafür ist, dass das Standarddienstkonto die Dienst-SID und nicht ein authentifizierter Domänenbenutzer ist. Sie können das Dienstkonto des Gateways ändern, um die ordnungsgemäße Authentifizierung beim Proxy zu ermöglichen.

> [!NOTE]
> Es wird empfohlen, ein verwaltetes Dienstkonto zu verwenden, damit Kennwörter nicht zurückgesetzt werden müssen. Erfahren Sie, wie Sie ein [verwaltetes Dienstkonto](https://technet.microsoft.com/library/dd548356.aspx) in Active Directory erstellen.
> 
> 

### <a name="change-the-on-premises-data-gateway-service-account"></a>Ändern des Dienstkontos für das lokale Datengateway
1. Ändern Sie das Windows-Dienstkonto für den **Dienst Lokales Datengateway**.
   
    Das Standardkonto für diesen Dienst lautet *NT SERVICE\PBIEgwService*. Sie sollten dieses in ein Domänenbenutzerkonto in der Active Directory-Domäne ändern. Oder verwenden Sie ein verwaltetes Dienstkonto, um das Kennwort nicht ändern zu müssen.
   
    Ändern Sie das Konto in den Eigenschaften des Windows-Diensts auf der Registerkarte **Anmelden**.
2. Starten Sie den **Dienst Lokales Datengateway** neu.
   
    Geben Sie an der Administratoreingabeaufforderung die folgenden Befehle aus.
   
        net stop PBIEgwService
   
        net start PBIEgwService
3. Starten Sie die **Konfiguration des lokalen Datengateways**. Sie können auf die Windows-Schaltfläche „Start“ klicken und nach *Lokales Datengateway* suchen.
4. Melden Sie sich bei Power BI an.
5. Stellen Sie das Gateway mit dem Wiederherstellungsschlüssel wieder her.
   
    Dies ermöglicht dem neuen Dienstkonto das Entschlüsseln von gespeicherten Anmeldeinformationen für Datenquellen.

## <a name="next-steps"></a>Nächste Schritte
[Lokales Datengateway (persönlicher Modus)](service-gateway-personal-mode.md)
[Firewallinformationen](service-gateway-onprem-tshoot.md#firewall-or-proxy)  
Weitere Fragen? [Wenden Sie sich an die Power BI-Community](http://community.powerbi.com/)

