---
title: Problembehandlung für Kachelfehler
description: Häufig in Power BI auftretende Fehler bei der Aktualisierung einer Kachel
author: mgblythe
manager: kfile
ms.reviewer: kayu
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 12/06/2018
ms.author: mblythe
LocalizationGroup: Troubleshooting
ms.openlocfilehash: c1df7e6293db703922f37c3f28546bb296d1a46a
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2019
ms.locfileid: "66050995"
---
# <a name="troubleshooting-tile-errors"></a>Problembehandlung für Kachelfehler
Im Folgenden sind häufige Fehler, die Ihnen möglicherweise in Verbindung mit Kacheln begegnen, gemeinsam mit den entsprechenden Erklärungen aufgeführt.

> [!NOTE]
> Falls bei Ihnen ein Fehler auftritt, der hier nicht aufgelistet ist, und Ihnen Probleme verursacht, können Sie auf der [Communitywebsite](http://community.powerbi.com/) um Hilfe bitten oder ein [Support-Ticket](https://powerbi.microsoft.com/support/) erstellen.
> 
> 

## <a name="errors"></a>Fehler
**Unerwarteter Fehler bei Power BI beim Laden des Modells. Versuchen Sie es später erneut.**
Oder: **Das Datenmodell konnte nicht abgerufen werden. Wenden Sie sich an den Besitzer des Dashboards, um sicherzustellen, dass die Datenquellen und das Modell vorhanden sind und der Zugriff auf sie möglich ist.**

Es konnte nicht auf Ihre Daten zugegriffen werden, da die Datenquelle nicht erreichbar war. Dieses Problem kann auftreten, wenn die Datenquelle entfernt, umbenannt, verschoben oder offline geschaltet bzw. wenn ihre Berechtigungen geändert wurden. Überprüfen Sie, ob sich die Quelle noch an dem verwiesenen Speicherort befindet und ob Sie darauf zugreifen können. Wenn dies nicht die Ursache des Problems ist, liegt es möglicherweise an einer langsamen Quelle. Versuchen Sie es zu einem Zeitpunkt erneut, wenn die Auslastung der Quelle geringer ist. Wenn es sich um eine lokale Quelle handelt, erhalten Sie vom Datenquellenbesitzer möglicherweise weitere Informationen.

**Sie haben keine Berechtigung zum Anzeigen dieser Kachel oder zum Öffnen der Arbeitsmappe.**

Wenden Sie sich an den Besitzer des Dashboards, um sicherzustellen, dass die Datenquellen und das Modell vorhanden sind und Sie über Ihr Konto darauf zugreifen können.

**Benutzerdefinierte Visuals wurden durch Ihren Administrator deaktiviert.**

Ihr Power BI-Administrator hat die Nutzung benutzerdefinierter Visuals für Ihre Organisation oder Ihre Sicherheitsgruppe deaktiviert. Sie können keine benutzerdefinierten Visuals von [Microsoft Marketplace](https://appsource.microsoft.com/en-us/marketplace/apps?page=1&product=power-bi-visuals) verwenden und keine privaten Visuals aus einer Datei importieren. Sie können nur die vorgegebenen Visuals verwenden.


**Die Daten-Shapes müssen mindestens eine Gruppe oder Berechnung enthalten, die Daten ausgibt. Wenden Sie sich an den Besitzer des Dashboards.**

Es stehen keine Daten zur Anzeige zur Verfügung, da die Abfrage leer ist. Versuchen Sie, Ihrer Visualisierung einige Felder aus der Feldliste hinzuzufügen, und heften Sie sie erneut an.

**Die Daten können nicht angezeigt werden, da Power BI die Beziehung zwischen zwei oder mehr Feldern nicht bestimmen kann.**

Sie versuchen, zwei oder mehr Felder aus Tabellen zu verwenden, die nicht verknüpft sind. Sie müssen die nicht verknüpften Felder aus der Visualisierung und eine Beziehung zwischen den Tabellen erstellen. Anschließend können Sie die Felder wieder zum Visual hinzufügen. Dies kann in Power BI Desktop oder Power Pivot für Excel erfolgen. [Weitere Informationen](desktop-create-and-manage-relationships.md)

**Die Gruppen auf der Primärachse und der Sekundärachse überschneiden sich. Die Gruppen auf der Primärachse können nicht die gleichen Schlüssel wie die Gruppen auf der Sekundärachse aufweisen.**

Dies ist normalerweise ein vorübergehendes Problem. Es tritt i. d. R. auf, wenn Sie Gruppen von Zeilen in Spalten verschieben. In diesem Fall sollte der Fehler nicht mehr angezeigt werden, wenn Sie alle Gruppen verschoben haben. Wenn die Meldung weiterhin angezeigt wird, wechseln Sie zwischen Zeilen und Spalten bzw. der Achsenlegende, oder entfernen Sie Felder aus der Visualisierung.  

**Diese Visualisierung überschreitet die verfügbaren Ressourcen. Versuchen Sie, einen Filter anzuwenden, um die angezeigten Daten zu reduzieren.**

Ihre Visualisierung hat versucht, zu viele Daten abzufragen, sodass die Abfrage nicht mit den verfügbaren Ressourcen abgeschlossen werden konnte. Versuchen Sie, die Visualisierung zu filtern, um die Datenmenge im Ergebnis zu reduzieren.

**Die folgenden Felder können nicht identifiziert werden: {0}. Aktualisieren Sie die Visualisierung mit Feldern, die im Dataset vorhanden sind.**

Das Feld wurde möglicherweise gelöscht oder umbenannt. Entfernen Sie das fehlerhafte Feld aus der Visualisierung, fügen Sie ein anderes Feld hinzu, und heften Sie sie erneut an.

**Die Daten für diese Visualisierung konnten nicht abgerufen werden. Versuchen Sie es später erneut.**

Dies ist normalerweise ein vorübergehendes Problem. Wenn Sie es später erneut versuchen und diese Meldung weiterhin angezeigt wird, wenden Sie sich an den Support.

**Kacheln weiterhin ungefilterte Daten angezeigt wird, nachdem Sie die einmalige Anmeldung (SSO) aktivieren.**

Dies kann vorkommen, wenn das zugrunde liegende Dataset für die Verwendung von DirectQuery-Modus oder einer Liveverbindung mit Analysis Services über ein lokales datengateway konfiguriert ist. In diesem Fall weiterhin die Kacheln zeigen die ungefilterten Daten nach dem Aktivieren von SSO für die Datenquelle, bis der nächsten Aktualisierung der dashboardkachel fällig ist. Bei der nächsten Aktualisierung der Kachel "verwendet Power BI-SSO-Konfiguration, und die Kacheln zeigen die Daten, die entsprechend der Benutzeridentität gefiltert. 

Wenn Sie die gefilterten Daten sofort sehen möchten, können Sie eine kachelaktualisierung erzwingen, indem Sie auf die Auslassungspunkte (...) in der oberen rechten Ecke des ein Dashboard und **dashboardkacheln aktualisieren**.

Außerdem können Sie als Besitzer eines Datasets Ändern der aktualisierungshäufigkeit der Kachel und legen Sie es auf 15 Minuten, um die Aktualisierung der dashboardkachel zu beschleunigen. Wählen Sie das Zahnradsymbol in der Ecke des Power BI-Dienst, und wählen Sie dann **Einstellungen**. Auf der **Einstellungen** Seite die **Datasets** Registerkarte. Erweitern Sie **geplante cacheaktualisierung** , und ändern Sie **Aktualisierungshäufigkeit**. Stellen Sie sicher, dass Sie die Konfiguration auf die ursprünglichen aktualisierungshäufigkeit zurücksetzen, nach Power BI mit der nächsten Aktualisierung der dashboardkachel führt.

> [!NOTE]
> Die **geplante cacheaktualisierung** Abschnitt ist nur für Datasets in DirectQuery/LiveConnection Modus verfügbar. Datasets im Importmodus ist keine separate kachelaktualisierung erforderlich, weil die Kacheln automatisch, während die nächste geplante datenaktualisierung aktualisiert werden.

## <a name="contact-support"></a>Support kontaktieren
Wenn weiterhin Probleme auftreten, wenden Sie sich an den [Support](https://support.powerbi.com), um dem Problem auf den Grund zu gehen.

## <a name="next-steps"></a>Nächste Schritte
[Problembehandlung beim lokalen Datengateway](service-gateway-onprem-tshoot.md)  
[Problembehandlung in Power BI Personal Gateway](service-admin-troubleshooting-power-bi-personal-gateway.md)  
Weitere Fragen? [Wenden Sie sich an die Power BI-Community](http://community.powerbi.com/)

