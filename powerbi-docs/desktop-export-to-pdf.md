---
title: Exportieren Sie Ihre Berichte aus Power BI Desktop in das PDF-Format.
description: Exportieren Sie Berichte aus Power BI Desktop ganz einfach ins PDF-Format, und drucken Sie diese aus.
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 08/08/2018
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 7b835231356ad14ab434b86a2d1f99aa7212358d
ms.sourcegitcommit: 5e83fa6c93a0bc6599f76cc070fb0e5c1fce0082
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/13/2019
ms.locfileid: "56215628"
---
# <a name="export-reports-to-pdf-from-power-bi-desktop"></a>Exportieren von Berichten aus Power BI Desktop in das PDF-Format
In **Power BI Desktop** können Sie Berichte in eine PDF-Datei exportieren und diese problemlos freigeben oder drucken.

![Exportieren von Berichten in das PDF-Format](media/desktop-export-to-pdf/export-to-pdf_01.png)

Der Vorgang zum Exportieren eines Bericht aus **Power BI Desktop** in ein PDF-Dokument und die Möglichkeit zum anschließenden Drucken oder Freigeben der Dokumente ist unkompliziert. Klicken Sie in Power BI Desktop einfach auf **Datei > In PDF exportieren**.

**In PDF exportieren** exportiert alle *sichtbaren* Seiten im Bericht, wobei jede Berichtsseite in eine einzelne Seite in der PDF-Datei exportiert wird. Berichtsseiten wie QuickInfos oder ausgeblendete Seiten, die aktuell nicht sichtbar sind, werden nicht in die PDF-Datei exportiert. 

![„In PDF exportieren“ wird ausgeführt.](media/desktop-export-to-pdf/export-to-pdf_02.png)

Wenn Sie auf **Datei > In PDF exportieren** klicken, wird der Export gestartet, und es wird ein Dialogfeld angezeigt, in dem darauf hingewiesen wird, dass der Exportvorgang ausgeführt wird. Das Dialogfeld wird solange auf dem Bildschirm angezeigt, bis der Exportvorgang abgeschlossen ist. Während des Exportvorgangs ist die Interaktion mit dem Bericht, der exportiert wird, vollständig deaktiviert. Sie können erst mit dem Bericht interagieren, nachdem der Exportvorgang abgeschlossen oder von Ihnen abgebrochen wurde. 

Wenn der Export abgeschlossen ist, wird die PDF-Datei im standardmäßig eingestellten PDF-Viewer des Computers geladen. 

## <a name="considerations-and-limitations"></a>Überlegungen und Einschränkungen
Bei Verwendung des Features **In PDF exportieren** sind einige Punkte zu beachten:

* Das Feature **In PDF exportieren** ist nur mit **Power BI Desktop** verfügbar und zurzeit nicht im **Power BI-Dienst** verfügbar.
* Während benutzerdefinierte Visuals exportiert werden, werden im Bericht angewendete Hintergründe *nicht* exportiert.

Da der Hintergrund nicht in die PDF-Datei exportiert wird, sollten Sie besonders bei Berichten mit dunklen Hintergründen darauf achten. Wenn der Text in Ihrem Bericht hell oder weiß ist, um ihn vom dunklen Hintergrund hervorzuheben, wird er schwer zu lesen oder beim Exportvorgang in das PDF-Format nicht lesbar sein, da der Hintergrund nicht mit den anderen Berichtskomponenten exportiert wird. 



## <a name="next-steps"></a>Nächste Schritte
Es gibt viele interessante Visualelemente und Features in **Power BI Desktop**. Weitere Informationen finden Sie in den folgenden Ressourcen:

* [Use visual elements to enhance Power BI reports (Erweitern von Power BI-Berichten durch Visualelemente)](desktop-visual-elements-for-reports.md)
* [Was ist Power BI Desktop?](desktop-what-is-desktop.md)


