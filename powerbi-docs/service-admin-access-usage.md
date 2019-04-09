---
title: Suchen nach angemeldeten Power BI-Benutzern
description: Wenn Sie Mandantenadministrator sind und sehen möchten, wer sich bei Power BI angemeldet hat, können Sie dazu die Azure Active Directory-Zugriffs- und -Verwendungsberichte verwenden.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 11/02/2018
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: 12a15360efbff62c40f5bd1098886ee046661e4f
ms.sourcegitcommit: 5222bc6a8336acc77c8e22db57ea6a7bf7daea57
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59290740"
---
# <a name="find-power-bi-users-that-have-signed-in"></a>Suchen nach angemeldeten Power BI-Benutzern

Wenn Sie Mandantenadministrator sind können Sie mithilfe der [Zugriffs- und Verwendungsberichte von Azure Active Directory](/azure/active-directory/reports-monitoring/concept-sign-ins) sehen, wer sich bei Power BI angemeldet hat.

<iframe width="640" height="360" src="https://www.youtube.com/embed/1AVgh9w9VM8?showinfo=0" frameborder="0" allowfullscreen></iframe>

> [!NOTE]
> Der Aktivitätsbericht enthält zwar nützliche Informationen, identifiziert jedoch nicht den Lizenztyp von Benutzern. Verwenden Sie das Microsoft 365 Admin Center, um Lizenzen anzuzeigen.

## <a name="requirements"></a>Anforderungen

Alle Benutzer – auch Nichtadministratoren – können einen Bericht mit den eigenen Anmeldeaktivitäten sehen. Allerdings müssen die folgenden Anforderungen erfüllt sein, um einen Bericht für alle Benutzer anzuzeigen:

* Ihr Mandant verfügt über eine Azure AD Premium-Lizenz.

* Sie müssen eine der folgenden Rollen besitzen: „Globaler Administrator“, „Sicherheitsadministrator“ oder „Sicherheitsleseberechtigter“.

## <a name="use-the-azure-portal-to-view-sign-ins"></a>Anzeigen von Anmeldungen mit dem Azure-Portal

So können Sie Anmeldeaktivitäten anzeigen

1. Wählen Sie im **Azure-Portal** **Azure Active Directory** aus.

1. Wählen Sie unter **Überwachung** **Anmeldungen** aus.
   
    ![Azure AD-Anmeldungen](media/service-admin-access-usage/azure-portal-sign-ins.png)

1. Filtern Sie die Anwendung entweder nach **Microsoft Power BI** oder nach **Power BI Gateway**, und wählen Sie **Übernehmen** aus.

    **Microsoft Power BI** filtert nach Anmeldeaktivitäten in Bezug auf den Dienst, wohingegen **Power BI Gateway** nach Anmeldeaktivitäten für das spezifische lokale Datengateway filtert.
   
    ![Filtern von Anmeldungen](media/service-admin-access-usage/sign-in-filter.png)

## <a name="export-the-data"></a>Exportieren der Daten

Sie haben zwei Möglichkeiten zum Exportieren der Anmeldedaten: Laden Sie eine CSV-Datei herunter, oder verwenden Sie PowerShell. Wählen Sie oben im Anmeldebericht eine der folgenden Optionen aus:

* **Download** zum Herunterladen einer CSV-Datei für die aktuell gefilterten Daten

* **Skript** zum Herunterladen eines PowerShell-Skripts für die aktuell gefilterten Daten Sie können den Filter im Skript bei Bedarf aktualisieren.

![Herunterladen der CSV-Datei oder des Skripts](media/service-admin-access-usage/download-sign-in-data-csv.png)

## <a name="data-retention"></a>Datenaufbewahrung

Daten zu Anmeldungen sind bis zu 30 Tage verfügbar. Weitere Informationen finden Sie unter [Aufbewahrungsrichtlinien für Azure Active Directory-Berichte](/azure/active-directory/reports-monitoring/reference-reports-data-retention).

## <a name="next-steps"></a>Nächste Schritte

[Verwenden von Überwachung in der Organisation](service-admin-auditing.md)

Weitere Fragen? [Wenden Sie sich an die Power BI-Community.](https://community.powerbi.com/)

