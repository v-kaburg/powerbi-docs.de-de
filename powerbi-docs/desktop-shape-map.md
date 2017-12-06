---
title: "Verwenden von Flächenkartogrammen in Power BI Desktop (Vorschau)"
description: "Erstellen von relativen Vergleichen von Regionen mithilfe von Flächenkartogrammen in Power BI Desktop"
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
ms.date: 12/06/2017
ms.author: davidi
ms.openlocfilehash: 70cb015b0f5c4aa952c33c6dd94da5292f9678d7
ms.sourcegitcommit: d91436de68a0e833ecff18d976de9d9431bc4121
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/06/2017
---
# <a name="shape-maps-in-power-bi-desktop-preview"></a>Flächenkartogramme in Power BI Desktop (Vorschau)
Erstellen Sie in Power BI Desktop die Visualisierung **Flächenkartogramm**, um relative Vergleiche von Regionen auf einer Karte darzustellen, indem verschiedene Farben für verschiedene Regionen angewendet werden. Im Gegensatz zur Visualisierung **Karte** kann **Flächenkartogramm** keine genauen geografischen Standorte von Datenpunkten auf einer Karte anzeigen. Stattdessen besteht der Hauptzweck dieses Elements darin, relative Vergleiche von Regionen auf einer Karte darzustellen, indem die Regionen unterschiedlich eingefärbt werden.

**Flächenkartogramme** basieren auf ESRI-/TopoJSON-Karten, die über die Funktion verfügen, benutzerdefinierte Karten zu verwenden, die Sie erstellen können, wie z.B. geografische Karten, Sitzordnungen, Grundrisse und andere. Die Funktion, benutzerdefinierte Karten zu verwenden, ist für dieses Vorschaurelease das **Flächenkartogramm** nicht verfügbar. Benutzerdefinierte Karten werden jedoch aktiviert, sobald sich diese Funktion nicht mehr in der Vorschauversion befindet, was voraussichtlich mit dem nächsten monatlichen Update für Power BI Desktop der Fall sein wird.

## <a name="creating-shape-maps"></a>Erstellen von Flächenkartogrammen
Sie können das Steuerelement **Flächenkartogramm** mit den Karten testen, die mit dieser Vorschauversion geliefert werden. Alternativ können Sie eine eigene benutzerdefinierte Karte verwenden, sofern sie die im folgenden Abschnitt **Verwenden benutzerdefinierter Karten** genannten Anforderungen erfüllt.

Die Visualisierung **Flächenkartogramm** befindet sich in der Vorschauversion und muss in Power BI Desktop aktiviert werden. Wählen Sie **Datei > Optionen und Einstellungen > Optionen > Vorschaufeatures** aus, und aktivieren Sie anschließend das Kontrollkästchen bei **Flächenkartogramm**, um **Flächenkartogramm** zu aktivieren. Sie müssen Power BI Desktop neu starten, nachdem Sie die Auswahl vorgenommen haben.

![](media/desktop-shape-map/shape-map_1a.png)

Sobald **Flächenkartogramm** aktiviert ist, klicken Sie auf das Steuerelement **Flächenkartogramm** im Bereich **Visualisierungen**.

![](media/desktop-shape-map/shape-map_2.png)

Power BI Desktop erstellt einen leeren Entwurfszeichenbereich für die Visualisierung **Flächenkartogramm**.

![](media/desktop-shape-map/shape-map_3.png)

Führen Sie die folgenden Schritte aus, um ein **Flächenkartogramm** zu erstellen:

1. Ziehen Sie im Bereich **Felder** ein Datenfeld mit den Regionsnamen (oder Abkürzungen) auf den Bucket **Standort** und eines der Felder, mit denen Daten gemessen werden, auf den Bucket **Werte** (es wird noch keine Karte angezeigt).
   
   > [!NOTE]
> Informationen dazu, wie Sie schnell Kartendaten zum Testen eines **Flächenkartogramms** erhalten, finden Sie weiter unten im Abschnitt **Abrufen von Kartendaten**.
   > 
   > 
   
   ![](media/desktop-shape-map/shape-map_3a.png)
2. Erweitern Sie im Bereich **Formateinstellungen** **Form**, und wählen Sie aus der Dropdownliste **Standardkarten** aus, um Ihre Daten anzuzeigen. Nun erfolgt das Rendering, wie in folgender Abbildung dargestellt.
   
   ![](media/desktop-shape-map/shape-map_3b.png)
   
   > [!NOTE]
> Im Abschnitt **Regionsschlüssel** am Ende dieses Artikels finden Sie eine Sammlung von Tabellen, die Regionsschlüssel für Karten enthalten, die Sie zum Testen des Visuals **Flächenkartogramm** verwenden können.
   > 
   > 
3. Anschließend können Sie im Bereich **Formateinstellungen** die Einstellungen für die Kartenprojektion und den Zoom sowie die Farben der Datenpunkte ändern. Sie können auch die Zoomeinstellungen ändern. Sie können z.B. Farben ändern, Mindest- und Höchstwerte festlegen usw.
   
   ![](media/desktop-shape-map/shape-map_3d.png)
4. Sie können dem Bucket **Legende** auch eine Spalte „Datenkategorie“ hinzufügen und die Kartenregionen basierend auf Kategorien klassifizieren.

## <a name="use-custom-maps"></a>Verwenden benutzerdefinierter Karten
Sie können benutzerdefinierte Karten für das **Flächenkartogramm** verwenden, sofern sie das **TopoJSON**-Format aufweisen. Wenn die Karte in einem anderen Format vorliegt, können Sie mit Onlinetools, z.B. [**Map Shaper**](http://mapshaper.org/), die *Shape-Dateien* oder *GeoJSON*-Karten in das **TopoJSON**-Format konvertieren.

Um die **TopoJSON**-Kartendatei zu verwenden, fügen Sie dem Bericht ein visuelles ShapeMap-Element hinzu, und fügen Sie den Buckets *Standort* und *Werte* Daten hinzu. Erweitern Sie dann im Bereich **Visualisierungen**, in dem der Abschnitt **Format** (das Pinselsymbol, in der folgenden Abbildung als (1) dargestellt) ausgewählt ist, den Abschnitt **Form**, und wählen Sie **+ Karte hinzufügen** aus.

![](media/desktop-shape-map/shape-map_6.png)

## <a name="getting-map-data"></a>Abrufen von Kartendaten
Um schnell Daten in ein Modell abzurufen, um **Flächenkartogramm** zu testen, können Sie eine der Tabellen am Ende dieses Artikels kopieren und anschließend auf dem Menüband **Start** **Daten eingeben** auswählen.

![](media/desktop-shape-map/shape-map_4.png)

Sie können die Tabelle anschließend in Power BI Desktop einfügen. Die oberste Zeile wird automatisch als Überschrift identifiziert.

![](media/desktop-shape-map/shape-map_5.png)

Sie können eine neue Spalte einfach hinzufügen, indem Sie einen neuen Spaltennamen (in die leere Spalte auf der rechten Seite) eingeben und anschließend wie in Excel jeder Zelle Werte hinzufügen. Wenn Sie damit fertig sind, wählen Sie **Laden** aus, und die Tabelle wird dem Datenmodell von Power BI Desktop hinzugefügt.

> [!NOTE]
> Verwenden Sie bei der Arbeit mit Ländern oder Regionen das dreistellige Buchstabenkürzel, um sicherzustellen, dass die Geocodierung in Kartenvisualisierungen ordnungsgemäß funktioniert. Verwenden Sie *nicht* die zweistelligen Kürzel, da einige Länder oder Regionen sonst unter Umständen nicht ordnungsgemäß erkannt werden.
> 
> Falls Sie nur über zweistellige Kürzel verfügen, informieren Sie sich in [diesem externen Blogbeitrag](https://blog.ailon.org/how-to-display-2-letter-country-data-on-a-power-bi-map-85fc738497d6#.yudauacxp) darüber, wie Sie Ihren zweistelligen Länder-/Regionskürzeln die dreistelligen Länder-/Regionskürzel zuordnen.
> 
> 

## <a name="preview-behavior-and-requirements"></a>Vorschauverhalten und -anforderungen
Für dieses Vorschaurelease von **Flächenkartogramm** gibt es einige Bedingungen und Anforderungen:

* Die Visualisierung **Flächenkartogramm** befindet sich in der Vorschauversion und muss in Power BI Desktop aktiviert werden. Wählen Sie **Datei > Optionen und Einstellungen > Optionen > Vorschaufeatures** aus, und aktivieren Sie anschließend das Kontrollkästchen bei **Flächenkartogramm**, um **Flächenkartogramm** zu aktivieren.
* Derzeit muss auch der Bucket **Werte** festgelegt sein, damit die Klassifizierung **Legende** ordnungsgemäß funktioniert. Dieses Verhalten soll im endgültigen Release von **Flächenkartogramm** verbessert werden.
* Die endgültige Releaseversion von **Flächenkartogramm** wird über eine Benutzeroberfläche verfügen, die die Kartenschlüssel der aktuell ausgewählten Karte anzeigt. In dieser Vorschau können Sie die Kartenregionsschlüssel über die Tabellen erhalten, die im folgenden Abschnitt **Regionsschlüssel** dieses Artikels aufgelistet sind.

## <a name="region-keys"></a>Regionsschlüssel
Verwenden Sie die folgenden **Regionsschlüssel** in diesem Vorschaurelease, um **Flächenkartogramm** zu testen.

### <a name="australia-states"></a>Australia: States
| id | abbr | iso | name | postal |
| --- | --- | --- | --- | --- |
| au-wa |WA |AU-WA |Western Australia |WA |
| au-vic |Vic |AU-VIC |Victoria |VIC |
| au-tas |Tas |AU-TAS |Tasmania |TAS |
| au-sa |SA |AU-SA |South Australia |SA |
| au-qld |Qld |AU-QLD |Queensland |QLD |
| au-nt |NT |AU-NT |Northern Territory |NT |
| au-nsw |NSW |AU-NSW |New South Wales |NSW |
| au-act |ACT |AU-ACT |Australian Capital Territory |ACT |

### <a name="austria-states"></a>Austria: States
| id | iso | name | name-en | postal |
| --- | --- | --- | --- | --- |
| at-wi |AT-9 |Wien |Vienna |WI |
| at-vo |AT-8 |Vorarlberg |Vorarlberg |VO |
| at-tr |AT-7 |Tirol |Tyrol |TR |
| at-st |AT-6 |Steiermark |Styria |ST |
| at-sz |AT-5 |Salzburg |Salzburg |SZ |
| at-oo |AT-4 |Oberösterreich |Upper Austria |OO |
| at-no |AT-3 |Niederösterreich |Lower Austria |NO |
| at-ka |AT-2 |Kärnten |Carinthia |KA |
| at-bu |AT-1 |Burgenland |Burgenland |BU |

### <a name="brazil-states"></a>Brazil: States
| id |
| --- |
| Tocantins |
| Pernambuco |
| Goias |
| Sergipe |
| Sao Paulo |
| Santa Catarina |
| Roraima |
| Rondonia |
| Rio Grande do Sul |
| Rio Grande do Norte |
| Rio de Janeiro |
| Piaui |
| Parana |
| Paraiba |
| Para |
| Minas Gerais |
| Mato Grosso |
| Maranhao |
| Mato Grosso do Sul |
| Distrito Federal |
| Ceara |
| Espirito Santo |
| Bahia |
| Amazonas |
| Amapa |
| Alagoas |
| Acre |
| Litigated Zone 1 |
| Litigated Zone 2 |
| Litigated Zone 3 |
| Litigated Zone 4 |

### <a name="canada-provinces"></a>Canada: Provinces
| id | iso | name | postal |
| --- | --- | --- | --- |
| ca-nu |CA-NU |Nunavut |NU |
| ca-nt |CA-NT |Northwest Territories |NT |
| ca-yt |CA-YT |Yukon |YT |
| ca-sk |CA-SK |Saskatchewan |SK |
| ca-qc |CA-QC |Quebec |QC |
| ca-pe |CA-PE |Prince Edward Island |PE |
| ca-on |CA-ON |Ontario |ON |
| ca-ns |CA-NS |Nova Scotia |NS |
| ca-nl |CA-NL |Newfoundland and Labrador |NL |
| ca-nb |CA-NB |New Brunswick |NB |
| ca-mb |CA-MB |Manitoba |MB |
| ca-bc |CA-BC |British Columbia |BC |
| ca-ab |CA-AB |Alberta |AB |

### <a name="france-regions"></a>France: Regions
| id | name | name-en |
| --- | --- | --- |
| Alsace |Alsace |Alsace |
| Rhone-Alpes |Rhône-Alpes |Rhone-Alpes |
| Provence-Alpes-Cote d'Azur |Provence-Alpes-Côte d'Azur |Provence-Alpes-Cote d'Azur |
| Poitou-Charentes |Poitou-Charentes |Poitou-Charentes |
| Picardie |Picardie |Picardy |
| Pays de la Loire |Pays de la Loire |Pays de la Loire |
| Nord-Pas-de-Calais |Nord-Pas-de-Calais |Nord-Pas-de-Calais |
| Midi-Pyrenees |Midi-Pyrénées |Midi-Pyrenees |
| Lorraine |Lorraine |Lorraine |
| Limousin |Limousin |Limousin |
| Languedoc-Roussillon |Languedoc-Roussillon |Languedoc-Roussillon |
| Ile-del-France |Île-de-France |Ile-de-France |
| Haute-Normandie |Haute-Normandie |Upper Normandy |
| Franche-Comte |Franche-Comté |Franche-Comte |
| Corse |Corse |Corsica |
| Champagne-Ardenne |Champagne-Ardenne |Champagne-Ardenne |
| Centre-Val de Loire |Centre-Val de Loire |Centre-Val de Loire |
| Bretagne |Bretagne |Brittany |
| Bourgogne |Bourgogne |Burgundy |
| Basse-Normandie |Basse-Normandie |Lower Normandy |
| Auvergne |Auvergne |Auvergne |
| Aquitaine |Aquitaine |Aquitaine |

### <a name="germany-states"></a>Germany: States
| id | iso | name | name-en | postal |
| --- | --- | --- | --- | --- |
| de-be |DE-BE |Berlin |Berlin |BE |
| de-th |DE-TH |Thüringen |Thuringia |TH |
| de-st |DE-ST |Sachsen-Anhalt |Saxony-Anhalt |ST |
| de-sn |DE-SN |Sachsen |Saxony |SN |
| de-mv |DE-MV |Mecklenburg-Vorpommern |Mecklenburg-Vorpommern |MV |
| de-bb |DE-BB |Brandenburg |Brandenburg |BB |
| de-sh |DE-SH |Schleswig-Holstein |Schleswig-Holstein |SH |
| de-sl |DE-SL |Saarland |Saarland |SL |
| de-rp |DE-RP |Rheinland-Pfalz |Rhineland-Palatinate |RP |
| de-nw |DE-NW |Nordrhein-Westfalen |North Rhine-Westphalia |NW |
| de-ni |DE-NI |Niedersachsen |Lower Saxony |NI |
| de-he |DE-HE |Hessen |Hesse |HE |
| de-hh |DE-HH |Hamburg |Hamburg |HH |
| de-hb |DE-HB |Bremen |Bremen |HB |
| de-by |DE-BY |Bayern |Bavaria |BY |
| de-bw |DE-BW |Baden-Württemberg |Baden-Wurttemberg |BW |

### <a name="ireland-counties"></a>Ireland: Counties
| id |
| --- |
| Wicklow |
| Wexford |
| Westmeath |
| Waterford |
| Sligo |
| Tipperary |
| Roscommon |
| Offaly |
| Monaghan |
| Meath |
| Mayo |
| Louth |
| Longford |
| Limerick |
| Leitrim |
| Laoighis |
| Kilkenny |
| Kildare |
| Kerry |
| Galway |
| Dublin |
| Donegal |
| Cork |
| Clare |
| Cavan |
| Carlow |

### <a name="italy-regions"></a>Italy: Regions
| id | iso | name | name-en | postal |
| --- | --- | --- | --- | --- |
| it-vn |IT-34 |Veneto |Veneto |VN |
| it-vd |IT-23 |Valle d'Aosta |Aosta Valley |VD |
| it-um |IT-55 |Umbria |Umbria |UM |
| it-tt |IT-32 |Trentino-Alto Adige |Trentino-South Tyrol |TT |
| it-tc |IT-52 |Toscana |Tuscany |TC |
| it-sc |IT-82 |Sicilia |Sicily |SC |
| it-sd |IT-88 |Sardegna |Sardinia |SD |
| it-pm |IT-21 |Piemonte |Piedmont |PM |
| it-ml |IT-67 |Molise |Molise |ML |
| it-mh |IT-57 |Marche |Marche |MH |
| it-lm |IT-25 |Lombardia |Lombardy |LM |
| it-lg |IT-42 |Liguria |Liguria |LG |
| it-lz |IT-62 |Lazio |Lazio |LZ |
| it-fv |IT-36 |Friuli-Venezia Giulia |Friuli-Venezia Giulia |FV |
| it-er |IT-45 |Emilia-Romagna |Emilia-Romagna |ER |
| it-cm |IT-72 |Campania |Campania |CM |
| it-lb |IT-78 |Calabria |Calabria |LB |
| it-bc |IT-77 |Basilicata |Basilicata |BC |
| it-pu |IT-75 |Apulia |Puglia |PU |
| it-ab |IT-65 |Abruzzo |Abruzzo |AB |

### <a name="mexico-states"></a>Mexico: States
| id | abreviatura | iso | name | name-en | postal |
| --- | --- | --- | --- | --- | --- |
| mx-zac |Zac. |MX-ZAC |Zacatecas |Zacatecas |ZA |
| mx-yuc |Yuc. |MX-YUC |Yucatán |Yucatan |YU |
| mx-ver |Ver. |MX-VER |Veracruz |Veracruz |VE |
| mx-tla |Tlax. |MX-TLA |Tlaxcala |Tlaxcala |TL |
| mx-tam |Tamps. |MX-TAM |Tamaulipas |Tamaulipas |TM |
| mx-tab |Tab. |MX-TAB |Tabasco |Tabasco |TB |
| mx-son |Son. |MX-SON |Sonora |Sonora |SO |
| mx-sin |Sin. |MX-SIN |Sinaloa |Sinaloa |SI |
| mx-slp |S.L.P. |MX-SLP |San Luis Potosí |San Luis Potosi |SL |
| mx-roo |Q.R. |MX-ROO |Quintana Roo |Quintana Roo |QR |
| mx-que |Qro. |MX-QUE |Querétaro |Queretaro |QE |
| mx-pue |Pue. |MX-PUE |Puebla |Puebla |PU |
| mx-oax |Oax. |MX-OAX |Oaxaca |Oaxaca |OA |
| mx-nle |N.L. |MX-NLE |Nuevo León |Nuevo Leon |NL |
| mx-nay |Nay. |MX-NAY |Nayarit |Nayarit |NA |
| mx-mor |Mor. |MX-MOR |Morelos |Morelos |MR |
| mx-mic |Mich. |MX-MIC |Michoacán |Michoacan |MC |
| mx-mex |Méx. |MX-MEX |Estado de México |Mexico State |MX |
| mx-jal |Jal. |MX-JAL |Jalisco |Jalisco |JA |
| mx-hid |Hgo. |MX-HID |Hidalgo |Hidalgo |HI |
| mx-gro |Gro. |MX-GRO |Guerrero |Guerrero |GR |
| mx-gua |Gto. |MX-GUA |Guanajuato |Guanajuato |GT |
| mx-dur |Dgo. |MX-DUR |Durango |Durango |DU |
| mx-dif |Col. |MX-DIF |Ciudad de México |Mexico City |DF |
| mx-col |Coah. |MX-COL |Colima |Colima |CL |
| mx-coa |Chis. |MX-COA |Coahuila |Coahuila |CA |
| mx-chh |Chih. |MX-CHH |Chihuahua |Chihuahua |CH |
| mx-chp |CDMX. |MX-CHP |Chiapas |Chiapas |CP |
| mx-cam |Camp. |MX-CAM |Campeche |Campeche |CM |
| mx-bcs |B.C.S. |MX-BCS |Baja California Sur |Baja California Sur |BS |
| mx-bcn |B.C. |MX-BCN |Baja California |Baja California |BN |
| mx-agu |Ags. |MX-AGU |Aguascalientes |Aguascalientes |AG |

### <a name="netherlands-provinces"></a>Netherlands: Provinces
| id | iso | name | name-en |
| --- | --- | --- | --- |
| nl-zh |NL-ZH |Zuid-Holland |South Holland |
| nl-ze |NL-ZE |Zeeland |Zeeland |
| nl-ut |NL-UT |Utrecht |Utrecht |
| nl-ov |NL-OV |Overijssel |Overijssel |
| nl-nh |NL-NH |Noord-Holland |North Holland |
| nl-nb |NL-NB |Noord-Brabant |North Brabant |
| nl-li |NL-LI |Limburg |Limburg |
| nl-gr |NL-GR |Groningen |Groningen |
| nl-ge |NL-GE |Gelderland |Gelderland |
| nl-fr |NL-FR |Fryslân |Friesland |
| nl-fl |NL-FL |Flevoland |Flevoland |
| nl-dr |NL-DR |Drenthe |Drenthe |

### <a name="uk-countries"></a>UK: Countries
| id | iso | name |
| --- | --- | --- |
| gb-wls |GB-WLS |Wales |
| gb-sct |GB-SCT |Scotland |
| gb-nir |GB-NIR |Northern Ireland |
| gb-eng |GB-ENG |England |

### <a name="usa-states"></a>USA: States
| id | name | postal |
| --- | --- | --- |
| us-mi |Michigan |MI |
| us-ak |Alaska |AK |
| us-hi |Hawaii |HI |
| us-fl |Florida |FL |
| us-la |Louisiana |LA |
| us-ar |Arkansas |AR |
| us-sc |South Carolina |SC |
| us-ga |Georgia |GA |
| us-ms |Mississippi |MS |
| us-al |Alabama |AL |
| us-nm |New Mexico |NM |
| us-tx |Texas |TX |
| us-tn |Tennessee |TN |
| us-nc |North Carolina |NC |
| us-ok |Oklahoma |OK |
| us-az |Arizona |AZ |
| us-mo |Missouri |MO |
| us-va |Virginia |VA |
| us-ks |Kansas |KS |
| us-ky |Kentucky |KY |
| us-co |Colorado |CO |
| us-md |Maryland |MD |
| us-wv |West Virginia |WV |
| us-de |Delaware |DE |
| us-dc |District of Columbia |DC |
| us-il |Illinois |IL |
| us-oh |Ohio |OH |
| us-ca |California |CA |
| us-ut |Utah |UT |
| us-nv |Nevada |NV |
| us-in |Indiana |IN |
| us-nj |New Jersey |NJ |
| us-ri |Rhode Island |RI |
| us-ct |Connecticut |CT |
| us-pa |Pennsylvania |PA |
| us-ny |New York |NY |
| us-ne |Nebraska |NE |
| us-ma |Massachusetts |MA |
| us-ia |Iowa |IA |
| us-nh |New Hampshire |NH |
| us-or |Oregon |OR |
| us-mn |Minnesota |MN |
| us-vt |Vermont |VT |
| us-id |Idaho |ID |
| us-wi |Wisconsin |WI |
| us-wy |Wyoming |WY |
| us-sd |South Dakota |SD |
| us-nd |North Dakota |ND |
| us-me |Maine |ME |
| us-mt |Montana |MT |
| us-wa |Washington |WA |

