---
title: Verwenden Sie eine alternative e-Mail-Adresse
description: Verwenden Sie eine alternative e-Mail-Adresse
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 04/23/2019
ms.author: mblythe
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 88432f55fc8cfeefa07b66ea68437bbb23f12531
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2019
ms.locfileid: "64906660"
---
# <a name="use-an-alternate-email-address"></a>Verwenden Sie eine alternative e-Mail-Adresse

Wenn Sie sich für Power BI registrieren, müssen Sie eine E-Mail-Adresse angeben. Power BI verwendet diese Adresse standardmäßig, um Ihnen Updates zu den Aktivitäten in diesem Dienst zu senden. Wenn Ihnen beispielsweise ein Benutzer eine Freigabeeinladung sendet, wird diese Adresse verwendet.

Es gibt jedoch Fälle, in denen diese E-Mails an eine andere als die bei der Registrierung verwendete Adresse gesendet werden sollen. Dieser Artikel erläutert, wie Sie in Office 365 und PowerShell eine alternative E-Mail-Adresse angeben. Der Artikel wird auch erläutert, wie Azure Active Directory (Azure AD) eine e-Mail-Adresse auflöst.

> [!NOTE]
> Die Angabe einer alternativen Adresse wirkt sich nicht auf die E-Mail-Adresse aus, die Power BI für Dienstupdates, Newsletter und andere Werbekommunikation verwendet. Diese Benachrichtigungen werden immer an die e-Mail-Adresse gesendet, dass Sie verwendet werden, wenn Sie sich für Power BI haben registriert.

## <a name="use-office-365"></a>Verwenden von Office 365

Um in Office 365 eine alternative Adresse anzugeben, führen Sie die folgenden Schritte aus.

1. Öffnen Sie Ihre [persönliche Office 365-Informationsseite](https://portal.office.com/account/#personalinfo). Wenn die app aufgefordert werden, melden Sie sich mit dem e-Mail-Adresse und das Kennwort für Power BI.

1. Wählen Sie im linken Menü **Persönliche Informationen** aus.

1. Klicken Sie im Abschnitt mit den **Kontaktdetails** auf **Bearbeiten**.

    Wenn Sie Ihre Informationen nicht bearbeiten können, bedeutet dies, dass Ihr Office 365-Administrator Ihre e-Mail-Adresse verwaltet. Wenden Sie sich an Ihren Administrator, um Ihre e-Mail-Adresse zu aktualisieren.

    ![Kontaktdetails](media/service-admin-alternate-email-address-for-power-bi/contact-details.png)

1. In der **alternative e-Mail-Adresse** Geben Sie die e-Mail-Adresse, die Office 365, die für Power BI-Updates verwendet werden soll.

## <a name="use-powershell"></a>Verwenden von PowerShell

Um in PowerShell eine alternative Adresse anzugeben, verwenden Sie den Befehl [Set-AzureADUser](/powershell/module/azuread/set-azureaduser/).

```powershell
Set-AzureADUser -ObjectId john@contoso.com -OtherMails "otheremail@somedomain.com"
```

## <a name="email-address-resolution-in-azure-ad"></a>Auflösung der E-Mail-Adresse in Azure AD

Klicken Sie zum Erfassen von Azure AD AAD-Token für Power BI, können Sie eine der drei verschiedene Typen von e-Mail-Adressen:

* Die Haupt-e-Mail-Adresse, die mit Azure AD-Konto eines Benutzers verknüpft ist

* Die UPN-E-Mail-Adresse (UserPrincipalName)

* Das Attribut für das Array *Andere E-Mail-Adresse*

Power BI wählt anhand der folgenden Kriterien (in der angegebenen Reihenfolge) aus, welche E-Mail-Adresse verwendet werden soll:

1. Wenn das E-Mail-Attribut im Azure AD-Benutzerobjekt vorhanden ist, verwendet Power BI dieses E-Mail-Attribut für die E-Mail-Adresse.

1. Wenn es sich bei der UPN-E-Mail-Adresse *nicht* um eine E-Mail-Adresse der Domäne **\*.onmicrosoft.com** handelt (die Informationen hinter dem Symbol „\@“), verwendet Power BI dieses E-Mail-Attribut für die E-Mail-Adresse.

1. Wenn die *anderen e-Mail-Adresse* arrayattribut im Azure AD-Benutzerobjekt vorhanden ist, und klicken Sie dann Power BI verwendet die erste e-Mail-Adresse in der Liste, (da es eine Liste der e-Mail-Nachrichten in diesem Attribut vorhanden sein kann).

1. Wenn keine der oben genannten Bedingungen vorhanden sind, verwendet Power BI die UPN-Adresse.

Weitere Fragen? [Wenden Sie sich an die Power BI-Community](http://community.powerbi.com/)