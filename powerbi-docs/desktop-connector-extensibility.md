---
title: Connectorerweiterbarkeit in Power BI
description: Connectorerweiterbarkeit, Funktionen, Sicherheitseinstellungen und zertifizierte Connectors
author: cpopell
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/22/2019
ms.author: gepopell
LocalizationGroup: Connect to data
ms.openlocfilehash: 16b96d91a9dd37fa8a502bbcca772438c703cb63
ms.sourcegitcommit: d88cc6a87d4ba82ad2c4d496a3634f927e4ac529
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/30/2019
ms.locfileid: "66412959"
---
# <a name="connector-extensibility-in-power-bi"></a>Connectorerweiterbarkeit in Power BI

In Power BI können Kunden und Entwickler die Datenquellen erweitern mit denen sie sich in vielerlei Hinsicht verbunden wird. Sie verwenden vorhandener Connectors und generische Datenquellen (z. B. ODBC, OData, OLE DB, Web, CSV, XML, JSON). Entwickler erstellen datenerweiterungen genannt **benutzerdefinierte Connectors**, und stellen sie **zertifizierte Connectors**.

Zurzeit, **benutzerdefinierte Connectors** über eine Menüoption, die sicher Sie können steuern, welche von benutzerdefiniertem Code können auf Ihrem System ausgeführt werden sollen. Sie können alle benutzerdefinierten Connectors oder nur die Connectors können nur zertifizierte und verteilt, die von Microsoft in die **Daten abrufen** Dialogfeld.

## <a name="custom-connectors"></a>Benutzerdefinierte Connectors

**Benutzerdefinierte Connectors** kann enthalten eine Vielzahl von Möglichkeiten, im Bereich von kleinen APIs, die kritisch für Ihr Unternehmen, mit großen branchenspezifische Services, die von Microsoft noch nicht freigegeben eines Connectors für. Viele Connectors, die vom Hersteller verteilt werden. Wenn Sie eine für einen bestimmten Data Connector müssen, sollten Sie einen Anbieter wenden.

Verwenden einer **Custom Connector**, fügen Sie ihn in das  *\[Dokumente]\\Power BI Desktop\\benutzerdefinierte Connectors* Ordner, und passen Sie die Sicherheitseinstellungen, wie in beschrieben Im folgenden Abschnitt.

Sie müssen die Sicherheitseinstellungen nicht anpassen, um **zertifizierte Connectors** zu verwenden.

## <a name="data-extension-security"></a>Sicherheit für Datenerweiterung

Zum Ändern von erweiterungseinstellungen Sicherheit Daten im **Power BI Desktop** wählen **Datei > Optionen und Einstellungen > Optionen > Sicherheit**.

![Steuern Sie, ob Sie benutzerdefinierte Connectors mit Erweiterung der Datensicherheit Optionen laden möchten](media/desktop-connector-extensibility/data-extension-security-1.png)

Unter **Datenerweiterungen** können Sie zwischen zwei Sicherheitsstufen wählen:

* (Empfohlen) Nur zertifizierte Erweiterungen laden
* (Nicht empfohlen) Alle Erweiterungen ohne Überprüfung oder Warnung laden

Wenn Sie planen **benutzerdefinierte Connectors** oder Connectors, die Sie oder einen Drittanbieter entwickelt haben, müssen Sie auswählen **"(Not Recommended) können eine beliebige Erweiterung ohne Warnung laden"** . Diese Einstellung empfohlen nicht, wenn Sie unbedingt Ihre benutzerdefinierten Connectors vertrauen. Da der Code dort Verarbeiten von Anmeldeinformationen, einschließlich der über HTTP senden und Sicherheitsstufen ignorieren kann.

Auf der **"(empfohlen)"** Sicherheit festlegen, wenn benutzerdefinierte Connectors in Ihrem System vorhanden sind, das ein Fehler angezeigt wird, die Connectors beschrieben wird, die wegen nicht geladen werden kann.

![Ein Dialogfeld wird beschrieben, benutzerdefinierte Connectors, die aufgrund von Sicherheitseinstellungen, in diesem Fall TripPin nicht geladen werden können](media/desktop-connector-extensibility/data-extension-security-2.png)

Ihre Sicherheitseinstellungen zu ändern, um den Fehler zu beheben, und verwenden diese Connectors, die **"(Not Recommended) können eine beliebige Erweiterung ohne Warnung laden"** festlegen, wie oben beschrieben. Starten Sie anschließend neu **Power BI Desktop**.

## <a name="certified-connectors"></a>Zertifizierte Connectors

Es gilt eine beschränkte Teilmenge von datenerweiterungen **Certified**. Zugriff auf die zertifizierte Connectors in der **Datenabruf** Dialogfeld. Allerdings von Drittanbietern, die Erstellung des Connectors ist verantwortlich für die Wartung und Support. Während Microsoft Connectors verteilt, ist es nicht für ihre Leistung oder einer weiteren Funktion verantwortlich.

Wenn Sie einen benutzerdefinierten Connector zertifizieren möchten, muss der Hersteller sich an dataconnectors@microsoft.com wenden.
