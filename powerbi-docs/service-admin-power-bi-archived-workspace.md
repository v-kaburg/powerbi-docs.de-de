---
title: Archivierter Arbeitsbereich in Power BI
description: "Archivierter Arbeitsbereich in Power BI nach dem Verwalten Ihres Office 365-Mandanten"
services: powerbi
documentationcenter: 
author: markingmyname
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
ms.date: 06/28/2017
ms.author: maghan
ms.openlocfilehash: 7698a1207f19382430fb8e225543b32b6aebcd49
ms.sourcegitcommit: 6e693f9caf98385a2c45890cd0fbf2403f0dbb8a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2018
---
# <a name="power-bi-archived-workspace"></a>Archivierter Arbeitsbereich in Power BI
Jeder Benutzer kann sich bei Power BI anmelden und innerhalb weniger Minuten mit der Verwendung des Diensts beginnen.  Möglicherweise entscheidet die IT-Abteilung Ihrer Organisation zu einem späteren Zeitpunkt, die Verwaltung von Power BI für Benutzer in Ihrer Organisation zu übernehmen.  Wenn dies geschieht, profitieren Sie von der zentralen Verwaltung von Benutzern und Berechtigungen in Ihrer Organisation und können eine vereinfachte Anmeldung mit dem gleichen Benutzernamen und Kennwort nutzen, das Sie für andere Dienste in Ihrer Organisation verwenden. 

Alle Inhalte, die Sie erstellt haben, bevor Ihre IT-Abteilung die Verwaltung von Power BI übernommen hat, werden in einen archivierten Arbeitsbereich in Power BI platziert, der über den linken Navigationsbereich von [Power BI](https://app.powerbi.com) zugänglich ist.  Sie sollten neue Power BI-Inhalte in Ihrem Arbeitsbereich erstellen, der von der IT-Abteilung Ihrer Organisation verwaltet und gesichert wird.  Der archivierte Arbeitsbereich bleibt bestehen, aber es gibt Einschränkungen für Aktionen, die Sie mit den Inhalten in Ihrem archivierten Arbeitsbereich ausführen können.  Um diese Einschränkungen zu entfernen, müssen Sie durch die IT-Abteilung den Inhalt in Ihrem archivierten Arbeitsbereich zu Ihrem Arbeitsbereich migrieren lassen.

## <a name="restrictions-in-your-archived-workspace"></a>Einschränkungen im archivierten Arbeitsbereich
Aus dem archivierten Arbeitsbereich werden keine Inhalte gelöscht.  Sie können weiterhin Daten abrufen, Berichte und Dashboards erstellen und Datasets aktualisieren.  Vorhandene Benutzer, mit denen Sie Inhalte geteilt haben, können diese Inhalte ebenfalls weiterhin in ihrem archivierten Arbeitsbereich anzeigen.

Es gibt jedoch einige Einschränkungen hinsichtlich des Inhalts in Ihrem archivierten Arbeitsbereich:

* **OneDrive for Business.**  Sie können keine Daten mehr aus OneDrive for Business für Datasets in Ihrem archivierten Arbeitsbereich abrufen oder aktualisieren.  Wenn Sie versuchen, eine Verbindung zu dieser Quelle herzustellen, erhalten Sie eine Warnung.
* **Freigeben von Dashboards.**  Sie können keine Dashboards in Ihrem archivierten Arbeitsbereich für andere Benutzer freigeben.  Alle Benutzer, die bereits über Zugriff verfügen, können weiterhin freigegebene Dashboards anzeigen, indem sie auf ihren archivierten Arbeitsbereich zugreifen.
* **Erstellen von Gruppen.**  Sie können keine Gruppen in Ihrem archivierten Arbeitsbereich erstellen.
* **Zugriff auf Power BI-Mobile Apps**  Sie können in Ihrem archivierten Arbeitsbereich zwar weiterhin Inhalte im Web anzeigen, diese werden jedoch in den mobilen Power BI-Apps nicht mehr angezeigt.

## <a name="migrating-content-in-your-archived-workspace"></a>Migrieren von Inhalten in Ihrem archivierten Arbeitsbereich
Um Power BI weiterhin zu verwenden, sollten Sie durch die IT-Abteilung neue Inhalte in Ihrem Arbeitsbereich erstellen lassen.   Außerdem sollten Sie die Migration aller Inhalte aus Ihrem archivierten Arbeitsbereich zu Ihrem Arbeitsbereich planen.  Die Art und Weise der Migration hängt von der Art der Inhalte ab:

* **Excel- oder Power BI Desktop-Datasets.**  Zum Migrieren dieser Datasets wechseln Sie von Ihrem archivierten Arbeitsbereich in Ihren aktuellen Arbeitsbereich und laden Sie erneut die Excel- oder Power BI Desktop-Datei hoch, indem Sie auf die Schaltfläche „Meine Daten“ klicken.  Wenn Sie eine planmäßige Aktualisierung eingerichtet haben, müssen Sie diese Einstellungen für das neue Dataset im Arbeitsbereich neu konfigurieren.
* **Weitere Datasets.**  Wechseln Sie zu Ihrem Arbeitsbereich, und klicken Sie auf die Schaltfläche „Daten abrufen“, um eine erneute Verbindung mit allen weiteren Datasets herzustellen, die Sie in Ihrem archivierten Arbeitsbereich erstellt haben.  Möglicherweise müssen Sie Sicherheits- oder Verbindungsinformationen erneut eingeben.
* **Berichte.**  Berichte, die in Excel- oder Power BI Desktop-Dateien oder -Berichten enthalten waren, und als Teil des Inhaltspakets installiert wurden, werden automatisch neu erstellt, sobald Sie die entsprechende Excel- oder Power BI Desktop-Datei erneut hochladen, oder eine erneute Verbindung mit dem Inhaltspaket herstellen.  Wenn Sie Ihre eigenen Berichte über den Power BI-Dienst erstellt haben, müssen Sie diese Berichte in Ihrem Arbeitsbereich neu erstellen.
* **Dashboards.**  Dashboards, die als Teil des Inhaltspakets installiert wurden, werden automatisch neu erstellt, wenn Sie eine erneute Verbindung mit dem Inhaltspaket in Ihrem Arbeitsbereich herstellen.  Wenn Sie Ihre eigenen Dashboards über den Power BI-Dienst erstellt haben, müssen Sie diese Dashboards in Ihrem Arbeitsbereich neu erstellen.

Weitere Fragen? [Stellen Sie Ihre Frage in der Power BI-Community.](http://community.powerbi.com/)

