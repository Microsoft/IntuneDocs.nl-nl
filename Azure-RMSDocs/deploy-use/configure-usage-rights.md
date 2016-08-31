---
title: Gebruiksrechten configureren voor Azure Rights Management | Azure RMS
description: Wanneer u met Azure Rights Management (Azure RMS) zonder sjabloon de beveiliging instelt voor bestanden of e-mail, moet u de gebruiksrechten zelf configureren. Als u daarnaast aangepaste sjablonen voor Azure RMS configureert, selecteert u de gebruiksrechten die vervolgens automatisch worden toegepast wanneer de sjabloon wordt geselecteerd door beheerders, gebruikers of geconfigureerde services.
author: cabailey
manager: mbaldwin
ms.date: 08/25/2016
ms.topic: article
ms.prod: 
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: 97ddde38-b91b-42a5-8eb4-3ce6ce15393d
ms.reviewer: esaggese
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: e1f1bef9ce87dcffb8d3da920f19198aa253e8e6
ms.openlocfilehash: bbfb00822a03609f5b81808e1e1c4cad8c02be0b


---

# Gebruiksrechten configureren voor Azure Rights Management

>*Van toepassing op: Azure Rights Management, Office 365*

Wanneer u met Azure Rights Management (Azure RMS) zonder sjabloon de beveiliging instelt voor bestanden of e-mail, moet u de gebruiksrechten zelf configureren. Als u daarnaast aangepaste sjablonen voor Azure RMS configureert, selecteert u de gebruiksrechten die vervolgens automatisch worden toegepast wanneer de sjabloon wordt geselecteerd door beheerders, gebruikers of geconfigureerde services. In de klassieke Azure-portal kunt u bijvoorbeeld rollen selecteren met een logische configuratie van gebruiksrechten, maar u kunt ook de afzonderlijke rechten configureren.

Gebruik dit artikel bij het configureren van de gewenste gebruiksrechten voor de toepassing dat en om te begrijpen hoe deze rechten door toepassingen worden geïnterpreteerd.

## Gebruiksrechten en beschrijvingen
De onderstaande tabel bevat een lijst en beschrijvingen van de gebruiksrechten die door Rights Management worden ondersteund en hoe ze worden gebruikt en geïnterpreteerd. Ze worden weergegeven met de **algemene naam**. Dit is de meer beschrijvende versie van de waarde van één woord in de code (de waarde van **Codering in beleid**) die doorgaans wordt gebruikt om de gebruiksrechten weer te geven of naar de gebruiksrechten te verwijzen. De **API-constante of -waarde** is de SDK-naam voor een MSIPC API-aanroep die wordt gebruikt wanneer u een toepassing met RMS-functionaliteit schrijft die controleert op gebruiksrechten of gebruiksrechten aan een beleid toegevoegd.


|Rechts|Beschrijving|Implementatie|
|-------------------------------|---------------------------|-----------------|
|Algemene naam: **Inhoud bewerken, Bewerken** <br /><br />Codering in beleid: **DOCEDIT**|Hiermee kan de gebruiker inhoud in de toepassing wijzigen, rangschikken, opmaken of filteren. Er worden geen rechten verleend om de bewerkte kopie op te slaan.|Aangepaste Office-rechten: als onderdeel van de opties **Wijzigen** en **Volledig beheer**. <br /><br />Naam in de klassieke Azure-portal: **Inhoud bewerken**<br /><br />Naam in AD RMS-sjablonen: **Bewerken** <br /><br />API-constante of -waarde: niet van toepassing.|
|Algemene naam: **Opslaan** <br /><br />Codering in beleid: **EDIT**|Hiermee kan de gebruiker het document op de huidige locatie opslaan.<br /><br />In Office-toepassingen kan de gebruiker met deze rechten het document wijzigen.|Aangepaste Office-rechten: als onderdeel van de opties **Wijzigen** en **Volledig beheer**. <br /><br />Naam in de klassieke Azure-portal: **Bestand opslaan**<br /><br />Naam in AD RMS-sjablonen: **Opslaan** <br /><br />API-constante of -waarde: `IPC_GENERIC_WRITE L"EDIT"`|
|Algemene naam: **Opmerking** <br /><br />Codering in beleid: **COMMENT**|Hiermee wordt de optie ingeschakeld voor het toevoegen van aantekeningen of opmerkingen aan de inhoud.<br /><br />Dit recht is beschikbaar in de SDK en als ad-hocbeleid in de module RMS-beveiliging voor Windows PowerShell, en is geïmplementeerd in sommige toepassingen van softwareleveranciers. Het recht wordt echter niet veel gebruikt en wordt momenteel niet ondersteund door Office-toepassingen.|Aangepaste Office-rechten: niet geïmplementeerd. <br /><br />Naam in de klassieke Azure-portal: niet geïmplementeerd.<br /><br />Naam in AD RMS-sjablonen: niet geïmplementeerd. <br /><br />API-constante of -waarde: `IPC_GENERIC_COMMENT L"COMMENT`|
|Algemene naam: **Opslaan als, Exporteren** <br /><br />Codering in beleid: **EXPORT**|Hiermee wordt de optie ingeschakeld voor het opslaan van de inhoud onder een andere bestandsnaam (Opslaan als). Het bestand kan zonder beveiliging worden opgeslagen als het om Office-documenten gaat.<br /><br />Met dit recht kan de gebruiker ook andere exportopties uitvoeren in programma’s, zoals **Verzenden naar OneNote**.|Aangepaste Office-rechten: als onderdeel van de opties **Wijzigen** en **Volledig beheer**. <br /><br />Naam in de klassieke Azure-portal: **Inhoud exporteren (Opslaan als)**<br /><br />Naam in AD RMS-sjablonen: **Exporteren (Opslaan als)** <br /><br />API-constante of -waarde: `IPC_GENERIC_EXPORT L"EXPORT"`|
|Algemene naam: **Doorsturen** <br /><br />Codering in beleid: **FORWARD**|Hiermee wordt de optie ingeschakeld voor het doorsturen van een e-mailbericht en het toevoegen van geadresseerden in de regels **Aan** en **CC**. Dit recht geldt niet voor documenten maar alleen voor e-mailberichten.<br /><br />Dit recht staat de doorstuurserver niet toe rechten te verlenen aan andere gebruikers als onderdeel van de doorstuuractie.|Aangepaste Office-rechten: geweigerd bij gebruik van het standaardbeleid **Niet doorsturen**.<br /><br />Naam in de klassieke Azure-portal: **Doorsturen**<br /><br />Naam in AD RMS-sjablonen: **Doorsturen** <br /><br />API-constante of -waarde: `IPC_EMAIL_FORWARD L"FORWARD"`|
|Algemene naam: **Volledig beheer** <br /><br />Codering in beleid: **OWNER**|Hiermee worden alle rechten voor het document verleend en kunnen alle beschikbare acties worden uitgevoerd.<br /><br />Omvat de mogelijkheid om beveiliging op te heffen en een document opnieuw te beveiligen.|Aangepaste Office-rechten: als de aangepaste optie **Volledig beheer**.<br /><br />Naam in de klassieke Azure-portal: **Volledig beheer**<br /><br />Naam in AD RMS-sjablonen: **Volledig beheer** <br /><br />API-constante of -waarde: `IPC_GENERIC_ALL L"OWNER"`|
|Algemene naam: **Afdrukken** <br /><br />Codering in beleid: **PRINT**|Hiermee wordt optie ingeschakeld voor het afdrukken van de inhoud.|Aangepaste Office-rechten: als de optie **Inhoud afdrukken** in aangepaste machtigingen. Geen instelling die per ontvanger wordt ingesteld.<br /><br />Naam in de klassieke Azure-portal: **Afdrukken**<br /><br />Naam in AD RMS-sjablonen: **Afdrukken** <br /><br />API-constante of -waarde: `IPC_GENERIC_PRINT L"PRINT"`|
|Algemene naam: **Beantwoorden** <br /><br />Codering in beleid: **REPLY**|Hiermee wordt de optie **Beantwoorden** ingeschakeld in een e-mailclient zonder dat wijzigingen in de regels **Aan** of **CC** mogen worden aangebracht.|Aangepaste Office-rechten: niet van toepassing.<br /><br />Naam in de klassieke Azure-portal: **Antwoorden**<br /><br />Naam in AD RMS-sjablonen: **Antwoorden** <br /><br />API-constante of -waarde: `IPC_EMAIL_REPLY`|
|Algemene naam: **Allen beantwoorden** <br /><br />Codering in beleid: **REPLYALL**|Hiermee wordt de optie **Allen beantwoorden** ingeschakeld in een e-mailclient, maar mag de gebruiker geen geadresseerden toevoegen in de regels **Aan** of **CC**.|Aangepaste Office-rechten: niet van toepassing.<br /><br />Naam in de klassieke Azure-portal: **Allen beantwoorden**<br /><br />Naam in AD RMS-sjablonen: **Allen beantwoorden** <br /><br />API-constante of -waarde: `IPC_EMAIL_REPLYALL L"REPLYALL"`|
|Algemene naam: **Weergeven, Openen, Lezen** <br /><br />Codering in beleid: **VIEW**|Hiermee kan de gebruiker het document openen en de inhoud bekijken.|Aangepaste Office-rechten: als onderdeel van het aangepaste beleid **Lezen**, optie **Weergave**.<br /><br />Naam in de klassieke Azure-portal: **Weergave**<br /><br />Naam in AD RMS-sjablonen: **Allen beantwoorden** <br /><br />API-constante of -waarde: `IPC_GENERIC_READ L"VIEW"`|
|Algemene naam: **Kopiëren** <br /><br />Codering in beleid: **EXTRACT**|Hiermee schakelt u opties in voor het kopiëren van gegevens (inclusief schermopnamen) uit het document naar hetzelfde of een ander document.<br /><br />In sommige toepassingen kunt u ook het hele document opslaan in een niet-beveiligde vorm.|Aangepaste Office-rechten: als de aangepaste beleidsoptie **Gebruikers met leestoegang toestaan om inhoud te kopiëren**.<br /><br />Naam in de klassieke Azure-portal: **Inhoud kopiëren en extraheren**<br /><br />Naam in AD RMS-sjablonen: **Extraheren** <br /><br />API-constante of -waarde: `IPC_GENERIC_EXTRACT L"EXTRACT"`|
|Algemene naam: **Macro's toestaan** <br /><br />Codering in beleid: **OBJMODEL**|Hiermee wordt de optie ingeschakeld voor het uitvoeren van macro's of andere toegang op programmeerniveau of externe toegang tot de inhoud in een document.|Aangepaste Office-rechten: als de aangepaste beleidsoptie **Toegang op programmeerniveau toestaan**. Geen instelling die per ontvanger wordt ingesteld.<br /><br />Naam in de klassieke Azure-portal: **Macro's toestaan**<br /><br />Naam in AD RMS-sjablonen: **Macro's toestaan** <br /><br />API-constante of -waarde: niet geïmplementeerd.|



## Rechten die beschikbaar zijn in machtigingsniveaus

In sommige toepassingen worden de gebruiksrechten gegroepeerd in machtigingsniveaus, om het selecteren van gebruiksrechten die doorgaans samen worden gebruikt te vereenvoudigen. Deze machtigingsniveaus bieden een samenvatting voor het complexiteitsniveau van gebruikers, zodat deze opties kunnen kiezen op basis van rollen.  Bijvoorbeeld, **Revisor** en **Medeauteur**. Hoewel deze opties vaak een samenvatting van de rechten weergeven voor gebruikers, bevatten ze mogelijk niet alle rechten die in de voorgaande tabel zijn opgenomen.

Gebruik de volgende tabel voor een lijst van deze machtigingsniveaus en een volledige lijst van de rechten die ze bevatten.

|Machtigingsniveau|Toepassingen|Opgenomen rechten (algemene naam)|
|---------------------|----------------|---------------------------------|
|Viewer|Klassieke Azure-portal<br /><br />Rights Management-toepassing voor delen voor Windows|Weergeven, Openen, Lezen; Antwoorden; Allen beantwoorden|
|Revisor|Klassieke Azure-portal<br /><br />Rights Management-toepassing voor delen voor Windows|Weergeven, Openen, Lezen; Opslaan; Inhoud bewerken, Bewerken; Antwoorden [[1]](#footnote-1); Allen beantwoorden[[1]](#footnote-1); Doorsturen[[1]](#footnote-1)|
|Medeauteur|Klassieke Azure-portal<br /><br />Rights Management-toepassing voor delen voor Windows|Weergeven, Openen, Lezen; Opslaan; Inhoud bewerken, Bewerken; Kopiëren; Rechten weergeven; Macro's toestaan; Opslaan als, Exporteren; Afdrukken; Antwoorden[[1]](#footnote-1); Allen beantwoorden [[1]](#footnote-1); Doorsturen [[1]](#footnote-1)|
|Mede-eigenaar|Klassieke Azure-portal<br /><br />Rights Management-toepassing voor delen voor Windows|Weergeven, Openen, Lezen; Opslaan; Inhoud bewerken, Bewerken; Kopiëren; Rechten weergeven; Macro's toestaan; Opslaan als, Exporteren; Afdrukken; Antwoorden[[1]](#footnote-1); Allen beantwoorden [[1]](#footnote-1); Doorsturen [[1]](#footnote-1); Volledige controle|

----

###### Voetnoot 1
Niet van toepassing voor Rights Management-toepassing voor delen voor Windows.

## Rechten die beschikbaar zijn in de standaardsjablonen
De volgende rechten zijn opgenomen in de standaardsjablonen:

|Weergavenaam|Opgenomen rechten (algemene naam)|
|----------------|---------------------------------|
|&lt;*Naam van de organisatie*&gt;*: alleen vertrouwelijke weergave*|Weergeven, Openen, Lezen|
|&lt;*Naam van organisatie*&gt;*: vertrouwelijk*|Weergeven, Openen, Lezen; Opslaan; Inhoud bewerken, Bewerken; Rechten weergeven; Macro's toestaan; Doorsturen; Antwoorden; Allen beantwoorden|

## De optie Niet doorsturen voor e-mailberichten

Exchange-clients en -services (bijvoorbeeld de Outlook-client, de Outlook Web Access-app en Exchange transportregels) hebben nog een eigen optie om gegevensrechten voor e-mails te beveiligen: **Niet doorsturen**. 

Hoewel deze optie wordt weergegeven aan gebruikers (en beheerders van Exchange) als een standaardsjabloon voor Rights Management die ze kunnen selecteren, is **Niet doorsturen** geen sjabloon. Hierdoor ziet u deze niet in de klassieke Azure-portal als u de sjablonen weergeeft en beheert voor Azure RMS. In plaats daarvan zijn de opties **Niet doorsturen** ingesteld als een set rechten die gebruikers dynamisch toepassen op hun e-mailontvangers.

Wanneer de optie **Niet doorsturen** wordt toegepast op een e-mailbericht, kunnen de ontvangers het niet doorsturen, afdrukken, kopiëren, de bijlagen niet opslaan en het bericht niet opslaan onder een andere naam. Als in de Outlook-client de knop Doorsturen bijvoorbeeld niet beschikbaar is, zijn de menuopties de **Opslaan als**, **Bijlage opslaan** en **Afdrukken** niet beschikbaar en kunt u geen ontvangers toevoegen of wijzigen in de vakken **Aan**, **Cc** of **Bcc**.

Er is een belangrijk verschil tussen het toepassen van de optie **Niet doorsturen** en het toepassen van een sjabloon waarbij het recht om een e-mail door te sturen niet wordt verleend: de optie **Niet doorsturen** maakt gebruik van een dynamische lijst met gemachtigde gebruikers die is gebaseerd op de door de gebruiker gekozen ontvangers van de oorspronkelijke e-mail, terwijl de rechten in de sjabloon een statische lijst met gemachtigde gebruikers hebben die de beheerder eerder heeft opgegeven. Wat is het verschil? Zie het volgende voorbeeld: 

Een gebruiker wil per e-mail aan specifieke personen van de marketingafdeling bepaalde informatie verzenden die niet mag worden gedeeld met iemand anders. Moet ze het e-mailbericht beveiligen met een sjabloon waarin alleen rechten (weergeven, beantwoorden en opslaan) worden verleend aan de marketingafdeling?  Of moet ze kiezen voor de optie **Niet doorsturen**? Beide opties leiden ertoe dat de ontvangers het e-mailbericht niet kunnen doorsturen. 

- Als ze de sjabloon heeft toegepast, kunnen de ontvangers de gegevens nog steeds delen met anderen van de marketingafdeling. Zo kan een ontvanger de Verkenner gebruiken om de e-mail te slepen en neer te zetten op een gedeelde locatie of een USB-station. Iedereen van de marketingafdeling (en de eigenaar van de e-mail) die toegang tot deze locatie heeft, kan de informatie in de e-mail weergeven.
 
- Als ze de optie **Niet doorsturen** heeft toegepast, kunnen de ontvangers de informatie niet delen met iemand anders van de marketingafdeling door het e-mailbericht naar een andere locatie verplaatsen. In dit scenario kunnen alleen de oorspronkelijke ontvangers (en de eigenaar van de e-mail) de informatie in de e-mail weergeven.

> [!NOTE] 
> Gebruik **Niet doorsturen** wanneer het belangrijk is dat alleen de ontvangers die de afzender kiest de informatie in het e-mailbericht kunnen zien. Gebruik een sjabloon voor e-mailberichten om de rechten te beperken tot een groep personen die de beheerder van tevoren heeft opgegeven, onafhankelijk van de ontvangers die de afzender heeft gekozen.




## Zie ook
[Aangepaste sjablonen configureren voor Azure Rights Management](configure-custom-templates.md)




<!--HONumber=Aug16_HO4-->


