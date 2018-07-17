## <a name="firewall-or-proxy"></a>Firewall oder Proxy
Informationen zum Bereitstellen von Proxyinformationen für Ihr Gateway finden Sie unter [Konfigurieren von Proxyeinstellungen für Power BI Gateways](../service-gateway-proxy.md).

Sie können mit dem Befehl [Test-NetConnection](https://docs.microsoft.com/powershell/module/nettcpip/test-netconnection) in einer PowerShell-Eingabeaufforderung testen, ob Ihre Firewall oder Ihr Proxy Verbindungen blockiert. Damit wird die Verbindung zum Azure Service Bus getestet. Es wird dadurch nur die Netzwerkverbindung getestet. Dies hat nichts mit dem Cloudserverdienst oder dem Gateway zu tun. Der Test hilft Ihnen dabei, zu bestimmen, ob Ihr Computer wirklich eine Verbindung mit dem Internet herstellen kann.

    Test-NetConnection -ComputerName watchdog.servicebus.windows.net -Port 9350

> [!NOTE]
> „Test-NetConnection“ ist nur unter Windows Server 2012 R2 und höher sowie unter Windows 8.1 und höher verfügbar. Bei früheren Betriebssystemversionen können Sie „Telnet“ verwenden, um die Konnektivität von Ports zu überprüfen.
> 
> 

Sie sollten in etwa folgende Ergebnisse erhalten. „TcpTestSucceeded“ wird vermutlich abweichen. Wenn **TcpTestSucceeded** nicht *true* ist, wird der Zugriff möglicherweise durch eine Firewall blockiert.

    ComputerName           : watchdog.servicebus.windows.net
    RemoteAddress          : 70.37.104.240
    RemotePort             : 5672
    InterfaceAlias         : vEthernet (Broadcom NetXtreme Gigabit Ethernet - Virtual Switch)
    SourceAddress          : 10.120.60.105
    PingSucceeded          : False
    PingReplyDetails (RTT) : 0 ms
    TcpTestSucceeded       : True

Für ein umfassendes Ergebnis können Sie die Werte **ComputerName** und **Port** durch die Angaben für [Ports](../service-gateway-onprem.md#ports) ersetzen.

Die Firewall blockiert möglicherweise auch die Verbindungen, die vom Azure Service Bus zu den Azure-Rechenzentren hergestellt werden. In diesem Fall müssen Sie die Blockierung der IP-Adressen Ihrer Region für diese Rechenzentren aufheben (freigeben). [Hier](https://www.microsoft.com/download/details.aspx?id=41653) finden Sie eine Liste der Azure IP-Adressen.

