---
title: Verwenden von SAP HANA in Power BI Desktop
description: Verwenden von SAP HANA in Power BI Desktop
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
LocalizationGroup: Connect to data
ms.openlocfilehash: c048a83dad3ea800f50b08bd15c0cec18d6d86cf
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/24/2018
---
# <a name="use-sap-hana-in-power-bi-desktop"></a>Verwenden von SAP HANA in Power BI Desktop
Sie haben nun die Möglichkeit, mit Power BI Desktop auf **SAP HANA** -Datenbanken zuzugreifen. Für die Verwendung von **SAP HANA**muss der SAP HANA-ODBC-Treiber auf dem lokalen Clientcomputer installiert sein, damit die Datenverbindung von Power BI Desktop zu **SAP HANA** ordnungsgemäß funktioniert. Sie können den SAP HANA-ODBC-Treiber aus dem [SAP Software Download Center](https://support.sap.com/swdc) herunterladen. Suchen Sie dort nach dem SAP HANA CLIENT für Windows-Computer. Da die Struktur des **SAP Software Download Center** regelmäßig überarbeitet wird, können wir keine genaueren Angaben zu dieser Website machen.

Zum Herstellen einer Verbindung mit einer **SAP HANA**-Datenbank wählen Sie **Daten abrufen > Datenbank > SAP HANA-Datenbank** aus, wie in der folgenden Abbildung dargestellt.

![](media/desktop-sap-hana/sap-hana-1.png)

Beim Herstellen der Verbindung mit einer SAP HANA-Datenbank geben Sie den Servernamen und den Port im Format *Server:Port* an. Die folgende Abbildung zeigt ein Beispiel mit einem Server mit dem Namen *ServerXYZ* und Port *30015*.

![](media/desktop-sap-hana/sap-hana-2.png)

In dieser Version wird **SAP HANA** im [DirectQuery](desktop-use-directquery.md)-Modus in Power BI Desktop und dem Power BI-Dienst unterstützt, und Sie können Berichte, die **SAP HANA** im DirectQuery-Modus verwenden, im Power BI-Dienst veröffentlichen oder hochladen. Darüber hinaus können Sie Berichte im Power BI-Dienst veröffentlichen und hochladen, wenn **SAP HANA** nicht im DirectQuery-Modus verwendet wird.

### <a name="supported-features-for-sap-hana"></a>Unterstützte Funktionen für SAP HANA
Diese Version enthält viele Funktionen für **SAP HANA**. Diese sind in der folgenden Liste aufgeführt:

* Der Power BI-Connector für **SAP HANA** verwendet zur komfortablen Anwendung den SAP-ODBC-Treiber
* **SAP HANA** unterstützt sowohl DirectQuery als auch Importoptionen
* Power BI unterstützt HANA-Informationsmodelle (z. B. Analytik- und Kalkulationsansichten) und bietet optimierte Navigation
* Mit **SAP HANA** lässt sich auch die direkte SQL-Funktion zur Verbindung mit Zeilen- und Spaltentabellen nutzen.
* Mit optimierter Navigation für HANA-Modelle
* Power BI unterstützt **SAP HANA** -Variablen und -Eingangsparameter

### <a name="installing-the-sap-hana-odbc-driver"></a>Installieren des SAP HANA-ODBC-Treibers
### <a name="limitations-of-sap-hana"></a>Einschränkungen für SAP HANA
Es gibt auch einige Einschränkungen bei der Verwendung von **SAP HANA**, wie unten gezeigt.

* NVARCHAR-Zeichenfolgen werden auf maximal 4000 Unicode-Zeichen gekürzt.
* SMALLDECIMAL wird nicht unterstützt.
* VARBINARY wird nicht unterstützt.
* Gültige Datumsangaben liegen zwischen 1899/12/30 und 9999/12/31.

