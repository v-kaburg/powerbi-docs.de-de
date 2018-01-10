---
title: Einbetten eines Berichts mithilfe eines iFrames
description: Die Installation von Power BI-Berichtsserver selbst erfolgt sehr schnell. Die Schritte zum Herunterladen, Installieren und Konfigurieren bis zur Inbetriebnahme dauern nur wenige Minuten.
services: powerbi
documentationcenter: 
author: guyinacube
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
ms.date: 11/09/2017
ms.author: maghan
ms.openlocfilehash: 0019b0a8d3fa628a1b3932a4c19eba0bf0d66ee3
ms.sourcegitcommit: eec6b47970bf69ed30638d1a20051f961ba792f2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/06/2018
---
# <a name="quickstart-embed-a-power-bi-report-using-an-iframe-and-url-parameters"></a>Schnellstart: Einbetten eines Power BI-Berichts mithilfe von URL-Parametern und eines iFrames

Sie können einen beliebigen Bericht einbetten, indem Sie einen iFrame in Ihrer Anwendung verwenden. 

## <a name="url-parameter"></a>URL-Parameter

Für jeden URl zu einem Bericht können Sie den Abfragezeichenfolgeparameter `?rs:Embed=true` hinzufügen.

Beispiel:

```
http://myserver/reports/powerbi/Sales?rs:embed=true
```

Dies funktioniert für alle Berichtstypen in Power BI-Berichtsserver.

## <a name="iframe"></a>iFrame

Sobald Sie die URL haben, können Sie einen iFrame auf einer Webseite erstellen, in dem der Bericht gehostet wird.

Beispiel:

```
<iframe width="800" height="600" src="http://myserver/reports/powerbi/Sales?rs:embed=true" frameborder="0" allowFullScreen="true"></iframe>
```

## <a name="url-filter"></a>URL-Filter

Sie können der URL einen Abfragezeichenfolgenparameter hinzufügen, um die im Power BI-Bericht zurückgegebenen Daten zu filtern.

Die Syntax ist einfach: Beginnen Sie mit der Berichts-URL, und fügen Sie ein Fragezeichen und dann diese Filtersyntax hinzu.

URL?filter=***Tabelle***/***Feld*** eq '***Wert***'

Beachten Sie folgende Punkte:

- Bei den Namen für **Tabelle** und **Feld** muss die Groß-/Kleinschreibung beachtet werden, beim **Wert** nicht.
- Sie können einen Bericht mit Feldern filtern, die in der Berichtsansicht ausgeblendet sind.
- **Wert** muss in einfache Anführungszeichen eingeschlossen werden.
- Beim Feldtyp muss es sich um eine Zeichenfolge handeln.
- Tabellen- und Feldnamen dürfen keine Leerzeichen enthalten.

###  <a name="example-filter-on-a-field"></a>Beispiel: Filtern nach einem Feld

Betrachten Sie das [Analysebeispiel für Einzelhandel](../sample-datasets.md). Angenommen, dies ist die URL des Berichts auf dem Berichtsserver in einem Ordner mit dem Namen „power-bi“:

```
https://report-server/reports/power-bi/Retail-Analysis-Sample
```

In der Kartenvisualisierung im Analysebeispiel für Einzelhandel werden Filialen in North Carolina und anderen Bundesstaaten angezeigt.

![Kartenvisualisierung aus dem Analysebeispiel für Einzelhandel](media/quickstart-embed/report-server-retail-analysis-sample-map.png)

*NC* ist der für „North Carolina“ im Feld **Territory** der Tabelle **Store** gespeicherte Wert. Wenn Sie den Bericht filtern möchten, sodass nur Daten für Filialen in North Carolina angezeigt werden, fügen Sie Folgendes an die URL an:

?filter=Store/Territory eq 'NC'

Der Bericht wird jetzt nach North Carolina gefiltert, und alle Visualisierungen auf der Berichtsseite zeigen nur noch Daten für North Carolina.

![Gefilterte Visualisierungen im Analysebeispiel für Einzelhandel](media/quickstart-embed/report-server-retail-analysis-sample-filtered-map.png)

### <a name="create-a-dax-formula-to-filter-on-multiple-values"></a>Erstellen einer DAX-Formel zum Filtern nach mehreren Werten

Eine andere Möglichkeit, nach mehreren Feldern zu filtern, besteht darin, in Power BI Desktop eine berechnete Spalte zu erstellen, in der zwei Felder zu einem einzelnen Wert verkettet werden. Anschließend können Sie nach diesem Wert filtern.

Das Analysebeispiel für Einzelhandel enthält zwei Felder: „Territory“ und „Chain“. In diesem Szenario können Sie in Power BI Desktop [eine berechnete Spalte](../desktop-tutorial-create-calculated-columns.md) (Feld) mit dem Namen „TerritoryChain“ erstellen. Beachten Sie, dass der **Feldname** keine Leerzeichen enthalten darf. Die DAX-Formel für diese Spalte sieht wie folgt aus:

TerritoryChain = [Territory] & "-" & [Chain]

Veröffentlichen Sie den Bericht auf dem Power BI-Berichtsserver, und verwenden Sie die URL-Abfragezeichenfolge, um die Daten so zu filtern, dass nur Lindseys-Filialen in NC angezeigt werden.

```
https://report-server/reports/power-bi/Retail-Analysis-Sample?filter=Store/TerritoryChain eq 'NC-Lindseys'

```

## <a name="next-steps"></a>Nächste Schritte

[Schnellstart: Erstellen eines Power BI-Berichts für Power BI-Berichtsserver](quickstart-create-powerbi-report.md)  
[Schnellstart: Erstellen eines paginierten Berichts für Power BI-Berichtsserver](quickstart-create-paginated-report.md)  

Weitere Fragen? [Stellen Sie Ihre Frage in der Power BI-Community.](https://community.powerbi.com/)