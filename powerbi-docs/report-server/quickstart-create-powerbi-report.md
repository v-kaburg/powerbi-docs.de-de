---
title: Erstellen eines Power BI-Berichts für den Power BI-Berichtsserver
description: Erfahren Sie, wie Sie in wenigen einfachen Schritten einen Power BI-Bericht für Power BI-Berichtsserver erstellen.
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.topic: conceptual
ms.date: 05/22/2019
ms.author: maggies
ms.openlocfilehash: 2401064f1f7f3be63c23d72e79987784e1ec7049
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2019
ms.locfileid: "66187504"
---
# <a name="create-a-power-bi-report-for-power-bi-report-server"></a>Erstellen eines Power BI-Berichts für den Power BI-Berichtsserver
Sie können Power BI-Berichte lokal im Webportal von Power BI-Berichtsserver ebenso wie in der Cloud im Power BI-Dienst https://powerbi.com) speichern und verwalten. Sie erstellen und bearbeiten Berichte in Power BI Desktop und veröffentlichen sie im Webportal. Anschließend können Leser in Ihrer Organisation die Berichte in einem Browser oder einer mobilen Power BI-App auf einem Mobilgerät anzeigen.

![Power BI-Bericht im Webportal](media/quickstart-create-powerbi-report/report-server-powerbi-report.png)

Hier finden Sie vier einfache Schritte, um Ihnen den Einstieg zu erleichtern.

## <a name="step-1-install-power-bi-desktop-optimized-for-power-bi-report-server"></a>Schritt 1: Installieren von für Power BI-Berichtsserver optimiertem Power BI Desktop

Wenn Sie bereits Power BI-Berichte in Power BI Desktop erstellt haben, ist das Erstellen von Power BI-Berichten für Power BI-Berichtsserver auch nicht mehr schwer. Wir empfehlen die Installation der Version von Power BI Desktop, die für Power BI-Berichtsserver optimiert ist, damit Sie sicher sein können, dass Server und App stets synchron sind. Es können beide Versionen von Power BI Desktop auf demselben Computer installiert sein.

1. Wählen Sie im Report Server Web-Portal die **herunterladen** Pfeil > **Power BI Desktop**.

    ![Power BI Desktop aus dem Webportal herunterladen](media/quickstart-create-powerbi-report/report-server-download-web-portal.png)

    Oder wechseln Sie direkt zu [Microsoft Power BI Desktop](https://www.microsoft.com/download/details.aspx?id=56723) (optimiert für Power BI-Berichtsserver – Mai 2019) im Microsoft Download Center.

2. Wählen Sie im Download Center **Download** aus.

3. Wählen Sie abhängig von Ihrem Computer eine der folgenden Versionen aus:

    - **PBIDesktopRS.msi** (32-Bit-Version) oder

    - **PBIDesktopRS_x64.msi** (64-Bit-Version).

4. Nachdem Sie das Installationsprogramm heruntergeladen haben, führen Sie den Setup-Assistenten für Power BI Desktop (Mai 2019).

2. Aktivieren Sie am Ende des Installationsvorgangs **Power BI Desktop jetzt starten**.
   
    Die App wird automatisch gestartet, sodass Sie gleich loslegen können. Sie können feststellen, dass Sie die richtige Version verfügen, da "Power BI Desktop (Mai 2019)" in der Titelleiste angezeigt wird.

    ![Power BI Desktop-Version Mai 2019](media/quickstart-create-powerbi-report/power-bi-report-server-desktop-may-2019.png)

3. Wenn Sie mit Power BI Desktop nicht vertraut sind, wird empfohlen, sich die Videos auf dem Begrüßungsbildschirm anzusehen.
   
    ![Startbildschirm von Power BI Desktop](media/quickstart-create-powerbi-report/report-server-powerbi-desktop-start.png)

## <a name="step-2-select-a-data-source"></a>Schritt 2: Auswählen einer Datenquelle
Sie können Verbindungen mit einer Vielzahl von Datenquellen herstellen. Erfahren Sie mehr über das [Verbinden mit Datenquellen](connect-data-sources.md).

1. Klicken Sie auf dem Begrüßungsbildschirm auf **Daten abrufen**.
   
    Oder klicken Sie auf der Registerkarte **Start** auf **Daten abrufen**.
2. Wählen Sie Ihre Datenquelle (in diesem Beispiel **Analysis Services**) aus.
   
    ![Datenquelle auswählen](media/quickstart-create-powerbi-report/report-server-get-data-ssas.png)
3. Füllen Sie **Server** und optional **Datenbank** aus. Stellen Sie sicher, dass **Live verbinden** ausgewählt ist, und klicken Sie auf **OK**.
   
    ![Servername](media/quickstart-create-powerbi-report/report-server-ssas-server-name.png)
4. Wählen Sie den Berichtsserver aus, auf dem Sie die Berichte speichern.
   
    ![Auswahl des Berichtsservers](media/quickstart-create-powerbi-report/report-server-select-server.png)

## <a name="step-3-design-your-report"></a>Schritt 3: Entwerfen des Berichts
Hier ist Kreativität gefragt, denn Sie erstellen nun die Visuals zum Veranschaulichen Ihrer Daten.

Sie können z.B. ein Trichterdiagramm von Kunden und Gruppenwerten nach Jahreseinkommen erstellen.

![Bericht entwerfen](media/quickstart-create-powerbi-report/report-server-create-funnel.png)

1. Wählen Sie in **Visualisierungen** die Option **Trichterdiagramm** aus.
2. Ziehen Sie das zu zählende Feld in den Bereich **Werte**. Wenn es sich nicht um ein numerisches Feld handelt, wird es von Power BI Desktop automatisch als *Anzahl* des Werts angezeigt.
3. Ziehen Sie das Feld, anhand dessen gruppiert wird, in den Bereich **Gruppe**.

Erfahren Sie mehr über das [Entwerfen eines Power BI-Berichts](../desktop-report-view.md).

## <a name="step-4-save-your-report-to-the-report-server"></a>Schritt 4: Speichern des Berichts auf dem Berichtsserver
Wenn Ihr Bericht fertig ist, speichern Sie ihn auf dem Power BI-Berichtsserver, den Sie in Schritt 2 ausgewählt haben.

1. Klicken Sie im Menü **Datei** auf **Speichern unter** > **Power BI-Berichtsserver**.
   
    ![Auf dem Berichtsserver speichern](media/quickstart-create-powerbi-report/report-server-save-as-powerbi-report-server.png)
2. Jetzt können Sie ihn im Webportal anzeigen.
   
    ![Den Bericht im Webportal anzeigen](media/quickstart-create-powerbi-report/report-server-powerbi-report.png)

## <a name="next-steps"></a>Nächste Schritte
### <a name="power-bi-desktop"></a>Power BI Desktop
Power BI Desktop bietet zahlreiche nützliche Ressourcen zum Erstellen von Berichten. Dieser Link ist ein guter Ausgangspunkt.

* [Erste Schritte mit Power BI Desktop](../desktop-getting-started.md)
* Lernen mit Anleitungen: [Erste Schritte mit Power BI Desktop](../guided-learning/gettingdata.yml?tutorial-step=2)

### <a name="power-bi-report-server"></a>Power BI-Berichtsserver
* [Installieren von für Power BI-Berichtsserver optimiertem Power BI Desktop](install-powerbi-desktop.md)  
* [Was ist der Power BI-Berichtsserver?](get-started.md)  

Weitere Fragen? [Stellen Sie Ihre Frage in der Power BI-Community.](https://community.powerbi.com/)
