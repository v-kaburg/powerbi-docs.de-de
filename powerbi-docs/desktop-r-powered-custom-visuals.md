---
title: "Verwenden von R-gestützten, benutzerdefinierten Visualisierungen in Power BI"
description: "Verwenden von R-gestützten, benutzerdefinierten Visualisierungen in Power BI"
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
ms.date: 09/06/2017
ms.author: davidi
ms.openlocfilehash: 1ab68b945c078e554e7d33914ed447d056a6d190
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2017
---
# <a name="use-r-powered-custom-visuals-in-power-bi"></a>Verwenden von R-gestützten, benutzerdefinierten Visualisierungen in Power BI
In **Power BI Desktop** ab der Version von Oktober 2016 und im **Power BI-Dienst** können Sie R-gestützte, benutzerdefinierte Visualisierungen erstellen, ganz ohne Kenntnisse in R und ohne Skripte in R zu verfassen. Dadurch können Sie die analytischen Möglichkeiten von R-Visualisierungen und R-Skripten nutzen, ohne R erlernen oder in R programmieren zu müssen.

Um R-gestützte, benutzerdefinierte Visualisierungen zu verwenden, wählen Sie die gewünschte benutzerdefinierte R-Visualisierung im Bereich **R-powered visuals** (R-gestützte Visualisierungen) der Power BI-Galerie **Custom visuals** (Benutzerdefinierte visuelle Elemente) aus, und laden Sie diese herunter.

![](media/desktop-r-powered-custom-visuals/powerbi-r-powered-custom-viz_1.png)

In den folgenden Abschnitten wird beschrieben, wie Sie R-gestützte Visualisierungen in **Power BI Desktop** auswählen, laden und verwenden können.

### <a name="using-r-custom-visuals"></a>Verwenden benutzerdefinierter R-Visualisierungen
Um R-gestützte, benutzerdefinierte Visualisierungen zu verwenden, müssen die einzelnen Visualisierungen aus der Bibliothek **Custom visuals** (Benutzerdefinierte visuelle Elemente) heruntergeladen werden. Dann können Sie die Visualisierung wie jede andere in **Power BI Desktop** verwenden. Gehen Sie wie folgt vor:

1. Navigieren Sie zur Bibliothek [Custom visuals](http://app.powerbi.com/visuals) (Benutzerdefinierte visuelle Elemente), die Sie unter [http://app.powerbi.com/visuals](http://app.powerbi.com/visuals) finden. Klicken Sie auf *R-powered visuals* (der Link befindet sich am oberen Rand der Seite).
   
   ![](media/desktop-r-powered-custom-visuals/powerbi-r-powered-custom-viz_2.png)
2. Wählen Sie im Katalog die gewünschte **R-gestützte Visualisierung** aus. Ein Dialogfeld wird geöffnet, in dem Sie weitere Informationen erhalten. Wählen Sie zum Herunterladen **Download Visual** (Visuelles Element herunterladen) aus.
   
   > [!NOTE]
> Für die Erstellung in **Power BI Desktop** muss R auf Ihrem lokalen Rechner installiert sein. Wenn ein Benutzer eine R-gestützte Visualisierung im **Power BI-Dienst** betrachten möchte, ist allerdings *keine* lokale Installation von R erforderlich.
   > 
   > 
   
   ![](media/desktop-r-powered-custom-visuals/powerbi-r-powered-custom-viz_3.png)
   
   Um R-gestützte, benutzerdefinierte Visualisierungen im **Power BI-Dienst** zu verwenden, brauchen Sie R nicht zu installieren. Wenn Sie R-gestützte, benutzerdefinierte Visualisierungen hingegen in **Power BI Desktop** verwenden möchten, *müssen* Sie R auf dem lokalen Computer installieren. Hier können Sie R herunterladen:
   
   * [CRAN 3.3.1](https://cran.r-project.org/bin/windows/base/R-3.3.1-win.exe)
   * [MRO 3.3.1](https://mran.microsoft.com/install/mro/3.3.1/microsoft-r-open-3.3.1.msi)
3. Sobald die Visualisierung (wie jede andere Datei über den Browser) heruntergeladen wurde, wechseln Sie zu **Power BI Desktop**, klicken Sie im Bereich **Visualisierungen** mit der rechten Maustaste auf die Auslassungspunkte (...), und wählen Sie **Benutzerdefiniertes visuelles Element importieren** aus.
   
   ![](media/desktop-r-powered-custom-visuals/powerbi-r-powered-custom-viz_4.png)
4. Sie erhalten eine Warnmeldung zum Importieren benutzerdefinierter Visualisierungen hingewiesen wie in der folgenden Abbildung:
   
   ![](media/desktop-r-powered-custom-visuals/powerbi-r-powered-custom-viz_5.png)
5. Navigieren Sie zum Speicherort der Visualisierungsdatei, und wählen Sie diese aus. In **Power BI Desktop** verfügen benutzerdefinierte Visualisierungen über die Dateierweiterung „.pbiviz“.
   
   ![](media/desktop-r-powered-custom-visuals/powerbi-r-powered-custom-viz_6.png)
6. Wenn Sie zu Power BI Desktop zurückkehren, sehen Sie den neuen Visualtyp im Bereich **Visualisierungen**.
   
   ![](media/desktop-r-powered-custom-visuals/powerbi-r-powered-custom-viz_7.png)
7. Wenn Sie die neue Visualisierung importieren (oder einen Bericht mit einer R-gestützten, benutzerdefinierten Visualisierung öffnen), werden die erforderlichen R-Pakete von **Power BI Desktop** automatisch installiert.
   
   ![](media/desktop-r-powered-custom-visuals/powerbi-r-powered-custom-viz_8.png)

Danach können Sie dieser wie jeder anderen Visualisierung in **Power BI Desktop** Daten hinzufügen. Nach Abschluss des Vorgangs sehen Sie die fertige Visualisierung auf der Zeichenfläche. In der folgenden Visualisierung wurde die R-gestützte Visualisierung **Forecasting** mit Daten aus den UN-Prognosen zur Geburtenrate (linke Visualisierung) verwendet.

![](media/desktop-r-powered-custom-visuals/powerbi-r-powered-custom-viz_10.png)

Wie jede andere Visualisierung in **Power BI Desktop** können Sie diesen R-gestützten visualisierten Bericht im **Power BI-Dienst** veröffentlichen und für andere freigeben.

Es lohnt sich, die Bibliothek mit [R-gestützten, benutzerdefinierten Visualisierungen](https://app.powerbi.com/visuals/R-powered) häufiger zu besuchen, da regelmäßig neue Visualisierungen hinzugefügt werden.

### <a name="contributing-r-powered-custom-visuals"></a>Beisteuern R-gestützter, benutzerdefinierter Visualisierungen
Wenn Sie für Ihre Berichte eigene R-Visualisierungen erstellen, können Sie diese für Benutzer auf der ganzen Welt über den **Katalog mit benutzerdefinierten Visualisierungen** freigeben. Beiträge werden über GitHub eingereicht. Dieser Vorgang wird hier beschrieben:

* [Contributing to the R-powered custom visuals gallery (in englischer Sprache)](https://github.com/Microsoft/PowerBI-visuals#building-r-powered-custom-visual-corrplot)

### <a name="troubleshooting-r-powered-custom-visuals"></a>Problembehandlung für R-gestützte benutzerdefinierte Visualisierungen
R-gestützte benutzerdefinierte Visualisierungen weisen bestimmte Abhängigkeiten auf, die berücksichtigt werden müssen, damit die Visualisierungen ordnungsgemäß ausgeführt werden. Wenn R-gestützte benutzerdefinierte Visualisierungen nicht ordnungsgemäß ausgeführt oder geladen werden, hat das Problem in der Regel eine der folgenden Ursachen:

* Das R-Modul fehlt.
* Fehler im R-Skript, auf dem die Visualisierung basiert.
* R-Pakete fehlen oder sind veraltet.

Im folgenden Abschnitt werden die Schritte beschrieben, mit denen Sie ggf. auftretende Probleme beheben können.

#### <a name="missing-or-outdated-r-packages"></a>Fehlende oder veraltete R-Pakete
Beim Installieren einer R-gestützten benutzerdefinierten Visualisierung können Fehler auftreten, wenn R-Pakete fehlen oder veraltet sind. Dies hat i. d. R. eine der folgenden Ursachen:

* Die R-Installation ist mit dem R-Paket nicht kompatibel.
* Eine Firewall, Antivirensoftware oder Proxyeinstellungen verhindern die Verbindung von R mit dem Internet.
* Die Internetverbindung ist langsam, oder es besteht ein Problem bei der Internetverbindung.

Das Power BI-Team arbeitet daran, diese Probleme zu beheben, bevor sie bei Ihnen auftreten, und die nächste Version von Power BI Desktop enthält Updates zum Beheben dieser Probleme. Bis dahin können Sie einen oder mehrere der folgenden Schritte ausführen, um die Probleme zu entschärfen:

1. Entfernen Sie die benutzerdefinierte Visualisierung, und installieren Sie sie dann erneut. Hierdurch wird eine erneute Installation der R-Pakete initiiert.
2. Wenn die Installation von R nicht aktuell ist, führen Sie ein Upgrade der R-Installation durch. Entfernen Sie dann die benutzerdefinierte Visualisierung, und installieren Sie sie erneut, wie im vorherigen Schritt beschrieben.
   
   * In der Beschreibung jeder R-gestützten benutzerdefinierten Visualisierung werden die unterstützten R-Versionen aufgeführt, wie in der folgenden Abbildung dargestellt.
     ![](media/desktop-r-powered-custom-visuals/powerbi-r-powered-custom-viz_11.png)
     > [!NOTE]
> Sie können die ursprüngliche R-Installation beibehalten und Power BI Desktop lediglich der aktuellen Version zuordnen, die Sie installieren. Wählen Sie **„Datei“ > „Optionen und Einstellungen“ -> „Optionen“ > „R-Skripterstellung“** aus.
3. Installieren Sie R-Pakete mit einer beliebigen R-Konsole manuell. Die Schritte dieser Vorgehensweise lauten wie folgt:
   
   a.  Laden Sie das Installationsskript für die R-gestützte Visualisierung herunter, und speichern Sie die Datei auf einem lokalen Laufwerk.
   
   b.  Führen Sie in der R-Konsole den folgenden Befehl aus:
   
       > source(“C:/Users/david/Downloads/ScriptInstallPackagesForForecastWithWorkarounds.R”)    
   
   Typische Standardinstallationspfade lauten wie folgt:
   
       c:\Program Files\R\R-3.3.x\bin\x64\Rterm.exe (for CRAN-R)
       c:\Program Files\R\R-3.3.x\bin\x64\Rgui.exe (for CRAN-R)
       c:\Program Files\R\R-3.3.x\bin\R.exe (for CRAN-R)
       c:\Program Files\Microsoft\MRO-3.3.x\bin\R.exe (for MRO)
       c:\Program Files\Microsoft\MRO-3.3.x\bin\x64\Rgui.exe (for MRO)
       c:\Program Files\RStudio\bin\rstudio.exe (for RStudio)
4. Wenn das Problem durch die vorherigen Schritte nicht behoben wird, versuchen Sie Folgendes:
   
   a. Verwenden Sie **R Studio**, und führen Sie den oben in 3.b. beschriebenen Schritt aus (die Skriptzeile in der R-Konsole ausführen).
   
   b. Wenn das Problem durch den vorherigen Schritt nicht behoben wird, wählen Sie in **R Studio** die Option **Tools > Global Options > Packages** (Extras > Globale Optionen > Pakete) aus, aktivieren Sie das Kontrollkästchen **Use Internet Explorer library/proxy for HTTP** (Internet Explorer-Bibliothek/-Proxy für HTTP verwenden), und wiederholen Sie dann Schritt 3.b. aus den oben genannten Schritten.

### <a name="next-steps"></a>Nächste Schritte
Betrachten Sie die folgenden zusätzlichen Informationen über R in Power BI.

* [Power BI-Katalog mit benutzerdefinierten Visualisierungen](https://app.powerbi.com/visuals/)
* [Ausführen von R-Skripts in Power BI Desktop](desktop-r-scripts.md)
* [Erstellen von visuellen R-Elementen in Power BI Desktop](desktop-r-visuals.md)
* [Verwenden einer externen R-IDE mit Power BI](desktop-r-ide.md)

