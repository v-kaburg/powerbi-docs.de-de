## <a name="validating-the-role-within-power-bi-desktop"></a>Überprüfen der Rolle in Power BI Desktop
Nachdem Sie Ihre Rolle erstellt haben, können Sie die Ergebnisse der Rolle in Power BI Desktop testen. Wählen Sie dazu **Als Rollen anzeigen** aus.

![](./media/rls-desktop-view-as-roles/powerbi-desktop-rls-view-as-roles.png)

Mit dem Dialog **Als Rollen anzeigen** können Sie die Ansicht für einen bestimmten Benutzer oder eine bestimmte Rolle ändern. Ihnen werden die Rollen angezeigt, die Sie erstellt haben.

![](./media/rls-desktop-view-as-roles/powerbi-desktop-rls-view-as-roles-dialog.png)

Wählen Sie die Rolle aus, die Sie erstellt haben, und wählen Sie anschließend **OK** aus, um diese Rolle auf die vor Ihnen liegende Ansicht anzuwenden. Die Berichte werden nur die für diese Rolle relevanten Daten rendern.

Sie können auch „Anderer Benutzer“ auswählen und einen bestimmten Benutzer angeben. Am besten geben Sie den Benutzerprinzipalnamen (User Principal Name; UPN) an, da der Power BI-Dienst diesen verwendet. Wählen Sie **OK** aus, und die Berichte rendern auf Grundlage dessen, was dem Benutzer angezeigt wird. 

![](./media/rls-desktop-view-as-roles/powerbi-desktop-rls-other-user.png)

> [!NOTE]
> In Power BI Desktop werden auf diesem Weg nur dann unterschiedliche Ergebnisse angezeigt, wenn Sie die dynamische Sicherheit basierend auf Ihren DAX-Ausdrücken verwenden.
> 
> 

