---
title: Archivierter Arbeitsbereich in Power BI
description: Archivierter Arbeitsbereich in Power BI nach dem Verwalten Ihres Office 365-Mandanten
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-admin
ms.topic: conceptual
ms.date: 11/02/2018
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: 8636ec85cb56e87f28a93f9f1f89989ffcc097bb
ms.sourcegitcommit: d20f74d5300197a0930eeb7db586c6a90403aabc
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2018
ms.locfileid: "50973141"
---
# <a name="power-bi-archived-workspace"></a>Archivierter Arbeitsbereich in Power BI

Jeder Benutzer kann sich bei Power BI anmelden und innerhalb weniger Minuten mit der Verwendung des Diensts beginnen.  Möglicherweise beschließt die IT-Abteilung Ihrer Organisation zu einem späteren Zeitpunkt, die Verwaltung von Power BI für die Benutzer in Ihrer Organisation zu übernehmen.  In diesem Fall profitieren Sie von der zentralen Verwaltung der Benutzer und Berechtigungen in Ihrer Organisation. Möglicherweise können Sie sich auch mit dem gleichen Benutzernamen und Kennwort bei Power BI anmelden, den/das Sie für andere Dienste in Ihrer Organisation verwenden.

Alle Inhalte, die Sie erstellt haben, bevor Ihre IT-Abteilung die Verwaltung von Power BI übernommen hat, werden in einen archivierten Arbeitsbereich in Power BI platziert, der über den linken Navigationsbereich von [Power BI](https://app.powerbi.com) zugänglich ist. Sie sollten neue Power BI-Inhalte in Ihrem Arbeitsbereich erstellen, der von der IT-Abteilung Ihrer Organisation verwaltet und gesichert wird.  Der archivierte Arbeitsbereich bleibt bestehen, aber es gibt Einschränkungen für Aktionen, die Sie mit den Inhalten in Ihrem archivierten Arbeitsbereich ausführen können.  Um diese Einschränkungen aufzuheben, müssen Sie durch die IT-Abteilung den Inhalt in Ihrem archivierten Arbeitsbereich zu Ihrem Arbeitsbereich migrieren lassen.

## <a name="restrictions-in-your-archived-workspace"></a>Einschränkungen im archivierten Arbeitsbereich

Power BI löscht keine Inhalte aus Ihrem archivierten Arbeitsbereich. Sie können weiterhin Daten abrufen, Berichte und Dashboards erstellen und Datasets aktualisieren. Vorhandene Benutzer, mit denen Sie Inhalte geteilt haben, können diese Inhalte ebenfalls weiterhin in ihrem archivierten Arbeitsbereich anzeigen. Es gibt jedoch einige Einschränkungen hinsichtlich des Inhalts in Ihrem archivierten Arbeitsbereich:

* **OneDrive for Business**: Sie können keine Daten mehr aus OneDrive for Business für Datasets in Ihrem archivierten Arbeitsbereich abrufen oder aktualisieren.  Wenn Sie versuchen, eine Verbindung mit dieser Quelle herzustellen, erhalten Sie eine Warnung.

* **Freigabe von Dashboards**: Sie können keine Dashboards in Ihrem archivierten Arbeitsbereich für andere Benutzer freigeben.  Alle Benutzer, die bereits über Zugriff verfügen, können weiterhin freigegebene Dashboards anzeigen, indem sie auf ihren archivierten Arbeitsbereich zugreifen.

* **Erstellen von Gruppen**: Sie können keine Gruppen in Ihrem archivierten Arbeitsbereich erstellen.

* **Zugriff auf mobile Power BI-Apps**: Sie können zwar weiterhin Inhalte im Web in Ihrem archivierten Arbeitsbereich anzeigen, jedoch werden diese Inhalte in den mobilen Power BI-Apps nicht mehr angezeigt.

## <a name="migrating-content-in-your-archived-workspace"></a>Migrieren von Inhalten in Ihrem archivierten Arbeitsbereich

Um Power BI weiterhin zu nutzen, sollten Sie neue Inhalte in Ihrem Arbeitsbereich erstellen. Außerdem sollten Sie die Migration aller Inhalte in Ihrem archivierten Arbeitsbereich zu Ihrem Arbeitsbereich planen.  Die Art und Weise der Migration hängt von der Art der Inhalte ab:

* **Excel- oder Power BI Desktop-Datasets**: Zum Migrieren dieser Datasets wechseln Sie von Ihrem archivierten Arbeitsbereich in Ihren Arbeitsbereich und laden die Excel- oder Power BI-Desktop-Datei erneut hoch, indem Sie auf die Schaltfläche **Meine Daten** klicken.  Wenn Sie eine planmäßige Aktualisierung eingerichtet haben, müssen Sie diese Einstellungen für das neue Dataset in Ihrem Arbeitsbereich neu konfigurieren.

* **Weitere Datasets**: Wechseln Sie zu Ihrem Arbeitsbereich, und klicken Sie dann auf die Schaltfläche **Daten abrufen**, um eine erneute Verbindung mit allen weiteren Datasets herzustellen, die Sie in Ihrem archivierten Arbeitsbereich erstellt haben.  Möglicherweise müssen Sie Sicherheits- oder Verbindungsinformationen erneut eingeben.

* **Berichte**: Berichte in Excel- oder Power BI Desktop-Dateien werden automatisch neu erstellt, sobald Sie die entsprechende Excel- oder Power BI Desktop-Datei erneut hochladen. Berichte, die im Rahmen eines Inhaltspakets installiert wurden, werden ebenfalls neu erstellt, wenn Sie erneut eine Verbindung mit dem Inhaltspaket herstellen. Wenn Sie Ihre eigenen Berichte über den Power BI-Dienst erstellt haben, erstellen Sie diese Berichte in Ihrem Arbeitsbereich neu.

* **Dashboards**: Dashboards, die als im Rahmen von Inhaltspaketen installiert wurden, werden automatisch neu erstellt, wenn Sie erneut eine Verbindung zum Inhaltspaket in Ihrem Arbeitsbereich herstellen. Wenn Sie Ihre eigenen Dashboards über den Power BI-Dienst erstellt haben, erstellen Sie diese Dashboards in Ihrem Arbeitsbereich neu.

Weitere Fragen? [Stellen Sie Ihre Frage in der Power BI-Community.](http://community.powerbi.com/)

