---
title: Verwenden von SAP HANA in Power BI Desktop
description: Verwenden von SAP HANA in Power BI Desktop
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 07/27/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: c2a2069eb5f4d056db5840a08ecb1a871bf587c8
ms.sourcegitcommit: f01a88e583889bd77b712f11da4a379c88a22b76
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/27/2018
ms.locfileid: "39329866"
---
# <a name="use-sap-hana-in-power-bi-desktop"></a>Verwenden von SAP HANA in Power BI Desktop
Sie haben nun die Möglichkeit, mit Power BI Desktop auf **SAP HANA** -Datenbanken zuzugreifen. Für die Verwendung von **SAP HANA**muss der SAP HANA-ODBC-Treiber auf dem lokalen Clientcomputer installiert sein, damit die Datenverbindung von Power BI Desktop zu **SAP HANA** ordnungsgemäß funktioniert. Sie können den SAP HANA-ODBC-Treiber aus dem [SAP Software Download Center](https://support.sap.com/swdc) herunterladen. Suchen Sie dort nach dem SAP HANA CLIENT für Windows-Computer. Da die Struktur des **SAP Software Download Center** regelmäßig überarbeitet wird, können wir keine genaueren Angaben zu dieser Website machen.

Zum Herstellen einer Verbindung mit einer **SAP HANA**-Datenbank klicken Sie wie in der folgenden Abbildung dargestellt auf **Daten abrufen > Datenbank > SAP HANA-Datenbank**.

![](media/desktop-sap-hana/sap-hana-1.png)

Beim Herstellen der Verbindung mit einer SAP HANA-Datenbank geben Sie den Servernamen und den Port im Format *Server:Port* an. Die folgende Abbildung zeigt ein Beispiel mit einem Server mit dem Namen *ServerXYZ* und Port *30015*.

![](media/desktop-sap-hana/sap-hana-2.png)

In diesem Release wird **SAP HANA** im [DirectQuery](desktop-directquery-sap-hana.md)-Modus in Power BI Desktop und dem Power BI-Dienst unterstützt, und Sie können Berichte, die **SAP HANA** im DirectQuery-Modus verwenden, im Power BI-Dienst veröffentlichen und hochladen. Darüber hinaus können Sie Berichte im Power BI-Dienst veröffentlichen und hochladen, wenn **SAP HANA** nicht im DirectQuery-Modus verwendet wird.

### <a name="supported-features-for-sap-hana"></a>Unterstützte Funktionen für SAP HANA
Diese Version enthält viele Funktionen für **SAP HANA**. Diese sind in der folgenden Liste aufgeführt:

* Der Power BI-Connector für **SAP HANA** verwendet zur benutzerfreundlichen Anwendung den SAP-ODBC-Treiber.
* **SAP HANA** unterstützt sowohl DirectQuery als auch Importoptionen
* Power BI unterstützt HANA-Informationsmodelle (z.B. Analytik- und Kalkulationsansichten) und bietet optimierte Navigation.
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


## <a name="next-steps"></a>Nächste Schritte
Weitere Informationen zu DirectQuery finden Sie in den folgenden Ressourcen:

* [DirectQuery und SAP HANA](desktop-directquery-sap-hana.md)
* [DirectQuery in Power BI](desktop-directquery-about.md)
* [Data Sources supported by DirectQuery (Von DirectQuery unterstützte Datenquellen)](desktop-directquery-data-sources.md)

