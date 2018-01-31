---
title: "Benutzerdefinierte Layouts für eingebettete Inhalte aus Power BI"
description: "Informieren Sie sich über benutzerdefinierte Layouts für Power BI-Inhalte, die Sie in Ihre Anwendung einbetten."
services: powerbi
documentationcenter: 
author: markingmyname
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
ms.date: 12/19/2017
ms.author: maghan
ms.openlocfilehash: 351cfa27cc092af4bc5650a09730bc8a2661abbc
ms.sourcegitcommit: 6e693f9caf98385a2c45890cd0fbf2403f0dbb8a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2018
---
# <a name="custom-layouts"></a>Benutzerdefinierte Layouts


Verwenden Sie benutzerdefinierte Layouts, um einen Bericht mit einem anderen Layout als im ursprünglichen Bericht einzubetten. Indem Sie ein neues Layout definieren, können Sie eine abweichende Seitengröße festlegen sowie die Größe, Position und Sichtbarkeit von Visuals steuern.

Um ein benutzerdefiniertes Layout zu definieren, definieren Sie ein Objekt für benutzerdefinierte Layouts und übergeben dieses an das Einstellungsobjekt in einer Einbettungskonfiguration. Außerdem legen Sie LayoutType auf Custom fest. Weitere Informationen finden Sie unter [Details zur Einbettungskonfiguration](https://github.com/Microsoft/PowerBI-JavaScript/wiki/Embed-Configuration-Details).

```javascript
var embedConfig = {
    ...
    settings: {
            layoutType: models.LayoutType.Custom
    customLayout: {...}
    }
};
```

## <a name="object-definition"></a>Objektdefinition

```javascript
interface ICustomLayout {
  pageSize?: IPageSize;
  displayOption?: DisplayOption;
  pagesLayout?: PagesLayout;
}

enum PageSizeType {
  Widescreen,
  Standard,
  Cortana,
  Letter,
  Custom
}
interface IPageSize {
  type: PageSizeType;
}
interface ICustomPageSize extends IPageSize {
  width?: number;
  height?: number;
}

enum DisplayOption {
  FitToPage,
  FitToWidth,
  ActualSize
}
```

- `pageSize`: Mit pageSize steuern Sie die Größe des Zeichenbereichs (d.h. den weißen Bereich eines Berichts).
- `displayOptions`: Mögliche Werte: FitToWidth, FitToPage und ActualSize. Hiermit wird gesteuert, wie der Zeichenbereich skaliert wird, damit er in den iFrame passt.
- `pagesLayout`: Steuert das Layout für jedes Visual. Weitere Informationen finden Sie unter PagesLayout.

## <a name="pages-layout"></a>Seitenlayout

Indem Sie ein Seitenlayoutobjekt definieren, bestimmen Sie im Grunde ein Layout für jede Seite und ein Layout für jedes Visual auf den einzelnen Seiten.
PageLayout ist optional. Wenn Sie für eine Seite kein Layout definieren, wird das Standardlayout angewendet (das im Bericht gespeichert ist).

pagesLayout ist eine Zuordnung des Seitennamens zum PageLayout-Objekt. Definition:

```javascript
type PagesLayout = { [key: string]: IPageLayout; };
```

PageLayout enthält eine Zuordnung visueller Layouts, die den Namen jedes Visuals einem Visuallayoutobjekt zuordnet:

```javascript
interface IPageLayout {
  visualsLayout: { [key: string]: IVisualLayout; };
}
```

## <a name="visual-layout"></a>Visuallayout

Um eine Visuallayout zu definieren, übergeben Sie eine neue Position und Größe und einen neuen Sichtbarkeitszustand.

```javascript
interface IVisualLayout {
  x?: number;
  y?: number;
  z?: number;
  width?: number;
  height?: number;
  displayState?: IVisualContainerDisplayState;
}

interface IVisualContainerDisplayState {
  mode: VisualContainerDisplayMode;
}

enum VisualContainerDisplayMode {
  Visible,
  Hidden
}
```

- `x,y,z`: Definiert die neue Position des Visuals.
- `width`: Definiert die neue Größe des Visuals.
- `displayState`: Definiert die Sichtbarkeit des Visuals.


## <a name="update-layout"></a>Aktualisieren des Layouts

Mit der updateSettings-Methode können Sie jederzeit während des Ladens des Berichts das Berichtslayout aktualisieren. Weitere Informationen finden Sie unter [Aktualisieren der Einstellungen](https://github.com/Microsoft/PowerBI-JavaScript/wiki/Update-Settings).

## <a name="code-example"></a>Codebeispiel

```javascript
// Get models. models contains enums that can be used.
var models = window['powerbi-client'].models;
    
var embedConfiguration = {
    type: 'report',
    id: '5dac7a4a-4452-46b3-99f6-a25915e0fe55',
    embedUrl: 'https://app.powerbi.com/reportEmbed',
    tokenType: models.TokenType.Embed,
    accessToken: 'H4...rf',
    settings: {
            layoutType: models.LayoutType.Custom
        customLayout: {
            pageSize: {
                type: models.PageSizeType.Custom,
                width: 1600,
                height: 1200
            },
            displayOption: models.DisplayOption.ActualSize,
            pagesLayout: {
                "ReportSection1" : {
                    visualsLayout: {
                        "VisualContainer1": {
                            x: 1,
                            y: 1,
                            z: 1,
                            width: 400,
                            height: 300,
                            displayState: {
                                mode: models.VisualContainerDisplayMode.Visible
                            }
                        },
                        "VisualContainer2": {
                            displayState: {
                                mode: models.VisualContainerDisplayMode.Hidden
                            }
                        },
                    }
                }
            }
        }
    }
};
     
// Get a reference to the embedded report HTML element
var embedContainer = document.getElementById('embedContainer');
 
// Embed the report and display it within the div container.
var report = powerbi.embed(embedContainer, embedConfiguration);

```


## <a name="see-also"></a>Siehe auch

[Einbetten von Power BI-Dashboards, -Berichten und -Kacheln](embedding-content.md)   
[Fragen an die Power BI-Community](https://community.powerbi.com/)

