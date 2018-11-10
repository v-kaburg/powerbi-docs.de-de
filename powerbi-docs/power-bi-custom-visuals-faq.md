---
title: Häufig gestellte Fragen zu benutzerdefinierten Visuals in Power BI
description: Durchsuchen Sie die Liste der häufig gestellten Fragen und Antworten zu benutzerdefinierten Visuals in Power BI.
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 10/29/2018
LocalizationGroup: Visualizations
ms.openlocfilehash: 064d32944f52f6e391d4a7ec4df41ecbf09b7e3f
ms.sourcegitcommit: 02f918a4f27625b6f4e47473193ebc8219db40e2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2018
ms.locfileid: "51223074"
---
# <a name="frequently-asked-questions-about-power-bi-custom-visuals"></a>Häufig gestellte Fragen zu benutzerdefinierten Visuals in Power BI

## <a name="organizational-custom-visuals"></a>Benutzerdefinierte Visuals für Organisationen

**Wie kann der Administrator die benutzerdefinierten Visuals für Organisationen verwalten?**

Im Administratorportal kann der Administrator auf der Registerkarte „Benutzerdefinierte Visuals für Organisationen“ [alle benutzerdefinierten Visuals im Unternehmen sehen und verwalten](https://docs.microsoft.com/power-bi/service-admin-portal#organization-visuals): hinzufügen, deaktivieren, aktivieren und löschen.
Diese Visuals müssen nicht mehr per E-Mail oder über einen freigegebenen Ordner weitergegeben werden. Nach der Bereitstellung im Repository der Organisation können die Benutzer in der Organisation diese benutzerdefinierten Visuals für Organisationen einfach ermitteln und direkt über Power BI Desktop oder -Dienst in ihre Berichte importieren. Die benutzerdefinierten Visuals für Organisationen finden Sie im integrierten Speicher (in Desktop und Dienst) auf der Registerkarte „MEINE ORGANISATION“. Sobald der Administrator eine neue Version eines benutzerdefinierten Visuals hochlädt, erhält jeder in der Organisation die gleiche aktualisierte Version. Berichtsautoren müssen das Visual in ihren Berichten nicht löschen, um die neue Version zu erhalten, da alle Berichte, die diese Visuals verwenden, automatisch aktualisiert werden! Der Aktualisierungsmechanismus ist ähnlich wie bei den Visuals im Marketplace.

**Wenn ein Administrator ein benutzerdefiniertes Visual vom öffentlichen Marketplace in den Unternehmensspeicher hochlädt, wird es dann automatisch aktualisiert, sobald ein Anbieter das Visual auf dem öffentlichen Marketplace aktualisiert?**

Nein, es gibt keine automatische Aktualisierungen vom öffentlichen Marketplace.
Es liegt in der Verantwortung des Administrators, die Version der benutzerdefinierten Visuals auf Wunsch zu aktualisieren.

**Gibt es eine Möglichkeit, den Speicher der Organisation zu deaktivieren?**

Nein, die Registerkarte „MEINE ORGANIZATION“ aus Power BI Desktop und -Dienst wird für die Benutzer immer angezeigt. Der Administrator kann alle benutzerdefinierten Visuals für Organisationen im Administratorportal deaktivieren oder löschen, und der Speicher der Organisation ist dann leer.
  
**Wenn der Administrator benutzerdefinierte Visuals über das Administratorportal deaktiviert (Mandanteneinstellungen), haben Benutzer dann noch Zugriff auf die benutzerdefinierten Visuals?**

Ja, wenn der Administrator die benutzerdefinierten Visuals im Administratorportal deaktiviert, hat dies keine Auswirkungen auf den Speicher der Organisation. Einige Organisationen deaktivieren benutzerdefinierte Visuals und aktivieren nur handverlesene Visuals, die vom Power BI-Administrator importiert und in den Speicher der Organisation hochgeladen wurden. Das Deaktivieren der benutzerdefinierten Visuals über das Administratorportal wird in Power BI Desktop nicht erzwungen. Desktop-Benutzer können weiterhin benutzerdefinierte Visuals vom öffentlichen Marketplace in ihren Berichten hinzufügen und verwenden. Diese öffentlichen benutzerdefinierten Visuals beenden jedoch das Rendering nach der Veröffentlichung im Power BI-Dienst und geben einen entsprechenden Fehler aus. Wenn Sie den Power BI-Dienst verwenden, können Sie keine benutzerdefinierten Visuals vom öffentlichen Marketplace importieren. Es können nur Visuals aus dem Speicher der Organisation importiert werden, da die Einstellung für benutzerdefinierte Visuals im Administrationsportal im Power BI-Dienst erzwungen wird.

**Warum sind der Speicher der Organisation und die benutzerdefinierten Visuals in Kombination eine großartige Unternehmenslösung?**

* Jeder erhält die gleiche visuelle Ansicht, die vom Power BI-Administrator gesteuert wird. Sobald der Administrator die Version des Visuals im Administratorportal aktualisiert, erhalten alle Benutzer in der Organisation automatisch die aktualisierte Version.

* Sie müssen keine Visual-Dateien mehr per E-Mail oder einem freigegebenen Ordner mehr weitergeben! Eine zentrale Anlaufstelle, sichtbar für alle angemeldeten Mitglieder.

* Sicherheit und Unterstützung, neue Versionen von benutzerdefinierten Visuals werden ähnlich den Marketplace-Visuals automatisch in allen Berichten aktualisiert.

* Benutzer in der Organisation, die die benutzerdefinierten Visuals verwenden, müssen angemeldet sein, um diese Visuals zu sehen und zu verwenden, die ein Sicherheitselement für die Organisation darstellen.

* Administratoren können steuern, welche benutzerdefinierten Visuals in der Organisation verfügbar sein sollen.

* Administratoren können Visuals zu Testzwecken im Administratorportal aktivieren/deaktivieren. Es besteht eine bessere Sicherheitsdurchsetzung, da diese Visuals nur für Organisationsmitglieder erlaubt sind.

## <a name="certified-custom-visuals"></a>Zertifizierte benutzerdefinierte Visuals

**Was sind zertifizierte benutzerdefinierte Visuals?**

Zertifizierte benutzerdefinierte Visuals sind Visuals im [Marketplace](https://appsource.microsoft.com/marketplace/apps?page=1&product=power-bi-visuals), die bestimmte [angegebene](power-bi-custom-visuals-certified.md) Codeanforderungen und Testkriterien des Power BI-Teams erfüllen.  Die durchgeführten Tests sollen sicherstellen, dass das Visual nicht auf externe Dienste oder Ressourcen zugreift; Microsoft ist jedoch nicht der Autor von benutzerdefinierten Visuals von Drittanbietern, und wir empfehlen unseren Kunden, sich direkt an den Autor zu wenden, um die Funktionalität dieses Visuals zu überprüfen.

## <a name="next-steps"></a>Nächste Schritte

Informationen zur Problembehandlung finden Sie auf der Seite [Troubleshoot Power BI custom visuals (Problembehandlung für benutzerdefinierte Power BI-Visuals)](power-bi-custom-visuals-troubleshoot.md).
