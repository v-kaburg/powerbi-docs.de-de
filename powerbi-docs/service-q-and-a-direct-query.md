---
title: Verwenden von Q&A mit Liveverbindungen in Power BI
description: Dokumentation für die Verwendung von Power BI Q&A-Abfragen in natürlicher Sprache mit Liveverbindungen mit Analysis Services-Daten und dem lokalen Datengateway.
author: maggiesMSFT
manager: kfile
ms.reviewer: mihart
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 10/16/2018
ms.author: maggies
LocalizationGroup: Ask questions of your data
ms.openlocfilehash: 9836cd88bef5066f61a8ae44eabe7685196e2bed
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2019
ms.locfileid: "65624945"
---
# <a name="enable-qa-for-live-connections-in-power-bi"></a>Aktivieren von Q&A für Liveverbindungen in Power BI
## <a name="what-is-the-on-premises-data-gateway--what-is-a-live-connection"></a>Was ist das lokale datengateway?  Was ist eine Liveverbindung?
Sie können Datasets in Power BI importieren oder eine Liveverbindung zu den Daten herstellen. Eine liveverbindung verwendete Datasets häufig auf die verwiesen wird als "lokal". Die Liveverbindungen werden mit einem [Gateway](service-gateway-onprem.md) verwaltet, und die Übermittlung der Daten und Abfragen erfolgt über Liveabfragen.

## <a name="qa-for-on-premises-data-gateway-datasets"></a>Q&A für Datasets mit Zugriff über das lokale Datengateway
Wenn Sie F&A mit Datasets verwenden möchten, auf die Sie über ein Gateway zugreifen, müssen Sie die Datasets zuerst aktivieren.

Nach der Aktivierung erstellt Power BI einen Index für Ihre Datenquelle und lädt eine Teilmenge der Daten in Power BI hoch, um das Stellen von Fragen zu ermöglichen. Das Erstellen des anfänglichen Index kann mehrere Minuten dauern. Dieser wird anschließend von Power BI verwaltet und bei Datenänderungen automatisch aktualisiert. Das F&A-Feature verhält sich mit diesen Datasets genauso wie mit in Power BI veröffentlichten Daten. In beiden Fällen wird der vollständige in F&A verfügbare Feature-Satz einschließlich der Verwendung der Datenquelle mit Cortana unterstützt.

Wenn Sie in Power BI Fragen stellen, ermittelt F&A die beste Visualisierung bzw. den besten Bericht, um Ihre Fragen mithilfe eines Index Ihres Datasets zu beantworten. Nachdem die bestmögliche Antwort ermittelt wurde, ruft Q&A mithilfe von DirectQuery Livedaten aus der Datenquelle über das Gateway ab, um Diagrammen und Grafiken zu füllen. Dadurch zeigen die F&A-Ergebnisse in Power BI stets die aktuellen Daten direkt aus der zugrunde liegenden Datenquelle an.

Da Power BI F&A die Text- und Schemawerte aus Ihrer Datenquelle verwenden, um zu ermitteln, wie das zugrunde liegende Modell für Antworten abgefragt werden soll, ist bei Suchen nach speziellen neuen oder gelöschten Textwerten (wie Fragen im Zusammenhang mit einem neu hinzugefügten Textdatensatz für einen Kunden) wichtig, dass der Index die aktuellen Werte enthält. Power BI aktualisiert den Text- und Schemaindex automatisch innerhalb von 60 Minuten nach einer Datenänderung.

Weitere Informationen finden Sie unter:

* Was ist das [lokale Datengateway](service-gateway-onprem.md)?
* [Power BI Q & A für Consumer](consumer/end-user-q-and-a.md)

## <a name="enable-qa"></a>Aktivieren von Q&A
Nachdem Sie das Datengateway eingerichtet haben, stellen Sie aus Power BI eine Verbindung mit Ihren Daten her.  Erstellen Sie ein Dashboard mit Ihren lokalen Daten oder laden Sie eine PBIX-Datei hoch, die lokale Daten verwendet.  Möglicherweise enthalten Ihre Dashboards, Berichte und Datasets auch bereits lokale Daten, die für Sie freigegeben wurden.

1. Klicken Sie rechts oben auf das Zahnradsymbol ![Zahnradsymbol](media/service-q-and-a-direct-query/power-bi-cog.png) und dann auf **Einstellungen**.
   
   ![Menü „Einstellungen“](media/service-q-and-a-direct-query/powerbi-settings.png)
2. Wählen Sie **Datasets**, und wählen Sie das für Q&A aktivierte Dataset aus.
   
   ![Anzeige „Datasets“ im Menü „Einstellungen“](media/service-q-and-a-direct-query/power-bi-q-and-a-settings.png)
3. Erweitern Sie **Q&A and Cortana**, aktivieren Sie das Kontrollkästchen **Turn on Q&A for this dataset**, und wählen Sie **Anwenden**.
   
    ![Erweiterter Q&A-Bereich](media/service-q-and-a-direct-query/power-bi-q-and-a-directquery.png)

## <a name="what-data-is-cached-and-how-is-privacy-protected"></a>Welche Daten werden zwischengespeichert, und wie werden Daten geschützt?
Wenn Sie F&A für Ihre lokalen Daten aktivieren, wird eine Teilmenge der Daten im Dienst zwischengespeichert. Damit wird eine akzeptable Leistung von F&A sichergestellt. Werte, die länger als 24 Zeichen sind, werden in Power BI nicht zwischengespeichert. Wenn Sie F&A deaktivieren (durch Deaktivieren von **Turn on Q&A for this dataset**) oder Ihr Dataset löschen, wird der Cache innerhalb weniger Stunden gelöscht.

## <a name="considerations-and-troubleshooting"></a>Zu beachtende Aspekte und Problembehandlung
Die Funktion weist einige Einschränkungen auf:

* Das Feature ist zunächst nur für tabellarische SQL Server 2016 Analysis Services-Datenquellen verfügbar. Das Feature wurde für die Zusammenarbeit mit tabellarischen Daten optimiert. Die f & A wird noch nicht unterstützt für mehrdimensionale. Im Lauf der Zeit werden weitere vom lokalen Datengateway unterstützte Datenquellen eingeführt.
* Sicherheit auf Zeilenebene, die in SQL Server Analysis Services definierte vollständige Unterstützung ist anfänglich nicht verfügbar. Beim stellen von Fragen in f & A, zugreifen nicht die "Automatische Vervollständigung" Fragen während der Eingabe-Werte ein Benutzer angezeigt werden kann auf. Die im Modell definierte Sicherheit auf Zeilenebene wird jedoch für Berichts- und Diagrammvisualisierungen respektiert, wobei keine zugrunde liegenden numerischen Daten angezeigt werden können. Optionen zum Steuern dieses Verhalten werden in kommenden Updates veröffentlicht.
* Sicherheit auf Objektebene (OLS) wird nicht unterstützt. Q & A nicht Sicherheit auf Objektebene respektieren und kann Offenlegen Tabellen- oder Spaltennamen für Benutzer, die keinen Zugriff darauf haben. Sie sollten die Sicherheit auf Zeilenebene aktivieren, um sicherzustellen, dass Datenwerte angemessen gesichert sind. 
* Liveverbindungen werden nur mit dem lokalen Datengateway unterstützt. Daher kann dies mit dem personal Gateway verwendet werden.

## <a name="next-steps"></a>Nächste Schritte

- [Lokales Datengateway](service-gateway-onprem.md)  
- [Verwalten Ihrer Datenquelle – Analysis Services](service-gateway-enterprise-manage-ssas.md)  
- [Power BI: Grundlegende Konzepte](consumer/end-user-basic-concepts.md)  
- [Übersicht über Power BI Q&A](consumer/end-user-q-and-a.md)  

Weitere Fragen? [Stellen Sie Ihre Frage in der Power BI-Community.](http://community.powerbi.com/)

