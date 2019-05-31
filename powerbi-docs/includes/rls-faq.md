---
ms.openlocfilehash: b05b5b0b5212f39b9b47cb63e2fc8522fff2f8e3
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2019
ms.locfileid: "61193807"
---
## <a name="faq"></a>HÄUFIG GESTELLTE FRAGEN
**Frage:** Was geschieht, wenn ich zuvor Rollen und Regeln für ein Dataset in Power BI-Dienst erstellt habe? Werden sie weiterhin funktionieren, wenn ich sie so belasse?  
**Antwort:** Nein. Visualisierungen werden nicht ordnungsgemäß gerendert. Sie müssen die Rollen und Regeln in Power BI Desktop neu erstellen und anschließend im Power BI-Dienst veröffentlichen.

**Frage:** Kann ich solche Rollen für Analysis Services-Datenquellen erstellen?  
**Antwort:** Das ist möglich, wenn Sie die Daten in Power BI Desktop importiert haben. Wenn Sie eine Liveverbindung verwenden, werden Sie RLS nicht im Power BI-Dienst konfigurieren können. Dies wird im lokalen Analysis Services-Modell definiert.

**Frage:** Kann ich mit der RLS die Spalten oder Measures einschränken, auf die Benutzer Zugriff haben?  
**Antwort:** Nein. Wenn ein Benutzer Zugriff auf eine bestimmte Datenzeile hat, sind alle Datenspalten dieser Zeile für ihn sichtbar.

**Frage:** Kann ich mit der RLS Detaildaten in Visuals ausblenden und Zugriff auf in Visuals zusammengefasste Daten erteilen?  
**Antwort:** Nein. Sie sichern einzelne Datenzeilen, für die Benutzer werden jedoch immer entweder die Details oder die zusammengefassten Daten angezeigt.

