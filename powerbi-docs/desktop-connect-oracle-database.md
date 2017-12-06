---
title: Herstellen einer Verbindung mit einer Oracle-Datenbank
description: Erforderliche Schritte und Downloads zum Verbinden von Oracle mit Power BI Desktop
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
ms.date: 12/06/2017
ms.author: davidi
ms.openlocfilehash: 462f4eb939ce34368afe9f4a247166a55b554e24
ms.sourcegitcommit: d91436de68a0e833ecff18d976de9d9431bc4121
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/06/2017
---
# <a name="connect-to-an-oracle-database"></a>Herstellen einer Verbindung mit einer Oracle-Datenbank
Um über **Power BI Desktop** eine Verbindung mit einer Oracle-Datenbank herzustellen, muss auf dem Computer, auf dem Power BI Desktop ausgeführt wird, die richtigen Oracle-Clientsoftware installiert sein. Welche Oracle-Clientsoftware Sie verwenden, hängt davon ab, ob Sie für Power BI Desktop die **32-Bit**-Version oder die **64-Bit**-Version installiert haben.

**Unterstützte Versionen**: Oracle 9 und höher, Oracle-Clientsoftware Version 8.1.7 und höher.

## <a name="determining-which-version-of-power-bi-desktop-is-installed"></a>Ermitteln der installierten Version von Power BI Desktop
Um zu bestimmen, welche Version von Power BI Desktop installiert ist, wählen Sie **Datei > Info** und überprüfen die Zeile **Version**. In der folgenden Abbildung ist eine 64-Bit-Version von Power BI Desktop installiert:

![](media/desktop-connect-oracle-database/connect-oracle-database_1.png)

## <a name="installing-the-oracle-client"></a>Installieren des Oracle-Clients
Verwenden Sie für **32-Bit**-Versionen von Power BI Desktop den folgenden Link, um den **32-Bit**-Oracle-Client herunterzuladen und zu installieren:

* [32-Bit-Oracle Data Access Components (ODAC) mit Oracle Developer Tools für Visual Studio (12.1.0.2.4)](http://www.oracle.com/technetwork/topics/dotnet/utilsoft-086879.html)

Verwenden Sie für **64-Bit**-Versionen von Power BI Desktop den folgenden Link, um den **64-Bit**-Oracle-Client herunterzuladen und zu installieren:

* [64-Bit-ODAC 12c-Version 4 (12.1.0.2.4) für Windows x64](http://www.oracle.com/technetwork/database/windows/downloads/index-090165.html)

## <a name="connect-to-an-oracle-database"></a>Herstellen einer Verbindung mit einer Oracle-Datenbank
Nachdem der entsprechende Oracle-Clienttreiber installiert wurde, können Sie eine Verbindung mit einer Oracle-Datenbank herstellen. Gehen Sie wie folgt vor, um die Verbindung herzustellen.

1. Wählen Sie im Fenster „Daten abrufen“ die Befehlsfolge **Datenbank > Oracle-Datenbank**.
   
   ![](media/desktop-connect-oracle-database/connect-oracle-database_2.png)
2. Geben Sie im daraufhin angezeigten Dialogfeld **Oracle-Datenbank** den Namen des Servers ein, und wählen Sie **Verbinden**. Wenn eine SID erforderlich ist, können Sie als zu verwendendes Format *Servername/SID* festlegen.
   
   ![](media/desktop-connect-oracle-database/connect-oracle-database_3.png)
3. Wenn Sie Daten mithilfe einer nativen Datenbankabfrage importieren möchten, können Sie Ihre Abfrage in das Feld **SQL-Anweisung** einfügen. Dieses wird angezeigt, wenn Sie im Dialogfeld **Oracle-Datenbank** die **Erweiterten Optionen** einblenden.
   
   ![](media/desktop-connect-oracle-database/connect-oracle-database_4.png)
4. Nachdem Sie die erforderlichen Informationen in das Dialogfeld „Oracle-Datenbank“ eingegeben haben (einschließlich aller optionalen Informationen wie SID oder nativer Datenbankabfrage), wählen Sie **OK**, um die Verbindung herzustellen.
5. Wenn für die Anmeldung bei der Oracle-Datenbank Anmeldeinformationen erforderlich sind, geben Sie diese bei Aufforderung in das Dialogfeld ein.

