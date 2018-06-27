---
title: Problembehandlung für Kachelfehler
description: Häufig auftretende Fehler bei der Aktualisierung einer Kachel
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 05/02/2018
ms.author: davidi
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 8b68ce7af749b7e7f292592f6debdc7e964d6c17
ms.sourcegitcommit: 2a7bbb1fa24a49d2278a90cb0c4be543d7267bda
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2018
ms.locfileid: "34242884"
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

Es konnte nicht auf Ihre Daten zugegriffen werden, da die Datenquelle nicht erreichbar war. Dies kann passieren, wenn die Datenquelle entfernt, umbenannt, verschoben oder offline geschaltet bzw. wenn ihre Berechtigungen geändert wurden. Überprüfen Sie, ob sich die Quelle noch an dem verwiesenen Speicherort befindet und ob Sie darauf zugreifen können. Wenn dies nicht die Ursache des Problems ist, liegt es möglicherweise an einer langsamen Quelle. Versuchen Sie es zu einem Zeitpunkt erneut, wenn die Auslastung der Quelle geringer ist. Wenn es sich um eine lokale Quelle handelt, erhalten Sie vom Datenquellenbesitzer möglicherweise weitere Informationen.

**Sie haben keine Berechtigung zum Anzeigen dieser Kachel oder zum Öffnen der Arbeitsmappe.**

Wenden Sie sich an den Besitzer des Dashboards, um sicherzustellen, dass die Datenquellen und das Modell vorhanden sind und der Zugriff auf sie möglich ist.

**Die Daten-Shapes müssen mindestens eine Gruppe oder Berechnung enthalten, die Daten ausgibt. Wenden Sie sich an den Besitzer des Dashboards.**

Es stehen keine Daten zur Anzeige zur Verfügung, da die Abfrage leer ist. Versuchen Sie, Ihrer Visualisierung einige Felder aus der Feldliste hinzuzufügen, und heften Sie sie erneut an.

**Die Daten können nicht angezeigt werden, da Power BI die Beziehung zwischen zwei oder mehr Feldern nicht bestimmen kann.**

Sie versuchen, zwei oder mehr Felder aus Tabellen zu verwenden, die nicht verknüpft sind. Sie müssen die nicht verknüpften Felder aus der Visualisierung und eine Beziehung zwischen den Tabellen erstellen. Anschließend können Sie die Felder wieder zur Visualisierung hinzufügen. Dies kann in Power BI Desktop oder Power Pivot für Excel erfolgen. [Weitere Informationen](desktop-create-and-manage-relationships.md)

**Die Gruppen auf der Primärachse und der Sekundärachse überschneiden sich. Die Gruppen auf der Primärachse können nicht die gleichen Schlüssel wie die Gruppen auf der Sekundärachse aufweisen.**

Dies ist normalerweise ein vorübergehendes Problem. Es tritt i. d. R. auf, wenn Sie Gruppen von Zeilen in Spalten verschieben. In diesem Fall sollte der Fehler nicht mehr angezeigt werden, wenn Sie alle Gruppen verschoben haben. Wenn die Meldung weiterhin angezeigt wird, wechseln Sie zwischen Zeilen und Spalten bzw. der Achsenlegende, oder entfernen Sie Felder aus der Visualisierung.  

**Diese Visualisierung überschreitet die verfügbaren Ressourcen. Versuchen Sie, einen Filter anzuwenden, um die angezeigten Daten zu reduzieren.**

Ihre Visualisierung hat versucht, zu viele Daten abzufragen, sodass die Abfrage nicht mit den verfügbaren Ressourcen abgeschlossen werden konnte. Versuchen Sie, die Visualisierung zu filtern, um die Datenmenge im Ergebnis zu reduzieren.

**Die folgenden Felder können nicht identifiziert werden: {0}. Aktualisieren Sie die Visualisierung mit Feldern, die im Dataset vorhanden sind.**

Das Feld wurde möglicherweise gelöscht oder umbenannt. Entfernen Sie das fehlerhafte Feld aus der Visualisierung, fügen Sie ein anderes Feld hinzu, und heften Sie sie erneut an.

**Die Daten für diese Visualisierung konnten nicht abgerufen werden. Versuchen Sie es später erneut.**

Dies ist normalerweise ein vorübergehendes Problem. Wenn Sie es später erneut versuchen und diese Meldung weiterhin angezeigt wird, wenden Sie sich an den Support.

## <a name="contact-support"></a>Support kontaktieren
Wenn weiterhin Probleme auftreten, wenden Sie sich an den [Support](https://support.powerbi.com), um dem Problem auf den Grund zu gehen.

## <a name="next-steps"></a>Nächste Schritte
[Problembehandlung beim lokalen Datengateway](service-gateway-onprem-tshoot.md)  
[Problembehandlung in Power BI Personal Gateway](service-admin-troubleshooting-power-bi-personal-gateway.md)  
Weitere Fragen? [Wenden Sie sich an die Power BI-Community](http://community.powerbi.com/)

