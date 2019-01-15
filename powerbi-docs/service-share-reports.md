---
title: Freigeben eines gefilterten Power BI-Berichts für Ihre Kollegen
description: Erfahren Sie, wie Sie einen Power BI-Bericht für Kollegen in Ihrer Organisation filtern und freigeben.
author: maggiesMSFT
manager: kfile
ms.reviewer: lukaszp
featuredvideoid: 0tUwn8DHo3s
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 12/21/2018
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: 05bdb9ccca7715b74cb18462f215f7d1bf640526
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/15/2019
ms.locfileid: "54279748"
---
# <a name="share-a-filtered-power-bi-report-with-your-coworkers"></a>Freigeben eines gefilterten Power BI-Berichts für Ihre Kollegen
*Freigeben* ist eine gute Möglichkeit, einigen Personen Zugriff auf Ihre Dashboards und Berichte zu gewähren. Zudem bietet Power BI [verschiedene Möglichkeiten zum gemeinsamen Bearbeiten und Verteilen Ihrer Berichte](service-how-to-collaborate-distribute-dashboards-reports.md).

Zum Freigeben benötigen Sie und die Empfänger eine [Power BI Pro-Lizenz](service-features-license-type.md), oder es muss sich um Inhalte in einer [Premium-Kapazität](service-premium.md) handeln. 

Sie können einen Bericht für Kollegen in derselben E-Mail-Domäne wie Sie von den meisten Stellen im Power BI-Dienst aus freigeben: Ihre „Favoriten“, „Zuletzt verwendet“, „Für mich freigegeben“ (wenn der Besitzer es erlaubt), „Mein Arbeitsbereich“ oder andere Arbeitsbereiche. Wenn Sie einen Bericht freigeben, können diejenigen Mitarbeiter, für die Sie ihn freigeben, diesen anzeigen und damit interagieren. Sie können ihn jedoch nicht bearbeiten. Sie sehen die gleichen Daten wie Sie im Bericht, es sei denn, die [Sicherheit auf Zeilenebene (Row-Level Security, RLS)](service-admin-rls.md) ist aktiviert. 

Wie gehen Sie vor, wenn Sie eine gefilterte Version eines Berichts freigeben möchten? Dabei handelt es sich möglicherweise um einen Bericht, der nur Daten für einen bestimmten Ort, einen bestimmten Vertriebsmitarbeiter oder ein bestimmtes Jahr enthält. Versuchen Sie, eine benutzerdefinierte URL zu erstellen. Der Bericht wird gefiltert, wenn Empfänger ihn erstmalig öffnen. Sie können den Filter entfernen, indem Sie die URL ändern.

## <a name="filter-and-share-a-report"></a>Filtern und Freigeben eines Berichts

1. Öffnen Sie den Bericht in der [Bearbeitungsansicht](consumer/end-user-reading-view.md), wenden Sie den Filter an, und speichern Sie den Bericht.
   
   In diesem Beispiel wird das [Analysebeispiel für den Einzelhandel](sample-tutorial-connect-to-the-samples.md) so gefiltert, dass nur Werte angezeigt werden, in denen **Territory** gleich **NC** ist.
   
   ![Berichtsfilterbereich](media/service-share-reports/power-bi-filter-report2.png)
2. Fügen Sie am Ende der Berichtsseiten-URL Folgendes hinzu:
   
   ?filter=*Tabellenname*/*Feldname* eq *Wert*
   
    Das Feld muss vom Typ **Zeichenfolge** sein. Die Werte *TableName* oder *FieldName* dürfen keine Leerzeichen enthalten.
   
   In diesem Beispiel lautet der Name der Tabelle **Store**, das Feld hat den Namen **Territory**, und der Wert, nach dem gefiltert werden soll, lautet **NC**:
   
    ?filter=Store/Territory eq 'NC'
   
   ![URL für gefilterten Bericht](media/service-share-reports/power-bi-filter-url3.png)
   
   Durch den Browser werden Sonderzeichen hinzugefügt, die Schrägstriche, Leerzeichen und Apostrophe darstellen, sodass die URL schließlich wie folgt lautet:
   
   app.powerbi.com/groups/me/reports/010ae9ad-a9ab-4904-a7a1-xxxxxxxxxxxx/ReportSection2?filter=Store%252FTerritory%20eq%20%27NC%27

3. [Teilen Sie den Bericht](service-share-dashboards.md), aber deaktivieren Sie das Kontrollkästchen **Send email notification to recipients** (E-Mail-Benachrichtigungen an Empfänger senden). 

    ![Dialogfeld „Bericht freigeben“](media/service-share-reports/power-bi-share-report-dialog.png)

4. Senden Sie den Link mit dem zuvor erstellten Filter.

## <a name="next-steps"></a>Nächste Schritte
* Feedback? Anregungen nehmen wir auf der [Power BI-Communitywebsite](https://community.powerbi.com/) entgegen.
* [Wie kann ich Dashboards und Berichte freigeben?](service-how-to-collaborate-distribute-dashboards-reports.md)
* [Freigeben eines Dashboards](service-share-dashboards.md)
* Weitere Fragen? [Wenden Sie sich an die Power BI-Community](http://community.powerbi.com/).

