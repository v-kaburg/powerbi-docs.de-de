---
title: Gateway-Leistungsüberwachung (öffentliche Vorschau)
description: Dieser Artikel enthält Informationen zum Überwachen der Leistung von die lokalen Daten-Gateway-Aktivitäten.
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-gateways
ms.topic: conceptual
ms.date: 05/08/2019
LocalizationGroup: Gateways
ms.openlocfilehash: 8c5f4170383f31ea465ebb7035aebfb53f551982
ms.sourcegitcommit: af2b2238fe77eaa1b2392a19a143a0250b8665cf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "65535365"
---
# <a name="gateway-performance-monitoring-public-preview"></a>Gateway-Leistungsüberwachung (öffentliche Vorschau)

Überwachen der Leistung haben bisher Gateway Admins abhing, zum Überwachen von Leistungsindikatoren über die Windows-Systemmonitor-Tool manuell. Wir bieten nun eine zusätzliche Protokollierung und ein [Gateway Leistung PBI-Vorlagendatei](http://download.microsoft.com/download/D/A/1/DA1FDDB8-6DA8-4F50-B4D0-18019591E182/GatewayPerformanceMonitoring.pbit) um die Ergebnisse zu visualisieren. Dieses Feature bietet neue Einblicke in die Auslastung des Gateways und ermöglicht es Ihnen, Abfragen mit geringer Leistung zu beheben.

> [!NOTE]
> Dieses Feature ist derzeit verfügbar ist, nur für das lokale datengateway in den Modus "standard" und nicht für den persönlichen Modus.

## <a name="enable-performance-logging"></a>Die leistungsprotokollierung aktivieren

Um dieses Feature zu aktivieren, stellen Sie die folgenden Änderungen an der *Microsoft.PowerBI.DataMovement.Pipeline.GatewayCore.dll.config* Datei der "\Program Files\On-Premises Data Gateway" Ordner:

1. Update **QueryExecutionReportOn** zu _"true"_ zusätzliche Protokollierung für Abfragen, die ausgeführt wird, über das Gateway aktivieren. Durch Aktivieren dieser Option werden sowohl den Ausführungsbericht für Abfrage und die Abfrage Aggregation Ausführungsbericht-Dateien erstellt.

   ``` xml
   <setting name="QueryExecutionReportOn" serializeAs="String">
     <value>True</value>
   </setting>
   ```

1. Update **SystemCounterReportOn** zu _"true"_ die zusätzliche Protokollierung für den Arbeitsspeicher und CPU-System-Indikatoren aktivieren. Durch Aktivieren dieser Option wird die System Leistungsindikator Aggregationsbericht-Datei erstellt.

   ```xml
   <setting name="SystemCounterReportOn" serializeAs="String">
     <value>True</value>
   </setting>
   ```

1. Es gibt andere Werte in der Config-Datei, die Sie aktualisieren können, je nach Bedarf.

    - **ReportFilePath**: Bestimmt den Pfad, in dem die drei Protokolldateien gespeichert werden. Standardmäßig ist dieser Pfad entweder "\Users\PBIEgwService\AppData\Local\Microsoft\On-premises Daten Gateway\Report" oder "Windows\ServiceProfiles\PBIEgwService\AppData\Local\Microsoft\On lokale Daten Gateway\Report", je nach Betriebssystemversion. Wenn Sie ein Dienstkonto nicht für das Gateway verwenden _PBIEgwService_, ersetzen Sie diesen Teil des Pfads durch den Namen des Dienstkontos.
    - **ReportFileCount**: Bestimmt die Anzahl der Protokolldateien jeder Art beibehalten werden sollen. Der Standardwert ist 10.
    - **ReportFileSizeInBytes**: Bestimmt die Größe der Datei zu verwalten. Der Standardwert ist 104857600.
    - **QuerExecutionAggregationTimeInMinutes**: Bestimmt die Anzahl der Minuten, die für die die Funktion zur aggregiert wird. Der Standardwert ist 5.
    - **SystemCounterAggregationTimeInMinutes**: Bestimmt die Anzahl der Minuten, die für die die Systemleistungsindikatoren aggregiert wird. Der Standardwert ist 5.

1. Nachdem Sie die Änderungen an der Config-Datei vorgenommen haben, starten Sie das Gateway für diese Konfigurationswerte wirksam neu. Sie müssen jetzt starten, sehen die Berichtsdateien, die Sie für die angegebenen Speicherort generiert wird **ReportFilePath**.

    > [!NOTE]
    > Es kann bis zu 10 Minuten dauern und legen Sie die Zeitspanne für **QuerExecutionAggregationTimeInMinutes** in der Config-Datei, bis Dateien beginnen, in dem Ordner angezeigt.

## <a name="understand-performance-logs"></a>Verstehen von Leistungsprotokollen

Wenn Sie dieses Feature aktivieren, erstellen wir drei neue Protokolldateien:

- Den Ausführungsbericht für Abfrage
- Die Abfrage Ausführung-Aggregationsbericht
- Das System Leistungsindikator-Aggregationsbericht

Den Ausführungsbericht für die Abfrage enthält ausführliche Informationen zum Ausführung. Wir erfassen, die die folgenden Attribute:

|Attribut |Beschreibung |
| ---- | ---- |
|**GatewayObjectId** |Eindeutiger Bezeichner für das Gateway. |
|**RequestId** |Eindeutiger Bezeichner für eine Gateway-Anforderung. Sie können für mehrere Abfragen identisch sein. |
|**DataSource** |Enthält den Typ der Datenquelle und die Datenquelle an. |
|**QueryTrackingId** |Eindeutiger Bezeichner für eine Abfrage. |  
|**QueryExecutionEndTimeUTC** |Uhrzeit, wann die Ausführung der Abfrage abgeschlossen. |
|**QueryExecutionDuration**(ms) |Die Dauer für eine abfrageausführung. |
|**QueryType** |Geben Sie der Abfrage – z. B., die Abfrage übergeben konnte eine Power BI-Aktualisierung/DirectQuery oder Abfragen von PowerApps und Microsoft Flow. |
|**DataProcessingEndTimeUTC** |Zeit bei der Datenverarbeitung Aktivitäten wie Aufträge, Datenabruf, Komprimierung, Datenverarbeitung und usw., die abgeschlossen wird. |
|**DataProcessingDuration**(ms) |Die Dauer für die Datenverarbeitung-Aktivitäten, wie Aufträge, Abrufen von Daten, Komprimierung, Datenverarbeitung und So weiter. |
|**Erfolg** |Gibt an, ob die Abfrage erfolgreich war oder fehlgeschlagen ist. |
|**ErrorMessage** |Die Fehlermeldung darauf hingewiesen, wenn Fehler bei der Abfrage. |
| | |

Die Abfrage Aggregation Ausführungsbericht enthält Abfrageinformationen, die auf ein Zeitintervall von aggregiert **GatewayObjectId**, **DataSource**, **Erfolg**, und **QueryType**. Der Standardwert ist 5 Minuten, aber Sie können es anpassen, wie unten beschrieben. Wir erfassen, die die folgenden Attribute:

|Attribut |Beschreibung |
| ---- | ---- |
|**GatewayObjectId** |Eindeutiger Bezeichner für das Gateway. |
|**AggregationStartTimeUTC** |Start des Zeitfensters für die Abfrageattribute aggregiert wurden. |
|**AggregationEndTimeUTC** |Das Ende des Zeitfensters für die Abfrage Attribute aggregiert wurden. |
|**DataSource** |Enthält den Typ der Datenquelle und die Datenquelle an. |
|**Erfolg** |Gibt an, ob die Abfrage erfolgreich war oder fehlgeschlagen ist. |
|**AverageQueryExecutionDuration**(ms) |Durchschnittliche Ausführungszeit der Abfrage für das Zeitfenster für die Aggregation an. |
|**MaxQueryExecutionDuration**(ms) |Maximale Ausführungszeit für das Zeitfenster für die Aggregation. |
|**MinQueryExecutionDuration**(ms) |Minimale Ausführungszeit für das Zeitfenster für die Aggregation. |
|**QueryType** |Geben Sie der Abfrage – z. B., die Abfrage übergeben konnte eine Power BI-Aktualisierung/DirectQuery oder Abfragen von PowerApps und Microsoft Flow. |
|**AverageDataProcessingDuration**(ms) |Die durchschnittliche Zeit für die Datenverarbeitung-Aktivitäten, wie Aufträge, Abrufen von Daten, Komprimierung und Verarbeitung von Daten, für das Zeitfenster für die Aggregation und so weiter. |
|**MaxDataProcessingDuration**(ms) |Maximale Zeit für das Zeitfenster für die Aggregation für die Datenverarbeitung-Aktivitäten, wie Aufträge, Abrufen von Daten, Komprimierung, Datenverarbeitung und So weiter. |
|**MinDataProcessingDuration**(ms) |Minimale Zeit für das Zeitfenster für die Aggregation für die Datenverarbeitung-Aktivitäten, wie Aufträge, Abrufen von Daten, Komprimierung, Datenverarbeitung und So weiter. |
|**Count** |Anzahl der Abfragen. |
| | |

Aggregationsbericht der Zähler enthält die System-Leistungsindikatorwerte auf ein Zeitintervall aggregiert. Der Standardwert ist 5 Minuten, aber Sie können es anpassen, wie unten beschrieben. Wir erfassen, die die folgenden Attribute:

|Attribut |Beschreibung |
| ---- | ---- |
|**GatewayObjectId** |Eindeutiger Bezeichner für das Gateway. |
|**AggregationStartTimeUTC** |Start des Zeitfensters für die Leistungsindikatoren des aggregiert wurden. |
|**AggregationEndTimeUTC** |Das Ende des Zeitfensters für welches System Leistungsindikatoren aggregiert wurden. |
|**CounterName** |Systemleistungsindikatoren, einschließlich Speicher- und CPU-Auslastung durch das Gateway, kombinieren und dem insgesamt vom Computer das Gateway. |
|**Max.** |Maximalwert für den Leistungsindikator "System" für das Zeitfenster für die Aggregation. |
|**Min** |Der Mindestwert für den Leistungsindikator "System" für das Zeitfenster für die Aggregation. |
|**Durchschnitt** |Der Durchschnittswert des Indikators "System" für das Zeitfenster für die Aggregation. |
| | |

## <a name="visualize-gateway-performance"></a>Visualisieren Sie die Gateway-Leistung

Jetzt können Sie die Daten visualisieren, die in den Protokolldateien.

1. Herunterladen der [Gateway Leistung PBI-Vorlage](http://download.microsoft.com/download/D/A/1/DA1FDDB8-6DA8-4F50-B4D0-18019591E182/GatewayPerformanceMonitoring.pbit) und öffnen Sie sie mithilfe von Power BI Desktop.

1. Klicken Sie im Dialogfeld, das geöffnet wird, überprüfen Sie, dass der Pfad, den Wert in entspricht **ReportFilePath**.

    ![Popup mit der für den Ordnerpfad](media/service-gateway-performance-monitoring/gateway-folder-path-pop-up.png)

1. Wählen Sie **Load**, und die Vorlagendatei startet Laden der Daten aus den Protokolldateien. Alle Visualisierungen sollten mit den Daten in den Berichten aufgefüllt werden.

1. Optional speichern Sie diese Datei als eine pbix-Datei, und veröffentlichen Sie es für den Dienst für automatische Aktualisierungen.

Darüber hinaus können Sie die Vorlagendatei gemäß Ihren Anforderungen anpassen. Weitere Informationen zu Power BI-Vorlagen finden Sie in diesem [Microsoft Power BI-Blog-Beitrag](https://powerbi.microsoft.com/en-us/blog/deep-dive-into-query-parameters-and-power-bi-templates/).