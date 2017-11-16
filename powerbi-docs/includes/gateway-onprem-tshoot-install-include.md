## <a name="update-to-the-latest-version"></a>Aktualisieren auf die neueste Version
Viele Probleme können auftreten, wenn die Gatewayversion veraltet ist.  Es ist ratsam sicherzustellen, dass Sie immer die aktuelle Version verwenden.  Wenn Sie das Gateway einen Monat oder länger nicht mehr aktualisiert haben, sollten Sie die aktuelle Version des Gateways installieren und prüfen, ob Sie das Problem reproduzieren können.

## <a name="common-issues"></a>Häufige Probleme
Im Folgenden werden einige häufig auftretenden Probleme und Lösungen aufgeführt, die von Kunden in Umgebungen mit eingeschränktem Zugriff auf das Internet erfolgreich eingesetzt wurden.

<iframe width="560" height="315" src="https://www.youtube.com/embed/-t7RO6mHATI?showinfo=0" frameborder="0" allowfullscreen></iframe>

### <a name="authentication-to-proxy-server"></a>Authentifizierung beim Proxyserver
Für Ihren Proxyserver ist möglicherweise eine Authentifizierung über ein Domänenbenutzerkonto erforderlich. Standardmäßig verwendet das Gateway eine Dienst-SID für den Anmeldebenutzer im Windows-Dienst. Dieses Problem kann durch das Ändern des Anmeldebenutzers in einen Domänenbenutzer behoben werden. Weitere Informationen finden Sie unter [Ändern des Gateway-Dienstkontos in einen Domänenbenutzer](../service-gateway-proxy.md#changing-the-gateway-service-account-to-a-domain-user).

### <a name="your-proxy-only-allows-ports-80-and-443-traffic"></a>Der Proxy lässt nur Datenverkehr über die Ports 80 und 443 zu.
Einige Proxys beschränken den Datenverkehr auf die Ports 80 und 443. Standardmäßig erfolgt die Kommunikation mit dem Azure Service Bus über andere Ports als 443.

Sie können erzwingen, dass das Gateway zur Kommunikation mit Azure Service Bus anstelle von TCP das HTTPS-Protokoll verwendet. Hierzu muss an der Datei *Microsoft.PowerBI.DataMovement.Pipeline.GatewayCore.dll.config* eine Änderung vorgenommen werden. Ändern Sie den Wert von `AutoDetect` in `Https`. Standardmäßig befindet sich diese Datei unter *C:\Programme\Lokales Datengateway*.

```
<setting name="ServiceBusSystemConnectivityModeString" serializeAs="String">
    <value>Https</value>
</setting>
```

## <a name="installation"></a>Installation
### <a name="error-failed-to-add-user-to-group---2147463168---pbiegwservice---performance-log-users---"></a>Fehler: Fehler beim Hinzufügen des Benutzers zur Gruppe.  (-2147463168 PBIEgwService Benutzer des Leistungsprotokolls)
Dieser Fehler wird möglicherweise angezeigt, wenn Sie versuchen, das Gateway auf einem Domänencontroller zu installieren. Das Bereitstellen auf einem Domänencontroller wird nicht unterstützt. Sie müssen das Gateway auf einem Computer bereitstellen, der kein Domänencontroller ist.

