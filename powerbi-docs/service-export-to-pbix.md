---
title: Exportieren eines Berichts aus dem Power BI-Dienst nach Power BI Desktop (Vorschau)
description: Herunterladen eines Berichts aus dem Power BI-Dienst in eine Power BI Desktop-Datei
services: powerbi
documentationcenter: 
author: mihart
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
ms.date: 01/24/2018
ms.author: mihart
ms.openlocfilehash: 7c0bd2f342385f71fd91bb81a284ef41deb46169
ms.sourcegitcommit: be5223b62e9a5d57c52f8588d4e539d814751dd6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2018
---
# <a name="export-a-report-from-power-bi-service-to-desktop-preview"></a>Exportieren eines Berichts aus dem Power BI-Dienst nach Power BI Desktop (Vorschau)
In Power BI Desktop können Sie einen Bericht in den Power BI-Dienst exportieren (dieser Vorgang wird auch als *Herunterladen* bezeichnet), indem Sie den Bericht speichern und **Veröffentlichen** auswählen. Es ist auch ein Export in die andere Richtung möglich, und Sie können einen Bericht aus dem Power BI-Dienst in die Desktopversion herunterladen. Die Erweiterung für in beide Richtungen exportierte Dateien lautet *.pbix*.

Es sind einige Einschränkungen und Überlegungen zu berücksichtigen, die weiter unten in diesem Artikel erläutert werden.

![](media/service-export-to-pbix/power-bi-file-export.png)

## <a name="download-the-report-as-a-pbix"></a>Herunterladen des Berichts als PBIX-Datei
Gehen Sie zum Herunterladen der PBIX-Datei folgendermaßen vor:

1. Öffnen Sie im **Power BI-Dienst** den Bericht, den Sie herunterladen möchten, in der [Bearbeitungsansicht](service-reading-view-and-editing-view.md).
2. Wählen Sie auf der Menüleiste **Datei > Bericht herunterladen** aus.
   
   > [!NOTE]
   > Der Bericht kann nur heruntergeladen werden, wenn er nach dem 23. November 2016 [mithilfe von Power BI Desktop](guided-learning/publishingandsharing.yml#step-2) erstellt und nach diesem Zeitpunkt aktualisiert wurde. Andernfalls ist die Menüoption *Bericht herunterladen* im Power BI-Dienst abgeblendet.
   > 
   > 
3. Der Status der PBIX-Dateierstellung wird in einem Statusbanner angezeigt. Wenn die PBIX-Datei bereit ist, werden Sie zum Öffnen oder Speichern der Datei aufgefordert. Der Name der Datei stimmt mit dem Titel des Berichts überein.
   
    ![](media/service-export-to-pbix/power-bi-save-pbix.png)
   
    Sie haben jetzt die Möglichkeit, die PBIX-Datei im Power BI-Dienst („app.powerbi.com“) oder in Power BI Desktop zu öffnen.     
4. Um den Bericht sofort in Power BI Desktop zu öffnen, wählen Sie **Öffnen** aus. Wählen Sie zum Speichern der Datei an einem bestimmten Speicherort **Speichern > Speichern unter** aus. Wenn nicht bereits geschehen, [installieren Sie Power BI Desktop](desktop-get-the-desktop.md).
   
    Wenn Sie den Bericht in Power BI Desktop öffnen, werden Sie möglicherweise in einer Warnmeldung darauf hingewiesen, dass einige im Power BI-Dienst-Bericht verfügbare Features in der Desktopversion eventuell nicht verfügbar sind.
   
    ![](media/service-export-to-pbix/power-bi-export-to-pbix_2.png)

5. Der Berichts-Editor in Power BI Desktop und der Berichts-Editor im Power BI-Dienst sind sich sehr ähnlich.  
   
    ![](media/service-export-to-pbix/power-bi-desktop.png)

## <a name="considerations-and-troubleshooting"></a>Zu beachtende Aspekte und Problembehandlung
Beim Herunterladen (Exportieren) einer *PBIX*-Datei aus dem Power BI-Dienst sind einige wichtige Aspekte zu beachten:

* Zum Herunterladen der Datei müssen Sie über Bearbeitungszugriff auf den Bericht verfügen.
* Der Bericht muss mit **Power BI Desktop** erstellt und für den **Power BI-Dienst** *veröffentlicht* worden sein, oder die PBIX-Datei muss in den Dienst *hochgeladen* worden sein.
* Die Berichte müssen nach dem 23. November 2016 veröffentlicht oder aktualisiert worden sein. Vor diesem Datum veröffentlichte Berichte können nicht heruntergeladen werden.
* Dieses Feature kann nicht für Berichte und Inhaltspakete genutzt werden, die ursprünglich im **Power BI-Dienst** erstellt wurden.
* Sie sollten immer die neueste Version von **Power BI Desktop** verwenden, wenn Sie heruntergeladene Dateien öffnen. Heruntergeladene *PBIX*-Dateien werden in nicht aktuellen Versionen von **Power BI Desktop** möglicherweise nicht geöffnet.
* Wenn Ihr Administrator die Fähigkeit zum Exportieren von Daten deaktiviert hat, wird dieses Feature im **Power BI-Dienst** nicht angezeigt.

## <a name="next-steps"></a>Nächste Schritte
Sehen Sie sich das **Guy in a Cube**-Kurzvideo (in englischer Sprache) zu diesem Feature an:

<iframe width="560" height="315" src="https://www.youtube.com/embed/ymWqU5jiUl0" frameborder="0" allowfullscreen></iframe>

Weitere Informationen zur Verwendung des **Power BI-Diensts** finden Sie in den folgenden Artikeln:

* [Berichte in Power BI](service-reports.md)
* [Power BI – Grundkonzepte](service-basic-concepts.md)

Nachdem Sie **Power BI Desktop** installiert haben, erhalten Sie in den folgenden Artikeln die nötigen Informationen für einen schnellen Einstieg:

* [Erste Schritte mit Power BI Desktop](desktop-getting-started.md)

Weitere Fragen? [Wenden Sie sich an die Power BI-Community](http://community.powerbi.com/)   

