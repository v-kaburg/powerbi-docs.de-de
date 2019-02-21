---
author: mgblythe
ms.service: powerbi
ms.topic: include
ms.date: 02/15/2019
ms.author: mblythe
ms.openlocfilehash: 44ef0aa9d436f3a8a02f9a6b831847d5c996558a
ms.sourcegitcommit: 91ac6185f7026ddbaa925dc54057bb742b4fa411
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/16/2019
ms.locfileid: "56333875"
---
## <a name="limitations"></a>Einschränkungen

Es folgt eine Liste der aktuellen Einschränkungen für die Sicherheit auf Zeilenebene für Cloudmodelle.

* Wenn Sie bereits Rollen und Regeln im Power BI-Dienst definiert haben, müssen Sie diese in Power BI Desktop neu erstellen.

* Sie können Sicherheit auf Zeilenebene (Row Level Security, RLS) nur auf den mithilfe von Power BI Desktop erstellten Datasets definieren. Wenn Sie RLS für mit Excel erstellte Datasets aktivieren möchten, müssen Sie Ihre Dateien zunächst in PBIX-Dateien (Power BI Desktop) konvertieren. [Weitere Informationen](../desktop-import-excel-workbooks.md)

* Es werden nur ETL- und DirectQuery-Verbindungen unterstützt. Live-Verbindungen zu Analysis Services werden im lokalen Modell verarbeitet.

* RLS unterstützt Cortana derzeit nicht.

## <a name="known-issues"></a>Bekannte Probleme

Wenn Sie versuchen, einen Bericht in Power BI Desktop zu veröffentlichen, der zuvor bereits veröffentlicht wurde, erhalten Sie eine Fehlermeldung. Dieses Problem ist bekannt. Das Szenario lautet wie folgt:

1. Anna verfügt über ein Dataset, das im Power BI-Dienst veröffentlicht und für RLS konfiguriert wurde.

1. Anna aktualisiert den Bericht in Power BI Desktop und veröffentlicht ihn erneut.

1. Anna erhält eine Fehlermeldung.

**Problemumgehung:** Veröffentlichen Sie die Power BI Desktop-Datei erneut im Power BI-Dienst, bis dieses Problem behoben ist. Sie erreichen dies, indem Sie auf **Daten abrufen** > **Dateien** klicken.
