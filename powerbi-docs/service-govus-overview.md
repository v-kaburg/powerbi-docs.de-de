---
title: "Power BI für Angehörige von US-Behörden – Übersicht"
description: "USA Angehörige von US-Behörden finden hier Informationen über die Funktionen und Einschränkungen des Power-BI US Government-Diensts."
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
ms.date: 09/06/2017
ms.author: davidi
ms.openlocfilehash: 9c8e2b44c128db283bef65198204e4aee1bfdd7a
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2017
---
# <a name="power-bi-for-us-government-customers"></a>Power BI für Angehörige von US-Behörden
Für den **Power BI-Dienst** ist im Rahmen von **Office 365 US Government Community**-Abonnements eine Version für Kunden verfügbar, die Angehörige von US-Behörden sind. Die in diesem Artikel vorgestellte Version des **Power BI-Diensts** ist speziell für Angehörige von US-Behörden konzipiert. Es handelt sich hierbei um ein separates und von der kommerziellen Version des **Power BI-Diensts** abweichendes Produkt.

![](media/service-govus-overview/service_usgov_overview-1.png)

In den folgenden Abschnitten werden die *Funktionen* beschrieben, die für die Version des **Power BI-Diensts** für US-Behörden verfügbar sind. Außerdem werden einige *Einschränkungen* erläutert, häufig gestellte Fragen (**FAQ**) und Antworten behandelt (u.a. zur Registrierung) und Links für weitere Informationen aufgeführt.

## <a name="features-of-power-bi-us-government"></a>Features von Power BI US Government
Es muss beachtet werden, dass **Power BI US Government** nur als **Pro-Lizenz** und nicht als Free-Lizenz verfügbar ist. Bestimmte Features des Power BI-Diensts stehen in der Version **Power BI US Government** des Diensts zur Verfügung.

Die folgenden Funktionen stehen Kunden von **Power BI US Government** zur Verfügung, gemäß der in der **Pro**-Lizenz beschriebenen Funktionalität:

* Erstellen und Anzeigen von Dashboards und Berichten
* [Beschränkung der Datenkapazität](service-admin-manage-your-data-storage-in-power-bi.md)
* [Geplante Datenaktualisierung](refresh-data.md)
* Aktualisierbare Teamdashboards
* Active Directory-Gruppen für Freigaben und die Verwaltung der Zugriffskontrolle
* [Importieren von Daten](service-get-data.md) und Berichten aus Excel-, CSV- und Power BI Desktop-Dateien
* Datenverwaltungsgateway
* Verschlüsselung sämtlicher Daten in SQL Azure und Blob Storage für Power BI
* Herstellen einer Dienstverbindung mit [Inhaltspaketen](service-connect-to-services.md)

## <a name="limitations-of-power-bi-us-government"></a>Einschränkungen von Power BI US Government
Einige Funktionen, die in der kommerziellen Version des **Power BI-Diensts** verfügbar sind, stehen im **Power BI-Dienst** für Angehörige von US-Behörden *nicht* zur Verfügung. Das Power BI-Team arbeitet derzeit daran, diese Funktionen auch für Kunden bei US-Behörden zur Verfügung zu stellen. Dieser Artikel wird aktualisiert, sobald diese Funktionen verfügbar sind.

* **Power BI US Government** ist nur als **Pro**-Lizenz verfügbar. Alle Verweise auf Power BI (Free)-Lizenzen im Administratorportal (oder als Benutzer) beziehen sich auf die Ausführung in einer kommerziellen Power BI-Dienstcloud.
* **Überwachung:** Überwachung ist über das Office 365 Security & Compliance Center nicht verfügbar.

Wenn Ihrem Konto **Power BI**-Free-Lizenzen zugewiesen sind, wird dieses Konto in einer kommerziellen Version des **Power BI**-Diensts ausgeführt und ist nicht Teil des Angebots **Power BI US Government**. Bei diesen Free-Konten können die folgenden Probleme auftreten:

* Authentifizieren von Gateway, Mobilgeräten und Desktops nicht möglich
* Kein Zugriff auf kommerzielle Azure-Datenquellen
* Manueller Upload von PBIX-Dateien aus der kommerziellen Version erforderlich
* Mobile Power BI-Apps nicht verfügbar

Um diese Probleme zu beheben, wenden Sie sich an den Ansprechpartner für Ihr Konto.

## <a name="frequently-asked-questions-faq-for-the-us-government-version-of-the-power-bi-service"></a>Häufig gestellte Fragen (FAQ) für die Version des Power BI-Diensts für US-Behörden
Anhand der folgenden Fragen (und Antworten) finden Sie schnell die benötigten Informationen zum Dienst.

**Frage:** Wie migriere ich meine Daten aus dem kommerziellen **Power BI**-Dienst in den **Power BI-Dienst** für US-Behörden?

**Antwort:** Ihr Administrator muss eine neue Instanz von **Power BI** unter einem separaten, für US-Behörden spezifischen Abonnement erstellen. Sie können dann die Daten aus der kommerziellen Version im **Power BI-Dienst** für US-Behörden replizieren, die kommerzielle Lizenz entfernen und die vorhandene Domäne dem neuen, für US-Behörden spezifischen Dienst zuordnen.

**Frage:** Warum kann ich keine Verbindung mit einem bestimmten Inhaltspaket herstellen?

**Antwort:** Sie müssen sicherstellen, dass Ihr Abonnement aktiviert wurde, damit Sie eine Verbindung mit dem Inhaltspaket herstellen können.

**Frage:** Ich möchte **Power BI** für meine US-Behörde verwenden. Wie beginne ich?

**Antwort:** Die Registrierungsschritte (auch als *Onboarding* bezeichnet) unterscheiden sich je nach vorhandener Lizenz und Abonnement. Im Artikel zur [Registrierung bei Power BI US Government](service-govus-signup.md) finden Sie weitere Informationen.

**Frage:** Lautet die URL für die Verbindung mit **Power BI** für US-Behörden anders als die URL für die kommerzielle Version von **Power BI**?

**Antwort:** Ja, die URLs unterscheiden sich. Die folgende Tabelle enthält die verschiedenen URLs:

| URL der kommerziellen Version | URL der Version für US-Behörden |
| --- | --- |
| https://app.powerbi.com/ |[https://app.powerbigov.us](https://app.powerbigov.us) |

## <a name="next-steps"></a>Nächste Schritte
Mit Power BI können Sie viele verschiedene Aufgaben ausführen. Weitere Informationen und Anweisungen sowie einen Artikel zur Registrierung für den Dienst finden Sie in den folgenden Ressourcen:

* [Registrierung bei Power BI for US Government](service-govus-signup.md)
* <a href="https://channel9.msdn.com/Blogs/Azure/Cognitive-Services-HDInsight-and-Power-BI-on-Azure-Government">Demo zu Power BI US Government</a>
* [Geführtes Lernen zu Power BI](guided-learning/gettingstarted.yml#step-1)
* [Erste Schritte mit Power BI](service-get-started.md)
* [Erste Schritte mit Power BI Desktop](desktop-getting-started.md)

