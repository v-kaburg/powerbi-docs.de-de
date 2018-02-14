---
title: Deaktivieren von Datenschutzeinstellungen
description: "Hier erfahren Sie, wie Sie schnelles Kombinieren innerhalb des persönlichen Gateways aktivieren, um die Datenschutzeinstellungen für die Aktualisierung zu deaktivieren."
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
ms.tgt_pltfrm: na
ms.workload: powerbi
ms.date: 02/06/2018
ms.author: davidi
ms.openlocfilehash: 5d754dbdd5d52e7a5b123755015e656d9fb2cea2
ms.sourcegitcommit: db37f5cef31808e7882bbb1e9157adb973c2cdbc
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2018
---
# <a name="disable-privacy-setting-in-power-bi-gateway---personal"></a>Deaktivieren der Datenschutzeinstellungen in Power BI-Gateway – Privat
> [!NOTE]
> Es gibt eine neue Version von Personal Gateway für Power BI, die als **Lokales Datengateway (persönlicher Modus)** bezeichnet wird. Im folgende Artikel wird die vorherige Version des persönlichen Gateways beschrieben, die als **Power BI Gateway – Personal** bezeichnet und nach dem 31. Juli 2017 eingestellt und funktionsunfähig wird. Informationen über die neue Version des persönlichen Gateways samt deren Installation finden Sie im Artikel [**Lokales Datengateway (persönlicher Modus)**](service-gateway-personal-mode.md). Schnelles Kombinieren ist ebenfalls in der neuen Version des persönlichen Gateways verfügbar und wird auch in dem Artikel beschrieben.
> 
> 

In Abhängigkeit von den Datenschutzeinstellungen für Ihre Datenquelle wird bei Verwendung des privaten Gateways möglicherweise die folgende Fehlermeldung angezeigt.

> *Fehler beim Verarbeiten der Daten im Dataset.*
> 
> *[Daten können nicht verbunden werden] &lt;Abfragteteil&gt;/&lt;…&gt;/&lt;…&gt; greift auf Datenquellen mit Sicherheitsstufen zu, die nicht gemeinsam verwendet werden können. Erstellen Sie diese Datenkombination neu.*
> 
> 

Um diesen Fehler zu umgehen, können Sie **Schnelles Kombinieren**aktivieren. Durch die Option **Schnelles Kombinieren** werden die Datenschutzeinstellungen ignoriert, wodurch die verschiedenen Datenquellen kombiniert werden können.

> [!NOTE]
> Datenschutzebenen werden nicht berücksichtigt, wenn Sie Daten kombinieren. Dadurch können beim Kombinieren von Daten vertrauliche Daten einer anderen Datenquelle zur Verfügung gestellt werden.
> 
> 

## <a name="what-is-fast-combine"></a>Was ist schnelles Kombinieren?
Weitere Informationen zu Sicherheitsstufen und schnellem Kombinieren finden Sie unter [Sicherheitsstufen](https://support.office.com/article/Privacy-levels-Power-Query-CC3EDE4D-359E-4B28-BC72-9BEE7900B540). Standardmäßig wird die Sicherheitsstufe auf „Privat“ festgelegt, was zum oben genannten Fehler führen kann. Dies liegt daran, dass die Einstellung „Privat“ die Datenquelle von anderen Quellen isoliert. Ein Beispiel, in dem dies ein Problem darstellen können, wäre eine parametrisierte Abfrage, die Eingaben aus einer anderen Datenquelle erhält.

Durch das Aktivieren von schnellem Kombinieren wird die Einstellung „Privat“ ignoriert und die Ausführung ermöglicht.

## <a name="turn-on-fast-combine"></a>Aktivieren von schnellem Kombinieren
Mithilfe der folgenden Schritte können Sie schnelles Kombinieren für Ihr privates Gateway aktivieren. Das lokale Datengateway verfügt nicht über diese Einstellung.

1. Öffnen Sie **ConnectorConfig.xml**.  Die Datei kann sich an einem von zwei Speicherorten auf dem Computer befinden.  Wenn Sie Administrator auf dem Computer sind, lautet der Speicherort wie folgt.
   
    <pre><code>C:\Program Files\Power BI Personal Gateway\1.0\Configurator\Connector</code></pre>
   
    Wenn Sie kein Administrator sind, ist die Datei in folgendem Pfad gespeichert.
   
    <pre><code>C:\Users\[username]\AppData\Local\Power BI Personal Gateway\1.0\Configurator\Connector</code></pre>
    
2. Fügen Sie das Element **&lt;EnableFastCombine&gt;** mit dem Wert „true“ der Konfigurationsdatei hinzu. Durch das Hinzufügen dieses Elements wird die Option **Schnelles Kombinieren** aktiviert.
   
   <pre><code>&lt;EnableFastCombine&gt;true&lt;/EnableFastCombine&gt;</code></pre>
   
   ![](media/refresh-enable-fast-combine/configfile.png)
3. Schließen Sie den Gateway-Konfigurationsbildschirm, und rufen Sie ihn erneut auf.
4. Es wird ein Status angezeigt, der Sie darüber informiert, dass schnelles Kombinieren aktiviert ist.
   
   ![](media/refresh-enable-fast-combine/fastcombineenabled.png)

## <a name="turn-off-fast-combine"></a>Deaktivieren von schnellem Kombinieren
1. Öffnen Sie **ConnectorConfig.xml**.  Die Datei kann sich an einem von zwei Speicherorten auf dem Computer befinden.  Wenn Sie Administrator auf dem Computer sind, lautet der Speicherort wie folgt.
   
    <pre><code>C:\Program Files\Power BI Personal Gateway\1.0\Configurator\Connector</code></pre>
   
    Wenn Sie kein Administrator sind, ist die Datei in folgendem Pfad gespeichert.
   
    <pre><code>C:\Users\[username]\AppData\Local\Power BI Personal Gateway\1.0\Configurator\Connector</code></pre>

2. Entfernen Sie das Element **&lt;EnableFastCombine&gt;** aus der Konfigurationsdatei. Durch das Entfernen dieses Elements wird die Option **Schnelles Kombinieren** deaktiviert.
3. Schließen Sie den Gateway-Konfigurationsbildschirm, und rufen Sie ihn erneut auf.
4. Der Status zur Aktivierung der Option **Schnelles Kombinieren** wird nicht mehr angezeigt.

## <a name="next-steps"></a>Nächste Schritte
[Lokales Datengateway (persönlicher Modus) – die neue Version des persönlichen Gateways](service-gateway-personal-mode.md)
[Datenschutzebenen](https://support.office.com/article/Privacy-levels-Power-Query-CC3EDE4D-359E-4B28-BC72-9BEE7900B540)  
[Allgemeine Abfrageaufgaben in Power BI Desktop](desktop-common-query-tasks.md)  
Weitere Fragen? [Wenden Sie sich an die Power BI-Community](http://community.powerbi.com/)

