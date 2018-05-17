## <a name="limitations"></a>Einschränkungen
Es folgt eine Liste der aktuellen Einschränkungen für die Sicherheit auf Zeilenebene für Cloudmodelle.

* Wenn Sie bereits Rollen und Regeln im Power BI-Dienst definiert hatten, müssen Sie diese in Power BI Desktop neu erstellen.
* Sie können RLS nur auf den mithilfe des Power BI Desktop-Clients erstellten Datasets definieren. Wenn Sie RLS für mit Excel erstellte Datasets aktivieren möchten, müssen Sie Ihre Dateien zunächst in PBIX-Dateien konvertieren. [Weitere Informationen](../desktop-import-excel-workbooks.md)
* Es werden nur ETL- und DirectQuery-Verbindungen unterstützt. Live-Verbindungen zu Analysis Services werden im lokalen Modell verarbeitet.
* RLS unterstützt derzeit weder Q&A noch Cortana. Das Q&A-Eingabefeld für Dashboards wird nicht angezeigt, wenn für alle Modelle RLS konfiguriert ist. Das ist zwar geplant, jedoch können wir noch keinen Zeitplan nennen.
* Die externe Freigabe wird zurzeit nicht für Datasets unterstützt, die RLS verwenden.
* Für jedes bestehende Modell beträgt die Maximalzahl der Azure AD-Prinzipale (d.h. der Einzelbenutzer oder Sicherheitsgruppen), die Sicherheitsrollen zugewiesen werden können, 1.000. Um Rollen große Benutzerzahlen zuzuweisen, achten Sie darauf, die Zuweisung an Sicherheitsgruppen statt an Einzelbenutzer vorzunehmen.

## <a name="known-issues"></a>Bekannte Probleme
Wenn Sie versuchen, etwas in Power BI Desktop zu veröffentlichen, das zuvor bereits veröffentlicht wurde, erhalten Sie eine Fehlermeldung. Dieses Problem ist bekannt. Das Szenario lautet wie folgt:

1. Anna verfügt über ein Dataset, das im Power BI-Dienst veröffentlicht wird und für RLS konfiguriert wurde.
2. Anna aktualisiert den Bericht in Power BI Desktop und veröffentlicht ihn erneut.
3. Anna erhält eine Fehlermeldung.

**Lösung:** Veröffentlichen Sie die Power BI Desktop-Datei erneut im Power BI-Dienst, bis dieses Problem behoben ist. Sie erreichen dies, indem Sie auf **Daten abrufen** > **Dateien** klicken. 

