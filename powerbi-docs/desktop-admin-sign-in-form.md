---
title: Verwalten des Power BI Desktop-Anmeldeformulars durch Administratoren
description: "Hier erfahren Sie, wie Sie das Anmeldeformular beim Öffnen von Power BI Desktop verwalten können."
services: powerbi
documentationcenter: 
author: davidiseminger
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/17/2017
ms.author: davidi
ms.openlocfilehash: eabb59b32234fce1ba5669b95abb41c4f7e04aa2
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2017
---
# <a name="how-administrators-can-manage-the-power-bi-desktop-sign-in-form"></a>Verwalten des Power BI Desktop-Anmeldeformulars durch Administratoren
Wenn Power BI Desktop erstmalig gestartet wird, wird ein Anmeldeformular geöffnet. Dort können Informationen eingegeben werden, oder es kann die Anmeldung bei Power BI ausgeführt werden, um fortzufahren. Administratoren können dieses Formular mithilfe eines Registrierungsschlüssels verwalten. 

![Anmeldeformular für Power BI Desktop](media/desktop-admin-sign-in-form/sign-in-form.png)

Administratoren können das Anmeldeformular mit dem folgenden Registrierungsschlüssel deaktivieren. Dies kann auch über globale Richtlinien auf die gesamte Organisation ausgeweitet werden.

```
Key: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Power BI Desktop
valueName: ShowLeadGenDialog
```

Durch den Wert „0“ wird das Dialogfeld deaktiviert.

Weitere Fragen? [Stellen Sie Ihre Frage in der Power BI-Community.](http://community.powerbi.com/)

