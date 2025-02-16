---
title: Exportieren eines Berichts aus dem Power BI-Dienst nach Power BI Desktop (Vorschau)
description: Herunterladen eines Berichts aus dem Power BI-Dienst in eine Power BI Desktop-Datei
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 03/02/2018
ms.author: maggies
LocalizationGroup: Reports
ms.openlocfilehash: 296970466505f01ae9ad11f994fe2008563f4884
ms.sourcegitcommit: 762857c8ca09ce222cc3f8b006fa1b65d11e4ace
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/05/2019
ms.locfileid: "66720207"
---
# <a name="export-a-report-from-power-bi-service-to-desktop-preview"></a>Exportieren eines Berichts aus dem Power BI-Dienst nach Power BI Desktop (Vorschau)
In Power BI Desktop können Sie einen Bericht in den Power BI-Dienst exportieren (dieser Vorgang wird auch als *Herunterladen* bezeichnet), indem Sie den Bericht speichern und **Veröffentlichen** auswählen. Es ist auch ein Export in die andere Richtung möglich, und Sie können einen Bericht aus dem Power BI-Dienst in die Desktopversion herunterladen. Die Erweiterung für in beide Richtungen exportierte Dateien lautet *.pbix*.

Es sind einige Einschränkungen und Überlegungen zu berücksichtigen, die weiter unten in diesem Artikel erläutert werden.

![Dropdownliste mit Dateien](media/service-export-to-pbix/power-bi-file-export.png)

## <a name="download-the-report-as-a-pbix"></a>Herunterladen des Berichts als PBIX-Datei
Gehen Sie zum Herunterladen der PBIX-Datei folgendermaßen vor:

1. Öffnen Sie im **Power BI-Dienst** den Bericht, den Sie herunterladen möchten, in der [Bearbeitungsansicht](consumer/end-user-reading-view.md).
2. Wählen Sie auf der Menüleiste **Datei > Bericht herunterladen** aus.
   
   > [!NOTE]
   > Der Bericht kann nur heruntergeladen werden, wenn er nach dem 23. November 2016 [mithilfe von Power BI Desktop](guided-learning/publishingandsharing.yml?tutorial-step=2) erstellt und nach diesem Zeitpunkt aktualisiert wurde. Andernfalls ist die Menüoption *Bericht herunterladen* im Power BI-Dienst abgeblendet.
   > 
   > 
3. Der Status der PBIX-Dateierstellung wird in einem Statusbanner angezeigt. Wenn die PBIX-Datei bereit ist, werden Sie zum Öffnen oder Speichern der Datei aufgefordert. Der Name der Datei stimmt mit dem Titel des Berichts überein.
   
    ![Öffnen, speichern oder Abbrechen](media/service-export-to-pbix/power-bi-save-pbix.png)
   
    Sie haben jetzt die Möglichkeit, die PBIX-Datei im Power BI-Dienst („app.powerbi.com“) oder in Power BI Desktop zu öffnen.     
4. Um den Bericht sofort in Power BI Desktop zu öffnen, wählen Sie **Öffnen** aus. Wählen Sie zum Speichern der Datei an einem bestimmten Speicherort **Speichern > Speichern unter** aus. Wenn nicht bereits geschehen, [installieren Sie Power BI Desktop](desktop-get-the-desktop.md).
   
    Wenn Sie den Bericht in Power BI Desktop öffnen, werden Sie möglicherweise in einer Warnmeldung darauf hingewiesen, dass einige im Power BI-Dienst-Bericht verfügbare Features in der Desktopversion eventuell nicht verfügbar sind.
   
    ![Dialogfeld „Warnung“](media/service-export-to-pbix/power-bi-export-to-pbix_2.png)

5. Der Berichts-Editor in Power BI Desktop und der Berichts-Editor im Power BI-Dienst sind sich sehr ähnlich.  
   
    ![Berichts-Editor in Desktop](media/service-export-to-pbix/power-bi-desktop.png)

## <a name="considerations-and-troubleshooting"></a>Zu beachtende Aspekte und Problembehandlung
Beim Herunterladen (Exportieren) einer *PBIX*-Datei aus dem Power BI-Dienst sind einige wichtige Aspekte zu beachten:

* Zum Herunterladen der Datei müssen Sie über Bearbeitungszugriff auf den Bericht verfügen.
* Der Bericht muss mit **Power BI Desktop** erstellt und für den **Power BI-Dienst** *veröffentlicht* worden sein, oder die PBIX-Datei muss in den Dienst *hochgeladen* worden sein.
* Die Berichte müssen nach dem 23. November 2016 veröffentlicht oder aktualisiert worden sein. Vor diesem Datum veröffentlichte Berichte können nicht heruntergeladen werden.
* Dieses Feature kann nicht für Berichte und Inhaltspakete genutzt werden, die ursprünglich im **Power BI-Dienst** erstellt wurden.
* Sie sollten immer die neueste Version von **Power BI Desktop** verwenden, wenn Sie heruntergeladene Dateien öffnen. Heruntergeladene *PBIX*-Dateien werden in nicht aktuellen Versionen von **Power BI Desktop** möglicherweise nicht geöffnet.
* Wenn Ihr Administrator die Fähigkeit zum Exportieren von Daten deaktiviert hat, wird dieses Feature im **Power BI-Dienst** nicht angezeigt.
* Ein Dataset mit inkrementeller Aktualisierung kann nicht in eine *PBIX*-Datei heruntergeladen werden.

## <a name="next-steps"></a>Nächste Schritte
Sehen Sie sich das **Guy in a Cube**-Kurzvideo (in englischer Sprache) zu diesem Feature an:

<iframe width="560" height="315" src="https://www.youtube.com/embed/ymWqU5jiUl0" frameborder="0" allowfullscreen></iframe>

Weitere Informationen zur Verwendung des **Power BI-Diensts** finden Sie in den folgenden Artikeln:

* [Berichte in Power BI](consumer/end-user-reports.md)
* [Grundlegende Konzepte für Designer im Power BI-Dienst](service-basic-concepts.md)

Nachdem Sie **Power BI Desktop** installiert haben, erhalten Sie in den folgenden Artikeln die nötigen Informationen für einen schnellen Einstieg:

* [Erste Schritte mit Power BI Desktop](desktop-getting-started.md)

Weitere Fragen? [Wenden Sie sich an die Power BI-Community](http://community.powerbi.com/)   

