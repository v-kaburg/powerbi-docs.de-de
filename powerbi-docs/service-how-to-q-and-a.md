---
title: Power BI Q&A verwenden
description: Power BI Q&A verwenden
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
editor: 
tags: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 09/25/2017
ms.author: mihart
ms.openlocfilehash: a6736916a4bb2e94c1f5e1e3c3c3e5339cf990ec
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2017
---
# <a name="how-to-use-power-bi-qa"></a>Power BI Q&A verwenden
## <a name="ask-questions-of-your-data-using-natural-language"></a>Fragen in natürlicher Sprache stellen
Zunächst benötigen Sie ein Dashboard. Im Q&A-Fragefeld können Sie Ihre Frage in natürlicher Sprache eingeben. Q&A erkennt die Wörter die Sie eingeben und prüft, wo (in welchem Dataset) die Antwort zu finden ist. Q&A unterstützt Sie mit automatischer Vervollständigung, Neuformulierung und anderen textlichen und visuellen Hilfsmitteln bei der Formulierung Ihrer Frage.

![](media/service-how-to-q-and-a/powerbi-qna.png)

Die Antwort auf Ihre Frage wird als eine interaktive Visualisierung angezeigt und beim Ändern der Frage aktualisiert.

Q&A ist interaktiv und sogar unterhaltsam. Häufig erhalten Sie durch nur eine Frage Antworten auf viele weitere, da die Visualisierungen interessante weitere Verweise enthalten. Sehen Sie sich an, wie Amanda mithilfe von F&A Visualisierungen erstellt, diese erläutert und an Dashboards anheftet.

> [!NOTE]
> Q&A steht auch in der [Microsoft Power BI-App für iOS auf iPads, iPhones und iPod Touch-Geräten](mobile-apps-ios-qna.md) zur Verfügung.
> 
> 

<iframe width="560" height="315" src="https://www.youtube.com/embed/qMf7OLJfCz8?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>

## <a name="use-natural-language-to-ask-questions-about-your-data"></a>Antworten zu Daten auf Fragen in natürlicher Sprache
1. Platzieren Sie den Cursor im Fragefeld. Noch bevor Sie mit der Eingabe beginnen, zeigt Q&A einen neuen Bildschirm mit Vorschlägen für die Formulierung Ihrer Frage an.
   
   ![](media/service-how-to-q-and-a/powerbi-qna-cursor.png)  
   
   Diese Liste enthält:  
   a.  die Fragen, die zur Erstellung von [Kacheln](service-dashboard-tiles.md) dienten, die bereits an das Dashboard angeheftet wurden, und  
   b.  die Namen der Tabellen in dem oder den [zugrunde liegenden Dataset(s)](service-get-data.md).  
   
   Sie können eine dieser Fragen als Ausgangspunkt verwenden und die Frage verfeinern, um die genaue Antwort darauf zu erhalten. Alternativ können Sie einen Tabellennamen zum Formulieren einer neuen Frage verwenden.
2. Wählen Sie aus der Dropdownliste aus, oder geben Sie Ihre Frage ein.  
   
   ![](media/service-how-to-q-and-a/powerbi-qna-list.png)
3. Wenn Sie eine Frage eingeben, wählt Power BI Q&A die optimale [Visualisierung](power-bi-visualization-types-for-reports-and-q-and-a.md), um Ihre Antwort anzuzeigen. Wenn Sie die Frage ändern, wird die Visualisierung dynamisch angepasst. Q&A unterstützt Sie mit automatischer Vervollständigung, Neuformulierung und anderen textlichen und visuellen Hilfsmitteln bei der Formulierung Ihrer Frage.  
   ![](media/service-how-to-q-and-a/powerbi-qna-viz.png)
4. Wenn Sie eine Abfrage eingeben, sucht Power BI in jedem Dataset nach einer Antwort, das über eine Kachel auf diesem Dashboard verfügt.  Wenn alle Kacheln von *DatasetA* stammen, ergibt sich Ihre Antwort ebenfalls aus *DatasetA*.  Wenn Kacheln aus *datasetA* und *datasetB* verfügbar sind, sucht Q&A in beiden Datasets nach der optimalen Antwort.
   
   > [!TIP]
   > Gehen Sie umsichtig vor. Wenn es für *datasetA* nur eine Kachel gibt und Sie diese aus dem Dashboard entfernen, hat Q&A keinen Zugriff mehr auf *datasetA*.
   > 
   > 
5. Wenn Sie mit dem Ergebnis zufrieden sind, [heften Sie die Visualisierung an ein Dashboard an](service-dashboard-pin-tile-from-q-and-a.md), indem Sie das Anheftsymbol in der oberen rechten Ecke auswählen. Wenn das Dashboard für Sie freigegeben wurde oder Bestandteil einer App ist, können Sie die Visualisierung nicht anheften.
   
   ![](media/service-how-to-q-and-a/pbi_qna_finish-typing-question.jpg)

### <a name="tell-qa-which-visualization-to-use"></a>Bestimmten Sie, welche Visualisierung Q&A verwenden soll.
Mit Q&A lassen Sie nicht nur Ihre Daten für sich selbst sprechen, Sie können sogar wählen, wie sie angezeigt werden sollen. Hängen Sie am Ende Ihrer Frage einfach den Zusatz „als <visualization type>“ an.  Beispiel: „Bestandsvolumen nach Werk als Karte anzeigen“ und „Gesamtvolumen als Karte anzeigen“.  Probieren Sie es einfach aus.

## <a name="how-does-qa-know-how-to-answer-questions"></a>Wie kann Q&A Fragen beantworten?
### <a name="which-datasets-does-qa-use"></a>Welche Datasets verwendet Q&A?
Wie kann der Bereich für Fragen und Antworten datenbezogene Fragen beantworten? Q&A bezieht sich auf die Namen der Tabellen, Säulen und berechneten Felder in einer Arbeitsmappe im zugrunde liegenden Dataset. Daher ist es wichtig, wie Sie (oder der Besitzer des Datasets) Dinge benennen! 

Nehmen wir an, Sie haben eine Excel-Tabelle namens „Vertrieb“, die die Spalten „Produkt“, „Monat“, „Verkaufte Einheiten“, „Bruttoumsätze“ und „Gewinn“ enthält. Sie können Fragen zu diesen Entitäten stellen.  Geben Sie z. B. Fragen wie „*Umsätze* anzeigen“, „Gesamter *Gewinn* nach *Monat* “, „*Produkte* nach *verkauften Einheiten* sortieren“ ein.

Q&A beantwortet Fragen, die auf der Organisation Ihres Datasets basieren. Wie sieht die Vorgehensweise bei Daten in Salesforce aus? Wenn Sie eine Verbindung zu Ihrem Konto bei salesforce.com aufbauen, erstellt Power BI automatisch ein Dashboard.  Bevor Sie Fragen in Q&A eingeben, prüfen Sie zunächst die Daten, die in den Dashboardvisualisierungen sowie in der Q&A-Dropdownliste angezeigt werden.

* Wenn die Achsenbeschriftungen und -werte der Visualisierungen Begriffe wie „Umsätze“, „Konto“, „Monat“ und „Chancen“ enthalten, können Sie ganz einfach Fragen wie „Welches *Konto* hat die besten *Chancen* “ oder „*Umsätze* nach Monat als Balkendiagramm anzeigen“ eingeben.
* Enthält die Dropdownliste Begriffe wie „Verkäufer“, „Bundesland“ und „Jahr“, dann werden Fragen wie: „welcher *Verkäufer* verzeichnete die geringsten *Umsätze* in *Hessen* im Jahr *2013* “ zuverlässig beantwortet.

Wenn Sie Website-Leistungsdaten in Google Analytics haben, könnten Sie bei Q&A in Erfahrung bringen, wie viel Zeit auf einer Website verbracht wird, wie häufig einzelne Seiten aufgerufen werden und wie die Benutzerbindung aussieht. Wenn Sie demografische Daten benötigen, können Sie auch Alter und Haushaltseinkommen nach Ort erfragen.

### <a name="which-visualization-does-qa-use"></a>Welche Visualisierung verwendet Q&A?
Q&A wählt die beste Visualisierung basierend auf den angezeigten Daten aus. Manchmal werden Daten in den zugrunde liegenden Datasets als bestimmter Typ oder bestimmte Kategorie definiert. Dadurch weiß Q&A, wie sie angezeigt werden sollen. Wenn Daten z. B. als Datentyp definiert sind, müssen sie wahrscheinlich als Liniendiagramm angezeigt werden. Daten, die als eine Stadt kategorisiert werden, müssen wahrscheinlich als Karte angezeigt werden.

Sie können Q&A auch mitteilen, welche Visualisierung verwendet werden soll, indem Sie Ihrer Frage diese Information hinzufügen. Bedenken Sie jedoch, dass Q&A Daten nicht immer im angeforderten Visualisierungstyp anzeigen kann.

Informationen zu Schlüsselwörtern, die Q&A erkennt, finden Sie unter [Tipps zum Stellen von Fragen](service-q-and-a-tips.md).

## <a name="next-steps"></a>Nächste Schritte
Zurück zu [Q&A in Power BI](service-q-and-a.md)  
[Tutorial: Verwenden von Q&A mit dem Einzelhandelsbeispiel](power-bi-visualization-introduction-to-q-and-a.md)  
[Tipps zum Stellen von Fragen mit Q&A](service-q-and-a-tips.md)  
[Vorbereiten einer Arbeitsmappe für Q&A](service-prepare-data-for-q-and-a.md)  
[Anheften einer Kachel an das Dashboard aus Q&A](service-dashboard-pin-tile-from-q-and-a.md)  

