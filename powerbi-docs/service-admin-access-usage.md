---
title: Suchen nach angemeldeten Power BI-Benutzern
description: Wenn Sie ein mandantenadministrator sind, und um anzuzeigen, die in Power BI angemeldet hat, können Sie die Berichte für die Azure Active Directory Zugriffs- und Nutzungsberichte, erhalten Sie einen Einblick.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 04/23/2019
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: e513607dd89aee15f10145cf62bd461621cc12c0
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2019
ms.locfileid: "64906762"
---
# <a name="find-power-bi-users-that-have-signed-in"></a>Suchen nach angemeldeten Power BI-Benutzern

Wenn Sie ein mandantenadministrator sind, und möchten, finden Sie unter, die bei Verwendung von Power BI angemeldet hat die [Berichte zur Zugriffs- und Nutzungsberichte von Azure Active Directory](/azure/active-directory/reports-monitoring/concept-sign-ins) erhalten Sie einen Einblick.

<iframe width="640" height="360" src="https://www.youtube.com/embed/1AVgh9w9VM8?showinfo=0" frameborder="0" allowfullscreen></iframe>

> [!NOTE]
> Die **Anmeldungen** Bericht enthält nützliche Informationen, aber es nicht ermitteln Sie die Lizenz, die jeder Benutzer hat. Verwenden Sie das Microsoft 365 Admin Center, um Lizenzen anzuzeigen.

## <a name="requirements"></a>Anforderungen

Alle Benutzer – auch Nichtadministratoren – können einen Bericht mit den eigenen Anmeldeaktivitäten sehen. Allerdings müssen die folgenden Anforderungen erfüllt sein, um einen Bericht für alle Benutzer anzuzeigen:

* Ihrem Mandanten muss es sich um eine Azure Active Directory Premium-Lizenz zugeordnet werden.

* Sie müssen eine der folgenden Rollen besitzen: „Globaler Administrator“, „Sicherheitsadministrator“ oder „Sicherheitsleseberechtigter“.

## <a name="use-the-azure-portal-to-view-sign-ins"></a>Anzeigen von Anmeldungen mit dem Azure-Portal

So können Sie Anmeldeaktivitäten anzeigen

1. Wählen Sie im **Azure-Portal** **Azure Active Directory** aus.

1. Wählen Sie unter **Überwachung** **Anmeldungen** aus.
   
    ![Screenshot der Azure-Benutzeroberfläche mit dem Azure Active Directory und Anmeldungen hervorgehoben.](media/service-admin-access-usage/azure-portal-sign-ins.png)

1. Filtern Sie die Anwendung entweder nach **Microsoft Power BI** oder nach **Power BI Gateway**, und wählen Sie **Übernehmen** aus.

    **Microsoft Power BI** Filter auf die Anmeldeaktivität sich an den Dienst beziehen, während **Power BI Gateway** Filter auf die Anmeldeaktivität für das lokale datengateway.
   
    ![Screenshot des Filters bei Anmeldungen das Feld "Anwendungen" hervorgehoben.](media/service-admin-access-usage/sign-in-filter.png)

## <a name="export-the-data"></a>Exportieren der Daten

Sie können [Herunterladen eines Berichts Anmeldung](/azure/active-directory/reports-monitoring/quickstart-download-sign-in-report) in zwei Formaten: eine CSV-Datei oder eine JSON-Datei.

![Screenshot der Schaltfläche "herunterladen".](media/service-admin-access-usage/download-sign-in-data-csv.png)

Am oberen Rand der **Anmeldungen** Bericht wählen **herunterladen** und wählen Sie eine der folgenden Optionen:

* **CSV** zum Herunterladen einer CSV-Datei für die derzeit gefilterten Daten.

* **JSON** zum Herunterladen einer JSON-Datei für die derzeit gefilterten Daten.

## <a name="data-retention"></a>Datenaufbewahrung

Daten zu Anmeldungen sind bis zu 30 Tage verfügbar. Weitere Informationen finden Sie unter [Aufbewahrungsrichtlinien für Azure Active Directory-Berichte](/azure/active-directory/reports-monitoring/reference-reports-data-retention).

## <a name="next-steps"></a>Nächste Schritte

[Verwenden von Überwachung in der Organisation](service-admin-auditing.md)

Weitere Fragen? [Stellen Sie Ihre Frage in der Power BI-Community.](https://community.powerbi.com/)