## <a name="using-the-username-or-userprincipalname-dax-function"></a>Verwenden der DAX-Funktion „username()“ oder „userprincipalname()“
Sie können die DAX-Funktion *username()* oder *userprincipalname()* in Ihrem Dataset verwenden. Sie können beide Funktionen in Ausdrücken in Power BI Desktop verwenden. Wenn Sie Ihr Modell veröffentlichen, wird es im Power BI-Dienst verwendet.

In Power BI Desktop gibt *username()* einen Benutzer im Format *DOMÄNE\Benutzer* und *userprincipalname()* einen Benutzer im Format <em>user@contoso.com</em> zurück.

Im Power BI-Dienst geben sowohl *username()* als auch *userprincipalname()* den Benutzerprinzipalnamen (User Principal Name, UPN) des Benutzers zurück. Dieser ähnelt einer E-Mail-Adresse.

