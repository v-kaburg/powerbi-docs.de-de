---
title: Ausführliche Informationen zu On-premises data gateway
description: Dieser Artikel befasst sich ausführlich mit dem lokalen Gateway. Er beleuchtet die Funktionsweise des Diensts in Kombination mit Azure Active Directory und Ihrem lokalen Active Directory, wenn Sie Analysis Services nutzen.
services: powerbi
documentationcenter: ''
author: davidiseminger
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: powerbi
ms.date: 12/06/2017
ms.author: davidi
LocalizationGroup: Gateways
ms.openlocfilehash: 5ab3159be71fbefbbe034ce8f39f9df02b48ede3
ms.sourcegitcommit: 65426de556cd7207cbc4f478198664e25c33a769
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/30/2018
---
# <a name="on-premises-data-gateway-in-depth"></a>Ausführliche Informationen zu On-premises data gateway
Benutzer in Ihrer Organisation können auf lokale Daten zugreifen (für die sie bereits über Zugriffsberechtigungen verfügen). Bevor diese Benutzer jedoch eine Verbindung mit der lokalen Datenquelle herstellen können, muss ein lokales Datengateway installiert und konfiguriert werden. Das Gateway ermöglicht die schnelle und sichere, im Hintergrund ablaufende Kommunikation eines Benutzers in der Cloud mit Ihrer lokalen Datenquelle und zurück in die Cloud.

Das Installieren und Konfigurieren eines Gateways wird normalerweise von einem Administrator vorgenommen. Dazu sind möglicherweise fundierte Kenntnisse Ihrer lokalen Server und in bestimmten Fällen auch Serveradministratorberechtigungen erforderlich.

In diesem Artikel erhalten Sie keine schrittweise Anleitung zum Installieren und Konfigurieren des Gateways. Lesen Sie zu diesem Thema unbedingt den Artikel [Lokales Datengateway](service-gateway-onprem.md). Ziel dieses Artikels ist es, Ihnen einen detaillierten Einblick in die Funktionsweise des Gateways zu vermitteln. Es werden Benutzernamen und Sicherheitsaspekte sowohl bei Azure Active Directory als auch bei Analysis Services etwas erörtert. Außerdem wird besprochen, wie der Clouddienst die für die Anmeldung erforderliche E-Mail-Adresse, das Gateway und Active Directory nutzt, um eine sichere Verbindung mit Ihren lokalen Daten herzustellen und diese sicher abzufragen.

<!-- Shared Requirements Include -->
[!INCLUDE [gateway-onprem-requirements-include](./includes/gateway-onprem-how-it-works-include.md)]

<!-- Shared Install steps Include -->
[!INCLUDE [gateway-onprem-datasources-include](./includes/gateway-onprem-datasources-include.md)]

## <a name="sign-in-account"></a>Das Anmeldekonto
Benutzer melden sich entweder mit einem Geschäfts-, Schul- oder Unikonto an. Dies ist das Konto Ihrer Organisation. Wenn Sie sich für ein Office 365-Angebot registriert haben und nicht Ihre tatsächliche geschäftliche E-Mail-Adresse angegeben haben, könnte es wie „nancy@contoso.onmicrosoft.com“ aussehen. Ihr Konto wird innerhalb eines Clouddiensts in einem Mandanten in Azure Active Directory (AAD) gespeichert. In den meisten Fällen entspricht der UPN Ihres AAD-Kontos der E-Mail-Adresse.

## <a name="authentication-to-on-premises-data-sources"></a>Authentifizierung gegenüber lokalen Datenquellen
Für die Verbindung vom Gateway aus zu lokalen Datenquellen, mit Ausnahme von Analysis Services, werden gespeicherte Anmeldeinformationen verwendet. Das Gateway verwendet die gespeicherten Anmeldeinformationen bei allen Benutzern zur Verbindungsherstellung.

## <a name="authentication-to-a-live-analysis-services-data-source"></a>Authentifizierung gegenüber einer Analysis Services-Livedatenquelle
Bei jeder Interaktion eines Benutzers mit Analysis Services, wird der effektive Benutzername an das Gateway und von dort aus an Ihren lokalen Analysis Services-Server übergeben. Als effektiver Benutzer wird der Benutzerprinzipalname (user principal name; UPN) – üblicherweise die E-Mail-Adresse, mit der Sie sich in der Cloud anmelden – an Analysis Services übergeben. Der UPN wird in der Verbindungseigenschaft „EffectiveUserName“ übergeben. Diese E-Mail-Adresse muss mit einem in der lokalen Active Directory-Domäne definierten UPN übereinstimmen. Der UPN ist eine Eigenschaft des Active Directory-Kontos. Das Windows-Konto muss dann in einer Analysis Services-Rolle vorhanden sein, um Zugriff auf den Server zu erhalten. Die Anmeldung wird nicht erfolgreich durchgeführt, wenn in Active Directory keine Übereinstimmung gefunden werden kann.

Analysis Services kann darüber hinaus eine Filterfunktion basierend auf diesem Konto bereitstellen. Es kann sowohl auf Grundlage eines rollenbasierten Sicherheitsmodells als auch auf Grundlage eines Sicherheitsmodells auf Zeilenebene gefiltert werden.

## <a name="role-based-security"></a>Rollenbasierte Sicherheit
Modelle stellen Sicherheit auf der Grundlage von Benutzerrollen bereit. Rollen werden für ein bestimmtes Modellprojekt während der Erstellung in den SQL Server Data Tools – Business Intelligence (SSDT-BI) oder nach der Bereitstellung des Modells mithilfe von SQL Server Management Studio (SSMS) definiert. Rollen enthalten Mitglieder, die anhand ihres Windows-Benutzernamens oder ihrer Windows-Gruppe angegeben sind. Rollen definieren die Berechtigungen eines Benutzers zu Abfragen oder Aktionen im Modell. In der Praxis werden die meisten Benutzer einer Rolle mit Leseberechtigungen angehören. Andere Rollen sind für Administratoren mit der Berechtigung zum Verarbeiten von Elementen, Verwalten von Datenbankfunktionen und Verwalten anderer Rollen vorgesehen.

## <a name="row-level-security"></a>Sicherheit auf Zeilenebene
Sicherheit auf Zeilenebene ist eine für Analysis Services charakteristische Funktion. Modelle können dynamische Sicherheitseinstellungen auf Zeilenebene bereitstellen. Im Gegensatz zu Rollen, von denen mindestens eine erforderlich ist, die Benutzer enthält, ist dynamische Sicherheit für tabellarische Modelle grundsätzlich nicht erforderlich. Allgemein ausgedrückt definiert dynamische Sicherheit den Lesezugriff eines Benutzers auf Daten bis hinunter zu einer bestimmten Zeile in einer bestimmten Tabelle. Ähnlich wie Rollen beruht dynamische Sicherheit auf Zeilenebene auf den Windows-Benutzernamen von Benutzern.

Die Berechtigung eines Benutzers, Daten des Modells abzufragen und anzuzeigen, wird erstens durch die Rollen bestimmt, deren Mitglied sein Windows-Benutzerkonto ist, und zweitens durch die dynamische Sicherheit auf Zeilenebene, sofern sie konfiguriert ist.

Das Implementieren von rollenbasierter Sicherheit und dynamischer Sicherheit auf Zeilenebene in Modellen würde den Rahmen dieses Artikels sprengen.  Weitere Informationen finden Sie unter [Rollen (SSAS – tabellarisch)](https://msdn.microsoft.com/library/hh213165.aspx) und [Sicherheitsrollen (Analysis Services – mehrdimensionale Daten)](https://msdn.microsoft.com/library/ms174840.aspx) auf MSDN. Eine besonders fundierte Darstellung der Sicherheit in tabellarischen Modellen finden Sie im Whitepaper [Securing the Tabular BI Semantic Model](https://msdn.microsoft.com/library/jj127437.aspx) (Sichern des semantischen BI-Tabellenmodells).

## <a name="what-about-azure-active-directory"></a>Welche Rolle spielt Azure Active Directory?
Die Clouddienste von Microsoft verwenden [Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-whatis/) für die Authentifizierung von Benutzern. Azure Active Directory ist der Mandant, der die Benutzernamen und Sicherheitsgruppen enthält. In der Regel entspricht die E-Mail-Adresse, mit der sich ein Benutzer anmeldet, dem UPN des Kontos.

Welcher Rolle gehört mein lokales Active Directory an?

Damit Analysis Services bestimmen kann, ob ein Benutzer, der eine Verbindung mit ihm herstellt, einer Rolle angehört, die über Berechtigungen zum Lesen von Daten verfügt, muss der Server den von AAD an das Gateway und an den Analysis Services-Server übergebenen effektiven Benutzernamen konvertieren. Der Analysis Services-Server übergibt den effektiven Benutzernamen an einen Windows Active Directory-Domänencontroller (DC). Der Active Directory-DC überprüft dann, ob der effektive Benutzername ein gültiger UPN ist, und gibt den Windows-Benutzernamen des betreffenden Benutzers an den Analysis Services-Server zurück.

EffectiveUserName kann nicht auf einem Analysis Services-Server verwendet werden, der nicht mit der Domäne verknüpft ist. Der Analysis Services-Server muss einer Domäne angehören, um Anmeldefehler zu vermeiden.

## <a name="how-do-i-tell-what-my-upn-is"></a>Woher weiß ich meinen UPN?
Sie kennen möglicherweise nicht Ihren UPN und sind auch kein Domänenadministrator. Sie können den folgenden Befehl von Ihrer Arbeitsstation ausführen, um den UPN für Ihr Konto zu ermitteln.

    whoami /upn

Das Ergebnis ähnelt einer E-Mail-Adresse, es handelt sich aber um den UPN für Ihr lokales Domänenkonto. Wenn Sie eine Analysis Services-Datenquelle für Liveverbindungen verwenden, muss diese mit der vom Gateway an EffectiveUserName übergebenen übereinstimmen.

## <a name="mapping-usernames-for-analysis-services-data-sources"></a>Zuordnen von Benutzernamen zu Analysis Services-Datenquellen
Power BI ermöglicht die Zuordnung von Benutzernamen zu Analysis Services-Datenquellen. Sie können Regeln konfigurieren, um einen in Power BI angemeldeten Benutzernamen einem Namen zuzuordnen, der in EffectiveUserName über die Analysis Services-Verbindung übergeben wird. Diese Funktion zur Zuordnung von Benutzernamen ist eine hervorragende Möglichkeit, das Problem zu umgehen, wenn Ihr Benutzername für AAD nicht mit einem UPN in Ihrem lokalen Active Directory übereinstimmt. Wenn Ihre E-Mail-Adresse beispielsweise nancy@contoso.onmicrsoft.com lautet, könnten Sie diese nancy@contoso.com zuordnen. Dieser Wert würde dann an das Gateway übergeben. Erfahren Sie mehr über das [Zuordnen von Benutzernamen](service-gateway-enterprise-manage-ssas.md#map-user-names).

## <a name="synchronize-an-on-premises-active-directory-with-azure-active-directory"></a>Synchronisieren eines lokalen Active Directorys mit Azure Active Directory
Ihre lokalen Active Directory-Konten sollten denen in Azure Active Directory entsprechen, wenn Sie planen, Analysis Services-Liveverbindungen zu verwenden. Ebenso wie der UPN der Konten übereinstimmen muss.

Die Clouddienste haben nur Kenntnis von Konten in Azure Active Directory. Es spielt keine Rolle, wenn Sie ein Konto in Ihrem lokalen Active Directory hinzufügen. Wenn es in AAD nicht vorhanden ist, kann es nicht verwendet werden. Es gibt verschiedene Möglichkeiten, Ihre lokalen Active Directory-Konten mit Azure Active Directory abzugleichen.

1. Sie können Konten in Azure Active Directory manuell hinzufügen.
   
   Sie können im Azure-Portal oder im Office 365 Admin Portal ein Konto erstellen, bei dem der Kontoname dem UPN des lokalen Active Directory-Kontos entspricht.
2. Sie können das [Azure AD Connect](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect/)-Tool verwenden, um lokale Konten mit Ihrem Azure Active Directory-Mandanten zu synchronisieren.
   
   Das Azure AD Connect-Tool stellt Optionen für die Synchronisierung des Verzeichnisses und des Kennworts bereit. Wenn Sie weder ein Mandantenadministrator noch ein lokaler Domänenadministrator sind, müssen Sie sich für diese Konfiguration an Ihren IT-Administrator wenden.
3. Sie können Active Directory-Verbunddienste (Active Directory Federation Services; AD FS) konfigurieren.
   
   Sie können den AD FS-Server mithilfe des [Azure AD Connect](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect/)-Tools Ihrem AAD-Mandanten zuordnen. AD FS verwendet die zuvor erwähnte Verzeichnissynchronisierung, erlaubt aber auch das einmalige Anmelden (Single Sign-On; SSO). Wenn Sie sich beispielsweise in Ihrem Arbeitsplatznetzwerk befinden und sich bei einem Clouddienst anmelden möchten, werden Sie möglicherweise nicht dazu aufgefordert, Ihren Benutzernamen oder Ihr Kennwort einzugeben. Sie müssen mit Ihrem IT-Administrator besprechen, ob diese Funktion für Ihre Organisation verfügbar ist.

Mit Azure AD Connect können Sie sicherstellen, dass der UPN Ihres AAD-Kontos und der Ihres lokalen Active Directory-Kontos übereinstimmen.

> [!NOTE]
> Das Synchronisieren von Konten mithilfe des Azure AD Connect-Tools erstellt neue Konten in Ihrem AAD-Mandanten.
> 
> 

## <a name="now-this-is-where-the-gateway-comes-in"></a>Das Gateway
Das Gateway fungiert als Brücke zwischen der Cloud und Ihrem lokalen Server. Die Datenübertragung zwischen der Cloud und dem Gateway ist mithilfe des [Azure Service Bus](https://azure.microsoft.com/documentation/services/service-bus/) geschützt. Der Service Bus erstellt einen sicheren Kanal zwischen der Cloud und Ihrem lokalen Server über eine ausgehende Verbindung auf dem Gateway.  Sie müssen dazu keine eingehenden Verbindungen in Ihrer lokalen Firewall zulassen.

Wenn Sie über eine Analysis Services-Datenquelle verfügen, müssen Sie das Gateway auf einem Computer installieren, der der gleichen Gesamtstruktur oder Domäne wie der Analysis Services-Server angehört.

Je kürzer die Entfernung zwischen Gateway und Server, desto schneller ist die Verbindung. Eine Netzwerklatenz zwischen Gateway und Server lässt sich am besten vermeiden, indem das Gateway auf dem gleichen Server wie die Datenquelle installiert wird.

## <a name="what-to-do-next"></a>Nächste Schritte
Nachdem Sie das Gateway installiert haben, sollten Sie die Datenquellen für dieses Gateway erstellen. Sie können Datenquellen im Bildschirm **Gateways verwalten** hinzufügen. Weitere Informationen finden Sie in den Artikeln zum Verwalten von Datenquellen.

[Verwalten Ihrer Datenquelle – Analysis Services](service-gateway-enterprise-manage-ssas.md)  
[Verwalten Ihrer Datenquelle –SAP HANA](service-gateway-enterprise-manage-sap.md)  
[Verwalten Ihrer Datenquelle – SQL Server](service-gateway-enterprise-manage-sql.md)  
[Verwalten der Datenquelle – Oracle](service-gateway-onprem-manage-oracle.md)  
[Verwalten der Datenquelle – Import/Geplante Aktualisierung](service-gateway-enterprise-manage-scheduled-refresh.md)  

## <a name="where-things-can-go-wrong"></a>An welchen Stellen etwas schief gehen kann
Manchmal tritt beim Installieren des Gateways ein Fehler auf. Oder aber die Installation des Gateways scheint erfolgreich verlaufen zu sein, und der Dienst kann es trotzdem nicht verwenden. Oft hat das Problem eine ganz einfache Ursache, z. B. das Kennwort für die Anmeldeinformationen, mit denen das Gateway bei der Datenquelle angemeldet wird.

In anderen Fällen können Probleme mit dem E-Mail-Adresstyp auftreten, den Benutzer für die Anmeldung verwenden, oder Analysis Services kann einen effektiven Benutzernamen nicht auflösen. Wenn Sie über mehrere Domänen mit eingerichteten Vertrauensstellungen verfügen und ihr Gateway sich in der einen, Analysis Services sich aber in einer anderen befindet, kann das manchmal zu Problemen führen.

Anstatt hier ausführlich auf die Behandlung von Gatewayproblemen einzugehen, haben wir eine Reihe von Tipps zur Problembehandlung im Artikel [Problembehandlung beim lokalen Datengateway](service-gateway-onprem-tshoot.md) zusammengestellt. Hoffentlich treten bei Ihnen keine Probleme auf. Falls aber doch, sollte Ihr Verständnis dieser Zusammenhänge in Verbindung mit dem Artikel zur Problembehandlung weiterhelfen.

<!-- Account and Port information -->
[!INCLUDE [gateway-onprem-accounts-ports-more](./includes/gateway-onprem-accounts-ports-more.md)]

## <a name="next-steps"></a>Nächste Schritte
[Problembehandlung beim lokalen Datengateway](service-gateway-onprem-tshoot.md)  
[Azure Service Bus](https://azure.microsoft.com/documentation/services/service-bus/)  
[Azure AD Connect](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect/)  
Weitere Fragen? [Wenden Sie sich an die Power BI-Community](http://community.powerbi.com/)

