---
title: Benutzerdefinierte Visualisierungen in Power BI
description: Benutzerdefinierte Visualisierungen in Power BI
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 02/06/2018
ms.author: maghan
LocalizationGroup: Visualizations
ms.openlocfilehash: d8c3a33a3ae6166d33ea7a613917616613b84696
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2018
ms.locfileid: "34721453"
---
# <a name="custom-visuals-in-power-bi"></a>Benutzerdefinierte Visualisierungen in Power BI
Beim Erstellen oder Bearbeiten eines Power BI-Berichts stehen Ihnen viele verschiedene Typen von Visuals zur Verfügung. Diese Visuals werden im Bereich **Visualisierungen** angezeigt. Wenn Sie Power BI Desktop herunterladen oder den Power BI-Dienst („app.powerbi.com“) öffnen, ist dieser Satz von Visuals vorkonfiguriert.

![](media/power-bi-custom-visuals/power-bi-visualizations.png)

Sie sind jedoch nicht auf diesen Satz von Visuals beschränkt. Durch Auswählen der Auslassungspunkte wird eine weitere Quelle von Berichtsvisuals geöffnet: *benutzerdefinierte Visuals*.

Benutzerdefinierte Visuals werden von Entwicklern mithilfe des SDK für benutzerdefinierte Visuals erstellt. Dadurch können Geschäftskunden die Daten auf die Weise anzeigen, die für das Unternehmen am besten geeignet ist. Berichtsautoren können die Dateien der benutzerdefinierten Visuals dann in ihre Berichte importieren und diese wie die anderen Power BI-Visuals verwenden. Benutzerdefinierte Visuals sind wichtige Bestandteile und können in Power BI unter anderem gefiltert, hervorhoben, bearbeitet und freigegeben werden.

Benutzerdefinierte Visuals können in Form von drei Bereitstellungskanälen vorliegen:
* Benutzerdefinierte Visualdateien
* Visuals für Organisationen
* Visuals im Marketplace

## <a name="custom-visual-files"></a>Benutzerdefinierte Visualdateien

Bei benutzerdefinierten Visuals handelt es sich um Pakete, die Code zum Rendern der Daten enthalten, die für diese bereitgestellt werden. Jeder Benutzer kann ein benutzerdefiniertes Visual erstellen und dieses in einer einzigen PBIVIZ-Datei packen, die in einen Power BI-Bericht importiert werden kann.

> [!WARNING]
> Ein benutzerdefiniertes Visual kann Code mit Sicherheits- oder Datenschutzrisiken enthalten. Stellen Sie sicher, dass Sie dem Autor und der Quelle des benutzerdefinierten Visuals vertrauen können, bevor Sie dieses in Ihren Bericht importieren.
> 
> 

## <a name="organization-visuals"></a>Visuals für Organisationen

Power BI-Administratoren können benutzerdefinierte Visuals für ihre Organisation bereitstellen, sodass Berichtsautoren die benutzerdefinierten Visuals, deren Verwendung innerhalb der Organisation vom Administrator genehmigt wurde, einfacher ermitteln und verwenden können. Dadurch kann der Administrator steuern, welche benutzerdefinierten Visuals für die Organisation bereitgestellt werden sollen. Zudem können die Visuals auf diese Weise einfach verwaltet werden (d.h. Aktualisieren der Version, Aktivieren/Deaktivieren). Für den Berichtsautor stellt dies einen einfachen Weg dar, um Visuals zu ermitteln, die nur für die Organisation verfügbar sind. Außerdem wird ein nahtloser Support bereitgestellt, um diese Visuals zu aktualisieren.

Weitere Informationen zu benutzerdefinierten Visuals für Organisationen finden Sie [hier](power-bi-custom-visuals-organization.md).

## <a name="marketplace-visuals"></a>Visuals im Marketplace

Mitglieder der Community und Microsoft haben benutzerdefinierte Visuals für die Öffentlichkeit erstellt und diese im [AppSource](https://appsource.microsoft.com/en-us/marketplace/apps?product=power-bi-visuals)-Marketplace bereitgestellt. Diese Visuals können heruntergeladen und Power BI-Berichten hinzugefügt werden. Alle dieser benutzerdefinierten Visuals wurden von Microsoft auf Funktionalität und Qualität getestet und genehmigt.

Was ist AppSource? Einfach ausgedrückt ist es der Ort, an dem Sie Apps, Add-Ins und Erweiterungen für Microsoft-Software finden. In [AppSource](https://appsource.microsoft.com/en-us/) finden Millionen von Benutzern Produkte, z.B. Office 365, Azure, Dynamics 365, Cortana und Power BI, mit denen sie die Effizienz ihrer Arbeit steigern, größere Einblicke gewinnen oder die Darstellung der Ergebnisse verbessern können.

### <a name="certified-visuals"></a>Zertifizierte Visuals

Bei zertifizierten Power BI-Visuals handelt es sich um Marketplace-Visuals, die zusätzlichen strengen Qualitätstests unterzogen wurden. Diese werden für zusätzliche Szenarios unterstützt, z.B. für [E-Mail-Abonnements](https://docs.microsoft.com/power-bi/service-report-subscribe) und die Option [Nach PowerPoint exportieren](https://docs.microsoft.com/power-bi/service-publish-to-powerpoint).
Die Liste der zertifizierten benutzerdefinierten visuellen Elemente sowie eine Anleitung zum Einreichen eigener benutzerdefinierter visueller Elemente finden Sie unter [Zertifizierte benutzerdefinierte visuelle Elemente](https://docs.microsoft.com/power-bi/power-bi-custom-visuals-certified).

Sind Sie Webentwickler und möchten eigene Visualisierungen erstellen und zu AppSource hinzufügen? Lesen Sie [Erste Schritte mit den Entwicklertools](https://docs.microsoft.com/power-bi/service-custom-visuals-getting-started-with-developer-tools), und erfahren Sie, wie [benutzerdefinierte Visuals in AppSource veröffentlicht werden](https://appsource.microsoft.com/en-us/marketplace/apps?product=power-bi-visuals).

### <a name="import-a-custom-visuals-from-a-file"></a>Importieren eines benutzerdefinierten Visuals aus einer Datei

1. Wählen Sie am unteren Rand des Bereichs „Visualisierungen“ die Auslassungspunkte aus.

    ![](media/power-bi-custom-visuals/power-bi-visualizations2.png)

2. Wählen Sie in der Dropdownliste **Aus Datei importieren** aus.

    ![](media/power-bi-custom-visuals/power-bi-custom-visual-import-from-file.png)

3. Klicken Sie im Menü „Datei öffnen“ auf die PBIVIZ-Datei, die Sie importieren möchten, und klicken Sie dann auf „Öffnen“. Am unteren Ende des Bereichs „Visualisierungen“ wird das Symbol für das benutzerdefinierte Visual hinzugefügt, und dieses kann jetzt in Ihrem Bericht verwendet werden.

    ![](media/power-bi-custom-visuals/power-bi-custom-visual-imported.png)

### <a name="import-organization-visuals"></a>Importieren von Visuals für Organisationen

1. Wählen Sie am unteren Rand des Bereichs „Visualisierungen“ die Auslassungspunkte aus.

    ![](media/power-bi-custom-visuals/power-bi-visual-org-01.png)

2. Wählen Sie in der Dropdownliste „Aus Marketplace importieren“ aus.

    ![](media/power-bi-custom-visuals/power-bi-visual-org-02.png)

3. Klicken Sie auf dem Menü der oberen Registerkarte auf **MEINE ORGANISATION**.

    ![](media/power-bi-custom-visuals/power-bi-visual-org-03.png)

4. Scrollen Sie in der Liste, um das Visual zu suchen, das Sie importieren möchten.
    
    ![](media/power-bi-custom-visuals/power-bi-visual-org-04.png)

5. Importieren Sie das benutzerdefinierte Visual, indem Sie **Hinzufügen** auswählen. Am unteren Ende des Bereichs „Visualisierungen“ wird das Symbol für das benutzerdefinierte Visual hinzugefügt, und dieses kann jetzt in Ihrem Bericht verwendet werden.

    ![](media/power-bi-custom-visuals/power-bi-visual-org-05.png)
 
## <a name="download-or-import-custom-visuals-from-microsoft-appsource"></a>Herunterladen oder Importieren benutzerdefinierter Visuals von Microsoft AppSource
Sie haben zwei Möglichkeiten zum Herunterladen und Importieren benutzerdefinierter Visuals: in Power BI und über die AppSource-Website.

### <a name="import-custom-visuals-from-within-power-bi"></a>Importieren benutzerdefinierter Visuals in Power BI

1. Wählen Sie am unteren Rand des Bereichs „Visualisierungen“ die Auslassungspunkte aus.

    ![](media/power-bi-custom-visuals/power-bi-visualizations2.png)

2. Wählen Sie in der Dropdownliste **Aus Marketplace importieren** aus.

    ![](media/power-bi-custom-visuals/power-bi-visual-org-02.png)

3. Scrollen Sie in der Liste, um das Visual zu suchen, das Sie importieren möchten.

    ![](media/power-bi-custom-visuals/power-bi-import-visual.png)

4. Wenn Sie zu einem der Visuals weitere Informationen erhalten möchten, markieren Sie es, und wählen Sie es aus.

    ![](media/power-bi-custom-visuals/power-bi-select.png)

5. Auf der Detailseite können Sie Screenshots, Videos, ausführliche Beschreibungen und weitere Elemente anzeigen.

    ![](media/power-bi-custom-visuals/power-bi-synoptic.png)

6. Scrollen Sie nach unten, um Bewertungen anzuzeigen.

    ![](media/power-bi-custom-visuals/power-bi-reviews.png)

7. Importieren Sie das benutzerdefinierte Visual, indem Sie auf „Hinzufügen“ klicken. Am unteren Ende des Bereichs „Visualisierungen“ wird das Symbol für das benutzerdefinierte Visual hinzugefügt, und dieses kann jetzt in Ihrem Bericht verwendet werden.

    ![](media/power-bi-custom-visuals/power-bi-custom-visual-imported.png)

### <a name="download-and-import-custom-visuals-from-microsoft-appsource"></a>Herunterladen und Importieren benutzerdefinierter Visuals von Microsoft AppSource

1. Wählen Sie in [Microsoft AppSource](https://appsource.microsoft.com) die Registerkarte für **Apps** aus. 

    ![](media/power-bi-custom-visuals/power-bi-appsource-apps.png)

2. Dadurch gelangen Sie zur Seite [App-Ergebnisse](https://appsource.microsoft.com/en-us/marketplace/apps), auf der Sie die beliebtesten Apps in den einzelnen Kategorien, einschließlich *Power BI-Apps*, anzeigen können. Da Sie jedoch benutzerdefinierte Visuals suchen, wählen Sie in der linken Navigationsliste **Power BI-Visuals** aus, um die Ergebnisse einzugrenzen.

    ![](media/power-bi-custom-visuals/power-bi-appsource-visuals.png)

3. In AppSource wird für jedes benutzerdefinierte Visual eine Kachel angezeigt.  Jede Kachel enthält eine Momentaufnahme des benutzerdefinierten Visuals, eine kurze Beschreibung und einen Downloadlink. Wählen Sie die Kachel aus, um weitere Details anzuzeigen. 

    ![](media/power-bi-custom-visuals/powerbi-custom-select-visual.png)

4. Auf der Detailseite können Sie Screenshots, Videos, ausführliche Beschreibungen und weitere Elemente anzeigen. Wählen Sie **Jetzt holen** aus, und stimmen Sie den Nutzungsbedingungen zu, um das benutzerdefinierte Visual herunterzuladen. 

    ![](media/power-bi-custom-visuals/power-bi-appsource-get.png)

5. Wählen Sie den Link aus, um das benutzerdefinierte Visual herunterzuladen.

    ![](media/power-bi-custom-visuals/powerbi-custom-download.png)

    Die Downloadseite enthält auch Anweisungen zum Importieren des benutzerdefinierten Visuals in Power BI Desktop und den Power BI-Dienst.

    Sie können auch einen Beispielbericht herunterladen, der das benutzerdefinierte Visual enthält und dessen Funktionen veranschaulicht.

    ![](media/power-bi-custom-visuals/powerbi-custom-try-sample.png)

6. Speichern Sie die PBIVIZ-Datei, und öffnen Sie dann Power BI.

7. Importieren Sie die PBIVIZ-Datei in Ihren Bericht. Weitere Informationen finden Sie unter [Import a custom visual from a file (Importieren eines benutzerdefinierten Visuals aus einer Datei)](#import-a-custom-visuals-from-a-file) im vorherigen Abschnitt.

## <a name="considerations-and-troubleshooting"></a>Zu beachtende Aspekte und Problembehandlung

- Beim Importieren wird eine benutzerdefinierte Visualisierungen einem bestimmten Bericht hinzugefügt. Wenn Sie die Visualisierung in einem anderen Bericht verwenden möchten, müssen Sie sie in diesen Bericht ebenfalls importieren. Wenn ein Bericht mit einer benutzerdefinierten Visualisierung mit der Option **Speichern unter** gespeichert wird, wird eine Kopie der benutzerdefinierten Visualisierung mit dem neuen Bericht gespeichert.

- Wenn der Bereich **Visualisierungen** nicht angezeigt wird, bedeutet dies, dass Sie über keine Bearbeitungsberechtigungen für den Bericht verfügen.  Sie können benutzerdefinierte Visuals nur Berichten hinzufügen, die Sie bearbeiten können, und keinen Berichten, die für Sie freigegeben wurden.

Weitere Fragen? [Wenden Sie sich an die Power BI-Community](http://community.powerbi.com/)
