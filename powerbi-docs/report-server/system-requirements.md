---
title: Hardware- und Softwareanforderungen für die Installation von Power BI-Berichtsserver
description: Hier finden Sie die Mindestanforderungen an die Hardware und Software zum Installieren und Ausführen von Power BI-Berichtsserver.
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-report-server
ms.topic: conceptual
ms.date: 11/01/2017
ms.author: maghan
ms.openlocfilehash: 2963dbe2a5d1109e4396568624e16bf49d98da10
ms.sourcegitcommit: 638de55f996d177063561b36d95c8c71ea7af3ed
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/17/2018
---
# <a name="hardware-and-software-requirements-for-installing-power-bi-report-server"></a>Hardware- und Softwareanforderungen für die Installation von Power BI-Berichtsserver
Hier finden Sie die Mindestanforderungen an die Hardware und Software zum Installieren und Ausführen von Power BI-Berichtsserver.

## <a name="processor-memory-and-operating-system-requirements"></a>Prozessor-, Arbeitsspeicher- und Betriebssystemanforderungen
| Komponente | Anforderung |
| --- | --- |
| .NET Framework |4.6<br><br>Über [Microsoft .NET Framework 4.6 (Webinstaller) für Windows](http://support.microsoft.com/kb/3045560) können Sie .NET Framework manuell installieren.<br/><br/> Weitere Informationen, Empfehlungen und Anleitungen zu .NET Framework 4.6 finden Sie im [Handbuch für die Bereitstellung von .NET Framework für Entwickler](http://msdn.microsoft.com/library/ee942965\(v=vs.110\).aspx).<br/><br/>Windows 8.1 und Windows Server 2012 R2 erfordern die Installation von [KB2919355](http://support.microsoft.com/kb/2919355) vor der Installation von .NET Framework 4.6. |
| Festplatte |Power BI-Berichtsserver erfordert mindestens 1 GB verfügbaren Speicherplatz auf der Festplatte.<br><br>Außerdem ist zusätzlicher Speicherplatz auf dem Datenbankserver erforderlich, der die Berichtsserver-Datenbank hostet. |
| Arbeitsspeicher |**Minimum:** 1GB<br/><br/> **Empfohlen:** Mindestens 4 GB |
| Prozessorgeschwindigkeit |**Minimum:** x64-Prozessor, 1,4 GHz<br/><br/> **Empfohlen:** 2,0 GHz oder schneller |
| Prozessortyp |x64-Prozessor: AMD Opteron, AMD Athlon 64, Intel Xeon mit Intel EM64T-Unterstützung, Intel Pentium IV mit EM64T-Unterstützung |
| Betriebssystem |Windows Server 2016 Datacenter<br><br>Windows Server 2016 Standard<br><br>Windows Server 2012 R2 Datacenter<br><br>Windows Server 2012 R2 Standard<br><br>Windows Server 2012 R2 Essentials<br><br>Windows Server 2012 R2 Foundation<br><br>Windows Server 2012 Datacenter<br><br>Windows Server 2012 Standard<br><br>Windows Server 2012 Essentials<br><br>Windows Server 2012 Foundation<br><br>Windows 10 Home<br><br>Windows 10 Professional<br><br>Windows 10 Enterprise<br><br>Windows 8.1<br><br>Windows 8.1 Pro<br><br>Windows 8.1 Enterprise<br><br>Windows 8<br><br>Windows 8 Pro<br><br>Windows 8 Enterprise |

> [!NOTE]
> Die Installation von Power BI-Berichtsserver wird nur für x64-Prozessoren unterstützt.
> 
> 

## <a name="database-server-version-requirements"></a>Anforderungen an die Version des Datenbankservers
Als Host der Berichtsserver-Datenbanken wird SQL Server verwendet. Die Instanz der SQL Server-Datenbank-Engine kann eine lokale oder Remoteinstanz sein. Die folgenden unterstützten Versionen der SQL Server-Datenbank-Engine können als Host der Berichtsserver-Datenbanken verwendet werden:

* SQL Server 2017
* SQL Server 2016
* SQL Server 2014
* SQL Server 2012
* SQL Server 2008 R2
* SQL Server 2008

Zum Erstellen der Berichtsserver-Datenbank auf einem Remotecomputer müssen Sie die Verbindung für die Verwendung eines Domänenbenutzerkontos oder Dienstkontos konfigurieren, das Netzwerkzugriff hat. Wenn Sie eine Remoteinstanz von SQL Server verwenden möchten, sollten Sie sorgfältig überlegen, welche Anmeldeinformationen der Berichtsserver zum Herstellen der Verbindung mit der SQL Server-Instanz verwenden soll. Weitere Informationen finden Sie unter [Konfigurieren einer Verbindung mit der Berichtsserver-Datenbank](https://docs.microsoft.com/sql/reporting-services/install-windows/configure-a-report-server-database-connection-ssrs-configuration-manager).

## <a name="considerations"></a>Überlegungen
Power BI-Berichtsserver installiert Standardwerte zum Konfigurieren der Haupteinstellungen, die für die Inbetriebnahme eines Berichtsservers erforderlich sind. Es gelten die folgenden Anforderungen:

* Eine SQL Server-Datenbank-Engine muss nach dem Setup und vor der Konfiguration der Datenbank für den Berichtsserver verfügbar sein. Die Instanz der Datenbank-Engine hostet die Berichtsserver-Datenbank, die der Konfigurations-Manager für Reporting Services erstellt. Die Datenbank-Engine ist für das eigentliche Setup nicht erforderlich.
* Das Benutzerkonto zum Ausführen von Setup muss Mitglied der lokalen Gruppe „Administratoren“ sein.
* Das Benutzerkonto für den Konfigurations-Manager für Reporting Services benötigen die Berechtigung für den Zugriff auf und das Erstellen von Datenbanken in der Instanz der Datenbank-Engine, die die Berichtsserver-Datenbanken hostet.
* Setup muss die Standardwerte verwenden können, um die URLs zu reservieren, die Zugriff auf den Berichtsserver und das Webportal gewähren. Zu diesen Werten gehören Port 80, ein Platzhalter und Namen der virtuellen Verzeichnisse im Format **ReportServer** und **Reports**.

## <a name="read-only-domain-controller-rodc"></a>Schreibgeschützter Domänencontroller (RODC)
 Wenngleich der Berichtsserver in einer Umgebung mit einem schreibgeschützten Domänencontroller (RODC) installiert werden kann, benötigt Reporting Services Zugriff auf einen Domänencontroller mit Lese-/Schreibzugriff, um ordnungsgemäß zu funktionieren. Wenn Reporting Services nur auf einen RODC zugreifen kann, können beim Versuch, den Dienst zu verwalten, Fehler auftreten.

## <a name="power-bi-reports-and-analysis-services-live-connections"></a>Power BI-Berichte und Analysis Services-Liveverbindungen
Sie können eine Liveverbindung für tabellarische oder mehrdimensionale Instanzen verwenden. Ihr Server mit Analysis Services benötigt die richtige Version und Edition, um ordnungsgemäß zu funktionieren.

| **Serverversion** | **Erforderliche SKU** |
| --- | --- |
| 2012 SP1 CU4 oder höher |Business Intelligence und Enterprise SKU |
| 2014 |Business Intelligence und Enterprise SKU |
| 2016 und höher |Standard-SKU oder höher |

## <a name="next-steps"></a>Nächste Schritte
[Benutzerhandbuch](user-handbook-overview.md)  
[Administratorhandbuch](admin-handbook-overview.md)  
[Installieren von Power BI-Berichtsserver](install-report-server.md)  
[Installieren des Berichts-Generators](https://docs.microsoft.com/sql/reporting-services/install-windows/install-report-builder)  
[Herunterladen der SQL Server Data Tools](http://go.microsoft.com/fwlink/?LinkID=616714)

Weitere Fragen? [Stellen Sie Ihre Frage in der Power BI-Community.](https://community.powerbi.com/)

