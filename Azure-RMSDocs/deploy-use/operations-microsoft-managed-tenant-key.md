---
# required metadata

title: Door Microsoft beheerde levenscyclusbewerkingen voor de tenantsleutel | Azure RMS
description:
keywords:
author: cabailey
manager: mbaldwin
ms.date: 06/03/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: 3c48cda6-e004-4bbd-adcf-589815c56c55

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: esaggese
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Door Microsoft beheerde levenscyclusbewerkingen voor de tenantsleutel

*Van toepassing op: Azure Rights Management, Office 365*

Als Microsoft uw tenantsleutel voor Azure Rights Management beheert (standaardinstelling), gebruikt u de volgende secties voor meer informatie over de levenscyclusbewerkingen die relevant zijn voor deze topologie.

## Uw tenantsleutel intrekken
Wanneer u zich afmeldt voor Azure RMS, wordt uw tenantsleutel niet meer gebruikt met Azure RMS en hoeft u verder geen actie te ondernemen.

## Uw tenantsleutel opnieuw instellen
Het opnieuw instellen van sleutels wordt ook key rolling genoemd. Stel uw tenantsleutel alleen opnieuw in wanneer dit echt nodig is. Oudere clients, zoals Office 2010, zijn niet ontworpen voor een correcte verwerking van sleutelwijzigingen. In dit scenario moet u Groepsbeleid of een vergelijkbaar mechanisme gebruiken om de RMS-status op computers te wissen. Er zijn echter enkele legitieme gebeurtenissen die u ertoe dwingen uw tenantsleutel opnieuw in te stellen. Bijvoorbeeld:

-   Uw bedrijf is opgesplitst in twee of meer bedrijven. Wanneer u uw tenantsleutel opnieuw instelt, heeft het nieuwe bedrijf geen toegang tot nieuwe inhoud die uw werknemers publiceren. Wanneer ze over een kopie van de oude tenantsleutel beschikken, hebben ze wel toegang tot de oude inhoud.

-   U denkt dat de oorspronkelijke tenantsleutel (de kopie in uw bezit) is aangetast.

U kunt uw tenant sleutel opnieuw instellen door contact op te nemen met de klantenondersteuning van Microsoft (CSS) en aan te tonen dat u de tenantbeheerder bent.

Wanneer u de tenantsleutel opnieuw instelt, wordt nieuwe inhoud beveiligd met de nieuwe tenantsleutel. Dit gebeurt op een gefaseerde manier, waardoor een deel van de nieuwe inhoud nog een bepaalde tijd met de oude tenantsleutel wordt beveiligd. Eerder beveiligde inhoud blijft beveiligd met uw oude tenantsleutel. Voor de ondersteuning van dit scenario wordt uw oude tenantsleutel door Azure RMS bewaard, zodat er licenties voor oude inhoud kunnen worden verleend.

## Een back-up van uw tenantsleutel maken en deze herstellen
Microsoft is verantwoordelijk voor de back-ups van uw tenantsleutel. U hoeft verder geen actie te ondernemen.

## Uw tenantsleutel exporteren
U kunt uw Azure RMS-configuratie en tenantsleutel exporteren door de instructies in deze drie stappen te volgen:

### Stap 1: export initiëren

-   Neem contact op met de klantenondersteuning van Microsoft (CSS) voor het openen van een **Azure Rights Management-ondersteuningsaanvraag met een aanvraag voor het exporteren van een Azure RMS-sleutels**. U moet bewijzen dat u een beheerder bent voor uw Azure RMS-tenant. Het bevestigen van dit proces duurt enkele dagen. Er gelden standaardkosten voor de ondersteuning. Het exporteren van uw tenant-sleutel is geen gratis ondersteuningsservice.

### Stap 2: wachten op verificatie

-   Microsoft verifieert of uw aanvraag om de RMS-tenantsleutel vrij te geven een legitieme aanvraag is. Dit proces kan maximaal drie weken duren.

### Stap 3: sleutelinstructies ontvangen van CSS

-   De klantenondersteuning van Microsoft (CSS) stuurt u een TPD-bestand dat is beveiligd met een wachtwoord. Dit bestand bevat uw versleutelde Azure RMS-configuratie en tenantsleutel. Hiervoor verstuurt CSS u (als de persoon die de export heeft gestart) eerst een e-mail met een hulpprogramma. U moet het hulpprogramma als volgt uitvoeren via een opdrachtprompt:

    ```
    AadrmTpd.exe -createkey
    ```
    Zodoende genereert u een RSA-sleutelpaar en worden de openbare en persoonlijke helften als bestanden opgeslagen in de huidige map. Bijvoorbeeld: **PublicKey-FA29D0FE-5049-4C8E-931B-96C6152B0441.txt** en **PrivateKey-FA29D0FE-5049-4C8E-931B-96C6152B0441.txt**.

    Beantwoord de e-mail van CSS en voeg het bestand bij dat begint met **PublicKey**. Vervolgens stuurt CSS een TPD-bestand als een XML-bestand dat is versleuteld met uw RSA-sleutel. Kopieer dit bestand naar dezelfde map van waaruit u het hulpprogramma AadrmTpd hebt uitgevoerd en voer het hulpprogramma opnieuw uit. Gebruik hierbij het bestand dat begint met **PrivateKey** en het bestand van CSS. Bijvoorbeeld:

    ```
    AadrmTpd.exe -key PrivateKey-FA29D0FE-5049-4C8E-931B-96C6152B0441.txt -target TPD-77172C7B-8E21-48B7-9854-7A4CEAC474D0.xml
    ```
    De uitvoer van deze opdracht bestaat ui twee bestanden: het ene bestand bevat het leesbare wachtwoord voor het TPD-bestand dat is beveiligd met een wachtwoord. Het andere bestand is het beveiligde TPD-bestand. Voor kruisverwijzingsdoeleinden moeten beide bestanden dezelfde GUID hebben als de openbare en persoonlijke sleutelbestanden van waaruit u de opdracht AadrmTpd.exe -createkey hebt uitgevoerd:

    -   Password-FA29D0FE-5049-4C8E-931B-96C6152B0441.txt

    -   ExportedTPD-FA29D0FE-5049-4C8E-931B-96C6152B0441.xml

    Maak een back-up van deze bestanden en sla ze veilig op om ervoor te zorgen dat u inhoud kunt blijven ontsleutelen die is beveiligd met deze tenantsleutel. Als u migreert naar AD RMS, kunt u het TPD-bestand (het bestand dat begint met **ExportedTDP**) bovendien importeren naar uw AD RMS-server.

### Stap 4: doorlopend: de sleutel van uw tenant te beveiligen

-   Nadat u de tenantsleutel hebt ontvangen, moet u deze veilige bewaren. Als iemand anders toegang tot de sleutel heeft, kan deze persoon alle documenten ontsleutelen met deze sleutel.

    Als u de tenantsleutel exporteert omdat u Azure RMS niet meer wilt gebruiken, kunt u uw RMS-tenant het beste deactiveren. Wacht hier niet mee totdat u de tenantsleutel hebt ontvangen, aangezien deze voorzorgsmaatregel de gevolgen minimaliseert bij ongeoorloofd gebruik van uw tenantsleutel. Zie [Decommissioning and Deactivating Azure Rights Management](decommission-deactivate.md) (Azure Rights Management uit bedrijf nemen en deactiveren) voor instructies.

## Reageren op een schending
Geen enkel beveiligingssysteem, hoe geavanceerd ook, is volledig zonder een proces voor een reactie op een schending. U tenantsleutel is mogelijk gekraakt of gestolen. Zelfs wanneer de sleutel goed is beveiligd, is het mogelijk dat er beveiligingsproblemen in de huidige generatie HSM-technologie of huidige sleutellengten en -algoritmen worden gevonden.

Microsoft beschikt over een speciaal team dat zich bezighoudt met beveiligingsincidenten in producten en services. Zodra er een geloofwaardige melding van een incident wordt gemaakt, onderzoekt dit team het bereik, de hoofdoorzaak en de oplossingen. Als dit incident van invloed is op uw assets, zal Microsoft uw Azure RMS-tenantbeheerders via een e-mail van op de hoogte stellen. Hiervoor wordt het e-mailadres gebruikt dat u hebt opgegeven toen u zich hebt aangemeld.

Welke actie u of Microsoft het beste kan ondernemen in het geval van een schending van de beveiliging, is afhankelijk van het bereik van de schending. Microsoft zal dit proces samen met u doorlopen. De volgende tabel bevat enkele veelvoorkomende situaties en de mogelijke reactie, hoewel de daadwerkelijke reactie afhankelijk is van alle informatie die tijdens het onderzoek aan het licht komt.

|Beschrijving van het incident|Waarschijnlijke reactie|
|------------------------|-------------------|
|Uw tenantsleutel is gelekt.|Uw tenantsleutel opnieuw instellen. Zie de sectie [Uw tenantsleutel opnieuw instellen](operations-tenant-key.md#re-key-your-tenant-key) in dit artikel.|
|Een niet-gemachtigde persoon of bepaalde schadelijke software beschikt over de rechten voor het gebruik van uw tenantsleutel, maar de sleutel zelf is niet gelekt.|In dit geval helpt het niet om de tenantsleutel opnieuw in te stellen en moet de hoofdoorzaak worden geanalyseerd. Als de niet-gemachtigde persoon zich toegang kon verschaffen door een proces- of softwarefout, moet die situatie worden opgelost.|
|Beveiligingsprobleem ontdekt in het RSA-algoritme of de sleutellengte of er bestaat rekenkundig gezien een kans op een beveiligingsaanval.|Microsoft moet de Azure RMS bijwerken voor de ondersteuning van nieuwe algoritmen en langere sleutellengten die hiertegen bestand zijn, en alle klanten instrueren om hun tenantsleutels te vernieuwen.|




<!--HONumber=Jun16_HO1-->


