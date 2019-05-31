---
title: Filtern eines Berichts, und teilen Sie es mit Kollegen – Power BI
description: Erfahren Sie, wie Sie einen Power BI-Bericht für Kollegen in Ihrer Organisation filtern und freigeben.
author: maggiesMSFT
manager: kfile
ms.reviewer: lukaszp
featuredvideoid: 0tUwn8DHo3s
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 04/24/2019
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: 5f3808884e63521ec1dd775d876f1cf707bbe56b
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2019
ms.locfileid: "64770682"
---
# <a name="filter-a-power-bi-report-and-share-it-with-coworkers"></a>Filtern eines Power BI-Berichts und für Kollegen freigeben
*Freigeben* ist eine gute Möglichkeit, einigen Personen Zugriff auf Ihre Dashboards und Berichte zu gewähren. Wie gehen Sie vor, wenn Sie eine gefilterte Version eines Berichts freigeben möchten? Dabei handelt es sich möglicherweise um einen Bericht, der nur Daten für einen bestimmten Ort, einen bestimmten Vertriebsmitarbeiter oder ein bestimmtes Jahr enthält. Versuchen Sie es Filtern eines Berichts freigeben, und erstellen eine benutzerdefinierte URL. Der Bericht wird gefiltert, wenn Empfänger ihn erstmalig öffnen. Sie können den Filter entfernen, indem Sie die URL ändern. 

Zudem bietet Power BI [verschiedene Möglichkeiten zum gemeinsamen Bearbeiten und Verteilen Ihrer Berichte](service-how-to-collaborate-distribute-dashboards-reports.md). Zum Freigeben benötigen Sie und die Empfänger eine [Power BI Pro-Lizenz](service-features-license-type.md), oder es muss sich um Inhalte in einer [Premium-Kapazität](service-premium-what-is.md) handeln. 

## <a name="two-ways-to-filter-a-report"></a>Zwei Möglichkeiten zum Filtern eines Berichts

### <a name="set-a-filter"></a>Legen Sie einen filter

Öffnen Sie den Bericht in der [Bearbeitungsansicht](consumer/end-user-reading-view.md), wenden Sie den Filter an, und speichern Sie den Bericht.
   
In diesem Beispiel wird das [Analysebeispiel für den Einzelhandel](sample-tutorial-connect-to-the-samples.md) so gefiltert, dass nur Werte angezeigt werden, in denen **Territory** gleich **NC** ist.
   
![Berichtsfilterbereich](media/service-share-reports/power-bi-filter-report2.png)

### <a name="create-a-filter-in-the-url"></a>Erstellen Sie einen Filter in der URL

Fügen Sie am Ende der Berichtsseiten-URL Folgendes hinzu:
   
?filter=*Tabellenname*/*Feldname* eq *Wert*
   
Das Feld muss vom Zahl vom Typ Datetime oder Zeichenfolge sein. Die Werte *TableName* oder *FieldName* dürfen keine Leerzeichen enthalten.
   
In diesem Beispiel lautet der Name der Tabelle **Store**, das Feld hat den Namen **Territory**, und der Wert, nach dem gefiltert werden soll, lautet **NC**:
   
?filter=Store/Territory eq 'NC'
   
![URL für gefilterten Bericht](media/service-share-reports/power-bi-filter-url3.png)
   
Durch den Browser werden Sonderzeichen hinzugefügt, die Schrägstriche, Leerzeichen und Apostrophe darstellen, sodass die URL schließlich wie folgt lautet:
   
app.powerbi.com/groups/me/reports/010ae9ad-a9ab-4904-a7a1-xxxxxxxxxxxx/ReportSection2?filter=Store%252FTerritory%20eq%20%27NC%27

Finden Sie im Artikel [Filtern eines Berichts mithilfe von Abfragezeichenfolgen-Parameter in der URL](service-url-filters.md) für sehr detailliert behandeln.

## <a name="share-the-filtered-report"></a>Die gefilterten Bericht freigeben

1. Wenn Sie [freigegebenen](service-share-dashboards.md)Deaktivieren der **-e-Mail-Benachrichtigung an Empfänger senden** Kontrollkästchen.

    ![Dialogfeld „Bericht freigeben“](media/service-share-reports/power-bi-share-report-dialog.png)

4. Senden Sie den Link mit dem zuvor erstellten Filter.

## <a name="next-steps"></a>Nächste Schritte
* Feedback? Anregungen nehmen wir auf der [Power BI-Communitywebsite](https://community.powerbi.com/) entgegen.
* [Wie kann ich Dashboards und Berichte freigeben?](service-how-to-collaborate-distribute-dashboards-reports.md)
* [Freigeben eines Dashboards](service-share-dashboards.md)
* Weitere Fragen? [Wenden Sie sich an die Power BI-Community](http://community.powerbi.com/).

