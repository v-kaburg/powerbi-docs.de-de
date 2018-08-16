---
title: Herstellen einer Verbindung mit Zuora mithilfe von Power BI
description: Zuora für Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 48246d61789a0b1e160109c1f2fb0e81838b3965
ms.sourcegitcommit: fbb7924603f8915d07b5e6fc8f4d0c7f70c1a1e1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/02/2018
ms.locfileid: "39280315"
---
# <a name="connect-to-zuora-with-power-bi"></a>Herstellen einer Verbindung mit Zuora mithilfe von Power BI
Mit Zuora für Power BI können Sie wichtige Umsatzerlös-, Abrechnungs- und Abonnementdaten visuell darstellen. Verwenden Sie die standardmäßigen Dashboards und Berichte, um Nutzungstrends zu analysieren, Abrechnungen und Zahlungen nachzuverfolgen und wiederkehrende Umsatzerlöse zu überwachen, oder passen Sie sie an Ihre eigenen Anforderungen an Dashboards und Berichte an.

Stellen Sie eine Verbindung mit [Zuora](https://app.powerbi.com/getdata/services/Zuora) für Power BI her.

## <a name="how-to-connect"></a>Herstellen der Verbindung
1. Wählen Sie unten im linken Navigationsbereich **Daten abrufen** aus.

   ![](media/service-connect-to-zuora/getdata.png)
2. Wählen Sie im Feld **Dienste** die Option **Abrufen**aus.

   ![](media/service-connect-to-zuora/services.png)
3. Wählen Sie **Zuora** \> **Abrufen** aus.

   ![](media/service-connect-to-zuora/zuora.png)
4. Geben Sie Ihre Zuora-URL an. Diese lautet in der Regel „<https://www.zuora.com>“. Unten finden Sie Einzelheiten zum [Suchen dieser Parameter](#FindingParams).

   ![](media/service-connect-to-zuora/params.png)
5. Wählen Sie als **Authentifizierungsmethode** **Standard** aus, und geben Sie Ihren Benutzernamen und Ihr Kennwort ein (Groß- und Kleinschreibung müssen beachtet werden), und wählen Sie dann **Anmelden**aus.

    ![](media/service-connect-to-zuora/creds.png)
6. Nach der Genehmigung wird der Importvorgang automatisch gestartet. Nach Abschluss des Vorgangs werden im Navigationsbereich ein neues Dashboard, ein Bericht und ein Modell angezeigt. Wählen Sie das Dashboard aus, um die importierten Daten anzuzeigen.

     ![](media/service-connect-to-zuora/dashboard.png)

**Was nun?**

* Versuchen Sie, am oberen Rand des Dashboards [im Q&A-Feld eine Frage zu stellen](power-bi-q-and-a.md).
* [Ändern Sie die Kacheln](service-dashboard-edit-tile.md) im Dashboard.
* [Wählen Sie eine Kachel aus](service-dashboard-tiles.md), um den zugrunde liegenden Bericht zu öffnen.
* Ihr Dataset ist auf eine tägliche Aktualisierung festgelegt. Sie können jedoch das Aktualisierungsintervall ändern oder es über **Jetzt aktualisieren** nach Bedarf aktualisieren.

## <a name="whats-included"></a>Inhalt
Das Inhaltspaket verwendet die Zuora AQUA-API zum Abrufen von Daten aus den folgenden Tabellen:

| Tabellen |  |  |
| --- | --- | --- |
| Account |InvoiceItemAdjustment |Refund |
| AccountingCode |Payment |RevenueSchedule |
| AccountingPeriod |PaymentMethod |RevenueScheduleItem |
| BillTo |Product |Subscription |
| DateDim |ProductRatePlan |TaxationItem |
| Invoice |ProductRatePlanCharge |Verwendung |
| InvoiceAdjustment |RatePlan | |
| InvoiceItem |RatePlanCharge | |

Es enthält auch diese berechneten Measures:

| Measure | Beschreibung | Pseudo-Berechnung |
| --- | --- | --- |
| Account: Payments |Gesamtsumme der Zahlungsbeträge in einem bestimmten Zeitraum, basierend auf dem tatsächlichen Zahlungszeitpunkt. |SUM (Payment.Amount) <br>WHERE<br>Payment.EffectiveDate =< TimePeriod.EndDate<br>AND Payment.EffectiveDate >= TimePeriod.StartDate |
| Account: Refunds |Gesamtsumme der Erstattungsbeträge in einem bestimmten Zeitraum, basierend auf dem Erstattungsdatum. Die Gesamtsumme wird als eine negative Zahl zurückgegeben. |-1*SUM(Refund.Amount)<br>WHERE<br>Refund.RefundDate =< TimePeriod.EndDate<br>AND    Refund.RefundDate >= TimePeriod.StartDate |
| Account: Net Payments |Kontozahlungen plus Kontoerstattungen in einem bestimmten Zeitraum. |Account.Payments + Account.Refunds |
| Account: Active Accounts |Die Summe der Konten, die in einem bestimmten Zeitraum aktiv waren. Abonnements müssen vor (oder an) dem Startdatum des Zeitraums gestartet sein. |COUNT (Account.AccountNumber)<br>WHERE<br>    Subscription.Status != "Expired"<br>AND    Subscription.Status != "Draft"<br>AND    Subscription.SubscriptionStartDate <= TimePeriod.StartDate<br>AND    (Subscription.SubscriptionEndDate > TimePeriod.StartDate<br>OR<br>Subscription.SubscriptionEndDate = null) –evergreen subscription |
| Account: Average Recurring Revenue |Brutto-MRR pro aktivem Konto in einem bestimmten Zeitraum. |Gross MRR / Account.ActiveAccounts |
| Account: Cancelled Subscriptions |Die Summe der Konten, die in einem bestimmten Zeitraum ein Abonnement gekündigt haben. |COUNT (Account.AccountNumber)<br>WHERE<br>Subscription.Status = "Cancelled"<br>AND    Subscription.SubscriptionStartDate <= TimePeriod.StartDate<br>AND    Subscription.CancelledDate >= TimePeriod.StartDate |
| Account: Payment Errors |Gesamtwert der Zahlungsfehler. |SUM (Payment.Amount)<br>WHERE<br>Payment.Status = "Error" |
| Revenue Schedule Item: Recognized Revenue |Gesamtsumme der Umsatzrealisierungen in einem Abrechnungszeitraum. |SUM (RevenueScheduleItem.Amount)<br>WHERE<br>AccountingPeriod.StartDate = TimePeriod.StartDate |
| Subscription: New Subscriptions |Die Summe der neuen Abonnements in einem bestimmten Zeitraum. |COUNT (Subscription.ID)<br>WHERE<br>Subscription.Version = "1"<br>AND    Subscription.CreatedDate <= TimePeriod.EndDate<br>AND    Subscription.CreatedDate >= TimePeriod.StartDate |
| Invoice: Invoice Items |Gesamtsumme der Rechnungspostenbeträge in einem bestimmten Zeitraum. |SUM (InvoiceItem.ChargeAmount)<br>WHERE<br>    Invoice.Status = "Posted"<br>AND Invoice.InvoiceDate <= TimePeriod.EndDate<br>AND Invoice.InvoiceDate >= TimePeriod.StartDate |
| Invoice: Taxation Items |Gesamtsumme der auf einen Rechnungsposten angefallenen Steuern in einem bestimmten Zeitraum. |SUM (TaxationItem.TaxAmount)<br>WHERE<br>Invoice.Status = "Posted"<br>AND Invoice.InvoiceDate <= TimePeriod.EndDate<br>AND Invoice.InvoiceDate >= TimePeriod.StartDate |
| Invoice: Invoice Item Adjustments |Gesamtsumme der Änderungen, die in einem bestimmten Zeitraum an einem Rechnungsposten vorgenommen wurden. |SUM (InvoiceItemAdjustment.Amount) <br>WHERE<br>    Invoice.Status = "Posted"<br>AND InvoiceItemAdjustment.AdjustmentDate <= TimePeriod.EndDate<br>AND    InvoiceItemAdjustment.AdjustmentDate >= TimePeriod.StartDate |
| Invoice: Invoice Adjustments |Gesamtsumme der Änderungen, die in einem bestimmten Zeitraum an einer Rechnung vorgenommen wurden. |SUM (InvoiceAdjustment.Amount) <br>WHERE<br>    Invoice.Status = "Posted"<br>AND InvoiceAdjustment.AdjustmentDate <= TimePeriod.EndDate<br>AND    InvoiceAdjustment.AdjustmentDate >= TimePeriod.StartDate |
| Invoice: Net Billings |Summe der Rechnungsposten, Steuer auf Rechnungsposten, Änderungen an Rechnungsposten und Änderungen an Rechnungen in einem bestimmten Zeitraum. |Invoice.InvoiceItems + Invoice.TaxationItems + Invoice.InvoiceItemAdjustments + Invoice.InvoiceAdjustments |
| Invoice: Invoice Aging Balance |Summe der gebuchten Rechnungssaldos. |SUM (Invoice.Balance) <br>WHERE<br>    Invoice.Status = "Posted" |
| Invoice: Gross Billings |Summe der Rechnungspostenbeträge für gebuchte Rechnungen in einem bestimmten Zeitraum. |SUM (InvoiceItem.ChargeAmount) <br>WHERE<br>    Invoice.Status = "Posted"<br>AND Invoice.InvoiceDate <= TimePeriod.EndDate<br>AND Invoice.InvoiceDate >= TimePeriod.StartDate |
| Invoice: Total Adjustments |Summe der verarbeiteten Änderungen an Rechnungen und Rechnungsposten, die den gebuchten Rechnungen zugeordnet sind. |SUM (InvoiceAdjustment.Amount) <br>WHERE<br>    Invoice.Status = "Posted"<br>AND InvoiceAdjustment.Status = "Processed"<br>+<br>SUM (InvoiceItemAdjustment.Amount) <br>WHERE<br>    Invoice.Status = "Posted"<br>AND invoiceItemAdjustment.Status = "Processed" |
| Rate Plan Charge: Gross MRR |Summe der monatlich wiederkehrenden Umsätze von Abonnements in einem bestimmten Zeitraum. |SUM (RatePlanCharge.MRR) <br>WHERE<br>    Subscription.Status != "Expired"<br>AND    Subscription.Status != "Draft"<br>AND    RatePlanCharge.EffectiveStartDate <= TimePeriod.StartDate<br>AND RatePlanCharge.EffectiveEndDate > TimePeriod.StartDate<br>    OR    RatePlanCharge.EffectiveEndDate = null --evergreen subscription |

## <a name="system-requirements"></a>Systemanforderungen
Zugriff auf die Zuora-API ist erforderlich.

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>Suchen von Parametern
Geben Sie die URL an, mit der Sie sich in der Regel anmelden, um auf Ihre Zuora-Daten zugreifen. Die gültigen Optionen sind:  

* https://www.zuora.com  
* https://www.apisandbox.zuora.com  
* Die Ihrer Dienstinstanz entsprechende URL  

## <a name="troubleshooting"></a>Problembehandlung
Das Zuora-Inhaltspaket berücksichtigt viele unterschiedliche Aspekte Ihres Zuora-Kontos. Wenn Sie bestimmte Features nicht verwenden, sind die dazugehörigen Kacheln/Berichte ggf. leer. Wenn Sie Probleme beim Laden haben, wenden Sie sich an den Power BI-Support.

## <a name="next-steps"></a>Nächste Schritte
[Erste Schritte mit Power BI](service-get-started.md)

[Abrufen von Daten in Power BI](service-get-data.md)
