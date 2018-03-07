---
title: Beheben von Problemen beim Importieren von Access- und XLS-Dateien in Power BI Desktop
description: Beheben von Problemen beim Importieren von Access-Datenbanken und XLS-Tabellen in Power BI Desktop und Power Query
services: powerbi
documentationcenter: 
author: davidiseminger
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
ms.author: davidi
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 97c3cdf1a7ba47f60cd78e9f424ba7af550f1527
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/24/2018
---
# <a name="resolve-issues-importing-access-and-xls-files-in-power-bi-desktop"></a>Beheben von Problemen beim Importieren von Access- und XLS-Dateien in Power BI Desktop
In **Power BI Desktop** verwenden sowohl **Access-Datenbanken** als auch frühe Versionen von **Excel-Arbeitsmappen** (XLS-Dateien vom Typ Excel 2003 bis 2007) das *Access-Datenbankmodul*. Es gibt drei häufige Situationen, die dazu führen können, dass das Access-Datenbankmodul nicht ordnungsgemäß funktioniert:

### <a name="situation-1-no-access-database-engine-installed"></a>Situation 1: Es ist kein Access-Datenbankmodul installiert
Wenn die Power BI Desktop-Fehlermeldung angibt, dass das Access-Datenbankmodul nicht installiert ist, müssen Sie die Version des Access-Datenbankmoduls (entweder 32-Bit oder 64-Bit) installieren, die Ihrer Version von Power BI Desktop entspricht. Sie können das Access-Datenbankmodul [hier](http://www.microsoft.com/en-us/download/details.aspx?id=13255) installieren.

>[!NOTE]
>Wenn sich die Bitversion des installierten Access-Datenbankmoduls von der Bitversion Ihrer Microsoft Office-Installation unterscheidet, können Office-Anwendungen das Access-Datenbankmodul nicht verwenden.

### <a name="situation-2-the-access-database-engine-bit-version-32-bit-or-64-bit-is-different-from-your-power-bi-desktop-bit-version"></a>Situation 2: Die Bitversion des Access-Datenbankmoduls (32-Bit oder 64-Bit) unterscheidet sich von Ihrer Power BI Desktop-Bitversion
Diese Situation tritt häufig auf, wenn es sich bei der installierten Version von Microsoft Office um eine 32-Bit-Version und bei Power BI Desktop um eine 64-Bit-Version handelt. Das gleiche Problem kann auch im umgekehrten Fall auftreten, sodass nicht übereinstimmende Bit-Versionen in jedem Fall problematisch sind. (Wenn Sie ein Office 365-Abonnement verwenden, kann ein anderes Problem auftreten. Unter **Situation 3** finden Sie die entsprechende Lösung.) Der Fehler durch nicht übereinstimmende Bit-Versionen kann mithilfe jeder dieser Lösungen behoben werden:

1. Ändern Sie die Power BI Desktop-Version, sodass diese mit der Bitversion Ihrer Microsoft Office-Installation übereinstimmt. Um die Bitversion von Power BI Desktop zu ändern, deinstallieren Sie Power BI Desktop, und installieren Sie anschließend die Version von Power BI Desktop, die Ihrer Office-Installation entspricht. Zum Auswählen einer Version von Power BI Desktop wählen Sie auf der Downloadseite für Power BI Desktop **Erweiterte Downloadoptionen**aus.
   
   ![](media/desktop-access-database-errors/desktop-access-errors-1.png)
   
   Wählen Sie auf der daraufhin angezeigten Downloadseite Ihre Sprache aus, und wählen Sie dann die Schaltfläche **Herunterladen** aus. Aktivieren Sie auf dem daraufhin angezeigten Bildschirm das Kontrollkästchen neben „PBIDesktop.msi“ für die 32-Bit-Version oder neben „PBIDesktop_x64.msi“ für die 64-Bit-Version. Im folgenden Bildschirm ist die 64-Bit-Version ausgewählt.
   
   ![](media/desktop-access-database-errors/desktop-access-errors-2.png)
   
   >[!NOTE]
   >Wenn Sie mit der 32-Bit-Version von Power BI Desktop sehr große Datenmodelle erstellen, können Probleme auftreten, weil nicht genügend Arbeitsspeicher vorhanden ist.
2. Ändern Sie die Microsoft Office-Version, sodass diese mit der Bitversion Ihrer Power BI Desktop-Installation übereinstimmt. Um die Bitversion von Microsoft Office zu ändern, deinstallieren Sie Microsoft Office, und installieren Sie anschließend die Office-Version, die Ihrer Power BI Desktop-Installation entspricht.
3. Wenn der Fehler beim Öffnen einer XLS-Datei (einer Excel 2003 bis 2007-Arbeitsmappe) auftritt, können Sie die Verwendung des Access-Datenbankmoduls vermeiden, indem Sie die XLS-Datei in Excel öffnen und als XLSX-Datei speichern.
4. Wenn die vorherigen drei Lösungen nicht möglich sind, können Sie beide Versionen des Access-Datenbankmoduls installieren. Dies wird jedoch *nicht* als Problemumgehung empfohlen. Das Installieren beider Versionen löst dieses Problem für Power Query für Excel und Power BI Desktop, führt jedoch zu Fehlern und Problemen bei Anwendungen, die automatisch (standardmäßig) die zuerst installierte Bitversion des Access-Datenbankmoduls verwenden. Um beide Bitversionen des Access-Datenbankmoduls zu installieren, [laden Sie beide Versionen herunter](http://www.microsoft.com/en-us/download/details.aspx?id=13255), und führen Sie beide mithilfe des Schalters */passive* aus. Beispiel:
   
       c:\users\joe\downloads\AccessDatabaseEngine.exe /passive
   
       c:\users\joe\downloads\AccessDatabaseEngine_x64.exe /passive

### <a name="situation-3-trouble-using-access-or-xls-files-with-an-office-365-subscription"></a>Situation 3: Probleme mit Access- oder XLS-Dateien bei einem Office 365-Abonnement
Wenn Sie ein Office 365-Abonnement wie **Office 2013** oder **Office 2016** verwenden, wird der Anbieter des Access-Datenbankmoduls an einem virtuellen Registrierungsstandort registriert, auf den *ausschließlich* Office-Prozesse zugreifen können. Da es kein Office-Prozess ist, kann das Mashup-Modul (führt Power BI Desktop sowie Excel-Versionen aus, die nicht Teil von Office 365 sind) den Anbieter des Access-Datenbankmoduls nicht verwenden.

Um das Problem zu lösen, können Sie die Redistributable des Access-Datenbankmoduls, die der Bit-Version Ihrer Power BI Desktop-Installation entspricht, herunterladen und installieren (zu Bit-Versionen siehe die Abschnitte oben).

Downloadlink: [Access-Datenbankmodul](http://www.microsoft.com/en-us/download/details.aspx?id=13255)

### <a name="other-situations-that-cause-import-issues"></a>Weitere für den Import problematische Situationen
Wir sind bemüht, im Zusammenhang mit Access- und XLS-Dateien auftretende Probleme möglichst umfassend darzustellen. Wenn ein Problem auftritt, das in diesem Artikel nicht behandelt wird, können Sie sich mit entsprechenden Fragen gerne an den [Power BI-Support](https://powerbi.microsoft.com/support/) wenden. Wir erweitern unsere Artikel regelmäßig um Lösungen für Probleme, die viele Kunden betreffen.

