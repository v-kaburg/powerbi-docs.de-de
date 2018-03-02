---
title: "Unterstützung für große Datasets in Power BI Premium"
description: "Power BI Premium unterstützt jetzt Datasets mit bis zu 10 GB."
services: powerbi
documentationcenter: 
author: MarkMcGeeAtAquent
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
ms.date: 02/27/2018
ms.author: jocaplan
LocalizationGroup: Premium
ms.openlocfilehash: def06965692644c0328dae7a1d0ade8d13cc0d6c
ms.sourcegitcommit: 743e44fc8730fea0f7149916080b0c6d7eb6359d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2018
---
# <a name="power-bi-premium-support-for-large-datasets"></a>Unterstützung für große Datasets in Power BI Premium

Power BI Premium unterstützt Uploads von Power BI Desktop-Dateien (.pbix) mit einer Größe von bis zu 10 GB. Sobald der Upload abgeschlossen ist, kann ein Dataset auf bis zu 12 GB aktualisiert werden. Wenn Sie ein großes Dataset verwenden möchten, veröffentlichen Sie es in einem Arbeitsbereich, dem Premium-Kapazität zugewiesen wurde.
 
## <a name="best-practices"></a>Bewährte Methoden

In diesem Abschnitt werden bewährte Methoden zum Arbeiten mit großen Datasets beschrieben.

**Große Modelle können sehr ressourcenintensiv für die Kapazität sein**. Daher wird mindestens eine P1-SKU für Modelle mit mehr als 1 GB empfohlen. In der folgenden Tabelle werden die empfohlenen SKUs für verschiedene PBIX-Größen aufgeführt:


   |SKU  |PBIX-Größe   |
   |---------|---------|
   |P1    | < 3 GB        |
   |P2    | < 6 GB        |
   |P3    | bis zu 10 GB   |



**In PBIX-Dateien werden Daten stark komprimiert gespeichert**. Die Daten werden in den meisten Fällen beim Laden in den Speicher mehrmals größer, ebenso wie anschließend bei jeder Datenaktualisierung.

**Die geplante Aktualisierung von großen Datasets kann lange dauern** und sehr ressourcenintensiv sein. Planen Sie daher nicht zu viele parallele Aktualisierungen. Beachten Sie auch, dass das Timeout für geplante Aktualisierungsaufträge bei allen Datasets in dieser Kapazität auf vier Stunden verdoppelt wurde.

**Das erste Laden eines Berichts für große Datasets kann sehr lange dauern**, wenn das Dataset längere Zeit nicht verwendet wurde, da das Modell in den Speicher der Premium-Kapazität geladen wird. Der Ladevorgang wird bei Berichten mit längerer Ladezeit in einer Statusanzeige angezeigt.

**Wenn Sie den Arbeitsbereich aus Premium-Kapazität entfernen**, funktionieren das Modell und alle zugehörigen Berichte und Dashboards nicht mehr.

**Die Speicher- und Zeitkapazitäten für die einzelnen Abfragen sind bei Premium-Kapazität deutlich höher**, es wird jedoch dringend empfohlen, Visuals mit Filtern und Datenschnitten so einzuschränken, dass nur die benötigten Daten angezeigt werden.

## <a name="next-steps"></a>Nächste Schritte
[Power BI Premium – Beschreibung](service-premium.md)  
[Power BI Premium release notes (Power BI Premium – Anmerkungen zu dieser Version)](service-premium-release-notes.md)  
[Microsoft Power BI Premium-Whitepaper](https://aka.ms/pbipremiumwhitepaper)  
[Planning a Power BI Enterprise Deployment whitepaper (Whitepaper zum Planen der Unternehmensbereitstellung von Power BI)](https://aka.ms/pbienterprisedeploy)  
[Extended Pro Trial activation (Aktivierung der erweiterten Pro-Testversion)](service-extended-pro-trial.md)  

Weitere Fragen? [Stellen Sie Ihre Frage in der Power BI-Community.](https://community.powerbi.com/)
