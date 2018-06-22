---
title: On-premises data gateway – Häufig gestellte Fragen
description: Dies sind die häufig gestellten Fragen zum lokalen Datengateway. Hier werden häufig gestellte Fragen für das Gateway an einem Ort gesammelt.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-gateways
ms.topic: conceptual
ms.date: 01/24/2018
ms.author: mblythe
LocalizationGroup: Gateways
ms.openlocfilehash: b4ecec3b2e53c2fea0fcbb7d78d1114da1a105ed
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2018
ms.locfileid: "34299629"
---
# <a name="on-premises-data-gateway-faq"></a>On-premises data gateway – Häufig gestellte Fragen
<!-- Shared FAQ shared Include -->
[!INCLUDE [gateway-onprem-faq-shared-include](./includes/gateway-onprem-faq-shared-include.md)]

## <a name="analysis-services"></a>Analysis Services
**Frage:** Kann „msdmpump.dll“ zum Erstellen eigener Zuordnungen zu effektiven Benutzernamen für Analysis Services verwendet werden?  
**Antwort:** Nein. Das wird zurzeit nicht unterstützt.

**Frage:** Kann das Gateway für Verbindungen mit einer mehrdimensionalen (OLAP-) Instanz verwendet werden?  
**Antwort:** Ja. Das lokale Datengateway unterstützt Liveverbindungen mit Tabellen- und mehrdimensionalen Modellen von Analysis Services.

**Frage:** Was geschieht, wenn ich das Gateway auf einem Computer in einer anderen Domäne als dem lokalen Server installiere, der die Windows-Authentifizierung verwendet?  
**Antwort:** Dafür geben wir keine Garantien. Es hängt alles von der Vertrauensstellung zwischen den beiden Domänen ab. Wenn sich die zwei verschiedenen Domänen in einem vertrauenswürdigen Domänenmodell befinden, ist das Gateway möglicherweise imstande, eine Verbindung mit dem Analysis Services-Server herzustellen, und der effektive Benutzername kann aufgelöst werden. Wenn dies nicht der Fall ist, treten möglicherweise Fehler bei der Anmeldung auf.

**Frage:** Wie kann ich herausfinden, welcher effektive Benutzername an meine lokalen Analysis Services-Server übergeben wird?  
**Antwort:** Wir beantworten diese Frage im [Artikel zur Problembehandlung](service-gateway-onprem-tshoot.md).

**Frage:** Ich verfüge über 25 Datenbanken in Analysis Services. Gibt es eine Möglichkeit, alle gleichzeitig für das Gateway zu aktivieren?  
**Antwort:** Nein. Das ist zwar geplant, jedoch können wir noch keinen Zeitrahmen nennen.

## <a name="administration"></a>Verwaltung
**Frage:** Kann ich mehr als einen Administrator für ein Gateway haben?  
**Antwort:** Ja. Wenn Sie ein Gateway verwalten, können Sie auf der Registerkarte „Administrator“ weitere Administratoren hinzufügen.

**Frage:** Muss der Gatewayadministrator auch Administrator auf dem Computer sein, auf dem das Gateway installiert ist?  
**Antwort:** Nein. Der Gatewayadministrator verwaltet das Gateway innerhalb des Diensts.

**Frage:** Kann ich verhindern, dass Benutzer in meiner Organisation ein Gateway erstellen?  
**Antwort:** Nein. Das ist zwar geplant, jedoch können wir noch keinen Zeitrahmen nennen.

**Frage:** Kann ich Informationen über die Verwendung und über Statistiken der Gateways in meiner Organisation erhalten?  
**Antwort:** Nein. Das ist zwar geplant, jedoch können wir noch keinen Zeitrahmen nennen.

## <a name="power-bi"></a>Power BI
**Frage:** Muss ich das persönliche Gateway upgraden?
**Antwort:** Nein, Sie können weiterhin das persönliche Gateway für Power BI verwenden.

**Frage:** Wie oft werden Kacheln in einem Dashboard in Power BI aktualisiert, wenn eine Verbindung über das lokale Datengateway besteht?  
**Antwort:** Etwa alle zehn Minuten. Das sind DirectQuery-Verbindungen. Das bedeutet jedoch nicht, dass eine Kachel alle zehn Minuten eine Abfrage an den lokalen Server ausgibt und neue Daten anzeigt.

**Frage:** Kann ich Excel-Arbeitsmappen mit Power Pivot-Datenmodellen hochladen, die Verbindungen mit lokalen Datenquellen aufweisen? Benötige ich bei diesem Szenario ein Gateway?  
**Antwort:** Ja, Sie können die Arbeitsmappe hochladen. Sie benötigen aber kein Gateway. Da die Daten sich im Excel-Datenmodell befinden, sind Berichte in Power BI, die auf der Excel-Arbeitsmappe beruhen, jedoch nicht live. Um Berichte in Power BI zu aktualisieren, müssen Sie jedes Mal wieder eine aktualisierte Arbeitsmappe hochladen. Verwenden Sie alternativ das Gateway mit geplanter Aktualisierung.

**Frage:** Wenn Benutzer Dashboards freigeben, die eine DirectQuery-Verbindung verwenden, können die anderen Benutzer die Daten auch dann sehen, wenn sie nicht über die gleichen Berechtigungen verfügen?  
**Antwort:** Wenn ein Dashboard mit Analysis Services verbunden ist, können Benutzer nur die Daten sehen, auf die sie Zugriff haben. Wenn die Benutzer nicht über die gleichen Berechtigungen verfügen, werden ihnen keine Daten angezeigt. Bei anderen Datenquellen verwenden alle Benutzer die gleichen Anmeldeinformationen, die vom Administrator für diese Datenquelle eingegeben wurden.

**Frage:** Warum kann ich keine Verbindung mit meinem Oracle-Server aufbauen?  
**Antwort:** Möglicherweise müssen Sie den Oracle-Client installieren und in der Datei „tnsnames.ora“ die benötigten Serverdaten eintragen, um die Verbindung mit dem Oracle-Server herzustellen. Diese Installation erfolgt separat außerhalb des Gateways. Weitere Informationen finden Sie unter [Installieren des Oracle-Clients](service-gateway-onprem-manage-oracle.md#installing-the-oracle-client).

**Frage:** Kann das Gateway mit ExpressRoute verwendet werden?  
**Antwort:** Ja. Weitere Informationen zu ExpressRoute und Power BI finden Sie unter [Power BI und ExpressRoute](service-admin-power-bi-expressroute.md).

## <a name="next-steps"></a>Nächste Schritte
[Lokales Datengateway](service-gateway-onprem.md)  
[Ausführliche Informationen zum lokalen Datengateway](service-gateway-onprem-indepth.md)  
[Problembehandlung beim lokalen Datengateway](service-gateway-onprem-tshoot.md)  
Weitere Fragen? [Wenden Sie sich an die Power BI-Community](http://community.powerbi.com/)

