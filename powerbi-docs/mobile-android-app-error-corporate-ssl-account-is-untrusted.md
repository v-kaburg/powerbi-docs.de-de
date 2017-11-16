---
title: 'Fehler: '
corporate: 
ssl: 
certificate: 
is: 
untrusted": 
'-': 
power: 
bi": 
description: "Bei der Anmeldung bei der Power BI-App für Android wird folgende Meldung angezeigt: „Die Authentifizierung konnte nicht durchgeführt werden, weil das SSL-Zertifikat Ihres Unternehmens von diesem Gerät als nicht vertrauenswürdig eingestuft wird.“"
.": 
services: powerbi
documentationcenter: 
author: maggiesMSFT
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
ms.date: 10/13/2017
ms.author: maggies
ms.openlocfilehash: 4ef29c0cab96e21045f30805d7445aa34d37697a
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2017
---
# <a name="error-corporate-ssl-certificate-is-untrusted---power-bi"></a>Fehler: „Das SSL-Zertifikat Ihres Unternehmens wird als nicht vertrauenswürdig eingestuft“ – Power BI
Bei der Anmeldung bei der mobilen Android-App für Microsoft Power BI wird folgende Meldung angezeigt: „Die Authentifizierung konnte nicht durchgeführt werden, weil das SSL-Zertifikat Ihres Unternehmens von diesem Gerät als nicht vertrauenswürdig eingestuft wird. Wenden Sie sich an den IT-Administrator Ihres Unternehmens.“ 

Die weitere Vorgehensweise ist normalerweise abhängig vom Betriebssystem auf Ihrem Android-Gerät, es gibt jedoch eine Reihe von anderen Problemen, die diesen Fehler verursachen können.

## <a name="on-android-7-or-later"></a>Android 7 oder höher
Suchen Sie nach einem Update für eine App namens **Chrome**, und installieren Sie das Update.

## <a name="on-android-6-and-earlier"></a>Android 6 und früher
Für Ihr Gerät ist möglicherweise eine aktualisierte Version von System Webview erforderlich. Diese ist möglicherweise bereits auf Ihrem Gerät installiert, und Sie müssen nur auf **Aktualisieren** tippen.

Wenn System Webview nicht auf Ihrem Gerät installiert ist:

1. Schließen Sie Power BI auf Ihrem Android-Gerät.
2. Öffnen Sie Google Play Store, und suchen Sie nach **System WebView** von Google Inc.
3. Installieren Sie das Tool.
4. Starten Sie die Power BI-App neu, und melden Sie sich an.

## <a name="time-zone-settings"></a>Zeitzoneneinstellungen
Die Zeitzoneneinstellungen auf Ihrem Gerät sind möglicherweise falsch. 

Öffnen Sie **Einstellungen** > **System** > **Datum und Uhrzeit**, um die Einstellungen zu überprüfen.

## <a name="custom-authentication-server"></a>Benutzerdefinierter Authentifizierungsserver
Wenn Sie einen benutzerdefinierten Authentifizierungsserver verwenden, ist das SSL-Zertifikat im Authentifizierungsserver des Unternehmens möglicherweise ungültig. Wenden Sie sich an den IT-Administrator Ihrer Organisation, um weitere Hilfe zu erhalten.

## <a name="next-steps"></a>Nächste Schritte
* [Herunterladen der Android-App](http://go.microsoft.com/fwlink/?LinkID=544867) aus dem Android App Store.
* Haben Sie Fragen? [Stellen Sie Ihre Frage in der Power BI-Community.](http://community.powerbi.com/)

