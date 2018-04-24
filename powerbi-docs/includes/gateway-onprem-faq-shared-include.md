## <a name="general"></a>Allgemein
**Frage:** Wie wird der eigentliche Windows-Dienst genannt?  
**Antwort:** Der Name des Gateways unter „Dienste“ lautet „On-premises data gateway service“

**Frage:** Was sind die Anforderungen für das Gateway?  
**Antwort:** Sehen Sie sich den Abschnitt „Anforderungen“ im [Hauptartikel zum Gateway](../service-gateway-onprem.md) an.

**Frage:** Welche Datenquellen werden vom Gateway unterstützt?  
**Antwort:** Sehen Sie sich die Tabelle mit Datenquellen im [Hauptartikel zum Gateway](../service-gateway-onprem.md) an.

**Frage:** Benötige ich ein Gateway für Clouddatenquellen wie Azure SQL-Datenbank?  
**Antwort:** Nein! Der Dienst wird auch ohne Gateway eine Verbindung mit dieser Datenquelle herstellen können.

**Frage:** Gibt es irgendwelche eingehenden Verbindungen von der Cloud zum Gateway?  
**Antwort:** Nein. Das Gateway verwendet ausgehende Verbindungen mit Azure Service Bus.

**Frage:** Was geschieht, wenn ich ausgehende Verbindungen blockiere? Was muss ich öffnen?  
**Antwort:** Sehen Sie sich die [Liste von Ports](../service-gateway-onprem.md#ports) und Hosts an, die das Gateway verwendet.

**Frage:** Muss das Gateway auf demselben Computer wie die Datenquelle installiert werden?  
**Antwort:** Nein. Das Gateway verbindet sich mit der Datenquelle mithilfe der Verbindungsinformationen, die bereitgestellt wurden. Stellen Sie sich das Gateway so gesehen als Clientanwendung vor. Es muss nur in der Lage sein, eine Verbindung mit dem bereitgestellten Servernamen herzustellen.

**Frage:** Was ist die Latenzzeit für das Ausführen von Abfragen an eine Datenquelle aus dem Gateway? Was ist die beste Architektur?  
**Antwort:** Es wird empfohlen, das Gateway so nahe wie möglich an der Datenquelle zu haben, um Netzwerklatenz zu vermeiden. Wenn Sie das Gateway auf der tatsächlichen Datenquelle installieren können, wird die Latenz minimiert. Bedenken Sie auch die Rechenzentren. Wenn Ihr Dienst z.B. das Rechenzentrum USA (Westen) verwendet und Ihr SQL Server auf einer Azure-VM gehostet wird, sollte sich die Azure-VM ebenfalls im Rechenzentrum USA (Westen) befinden. Dadurch wird die Latenz minimiert, und Kosten für ausgehende Daten auf der Azure-VM werden vermieden.

**Frage:** Gibt es Anforderungen an die Netzwerkbandbreite?  
**Antwort:** Es wird empfohlen, über einen guten Durchsatz für die Netzwerkverbindung zu verfügen. Jede Umgebung ist anders, und dies hängt auch von der Datenmenge ab, die gesendet wird. Mithilfe von ExpressRoute könnten Sie einen gewissen Durchsatz zwischen lokalen und den Azure-Rechenzentren gewährleisten.

Sie können die Drittanbieterapp [Azure Speed Test](http://azurespeedtest.azurewebsites.net/) verwenden, um Ihren Durchsatz zu messen.

**Frage:** Kann das Gateway „Windows-Dienst“ über ein Azure Active Directory-Konto ausgeführt werden?  
**Antwort:** Nein. Der Windows-Dienst muss über ein gültiges Windows-Konto verfügen. Standardmäßig wird er mit der Dienst-SID *NT SERVICE\PBIEgwService* ausgeführt.

**Frage:** Wie werden Ergebnisse zurück in die Cloud gesendet?  
**Antwort:** Dies erfolgt über Azure Service Bus. Weitere Informationen finden Sie im Artikel zur [Funktionsweise](../service-gateway-onprem.md#how-the-gateway-works).

**Frage:** Wo werden meine Anmeldeinformationen gespeichert?  
**Antwort:** Die Anmeldeinformationen, die Sie für eine Datenquelle eingeben, werden verschlüsselt im Gatewayclouddienst gespeichert. Die Anmeldeinformationen werden im lokalen Gateway entschlüsselt.

**Frage:** Kann ich das Gateway in einem Umkreisnetzwerk (auch bezeichnet als abgeschirmtes Subnetz, demilitarisierte Zone oder DMZ) platzieren?  
**Antwort:** Das Gateway erfordert eine Verbindung mit der Datenquelle. Wenn die Datenquelle nicht im Perimeternetzwerk zugänglich ist, kann das Gateway möglicherweise keine Verbindung mit ihr herstellen. Beispielsweise ist SQL Server eventuell nicht im Perimeternetzwerk vorhanden. Und Sie können aus dem Perimeternetzwerk keine Verbindung mit dem SQL Server herstellen. Wenn Sie das Gateway im Perimeternetzwerk platzieren, kann es nicht mit SQL Server kommunizieren.

**Frage:** Kann erzwungen werden, dass das Gateway über das HTTPS-Protokoll statt über TCP mit Azure Service Bus kommuniziert?  
**Antwort:** Ja. Dadurch wird allerdings die Leistung erheblich beeinträchtigt. Hierzu muss eine Änderung an der Datei *Microsoft.PowerBI.DataMovement.Pipeline.GatewayCore.dll.config* vorgenommen werden. Ändern Sie den Wert von `AutoDetect` in `Https`. Standardmäßig befindet sich diese Datei unter *C:\Programme\Lokales Datengateway*.

**Frage:** Muss ich die Liste der Azure Datacenter-IP-Adressen auf eine Positivliste setzen? Wo erhalte ich die Liste?  
**Antwort:** Wenn Sie ausgehenden IP-Datenverkehr blockieren, müssen Sie die Liste der Azure Datacenter-IP-Adressen möglicherweise auf eine Positivliste setzen. Derzeit verwendet das Gateway für die Kommunikation mit Azure Service Bus zusätzlich zum vollständig qualifizierten Domänennamen die IP-Adresse. Die Liste der Azure Datacenter-IP-Adressen wird wöchentlich aktualisiert. Sie können die [Liste der Microsoft Azure Datacenter IP-Adressen](https://www.microsoft.com/download/details.aspx?id=41653) herunterladen.

```
<setting name="ServiceBusSystemConnectivityModeString" serializeAs="String">
    <value>Https</value>
</setting>
```

## <a name="high-availabilitydisaster-recovery"></a>Hohe Verfügbarkeit/Notfallwiederherstellung
**Frage:** Ist es geplant, Szenarios mit Hochverfügbarkeit für das Gateway zu aktivieren?  
**Antwort:** Ja, dies ist ein Bereich, der vom Power BI-Team bearbeitet werden wird. Bitte informieren Sie sich im [Power BI-Blog](https://powerbi.microsoft.com/blog/) über Neuigkeiten zu diesem Feature.

**Frage:** Welche Optionen für die Notfallwiederherstellung sind verfügbar?  
**Antwort:** Sie können den Wiederherstellungsschlüssel zum Wiederherstellen oder Verschieben des Gateways verwenden. Wenn Sie das Gateway installieren, stellen Sie den Wiederherstellungsschlüssel bereit.

**Frage:** Was ist der Vorteil des Wiederherstellungsschlüssels?  
**Antwort:** Er bietet eine Möglichkeit zum Migrieren oder Wiederherstellen Ihrer Gatewayeinstellungen. Er wird auch für die Notfallwiederherstellung verwendet.

## <a name="troubleshooting"></a>Problembehandlung
**Frage:** Wo werden die Gatewayprotokolle gespeichert?  
**Antwort:** Sehen Sie sich den Abschnitt „Tools“ im [Artikel zur Problembehandlung](../service-gateway-onprem-tshoot.md#tools-for-troubleshooting) an.

**Frage:** Wie kann ich sehen, welche Abfragen an die lokale Datenquelle gesendet werden?  
**Antwort:** Sie können die Abfrageablaufverfolgung aktivieren.  Dies schließt die Abfragen ein, die gesendet werden. Denken Sie daran, diese Einstellung nach der Problembehandlung wieder auf den ursprünglichen Wert festzulegen. Wenn die Abfrageablaufverfolgung aktiviert ist, werden die Protokolle größer.

Sie können sich auch die Tools zum Verfolgen von Abfragen ansehen, über die Ihre Datenquelle verfügt. Für SQL Server und Analysis Services können Sie z.B. Erweiterte Ereignisse oder SQL Profiler verwenden.

