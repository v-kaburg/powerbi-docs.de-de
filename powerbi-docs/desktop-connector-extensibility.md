---
title: Connectorerweiterbarkeit in Power BI
description: Connectorerweiterbarkeit, Funktionen, Sicherheitseinstellungen und zertifizierte Connectors
author: cpopell
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 07/25/2018
ms.author: gepopell
LocalizationGroup: Connect to data
ms.openlocfilehash: c63357df043ff6a646562d398a07d8042dd5a0ee
ms.sourcegitcommit: 7fb0b68203877ff01f29724f0d1761d023075445
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/26/2018
ms.locfileid: "39256573"
---
# <a name="connector-extensibility-in-power-bi"></a>Connectorerweiterbarkeit in Power BI

In Power BI können Kunden und Entwickler die Datenquellen, mit denen sie sich verbinden können, auf vielfältige Weise erweitern, z. B. über vorhandene Connectors und generische Datenquellen (z. B. ODBC, OData, OLEDB, Web, CSV, XML, JSON). Entwickler können zusätzlich zu diesen Datenquellen Datenerweiterungen erstellen, sogenannte **benutzerdefinierte Connectors**, und einen Connector zertifizieren, sodass er ein **zertifizierter Connector** wird.

In früheren Power BI-Versionen wurde die Verwendung von **benutzerdefinierten Connectors** über einen Featureschalter aktiviert. Nun können Sie über ein Menü den benutzerdefinierten Code, den Sie auf Ihrem System ausführen möchten, sicher steuern. Sie können alle benutzerdefinierten Connectors zulassen oder nur die Connectors, die von Microsoft im Dialogfeld **Daten abrufen** zertifiziert und verteilt werden.

## <a name="custom-connectors"></a>Benutzerdefinierte Connectors

**Benutzerdefinierte Connectors** können zahlreiche Funktionen bereitstellen – von kleinen APIs, die für Ihr Unternehmen wichtig sind, bis hin zu großen branchenspezifischen Diensten, die Microsoft nicht implementiert hat. Die meisten dieser Connectors werden vom Hersteller selbst vertrieben. Wenn Sie also einen bestimmten Datenconnector benötigen, sollten Sie sich an einen Hersteller wenden.

Um einen **benutzerdefinierten Connector** zu verwenden, legen Sie ihn in den Ordner *\[Dokumente]\\Power BI Desktop\\Benutzerdefinierte Connectors* und passen Sie die Sicherheitseinstellungen wie im folgenden Abschnitt beschrieben an.

Sie müssen die Sicherheitseinstellungen nicht anpassen, um **zertifizierte Connectors** zu verwenden.

## <a name="data-extension-security"></a>Sicherheit für Datenerweiterung

Um die Sicherheitseinstellungen der Datenerweiterung zu ändern, wählen Sie in **Power BI Desktop** **Datei > Optionen und Einstellungen > Optionen > Sicherheit** aus.

![Legen Sie fest, ob Sie benutzerdefinierte Connectors mit Sicherheitsoptionen für die Datenerweiterung laden können.](media/desktop-connector-extensibility/data-extension-security-1.png)

Unter **Datenerweiterungen** können Sie zwischen zwei Sicherheitsstufen wählen:

* (Empfohlen) Nur zertifizierte Erweiterungen laden
* (Nicht empfohlen) Alle Erweiterungen ohne Überprüfung oder Warnung laden

Wenn Sie **benutzerdefinierte Connectors** oder von Ihnen bzw. von einem Drittanbieter entwickelte und verteilte Connectors verwenden möchten, müssen Sie folgende Option auswählen: **(Nicht empfohlen) Alle Erweiterungen ohne Überprüfung oder Warnung laden**. Diese Sicherheitseinstellung wird nur empfohlen, wenn Sie **benutzerdefinierte Connectors** ausführen möchten.

Wenn Sie benutzerdefinierte Connectors in Ihrem System verwenden, wird bei der Sicherheitseinstellung **(Empfohlen)** ein Fehler angezeigt, der die Connectors beschreibt, die aus Sicherheitsgründen nicht geladen werden können.

![Ein Dialogfeld beschreibt benutzerdefinierte Connectors, die aufgrund von Sicherheitseinstellungen nicht geladen werden können, in diesem Fall TripPin.](media/desktop-connector-extensibility/data-extension-security-2.png)

Um den Fehler zu beheben und diese Connectors zu verwenden, müssen Sie Ihre Sicherheitseinstellungen wie oben beschrieben zu **(Nicht empfohlen)** ändern und **Power BI Desktop** neu starten.

## <a name="certified-connectors"></a>Zertifizierte Connectors

Eine begrenzte Anzahl von Datenerweiterungen gilt als **zertifiziert**. Zertifizierte Connectors sind über das Dialogfeld **Daten erhalten** verfügbar, doch für Wartung und Support ist der Drittanbieter verantwortlich, der den Connector erstellt hat. Microsoft verteilt diese zwar, ist jedoch nicht verantwortlich für deren Leistung oder weitere Funktionalität.

Um einen benutzerdefinierten Connector zu zertifizieren, muss sich der Hersteller an Microsoft wenden.
