---
title: Vertrauenswürdige Drittanbieter-Connectors in Powerbi
description: 'Gewusst wie: einen mit Drittanbieter-Connector in Power BI zu vertrauen'
author: cpopell
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 04/3/2019
ms.author: gepopell
LocalizationGroup: Connect to data
ms.openlocfilehash: 30b7457c6149320c43f24b967a842382821b01b1
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2019
ms.locfileid: "65607779"
---
# <a name="trusting-third-party-connectors"></a>Vertrauen Drittanbieter-connectors

## <a name="why-do-you-need-trusted-third-party-connectors"></a>Warum benötigen Sie die vertrauenswürdigen Drittanbieter-Connectors?

In Power BI empfehlen wir in der Regel Ihre Sicherheit zum Erweiterung von Daten auf dem höheren Grad an, die Laden von Code, die nicht durch Microsoft zertifiziert wird verhindert, dass Ebene beibehalten. Allerdings gibt es möglicherweise viele Fälle, in denen Sie bestimmte Connectors – diejenigen, die Sie geschrieben haben, noch diejenigen, die durch einen Berater oder der Anbieter außerhalb des Pfads der Microsoft-Zertifizierung bereitgestellte laden möchten.

Der Entwickler eines bestimmten Connectors können sie mit einem Zertifikat signieren und bieten Ihnen die Informationen, die auf sichere Weise Laden ohne verringern die Sicherheitseinstellungen werden sollen.

Wenn Sie weitere Informationen zu den Sicherheitseinstellungen erhalten möchten, müssen Sie erhalten Informationen über diese [hier](https://docs.microsoft.com/power-bi/desktop-connector-extensibility).

## <a name="using-the-registry-to-trust-third-party-connectors"></a>Mithilfe der Registrierung, um Drittanbieter-Connectors zu vertrauen.

Vertrauen Drittanbieter-Connectors in Power BI erfolgt durch Auflisten der Fingerabdruck des Zertifikats, die Sie in einem angegebenen Registrierungswert vertrauen möchten. Wenn dieser Fingerabdruck den Fingerabdruck des Zertifikats für den Connector ein, das Sie laden möchten entspricht, werden Sie zu "Empfohlen" Sicherheitsstufe von Power BI laden können. 

Der Registrierungspfad ist HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Power BI-Desktop. Stellen Sie sicher, dass der Pfad vorhanden ist, oder erstellen sie. Wir haben uns entschieden, diesen Speicherort aufgrund von IT-Richtlinie als auch erfordern lokale Computer Administratorenzugriff so bearbeiten Sie in erster Linie gesteuert. 

![Power BI Desktop-Registrierung ohne vertrauenswürdigen Drittanbieter-Schlüssel festlegen](media/desktop-trusted-third-party-connectors/desktoptrustedthird1.png)

Fügen Sie einen neuen Wert unter dem oben angegebenen Pfad hinzu. Der Typ muss "Mehrteilige Zeichenfolge-Value" (REG_MULTI_SZ) und "TrustedCertificateThumbprints" sollte aufgerufen werden 

![Power BI Desktop-Registrierung mit einem Eintrag für den vertrauenswürdigen Drittanbieter-Connectors, aber keine Schlüssel](media/desktop-trusted-third-party-connectors/desktoptrustedthird2.png)

Fügen Sie die Fingerabdrücke der Zertifikate zu vertrauen. Sie können mehrere Zertifikate mithilfe von "\0" als Trennzeichen oder in den Registrierungs-Editor, des rechten Maustaste auf ändern, und jeder Fingerabdruck in einer neuen Zeile platzieren, hinzufügen. Beispielfingerabdruck ist ein selbst signiertes Zertifikat entnommen. 

 ![Power BI Desktop-Registrierung mit einem vertrauenswürdigen Drittanbieter-Schlüssel festlegen](media/desktop-trusted-third-party-connectors/desktoptrustedthird3.png)

Wenn Sie ordnungsgemäß die Anweisungen befolgt haben und den richtigen Fingerabdruck durch Ihre Entwickler übergeben worden sein, sollten Sie jetzt auf sichere Trust-Connectors, die mit dem zugehörigen Zertifikat signiert sein.

## <a name="how-to-sign-connectors"></a>Gewusst wie: Signieren von Connectors

Wenn Sie einen Connector haben Sie oder ein Entwickler müssen sich anmelden, informieren Sie sich über ihn in der Power Query-Dokumentation [hier](https://docs.microsoft.com/power-query/handlingconnectorsigning).
