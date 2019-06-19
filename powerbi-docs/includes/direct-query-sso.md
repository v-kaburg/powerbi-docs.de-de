---
title: Includedatei
description: Includedatei
services: powerbi
author: mgblythe
ms.service: powerbi
ms.topic: include
ms.date: 05/31/2019
ms.author: mblythe
ms.openlocfilehash: 94b6959b6bcbf250e54a353e8b725b6c9e5a2e30
ms.sourcegitcommit: c539726c9c180e899a8a34443e3fda2b9848beb2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/31/2019
ms.locfileid: "66448408"
---
## <a name="single-sign-on"></a>Einmaliges Anmelden

Nachdem Sie ein Azure SQL DirectQuery-Dataset im Dienst veröffentlichen, können Sie einmaliges Anmelden (Single Sign-On, SSO) über Azure AD-OAuth2 (Azure Active Directory) für Endbenutzer aktivieren.

Um SSO zu aktivieren, rufen Sie die Einstellungen für das Dataset auf, öffnen die Registerkarte **Datenquellen**, und aktivieren Sie das Kontrollkästchen „SSO“.

![Dialogfeld zum Konfigurieren von Azure SQL-Datenquellen](media/direct-query-sso/sso-dialog.png)

Wenn die Option „SSO“ aktiviert ist und Benutzer auf Berichte zugreifen, die auf der Datenquelle beruhen, werden deren authentifizierte Azure AD-Anmeldeinformationen von Power BI in den Abfragen an die Azure SQL-Datenbank oder das Data Warehouse gesendet. Dadurch wird sichergestellt, dass die auf Datenquellenebene konfigurierten Sicherheitseinstellungen in Power BI berücksichtigt werden.

Die SSO-Option gilt für alle Datasets, die diese Datenquelle verwenden. Sie hat keine Auswirkungen auf das Authentifizierungsverfahren, das bei Importszenarien verwendet wird.

> [!Note]
> Azure Multi-Factor Authentication (MFA) wird nicht unterstützt. Benutzer, die SSO mit Azure SQL DirectQuery verwenden möchten, müssen von MFA ausgenommen werden.