---
title: Veelvoorkomende problemen met de intune Exchange connector oplossen
titleSuffix: Microsoft Intune
description: Problemen oplossen en veelvoorkomende problemen oplossen voor de on-premises Microsoft Intune Exchange-connector.
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 11/26/2019
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: de365312a7d293527c3c83fbbd84ab55de41d530
ms.sourcegitcommit: 23e9c48348a6eba494d072a2665b7481e5b5c84e
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 11/26/2019
ms.locfileid: "74547676"
---
# <a name="resolve-common-problems-with-the-intune-exchange-connector"></a>Veelvoorkomende problemen met de intune Exchange connector oplossen
 
Dit artikel kan de intune-beheerder helpen bij het oplossen van veelvoorkomende problemen met de werking van de intune Exchange connector.

Raadpleeg voor informatie over het oplossen van problemen [de intune on-premises Exchange connector problemen met](troubleshoot-exchange-connector.md) de algemene gegevens over de connector. Bekijk ook algemene problemen voor de configuratie van de connector.

## <a name="an-exchange-activesync-device-isnt-discovered-from-exchange"></a>Een Exchange ActiveSync-apparaat wordt niet gedetecteerd door Exchange

Wanneer er geen Exchange ActiveSync-apparaat wordt gedetecteerd vanuit Exchange, [controleert u de activiteit van de Exchange-connector](exchange-connector-install.md#on-premises-intune-exchange-connector-high-availability-support) om te zien of de Exchange-connector wordt gesynchroniseerd met de Exchange-Server. Als er geen synchronisatie is uitgevoerd sinds het apparaat is toegevoegd, verzamelt u de synchronisatie logboeken en koppelt u deze aan een ondersteunings aanvraag. Als een volledige synchronisatie of snelle synchronisatie is voltooid nadat het apparaat is toegevoegd, controleert u de volgende problemen:

- Zorg ervoor dat gebruikers beschikken over een intune-licentie. Als dat niet het geval is, detecteert de Exchange-connector hun apparaten niet.

- Als het primaire SMTP-adres van een gebruiker anders is dan de UPN (user principal name) in Azure Active Directory (Azure AD), detecteert de Exchange-connector geen enkel apparaat voor die gebruiker. Corrigeer het primaire SMTP-adres om het probleem op te lossen.

- Als u zowel een Exchange 2010- als Exchange 2013-postvakserver in uw omgeving hebt, kunt u de Exchange-connector het beste laten verwijzen naar een Exchange 2013-CAS (Client Access Aerver). Als de Exchange-connector is ingesteld om te communiceren met een Exchange 2010-CAS, kan de Exchange-connector geen apparaten van gebruikers detecteren in Exchange 2013.

- Voor Exchange Online-specifieke omgevingen moet u de Exchange-connector naar een Exchange 2013-CAS (geen Exchange 2010-CA'S) verwijzen in de toegewezen omgeving tijdens de eerste installatie. De connector communiceert alleen met Exchange 2013-CA'S wanneer Power shell-cmdlets worden uitgevoerd.

## <a name="problems-with-the-notification-email-message"></a>Problemen met het e-mail bericht voor meldingen

Als u voorwaardelijke toegang wilt ondersteunen voor on-premises post vakken op apparaten waarop Android Knox niet wordt uitgevoerd, moet u ervoor zorgen dat de intune-inschrijving wordt gestart vanuit het e-mail bericht ' nu aan de slag ' dat door de intune Exchange connector wordt verzonden. Als u de inschrijving van het bericht start, zorgt u ervoor dat het apparaat een unieke ActiveSyncID ontvangt voor alle platformen (Exchange, Azure AD, intune).

Een gebruiker ontvangt mogelijk geen e-mail bericht met de melding omdat:

- Het meldings account is onjuist ingesteld.
- Automatische detectie voor het meldings account is mislukt.
- De Exchange Web Services (EWS)-aanvraag voor het verzenden van het e-mail bericht is mislukt.

Bekijk de volgende secties om problemen met e-mail meldingen op te lossen.

### <a name="check-the-notification-account-that-retrieves-autodiscover-settings"></a>Controleer het account voor meldingen dat instellingen voor automatische detectie ophaalt

1. Zorg ervoor dat de Autodiscover-service en EWS zijn geconfigureerd op de Exchange Client Access-services. Zie voor meer informatie [Services voor client toegang](https://docs.microsoft.com/Exchange/architecture/client-access/client-access) en de [service autodis cover in Exchange Server](https://docs.microsoft.com/Exchange/architecture/client-access/autodiscover?view=exchserver-2019).

2. Controleer of uw meldings account aan de volgende vereisten voldoet:

   - Het account heeft een actief postvak dat wordt gehost door uw Exchange on-premises server.

   - De UPN van het account komt overeen met het SMTP-adres.

3. Automatische detectie vereist een DNS-server met een DNS-record voor **Autodiscover.SMTPdomain.com** (bijvoorbeeld Autodiscover.contoso.com) die verwijst naar de Exchange-Server voor client toegang. Geef uw FQDN op in plaats van *Autodiscover.SMTPdomain.com* en voer de volgende stappen uit om de record te controleren:

   1. Voer bij een opdracht prompt *nslookup*in.

   2. Voer *Autodiscover.SMTPdomain.com*in. De uitvoer moet er ongeveer uitzien als de volgende afbeelding: ![Nslookup-resultaten](./media/troubleshoot-exchange-connector-common-problems/nslookup-results.png
      )

   U kunt ook de service autodis cover van Internet op https://testconnectivity.microsoft.com testen. U kunt het ook testen vanuit een lokaal domein met behulp van het hulp programma micro soft Connectivity Analyzer. Zie het [hulp programma micro soft Connectivity Analyzer](https://docs.microsoft.com/previous-versions/office/exchange-remote-connectivity/jj851141(v=exchg.80))voor meer informatie.


### <a name="check-autodiscovery"></a>Automatische detectie controleren

Als automatische detectie mislukt, voert u de volgende stappen uit:

1. [Configureer een geldige automatische detectie DNS-record](https://docs.microsoft.com/previous-versions/exchange-server/exchange-150/mt473798(v=exchg.150)).

2. Harde code de EWS-URL in het configuratie bestand van de intune Exchange connector:

   1. Bepaal de EWS-URL. De standaard EWS-URL voor Exchange is `https://<mailServerFQDN>/ews/exchange.asmx`, maar uw URL kan anders zijn. Neem contact op met de Exchange-beheerder om de juiste URL voor uw omgeving te controleren.

   2. Bewerk het bestand *OnPremisesExchangeConnectorServiceConfiguration.xml*. Het bestand bevindt zich standaard in *%ProgramData%\Microsoft\Windows intune Exchange connector* op de computer waarop de Exchange-connector wordt uitgevoerd. Open het bestand in een tekst editor en wijzig vervolgens de volgende regel zodat de EWS-URL voor uw omgeving wordt weer gegeven: `<ExchangeWebServiceURL>https://<YourExchangeHOST>/EWS/Exchange.asmx</ExchangeWebServiceURL>`

3. Sla het bestand op en start de computer opnieuw op of start de Microsoft Intune Exchange Connector-service opnieuw.

>[!NOTE]
> In deze configuratie stopt de intune Exchange connector met automatische detectie en maakt rechtstreeks verbinding met de EWS-URL.

## <a name="next-steps"></a>Volgende stappen

Voor hulp bij specifieke fouten kunt u proberen [veelvoorkomende fouten voor de intune Exchange connector op te lossen](troubleshoot-exchange-connector-common-errors.md).

Om ondersteuning te krijgen of om hulp te krijgen van de intune-Community:

- Zie [ondersteuning verkrijgen](../fundamentals/get-support.md) voor het gebruik van de intune-console om het probleem op te lossen of om een ondersteunings aanvraag te openen bij micro soft.
- Plaats uw probleem in de [Microsoft intune forums](https://social.technet.microsoft.com/Forums/home?forum=microsoftintuneprod).