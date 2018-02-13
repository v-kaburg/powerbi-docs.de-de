---
title: "Überprüfen von benutzerdefinierten Visualisierungen auf Sicherheit und Datenschutz"
description: "Bevor Sie eine benutzerdefinierte Visualisierung aktivieren, sollten Sie sie auf Sicherheit und Datenschutz überprüfen, um sicherzustellen, dass sie die Standards Ihrer Organisation erfüllt."
services: powerbi
documentationcenter: 
author: markingmyname
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
ms.date: 09/05/2017
ms.author: maghan
ms.openlocfilehash: 15f8d9090736a62fdaa53aa3f19e7e0fff127337
ms.sourcegitcommit: 6e693f9caf98385a2c45890cd0fbf2403f0dbb8a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2018
---
# <a name="review-custom-visuals-for-security-and-privacy"></a>Überprüfen von benutzerdefinierten Visualisierungen auf Sicherheit und Datenschutz
Bevor Sie eine benutzerdefinierte Visualisierung aktivieren, sollten Sie sie auf Sicherheit und Datenschutz überprüfen, um sicherzustellen, dass sie die Standards Ihrer Organisation erfüllt.

## <a name="enable-a-custom-visual"></a>Aktivieren benutzerdefinierter Visualisierungen
<a name="enable"></a>Benutzerdefinierte Visualisierungen werden in einem Bericht so lange deaktiviert, bis Sie **Benutzerdefinierte Visualisierungen aktivieren** auswählen, wie nachstehend dargestellt.  

![](media/service-custom-visuals-review-for-security-and-privacy/emptyvisual.png)

## <a name="considerations-before-you-enable-a-custom-visual"></a>Überlegungen vor dem Aktivieren benutzerdefinierter Visualisierungen
<a name="considerations"></a>

> [!WARNING]
> Benutzerdefinierte Visualisierungen können Code mit Sicherheits- oder Datenschutzrisiken enthalten. Daher wird eine benutzerdefinierte Visualisierung in einem Bericht deaktiviert, bis Sie „Benutzerdefinierte Visualisierungen aktivieren“ auswählen. Im Folgenden finden Sie einige Aspekte, die Sie berücksichtigen sollten, bevor Sie entscheiden, ob Sie eine benutzerdefinierte Visualisierung aktivieren:
> 
> 

1. Überlegen Sie, ob Sie dem Autor und der Quelle der im Bericht verwendeten benutzerdefinierten Visualisierung vertrauen.
2. Wenn Sie nicht genau wissen, wie Sie vorgehen sollten, wenden Sie sich an Ihr IT-Team. Dieses kann dann entscheiden, ob Sie die benutzerdefinierten Visualisierungen für die von Ihnen angezeigten Berichte aktivieren sollten.
3. Wenn jemand einen Bericht für Sie freigegeben hat, der eine benutzerdefinierte Visualisierung enthält, sollten Sie sich selbst bei einem Kollegen nicht verpflichtet fühlen, die benutzerdefinierte Visualisierung aktivieren zu müssen. Es ist immer angemessen, zu überlegen, ob dies für die jeweilige Aufgabe unerlässlich ist. Es ist auch immer in Ordnung, um einen Bericht ohne benutzerdefinierte Visualisierungen zu bitten, wenn Sie sich bei einer benutzerdefinierten Visualisierung nicht sicher sind.

## <a name="security-best-practices-for-it-professionals-to-enable-a-custom-visual"></a>Bewährte Sicherheitsmethoden für IT-Experten beim Aktivieren benutzerdefinierter Visualisierungen
<a name="security"></a>

> [!WARNING]
> Benutzerdefinierte Visualisierungen können Code mit Sicherheits- oder Datenschutzrisiken enthalten. Daher wird eine benutzerdefinierte Visualisierung in einem Bericht deaktiviert, bis Sie „Benutzerdefinierte Visualisierungen aktivieren“ auswählen. Es gibt verschiedene bewährte Methoden, mit denen Sie eine benutzerdefinierte Visualisierung auf Sicherheit und Datenschutz überprüfen können.
> 
> 

1. Implementieren Sie innerhalb der Organisation einen Prozess für die Sicherheitsüberprüfung von benutzerdefinierten Visualisierungen. Überprüfte benutzerdefinierte Visualisierungen können über eine interne Website wie z. B. eine SharePoint-Dokumentbibliothek oder ein OneNote-Dokument für interne Benutzer freigegeben werden.
2. Bieten Sie Geschäftsbenutzern Unterstützung bei der angemessenen Verwendung von benutzerdefinierten Visualisierungen. Stellen Sie auch eine E-Mail-Gruppe für Geschäftsbenutzer bereit, in der diese Fragen zur Sicherheit und zum Datenschutz stellen können.
3. Überprüfen Sie den JavaScript-Code in der PBIVIZ-Datei der benutzerdefinierten Visualisierung.

**So überprüfen Sie den JavaScript-Code in einer benutzerdefinierten Visualisierung**

Benutzerdefinierte Visualisierungen verwenden JavaScript. Aus diesem Grund können Sie Sicherheits- oder Datenschutzrisiken enthalten. Wenn Sie eine benutzerdefinierte Visualisierung oder eine PBIX-Datei mit einer benutzerdefinierten Visualisierung aus einer unbekannten Quelle erhalten, sollten Sie die Sicherheit des JavaScript-Codes überprüfen.

Um den JavaScript-Code in einer benutzerdefinierten Visualisierung zu überprüfen, extrahieren Sie den Code der benutzerdefinierten Visualisierung. Im Folgenden wird gezeigt, wie Sie den Code extrahieren:  

1. Speichern Sie die PBIVIZ-Datei in einem Ordner.
2. Benennen Sie die Datei in eine ZIP-Datei um.
3. Extrahieren Sie die ZIP-Datei in einen lokalen Ordner.

## <a name="custom-visual-file-contents"></a>Dateiinhalte benutzerdefinierter Visualisierungen
PBIVIZ-Dateien enthalten Folgendes:

| **Datei** | **Beschreibung** |
|:--- |:--- |
| ./package.json |Eine Manifestdatei, die angibt, welche Dateien für die benutzerdefinierte Visualisierung geladen werden müssen. |
| ./resources |Enthält den CSS-, TypeScript- und JavaScript-Code, der von der benutzerdefinierten Visualisierung verwendet wird. |
| ./resources/&lt;Name&gt; |&lt;Name&gt; ist der Name der benutzerdefinierten Visualisierung. |
| ./resources/&lt;Name&gt;.css |Die für die benutzerdefinierte Visualisierung verwendete CSS-Ressourcendatei. |
| ./resources/&lt;Name&gt;.js |Der Code, der ausgeführt wird, wenn ein Benutzer auf „Benutzerdefinierte Visualisierungen aktivieren“ klickt oder nachdem ein Benutzer eine benutzerdefinierte Visualisierung importiert hat. Warnung: JavaScript-Code kann Sicherheits- oder Datenschutzrisiken enthalten. |
| ./resources/&lt;Name&gt;.ts |Der JavaScript-Quellcode für die Visualisierung im TypeScript-Format. Warnung: JavaScript- oder TypeScript-Code kann Sicherheits- oder Datenschutzrisiken enthalten. |
| ./resources/&lt;Name&gt;.png |Das Symbol, das Benutzern für die Visualisierung angezeigt wird. |

Nachdem Sie die PBIVIZ-Datei extrahiert haben, können Sie den Code überprüfen. Hier sind einige bewährte Methoden sowie Bedrohungen, nach denen Sie suchen sollten.

## <a name="best-practices-to-evaluate-the-javascript-or-typescript-code"></a>Bewährte Methoden zum Überprüfen des JavaScript- oder TypeScript-Codes
**JavaScript**- oder **TypeScript**-Code kann Sicherheits- oder Datenschutzrisiken enthalten. Hier sind einige bewährte Methoden sowie Bedrohungen, nach denen Sie suchen sollten.

### <a name="best-practices-to-evaluate-javascript-code"></a>Bewährte Methoden zum Überprüfen von JavaScript-Code
* Überprüfen Sie immer den Inhalt der JS-Datei. Dies ist der Code, der tatsächlich ausgeführt wird. Es ist auch möglich, dass der Inhalt der TS-Datei nicht in die JS-Datei kompiliert wird, die in der benutzerdefinierten Visualisierung enthalten ist.
* Überprüfen Sie immer den Inhalt der TS-Datei. Sie können die TS-Datei in die **Entwicklertools** laden, die Visualisierung exportieren und die daraus resultierende JS-Datei in der neu erstellten PBIVIZ-Datei mit der ursprünglichen JS-Datei der Visualisierung vergleichen.
* Vergewissern Sie sich, dass das Symbol für die benutzerdefinierte Visualisierung dem für andere Visualisierungen, die der Benutzer eventuell schon kennt, nicht zu sehr ähnelt.
* Überprüfen Sie Visualisierungen immer unter einem Testkonto, das nur über die mindestens erforderlichen Berechtigungen verfügt und keinen Zugriff auf vertrauliche Daten hat. Im Idealfall ist dieses Testkonto ein lokales Konto ohne Anmeldeinformationen für andere Dienste als Power BI.

### <a name="threats-to-look-for-in-javascript-code"></a>Bedrohungen, auf die im JavaScript-Code geachtet werden sollte
* Überprüfen Sie die Netzwerkaktivität, wenn die Visualisierung im Bearbeitungs- und Ansichtsmodus verwendet wird. Überprüfen Sie die durchgeführten Anfragen auf Konformität. Es sollten keine Anfragen an Ressourcen außerhalb der Power BI-Domäne erfolgen, sofern der Autor der Visualisierung dies nicht zuvor mitgeteilt hat.
* Alle Daten, die aus der Power BI-Domäne übermittelt werden, sollten Ihren Erwartungen an eine „normale“ Verwendung entsprechen. Beispiel: Wenn die Visualisierung einen Videoplayer implementiert, der einen iFrame verwendet, um ein Video von einer anderen Website anzuzeigen, werden in den IFrame-Anforderungen einige Informationen zum richtigen Rendern des Videos übermittelt. Wenn Sie jedoch feststellen, dass das gesamte Dataset über das Netzwerk gesendet wird, sollten Sie genau untersuchen, ob dies erforderlich und gewünscht ist.
* Überprüfen Sie, ob persönlich identifizierbare Daten gesendet oder von der benutzerdefinierten Visualisierung gespeichert werden.
* Überprüfen Sie, ob die benutzerdefinierte Visualisierung auf lokale Ressourcen auf dem Computer zugreift, um z. B. Dateien auf den Datenträger zu schreiben oder auf Cookies zuzugreifen.
* Überprüfen Sie, ob die benutzerdefinierte Visualisierung verborgenen Code enthält oder Code, der keinen klaren Zweck erfüllt.
* Speichern Sie Kopien der einzelnen Visualisierungen, die Sie in der Vergangenheit bereits überprüft haben.
* Wenn Sie ein Update einer bereits einmal überprüften Visualisierung überprüfen, achten Sie auf Änderungen. Wenden Sie immer dieselbe Sorgfalt auf Updates an, wie beim ersten Überprüfen der Visualisierung.
* Wenn Sie etwas finden, das verdächtig oder unklar ist, können Sie sich gerne an uns wenden.

## <a name="next-steps"></a>Nächste Schritte
[Visualisierungen in Power BI](power-bi-report-visualizations.md)  
[Benutzerdefinierte Visualisierungen in Power BI](power-bi-custom-visuals.md)  
[Veröffentlichen benutzerdefinierter Visualisierungen im Office Store](developer/office-store.md)  
[Erste Schritte mit den Power BI-Entwicklertools ](service-custom-visuals-getting-started-with-developer-tools.md)  
[Zertifizieren eines benutzerdefinierten visuellen Elements](power-bi-custom-visuals-certified.md)    
[Video zum Erstellen von benutzerdefinierten Visualisierungen für Power BI mit Sachin Patney und Nico Cristache (in englischer Sprache)](https://www.youtube.com/watch?v=kULc2VbwjCc)  

Weitere Fragen? [Stellen Sie Ihre Frage in der Power BI-Community.](http://community.powerbi.com/)

