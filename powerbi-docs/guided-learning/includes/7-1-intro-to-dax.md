---
ms.openlocfilehash: 8af5b1cf243d599ab68e9c2db1a3c6003f82c29f
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2019
ms.locfileid: "61273401"
---
Willkommen zum Abschnitt **Geführtes Lernen** von Power BI, das Ihnen eine Einführung in **DAX** geben soll.

**DAX** steht für **Data Analysis Expressions**, und es ist die Formelsprache, die in Power BI verwendet wird (sie wird auch von Power BI im Hintergrund verwendet). Sie finden DAX auch in anderen Angeboten von Microsoft, wie Power Pivot und SSAS Tabular, und diese Sammlung von Themen des Geführten Lernens bezieht sich auf den Gebrauch von DAX in Power BI und kann von Ihnen verwendet werden.

## <a name="dax-and-this-guided-learning-video-series"></a>DAX und die Videoreihe zum geführten Lernen
Das Ziel dieses Abschnitts **Geführtes Lernen** ist es, Ihnen die Grundlagen von DAX zu vermitteln – wie man sich DAX vorstellt, wie es funktioniert und die nützlichsten Funktionen, die vom renommierten DAX-Experten [Alberto Ferrari](http://www.sqlbi.com/learning-dax) erklärt (und mit viel Erfahrung beigebracht) werden.

![Por­t­rät von Alberto Ferrari](media/7-1-intro-to-dax/intro_dax_6_alberto_ferrari.png)

Die Videos in diesem Abschnitt des **geführten Lernens** von **DAX** vermitteln Ihnen DAX-Grundlagen und zwar in Bezug darauf, wie die DAX-Formelsprache funktioniert. Dies ist nützlich, wenn Sie DAX-Formeln von Grund auf neu erstellen und für das Verständnis darüber, wie Power BI diese DAX-Formeln erstellt, während Sie Abfragen im **Abfrage-Editor** erstellen.

## <a name="in-this-video---introduction-to-dax"></a>In diesem Video: Einführung in DAX
DAX-Konzepte sind einfach und unkompliziert, nichtsdestotrotz ist DAX leistungsstark. DAX verwendet eine Reihe spezieller Programmierkonzepte und -muster, die ein umfassendes Verständnis erschweren können. Herkömmlichen Methoden zum Erlernen von Sprachen sind möglicherweise nicht der beste Ansatz für DAX. In diesem Video sollen daher die Konzepte und die Theorie vorgestellt werden, die Ihnen später bei der Arbeit in Power BI helfen.

DAX ist eine *funktionale Sprache*, d.h., der vollständige ausgeführte Code ist in einer Funktion enthalten.

In DAX können Funktionen andere, geschachtelte Funktionen, Bedingungsanweisungen und Wertverweise enthalten. Die Ausführung in DAX beginnt mit der innersten Funktion oder dem innersten Parameter und setzt sich nach außen fort. In Power BI werden DAX-Formeln in einer einzelnen Zeile geschrieben, die richtige Formatierung Ihrer Funktionen ist daher für die Lesbarkeit wichtig.

DAX ist für die Arbeit mit Tabellen, es gelten somit nur zwei primäre Datentypen konzipiert: **Numerische** und **andere**. Bei **numerischen** Daten kann es sich um *ganze Zahlen*, *Dezimalzahlen* oder *Währungen* handeln. **Andere Daten** sind *Zeichenfolgen* und *binäre Objekte*. Wenn Sie also eine DAX-Funktion so erstellen, dass sie für einen Zahlentyp funktioniert, können Sie sicher sein, dass sie auch für alle anderen numerischen Daten verwendet werden kann.

DAX verwendet die Operatorüberladung, d.h., Sie können Datentypen in Ihren Berechnungen mischen und die Ergebnisse werden abhängig vom in der Eingaben verwendeten Datentyp geändert. Die Konvertierung erfolgt automatisch. Dies bedeutet, dass Sie die Datentypen der Spalten, mit denen Sie in Power BI arbeiten, nicht kennen müssen. Es bedeutet aber auch, dass die Konvertierung in einigen Fällen auf unerwartete Weise erfolgen kann. Sie sollten daher die Daten kennen, die Sie verwenden, um sicherzustellen, dass die Operatoren sich wie erwartet verhalten.

Dies ist ein Datentyp in bestimmten, die Sie wahrscheinlich mit viel werden Sie in Power BI arbeiten: **"DateTime"** . **DateTime** wird als Gleitkommazahl mit Integer- und Dezimalzahlkomponenten gespeichert. DateTime kann zur genauen Berechnung jedes Zeitraums nach dem 1. März 1900 verwendet werden.

> Videoinhalt zur Verfügung gestellt von [Alberto Ferrari, SQLBI](http://www.sqlbi.com/learning-dax/?utm_source=powerbi&utm_medium=marketing&utm_campaign=after-summit)
> 
> 

