---
title: Abonnieren Sie paginierte Berichte in Power BI-Dienst
description: In diesem Artikel erfahren Sie, Dinge zu bedenken zum Abonnieren von paginierten Berichten im Power BI-Dienst.
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: report-builder
ms.topic: conceptual
ms.date: 05/24/2019
ms.openlocfilehash: ccec6658808d94728f2a4f14de67c36da0f51def
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2019
ms.locfileid: "66222202"
---
# <a name="subscribe-yourself-and-others-to-paginated-reports-in-the-power-bi-service"></a>Abonnieren von sich selbst und andere paginierte Berichte in Power BI-Dienst 

Sie können jetzt e-Mail-Abonnements für sich selbst und andere für paginierte Berichte im Power BI-Dienst einrichten. Im Allgemeinen der Prozess ist identisch mit [Abonnieren von Berichten und Dashboards in Power BI-Dienst](service-report-subscribe.md). Dieser Artikel beschreibt die Unterschiede und Überlegungen. 

Einrichten von Abonnements, Sie wählen Sie im wie oft soll die e-Mail-Nachrichten: täglich, wöchentlich oder stündlich. Wenn Sie täglich oder wöchentlich durchgeführt wird, Sie die Zeit können möchten Sie die Ausführung des Abonnements. In allen können Sie bis zu 24 verschiedenen Abonnements pro Tag für jeden Bericht festlegen. 

## <a name="considerations-for-paginated-report-subscriptions"></a>Überlegungen für Abonnements von paginierten Berichts 

- Im Gegensatz zu Abonnements für Dashboards oder Power BI-Berichten enthält das Abonnement eine Anlage von der gesamten Berichtsausgabe.  Die folgende Anlagetypen werden unterstützt: PDF-Datei, PowerPoint-Präsentation (PPTX), Excel-Arbeitsmappe (XLSX), Word-Dokument (DOCX), CSV-Datei und XML.

- Es ist kein Vorschaubild des Berichts in der e-Mail-Text.  Es ist geplant, um das Bild der ersten Seite des Berichts als optionale Element zu erhalten. 

- Die maximale Größe der Anlage ist 25 MB. 

- Sie können andere Benutzer für paginierte Berichte abonnieren, die alle derzeit unterstützten Datenquellen, einschließlich Azure Analysis Services oder Power BI-Datasets herstellen. Bedenken Sie die Anlage des Berichts die Daten basierend auf Ihren Berechtigungen können spiegelt wider, wie SQL Server Reporting Services noch heute. 

- Abonnements sind auf den Namen des Berichts gebunden.  

- E-Mail-Abonnements werden mit Standardwerte des Berichts gesendet. 

- Es gibt keine **nach Daten zu aktualisieren** Option für die Häufigkeit, mit paginierten Berichten. Sie erhalten immer die aktuellen Werte aus der zugrunde liegenden Datenquelle. 

## <a name="next-steps"></a>Nächste Schritte

[Abonnieren von sich selbst und andere Berichte und Dashboards in Power BI-Dienst](service-report-subscribe.md)

[Was sind paginierte Berichte in Power BI Premium (Vorschau)?](paginated-reports-report-builder-power-bi.md)
