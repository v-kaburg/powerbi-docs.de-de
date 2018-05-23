---
title: Freigeben von Power BI-Dashboards und -Berichten für Kollegen und andere
description: In diesem Artikel wird erläutert, wie Sie Power BI-Dashboards und -Berichte für Kollegen innerhalb und außerhalb Ihrer Organisation freigeben, und was Sie über die Freigabe wissen müssen.
author: maggiesMSFT
manager: kfile
ms.reviewer: lukaszp
featuredvideoid: 0tUwn8DHo3s
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 01/18/2018
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: e176f82e106c531410b8e9233b983c6e321bddf4
ms.sourcegitcommit: 638de55f996d177063561b36d95c8c71ea7af3ed
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/17/2018
---
# <a name="share-your-power-bi-dashboards-and-reports-with-coworkers-and-others"></a>Freigeben Ihrer Power BI-Dashboards und -Berichte für Kollegen und andere
*Freigeben* ist eine gute Möglichkeit, einigen Personen Zugriff auf Ihre Dashboards und Berichte zu gewähren. Zudem bietet Power BI [verschiedene Möglichkeiten zum gemeinsamen Bearbeiten und Verteilen von Dashboards und Berichten](service-how-to-collaborate-distribute-dashboards-reports.md).

![Symbol „Freigeben“ in einer Liste von Favoritendashboards](media/service-share-dashboards/power-bi-share-dash-report-favorites.png)

Zum Freigeben benötigen Sie eine [Power BI Pro-Lizenz](service-free-vs-pro.md), egal, ob Sie Inhalte innerhalb oder außerhalb Ihrer Organisation freigeben. Auch Ihre Empfänger benötigen Power BI Pro-Lizenzen, oder es muss sich um Inhalte in einer [Premium-Kapazität](service-premium.md) handeln. 

Sie können Dashboards und Berichte von den meisten Stellen im Power BI-Dienst aus freigeben: Ihre „Favoriten“, „Zuletzt verwendet“, „Für mich freigegeben“ (wenn der Besitzer es erlaubt), „Mein Arbeitsbereich“ oder andere Arbeitsbereiche. Wenn Sie Dashboards oder Berichts freigeben, können diejenigen, für die Sie sie freigeben, diese anzeigen und damit interagieren, aber nicht bearbeiten. Sie sehen die gleichen Daten wie Sie im Dashboard oder Bericht, es sei denn, die [Sicherheit auf Zeilenebene (RLS)](service-admin-rls.md) ist aktiviert. Die Kollegen, für die Sie Inhalte freigeben, können diese auch für ihre Kollegen freigeben, wenn Sie dies zulassen. Die Personen außerhalb Ihrer Organisation können ebenfalls das Dashboard oder den Bericht anzeigen und damit interagieren, aber diese nicht freigeben. 

Sie können [ein Dashboard auch aus einer beliebigen mobilen Power BI-App freigeben](mobile-share-dashboard-from-the-mobile-apps.md). Sie können Dashboards über den Power BI-Dienst und die mobilen Power BI-Apps, aber nicht über Power BI Desktop freigeben.

## <a name="video-share-a-dashboard"></a>Video: Freigeben eines Dashboards
Sehen Sie sich an, wie Amanda ihr Dashboard für Kollegen im Unternehmen und externe Personen freigibt. Befolgen Sie dann die schrittweisen Anleitungen unter dem Video, um es selbst ausprobieren.

<iframe width="560" height="315" src="https://www.youtube.com/embed/0tUwn8DHo3s?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>

## <a name="share-a-dashboard-or-report"></a>Freigeben eines Dashboards oder Berichts

1. Wählen Sie in einer Liste von Dashboards bzw. Berichten oder in einem geöffneten Dashboard oder Bericht **Freigeben** ![Symbol „Freigeben“](media/service-share-dashboards/power-bi-share-icon.png).

1. Geben Sie im oberen Feld die vollständigen E-Mail-Adressen für Einzelpersonen, Verteilergruppen oder Sicherheitsgruppen ein. Bei dynamischen Verteilerlisten sind Freigaben nicht möglich. 
   
   Freigaben sind auch für Personen mit Adressen außerhalb der Organisation möglich. In diesem Fall wird allerdings eine Warnung angezeigt.
   
   ![Warnung zur externen Freigabe](media/service-share-dashboards/power-bi-share-dialog-warning.png) 
 
3. Wenn Sie möchten, fügen Sie eine Nachricht hinzu. Dies ist optional.
4. Damit Ihre Kollegen Ihren Inhalt für weitere Personen freigeben können, aktivieren Sie das Kontrollkästchen **Empfängern das Freigeben Ihres Dashboards/Berichts erlauben**.
   
   Wenn Sie anderen Personen das Freigeben gestatten, wird dies als *erneutes Freigeben* bezeichnet. In diesem Fall können die anderen Personen die Inhalte über den Power BI-Dienst und die mobilen Apps erneut freigeben oder die E-Mail-Einladung an andere Personen in der Organisation weiterleiten. Nach einem Monat läuft die Einladung ab. Für Personen außerhalb Ihrer Organisation ist die erneute Freigabe nicht möglich. Als Besitzer des Inhalts können Sie die erneute Freigabe deaktivieren oder individuell widerrufen. Siehe unten [Aufheben der Freigabe oder Aufheben der Freigabe durch andere](service-share-dashboards.md#stop-sharing-or-stop-others-from-sharing).

5. Wählen Sie **Freigeben** aus.
   
   ![Schaltfläche „Freigeben“ auswählen](media/service-share-dashboards/power-bi-share-dialog-share.png)  
   
   Power BI sendet an die Personen, jedoch nicht an Gruppen, eine Einladung per E-Mail, die einen Link zum freigegebenen Inhalt enthält. Die Benachrichtigung **Erfolgreich** wird angezeigt. 
   
   Wenn Empfänger in Ihrer Organisation auf den Link klicken, wird das Dashboard bzw. der Bericht in Power BI ihrer Listenseite **Für mich freigegeben** hinzugefügt. Die Empfänger können Ihren Namen auswählen, um alle von Ihnen für sie freigegebenen Inhalte anzuzeigen. 
   
   ![Listenseite „Für mich freigegeben“](media/service-share-dashboards/power-bi-shared-with-me-dashboards-reports.png)
   
   Wenn Empfänger außerhalb der Organisation auf den Link klicken, wird das Dashboard bzw. der Bericht angezeigt, jedoch nicht im üblichen Power BI-Portal. Im Abschnitt [Freigeben für Personen außerhalb Ihrer Organisation](service-share-dashboards.md#share-a-dashboard-with-people-outside-your-organization) weiter unten finden Sie eine nähere Beschreibung.

## <a name="who-has-access-to-a-dashboard-or-report-you-shared"></a>Wer hat Zugriff auf von Ihnen freigegebene Dashboards und Berichte?
In einigen Fällen müssen Sie sehen können, für welche Personen Sie Inhalte freigegeben haben, und für welche Personen diese die Inhalte freigegeben haben.

1. Wählen Sie in der Liste der Dashboards und Berichte oder im Dashboard bzw. Bericht selbst **Freigeben** ![Symbol „Freigeben“](media/service-share-dashboards/power-bi-share-icon.png) aus. 
2. Wählen Sie im Dialogfeld **Dashboard/Bericht freigeben** die Option **Zugriff** aus.
   
    ![Dialogfeld „Dashboard freigeben“, Registerkarte „Zugriff“](media/service-share-dashboards/power-bi-share-dialog-access.png)
   
    Personen außerhalb Ihrer Organisation werden als **Gast** aufgelistet.

## <a name="stop-sharing-or-stop-others-from-sharing"></a>Aufheben der Freigabe oder Aufheben der Freigabe durch andere
Nur der Dashboard- bzw. Berichtbesitzer kann die erneute Freigabe aktivieren und deaktivieren.

### <a name="if-you-havent-sent-the-sharing-invitation-yet"></a>Wenn Sie die Freigabeeinladung noch nicht gesendet haben
* Deaktivieren Sie unten in der Einladung das Kontrollkästchen **Empfängern das Freigeben Ihres Dashboards/Berichts erlauben**, bevor Sie sie senden.

### <a name="if-youve-already-shared-the-dashboard-or-report"></a>Wenn Sie das Dashboard bzw. den Bericht bereits freigegeben haben
1. Wählen Sie in der Liste der Dashboards und Berichte oder im Dashboard bzw. Bericht selbst **Freigeben** ![Symbol „Freigeben“](media/service-share-dashboards/power-bi-share-icon.png) aus. 
2. Wählen Sie im Dialogfeld **Dashboard/Bericht freigeben** die Option **Zugriff** aus.
   
    ![Dialogfeld „Dashboard freigeben“, Registerkarte „Zugriff“](media/service-share-dashboards/power-bi-share-dialog-access.png)
3. Klicken Sie auf die Auslassungspunkte (**...**) neben **Lesen und erneut freigeben**, und wählen Sie dann Folgendes:
   
   ![Auslassungspunkte neben „Lesen und erneut freigeben“](media/service-share-dashboards/power-bi-change-access.png)
   
   * **Lesen**, um Freigaben dieser Person für andere Personen zu verhindern.
   * **Zugriff entfernen**, um zu verhindern, dass diese Person den freigegebenen Inhalt anzeigen kann.

4. Legen Sie im Dialogfeld **Zugriff entfernen** fest, ob Sie auch den Zugriff auf verwandte Inhalte entfernen möchten, z.B. auf Berichte und Datasets. Wenn Sie Elemente mit einem Warnsymbol ![Power BI-Warnsymbol](media/service-share-dashboards/power-bi-warning-icon.png) entfernen, sollten Sie auch verwandte Inhalte entfernen, da sie nicht korrekt angezeigt werden.

## <a name="share-a-dashboard-or-report-with-people-outside-your-organization"></a>Freigeben eines Dashboards bzw. eines Berichts für Personen außerhalb Ihrer Organisation
Bei einer Freigabe für Personen außerhalb Ihrer Organisation erhalten diese eine E-Mail mit einem Link zum freigegebenen Dashboard bzw. Bericht. Sie müssen sich bei Power BI anmelden, um den Inhalt anzuzeigen. Wenn sie keine Power BI Pro-Lizenz haben, können sie sich nach Klicken auf den Link für eine Lizenz registrieren.

Nachdem sie sich angemeldet haben, sehen sie das freigegebene Dashboard bzw. den freigegebenen Bericht in einem eigenen Browserfenster ohne den linken Navigationsbereich, nicht in ihrem üblichen Power BI-Portal. Sie müssen den Link als Favoriten speichern, um künftig auf dieses Dashboard bzw. diesen Bericht zugreifen zu können.

Sie können Inhalte in diesem Dashboard oder Bericht nicht bearbeiten. Aber Sie haben die Möglichkeit, im Bericht mit den Diagrammen zu interagieren und Änderungsfilter oder Datenschnitte zu ändern, wobei sie ihre Änderungen jedoch nicht speichern können.

Nur direkte Empfänger können das freigegebene Dashboard bzw. den freigegebenen Bericht anzeigen. Wenn Sie die E-Mail beispielsweise an Vicki@contoso.com gesendet haben, wird das Dashboard nur für Vicki angezeigt. Niemand sonst kann das Dashboard sehen, selbst wenn der Link verfügbar ist, und Vicki muss dieselbe E-Mail-Adresse verwenden, um auf dieses Dashboard zuzugreifen. Wenn sie sich mit einer anderen E-Mail-Adresse anmeldet, hat sie auch keinen Zugriff auf das Dashboard.

Personen außerhalb Ihrer Organisation können überhaupt keine Daten anzeigen, wenn für lokale Analysis Services-Tabellenmodelle die Sicherheit auf Rollen- oder Zeilenebene implementiert ist.

Wenn Sie aus einer mobilen Power BI-App einen Link an Personen außerhalb Ihrer Organisation senden und diese auf den Link klicken, wird das Dashboard in einem Browser und nicht in der mobilen Power BI-App geöffnet.

## <a name="limitations-and-considerations"></a>Einschränkungen und Überlegungen
Aspekte, die beim Freigeben von Dashboards und Berichten zu beachten sind:

* Im Allgemeinen sehen Sie und Ihre Kollegen die gleichen Daten im Dashboard bzw. Bericht. Wenn Sie folglich mehr Berechtigungen als Ihre Kollegen haben, Daten zu sehen, werden sie alle Daten in Ihrem Dashboard bzw. Bericht sehen können. Wenn jedoch die [Sicherheit auf Zeilenebene (RLS)](service-admin-rls.md) auf das einem Dashboard bzw. Bericht zugrunde liegende Dataset angewendet ist, wird anhand der Anmeldeinformationen jeder Person festgelegt, auf welche Daten sie zugreifen kann.
* Jede Person, für die Sie das Dashboard freigeben, kann es anzeigen und in der [Leseansicht](service-reading-view-and-editing-view.md) mit den verknüpften Berichten interagieren. Sie können keine Berichte erstellen oder Änderungen an vorhandenen Berichten speichern.
* Das Dataset kann von ihnen nicht angezeigt oder heruntergeladen werden.
* Alle Benutzer können die [Daten manuell aktualisieren](refresh-data.md).
* Wenn Sie Office 365 für E-Mails verwenden, ist die Freigabe für Mitglieder einer Verteilergruppe möglich, indem Sie die der Verteilergruppe zugeordnete E-Mail-Adresse eingeben.
* Kollegen in derselben E-Mail-Domäne wie Sie und Kollegen, die zu einer anderen Domäne gehören, aber innerhalb desselben Mandanten registriert sind, können das Dashboard für andere freigeben. Angenommen, die Domänen „contoso.com“ und „contoso2.com“ sind im selben Mandanten registriert. Wenn Sie die E-Mail-Adresse konrads@contoso.com haben, ist sowohl ravali@contoso.com als auch gustav@contoso2.com eine Freigabe erlaubt, sofern Sie ihnen die Berechtigung zum Freigeben erteilt haben.
* Wenn Ihre Kollegen bereits über den Zugriff auf ein bestimmtes Dashboard bzw. einen bestimmten Bericht verfügen, können Sie einen direkten Link senden, indem Sie einfach die URL kopieren, wenn Sie sich auf dem Dashboard bzw. im Bericht befinden. Beispiel: `https://powerbi.com/dashboards/g12466b5-a452-4e55-8634-xxxxxxxxxxxx`
* Ebenso können Sie, wenn Ihre Kollegen bereits Zugriff auf ein bestimmtes Dashboard haben, [einen direkten Link zum zugrunde liegenden Bericht senden](service-share-reports.md). 

## <a name="troubleshoot-sharing"></a>Behandeln von Problemen bei der Freigabe

### <a name="my-dashboard-recipients-see-a-lock-icon-in-a-tile-or-a-permission-required-message"></a>Die Empfänger meines Dashboards sehen ein Schlosssymbol auf einer Kachel oder die Meldung „Berechtigung erforderlich“.

Den Personen, für die Sie Inhalte freigeben, wird möglicherweise eine gesperrte Kachel in einem Dashboard oder die Meldung „Berechtigung erforderlich“ angezeigt, wenn sie einen Bericht anzeigen möchten.

![Gesperrte Power BI-Kachel](media/service-share-dashboards/power-bi-locked_tile_small.png)

In diesem Fall müssen Sie ihnen eine Berechtigung für das zugrunde liegende Dataset gewähren. Dazu gehen Sie wie folgt vor.

1. Wechseln Sie in der Liste Ihrer Inhalte zur Registerkarte **Datasets**.

1. Wählen Sie die Auslassungspunkte (**...** ) neben dem Dataset > **Berechtigungen verwalten** aus.

    ![Verwalten von Berechtigungen](media/service-share-dashboards/power-bi-sharing-manage-permissions.png)

3. Wählen Sie **Benutzer hinzufügen** aus.

    ![„Benutzer hinzufügen“ auswählen](media/service-share-dashboards/power-bi-share-dataset-add-user.png)

1. Geben Sie die vollständigen E-Mail-Adressen für Einzelpersonen, Verteilergruppen oder Sicherheitsgruppen ein. Bei dynamischen Verteilerlisten sind Freigaben nicht möglich.

    ![E-Mail-Adressen hinzufügen](media/service-share-dashboards/power-bi-add-user-dataset.png)

5. Wählen Sie **Hinzufügen**.

### <a name="i-cant-share-a-dashboard-or-report"></a>Ein Dashboard oder Bericht kann nicht freigegeben werden

Zum Freigeben eines Dashboards oder Berichts benötigen Sie die Berechtigung zum Freigeben des zugrunde liegenden Inhalts, d.h. alle zugehörigen Berichte und Datasets. Wenn eine Meldung angezeigt wird, dass die Freigabe nicht möglich ist, bitten Sie den Autor des Berichts, Ihnen für diese Berichte und Datasets die Berechtigung zum erneuten Freigeben zu gewähren.


## <a name="next-steps"></a>Nächste Schritte
* Feedback? Anregungen nehmen wir auf der [Power BI-Communitywebsite](https://community.powerbi.com/) entgegen.
* [Wie kann ich Dashboards und Berichte freigeben?](service-how-to-collaborate-distribute-dashboards-reports.md)
* [Freigeben eines gefilterten Power BI-Berichts](service-share-reports.md)
* Haben Sie Fragen? [Wenden Sie sich an die Power BI-Community](http://community.powerbi.com/).

