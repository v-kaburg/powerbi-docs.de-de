---
title: "Hinzufügen benutzerdefinierter Visualisierungen zu Berichten (Desktop)"
description: "Hinzufügen benutzerdefinierter Visualisierungen zu Berichten in der Desktop-Version"
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: complete
qualitydate: 03/15/2016
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 09/27/2017
ms.author: mihart
ms.openlocfilehash: b3a3e34fac546ee57cd66924e72a2c93aa647850
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2017
---
# <a name="add-a-custom-visual-to-a-report-desktop"></a>Hinzufügen benutzerdefinierter Visualisierungen zu Berichten (Desktop)
Sie haben [eine benutzerdefinierte Visualisierungsvorlage heruntergeladen](service-custom-visuals-office-store.md) und sie auf Ihrem Computer oder an einem anderen Speicherort gespeichert.  Der nächste Schritt ist das Importieren der benutzerdefinierten Visualvorlage in einen Bericht, damit sie Ihrem Bereich „Visualisierungen“ als Option hinzugefügt wird.

![](media/power-bi-custom-visuals-use/pbi-custom-viz-icon.png)

Beim Importieren wird eine benutzerdefinierte Visualisierungsvorlage einem bestimmten Bericht hinzugefügt. Wenn Sie die Visualisierungsvorlage in einem anderen Bericht verwenden möchten, müssen Sie sie ebenfalls in diesen Bericht importieren. Wenn ein Bericht mit einer benutzerdefinierten Visualisierung mit der Option **Speichern unter** gespeichert wird, wird eine Kopie der benutzerdefinierten Visualisierungsvorlage mit dem neuen Bericht gespeichert.

1. Öffnen Sie Power BI Desktop, und wählen Sie den Bericht aus, in dem Sie die benutzerdefinierte Visualisierung hinzufügen möchten.   
2. Es gibt zwei Möglichkeiten für das Importieren einer benutzerdefinierten Visualisierungsvorlage: über das Menü **Datei** oder im Bereich **Visualisierungen** .
   
    **Über das Menü „Datei“ der Desktop-Version**
   
    Wählen Sie im Menü **Datei** des Berichts **Importieren** &gt; **Benutzerdefiniertes visuelles Power BI-Element** aus. Sie müssen dazu die Bearbeitungsansicht verwenden.    
   
      ![](media/power-bi-custom-visuals-use/power-bi-import.png)
   
    **Im Bereich „Visualisierung“**
   
    Wählen Sie im Bereich **Visualisierungen** die Option **Einfügen (…)**aus.    
   
      ![](media/power-bi-custom-visuals-use/insertpane.png)
   
    Wählen Sie **Benutzerdefiniertes visuelles Element importieren** aus.  
   
      ![](media/power-bi-custom-visuals-use/insertpane.png)
3. **Überprüfen Sie die Warnung**.
   
    Ein benutzerdefiniertes Visual hat Zugriff auf die Daten im Bericht, und wenn Sie einen Bericht, der ein benutzerdefiniertes Visual enthält, freigeben, können Ihre Kollegen möglicherweise auf diese Daten zugreifen. Überprüfen Sie deshalb unbedingt die benutzerdefinierte Visualisierung, um sicherzustellen, dass sie aus einer vertrauenswürdigen Quelle stammt. Microsoft empfiehlt Ihnen die Zusammenarbeit mit Ihrer IT-Abteilung, wenn Sie sich nicht sicher sind, ob Sie ein bestimmtes benutzerdefiniertes Visual verwenden sollten, das Sie aus dem Office Online Store, per E-Mail oder von einer anderen Quelle erhalten haben.
   
    ![](media/power-bi-custom-visuals-use/caution.png)
4. Navigieren Sie zum Speicherort der PBIVIZ-Datei für das benutzerdefinierte Visual, und öffnen Sie sie.
5. Ein Symbol (auch als *Vorlage* bezeichnet) wird Ihrem Bereich **Visualisierungen** hinzugefügt.
   
    ![](media/power-bi-custom-visuals-use/visualuse.png)
6. Wählen Sie die benutzerdefinierte Visualisierungsvorlage aus, um sie zu Ihrem Bericht hinzuzufügen, genauso wie andere Vorlagen im Bereich „Visualisierungen“. Fügen Sie Felder und Filter hinzu, und erstellen Sie das visuelle Element.
7. Formatieren Sie die benutzerdefinierte Visualisierung, wie Sie es von anderen Visualisierungen gewohnt sind.  Wählen Sie im Bereich **Visualisierungen** das Farbrollersymbol aus. Die verfügbaren Formatierungsoptionen sind vom Typ der Visualisierung abhängig.

## <a name="considerations-and-troubleshooting"></a>Zu beachtende Aspekte und Problembehandlung
* Damit benutzerdefinierte visuelle Elemente in [PowerPoint exportiert](service-publish-to-powerpoint.md) oder [in E-Mail-Nachrichten angezeigt werden können, die empfangen werden, wenn ein Kunde Berichtsseiten abonniert](service-report-subscribe.md), müssen sie als zertifizierte benutzerdefinierte visuelle Elemente definiert werden, die den Microsoft-Zertifizierungsprozess für *benutzerdefinierte visuelle Elemente* erfolgreich durchlaufen haben.  Die Liste der *zertifizierten benutzerdefinierten visuellen Elemente* sowie weitere Informationen zum Zertifizierungsprozess finden Sie unter [Zertifizierte benutzerdefinierte visuelle Elemente](power-bi-custom-visuals-certified.md).

## <a name="next-steps"></a>Nächste Schritte
[Herunterladen und Verwenden benutzerdefinierter Visualisierungen aus dem Office Store](service-custom-visuals-office-store.md)  
[Hinzufügen benutzerdefinierter Visualisierungen zu Berichten im Power BI-Dienst](power-bi-report-add-custom-visual.md)  
[Veröffentlichen benutzerdefinierter Visualisierungen im Office Store](developer/office-store.md)  
[Benutzerdefinierte Visualisierungen in Power BI](power-bi-custom-visuals.md)  
Weitere Fragen? [Wenden Sie sich an die Power BI-Community](http://community.powerbi.com/)

