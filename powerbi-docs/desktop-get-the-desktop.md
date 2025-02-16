---
title: Power BI Desktop erwerben
description: Herunterladen und Installieren von Power BI Desktop
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/08/2019
ms.author: davidi
LocalizationGroup: Get started
ms.openlocfilehash: 5e5d143c21ad726e7cdb8a4bc99903238916bb64
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2019
ms.locfileid: "65454531"
---
# <a name="get-power-bi-desktop"></a>Power BI Desktop erwerben
In **Power BI Desktop** können Sie erweiterte Abfragen, Modelle und Berichte erstellen, die Daten visualisieren. Mit **Power BI Desktop** können Sie Datenmodelle entwerfen, Berichte erstellen und Ihre Arbeit durch die Veröffentlichung im Power BI-Dienst freigeben.  **Power BI Desktop** steht als kostenloser Download zur Verfügung.

Sie können **Power BI Desktop** auf zwei Arten erhalten, von denen jede in den folgenden Abschnitten beschrieben wird:

* Direktes **Herunterladen** (ein MSI-Paket, das Sie herunterladen und auf dem Computer installieren)
* Installation als App aus dem **Microsoft Store**

Mit beiden Methoden erhalten Sie auf Ihrem Computer die neueste Version von **Power BI Desktop**. Es sind jedoch einige Unterschiede zu beachten, die in den folgenden Abschnitten beschrieben werden.

## <a name="download-power-bi-desktop"></a>Laden Sie Power BI Desktop herunter
Um die neueste Version von **Power BI Desktop** herunterzuladen, können Sie im Power BI-Dienst rechts oben auf das Downloadsymbol klicken und **Power BI Desktop** auswählen.

![](media/desktop-get-the-desktop/getpbid_downloads.png)

Sie können die neueste Version von Power BI Desktop auch von dieser Downloadseite herunterladen:

* [**Power BI Desktop-Download** (32-Bit und 64-Bit-Version)](https://powerbi.microsoft.com/desktop).
  
  [![](media/service-admin-power-bi-security/PBI_Security_01.png)](https://powerbi.microsoft.com/desktop)

Unabhängig von der ausgewählten Downloadoption werden Sie nach dem Download von **Power BI Desktop** zum Ausführen der Installationsdatei aufgefordert:

![](media/desktop-get-the-desktop/getpbid_3.png)

**Power BI Desktop** wird als Anwendung installiert und auf dem Desktop ausgeführt.

![](media/desktop-get-the-desktop/designer_gsg_install.png)

> [!NOTE]
> Das Installieren der heruntergeladenen Version (MSI-Paket) von **Power BI Desktop** und der Version aus dem **Microsoft Store** auf demselben Computer (auch als *parallele Installation* bezeichnet) wird nicht unterstützt.
> 
> 

## <a name="install-as-an-app-from-the-microsoft-store"></a>Installation als App aus dem Microsoft Store
Sie können **Power BI Desktop** auch über den folgenden Link aus dem Microsoft Store herunterladen:

* [Installation von **Power BI Desktop** über den **Microsoft Store**](http://aka.ms/pbidesktopstore)

![](media/desktop-get-the-desktop/getpbid_04.png)

Das Installieren von **Power BI Desktop** aus dem Microsoft Store bietet einige Vorteile:

* **Automatische Updates** – Windows lädt automatisch im Hintergrund die aktuelle Version herunter, sobald sie verfügbar ist, sodass Ihre Version immer auf dem neuesten Stand ist.
* **Kleinere Downloads**: Durch den **Microsoft Store** wird sichergestellt, dass in den einzelnen Updates nur geänderte Komponenten auf Ihren Computer heruntergeladen werden, was zu kleineren Downloads für jedes Update führt.
* **Keine Administratorberechtigung erforderlich** – Wenn Sie die MSI-Datei direkt herunterladen und installieren, müssen Sie Administrator sein, damit die Installation erfolgreich abgeschlossen wird. Wenn Sie **Power BI Desktop** aus dem Microsoft Store abrufen, ist *keine* Administratorberechtigung erforderlich.
* **Rollout durch IT möglich**: Die **Microsoft Store**-Version lässt sich leichter für alle Benutzer in der Organisation bereitstellen (per *Rollout*), und **Power BI Desktop** kann über den **Microsoft Store für Unternehmen** verfügbar gemacht werden.
* **Spracherkennung**: Die **Microsoft Store**-Version umfasst alle unterstützten Sprachen und überprüft bei jedem Start, welche Sprachen auf dem Computer verwendet werden. Dies wirkt sich auch auf die Lokalisierung von Modellen aus, die in **Power BI Desktop** erstellt werden. Beispielsweise entsprechen integrierte Datumshierarchien der Sprache, die in **Power BI Desktop** beim Erstellen der PBIX-Datei verwendet wurde.

Für die Installation von **Power BI Desktop** aus dem Microsoft Store gelten einige Einschränkungen und Hinweise, darunter die folgenden:

* Wenn Sie den SAP-Connector verwenden, müssen Sie möglicherweise die SAP-Treiberdateien in den Ordner *Windows\System32* verschieben.
* Beim Installieren von **Power BI Desktop** aus dem Microsoft Store werden keine Benutzereinstellungen aus der MSI-Version kopiert. Sie müssen möglicherweise eine neue Verbindung mit Ihren aktuellen Datenquellen herstellen und die Anmeldeinformationen für Ihre Datenquellen neu eingeben. 

> [!NOTE]
> Das Installieren der heruntergeladenen Version (MSI-Paket) von **Power BI Desktop** und der Version aus dem **Microsoft Store** auf demselben Computer (auch als *parallele Installation* bezeichnet) wird nicht unterstützt. Sie müssen **Power BI Desktop** manuell deinstallieren, bevor Sie den Download aus dem **Microsoft Store** starten.
> 
> [!NOTE]
> Die Power BI-Berichtsserver-Version von **Power BI Desktop** ist eine eigene Installation und unterscheidet sich von den in diesem Artikel behandelten Versionen. Informationen über die Berichtsserver-Version von **Power BI Desktop** finden Sie im Artikel [Erstellen eines Power BI-Berichts für Power BI-Berichtsserver](report-server/quickstart-create-powerbi-report.md).
> 
> 

## <a name="using-power-bi-desktop"></a>Verwenden von Power BI Desktop
Wenn Sie **Power BI Desktop** starten, wird ein*Willkommensbildschirm* angezeigt.

![](media/desktop-get-the-desktop/getpbid_05.png)

Wenn Sie **Power BI Desktop** zum ersten Mal verwenden (und die Installation kein Upgrade ist), werden Sie aufgefordert, ein Formular auszufüllen und einige Fragen zu beantworten, oder Sie müssen sich beim **Power BI-Dienst** anmelden, damit Sie fortfahren können.

Von dort aus können Sie damit beginnen, Datenmodelle oder Berichte zu erstellen und diese im Power BI-Dienst mit anderen Personen zu teilen. Über die Link **Weitere Informationen** am Ende dieses Artikels gelangen Sie zu weiteren Artikeln, die Ihnen bei Ihren ersten Schritten mit **Power BI Desktop** Unterstützung bieten.

## <a name="minimum-requirements"></a>Mindestanforderungen
Die folgende Liste zeigt die Mindestanforderungen zur Ausführung von **Power BI Desktop**:

* Windows 7/Windows Server 2008 R2 oder höher
* .NET 4.5
* Internet Explorer 9 oder höher
* **Arbeitsspeicher (RAM):** Mindestens 1 GB freier Arbeitsspeicher, 1,5 GB oder mehr empfohlen.
* **Bildschirm:** Mindestens 1440 × 900 oder 1600 × 900 (16:9) empfohlen. Geringere Auflösungen, z. B. 1024 x 768 oder 1280 x 800, werden nicht empfohlen, da zum Anzeigen bestimmter Steuerelemente (z. B. das Schließen des Startbildschirms) eine höhere Auflösung erforderlich ist.
* **Windows-Anzeigeeinstellungen:** Wenn Ihre Anzeigeeinstellungen so konfiguriert sind, dass die Größe von Text, Apps und anderen Elementen auf mehr als 100 % geändert wird, sind einige Dialogfelder möglicherweise nicht sichtbar, die zum Fortsetzen der Arbeit in **Power BI Desktop** geschlossen oder bearbeitet werden müssen. Wenn dieses Problem auftritt, überprüfen Sie Ihre **Anzeigeeinstellungen**; wählen Sie dazu in Windows **Einstellungen > System > Anzeige** aus, und setzen Sie die Anzeigeeinstellungen mithilfe des Schiebereglers auf 100 % zurück.
* **CPU:** x86- oder x64-Prozessor mit 1 Gigahertz (GHz) oder schneller empfohlen.

## <a name="considerations-and-limitations"></a>Überlegungen und Einschränkungen

Wir möchten, dass Sie nur die besten Erfahrungen mit Power BI Desktop machen. Sollte einmal ein Problem mit Power BI Desktop auftreten, finden Sie in diesem Abschnitt Lösungen oder Vorschläge, wie sich diese Probleme beheben lassen. 

### <a name="issues-when-using-previous-releases-of-power-bi-desktop"></a>Probleme bei der Verwendung von früheren Versionen von Power BI Desktop

Bei einigen Benutzern tritt ein Fehler auf, der dem folgenden ähnelt, wenn sie eine veraltete Version von **Power BI Desktop** verwenden: 

    "We weren't able to restore the saved database to the model" 

In der Regel können Sie dieses Problem beheben, indem Sie Power BI Desktop auf die aktuelle Version aktualisieren.

### <a name="disabling-notifications"></a>Deaktivieren von Benachrichtigungen
Es empfiehlt sich, ein Update auf die neueste Version von Power BI Desktop auszuführen, um von neuen Features, Verbesserungen bei Leistung und Stabilität sowie weiteren Vorteilen zu profitieren. In einigen Organisationen ist es aber möglicherweise nicht erwünscht, dass Benutzer bei jeder neuen Version ein Update ausführen. Sie können Benachrichtigungen deaktivieren, indem Sie mithilfe der folgenden Schritte die Registrierung ändern:

1. Navigieren Sie im Registrierungs-Editor zu *HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft Power BI Desktop*.
2. Erstellen Sie dort einen neuen Eintrag mit den folgenden Einstellungen: *REG_DWORD: DisableUpdateNotification*
3. Legen Sie den Wert dieses neuen Eintrags auf **1** fest.

Sie müssen den Computer neu starten, damit die Änderung wirksam wird.

### <a name="power-bi-desktop-loads-with-a-partial-screen"></a>Power BI Desktop lädt mit einer Teilanzeige

Unter bestimmten Umständen, beispielsweise bei einigen Konfigurationen der Bildschirmauflösung, werden Power BI Desktop-Inhalte nicht vollständig geladen, und stattdessen werden große schwarze Bereiche angezeigt. Dies ist in der Regel die Folge von Betriebssystemupdates, die sich auf die Anzeige von Elementen auswirken, und liegt nicht an der Inhaltsdarstellung durch Power BI Desktop. Dennoch sind solche Bereiche natürlich nicht wünschenswert. Führen Sie daher die folgenden Schritte aus, um dieses Problem zu beheben:

1. Klicken Sie auf die Schaltfläche „Start“, und geben Sie in der angezeigten Leiste das Wort *blurry* (unscharf) ein.
2. Wählen Sie im daraufhin angezeigten Dialogfeld diese Option aus: *Windows das Beheben von unscharfen Apps überlassen*.
3. Starten Sie Power BI Desktop neu.

Dieses Problem wird möglicherweise behoben, nachdem nachfolgende Windows-Updates veröffentlicht werden. 
 

## <a name="next-steps"></a>Nächste Schritte
Nachdem Sie **Power BI Desktop** installiert haben, erhalten Sie in den folgenden Artikeln die nötigen Informationen für einen schnellen Einstieg:

* [Was ist Power BI Desktop?](desktop-what-is-desktop.md)
* [Übersicht zu Abfragen mit Power BI Desktop](desktop-query-overview.md)
* [Datenquellen in Power BI Desktop](desktop-data-sources.md)
* [Verbinden mit Daten in Power BI Desktop](desktop-connect-to-data.md)
* [Strukturieren und Kombinieren von Daten mit Power BI Desktop](desktop-shape-and-combine-data.md)
* [Allgemeine Abfrageaufgaben in Power BI Desktop](desktop-common-query-tasks.md)   

