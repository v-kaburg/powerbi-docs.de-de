---
title: Erstellen eines Links zu einer bestimmten Stelle in den mobilen Power BI-Apps
description: Erfahren Sie, wie Sie mit einem URI (Uniform Resource Identifier) einen Deep-Link zu einem bestimmten Dashboard, einer bestimmten Kachel oder einem bestimmten Bericht in der mobilen Power BI-App erstellen.
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-mobile
ms.topic: conceptual
ms.date: 06/28/2018
ms.author: maggies
ms.openlocfilehash: 1f9503980ba19b290fa5d0fd1f521bb85ef93759
ms.sourcegitcommit: 5206651c12f2b91a368f509470b46f3f4c5641e6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/02/2019
ms.locfileid: "53983575"
---
# <a name="create-a-link-to-a-specific-location-in-the-power-bi-mobile-apps"></a>Erstellen eines Links zu einer bestimmten Stelle in den mobilen Power BI-Apps
Sie können einen URI (Uniform Resource Identifier) erstellen und als Link zu einer bestimmten Stelle (*Deep-Link*) in den mobilen Power BI-Apps auf allen Plattformen verwenden: iOS, Android und Windows 10.

URI-Links können direkt auf Dashboards, Kacheln und Berichte verweisen.

Das Ziel des Deep-Links bestimmt das Format des URI. Gehen Sie wie folgt vor, um Deep-Links zu unterschiedlichen Stellen zu erstellen. 

## <a name="open-the-power-bi-mobile-app"></a>Öffnen der mobilen Power BI-App
Verwenden Sie diesen URI zum Öffnen der mobilen Power BI-App auf einem beliebigen Gerät:

    mspbi://app/


## <a name="open-to-a-specific-dashboard"></a>Öffnen in einem bestimmten Dashboard
Mit diesem URI wird die mobile Power BI-App in einem bestimmten Dashboard geöffnet:

    mspbi://app/OpenDashboard?DashboardObjectId=<36-character-dashboard-id>

Um die aus 36 Zeichen bestehende Dashboardobjekt-ID zu suchen, navigieren Sie im Power BI-Dienst (https://powerbi.com) zum betreffenden Dashboard. Der hervorgehobene Abschnitt dieser URL zeigt ein Beispiel:

`https://powerbi.com/groups/me/dashboards/**61b7e871-cb98-48ed-bddc-6572c921e270**`

Wenn sich das Dashboard in einer anderen Gruppe als „Mein Arbeitsbereich“ befindet, fügen Sie `&GroupObjectId=<36-character-group-id>` vor oder nach der Dashboard-ID hinzu. Beispiel: 

mspbi://app/OpenDashboard?DashboardObjectId=e684af3a-9e7f-44ee-b679-b9a1c59b5d60 **&GroupObjectId=8cc900cc-7339-467f-8900-fec82d748248**

Beachten Sie das kaufmännische Und-Zeichen (&) zwischen den beiden IDs.

## <a name="open-to-a-specific-tile-in-focus"></a>Öffnen mit einer bestimmten Kachel im Fokus
Mit diesem URI wird die mobile Power BI-App geöffnet, wobei eine bestimmte Kachel den Fokus hat:

    mspbi://app/OpenTile?DashboardObjectId=<36-character-dashboard-id>&TileObjectId=<36-character-tile-id>

Um die aus 36 Zeichen bestehenden Dashboard- und Kachelobjekt-IDs zu suchen, navigieren Sie im Power BI-Dienst (https://powerbi.com) zum betreffenden Dashboard, und öffnen Sie die Kachel im Fokusmodus. Die hervorgehobenen Abschnitte dieser URL zeigen ein Beispiel:

`https://powerbi.com/groups/me/dashboards/**3784f99f-b460-4d5e-b86c-b6d8f7ec54b7**/tiles/**565f9740-5131-4648-87f2-f79c4cf9c5f5**/infocus`

Für diese Kachel lautet der URI:

    mspbi://app/OpenTile?DashboardObjectId=3784f99f-b460-4d5e-b86c-b6d8f7ec54b7&TileObjectId=565f9740-5131-4648-87f2-f79c4cf9c5f5

Beachten Sie das kaufmännische Und-Zeichen (&) zwischen den beiden IDs.

Wenn sich das Dashboard in einer anderen Gruppe als „Mein Arbeitsbereich“ befindet, fügen Sie `&GroupObjectId=<36-character-group-id>` hinzu.

## <a name="open-to-a-specific-report"></a>Öffnen eines bestimmten Berichts
Mit diesem URI wird ein bestimmter Bericht in der mobilen Power BI-App geöffnet:

    mspbi://app/OpenReport?ReportObjectId=<36-character-report-id>

Um die aus 36 Zeichen bestehende Berichtsobjekt-ID zu suchen, navigieren Sie im Power BI-Dienst (https://powerbi.com) zum betreffenden Bericht. Der hervorgehobene Abschnitt dieser URL zeigt ein Beispiel:

`https://powerbi.com/groups/me/reports/df9f0e94-31df-450b-b97f-4461a7e4d300`

Wenn sich der Bericht in einer anderen Gruppe als „Mein Arbeitsbereich“ befindet, fügen Sie `&GroupObjectId=<36-character-group-id>` vor oder nach der Berichts-ID hinzu. Beispiel: 

mspbi://app/OpenReport?ReportObjectId=e684af3a-9e7f-44ee-b679-b9a1c59b5d60 **&GroupObjectId=8cc900cc-7339-467f-8900-fec82d748248**

Beachten Sie das kaufmännische Und-Zeichen (&) zwischen den beiden IDs.

## <a name="open-to-a-specific-report-page"></a>Öffnen einer bestimmten Berichtsseite
Mit diesem URI wird eine bestimmte Berichtsseite in der mobilen Power BI-App geöffnet:

    mspbi://app/OpenReport?ReportObjectId=<36-character-report-id>&reportPage=ReportSection<number>

Der Name der Berichtsseite lautet „ReportSection“, gefolgt von einer Zahl. Öffnen Sie den Bericht im Power BI-Dienst (https://powerbi.com), und navigieren Sie zu der spezifischen Berichtsseite. 

Der hervorgehobene Abschnitt dieser URL zeigt ein Beispiel:

`https://powerbi.com/groups/me/reports/df9f0e94-31df-450b-b97f-4461a7e4d300/ReportSection11`

## <a name="open-in-full-screen-mode"></a>Öffnen im Vollbildmodus
Fügen Sie den Parameter in Fettschrift hinzu, um einen bestimmten Bericht im Vollbildmodus zu öffnen:

    mspbi://app/OpenReport?ReportObjectId=<36-character-report-id>**&openFullScreen=true**

Beispiel: 

mspbi://app/OpenReport?ReportObjectId=500217de-50f0-4af1-b345-b81027224033&openFullScreen=true

## <a name="add-context-optional"></a>Hinzufügen von Kontext (optional)
Sie können in der Zeichenfolge auch Kontext hinzufügen. Wenn Sie Kontakt zu uns aufnehmen möchten, können wir diesen Kontext verwenden, um unsere Daten für Ihre App zu filtern. Fügen Sie dem Link `&context=<app-name>` hinzu.

Der hervorgehobene Abschnitt dieser URL zeigt ein Beispiel: 

`https://powerbi.com/groups/me/reports/df9f0e94-31df-450b-b97f-4461a7e4d300/&context=SlackDeepLink`

## <a name="next-steps"></a>Nächste Schritte
Ihr Feedback hilft uns zu entscheiden, welche Features wir künftig realisieren. Geben Sie deshalb Ihr Votum ab, welche Features Sie sich in den mobilen Power BI-Apps wünschen. 

* [Power BI-Apps für mobile Geräte](mobile-apps-for-mobile-devices.md)
* Folgen Sie @MSPowerBI auf Twitter
* Werden Sie Teil der [Power BI-Community](http://community.powerbi.com/), um sich mit den Mitgliedern auszutauschen
* [Was ist Power BI?](../../power-bi-overview.md)

