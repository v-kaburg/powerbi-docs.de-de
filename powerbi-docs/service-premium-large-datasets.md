---
title: Unterstützung für große Datasets in Power BI Premium
description: Power BI Premium unterstützt jetzt Datasets mit bis zu 10 GB.
author: jocaplan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-admin
ms.topic: conceptual
ms.date: 10/18/2018
ms.author: jocaplan
LocalizationGroup: Premium
ms.openlocfilehash: 416f022ee3c413c69650e6f1736cc94edcd58f13
ms.sourcegitcommit: a764e4b9d06b50d9b6173d0fbb7555e3babe6351
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2018
ms.locfileid: "49641250"
---
# <a name="power-bi-premium-support-for-large-datasets"></a>Unterstützung für große Datasets in Power BI Premium

Power BI Premium unterstützt Uploads von Power BI Desktop-Dateien (.pbix) mit einer Größe von bis zu 10 GB. Sobald der Upload abgeschlossen ist, kann ein Dataset auf bis zu 12 GB aktualisiert werden. Wenn Sie ein großes Dataset verwenden möchten, veröffentlichen Sie es in einem Arbeitsbereich, dem Premium-Kapazität zugewiesen wurde. In diesem Artikel werden Überlegungen und bewährte Methoden für die Arbeit mit großen Datasets beschrieben.

**Große Modelle können sehr ressourcenintensiv** für die Kapazität sein. Für Modelle mit mehr als 1 GB wird mindestens eine P1 SKU empfohlen. In der folgenden Tabelle werden die empfohlenen SKUs für verschiedene PBIX-Größen aufgeführt:

   |SKU  |PBIX-Größe   |
   |---------|---------|
   |P1    | < 3 GB        |
   |P2    | < 6 GB        |
   |P3, P4, P5    | bis zu 10 GB |

**In PBIX-Dateien werden Daten stark komprimiert gespeichert**. Die Daten werden in den meisten Fällen beim Laden in den Speicher mehrmals größer, ebenso wie anschließend bei jeder Datenaktualisierung.

**Die geplante Aktualisierung von großen Datasets kann lange dauern** und sehr ressourcenintensiv sein. Planen Sie daher nicht zu viele parallele Aktualisierungen. Beachten Sie auch, dass das Timeout für geplante Aktualisierungsaufträge bei allen Datasets in dieser Kapazität auf vier Stunden verdoppelt wurde. Die [inkrementelle Aktualisierung](service-premium-incremental-refresh.md) wird empfohlen, da Sie schneller sowie zuverlässiger ist und weniger Ressourcen beansprucht.

**Das erste Laden eines Berichts für große Datasets kann sehr lange dauern**, wenn das Dataset längere Zeit nicht verwendet wurde, da das Modell in den Speicher der Premium-Kapazität geladen wird. Der Ladevorgang wird bei Berichten mit längerer Ladezeit in einer Statusanzeige angezeigt.

**Wenn Sie den Arbeitsbereich aus Premium-Kapazität entfernen**, funktionieren das Modell und alle zugehörigen Berichte und Dashboards nicht mehr.

**Die Speicher- und Zeitkapazitäten für die einzelnen Abfragen sind bei Premium-Kapazität deutlich höher**, es wird jedoch dringend empfohlen, dass Sie Visuals mit Filtern und Datenschnitten einschränken, sodass nur die benötigten Daten angezeigt werden.

**Nächste Schritte**

[Was ist Power BI Premium?](service-premium.md)
[Neuigkeiten bei Power BI Premium](service-premium-release-notes.md)
[Microsoft Power BI Premium whitepaper (Whitepaper zu Microsoft Power BI Premium)](https://aka.ms/pbipremiumwhitepaper)
[Planning a Power BI Enterprise Deployment whitepaper (Whitepaper zur Planung einer Unternehmensbereitstellung von Power BI)](https://aka.ms/pbienterprisedeploy)

Weitere Fragen? [Stellen Sie Ihre Frage in der Power BI-Community.](https://community.powerbi.com/)
