---
title: Erste Schritte mit Power BI-Gateways
description: "Erfahren Sie Grundlegendes zu Datengateways für Power BI."
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
ms.tgt_pltfrm: na
ms.workload: powerbi
ms.date: 09/25/2017
ms.author: davidi
ms.openlocfilehash: 617dcbf1d149966369aa0d1566094f6ce820a40a
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2017
---
# <a name="getting-started-with-power-bi-gateways"></a>Erste Schritte mit Power BI-Gateways
Willkommen beim Handbuch **Erste Schritte mit Power BI-Gateways**. In dieser kurzen exemplarischen Vorgehensweise wird die Funktionsweise von Gateways erläutert und wie Sie ein eigenes Gateway installieren, konfigurieren und ausführen.  

![](media/service-gateway-getting-started/gw_gettingstarted_0a.png)

Das Thema Gateways kann technisch anspruchsvoll sein. Da jedes Netzwerk und jedes Unternehmen unterschiedlich ist, kann die Komplexität von Gateways sehr hoch sein. Um diese Komplexität im Griff zu behalten, beginnen wir nun mit den Grundlagen.

## <a name="how-power-bi-gateways-work"></a>Funktionsweise von Power BI-Gateways
Ein **Gateway** ist eine Software, die den Zugriff auf Daten in einem privaten, lokalen Netzwerk erleichtert, um diese zu einem späteren Zeitpunkt in einem Clouddienst wie Power BI zu verwenden. Es handelt sich dabei um eine Art Torwächter, der Verbindungsanfragen überwacht und diese nur zulässt, wenn die Benutzeranforderung bestimmte Kriterien erfüllt (z.B., ob der Benutzer die Berechtigung zur Verwendung des Gateways hat). Auf diese Weise können Organisationen Datenbanken und Warehouses in ihren lokalen Netzwerken belassen. Dabei können Teilmengen dieser Daten zum Erstellen beeindruckender Berichte und Dashboards in Power BI sicher verwendet werden.

Außerdem sichert ein Gateway den Zugriff sowie Daten durch die Verschlüsselung und Komprimierung sämtlicher Daten, die das Gateway durchlaufen, und alle Kennwörter, die zur Verbindung mit Datenquellen verwendet werden. Das alles klingt recht unkompliziert, aber es müssen zahlreiche Details berücksichtigt werden.

Es kann vorkommen, dass Sie ein Gateway nur für eigene Zwecke verwenden möchten – vielleicht haben Sie eine große Excel-Arbeitsmappe und drei SQL-Datenbanken mit seit Jahren gesammelten Umsatz- und Marketingdaten und möchten ein Power BI-Dashboard erstellen, dass diese Umsätze aus jedem erdenklichen Blickwinkel darstellt. Sie sind der einzige Benutzer, der Berichte erstellt, es ist Ihre Excel-Arbeitsmappe, und nur Sie verwenden diese Datenbanken, um Power BI-Berichte zu erstellen. Ein Gateway benötigen Sie lediglich für den persönlichen Gebrauch, aber nicht, um diese Datenquellen für alle anderen Benutzer freizugeben.

In einem anderen Beispiel arbeiten Sie vielleicht in einer Organisation mit allen Arten von Datenbanken unterschiedlicher Anbieter, z.B. Analysis Services, SAP, Oracle, IBM und verschiedene andere Datenquellen, und viele Personen benötigen den Zugriff darauf, sodass sie zahlreiche Berichte erstellen können. In diesem Fall benötigen Sie ein Gateway, über das Sie den Zugriff auf alle diese Quellen konfigurieren können und das Sie anschließend für viele Benutzer in Ihrer Organisation freigeben müssen. Dabei handelt es sich um ein ganz anderes Gateway als das im vorherigen Beispiel.

Glücklicherweise bietet Power BI zwei Gateways, die jeweils ideal zu diesen Szenarien passen. Diese zwei verfügbaren Power BI-Gateways sind:

* **Lokales Datengateway (persönlicher Modus)**: ermöglicht einem Benutzer die Verbindung mit Datenquellen und kann nicht für andere Benutzer freigegeben werden. Kann nur mit Power BI verwendet werden.
* **Lokales Datengateway**: ermöglicht mehreren Benutzern die Verbindung mit mehreren lokalen Datenquellen und kann mit Power BI, **PowerApps**, Flow und Azure Logic Apps verwendet werden, wobei jeweils eine einzelne Gatewayinstallation verwendet wird.

Beide Gateways haben eine ähnliche Funktion – sie erleichtern den Zugriff auf Daten, die sich in einem privaten lokalen Netzwerk befinden, sodass diese Daten in cloudbasierten Diensten wie Power BI verwendet werden können. Das persönliche Gateway kann von einer Person und nur über Power BI verwendet werden, das **lokale Datengateway** kann von vielen Benutzern und vielen Diensten verwendet werden.

Das Einrichten eines Gateways lässt sich in drei Abschnitte unterteilen:

* Installation des Gateways
* Hinzufügen von Benutzern für das Gateway (die Verwendung des Gateways erlauben)
* Verbinden mit Datenquellen

Darüber hinaus bietet ein Gateway eine weitere Möglichkeit, die wichtig sein kann:

* Aktualisieren von lokalen Daten, sodass Power BI-Berichte mit neuen Daten aktualisiert werden können

Das Aktualisieren von Daten bedeutet, dass Ihre Power BI-Dashboards und -Berichte aktuell sind und die neuesten Daten widerspiegeln. Wenn also jemand einen Bericht betrachtet, den Sie mit lokalen Daten erstellt haben, kann dieser Bericht die neuesten Informationen enthalten, obwohl Sie ihn bereits vor einiger Zeit erstellt haben.

Der erste Teil, die Installation eines Gateways, ist ganz einfach. Benutzern den Zugriff auf das Gateway zu gewähren, ist ebenfalls ganz leicht – Sie fügen sie einfach in einem Power BI-Dialogfeld hinzu, und dann können sie loslegen. Das Herstellen einer Verbindung mit Datenquellen kann komplex sein, da es so viele Datenquellen gibt, die jeweils eigene Verbindungsanforderungen und Details aufweisen. Die Aktualisierung wird in einem anderen Handbuch beschrieben, sodass sich dieser Artikel ausschließlich um das Gateway dreht.

Fangen wir einfach an und sehen uns die einzelnen Schritte zur Gatewayinstallation an.

## <a name="install-the-gateway"></a>Installation des Gateways
Um ein Gateway zu installieren, öffnen Sie den Power BI-Dienst (Sie können diesen Link verwenden, um den Power BI-Dienst im Browser zu öffnen und sich anzumelden), und melden Sie sich bei Ihrem Power BI-Konto an. Wählen Sie im Power BI-Dienst in der oberen rechten Ecke das **Downloadsymbol**  aus, wie in der folgenden Abbildung dargestellt. Wählen Sie dann **Datengateway** aus.

![](media/service-gateway-getting-started/gw_gettingstarted_01.png)

Nun gelangen Sie zu einer Downloadseite, auf der Sie auf die Schaltfläche **Download Gateway** (Gateway herunterladen) klicken, um den Download zu starten.

![](media/service-gateway-getting-started/gw_gettingstarted_02.png)

Auf diesem Bildschirm finden Sie eine knappe Erklärung der Funktionsweise eines Gateways. Darüber hinaus enthält sie einige wichtige **Warnungen**: Wenn Sie ein Gateway installieren, wird dieses auf dem Computer ausgeführt, auf dem Sie die Installation durchführen. Falls dieser Computer ausgeschaltet wird, wird auch das Gateway ausgeschaltet (es funktioniert also nicht, wenn es nicht ausgeführt wird). Außerdem ist die Installation auf einem Computer, der ein Drahtlosnetzwerk verwendet, nicht ideal. Sie sollten daher einen Computer wählen, der über Kabel mit einem Netzwerk verbunden ist.

Wenn Sie bereit sind, wählen Sie **Weiter**, um die Einrichtung fortzusetzen.

![](media/service-gateway-getting-started/gw_gettingstarted_03.png)

An diesem Punkt legen Sie fest, welches Gateway Sie installieren – ein lokales Gateway oder ein persönliches Gateway. In diesem Handbuch wird das **lokales Datengateway** installiert.

Bei dieser Entscheidung gibt es einige Punkte zu beachten:

* Beide Gateways erfordern 64-Bit-Windows-Betriebssysteme.
* Gateways können nicht auf einem Domänencontroller installiert werden.
* Sie können bis zu zwei lokale Datengateways auf demselben Computer installieren, von denen jedes jeweils in einem der einzelnen Modi (persönlich oder Standard) ausgeführt wird. 
* Sie dürfen auf ein und demselben Computer nicht mehrere Gateways im gleichen Modus ausführen.
* Sie können mehrere lokale Gateways auf verschiedenen Computern installieren und alle über dieselbe Power BI Gateway-Verwaltungsschnittstelle verwalten (mit Ausnahme des persönlichen Modus, siehe folgender Aufzählungspunkt).
* Sie können für jeden Power BI-Benutzer nur ein Gateway im persönlichen Modus ausführen. Wenn Sie ein weiteres Gateway im persönlichen Modus für denselben Benutzer installieren (selbst wenn dies auf einem anderen Computer geschieht), ersetzt die neueste Installation die vorhandene vorherige Installation.

Sobald Sie **Weiter** auswählen, beginnt die Installation des Gateways. Sie müssen den Installationsort angeben. In der Regel ist der Standardspeicherort am besten geeignet.

![](media/service-gateway-getting-started/gw_gettingstarted_06.png)

Der Installationsvorgang geht schnell voran, und es wird eine Statusleiste angezeigt.

![](media/service-gateway-getting-started/gw_gettingstarted_06a.png)

Kurz vor Abschluss des Vorgangs müssen Sie das Konto angeben, das mit dem Gateway verwendet werden soll. Dies sollte das Konto (Benutzername und Kennwort) sein, mit dem Sie sich bei Power BI anmelden. Das Gateway wird mit Ihrem Power BI-Konto verknüpft, und Sie konfigurieren Gateways im Power BI-Dienst.

![](media/service-gateway-getting-started/gw_gettingstarted_07.png)

Sie werden angemeldet, wie in der folgenden Abbildung dargestellt.

![](media/service-gateway-getting-started/gw_gettingstarted_08.png)

Sobald Sie angemeldet sind, müssen Sie einen **Wiederherstellungsschlüssel** erstellen. Dies wird in einem anderen Artikel ausführlicher erläutert. Vorerst sollten Sie wissen, dass Sie diesen Schlüssel benötigen, um das Gateway wiederherzustellen oder zu verschieben.

![](media/service-gateway-getting-started/gw_gettingstarted_09.png)

Bei einer erfolgreichen Installation wird ein Fenster geöffnet, in dem Ihnen mitgeteilt wird, dass Ihr Gateway einsatzbereit ist.

![](media/service-gateway-getting-started/gw_gettingstarted_10.png)

Damit ist die Installation eines lokalen Gateways abgeschlossen. Wie angekündigt, war dieser Vorgang ziemlich einfach. Der nächste Schritt ist dann entweder das **Hinzufügen von Benutzern** oder das **Hinzufügen von Datenquellen**. Sie können jeden dieser Schritte zuerst ausführen bzw. nach der Erstkonfiguration hinzufügen.

Im nächsten Abschnitt wird beschrieben, wie Sie dem Gateway Benutzer hinzufügen. Danach wird erläutert, wie Sie dem Gateway Datenquellen hinzufügen.

## <a name="add-users-to-a-gateway"></a>Hinzufügen von Benutzern zu einem Gateway
Nachdem das Gateway installiert ist, wird es über den **Power BI-Dienst** verwaltet. Um das Verwaltungsfenster für Gateways zu öffnen, wählen Sie im Power BI-Dienst das Zahnradsymbol in der oberen rechten Ecke aus, und wählen Sie dann **Gateways verwalten** aus.

![](media/service-gateway-getting-started/gw_gettingstarted_15.png)

Im Power BI-Dienstbereich wird eine Seite angezeigt, auf der Sie Ihre Gateways verwalten können. Die Seite **Gatewayeinstellungen** sieht wie folgt aus.

![](media/service-gateway-getting-started/gw_gettingstarted_12.png)

Wenn Sie auf **Administratoren** tippen oder klicken, wird die folgende Verwaltungsseite für Administratoren angezeigt. Beachten Sie, dass Sie hier nur die Benutzer finden, die das Gateway *verwalten* können. Die Benutzer des Gateways werden für jede einzelne Datenquelle auf einer anderen Seite hinzugefügt (oder entfernt). Dies wird im nächsten Abschnitt beschrieben.

![](media/service-gateway-getting-started/gw_gettingstarted_13.png)

Nachdem Sie eine Datenquelle installiert und überprüft (erfolgreich eine Verbindung hergestellt) haben, wird diese auf der linken Seite des Fensters **Gateways verwalten** unter dem zugeordneten Gateway aufgeführt, wie in der folgenden Abbildung gezeigt. Beachten Sie, dass Sie im rechten Bereich zwischen zwei Abschnitten wechseln können: **Datenquelleneinstellungen** und **Benutzer**. Der unmittelbar folgende Bildschirm ist der Abschnitt **Datenquelleneinstellungen**.

![](media/service-gateway-getting-started/gw_gettingstarted_16.png)

Bei der Auswahl von **Benutzer** können Sie in einem Textfeld Benutzer aus Ihrer Organisation eingeben, denen der Zugriff auf die ausgewählte Datenquelle gewährt werden soll. Im folgenden Bildschirm sehen Sie, dass ich Maggie und Adam hinzugefügt haben.

Wenn Sie beginnen, eine E-Mail-Adresse in das Textfeld einzugeben, zeigt Power BI eine Liste der Benutzer an, deren E-Mail-Adresse mit Ihrer Eingabe übereinstimmt. Sie können dann auf den Namen klicken und ihn der Liste hinzufügen.

Neben Einzelpersonen können Sie auch E-Mail-Gruppen (Aliase) hinzufügen, um Benutzergruppen Zugriff zu gewähren.

![](media/service-gateway-getting-started/gw_gettingstarted_17.png)

Nachdem Sie **Hinzufügen** ausgewählt haben, werden die hinzugefügten Mitglieder im Feld angezeigt, und Sie können bei Bedarf weitere hinzufügen. Das Entfernen von Benutzern ist genauso einfach. Aktivieren Sie einfach das Kontrollkästchen neben dem Namen, und wählen Sie dann die Schaltfläche **Entfernen** unterhalb des Felds aus.

![](media/service-gateway-getting-started/gw_gettingstarted_18.png)

Das war schon alles. Denken Sie daran, dass Sie jeder Datenquelle, für die Sie den Zugriff gewähren möchten, Benutzer hinzufügen müssen. Jede Datenquelle verfügt über eine eigene Liste von Benutzern, und Sie müssen jeder Datenquelle separat Benutzer hinzufügen.

## <a name="adding-data-sources"></a>Hinzufügen von Datenquellen
Damit Ihr Gateway seinen Zweck erfüllt, sollten Sie natürlich Datenquellen hinzufügen. Hier tritt zum Teil die Komplexität von Power BI-Gateways zutage – es sind viele unterschiedliche Datenquellen verfügbar, und jede hat eigene Anforderungen (und erfordert häufig einen eigenen Treiber).

Aber bevor Sie mit einem weiteren Artikel fortfahren, folgt hier ein Überblick über das Hinzufügen einer Datenquelle. Wählen Sie auf der Seite **Gateways verwalten** des **Power BI-Diensts** das Gateway aus, dem Sie eine Datenquelle hinzufügen möchten. Wählen Sie dann in der oberen linken Ecke der Seite über der Liste der Gateways **Datenquelle hinzufügen** aus.

Anschließend wird auf der rechten Seite der Bereich **Datenquelleneinstellungen** angezeigt, wie in der folgenden Abbildung dargestellt. Dort können Sie der Datenquelle einen Namen zuweisen (den Sie im Textfeld **Datenquellenname** eingeben), und den Typ in der Dropdownliste **Datenquellentyp** auswählen.

![](media/service-gateway-getting-started/gw_gettingstarted_14.png)

Sie haben jetzt ein Gateway installiert und können Datenquellen hinzufügen. Sehr gut! Weitere Informationen zu Datenquellen, mehr Details zur Verwendung von Gateways und andere nützliche Informationen finden Sie in den Ressourcen im folgenden Abschnitt.

## <a name="next-steps"></a>Nächste Schritte
[Verwenden des lokalen Gateways](service-gateway-onprem.md)  
[Ausführliche Informationen zum lokalen Datengateway](service-gateway-onprem-indepth.md)  
[Lokales Datengateway (persönlicher Modus)](service-gateway-personal-mode.md)

[Lokales Datengateway – Problembehandlung](service-gateway-onprem-tshoot.md)  
Weitere Fragen? [Wenden Sie sich an die Power BI-Community](http://community.powerbi.com/)

