---
title: Beheben von Problemen beim Starten von Power BI Desktop
description: Beheben von Problemen beim Starten von Power BI Desktop
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
ms.date: 10/05/2017
ms.author: davidi
ms.openlocfilehash: 80593c13adb54950efbf5ff6e12a962b557fe7a0
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2017
---
# <a name="resolve-issues-when-power-bi-desktop-will-not-launch"></a>Beheben von Problemen beim Starten von Power BI Desktop
In **Power BI Desktop** können Benutzer, die frühere Versionen des **lokalen Datengateways von Power BI** installiert haben und ausführen, am Starten von Power BI Desktop gehindert werden. Grund sind Einschränkungen durch eine administrative Richtlinie, die das lokale Datengateway von Power BI auf Named Pipes auf dem lokalen Computer angewendet hat. 

## <a name="resolve-issues-with-the-on-premises-data-gateway-and-power-bi-desktop"></a>Beheben von Problemen beim lokalen Datengateway und **Power BI Desktop**
Es gibt drei Möglichkeiten, das Problem beim lokalen Datengateway zu beheben, damit Power BI Desktop gestartet werden kann:

### <a name="resolution-1-install-the-latest-version-of-power-bi-on-premises-data-gateway"></a>Lösung 1: Installieren der neuesten Version des lokalen Datengateways von Power BI
Die neueste Version des lokalen Datengateways von Power BI wendet keine Named Pipe-Einschränkungen auf den lokalen Computer an, sodass Power BI Desktop ordnungsgemäß starten kann. Wenn Sie das lokale Datengateway von Power BI weiter verwenden müssen, ist dies die empfohlene Lösung. Sie können die neueste Version des lokalen Datengateways von Power BI [hier](https://go.microsoft.com/fwlink/?LinkId=698863) herunterladen. Beachten Sie, dass der Link ein direkter Downloadlink zur ausführbaren Installationsdatei ist.

### <a name="resolution-2-uninstall-or-stop-the-power-bi-on-premises-data-gateway-windows-service"></a>Lösung 2: Deinstallieren oder Beenden des Windows-Diensts Lokales Datengateway von Power BI
Wenn Sie das lokale Datengateway von Power BI nicht mehr benötigen, können Sie es deinstallieren. Oder Sie können den Windows-Dienst Lokales Datengateway von Power BI beenden, wodurch die Einschränkung der Zugriffsrichtlinie aufgehoben wird, sodass Power BI Desktop gestartet werden kann.

### <a name="resolution-3-run-power-bi-desktop-with-administrator-privilege"></a>Lösung 3: Ausführen von Power BI Desktop mit Administratorrechten
Alternativ können Sie Power BI Desktop als Administrator erfolgreich starten, wodurch auch Power BI Desktop erfolgreich gestartet werden kann. Es gilt jedoch weiter die Empfehlung, die neueste Version des lokalen Datengateways von Power BI zu installieren (wie zuvor in diesem Artikel beschrieben).

## <a name="help-with-other-issues-when-launching-power-bi-desktop"></a>Hilfe bei anderen Problemen, die beim Starten von **Power BI Desktop** auftreten
Wir sind bemüht, im Zusammenhang mit **Power BI Desktop** auftretende Probleme möglichst umfassend darzustellen. Wir erweitern unsere Artikel regelmäßig um Lösungen für Probleme, die viele Kunden betreffen.

Wenn das Problem beim Starten von **Power BI Desktop** nicht mit dem lokalen Datengateway zusammenhängt oder wenn die oben genannten Lösungsvorschläge das Problem nicht beheben, können Sie einen Supportfall an den [Power BI-Support](https://support.powerbi.com) (https://support.powerbi.com) senden, um das Identifizieren und Beheben des Problems zu unterstützen.

Bei anderen Problemen, die zukünftig möglicherweise bei **Power BI Desktop** auftreten (wir hoffen, dass keine oder nur sehr wenige Probleme auftreten), empfiehlt es sich, die Ablaufverfolgung zu aktivieren und Protokolldateien zu sammeln, damit das Problem besser eingegrenzt und identifiziert werden kann. Wählen Sie zum Aktivieren der Ablaufverfolgung **Datei > Optionen und Einstellungen > Optionen** und dann **Diagnose** aus, und aktivieren Sie dann unter *Diagnoseoptionen* die Option **Ablaufverfolgung aktivieren**. Uns ist bewusst, dass zum Festlegen dieser Option **Power BI Desktop** ausgeführt werden muss. Deshalb ist diese Empfehlung insbesondere für die Behebung zukünftiger Probleme beim Starten von **Power BI Desktop** relevant.

