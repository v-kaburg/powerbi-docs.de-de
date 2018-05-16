---
title: Beheben von Problemen beim Starten von Power BI Desktop
description: Beheben von Problemen beim Starten von Power BI Desktop
services: powerbi
documentationcenter: ''
author: davidiseminger
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 04/24/2018
ms.author: davidi
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 2014524b3209a67bd0f0aaa3d1ddf00042227c4d
ms.sourcegitcommit: 3f2f254f6e8d18137bae879ddea0784e56b66895
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="resolve-issues-when-power-bi-desktop-will-not-launch"></a>Beheben von Problemen beim Starten von Power BI Desktop
In **Power BI Desktop** können Benutzer, die frühere Versionen des **lokalen Datengateways von Power BI** installiert haben und ausführen, am Starten von Power BI Desktop gehindert werden. Grund dafür sind Einschränkungen durch eine administrative Richtlinie, die das lokale Datengateway von Power BI auf Named Pipes auf dem lokalen Computer angewendet hat. 

## <a name="resolve-issues-with-the-on-premises-data-gateway-and-power-bi-desktop"></a>Beheben von Problemen mit dem lokalen Datengateway und Power BI Desktop
Es gibt drei Möglichkeiten, das Problem mit dem lokalen Datengateway zu beheben, damit Power BI Desktop gestartet werden kann:

### <a name="resolution-1-install-the-latest-version-of-power-bi-on-premises-data-gateway"></a>Lösung 1: Installieren der neuesten Version des lokalen Datengateways von Power BI
Die neueste Version des lokalen Datengateways von Power BI wendet keine Named Pipe-Einschränkungen auf dem lokalen Computer an, sodass Power BI Desktop ordnungsgemäß starten kann. Wenn Sie das lokale Datengateway von Power BI weiter verwenden müssen, ist dies die empfohlene Lösung. Sie können die neueste Version des lokalen Datengateways von Power BI [hier](https://go.microsoft.com/fwlink/?LinkId=698863) herunterladen. Beachten Sie, dass der Link ein direkter Downloadlink zur ausführbaren Installationsdatei ist.

### <a name="resolution-2-uninstall-or-stop-the-power-bi-on-premises-data-gateway-windows-service"></a>Lösung 2: Deinstallieren oder Beenden des Windows-Diensts lokales Datengateway von Power BI
Wenn Sie das lokale Datengateway von Power BI nicht mehr benötigen, können Sie es deinstallieren. Stattdessen können Sie auch den Windows-Dienst lokales Datengateway von Power BI beenden, wodurch die Einschränkung der Zugriffsrichtlinie aufgehoben wird, sodass Power BI Desktop gestartet werden kann.

### <a name="resolution-3-run-power-bi-desktop-with-administrator-privilege"></a>Lösung 3: Ausführen von Power BI Desktop mit Administratorrechten
Alternativ können Sie Power BI Desktop als Administrator erfolgreich starten, wodurch auch Power BI Desktop erfolgreich gestartet werden kann. Es gilt jedoch weiter die Empfehlung, die neueste Version des lokalen Datengateways von Power BI zu installieren (wie zuvor in diesem Artikel beschrieben).

Beachten Sie unbedingt, dass Power BI Desktop als Mehrprozessarchitektur entwickelt wurde und einige dieser Prozesse mittels Named Pipes von Windows kommunizieren. Möglicherweise gibt es andere Prozesse, bei denen Konflikte mit diesen Named Pipes auftreten können. Die häufigste Ursache für solche Konflikte sind Sicherheitsregeln, einschließlich Situationen, in denen Antivirussoftware oder Firewalls die Pipes blockieren oder den Datenverkehr zu einem bestimmten Port umleiten könnten. Das Starten von Power BI Desktop mit Administratorrechten könnte dieses Problem lösen. Wenn das Starten mit Administratorrechten nicht möglich ist, wenden Sie sich an Ihren Administrator, um zu ermitteln, welche Sicherheitsregeln angewendet werden, die die ordnungsgemäße Kommunikation der Named Pipes verhindern, und setzen Sie Power BI Desktop und die jeweiligen Unterprozesse auf die Whitelist.

## <a name="help-with-other-issues-when-launching-power-bi-desktop"></a>Hilfe bei anderen Problemen, die beim Starten von Power BI Desktop auftreten
Wir sind bemüht, im Zusammenhang mit **Power BI Desktop** auftretende Probleme möglichst umfassend darzustellen. Wir erweitern unsere Artikel regelmäßig um Lösungen für Probleme, die viele Kunden betreffen.

Wenn das Problem beim Starten von **Power BI Desktop** nicht mit dem lokalen Datengateway zusammenhängt oder wenn die oben genannten Lösungsvorschläge das Problem nicht beheben, können Sie einen Supportfall an den [Power BI-Support](https://support.powerbi.com) (https://support.powerbi.com) senden, um Unterstützung beim Identifizieren und Beheben des Problems zu erhalten.

Bei anderen Problemen, die zukünftig möglicherweise bei **Power BI Desktop** auftreten (wir hoffen, dass keine oder nur sehr wenige Probleme auftreten), empfiehlt es sich, die Ablaufverfolgung zu aktivieren und Protokolldateien zu sammeln, damit das Problem besser eingegrenzt und identifiziert werden kann. Wählen Sie zum Aktivieren der Ablaufverfolgung **Datei > Optionen und Einstellungen > Optionen** und dann **Diagnose** aus, und aktivieren Sie dann unter *Diagnoseoptionen* die Option **Ablaufverfolgung aktivieren**. Uns ist bewusst, dass zum Festlegen dieser Option **Power BI Desktop** ausgeführt werden muss. Deshalb ist diese Empfehlung insbesondere für die Behebung zukünftiger Probleme beim Starten von **Power BI Desktop** relevant.

