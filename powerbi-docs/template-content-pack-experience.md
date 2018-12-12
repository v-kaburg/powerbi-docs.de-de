---
title: Vorlageninhaltspakete in Power BI in der Praxis
description: Vorlageninhaltspakete in der Praxis
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/09/2017
ms.author: maggies
ms.openlocfilehash: 23a8875479197f1d200a9f086fcfd27d483faf40
ms.sourcegitcommit: b03912343a5a214c6bb972aaa6aa051c2a5f4332
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2018
ms.locfileid: "52900219"
---
# <a name="template-content-pack-experiences-in-power-bi"></a>Vorlageninhaltspakete in Power BI in der Praxis
In diesem Abschnitt wird ein typisches praktisches Beispiel für einen Benutzer durchlaufen, der eine Verbindung mit dem [Inhaltspaket](service-connect-to-services.md) eines unabhängigen Softwareherstellers herstellt.

Testen Sie die Verbindung, indem Sie eine Verbindung mit einem veröffentlichten Inhaltspaket unter https://app.powerbi.com/getdata/services herstellen (z.B. mit dem unten beschriebenen [GitHub-Inhaltspaket](https://app.powerbi.com/getdata/services/github)).

## <a name="connect"></a>Verbinden
Zu Beginn durchsucht ein Benutzer den Inhaltspaketkatalog und wählt ein Inhaltspaket aus, mit dem er eine Verbindung herstellt. Der Eintrag des Inhaltspakets enthält einen Namen, ein Symbol und eine Beschreibung mit weiteren Informationen für den Benutzer.

![Verbindung](media/template-content-pack-experience/github_data.png)

![Verbindung](media/template-content-pack-experience/github_connect.png)

## <a name="parameters"></a>Parameter
Nach der Auswahl des Inhaltspakets wird der Benutzer aufgefordert, Parameter anzugeben (sofern erforderlich). Das Dialogfeld „Parameter“ wird vom Autor während der Erstellung des Inhaltspakets deklarativ festgelegt.

Derzeit ist die Benutzeroberfläche für Parameter sehr einfach: Dropdownlisten können nicht aufgelistet werden, und die Überprüfung von Dateneingaben ist auf reguläre Ausdrücke beschränkt.

![Parameter](media/template-content-pack-experience/github_params.png)

## <a name="credentials"></a>Anmeldeinformationen
Nach der Eingabe der Parameter wird der Benutzer aufgefordert, sich anzumelden.  Wenn die Quelle mehrere Authentifizierungsmethoden unterstützt, wählt der Benutzer die entsprechende Methode aus. Wenn für die Quelle eine Authentifizierung mit OAuth erforderlich ist, wird die Anmeldebenutzeroberfläche des Diensts angezeigt, wenn der Benutzer „Anmelden“ auswählt.  Andernfalls kann der Benutzer im angezeigten Dialogfeld seine Anmeldeinformationen eingeben.

![Anmeldeinformationen](media/template-content-pack-experience/github_login.png)

![Verbindung](media/template-content-pack-experience/github_creds2.png)

## <a name="instantiation"></a>Instanziierung
Nach erfolgter Anmeldung werden die im Inhaltspaket enthaltenen Artefakte (Modell, Berichte und Dashboard) auf der Navigationsleiste angezeigt.  Diese Artefakte werden jedem Konto des Benutzers hinzugefügt.  Die Daten werden asynchron geladen, um das Dataset (Modell) aufzufüllen.  Der Benutzer kann dann das Dashboard, die Berichte und das Modell nutzen.

Standardmäßig ist ein täglicher Aktualisierungszeitplan für den Benutzer konfiguriert, mit dem die Abfragen im Modell neu ausgewertet werden.  Mit den für den Benutzer bereitgestellten Anmeldeinformationen muss ermöglicht werden, dass die Daten ohne seine Anwesenheit aktualisiert werden.

![Instanziierung](media/template-content-pack-experience/github_dashboard.png)

## <a name="exploration-and-monitoring"></a>Untersuchung und Überwachung
Nachdem das Inhaltspaket im Konto des Benutzers aktualisiert wurde, kann dieser die Daten bzw. Einblicke untersuchen und überwachen.

Dies umfasst in der Regel Folgendes:

* Anzeigen und Anpassen des Dashboards
* Anzeigen und Anpassen des Berichts
* Verwenden von Fragen in natürlicher Sprache
* Untersuchen der Daten im Datenmodell im entsprechenden Zeichenbereich

Die Bereitstellung der Modellierung in natürlicher Sprache (Synonyme) und eines verständlichen Modellschemas sollte in Betracht gezogen werden, um die Untersuchung der Daten zu optimieren.

