---
title: Problembehandlung bei der Entwicklung von benutzerdefinierten Power BI-Visuals
description: In diesem Artikel werden einige häufige Probleme erläutert, die beim Entwickeln oder Erstellen eines benutzerdefinierten Power BI-Visuals auftreten können.
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-developer
ms.topic: conceptual
ms.date: 11/06/2018
ms.openlocfilehash: d6f3f654574e9cca081ae2f8191fd7b9fc017afd
ms.sourcegitcommit: 02f918a4f27625b6f4e47473193ebc8219db40e2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2018
ms.locfileid: "51223546"
---
# <a name="troubleshoot-power-bi-custom-visuals"></a>Problembehandlung bei benutzerdefinierten Power BI-Visuals

## <a name="debug"></a>Debuggen

**Pbiviz-Befehl wurde nicht gefunden (oder ähnliche Fehler)**

Wenn Sie `pbiviz` über die Befehlszeile Ihres Terminals ausführen, sollte das Hilfefenster angezeigt werden. Wenn dies nicht der Fall ist, war die Installation fehlerhaft. Stellen Sie sicher, dass Sie mindestens Version 4.0 von NodeJS installiert haben.

**Das Debug-Visual wird nicht auf der Registerkarte „Visualisierungen“ angezeigt**

Die Debug-Visualisierung sieht wie ein Eingabeaufforderungssymbol auf der Registerkarte **Visualisierungen** aus.

![Auswahl des Visuals](media/power-bi-custom-visuals-troubleshoot/powerbi-developer-visual-selection.png)

Wenn sie nicht angezeigt wird, vergewissern Sie sich, dass Sie sie in den Power BI-Einstellungen aktiviert haben.

> [!NOTE]
> Die Debug-Visualisierung ist derzeit nur im Power BI-Dienst und nicht in Power BI Desktop oder in der mobilen App verfügbar. Die gepackte Visualisierung kann aber überall ausgeführt werden.

**Server für visuelle Elemente kann nicht erreicht werden**

Führen Sie den Server für Visuals mit dem Befehl `pbiviz start` über die Befehlszeile Ihres Terminals im Stammverzeichnis des Visualprojekts aus. Wenn der Server ausgeführt wird, wurden vermutlich die SSL-Zertifikate nicht ordnungsgemäß installiert.

## <a name="next-steps"></a>Nächste Schritte

Weitere Informationen und Antworten auf Fragen finden Sie in den [häufig gestellten Fragen zu benutzerdefinierten Power BI-Visuals](power-bi-custom-visuals-faq.md#organizational-custom-visuals).