---
title: Verwalten des Power BI Desktop-Anmeldeformulars durch Administratoren
description: Hier erfahren Sie, wie Sie das Anmeldeformular beim Öffnen von Power BI Desktop verwalten können.
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 11/28/2018
ms.author: davidi
ms.openlocfilehash: a61075993afaa75aea420f55babc773dec075f73
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/15/2019
ms.locfileid: "54280887"
---
# <a name="how-administrators-can-manage-the-power-bi-desktop-sign-in-form"></a>Verwalten des Power BI Desktop-Anmeldeformulars durch Administratoren
Wenn Power BI Desktop erstmalig gestartet wird, wird ein Anmeldeformular geöffnet. Dort können Informationen eingegeben werden, oder es kann die Anmeldung bei Power BI ausgeführt werden, um fortzufahren. Administratoren verwalten dieses Formular mithilfe eines Registrierungsschlüssels. 

![Anmeldeformular für Power BI Desktop](media/desktop-admin-sign-in-form/sign-in-form.png)

Administratoren verwenden den folgenden Registrierungsschlüssel, um das Anmeldeformular zu deaktivieren. Dies kann auch über globale Richtlinien mithilfe von Push an eine gesamte Organisation übertragen werden.

```
Key: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Power BI Desktop
valueName: ShowLeadGenDialog
```

Durch den Wert „0“ wird das Dialogfeld deaktiviert.

Weitere Fragen? [Stellen Sie Ihre Frage in der Power BI-Community.](http://community.powerbi.com/)

