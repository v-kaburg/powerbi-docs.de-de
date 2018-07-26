Die Verwendung von **Variablen** ist ein äußerst wichtiger Teil eines DAX-Ausdrucks.

![](media/7-4-dax-expressions/dax-variables_1.png)

Sie können eine Variable überall in einem DAX-Ausdruck definieren. Verwenden Sie dabei die folgenden Syntax:

    VARNAME = RETURNEDVALUE

Bei Variablen kann es sich um einen beliebigen Datentyp handeln, u.a. ganze Tabellen.

Beachten Sie, dass Power BI bei jedem Verweis auf die Variable in Ihrem DAX-Ausdruck den Wert entsprechend der Definition neu berechnen muss. Es wird daher empfohlen, Variablen in einer Funktion nicht zu wiederholen.

> Videoinhalt zur Verfügung gestellt von [Alberto Ferrari, SQLBI](http://www.sqlbi.com/learning-dax)
> 
> 

