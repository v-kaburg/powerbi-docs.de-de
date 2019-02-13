---
title: Einbetten eines Berichts mithilfe eines iFrames
description: Einbetten eines Power BI-Berichtsserver-Berichts in einen iFrame in SharePoint Server
author: markingmyname
ms.author: maghan
ms.date: 05/04/2018
ms.topic: quickstart
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.custom: mvc
manager: kfile
ms.openlocfilehash: 4730bef0e7f1fc47a4a59a0129640760714fe2e0
ms.sourcegitcommit: 80961ace38ff9dac6699f81fcee0f7d88a51edf4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/13/2019
ms.locfileid: "56223327"
---
# <a name="quickstart-embed-a-power-bi-report-server-report-using-an-iframe-in-sharepoint-server"></a>Schnellstart: Einbetten eines Power BI-Berichtsserver-Berichts in einen iFrame in SharePoint Server

In diesem Schnellstart erfahren Sie, wie Sie einen Power BI-Berichtsserver-Bericht mithilfe eines iFrames in eine SharePoint-Seite einbetten. Wenn Sie mit SharePoint Online arbeiten, muss der öffentliche Zugriff auf den Power BI-Berichtsserver möglich sein. In SharePoint Online funktioniert der Power BI-Webpart, der mit dem Power BI-Dienst funktioniert, nicht mit dem Power BI-Berichtsserver. 

![iFrame-Beispiel](media/quickstart-embed/quickstart_embed_01.png)
## <a name="prerequisites"></a>Voraussetzungen
* Der [Power BI-Berichtsserver](https://powerbi.microsoft.com/report-server/) muss installiert und konfiguriert sein.
* [Für den Power BI-Berichtsserver optimiertes Power BI Desktop](install-powerbi-desktop.md) muss installiert sein.
* Eine installierte und konfigurierte [SharePoint](https://docs.microsoft.com/sharepoint/install/install)-Umgebung ist erforderlich.

## <a name="creating-the-power-bi-report-server-report-url"></a>Erstellen der Berichts-URL für den Power BI-Berichtsserver

1. Laden Sie das Beispiel von GitHub herunter – [Blog-Demo](https://github.com/Microsoft/powerbi-desktop-samples).

    ![PBIX-Beispieldatei herunterladen](media/quickstart-embed/quickstart_embed_14.png)

2. Öffnen Sie die PBIX-Beispieldatei über GitHub in **für den Power BI-Berichtsserver optimiertem Power BI Desktop**.

    ![Power BI-Berichtsserver-Desktop-Tool](media/quickstart-embed/quickstart_embed_02.png)

3. Speichern Sie den Bericht auf dem **Power BI-Berichtsserver**. 

    ![Speichern auf dem Power BI-Berichtsserver](media/quickstart-embed/quickstart_embed_03.png)

4. Zeigen Sie den Bericht im **Webportal** an.

    ![Webportal](media/quickstart-embed/quickstart_embed_04.png)

### <a name="capturing-the-url-parameter"></a>Erfassen des URL-Parameters

Sobald Sie die URL haben, können Sie einen iFrame auf einer SharePoint-Seite erstellen, in dem der Bericht gehostet wird. Sie können für jede Power BI-Berichtsserver-Berichts-URL einen querystring-Parameter von `?rs:embed=true` hinzufügen, um Ihren Bericht in einen iFrame einzubetten. 

   Beispiel:
    ``` 
    http://myserver/reports/powerbi/Sales?rs:embed=true
    ```
## <a name="embedding-a-power-bi-report-server-report-in-a-sharepoint-iframe"></a>Einbetten eines Power BI-Berichtsserver-Berichts in einen SharePoint-iFrame

1. Navigieren Sie zu einer **Websiteinhalte**-Seite in SharePoint.

    ![Websiteinhalte-Seite](media/quickstart-embed/quickstart_embed_05.png)

2. Wählen Sie die Seite aus, auf der Sie Ihren Bericht hinzufügen möchten.

    ![Websiteinhalte-Seite-App](media/quickstart-embed/quickstart_embed_06.png)

3. Wählen Sie das Zahnrad oben rechts und dann **Seite bearbeiten** aus.

    ![Option „Seite bearbeiten“](media/quickstart-embed/quickstart_embed_07.png)

4. Wählen Sie **Webpart hinzufügen** aus.

    ![„Webpart hinzufügen“](media/quickstart-embed/quickstart_embed_08.png)

5. Wählen Sie unter **Kategorien** die Option **Medien und Inhalt** aus, unter **Teile** die Option **Inhalts-Editor**, und wählen Sie dann **Hinzufügen** aus.

    ![Inhalts-Editor-Webpart auswählen](media/quickstart-embed/quickstart_embed_09.png) ![„Hinzufügen“ auswählen](media/quickstart-embed/quickstart_embed_091.png)

6. Wählen Sie **Hier klicken, um neue Inhalte hinzuzufügen** aus.

    ![Neue Inhalte hinzufügen](media/quickstart-embed/quickstart_embed_10.png)

7. Wählen Sie im Menüband die Registerkarte **Text formatieren** aus und dann **Quelle bearbeiten**.

     ![„Quelle bearbeiten“](media/quickstart-embed/quickstart_embed_11.png)

8. Fügen Sie im Fenster „Quelle bearbeiten“ Ihren iFrame-Code ein, und wählen Sie „OK“ aus.

    ![iFrame-Code](media/quickstart-embed/quickstart_embed_12.png)

     Beispiel:
     ```html
     <iframe width="800" height="600" src="http://myserver/reports/powerbi/Sales?rs:embed=true" frameborder="0" allowFullScreen="true"></iframe>
     ```

9. Wählen Sie im Menüband die Registerkarte **Seite** aus und dann **Bearbeitung beenden**.

    ![„Bearbeitung beenden“](media/quickstart-embed/quickstart_embed_13.png)

10. Jetzt sollte der Bericht auf der Seite angezeigt werden.

    ![iFrame-Beispiel](media/quickstart-embed/quickstart_embed_01.png)

## <a name="next-steps"></a>Nächste Schritte

[Schnellstart: Erstellen eines Power BI-Berichts für Power BI-Berichtsserver](quickstart-create-powerbi-report.md)  
[Schnellstart: Erstellen eines paginierten Berichts für Power BI-Berichtsserver](quickstart-create-paginated-report.md)  

Weitere Fragen? [Stellen Sie Ihre Frage in der Power BI-Community.](https://community.powerbi.com/) 