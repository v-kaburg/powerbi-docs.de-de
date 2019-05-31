---
ms.openlocfilehash: 3e89344ef1298864b485f465b28c56397a7e1511
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2019
ms.locfileid: "61193816"
---
## <a name="using-the-username-or-userprincipalname-dax-function"></a>Verwenden der DAX-Funktion „username()“ oder „userprincipalname()“
Sie können die DAX-Funktion *username()* oder *userprincipalname()* in Ihrem Dataset verwenden. Sie können beide Funktionen in Ausdrücken in Power BI Desktop verwenden. Wenn Sie Ihr Modell veröffentlichen, wird es im Power BI-Dienst verwendet.

In Power BI Desktop gibt *username()* einen Benutzer im Format *DOMÄNE\Benutzer* und *userprincipalname()* einen Benutzer im Format <em>user@contoso.com</em> zurück.

Im Power BI-Dienst geben sowohl *username()* als auch *userprincipalname()* den Benutzerprinzipalnamen (User Principal Name, UPN) des Benutzers zurück. Dieser ähnelt einer E-Mail-Adresse.

