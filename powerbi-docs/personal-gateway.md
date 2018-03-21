---
title: "Power BI Gateway – Personal"
description: "Power BI Gateway – Personal"
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
LocalizationGroup: Gateways
ms.openlocfilehash: 7a523284bd777d87b7ac42ba7e9ff82ee7bdf623
ms.sourcegitcommit: 4217430c3419046c3a90819c34f133ec7905b6e7
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2018
---
# <a name="power-bi-gateway---personal"></a>Power BI Gateway – Personal
> [!NOTE]
> Es gibt eine neue Version des persönlichen Gateways für Power BI, die als **Lokales Datengateway (persönlicher Modus)** bezeichnet wird. Im folgende Artikel wird die vorherige Version des persönlichen Gateways beschrieben, die als **Power BI Gateway – Personal** bezeichnet und nach dem 31. Juli 2017 eingestellt und funktionsunfähig wird. Informationen über die neue Version des persönlichen Gateways samt deren Installation finden Sie im Artikel [**Lokales Datengateway (persönlicher Modus)**](service-gateway-personal-mode.md).
> 
> 

[Power BI Gateway – Personal](refresh-data.md) fungiert als Brücke für die schnelle und sichere Datenübertragung zwischen dem Power BI-Dienst und lokalen Datenquellen, die **Aktualisieren** unterstützen. Das Ziel dieses Artikels besteht darin, Ihnen ein tiefgreifendes Verständnis für die Funktionsweise des Gateways zu vermitteln und die Frage zu beantworten, ob Sie ein Gateway benötigen. Wir haben ferner ein [nützliches Video](https://www.youtube.com/watch?v=de58vROLqZI) zum Personal Gateway zusammengestellt. 

Es wird als Dienst auf Ihrem Computer installiert und ausgeführt. Als Dienst wird es mit einem Windows-Benutzerkonto ausgeführt, das Sie während der Konfiguration angeben. In manchen Fällen wird das Gateway als Anwendung ausgeführt. Wir gehen dazu später mehr ins Detail.

Wenn Power BI Daten aus einer lokalen Datenquelle aktualisiert, stellt das Gateway sicher, dass Ihr Power BI-Konto die richtigen Berechtigungen zum Verbinden mit der und Abfragen von Daten bei der Datenquelle hat.

Die Datenübertragung zwischen Power BI und dem Gateway ist mithilfe des [Azure Service Bus](http://azure.microsoft.com/documentation/services/service-bus/) geschützt. Der Service Bus erstellt einen sicheren Kanal zwischen dem Power BI-Dienst und Ihrem Computer. Da das Gateway diese sichere Verbindung bereitstellt, besteht normalerweise keine Notwendigkeit, einen Port in der Firewall zu öffnen.

Bevor wir uns dem Gateway im Detail zuwenden, werfen wir einen Blick auf einige Begriffe, die in Power BI eine Rolle spielen:

Ein *Dataset* sind Daten, die aus einer lokalen oder Onlinedatenquelle in den Power BI-Dienst hochgeladen wurden. Sie erstellen ein Dataset, wenn Sie „Daten abrufen“ verwenden, um eine Verbindung mit Daten herzustellen und diese hochzuladen. Datasets werden im Bereich „Mein Arbeitsbereich“ Ihres Power BI-Arbeitsbereichs im Browser angezeigt. Wenn Sie Berichte erstellen und Kacheln an Ihre Dashboards anheften, betrachten Sie Daten aus Ihren Datasets.

Eine *Datenquelle* ist der Ort, von dem die Daten, die Sie in ein Dataset hochladen, tatsächlich stammen. Das kann so ziemlich alles sein; eine Datenbank, ein Excel-Arbeitsblatt, ein Webdienst usw. Mit Excel-Arbeitsmappen können Sie ein einfaches Arbeitsblatt mit Zeilen von Daten erstellen, und das wird dann als Datenquelle angesehen. Sie können in Excel auch Power Query oder Power Pivot verwenden, um Verbindungen mit Datenquellen herzustellen und Daten abzurufen, online oder lokal, alles innerhalb der gleichen Arbeitsmappe. In Power BI Desktop verwenden Sie „Daten abrufen“, um Verbindungen mit lokalen oder Onlinedatenquellen herzustellen und Daten abzufragen.

Das persönliche Gateway wird über das lokale Datengateway installiert. Dieses können Sie über die Seite [Power BI Gateway](https://powerbi.microsoft.com/gateway/) herunterladen.

## <a name="do-i-need-a-gateway"></a>Benötige ich ein Gateway?
Bevor Sie ein Gateway installieren, müssen Sie wissen, ob Sie wirklich ein Gateway benötigen. Das hängt ganz von Ihren Datenquellen ab:

### <a name="on-premises-data-sources"></a>Lokale Datenquellen
Ein Personal Gateway *ist erforderlich*, um Datasets zu aktualisieren, die Daten aus einer unterstützten lokalen Datenquelle in Ihrer Organisation beziehen.

Mit einem Gateway werden JETZT AKTUALISIEREN und ZEITPLANAKTUALISIERUNG für Datasets unterstützt, die aus diesen Quellen hochgeladen wurden:

* Microsoft Excel 2013-Arbeitsmappen (oder höher), in denen Power Query oder Power Pivot verwendet werden, um Verbindungen mit Daten aus einer unterstützten lokalen Datenquelle herzustellen und Daten abzufragen. Alle lokalen Datenquellen, die in Power Query oder Power Pivot unter „Externe Daten abrufen“ angezeigt werden, unterstützen die Aktualisierung, ausgenommen Hadoop-Datei (HDFS) und Microsoft Exchange.
* Microsoft Power BI Desktop-Dateien, in denen „Daten abrufen“ verwendet wird, um Verbindungen mit einer unterstützten lokalen Datenquelle herzustellen und Daten abzufragen. Alle lokalen Datenquellen, die unter „Daten abrufen“ angezeigt werden, unterstützen die Aktualisierung, ausgenommen Hadoop-Datei (HDFS) und Microsoft Exchange.

### <a name="online-data-sources"></a>Onlinedatenquellen
Ein Gateway *ist nur erforderlich*, wenn Sie die [**Web.Page**](https://msdn.microsoft.com/library/mt260924.aspx)-Funktion verwenden. In anderen Fällen ist ein Gateway *nicht erforderlich*, um Datasets zu aktualisieren, die Daten nur aus einer Onlinedatenquelle abrufen.

> [!NOTE]
> Wenn Sie die [**Web.Page**](https://msdn.microsoft.com/library/mt260924.aspx)-Funktion verwenden, benötigen Sie ein Gateway, sofern das Dataset oder der Bericht nach dem 18. November 2016 veröffentlicht wurde.
> 
> 

JETZT AKTUALISIEREN und ZEITPLANAKTUALISIERUNG werden ohne Gateway für Datasets aus den folgenden Quellen unterstützt:

* Inhaltspakete aus Onlinedatenquellen (Inhaltspakete\\Services). Standardmäßig werden Datasets aus Inhaltspaketen automatisch einmal täglich aktualisiert, Sie können sie aber auch manuell aktualisieren oder einen Aktualisierungszeitplan festlegen.
* Microsoft Excel 2013-Arbeitsmappen (oder höher), in denen Power Query oder Power Pivot verwendet werden, um Verbindungen mit Daten aus einer Onlinedatenquelle herzustellen und Daten abzufragen.
* Microsoft Power BI Desktop-Dateien, in denen „Daten abrufen“ verwendet wird, um Verbindungen mit einer Onlinedatenquelle herzustellen und Daten abzufragen.

**Frage:** Was ist in dem Fall, dass meine Excel-Arbeitsmappe oder Power BI Desktop-Datei Daten sowohl aus lokalen als auch aus Onlinedatenquellen abruft?

**Antwort:** Dann *ist* ein Gateway erforderlich. Sie müssen ein Gateway installieren und konfigurieren, um Daten aus Ihren lokalen Datenquellen aktualisieren zu können.

**Frage:** Was ist in dem Fall, dass meine Excel-Arbeitsmappe nur Datenzeilen aufweist, die ich eingegeben habe?**

**Antwort:** Dann ist ein Gateway *nicht* erforderlich. Sie brauchen ein Gateway nur zu installieren und zu konfigurieren, wenn Ihre Arbeitsmappe Power Query oder Power Pivot verwendet, um Daten aus einer unterstützten lokalen Datenquelle abzufragen und in das Datenmodell zu laden

## <a name="setting-up-a-gateway-for-the-first-time"></a>Erstmaliges Einrichten eines Gateways
Der Vorgang zur Ersteinrichtung eines Gateways besteht aus drei Schritten:

1. Herunterladen und Installieren eines Gateways
2. Konfigurieren des Gateways
3. Anmelden bei Datenquellen in Power BI

Sehen wir uns die einzelnen Schritte näher an.

### <a name="download-and-install-a-gateway"></a>Herunterladen und Installieren eines Gateways
> [!NOTE]
> Es gibt eine neue Version von Personal Gateway für Power BI, die als **Lokales Datengateway (persönlicher Modus)** bezeichnet wird. In diesem Artikel wird die vorherige Version des persönlichen Gateways beschrieben, die als **Power BI Gateway – Personal** bezeichnet und nach dem 31. Juli 2017 eingestellt und funktionsunfähig wird. Informationen über die neue Version des persönlichen Gateways samt deren Installation finden Sie im Artikel [**Lokales Datengateway (persönlicher Modus)**](service-gateway-personal-mode.md).
> 
> 

Sie werden aufgefordert, ein Gateway zu installieren, wenn Sie zum ersten Mal für ein unterstütztes Dataset auf JETZT AKTUALISIEREN oder ZEITPLANAKTUALISIERUNG klicken. Klicken Sie alternativ im Menü „Downloads“ auf **Datengateway**, um das Gateway herunterzuladen. Laden Sie [On-premises data gateway](http://go.microsoft.com/fwlink/?LinkID=820925) herunter.

Sie sollten statt **On-premises data gateway** ein **Persönliches Gateway** auswählen, um ein eigenes Gateway zu besitzen.

Die Installation eines Gateways ist nicht anspruchsvoll. Sie wählen einen Speicherort für die Installation aus. Dann lesen Sie die Lizenzvereinbarung und stimmen ihr zu, wie bei jeder anderen Anwendung. Ein paar wichtige Dinge müssen Sie aber wissen. Insbesondere geht es um die Art des Computers, auf dem Sie das Gateway installieren, und den Typ des Kontos, mit dem Sie bei Windows auf diesem Computer angemeldet sind.

> [!NOTE]
> Das Gateway muss auf die Datenquelle zugreifen können. Wenn Ihr persönlicher Computer keine Verbindung mit der Datenquelle herstellen kann, sollten Sie ein [lokales Datengateway](service-gateway-onprem.md) auf einem Computer installieren, der über Zugriff auf die Datenquelle verfügt. Beispiel: Installation von SQL Server auf einem Azure-gehosteten virtuellen Computer (VM). Angenommen, Ihr persönlicher Computer hat keinen Zugriff auf die VM. Sie könnten dann stattdessen ein lokales Datengateway auf der VM installieren und die Datenquelle über den Power BI-Dienst konfigurieren.
> 
> 

### <a name="computer-type"></a>Computertyp
Der Typ des Computers, auf dem Sie das Gateway installieren, ist wichtig.

> [!NOTE]
> Das Personal Gateway wird nur unter 64-Bit-Windows-Betriebssystemen unterstützt.
> 
> 

Auf einem Laptopcomputer – Damit eine geplante Aktualisierung ausgeführt werden kann, muss das Gateway bereit sein und ausgeführt werden. Laptopcomputer sind normalerweise länger heruntergefahren oder im Energiesparmodus, als sie aktiv ausführen. Wenn Sie Ihr Gateway auf einem Laptop installieren, achten Sie darauf, die geplanten Aktualisierungen auf Zeiten festzulegen, zu denen der Laptop ausgeführt wird. Wird er das nicht, wird bis zur nächsten geplanten Aktualisierung kein erneuter Aktualisierungsversuch unternommen.

Auf einem Desktopcomputer – hier gibt es nicht viele Probleme. Achten Sie einfach darauf, dass der Computer und das Gateway zu den geplanten Aktualisierungszeiten bereit sind und ausgeführt werden. Viele Desktopcomputer wechseln in den Energiesparmodus, und dann kann eine geplante Aktualisierung nicht ausgeführt werden.

Nachdem Sie ein Gateway installiert haben, brauchen Sie kein zweites mehr zu installieren. Ein Gateway funktioniert für eine beliebige Anzahl von unterstützten Datasets. Ferner müssen Sie das Gateway nicht auf dem gleichen Computer installieren, von dem Sie Ihre Arbeitsmappen- und Power BI Desktop-Dateien hochladen. Ein Beispiel: Angenommen, Sie haben eine Excel-Arbeitsmappe, die mit einer SQL Server-Datenquelle in Ihrer Organisation verbunden ist. Sie haben „Daten abrufen“ in Power BI verwendet, um die Arbeitsmappe von Ihrem Laptopcomputer hochzuladen. Sie verfügen außerdem über einen Desktopcomputer, der ständig in Betrieb ist, und auf diesem Computer haben Sie ein Gateway installiert und konfiguriert. In Power BI haben Sie sich bei Ihren Datenquellen angemeldet und einen Aktualisierungszeitplan für das Dataset eingerichtet.  Wenn ein geplanter Aktualisierungszeitpunkt erreicht wird, stellt Power BI eine sichere Verbindung mit dem auf Ihrem Desktopcomputer installierten Gateway her. Dieses stellt dann eine sichere Verbindung zu den Datenquellen her, um die Aktualisierungen abzurufen. Für die Aktualisierung findet keine Kommunikation mit der ursprünglichen Arbeitsmappe, die Sie von Ihrem Laptopcomputer hochgeladen haben, statt.

> [!NOTE]
> Sie können Personal- und Enterprise-Gateways auf dem gleichen Computer installieren.
> 
> 

### <a name="windows-account"></a>Windows-Konto
Wenn Sie das Gateway installieren, müssen Sie mit Ihrem Windows-Konto beim Computer angemeldet sein. Die Art der Berechtigung Ihres Windows-Kontos wirkt sich darauf aus, wie das Gateway installiert und unter Windows ausgeführt wird.

Wenn Sie in dieser Weise bei Windows angemeldet sind:

|  | Mit Administratorberechtigungen | Ohne Administratorberechtigungen |
| --- | --- | --- |
| **Power BI Gateway – Personal wird ausgeführt als** |Dienst |Anwendung |
| **Geplante Aktualisierung** |Solange Ihr Computer und der Gatewaydienst ausgeführt werden, müssen Sie zum Zeitpunkt der geplanten Aktualisierung nicht angemeldet sein. |Sie müssen zum Zeitpunkt der geplanten Aktualisierung auf Ihrem Computer angemeldet sein. |
| **Ändern des Windows-Kontokennworts** |Sie müssen Ihr Kennwort im Gatewaydienst ändern. Wenn das Kennwort für das Gateway nicht mehr gültig ist, misslingt die Aktualisierung. |Das Gateway wird stets unter dem Konto und mit dem Kennwort ausgeführt, mit dem Sie derzeit angemeldet sind. Wenn Sie nicht bei Windows angemeldet sind, wird das Gateway nicht ausgeführt, und bei der Aktualisierung tritt ein Fehler auf. |

### <a name="configure-the-gateway"></a>Konfigurieren des Gateways
Wenn der Installations-Assistent abgeschlossen ist, werden Sie aufgefordert, den Konfigurations-Assistenten zu starten. Die Konfiguration eines Gateways ist wirklich keine große Sache. Sie müssen sich über den Assistenten bei Power BI anmelden. Dies ist erforderlich, damit der Assistent im Power BI-Dienst eine Verbindung mit Ihrem Power BI-Konto herstellen kann.

Wenn Sie bei Windows mit einem Konto mit Administratorberechtigungen angemeldet sind, werden Sie aufgefordert, Ihre Windows-Kontoanmeldeinformationen einzugeben. Sie können ein anderes Windows-Konto angeben, aber beachten Sie, dass die Berechtigungen des Kontos bestimmen, wie das Gateway ausgeführt wird. Der Gatewaydienst wird mithilfe dieses Kontos ausgeführt.

### <a name="sign-in-to-data-sources"></a>Anmelden bei Datenquellen
Nach dem Abschließen des Konfigurations-Assistenten, wenn das Gateway betriebsbereit ist und ausgeführt wird, müssen Sie einen Authentifizierungstyp angeben und sich bei jeder der Datenquellen Ihres Datasets anmelden. Führen Sie diesen Schritt in Power BI aus.

![](media/personal-gateway/pg_dataset_settings_signin.png)

Sie brauchen nur einmal einen Authentifizierungstyp anzugeben und sich bei einer Datenquelle anzumelden. Sie melden sich im Abschnitt **Datenquellen verwalten** auf dem Bildschirm „Einstellungen“ eines Datasets an. Wenn Sie mehrere Datenquellen haben, müssen Sie sich bei jeder anmelden. Das Gateway bestimmt abhängig von der Datenquelle einen Standardauthentifizierungstyp. In den meisten Fällen ist das die Windows-Authentifizierung; in einigen Fällen erfordert Ihre Datenquelle jedoch möglicherweise einen anderen Authentifizierungstyp. Wenn Sie sich nicht sicher sind, klären Sie das bei Ihrem Datenquellenadministrator.

## <a name="up-and-running"></a>Betriebsbereit und ausgeführt!
Wenn Ihr Gateway betriebsbereit ist und ausgeführt wird, können Sie für ein Dataset auf der Seite „Einstellungen“ für das Dataset auf ZEITPLANAKTUALISIERUNG klicken.

![](media/personal-gateway/pg_awintsales_settings.png)

Diese Seite zeigt Folgendes an:

1. Aktualisierungsstatus – Zeigt den Erfolg einer Aktualisierung und den nächsten geplanten Aktualisierungszeitpunkt an.
2. **Gateway** – Zeigt an, ob ein Gateway installiert und online ist. Wenn ein Gateway installiert, aber nicht online ist, sind die Einstellungen „Datenquellen verwalten“ und „Aktualisierung planen“ deaktiviert.
3. **Datenquellen verwalten** – Zeigt die Datenquellen an, mit denen das Dataset Verbindungen herstellt. Sie können sich anmelden oder den Authentifizierungstyp ändern. Sie brauchen sich bei jeder Datenquelle nur einmal anzumelden.
4. **Zeitplanaktualisierung** – Hier können Sie die Einstellungen für einen Aktualisierungszeitplan konfigurieren. Wenn das Gateway nicht online ist, sind diese Einstellungen deaktiviert.
5. Benachrichtigungen bei Aktualisierungsfehlern – Diese Option, die standardmäßig aktiviert ist, sendet Ihnen eine E-Mail, wenn bei einer geplanten Aktualisierung ein Fehler auftritt.

## <a name="updating-your-windows-account-password"></a>Aktualisieren Ihres Windows-Kontokennworts
Wenn Sie bei der Installation des Gateways beim Computer mit einem Windows-Konto mit Administratorberechtigungen angemeldet waren, wird das Gateway als Dienst unter dem Windows-Konto ausgeführt, das Sie im Konfigurations-Assistenten angegeben haben. Dabei wird es sich in den meisten Fällen um das Konto handeln, mit dem Sie sich auch bei Ihrem Computer anmelden. Wenn Sie Ihr Windows-Kontokennwort ändern, müssen Sie es auch im Gateway ändern, andernfalls wird der Dienst möglicherweise nicht ausgeführt und bei der Aktualisierung tritt ein Fehler auf. Um Ihr Windows-Kontokennwort für das Gateway zu ändern, wählen Sie auf Ihrer Windows Desktop-Taskleiste oder unter „Apps“ das Personal Gateway-Symbol.

![](media/personal-gateway/pg_programicon.png)

Von hier aus können Sie Ihr Kennwort aktualisieren und den Verbindungsstatus Ihres Gateways überprüfen.

![](media/personal-gateway/pg_credentials.png)

## <a name="ports"></a>Ports
Das Gateway kommuniziert über die ausgehenden Ports TCP 443 (Standardwert), 5671, 5672, 9350 bis 9354.  Das Gateway benötigt keine eingehenden Ports.

| Domänennamen | Ausgehende Ports | Beschreibung |
| --- | --- | --- |
| *.powerbi.com |443 |HTTPS |
| *.analysis.windows.net |443 |HTTPS |
| *.login.windows.net |443 |HTTPS |
| *.servicebus.windows.net |5671-5672 |Advanced Message Queuing Protocol (AMQP) |
| *.servicebus.windows.net |443, 9350-9354 |Listener an Service Bus Relay über TCP (erfordert 443 für Bezug des Access Control-Tokens) |
| *.frontend.clouddatahub.net |443 |HTTPS |
| *.core.windows.net |443 |HTTPS |
| login.microsoftonline.com |443 |HTTPS |
| login.windows.net |443 |HTTPS |

Wenn Sie IP-Adressen in der Positivliste anstelle der Domänen benötigen, können Sie die Liste der Microsoft Azure Datacenter-IP-Bereiche herunterladen und verwenden. [Download](https://www.microsoft.com/download/details.aspx?id=41653)

## <a name="next-steps"></a>Nächste Schritte
[Lokales Datengateway (persönlicher Modus) – die neue Version des Personal Gateway](service-gateway-personal-mode.md)
[Konfigurieren von Proxyeinstellungen für Power BI-Gateways](service-gateway-proxy.md)  
[Power BI Premium](service-premium.md)

Weitere Fragen? [Stellen Sie Ihre Frage in der Power BI-Community.](http://community.powerbi.com/)

