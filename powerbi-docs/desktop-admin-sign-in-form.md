---
title: Verwalten des Power BI Desktop-Anmeldeformulars durch Administratoren
description: Hier erfahren Sie, wie Sie das Anmeldeformular beim Öffnen von Power BI Desktop verwalten können.
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 02/21/2019
ms.author: davidi
ms.openlocfilehash: 9e35bbffec40aa57d3097e122bd038659405dfed
ms.sourcegitcommit: 76772a361e6cd4dd88824b2e4b32af30656e69db
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/27/2019
ms.locfileid: "56892296"
---
# <a name="how-administrators-can-manage-the-power-bi-desktop-sign-in-form"></a>Verwalten des Power BI Desktop-Anmeldeformulars durch Administratoren
Wenn Power BI Desktop erstmalig gestartet wird, wird ein Anmeldeformular geöffnet. Dort können Informationen eingegeben werden, oder es kann die Anmeldung bei Power BI ausgeführt werden, um fortzufahren. Administratoren verwalten dieses Formular mithilfe eines Registrierungsschlüssels. 

![Anmeldeformular für Power BI Desktop](media/desktop-admin-sign-in-form/sign-in-form.png)

Administratoren verwenden den folgenden Registrierungsschlüssel, um das Anmeldeformular zu deaktivieren. Dies kann auch über globale Richtlinien mithilfe von Push an eine gesamte Organisation übertragen werden.

```
Key: HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Microsoft Power BI Desktop
valueName: ShowLeadGenDialog
```

Durch den Wert „0“ wird das Dialogfeld deaktiviert.

Weitere Fragen? [Stellen Sie Ihre Frage in der Power BI-Community.](http://community.powerbi.com/)

