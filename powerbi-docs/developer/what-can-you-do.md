---
title: Welche Möglichkeiten bietet Power BI Entwicklern?
description: Power BI bietet eine Vielzahl von Möglichkeiten für Entwickler. Dies reicht vom Einbetten bis hin zu benutzerdefinierten Visuals und dem Streamen von Datasets.
author: markingmyname
ms.author: maghan
ms.date: 05/03/2018
ms.topic: overview
ms.service: powerbi
ms.component: powerbi-developer
ms.custom: mvc
manager: kfile
ms.openlocfilehash: ee9f5b2e89a1746267090da3485076d67a99d6f9
ms.sourcegitcommit: 638de55f996d177063561b36d95c8c71ea7af3ed
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/17/2018
ms.locfileid: "34290566"
---
# <a name="what-can-developers-do-with-power-bi"></a>Welche Möglichkeiten bietet Power BI Entwicklern?

Entwicklern stehen verschiedene Optionen zur Verfügung, um Power BI-Inhalte in Anwendungen einzuschließen. Hier gehören: **Einbetten mit Power BI**, **benutzerdefinierte visuelle Elemente** und **Übertragen von Daten in Power BI per Push**.

## <a name="embedding"></a>Einbetten
Der Power BI-Dienst (SaaS) und der Power BI Embedded-Dienst in Azure (PaaS) verfügen über APIs zum Einbetten Ihrer Dashboards und Berichte. Dies bedeutet, dass Ihnen eine ganze Reihe von Funktionen und Zugriff auf die neuesten Power BI-Funktionen – z.B. Dashboards, Gateways und App-Arbeitsbereiche – zur Verfügung stehen, wenn Sie Inhalte einbetten.

![PBIE-Beispiel](media/what-can-you-do/what-can-you-do-01.png)

## <a name="develop-custom-visuals"></a>Entwickeln von benutzerdefinierten Visuals
Mit benutzerdefinierten Visuals können Sie Ihre eigenen Visuals für die Verwendung in Power BI-Berichten erstellen. Benutzerdefinierte Visuals werden in TypeScript geschrieben, die auf JavaScript aufsetzt. TypeScript unterstützt einige erweiterte Features und frühzeitigen Zugriff auf ES6/ES7-Funktionen. Stile für Visuals werden mit Cascading Stylesheets (CSS) angewendet. Zur Vereinfachung wird der Less-Vorcompiler verwendet, der einige erweiterte Funktionen unterstützt, u.a. Schachtelung, Variablen, Bedingungen und Schleifen. Wenn Sie diese Funktionen nicht verwenden möchten, können Sie einfachen CSS-Code in der Less-Datei schreiben.

![CV-Beispiel](media/what-can-you-do/powerbi-custom-visual-store.png)

## <a name="push-data-into-power-bi"></a>Übertragen von Daten in Power BI per Push
Sie können die Power BI-API zum Übertragen von Daten per Push zu einem Dataset verwenden. So können Sie eine Zeile in einer Tabelle in einem Dataset hinzufügen Die neuen Daten können dann in Kacheln in einem Dashboard und in Visuals in einem Bericht angezeigt werden.

![Beispiel für das Übertragen von Daten per Push](media/what-can-you-do/powerbi-push-data.png)

## <a name="next-steps"></a>Nächste Schritte
[Einbetten mit Power BI](embedding.md)  
[Veröffentlichen benutzerdefinierter Visualisierungen im Office Store](office-store.md)  
[Übertragen von Daten in ein Dashboard per Push](walkthrough-push-data.md)
