---
ms.openlocfilehash: eb7cba03daee47f6772fc46be50419731b41765e
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2019
ms.locfileid: "61193840"
---
## <a name="validate-the-roles-within-power-bi-desktop"></a>Überprüfen der Rollen in Power BI Desktop
Nachdem Sie Ihre Rollen erstellt haben, können Sie die Ergebnisse der Rollen in Power BI Desktop testen.

1. Wählen Sie **Als Rollen anzeigen** aus. 

    ![](./media/rls-desktop-view-as-roles/powerbi-desktop-rls-view-as-roles.png)

    Unter **Als Rollen anzeigen** werden die erstellten Rollen angezeigt.

    ![](./media/rls-desktop-view-as-roles/powerbi-desktop-rls-view-as-roles-dialog.png)

3. Wählen Sie eine von Ihnen erstellte Rolle und anschließend **OK** aus, um diese Rolle anzuwenden. Die Berichte rendert dann die Daten, die für diese Rolle relevant sind. 

4. Sie können auch **Anderer Benutzer** auswählen und einen bestimmten Benutzer angeben. Es wird empfohlen, den Benutzerprinzipalnamen (User Principal Name; UPN) anzugeben, da der Power BI-Dienst und der Power BI-Berichtsserver diesen verwenden.

    ![](./media/rls-desktop-view-as-roles/powerbi-desktop-rls-other-user.png)

1. Wählen Sie **OK** aus. Daraufhin wird der Bericht unter Berücksichtigung der für diesen Benutzer sichtbaren Elemente gerendert. 

In Power BI Desktop zeigt die Option **Anderer Benutzer** nur dann unterschiedliche Ergebnisse an, wenn Sie die dynamische Sicherheit auf Ihren DAX-Ausdrücken basierend verwenden. 

