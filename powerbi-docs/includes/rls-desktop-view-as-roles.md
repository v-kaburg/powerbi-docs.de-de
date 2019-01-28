## <a name="validate-the-roles-within-power-bi-desktop"></a>Überprüfen der Rollen in Power BI Desktop
Nachdem Sie Ihre Rollen erstellt haben, können Sie die Ergebnisse der Rollen in Power BI Desktop testen.

1. Klicken Sie auf  **Als Rollen anzeigen**. 

    ![](./media/rls-desktop-view-as-roles/powerbi-desktop-rls-view-as-roles.png)

    Unter **Als Rollen anzeigen** werden die erstellten Rollen angezeigt.

    ![](./media/rls-desktop-view-as-roles/powerbi-desktop-rls-view-as-roles-dialog.png)

3. Wählen Sie eine erstellte Rolle aus, und klicken Sie auf  **OK** , um diese Rolle anzuwenden. Die Berichte rendert dann die Daten, die für diese Rolle relevant sind. 

4. Sie können auch **Anderer Benutzer** auswählen und einen bestimmten Benutzer angeben. Es wird empfohlen, den Benutzerprinzipalnamen (User Principal Name; UPN) anzugeben, da der Power BI-Dienst und der Power BI-Berichtsserver diesen verwenden.

    ![](./media/rls-desktop-view-as-roles/powerbi-desktop-rls-other-user.png)

1. Klicken Sie auf  **OK** , damit die Berichte rendern auf Grundlage dessen gerendert werden, was dem Benutzer angezeigt wird. 

In Power BI Desktop zeigt die Option **Anderer Benutzer** nur dann unterschiedliche Ergebnisse an, wenn Sie die dynamische Sicherheit auf Ihren DAX-Ausdrücken basierend verwenden. 

