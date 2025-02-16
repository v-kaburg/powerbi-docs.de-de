---
title: Herstellen einer Verbindung mit Azure und Abrufen von Kosten- und Nutzungsdaten über Power BI Desktop
description: Einfaches Herstellen einer Verbindung mit Azure und Erhalten von Einblicken in Verbrauch und Verwendung mithilfe von Power BI Desktop
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 12/06/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 4c2ef62dc3ea8aac9c4a0d30ba4dba58e2279490
ms.sourcegitcommit: 57a12aa42c8549debc60ff1c8e78533dc42e1b86
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/03/2019
ms.locfileid: "66469818"
---
# <a name="analyze-azure-cost-and-usage-data-in-power-bi-desktop"></a>Analysieren von Kosten- und Nutzungsdaten für Azure in Power BI Desktop

Power BI Desktop kann eine Verbindung mit Azure herstellen und detaillierte Daten zur Nutzung des Azure-Diensts durch Ihre Organisation abrufen. Auf der Grundlage dieser Daten können Sie benutzerdefinierte Berichte und Measures erstellen, die Ihnen dabei helfen, Ihre Azure-Ausgaben zu analysieren und besser zu verstehen.

Power BI unterstützt aktuell die Verbindungsherstellung mit Abrechnungskonten vom Typ „Enterprise Agreement“ und „Kundenvertrag“.

* **Enterprise Agreement**-Benutzer müssen für die Verbindungsherstellung den **Azure Consumption Insights-Connector** verwenden.

* Benutzer mit **Kundenvertragskonto** müssen für die Verbindungsherstellung den **Azure Cost Management-Connector** verwenden.

## <a name="connect-with-azure-consumption-insights"></a>Herstellen einer Verbindung mit Azure Consumption Insights

Mit Azure Consumption Insights können Sie eine Verbindung mit Azure Enterprise Agreement-Abrechnungskonten herstellen.

In diesem Abschnitt erfahren Sie, wie Sie die benötigten Daten abrufen und die Migration vom Azure Enterprise-Connector durchführen. Darüber hinaus finden Sie hier eine Übersicht über die in der **ACI**-API (Azure Consumption Insights) verfügbaren *Nutzungsdetailspalten*.

Zum erfolgreichen Herstellen einer Verbindung mit dem **Azure Consumption Insights**-Connector benötigen Sie Zugriff auf die Enterprise-Features im Azure-Portal.

Um mithilfe des **Azure Consumption Insights**-Connectors eine Verbindung herzustellen, klicken Sie im Menüband **Start** von **Power BI Desktop** auf **Daten abrufen**. Wählen Sie in den Kategorien auf der linken Seite **Onlinedienste** aus. Anschließend wird **Microsoft Azure Consumption Insights (Beta)** angezeigt. Wählen Sie **Verbinden** aus.

![](media/desktop-connect-azure-consumption-insights/azure-consumption-insights_01b.png)

Geben Sie im daraufhin angezeigten Dialogfeld Ihre *Registrierungsnummer* ein.

![](media/desktop-connect-azure-consumption-insights/azure-consumption-insights_02.png)

* Sie finden Ihre Registrierungsnummer im [Azure Enterprise-Portal](https://ea.azure.com) an der in der folgenden Abbildung dargestellten Position:

  ![](media/desktop-connect-azure-consumption-insights/azure-consumption-insights_08.png)

  Diese Version des Connectors unterstützt nur Enterprise-Registrierungen über https://ea.azure.com. Registrierungen in China werden derzeit nicht unterstützt.

Geben Sie anschließend Ihren *Zugriffsschlüssel* an, um die Verbindung herzustellen.

![](media/desktop-connect-azure-consumption-insights/azure-consumption-insights_03.png)

* Sie finden den Zugriffsschlüssel für die Registrierung im [Azure Enterprise-Portal](https://ea.azure.com).

  ![](media/desktop-connect-azure-consumption-insights/azure-consumption-insights_09.png)

Sobald Sie Ihren *Zugriffsschlüssel* angegeben und **Verbinden** ausgewählt haben, wird ein **Navigator**-Fenster geöffnet, in dem die 9 für Sie verfügbaren Tabellen angezeigt werden:
* **Budgets:** Enthält Budgetdetails zur Anzeige der tatsächlichen Kosten oder Nutzung im Vergleich zu vorhandenen Budgetzielen.
* **MarketPlace:** Hier werden die nutzungsbasierten Azure Marketplace-Gebühren angezeigt.
* **PriceSheets:** Zeigt die geltenden Preise nach Verbrauchseinheit für eine Registrierung an.
* **RICharges:** Hier werden die Gebühren für Ihre reservierten Instanzen in den letzten 24 Monaten angezeigt.
* **RIRecommendations_Single:** Zeigt basierend auf Ihren Nutzungstrends für ein einzelnes Abonnement in den letzten 7, 30 oder 60 Tagen Kaufempfehlungen für reservierte Instanzen an.
* **RIRecommendations_Shared:** Zeigt basierend auf Ihren Nutzungstrends für alle Ihre Abonnement in den letzten 7, 30 oder 60 Tagen Kaufempfehlungen für reservierte Instanzen an.
* **RIUsage:** Hier werden ausführliche Informationen zum Verbrauch für Ihre vorhandenen reservierten Instanzen im letzten Monat angezeigt.
* **Summaries:** Bietet eine monatliche Übersicht über Salden, neue Käufe, Azure Marketplace-Dienstgebühren, Anpassungen und Überschreitungsgebühren.
* **UsageDetails:** Zeigt eine Aufschlüsselung der verbrauchten Mengen und der geschätzten Kosten für eine Registrierung an.

Sie können neben jeder Tabelle ein Kontrollkästchen aktivieren, um eine Vorschau anzuzeigen. Sie können eine oder mehrere Tabellen auswählen, indem Sie das Kontrollkästchen neben dem Tabellennamen aktivieren, und dann **Laden** wählen.

![](media/desktop-connect-azure-consumption-insights/azure-consumption-insights_04b.png)

> [!NOTE]
> Die Tabellen *Summaries* und *PriceSheets* sind nur für den API-Schlüssel auf Registrierungsebene verfügbar. Standardmäßig sind die Daten für die Tabellen *UsageDetails* und *PriceSheets* die Daten des aktuellen Monats. Die Tabellen *Summaries* und *Marketplace* sind nicht auf den aktuellen Monat beschränkt.
>
>

Wenn Sie **Laden** auswählen, werden die Daten in **Power BI Desktop** geladen.

![](media/desktop-connect-azure-consumption-insights/azure-consumption-insights_05.png)

Nachdem die von Ihnen ausgewählten Daten geladen wurden, werden im Bereich **Felder** die von Ihnen ausgewählten Tabellen und Felder angezeigt.

![](media/desktop-connect-azure-consumption-insights/azure-consumption-insights_06.png)

## <a name="using-azure-consumption-insights"></a>Verwenden von Azure Consumption Insights
Um den **Azure Consumption Insights**-Connector zu verwenden, benötigen Sie Zugriff auf die Enterprise-Features im Azure-Portal.

Nachdem Sie mithilfe des **Azure Consumption Insights**-Connectors Daten erfolgreich geladen haben, können Sie mit dem **Abfrage-Editor** eigene benutzerdefinierte Measures und Spalten erstellen sowie Visuals, Berichte und Dashboards erstellen, die Sie im **Power BI-Dienst** freigeben können.

Azure enthält eine Sammlung benutzerdefinierter Beispielabfragen, die Sie mit einer leeren Abfrage abrufen können. Wählen Sie hierzu im Menüband **Start** von **Power BI Desktop** den Dropdownpfeil in **Daten abrufen** aus, und wählen Sie dann **Leere Abfrage**. Sie können hierzu auch den **Abfrage-Editor** verwenden, indem Sie auf der linken Seite im Bereich **Abfragen** mit der rechten Maustaste klicken und im daraufhin angezeigten Menü **Neue Abfrage > Leere Abfrage** auswählen.

Geben Sie in der **Bearbeitungsleiste** Folgendes ein:

    = MicrosoftAzureConsumptionInsights.Contents

Wie Sie der folgenden Abbildung entnehmen können, wird eine Sammlung von Beispielen angezeigt:

![](media/desktop-connect-azure-consumption-insights/azure-consumption-insights_07.png)

Gehen Sie beim Arbeiten mit Berichten und Erstellen von Abfragen wie folgt vor:

* Verwenden Sie zum Definieren der Anzahl von Monaten ab dem aktuellen Datum *numberOfMonth*.
  * Verwenden Sie zum Darstellen der Anzahl von Monaten ab dem aktuellen Datum, die Sie importieren möchten, einen Wert zwischen 1 und 36. Es wird empfohlen, Daten von nicht mehr als 12 Monaten abzurufen, um das Überschreiten von Importeinschränkungen und der Menge der für Abfragen in Power BI zulässigen Daten zu vermeiden.
* Verwenden Sie *startBillingDataWindow* und *endBillingDataWindow*, um einen Zeitraum von Monaten in einem historischen Zeitfenster zu definieren.
* *numberOfMonth* darf *nicht* zusammen mit *startBillingDataWindow* oder *endBillingDataWindow* verwendet werden.

## <a name="migrating-from-the-azure-enterprise-connector"></a>Migrieren vom Azure Enterprise-Connector
Einige Kunden haben Visuals mit dem *Azure Enterprise-Connector (Beta)* erstellt, dessen Unterstützung demnächst eingestellt wird, da er durch den **Azure Consumption Insights**-Connector ersetzt wird. Der **Azure Consumption Insights**-Connector verfügt u.a. über die folgenden Features und Verbesserungen:

* Zusätzliche verfügbare Datenquellen für *Saldozusammenfassung* und *Marketplace-Einkäufe*
* Neue und verbesserte Parameter, z.B. *startBillingDataWindow* und *endBillingDataWindow*
* Bessere Leistung und Reaktionsfähigkeit

In den folgenden Schritten wird der Wechsel zu dem neueren **Azure Consumption Insights**-Connector gezeigt, um es Kunden zu ermöglichen, ihre bereits erstellten benutzerdefinierten Dashboards oder Berichte weiterzuverwenden.

### <a name="step-1-connect-to-azure-using-the-new-connector"></a>Schritt 1: Mithilfe des neuen Connectors eine Verbindung mit Azure herstellen
Der erste Schritt ist das Herstellen einer Verbindung mithilfe des **Azure Consumption Insights**- Connectors, der weiter oben in diesem Artikel ausführlich beschrieben wurde. Wählen Sie in diesem Schritt im Menüband **Start** von **Power BI Desktop** die Option **Daten abrufen > Leere Abfrage** aus.

### <a name="step-2-use-the-advanced-editor-to-create-a-query"></a>Schritt 2: Im Erweiterten Editor eine Abfrage erstellen
Wählen Sie im **Abfrage-Editor** im Abschnitt **Abfrage** des Menübands **Start** die Option **Erweiterter Editor** aus. Geben Sie im daraufhin angezeigten Fenster **Erweiterter Editor** die folgende Abfrage ein:

    let    
        enrollmentNumber = "100",
        optionalParameters = [ numberOfMonth = 6, dataType="DetailCharges" ],
        data = MicrosoftAzureConsumptionInsights.Contents(enrollmentNumber, optionalParameters)   
    in     
        data

![](media/desktop-connect-azure-consumption-insights/azure-consumption-insights_10.png)

Sie müssen selbstverständlich den Wert von *enrollmentNumber* durch Ihre eigene Registrierungsnummer ersetzen, die Sie im [Azure Enterprise-Portal](https://ea.azure.com) finden. Der Parameter *numberOfMonth* gibt die Anzahl der Monate vor dem aktuellen Datum an, die Sie einbeziehen möchten. Verwenden Sie für den aktuellen Monat 0 (null).

Sobald Sie im Fenster **Erweiterter Editor** auf **Fertig** geklickt haben, wird die Vorschau aktualisiert, und in der Tabelle werden Daten aus dem angegebenen Monatsbereich angezeigt. Wählen Sie **Schließen und übernehmen** aus, und kehren Sie zum Abfrage-Editor zurück.

### <a name="step-3-move-measures-and-custom-columns-to-the-new-report"></a>Schritt 3: Measures und benutzerdefinierte Spalten in den neuen Bericht verschieben
Anschließend müssen Sie alle benutzerdefinierten Spalten oder Measures, die Sie erstellt haben, in die neue Detailtabelle verschieben. Gehen Sie wie folgt vor.

1. Öffnen Sie Editor (oder einen anderen Text-Editor).
2. Wählen Sie das Measure aus, das Sie verschieben möchten, kopieren Sie den Text aus dem Feld *Formel*, und fügen Sie ihn in Editor ein.

   ![](media/desktop-connect-azure-consumption-insights/azure-consumption-insights_11.png)
3. Benennen Sie *Abfrage1* mit dem Namen der ursprünglichen Detailtabelle um.
4. Erstellen Sie in der Tabelle neue Measures und benutzerdefinierte Spalten, indem Sie mit der rechten Maustaste auf die Tabelle klicken, **Neues Measure** auswählen und dann die gespeicherten Measures und Spalten ausschneiden und einfügen, bis sie alle eingefügt haben.

### <a name="step-4-re-link-tables-that-had-relationships"></a>Schritt 4: Tabellen, die Beziehungen aufwiesen, erneut verknüpfen
Viele Dashboards verfügen über zusätzliche Tabellen, die zum Nachschlagen und Filtern verwendet werden, wie z.B. Datumstabellen oder Tabellen, die für benutzerdefinierte Projekte genutzt werden. Die meisten verbleibenden Probleme werden durch das Wiederherstellen dieser Beziehungen gelöst. Dazu gehen Sie wie folgt vor.

- Wählen Sie auf der Registerkarte **Modellierung** in **Power BI Desktop** die Option **Beziehungen verwalten** aus, um ein neues Fenster zu öffnen, in dem Sie Beziehungen im Modell verwalten können. Verknüpfen Sie die Tabellen nach Bedarf erneut.

    ![](media/desktop-connect-azure-consumption-insights/azure-consumption-insights_12.png)

### <a name="step-5-verify-your-visuals-and-adjust-field-formatting-as-needed"></a>Schritt 5: Die Visuals überprüfen und die Feldformatierung nach Bedarf anpassen
Nachdem Sie die vorherigen Schritte ausgeführt haben, sollten die meisten Ihrer ursprünglichen Visuals, Tabellen und Drilldowns wie erwartet ausgeführt werden. Möglicherweise sind jedoch einige kleinere Anpassungen der Formatierung erforderlich, damit die Darstellung Ihren Wünschen entspricht. Nehmen Sie sich etwas Zeit, um sich alle Dashboards und Visuals anzusehen und sicherzustellen, dass sie wie gewünscht aussehen.

## <a name="using-the-azure-consumption-and-insights-aci-api-to-get-consumption-data"></a>Abrufen von Verbrauchsdaten mithilfe der ACI-API (Azure Consumption and Insights)
Azure stellt auch die [**ACI-API (Azure Consumption and Insights)** ](https://azure.microsoft.com/blog/announcing-general-availability-of-consumption-and-charge-apis-for-enterprise-azure-customers/) bereit. Mit der ACI-API können Sie eigene benutzerdefinierte Lösungen zum Sammeln, Dokumentieren und Visualisieren von Azure-Verbrauchsinformationen erstellen.

### <a name="mapping-names-and-usage-details-between-the-portal-the-connector-and-the-api"></a>Zuordnen von Namen und Nutzungsdetails zwischen dem Portal, dem Connector und der API
Die Spalten und Namen der Details im Azure-Portal sind in der API und im Connector ähnlich, jedoch nicht immer identisch. Zur Erläuterung enthält die folgende Tabelle eine Zuordnung zwischen der API, dem Connector und den im Azure-Portal angezeigten Spalten. Es wird außerdem angegeben, ob die Spalte veraltet ist. Weitere Informationen und Definitionen der Begriffe finden Sie im [Azure-Wörterbuch für Abrechnungsdaten](https://docs.microsoft.com/azure/billing/billing-enterprise-api-usage-detail).

| Spaltenname im ACI-Connector/Inhaltspaket | ACI-API-Spaltenname | EA-Spaltenname | Veraltet/aus Gründen der Abwärtskompatibilität vorhanden |
| --- | --- | --- | --- |
| AccountName |accountName |Account Name |Nein |
| AccountId |accountId | |Ja |
| AcccountOwnerId |accountOwnerEmail |AccountOwnerId |Nein |
| AdditionalInfo |additionalInfo |AdditionalInfo |Nein |
| AdditionalInfold | | |Ja |
| Verbrauchte Menge |consumedQuantity |Verbrauchte Menge |Nein |
| Genutzter Dienst |consumedService |Genutzter Dienst |Nein |
| ConsumedServiceId |consumedServiceId | |Ja |
| Cost |cost |ExtendedCost |Nein |
| Kostenstelle |costCenter |Kostenstelle |Nein |
| Datum |Datum |Datum |Nein |
| Tag | |Tag |Nein |
| DepartmentName |departmentName |Department Name |Nein |
| DepartmentID |departmentId | |Ja |
| Instanzen-ID | | |Ja |
| InstanceId |instanceId |Instanzen-ID |Nein |
| Standort | | |Ja |
| Kategorie für Messung |meterCategory |Kategorie für Messung |Nein |
| Messungs-ID | | |Ja |
| Meter Name |meterName |Meter Name |Nein |
| Messbereich |meterRegion |Messbereich |Nein |
| Unterkategorie für Messung |meterSubCategory |Unterkategorie für Messung |Nein |
| MeterId |meterId |Messungs-ID |Nein |
| Month | |Month |Nein |
| Produkt |product |Produkt |Nein |
| ProductId |productId | |Ja |
| Resource Group |resourceGroup |Resource Group |Nein |
| Ressourcenspeicherort |resourceLocation |Ressourcenspeicherort |Nein |
| ResourceGroupId | | |Ja |
| ResourceLocationId |resourceLocationId | |Ja |
| ResourceRate |resourceRate |ResourceRate |Nein |
| ServiceAdministratorId |serviceAdministratorId |ServiceAdministratorId |Nein |
| ServiceInfo1 |serviceInfo1 |ServiceInfo1 |Nein |
| ServiceInfo1Id | | |Ja |
| ServiceInfo2 |serviceInfo2 |ServiceInfo2 |Nein |
| ServiceInfo2Id | | |Ja |
| Dienstbezeichner speichern |storeServiceIdentifier |Dienstbezeichner speichern |Nein |
| StoreServiceIdentifierId | | |Ja |
| Subscription Name |subscriptionName |Subscription Name |Nein |
| Tags |tags |Tags |Nein |
| TagsId | | |Ja |
| Maßeinheit |unitOfMeasure |Maßeinheit |Nein |
| Jahr | |Jahr |Nein |
| SubscriptionId |subscriptionId |SubscriptionId |Ja |
| SubscriptionGuid |subscriptionGuid |SubscriptionGuid |Nein |

## <a name="connect-with-azure-cost-management"></a>Herstellen einer Verbindung mit Azure Cost Management

In diesem Abschnitt erfahren Sie, wie Sie eine Verbindung mit einem Abrechnungskonto vom Typ „Kundenvertrag“ herstellen.

> [!NOTE]
> Der Azure Cost Management-Connector unterstützt derzeit die Kunden mit **Kundenvertrag**.  **Enterprise Agreement**-Kunden sollten den Microsoft Azure Consumption Insights-Connector verwenden.
>
>

Um mithilfe des Connectors **Azure Cost Management** eine Verbindung herzustellen, klicken Sie auf dem Menüband **Start** von **Power BI Desktop** auf **Daten abrufen**.  Wählen Sie in den Kategorien auf der linken Seite die Kategorie **Azure** aus. Daraufhin wird **Azure Cost Management (Beta)** angezeigt. Wählen Sie **Verbinden** aus.

![](media/desktop-connect-azure-consumption-insights/azure-cost-management-00.png)

Geben Sie im daraufhin angezeigten Dialogfeld Ihre *ID des Abrechnungsprofils* ein.

![](media/desktop-connect-azure-consumption-insights/azure-cost-management-01.png)

Die ID des Abrechnungsprofils finden Sie im [Azure-Portal](https://portal.azure.com).  Navigieren Sie zu **Kostenverwaltung + Abrechnung**. Wählen Sie Ihr Abrechnungskonto und anschließend auf der Randleiste die Option **Abrechnungsprofile** aus.  Wählen Sie Ihr Abrechnungsprofil und anschließend auf der Randleiste die Option **Eigenschaften** aus.  Kopieren Sie die ID des Abrechnungsprofils.

![](media/desktop-connect-azure-consumption-insights/azure-cost-management-02.png)

Sie werden aufgefordert, sich mit Ihrer Azure-E-Mail-Adresse und Ihrem Kennwort anzumelden.  Nach Abschluss der Authentifizierung wird ein **Navigatorfenster**mit zwölf verfügbaren Tabellen angezeigt:

* **Billing events** (Abrechnungsereignisse): Enthält ein Ereignisprotokoll für neue Rechnungen, Gutschriftkäufe und Ähnliches.
* **Budgets:** Enthält Budgetdetails zur Anzeige der tatsächlichen Kosten oder Nutzung im Vergleich zu vorhandenen Budgetzielen.
* **Charges** (Gebühren): Enthält eine monatsbasierte Zusammenfassung für Azure-Nutzung, Marketplace-Gebühren und separat abgerechnete Gebühren.
* **Credit lots** (Gutschriftanteile): Enthält Details zu Azure-Gutschriftanteilskäufen für das angegebene Abrechnungsprofil.
* **Credit summary** (Gutschriftzusammenfassung): Enthält eine Gutschriftzusammenfassung für das angegebene Abrechnungsprofil.
* **Marketplace**: Hier werden die nutzungsbasierten Azure Marketplace-Gebühren angezeigt.
* **Pricesheets** (Preisblätter): Enthält die geltenden Preise nach Verbrauchseinheit für das angegebene Abrechnungsprofil.
* **RI charges** (Gebühren für reservierte Instanzen): Hier werden die Gebühren für Ihre reservierten Instanzen in den letzten 24 Monaten angezeigt.
* **RI recommendations (single)** (Empfehlungen für reservierte Instanzen (einzeln)): Zeigt basierend auf Ihren Nutzungstrends für ein einzelnes Abonnement in den letzten 7, 30 oder 60 Tagen Kaufempfehlungen für reservierte Instanzen an.
* **RI recommendations (shared)** (Empfehlungen für reservierte Instanzen (gemeinsam genutzt)): Zeigt basierend auf Ihren Nutzungstrends für alle Ihre Abonnement in den letzten 7, 30 oder 60 Tagen Kaufempfehlungen für reservierte Instanzen an.
* **RI usage** (Nutzung reservierter Instanzen): Hier werden ausführliche Informationen zum Verbrauch für Ihre vorhandenen reservierten Instanzen im letzten Monat angezeigt.
* **Usage details** (Nutzungsdetails): Enthält eine Aufschlüsselung der verbrauchten Mengen und der geschätzten Kosten für die angegebene ID des Abrechnungsprofils.

Sie können neben jeder Tabelle ein Kontrollkästchen aktivieren, um eine Vorschau anzuzeigen.  Sie können einzelne oder mehrere Tabellen auswählen, indem Sie das Kontrollkästchen neben dem Tabellennamen aktivieren, und dann **Laden** wählen.

![](media/desktop-connect-azure-consumption-insights/azure-cost-management-03.png)

Wenn Sie **Laden** auswählen, werden die Daten in **Power BI Desktop** geladen.

![](media/desktop-connect-azure-consumption-insights/azure-consumption-insights_05.png)

Nachdem die von Ihnen ausgewählten Daten geladen wurden, werden im Bereich **Felder** die von Ihnen ausgewählten Tabellen und Felder angezeigt.

![](media/desktop-connect-azure-consumption-insights/azure-cost-management-05.png)

Sehen Sie sich das Video [How to analyze spending in Power BI with Azure Consumption Insights](https://www.youtube.com/watch?v=QKBMXXrlpEk) (Analysieren der Ausgaben in Power BI mit Azure Consumption Insights) zum Überprüfen Ihrer Kostendaten in Power BI Desktop mithilfe des Azure Consumption Insights-Connectors an.

## <a name="writing-custom-queries"></a>Schreiben benutzerdefinierter Abfragen

Wenn Sie die Monatsanzahl anpassen, die API-Version ändern oder eine komplexere Logik auf die zurückgegebenen Daten anwenden möchten, können Sie eine benutzerdefinierte M-Abfrage erstellen.

Wählen Sie auf dem Menüband **Start** von **Power BI Desktop** das Dropdownelement in **Daten abrufen** und anschließend die Option **Leere Abfrage** aus.  Sie können auch den **Abfrage-Editor** verwenden. Klicken Sie hierzu auf der linken Seite im Bereich **Abfragen** mit der rechten Maustaste, und wählen Sie im daraufhin angezeigten Menü **Neue Abfrage > Leere Abfrage** aus.

Geben Sie auf der **Bearbeitungsleiste** Folgendes ein, und ersetzen Sie dabei `billingProfileId` durch Ihre tatsächliche ID und „charges“ durch einen gültigen Tabellennamen (siehe Liste weiter oben).

```
let
    Source = AzureCostManagement.Tables(billingProfileId, [ numberOfMonths = 3 ]),
    charges = Source{[Key="charges"]}[Data]
in
    charges
```

`numberOfMonths` kann auf einen beliebigen Wert zwischen 1 und 36 festgelegt werden. Außerdem können Sie Folgendes angeben:

* `apiVersion`, um die Version der API anzupassen, die von der Abfrage aufgerufen wird
* `lookbackWindow`, um bei Empfehlungen für reservierte Instanzen (einzeln oder gemeinsam genutzt) das Zeitfenster für die Empfehlungsgenerierung zu ändern (zulässige Optionen: sieben, 30 oder 60 Tage)


## <a name="next-steps"></a>Nächste Schritte
Sie können mithilfe von Power BI Desktop eine Verbindung mit Daten jeglicher Art herstellen. Weitere Informationen zu Datenquellen finden Sie in folgenden Ressourcen:

* [Was ist Power BI Desktop?](desktop-what-is-desktop.md)
* [Datenquellen in Power BI Desktop](desktop-data-sources.md)
* [Strukturieren und Kombinieren von Daten mit Power BI Desktop](desktop-shape-and-combine-data.md)
* [Verbinden mit Excel in Power BI Desktop](desktop-connect-excel.md)   
* [Eingeben von Daten direkt in Power BI Desktop](desktop-enter-data-directly-into-desktop.md)   
