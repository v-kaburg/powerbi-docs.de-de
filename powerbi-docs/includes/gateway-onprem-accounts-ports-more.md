## <a name="sign-in-account"></a>Das Anmeldekonto
Benutzer melden sich entweder mit einem Geschäfts-, Schul- oder Unikonto an. Dies ist das Konto Ihrer Organisation. Wenn Sie sich für ein Office 365-Angebot registriert haben und nicht Ihre tatsächliche geschäftliche E-Mail-Adresse angegeben haben, könnte es wie „nancy@contoso.onmicrosoft.com“ aussehen. Ihr Konto wird innerhalb eines Clouddiensts in einem Mandanten in Azure Active Directory (AAD) gespeichert. In den meisten Fällen entspricht der UPN Ihres AAD-Kontos der E-Mail-Adresse.

## <a name="windows-service-account"></a>Windows-Dienstkonto
Das lokale Datengateway ist so konfiguriert, dass als Anmeldeinformationen für den Windows-Dienst *NT SERVICE\PBIEgwService* verwendet wird. Das Gateway hat standardmäßig die Berechtigung „Anmelden als Dienst“. Diese befindet sich im Kontext des Computers, auf dem das Gateway installiert wird.

> [!NOTE]
> Wenn Sie den persönlichen Modus ausgewählt haben, konfigurieren Sie das Windows-Dienstkonto separat.
> 
> 

Dies ist nicht das Konto, das für die Verbindung mit lokalen Datenquellen verwendet wird.  Dies ist auch nicht Ihr Geschäfts-, Schul- oder Unikonto, mit dem Sie sich bei Clouddiensten anmelden.

Wenn aufgrund der Authentifizierung Probleme beim Proxyserver auftreten, sollten Sie das Windows-Dienstkonto in ein Domänenbenutzerkonto oder verwaltetes Dienstkonto ändern. Erfahren Sie, wie Sie das Konto in der [Proxykonfiguration](../service-gateway-proxy.md#changing-the-gateway-service-account-to-a-domain-user) ändern.

## <a name="ports"></a>Ports
Das Gateway stellt eine ausgehende Verbindung mit Azure Service Bus her. Die Kommunikation erfolgt über die ausgehenden Ports TCP 443 (Standardwert), 5671, 5672, 9350 bis 9354.  Das Gateway benötigt keine eingehenden Ports. [Weitere Informationen](https://azure.microsoft.com/documentation/articles/service-bus-fundamentals-hybrid-solutions/)

Es wird empfohlen, in der Firewall die Blockierung der IP-Adressen für Ihren Datenbereich aufzuheben. Sie können die [Liste der Microsoft Azure Datacenter IP-Adressen](https://www.microsoft.com/download/details.aspx?id=41653) herunterladen. Diese Liste wird wöchentlich aktualisiert. Das Gateway verwendet für die Kommunikation mit Azure Service Bus die IP-Adresse zusammen mit dem vollständig qualifizierten Domänennamen (Fully Qualified Domain Name, FQDN). Wenn Sie für das Gateway Kommunikation per HTTPS erzwingen, verwendet das Gateway ausschließlich den FQDN, und es erfolgt keine Kommunikation mithilfe von IP-Adressen.

> [!NOTE]
> Die IP-Adressen in der Liste der Azure-Datacenter-IP-Adressen sind in CIDR-Notation angegeben. Beispielsweise bedeutet „10.0.0.0/24“ nicht „10.0.0.0 bis 10.0.0.24“. Erfahren Sie mehr zur [CIDR-Notation](http://whatismyipaddress.com/cidr).
> 
> 

Es folgt eine Liste der vollqualifizierten Domänennamen, die vom Gateway verwendet werden.

| Domänennamen | Ausgehende Ports | Beschreibung |
| --- | --- | --- |
| *.download.microsoft.com |80 |Zum Herunterladen des Installationsprogramms wird HTTP verwendet. |
| *.powerbi.com |443 |HTTPS |
| *.analysis.windows.net |443 |HTTPS |
| *.login.windows.net |443 |HTTPS |
| *.servicebus.windows.net |5671-5672 |Advanced Message Queuing Protocol (AMQP) |
| *.servicebus.windows.net |443, 9350-9354 |Listener an Service Bus Relay über TCP (erfordert 443 für Bezug des Access Control-Tokens) |
| *.frontend.clouddatahub.net |443 |HTTPS |
| *.core.windows.net |443 |HTTPS |
| login.microsoftonline.com |443 |HTTPS |
| *. msftncsi.com |443 |Wird zum Testen der Internetverbindung verwendet, wenn der Power BI-Dienst das Gateway nicht erreichen kann. |
| *.microsoftonline-p.com |443 |Wird abhängig von der Konfiguration für die Authentifizierung verwendet. |

> [!NOTE]
> Datenverkehr von „visualstudio.com“ oder „visualstudioonline.com“ wird für Einblicke in die App benötigt und ist für die Funktion des Gateways nicht erforderlich.
> 
> 

## <a name="forcing-https-communication-with-azure-service-bus"></a>Erzwingen der HTTPS-Kommunikation mit Azure Service Bus
Sie können erzwingen, dass das Gateway zur Kommunikation mit Azure Service Bus anstelle von TCP das HTTPS-Protokoll verwendet. Dies kann die Leistung beeinträchtigen. Ändern Sie zu diesem Zweck die Datei *Microsoft.PowerBI.DataMovement.Pipeline.GatewayCore.dll.config*, indem Sie den Wert von `AutoDetect` in `Https` ändern, wie im Codeausschnitt direkt nach diesem Abschnitt gezeigt. Diese Datei befindet sich (standardmäßig) unter *C:\Programme\Lokales Datengateway*.

```
<setting name="ServiceBusSystemConnectivityModeString" serializeAs="String">
    <value>Https</value>
</setting>
```

Beim Wert des *ServiceBusSystemConnectivityModeString*-Parameters muss die Groß-Kleinschreibung beachtet werden. Gültige Werte sind *AutoDetect* und *Https*.

Alternativ können Sie ab der Version von [März 2017](https://powerbi.microsoft.com/blog/power-bi-gateways-march-update/) mithilfe der Gateway-Benutzeroberfläche dieses Verhalten des Gateways erzwingen. Wählen Sie auf der Gateway-Benutzeroberfläche **Netzwerk** aus, und wählen Sie dann für **Azure Service Bus-Konnektivitätsmodus** die Option **Ein** aus.

![](./media/gateway-onprem-accounts-ports-more/gw-onprem_01.png)

Wenn Sie nach dem Durchführen der Änderung **Übernehmen** (eine Schaltfläche, die nur angezeigt wird, wenn Sie eine Änderung vornehmen) auswählen, wird der *Windows-Dienst Gateway* automatisch neu gestartet, damit die Änderung wirksam werden kann.

In ähnlichen Situationen in der Zukunft können Sie den *Windows-Dienst Gateway* über das Dialogfeld neu starten, indem Sie **Diensteinstellungen** und dann *Jetzt neu starten* auswählen.

![](./media/gateway-onprem-accounts-ports-more/gw-onprem_02.png)

## <a name="support-for-tls-1112"></a>Unterstützung für TLS 1.1/1.2
Ab dem Update von August 2017 verwendet das lokale Datengateway für die Kommunikation mit dem **Power BI-Dienst** standardmäßig Transport Layer Security (TLS) 1.1 bzw. 1.2. Frühere Versionen des lokalen Datengateways verwenden standardmäßig TLS 1.0. Am 15. Januar 2018 endet die Unterstützung für TLS 1.0, einschließlich der Fähigkeit des Gateways, mit dem **Power BI-Dienst** über TLS 1.0 zu interagieren. Bis zu diesem Zeitpunkt müssen Sie also ein Upgrade Ihrer Installationen des lokalen Datengateways auf das Release vom August 2017 oder ein neueres Release durchführen, damit Ihre Gateways funktionsfähig bleiben.

Es ist zu beachten, dass vor dem 1. November TLS 1.0 durch das lokale Datengateway immer noch unterstützt und als Fallbackmechanismus verwendet wird. Um sicherzustellen, dass für sämtlichen Datenverkehr im Gateway TLS 1.1 oder 1.2 verwendet wird (und um die Verwendung von TLS 1.0 im Gateway zu verhindern), müssen Sie auf dem Computer, auf dem der Gatewaydienst ausgeführt wird, die folgenden Registrierungsschlüssel hinzufügen oder ändern:

        [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\v4.0.30319]"SchUseStrongCrypto"=dword:00000001
        [HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\.NETFramework\v4.0.30319]"SchUseStrongCrypto"=dword:00000001

> [!NOTE]
> Durch Hinzufügen bzw. Ändern dieser Registrierungsschlüssel wird die Änderung auf alle .NET-Anwendungen angewendet. Weitere Informationen zu den Registrierungsänderungen mit Auswirkungen auf TLS für andere Anwendungen finden Sie unter [TLS-Registrierungseinstellungen (Transport Layer Security)](https://docs.microsoft.com/windows-server/security/tls/tls-registry-settings).
> 
> 

## <a name="how-to-restart-the-gateway"></a>So starten Sie das Gateway neu
Das Gateway wird als Windows-Dienst ausgeführt. Sie können es wie jeden anderen Windows-Dienst starten und beenden. Es gibt mehrere Möglichkeiten, dies zu tun. In der Eingabeforderung müssen Sie daher wie folgt vorgehen:

1. Starten Sie auf dem Computer, auf dem das Gateway ausgeführt wird, eine Administratoreingabeaufforderung.
2. Verwenden Sie den folgenden Befehl zum Beenden des Diensts.
   
   net stop PBIEgwService
3. Verwenden Sie den folgenden Befehl zum Starten des Diensts.
   
   net start PBIEgwService

