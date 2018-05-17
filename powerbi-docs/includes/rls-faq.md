## <a name="faq"></a>HÄUFIG GESTELLTE FRAGEN
**Frage:** Was passiert, wenn ich im Power BI-Dienst bereits Rollen und Regeln für ein Dataset erstellt habe? Werden sie weiterhin funktionieren, wenn ich sie so belasse?  
**Antwort:** Nein. Visualisierungen werden nicht ordnungsgemäß gerendert. Sie müssen die Rollen und Regeln in Power BI Desktop neu erstellen und anschließend im Power BI-Dienst veröffentlichen.

**Frage:** Kann ich solche Rollen für Analysis Services-Datenquellen erstellen?  
**Antwort:** Das ist möglich, wenn Sie die Daten in Power BI Desktop importiert haben. Wenn Sie eine Liveverbindung verwenden, werden Sie RLS nicht im Power BI-Dienst konfigurieren können. Dies wird im lokalen Analysis Services-Modell definiert.

**Frage:** Kann ich mit RLS die Spalten oder Measures beschränken, auf die Benutzer Zugriff haben?  
**Antwort:** Nein. Wenn ein Benutzer Zugriff auf eine bestimmte Datenzeile hat, sind alle Datenspalten dieser Zeile für ihn sichtbar.

**Frage:** Kann ich bei RLS Detaildaten in Visuals ausblenden und Zugriff auf in Visuals zusammengefasste Daten erteilen?  
**Antwort:** Nein. Sie sichern einzelne Datenzeilen, für die Benutzer werden jedoch immer entweder die Details oder die zusammengefassten Daten angezeigt.

