---
ms.openlocfilehash: 240045c05a35a6583b537b785c6639a39c6aa9d4
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2019
ms.locfileid: "61193828"
---
## <a name="define-roles-and-rules-in-power-bi-desktop"></a>Definieren von Rollen und Regeln in Power BI Desktop
Sie können Rollen und Regeln in Power BI Desktop definieren. Wenn Sie etwas in Power BI veröffentlichen, werden auch die Rollendefinitionen veröffentlicht.

Gehen Sie folgendermaßen vor, wenn Sie Sicherheitsrollen definieren möchten.

1. Importieren Sie Daten in Ihren Power BI Desktop-Bericht, oder konfigurieren Sie eine DirectQuery-Verbindung.
   
   > [!NOTE]
   > Sie können in Power BI Desktop keine Rollen für Analysis Services-Liveverbindungen definieren. Sie müssen sie im Analysis Services-Modell definieren.
   > 
   > 
1. Wählen Sie die Registerkarte **Modellierung** aus.
2. Wählen Sie **Rollen verwalten** aus.
   
   ![](./media/rls-desktop-define-roles/powerbi-desktop-security.png)
4. Wählen Sie **Erstellen** aus.
   
   ![](./media/rls-desktop-define-roles/powerbi-desktop-security-create-role.png)
5. Geben Sie einen Namen für die Rolle an. 
6. Wählen Sie die Tabelle aus, auf die eine DAX-Regel angewendet werden soll.
7. Geben Sie die DAX-Ausdrücke ein. Dieser Ausdruck muss TRUE oder FALSE zurückgeben. Zum Beispiel: [Entitäts-ID] = "Wert".
   
   > [!NOTE]
   > Sie können *username()* innerhalb dieses Ausdrucks verwenden. Beachten Sie, dass *username()* in Power BI Desktop das Format *DOMÄNE\Benutzername* aufweist. Im Power BI-Dienst und im Power BI-Berichtsserver entspricht das Format dem Benutzerprinzipalnamen des Benutzers. Alternativ können Sie *userprincipalname()* verwenden, wodurch der Benutzer immer im Format seines Benutzerprinzipalnamens (*Benutzername\@contoso.com*) zurückgegeben wird.
   > 
   > 
   
   ![](./media/rls-desktop-define-roles/powerbi-desktop-security-create-rule.png)
8. Wählen Sie nach der Erstellung des DAX-Ausdrucks das Häkchen über dem Ausdrucksfeld aus, um den Ausdruck zu überprüfen.
   
   ![](./media/rls-desktop-define-roles/powerbi-desktop-security-validate-dax.png)
9. Wählen Sie **Speichern**.

In Power BI Desktop ist es nicht möglich, Benutzer einer Rolle zuzuweisen. Sie können diese Zuweisung im Power BI-Dienst vornehmen. Sie können die dynamische Sicherheit in Power BI Desktop aktivieren, indem Sie *username()* - oder *userprincipalname()* -DAX-Funktionen verwenden und die richtigen Beziehungen konfigurieren. 

