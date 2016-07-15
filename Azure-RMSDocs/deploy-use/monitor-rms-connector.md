---
title: De Azure Rights Management-connector controleren | Azure RMS
description: 
keywords: 
author: cabailey
manager: mbaldwin
ms.date: 07/08/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: 8a1b3e54-f788-4f84-b9d7-5d5079e50b4e
ms.reviewer: esaggese
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: f8e23e8bcbfb25092cb31f7af76d17239f3063a7
ms.openlocfilehash: 32c3c93d55bd82f45fa7a081e55ae7ebe8f5956f


---

# De Azure Rights Management-connector controleren

*Van toepassing op: Azure Rights Management, Windows Server 2012, Windows Server 2012 R2*

Nadat u de RMS-connector hebt geïnstalleerd en geconfigureerd, kunt u de volgende methoden en informatie gebruiken om de connector en het gebruik van Azure RMS door uw organisatie te controleren.

## Vermeldingen in Toepassingsgebeurtenislogboek

In RMS-connector wordt Toepassingsgebeurtenislogboek gebruikt om vermeldingen voor gegevens voor **Microsoft RMS-connector** vast te leggen. 

Zo geeft de informatiegebeurtenis met id 1000 aan dat de connectorservice is gestart, geeft de id 1002 aan dat een server verbinding heeft gemaakt met de RMS-connector en wordt de id 1004 gebruikt wanneer de lijst met geautoriseerde accounts (waarin in elk account wordt vermeld) wordt gedownload naar de connector. 

Als u de connector niet hebt geconfigureerd voor het gebruik van HTTPS, wordt een waarschuwing met de id 2002 weergegeven waarin wordt gemeld dat een client een onbeveiligde verbinding (HTTP) gebruikt.

Als de connector geen verbinding kan maken met Azure RMS, wordt waarschijnlijk fout 3001 weergegeven. Dit kan bijvoorbeeld het gevolg zijn van een DNS-probleem of een gebrek aan internettoegang voor een of meer servers met de RMS-connector. 

> [!TIP]
> Wanneer de servers met de RMS-connector geen verbinding kunnen maken met Azure RMS, wordt dit vaak veroorzaakt door configuraties van webproxy's.

Net als bij alle vermeldingen in het gebeurtenislogboek kunt u het bericht in detail analyseren voor meer informatie.

Nadat u de connector voor de eerste keer hebt geïmplementeerd, moet u naast de controle van het gebeurtenislogboek ook regelmatig controleren op waarschuwingen en fouten. Zo kan de connector in eerste instantie volgens verwachting werken, maar worden afhankelijke configuraties mogelijk gewijzigd door andere beheerders. Een andere beheerder kan bijvoorbeeld de serverconfiguratie van de webproxyserver wijzigen waardoor de servers met de RMS connector geen toegang meer hebben tot internet (fout 3001), of een beheerder verwijdert een computeraccount uit een groep die u machtigingen hebt gegeven om de connector te gebruiken (waarschuwing 2001).

### Gebeurtenislogboek-id's en beschrijvingen

In de volgende secties kunt u de mogelijke gebeurtenis-id's identificeren en de bijbehorende beschrijvingen en eventuele aanvullende informatie lezen.

-----

Informatie **1000**

**De webservice van de Microsoft RMS-connector is gestart.**

Deze gebeurtenis wordt geregistreerd wanneer de RMS-connector voor het eerst wordt gestart.

----

Informatie **1001**

**De webservice van de Microsoft RMS-connector is gestopt.**

Deze gebeurtenis wordt geregistreerd wanneer de RMS-connector wordt gestopt als gevolg van een normale bewerking. Een voorbeeld hiervan is wanneer IIS opnieuw wordt gestart of wanneer de computer wordt afgesloten. 

----

Informatie **1002**

**Toegang tot de Microsoft RMS-connector is toegestaan voor een gemachtigde server.**

Deze gebeurtenis wordt geregistreerd wanneer een account van een on-premises server eerst verbinding maakt met de RMS-connector nadat het account door de Azure RMS-beheerder is gemachtigd met behulp van het beheerprogramma van de RMS-connector. Het gebeurtenisbericht bevat de SID, de accountnaam en de naam van de computer die de verbinding maakt.

----

Informatie **1003**

**De verbinding van de hieronder vermelde client is gewijzigd van een niet-beveiligde (HTTP-) verbinding in een beveiligde (HTTPS-) verbinding.**

Deze gebeurtenis wordt geregistreerd wanneer de verbinding van de RMS-connector op een on-premises server wordt gewijzigd van HTTP (minder veilig) in HTTPS (veiliger). Het gebeurtenisbericht bevat de SID, de accountnaam en de naam van de computer die de verbinding maakt.

----

Informatie **1004**

**De lijst met gemachtigde accounts is bijgewerkt.**

Deze gebeurtenis wordt geregistreerd als de meest recente lijst met accounts (bestaande accounts en eventuele wijzigingen) die zijn gemachtigd om de RMS-connector te gebruiken, is gedownload door de RMS-connector. Deze lijst wordt elke vijftien minuten gedownload, ervan uitgaande dat de RMS-connector kan communiceren met Azure RMS.

----

Waarschuwing **2000**

**De principal van gebruiker in de HTTP-context ontbreekt of is ongeldig. Controleer of Anonieme verificatie op de website van de Microsoft RMS-connector is uitgeschakeld in IIS en alleen Windows-verificatie is ingeschakeld.**

Deze gebeurtenis wordt geregistreerd wanneer het account waarmee wordt geprobeerd verbinding met de RMS-connector te maken, niet uniek kan worden geïdentificeerd in de RMS-connector. Dit kan komen doordat anonieme verificatie voor IIS niet juist is geconfigureerd of doordat het account afkomstig is uit een niet-vertrouwd forest.

----

Waarschuwing **2001**

**Poging tot onbevoegde toegang tot Microsoft RMS-connector.**

Deze gebeurtenis wordt geregistreerd wanneer een account geen verbinding met de RMS-connector kan maken. Meestal komt dit doordat het account waarmee de verbinding wordt gemaakt, zich niet in de lijst met gemachtigde accounts bevindt die door de RMS-connector van Azure RMS wordt gedownload. Het kan bijvoorbeeld voorkomen dat de meest recente lijst nog niet is gedownload (dit gebeurt elke 15 minuten) of dat het account ontbreekt in de lijst. 

Een andere reden kan zijn dat u de RMS-connector op dezelfde server hebt geïnstalleerd als de server die is geconfigureerd voor gebruik van de connector. U hebt de RMS-connector bijvoorbeeld geïnstalleerd op een server waarop Exchange Server wordt uitgevoerd en u hebt een Exchange-account gemachtigd om de connector te gebruiken. Deze configuratie wordt niet ondersteund, omdat dit account niet correct kan worden geïdentificeerd met de RMS-connector wanneer deze verbinding probeert te maken.

Het gebeurtenisbericht bevat informatie over het account en de computer waarmee wordt geprobeerd verbinding met de RMS-connector te maken:

- Als het account waarmee wordt geprobeerd verbinding met de RMS-connector te maken een geldig account is, gebruikt u het beheerprogramma van de RMS-connector om het account aan de lijst met gemachtigde accounts toe te voegen. Zie [Een server toevoegen aan de lijst met toegestane servers](install-configure-rms-connector.md#add-a-server-to-the-list-of-allowed-servers) voor meer informatie over welke accounts moeten worden gemachtigd. 

- Als het account waarmee wordt geprobeerd verbinding te maken met de RMS-connector zich op dezelfde computer bevindt als de server van de RMS-connector, kunt u de connector op een afzonderlijke server installeren. Zie [Vereiste voor de RMS-connector]( deploy-rms-connector.md#prerequisites-for-the-rms-connector) voor meer informatie over de vereisten voor de connector.

----

Waarschuwing **2002**

**De verbinding van de hieronder vermelde client maakt gebruik van een niet-beveiligde (HTTP-) verbinding.**

Deze gebeurtenis wordt geregistreerd wanneer een on-premises server verbinding maakt met de RMS-connector, maar voor de verbinding gebruik wordt gemaakt van HTTP (minder veilig) in plaats van HTTPS (veiliger). Een gebeurtenis wordt per account geregistreerd in plaats per verbinding. Deze gebeurtenis wordt opnieuw geactiveerd als het account is overgeschakeld naar het gebruik van HTTPS, maar vervolgens wordt teruggezet naar HTTP.

Het gebeurtenisbericht bevat de SID van het account, de accountnaam en de naam van de computer die de verbinding met de RMS-connector maakt.

Zie [De RMS-connector configureren voor het gebruik van HTTPS](install-configure-rms-connector.md#configuring-the-rms-connector-to-use-https) voor meer informatie over het configureren van de RMS-connector voor HTTPS-verbindingen.

----

Waarschuwing **2003**

**De lijst met machtigingen is leeg. De service kan pas worden gebruikt als de lijst met gemachtigde gebruikers en groepen voor de connector is gevuld.**

Deze gebeurtenis wordt geregistreerd wanneer voor de RMS-connector geen lijst met gemachtigde accounts bestaat, waardoor on-premises servers geen verbinding met de connector kunnen maken. Met de RMS-connector wordt de lijst elke 15 minuten van Azure RMS gedownload. 

Als u de accounts wilt opgeven, gebruikt u het beheerprogramma voor de RMS-connector. Zie [Servers autoriseren voor het gebruik van de RMS-connector]( install-configure-rms-connector.md#authorizing-servers-to-use-the-rms-connector) voor meer informatie. 

----

Fout **3000**

**Er is een onverwerkte uitzondering opgetreden in Microsoft RMS-connector.**

Elke keer dat in de RMS-connector een onverwachte fout wordt aangetroffen, wordt deze gebeurtenis geregistreerd. De details van de fout worden in het gebeurtenisbericht weergegeven.

Een mogelijke oorzaak wordt aangeduid met de tekst **De aanvraag is mislukt. Een leeg antwoord werd ontvangen.** in het gebeurtenisbericht. Als u deze tekst ziet, treedt de fout mogelijk op omdat er met een netwerkapparaat SSL-inspectie wordt uitgevoerd op de pakketten die worden uitgewisseld tussen de on-premises servers en de server met de RMS-connector. Dit wordt niet ondersteund waardoor de communicatie mislukt en dit gebeurtenislogboekbericht wordt weergegeven.

----

Fout **3001**

**Er is een uitzondering opgetreden tijdens het downloaden van de autorisatiegegevens.**

Deze gebeurtenis wordt geregistreerd als de meest recente lijst met accounts die zijn gemachtigd voor het gebruik van de RMS-connector, niet kan worden gedownload met de RMS-connector. In het gebeurtenisbericht worden de details van de fout weergegeven.



----

## Prestatiemeteritems

Wanneer u de RMS-connector installeert, worden automatisch prestatiemeteritems voor **Microsoft Rights Management-connector** gemaakt die u kunnen helpen bij het controleren van de prestaties voor het gebruik van Azure RMS via de connector. 

Als u bijvoorbeeld regelmatig vertraging ondervindt bij het beveiligen van documenten of e-mails, of bij het openen van beveiligde documenten of e-mails, kunt u de prestatiemeteritems gebruiken om te bepalen of de vertraging wordt veroorzaakt door de verwerkingstijd van de connector, de verwerkingstijd van Azure RMS of door netwerkvertragingen. Als u wilt vaststellen waar de vertraging optreedt, zoekt u naar prestatiemeteritems met gemiddelden voor de ** verwerkingstijd van de connector**, de **reactietijd van de service** en de **reactietijd van de connector**. Bijvoorbeeld: **Licensing Successful Batched Request Average Connector Response Time** (Gemiddelde reactietijd van connector voor voltooide batchaanvragen voor licenties).

Als u onlangs nieuwe serveraccounts hebt toegevoegd waarvoor de connector wordt gebruikt, is het nuttig om het item **Time since last authorization policy update** (Tijd sinds de laatste update van het autorisatiebeleid) te controleren om na te gaan of de connector de lijst heeft gedownload nadat u deze hebt bijgewerkt of dat u nog wat langer moet wachten (tot vijftien minuten).

## RMS Analyzer

U kunt het hulpprogramma Rights Management Services Analyzer gebruiken om de status van de connector te controleren en eventuele configuratieproblemen te identificeren.

Als u dit hulpprogramma nog niet hebt gedownload, kunt u dit doen via het [Downloadcentrum](https://www.microsoft.com/en-us/download/details.aspx?id=46437). Vervolgens kunt u het hulpprogramma installeren op elke computer met internettoegang waarmee verbinding kan worden gemaakt met de RMS-connector. Voer het hulpprogramma uit en klik op de **welkomstpagina** op de optie **Azure RMS connector**.

Zie de **details** en **installatie-instructies** op de downloadpagina voor aanvullende informatie en instructies.

## Logboekregistratie

Met gebruiksregistratie kunt u identificeren wanneer e-mails en documenten worden beveiligd en verbruikt. Wanneer dit wordt gedaan met de RMS-connector, bevat het veld met de gebruikers-id in de logboeken de Service Principal Name **Aadrm_S-1-7-0** die automatisch wordt gegenereerd voor de RMS-connector.

Zie [Het gebruik van Azure Rights Management registreren in een logboek en analyseren](log-analyze-usage.md) voor meer informatie over logboekregistratie van het gebruik.

Als u voor diagnosedoeleinden meer gedetailleerde logboekregistratie nodig hebt, kunt u [Debug View](http://go.microsoft.com/fwlink/?LinkID=309277) van Windows Sysinternals gebruiken en tracering voor de RMS-connector inschakelen door het Web.config-bestand voor de standaardsite in IIS aan te passen. U doet dit als volgt:

1. Zoek naar het Web.config-bestand bij **%programfiles%\Microsoft Rights Management connector\Web Service**.

2. Zoek naar de volgende regel:

        <trace enabled="false" requestLimit="10" pageOutput="false" traceMode="SortByTime" localOnly="true"/>

3. Vervang de regel door het volgende:

        <trace enabled="true" requestLimit="10" pageOutput="false" traceMode="SortByTime" localOnly="true"/>

4.  Activering de tracering door IIS te stoppen en te starten. 

5.  Nadat u de benodigde traceringen hebt vastgelegd, moet u de regel in stap 3 weer terugzetten en IIS nogmaals stoppen en starten.




<!--HONumber=Jul16_HO2-->


