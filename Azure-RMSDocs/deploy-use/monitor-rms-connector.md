---
# required metadata

title: De Azure Rights Management-connector controleren | Azure RMS
description:
keywords:
author: cabailey
manager: mbaldwin
ms.date: 06/09/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: 8a1b3e54-f788-4f84-b9d7-5d5079e50b4e

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: esaggese
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# De Azure Rights Management-connector controleren

*Van toepassing op: Azure Rights Management, Windows Server 2012, Windows Server 2012 R2*

Nadat u de RMS-connector hebt geïnstalleerd en geconfigureerd, kunt u de volgende methoden en informatie gebruiken om de connector en het gebruik van Azure RMS door uw organisatie te controleren.

## Vermeldingen in Toepassingsgebeurtenislogboek

In RMS-connector wordt Toepassingsgebeurtenislogboek gebruikt om vermeldingen voor gegevens voor **Microsoft RMS-connector** vast te leggen. 

Zo geeft de informatiegebeurtenis met id 1000 aan dat de connectorservice is gestart, geeft de id 1002 aan dat een server verbinding heeft gemaakt met de RMS-connector en wordt de id 1004 gebruikt wanneer de lijst met geautoriseerde accounts (waarin in elk account wordt vermeld) wordt gedownload naar de connector. 

Als u de connector niet hebt geconfigureerd voor het gebruik van HTTPS, wordt een waarschuwing met de id 2002 weergegeven waarin wordt gemeld dat een client een onbeveiligde verbinding (HTTP) gebruikt.

Als de connector geen verbinding kan maken met Azure RMS, wordt waarschijnlijk fout 3001 weergegeven. Dit kan bijvoorbeeld het gevolg zijn van een DNS-probleem of een gebrek aan internettoegang voor een of meer servers met de RMS-connector. 

> [!TIP] Wanneer de servers met de RMS-connector geen verbinding kunnen maken met Azure RMS, wordt dit vaak veroorzaakt door configuraties van webproxy's.

Net als bij alle vermeldingen in het gebeurtenislogboek kunt u het bericht in detail analyseren voor meer informatie.

Nadat u de connector voor de eerste keer hebt geïmplementeerd, moet u naast de controle van het gebeurtenislogboek ook regelmatig controleren op waarschuwingen en fouten. Zo kan de connector in eerste instantie volgens verwachting werken, maar worden afhankelijke configuraties mogelijk gewijzigd door andere beheerders. Een andere beheerder kan bijvoorbeeld de serverconfiguratie van de webproxyserver wijzigen waardoor de servers met de RMS connector geen toegang meer hebben tot internet (fout 3001), of een beheerder verwijdert een computeraccount uit een groep die u machtigingen hebt gegeven om de connector te gebruiken (waarschuwing 2001).

## Prestatiemeteritems

Wanneer u de RMS-connector installeert, worden automatisch prestatiemeteritems voor **Microsoft Rights Management-connector** gemaakt die u kunnen helpen bij het controleren van de prestaties voor het gebruik van Azure RMS via de connector. 

Als u bijvoorbeeld regelmatig vertraging ondervindt bij het beveiligen van documenten of e-mails, of bij het openen van beveiligde documenten of e-mails, kunt u de prestatiemeteritems gebruiken om te bepalen of de vertraging wordt veroorzaakt door de verwerkingstijd van de connector, de verwerkingstijd van Azure RMS of door netwerkvertragingen. Als u wilt vaststellen waar de vertraging optreedt, zoekt u naar prestatiemeteritems met gemiddelden voor de ** verwerkingstijd van de connector**, de **reactietijd van de service** en de **reactietijd van de connector**. Bijvoorbeeld: **Licensing Successful Batched Request Average Connector Response Time** (Gemiddelde reactietijd van connector voor voltooide batchaanvragen voor licenties).

Als u onlangs nieuwe serveraccounts hebt toegevoegd waarvoor de connector wordt gebruikt, is het nuttig om het item **Time since last authorization policy update** (Tijd sinds de laatste update van het autorisatiebeleid) te controleren om na te gaan of de connector de lijst heeft gedownload nadat u deze hebt bijgewerkt of dat u nog wat langer moet wachten (tot vijftien minuten).

## RMS Analyzer

U kunt het hulpprogramma Rights Management Services Analyzer gebruiken om de status van de connector te controleren en eventuele configuratieproblemen te identificeren.

Als u dit hulpprogramma nog niet hebt gedownload, kunt u dit doen via het [Downloadcentrum](https://www.microsoft.com/en-us/download/details.aspx?id=46437). Vervolgens kunt u het hulpprogramma installeren op elke computer met internettoegang waarmee verbinding kan worden gemaakt met de RMS-connector. Voer het hulpprogramma uit en klik op de **welkomstpagina** op de optie **Azure RMS connector**.

Zie de **details** en **installatie-instructies** op de downloadpagina voor aanvullende informatie en instructies.

## Logboekregistratie

Met gebruiksregistratie kunt u identificeren wanneer e-mails en documenten worden beveiligd en verbruikt. Wanneer dit wordt gedaan met de RMS-connector, bevat het veld met de gebruikers-id in de logboeken de Service Principal Name die automatisch wordt gegenereerd wanneer u de RMS-connector installeert.

Zie [Logging and analyzing Azure Rights Management usage](log-analyze-usage.md) (Het gebruik van Azure Rights Management registreren in een logboek en analyseren) voor meer informatie.

Als u voor diagnosedoeleinden meer gedetailleerde logboekregistratie nodig hebt, kunt u [Debug View](http://go.microsoft.com/fwlink/?LinkID=309277) van Windows Sysinternals gebruiken en tracering voor de RMS-connector inschakelen door het Web.config-bestand voor de standaardsite in IIS aan te passen. U doet dit als volgt:

1. Zoek naar het Web.config-bestand bij **%programfiles%\Microsoft Rights Management connector\Web Service**.

2. Zoek naar de volgende regel:

        <trace enabled="false" requestLimit="10" pageOutput="false" traceMode="SortByTime" localOnly="true"/>

3. Vervang de regel door het volgende:

        <trace enabled="true" requestLimit="10" pageOutput="false" traceMode="SortByTime" localOnly="true"/>

4.  Activering de tracering door IIS te stoppen en te starten. 

5.  Nadat u de benodigde traceringen hebt vastgelegd, moet u de regel in stap 3 weer terugzetten en IIS nogmaals stoppen en starten.



<!--HONumber=Jun16_HO2-->


