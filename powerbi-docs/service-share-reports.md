---
title: "Freigeben von Power BI-Berichten für Kollegen"
description: "Erfahren Sie, wie Sie Power BI-Berichte und gefilterte Berichte für Kollegen in Ihrer Organisation freigeben."
services: powerbi
documentationcenter: 
author: maggiesMSFT
manager: kfile
backup: ajayan
editor: 
tags: 
featuredvideoid: 0tUwn8DHo3s
qualityfocus: complete
qualitydate: 06/22/2016
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 11/14/2017
ms.author: maggies
ms.openlocfilehash: 022f085d12d7dc872052ca9205deca264b1c0418
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2017
---
# <a name="share-power-bi-reports-with-your-coworkers"></a>Freigeben von Power BI-Berichten für Ihre Kollegen
*Freigeben* ist eine gute Möglichkeit, einigen Personen Zugriff auf Ihre Dashboards und Berichte zu gewähren. Power BI bietet [verschiedene Möglichkeiten zum gemeinsamen Bearbeiten und Verteilen Ihrer Berichte](service-how-to-collaborate-distribute-dashboards-reports.md), und Freigeben ist nur eine davon.

Zum Freigeben benötigen Sie und die Empfänger eine [Power BI Pro-Lizenz](service-free-vs-pro.md), oder es muss sich um Inhalte in einer [Premium-Kapazität](service-premium.md) handeln. Vorschläge? Das Power BI-Team ist immer an Ihrem Feedback interessiert. Besuchen Sie daher die [Power BI-Community-Website](https://community.powerbi.com/).

Sie können einen Bericht für Kollegen freigeben, deren E-Mail-Domäne mit der Ihrigen identisch ist – über „Mein Arbeitsbereich“ oder über einen App-Arbeitsbereich. Wenn Sie einen Bericht freigeben, können diejenigen, für die Sie ihn freigeben, ihn anzeigen und damit interagieren, aber ihn nicht bearbeiten. Sie sehen die gleichen Daten wie Sie im Bericht, es sei denn, die [Sicherheit auf Zeilenebene (Row-Level Security, RLS)](service-admin-rls.md) ist aktiviert. 

## <a name="share-a-power-bi-report"></a>Freigeben eines Power BI-Berichts
1. [Erstellen Sie im Power BI-Dienst ein Dashboard](service-dashboard-create.md) mit mindestens einer Kachel, die mit dem Bericht verknüpft ist, den Sie freigeben möchten. 
   
    Auch wenn Sie nur den Bericht freigeben möchten, müssen Sie zunächst ein Dashboard erstellen, das mit dem Bericht verknüpft ist, und es freigeben. 

1. Wählen Sie in der rechten oberen Ecke des Dashboards **Freigeben** aus.

     ![„Freigeben“ auswählen](media/service-share-reports/power-bi-share-upper-right.png)
  
2. Geben Sie an, für wen es freigegeben werden soll. Wenn diese Personen nicht per E-Mail über das Dashboard benachrichtigt werden sollen, deaktivieren Sie das Kontrollkästchen **E-Mail-Benachrichtigung an Empfänger senden**.

     ![Kontrollkästchen „E-Mail-Benachrichtigung an Empfänger senden“ deaktivieren](media/service-share-reports/power-bi-share-dont-send-mail.png)

4. Wählen Sie **Freigeben**aus.

      Die Personen, für die Sie das Dashboard freigeben, sind dann berechtigt, den zugrunde liegenden Bericht anzuzeigen. 

1. Öffnen Sie den Bericht im Power BI-Dienst, kopieren Sie die URL der Berichtsseite, und senden Sie sie an Ihre Kollegen. 
   
    Wenn diese den Link auswählen, wird in Power BI eine schreibgeschützte Version des Berichts geöffnet.

## <a name="share-a-filtered-version-of-a-report"></a>Freigeben einer gefilterten Version eines Berichts
Wie gehen Sie vor, wenn Sie eine gefilterte Version eines Berichts freigeben möchten? Dabei handelt es sich möglicherweise um einen Bericht, der nur Daten für einen bestimmten Ort, einen bestimmten Vertriebsmitarbeiter oder ein bestimmtes Jahr enthält. Sie erstellen zu diesem Zweck eine benutzerdefinierte URL.

1. Öffnen Sie den Bericht in der [Bearbeitungsansicht](service-reading-view-and-editing-view.md), wenden Sie den Filter an, und speichern Sie den Bericht.
   
   In diesem Beispiel wird das [Analysebeispiel für den Einzelhandel](sample-tutorial-connect-to-the-samples.md) so gefiltert, dass nur Werte angezeigt werden, in denen **Territory** gleich **NC** ist.
   
   ![Berichtsfilterbereich](media/service-share-reports/power-bi-filter-report2.png)
2. Fügen Sie am Ende der Berichtsseiten-URL Folgendes hinzu:
   
   ?filter=*Tabellenname*/*Feldname* eq *Wert*
   
    Das Feld muss vom Typ **string** sein, und weder der *Tabellenname* noch der *Feldname* darf Leerzeichen enthalten.
   
   In diesem Beispiel lautet der Name der Tabelle **Store**, das Feld hat den Namen **Territory**, und der Wert, nach dem gefiltert werden soll, lautet **NC**:
   
    ?filter=Store/Territory eq NC
   
   ![URL für gefilterten Bericht](media/service-share-reports/power-bi-filter-url3.png)
   
   Durch den Browser werden Sonderzeichen hinzugefügt, die Schrägstriche und Leerzeichen darstellen, sodass die URL schließlich wie folgt lautet:
   
   app.powerbi.com/groups/me/reports/010ae9ad-a9ab-4904-a7a1-10a61f70f2f5/ReportSection2?filter=Store%252FTerritory%20eq%20NC
3. Senden Sie diese URL an Ihre Kollegen. 
   
   Wenn diese den Link auswählen, wird in Power BI eine schreibgeschützte Version des gefilterten Berichts geöffnet.

## <a name="next-steps"></a>Nächste Schritte
* Feedback? Anregungen nehmen wir auf der [Power BI-Communitywebsite](https://community.powerbi.com/) entgegen.
* [Wie kann ich Dashboards und Berichte freigeben?](service-how-to-collaborate-distribute-dashboards-reports.md)
* [Freigeben eines Dashboards](service-share-dashboards.md)
* Weitere Fragen? [Wenden Sie sich an die Power BI-Community](http://community.powerbi.com/).

