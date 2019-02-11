---
title: Exportieren von Berichten als PDF-Dateien
description: Erfahren Sie, wie Sie Power BI-Bericht als PDF-Dateien exportieren.
author: mihart
manager: kvivek
ms.custom: ''
ms.reviewer: cmfinlan
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 02/04/2019
ms.author: mihart
LocalizationGroup: Share your work
ms.openlocfilehash: c18257f1f4e4e3f325c8d4d895e3b6abf88e900c
ms.sourcegitcommit: 54d44deb6e03e518ad6378656c769b06f2a0b6dc
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/07/2019
ms.locfileid: "55794992"
---
# <a name="export-reports-from-power-bi-to-pdf"></a>Exportieren von Power BI-Berichten als PDF-Dateien
Mit Power BI können Sie Berichte im PDF-Format veröffentlichen und darauf basierend einfach ein Dokument erstellen. Wenn Sie das Feature **In PDF exportieren** verwenden, wird jede Seite des Power BI-Berichts als individuelle Seite im PDF-Dokument angezeigt.

## <a name="how-to-export-your-power-bi-report-to-pdf"></a>Exportieren eines Power BI-Berichts als PDF-Datei
Wählen Sie im Power BI-Dienst einen Bericht aus, der im Zeichenbereich angezeigt werden soll. Sie können auch einen Bericht von der Startseite, aus Apps oder einem anderen Abschnitt im linken Navigationsbereich auswählen.

1. Klicken Sie in der Menüleiste auf **Datei** > **In PDF exportieren**.

    ![„Datei“ auf der Menüleiste und Pfeil, der auf „In PDF exportieren“ zeigt](media/end-user-pdf/power-bi-export-pdf.png)

    In der oberen rechten Ecke wird eine Fortschrittsleiste angezeigt. Das Exportieren kann einige Minuten dauern. Während der Bericht exportiert wird, können Sie in Power BI weiterarbeiten.

    ![Meldung zum Fortschritt des Exportierens](media/end-user-pdf/power-bi-export-message.png)

    Sobald der Vorgang beendet ist, wird über das Banner gemeldet, dass der Power BI-Dienst den Export abgeschlossen hat.

2. Ihre Datei ist dann dort verfügbar, wo Ihr Browser heruntergeladene Dateien speichert. In der folgenden Abbildung wird die Datei als Downloadbanner unten im Browserfenster angezeigt.

    ![Speicherort für heruntergeladene Datei](media/end-user-pdf/power-bi-save-file.png)

Das war schon alles. Sie können die Datei herunterladen und mit einem beliebigen PDF-Viewer öffnen, z.B. der in Microsoft Edge enthaltene.


## <a name="limitations-and-considerations"></a>Einschränkungen und Überlegungen
Einige Aspekte und Einschränkungen sind bei der Arbeit mit dem Feature **In PDF exportieren** zu beachten.

- Sitzungsinterne Interaktivität wie Hervorheben und Filtern, Drilldown usw. wird beim Export in PDF derzeit nicht unterstützt. Die exportierte PDF-Datei enthält die ursprünglichen Visuals, wie sie im Bericht gespeichert wurden. Wenn Sie Filter und Datenschnitte angewendet haben und diese im Export beibehalten werden sollen, speichern Sie den Bericht, und führen Sie erst dann den Export durch.

* **R-Visuals** werden derzeit nicht unterstützt. Diese Visuals werden in der PDF-Datei leer sein und eine Fehlermeldung anzeigen.  

* **Benutzerdefinierte Visuals**, die **zertifiziert** wurden, werden unterstützt. Weitere Informationen zu zertifizierten benutzerdefinierten Visuals sowie zum Zertifizieren von benutzerdefinierten Visuals finden Sie unter [Wie wird ein benutzerdefiniertes Visual zertifiziert?](../power-bi-custom-visuals-certified.md). Nicht zertifizierte, benutzerdefinierte Visuals werden nicht unterstützt. In der PDF-Datei werden sie mit einer Fehlermeldung angezeigt.   

* Berichte mit mehr als 30 Berichtsseiten können derzeit nicht exportiert werden.

* Der Exportvorgang des Berichts als PDF-Datei kann einige Minuten dauern. Zu den Faktoren, die die benötigte Zeit beeinflussen, zählen die Struktur des Berichts sowie die jeweils aktuelle Auslastung des Power BI-Diensts.

* Wenn das Menüelement **In PDF exportieren** im Power BI-Dienst nicht verfügbar ist, hat der Mandantenadministrator dieses Feature wahrscheinlich deaktiviert. Wenden Sie sich an den Mandantenadministrator, um Einzelheiten zu erfahren.

* Hintergrundbilder werden an der Begrenzung des Diagramms abgeschnitten. Es wird empfohlen, Hintergrundbilder vor dem Export als PDF-Datei zu entfernen.

* Berichte, die ein Benutzer außerhalb Ihrer Power BI-Mandantendomäne besitzt (beispielsweise ein Bericht im Besitz einer Person außerhalb Ihrer Organisation, die ihn für Sie freigegeben hat), können nicht als PDF-Datei veröffentlicht werden.

* Wenn Sie ein Dashboard für Personen außerhalb Ihrer Organisation freigeben (und damit für einen Benutzer, der nicht Ihrem Power BI-Mandanten angehört), kann der betreffende Benutzer die zugehörigen Berichte des freigegebenen Dashboards nicht als PDF-Datei exportieren. Wenn Sie beispielsweise aaron@contoso.com sind, können Sie Berichte für cassie@cohowinery.com freigeben. cassie@cohowinery.com kann die zugehörigen Berichte jedoch nicht als PDF-Datei exportieren.

* Der Power BI-Dienst verwendet Ihre Power BI-Spracheinstellung, um die Sprache für den PDF-Export festzulegen. Sie können die Spracheinstellung anzeigen, indem Sie das Zahnradsymbol und dann **Einstellungen** > **Allgemein** > **Sprache** auswählen.

## <a name="next-steps"></a>Nächste Schritte
[Drucken eines Berichts](end-user-print.md)