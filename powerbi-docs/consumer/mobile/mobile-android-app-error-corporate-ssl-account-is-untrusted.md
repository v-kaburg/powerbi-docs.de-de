---
title: 'Fehlerbehebung: „Das SSL-Zertifikat Ihres Unternehmens ist nicht vertrauenswürdig.“'
description: 'Bei der Anmeldung bei der Power BI-App für Android wird folgende Meldung angezeigt: „Die Authentifizierung konnte nicht durchgeführt werden, weil das SSL-Zertifikat Ihres Unternehmens von diesem Gerät als nicht vertrauenswürdig eingestuft wird.“'
.": ''
author: mshenhav
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-mobile
ms.topic: conceptual
ms.date: 05/18/2018
ms.author: mshenhav
ms.openlocfilehash: de103412e21e0d26d20058e2d4e1fb9a8a5449bf
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2019
ms.locfileid: "61341349"
---
# <a name="fixing-corporate-ssl-certificate-is-untrusted---power-bi"></a>Fehlerbehebung: „Das SSL-Zertifikat Ihres Unternehmens wird als nicht vertrauenswürdig eingestuft“ – Power BI
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
Wenn Sie einen benutzerdefinierten Authentifizierungsserver verwenden, ist das SSL-Zertifikat im Authentifizierungsserver des Unternehmens möglicherweise ungültig. Arbeiten Sie mit der IT-Abteilung Ihrer Organisation zusammen, um die Konfiguration des Authentifizierungsservers des Unternehmens gemäß der Anleitung in [diesem Artikel](https://support.microsoft.com/en-us/help/3203929/using-adal-to-authenticate-from-android-devices-fails-if-additional-ce) zu testen.

## <a name="next-steps"></a>Nächste Schritte
* [Herunterladen der Android-App](http://go.microsoft.com/fwlink/?LinkID=544867) aus dem Android App Store.
* Haben Sie Fragen? [Stellen Sie Ihre Frage in der Power BI-Community.](http://community.powerbi.com/) 

