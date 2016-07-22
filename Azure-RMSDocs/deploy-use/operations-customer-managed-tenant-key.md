---
title: Door de klant beheerde levenscyclusbewerkingen voor de tenantsleutel | Azure RMS
description: 
keywords: 
author: cabailey
manager: mbaldwin
ms.date: 04/28/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: c5b19c59-812d-420c-9c54-d9776309636c
ms.reviewer: esaggese
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 0f355da35dff62ecee111737eb1793ae286dc93e
ms.openlocfilehash: 496edca2e2323e17216858e2ab4844fdb0aa1fb0


---


# Door de klant beheerde levenscyclusbewerkingen voor de tenantsleutel

*Van toepassing op: Azure Rights Management, Office 365*

Als u de tenantsleutel voor Azure Rights Management zelf beheert (het Bring Your Own Key-scenario, ofwel BYOK), leest u de volgende gedeelten voor meer informatie over de levenscyclusbewerkingen die relevant zijn voor deze topologie.

## Uw tenantsleutel intrekken
Wanneer u zich afmeldt voor Azure RMS, wordt uw tenantsleutel niet meer gebruikt met Azure RMS en hoeft u verder geen actie te ondernemen.

## Uw tenantsleutel opnieuw instellen
Het opnieuw instellen van sleutels wordt ook key rolling genoemd. Stel uw tenantsleutel alleen opnieuw in wanneer dit echt nodig is. Oudere clients, zoals Office 2010, zijn niet ontworpen voor een correcte verwerking van sleutelwijzigingen. In dit scenario moet u Groepsbeleid of een vergelijkbaar mechanisme gebruiken om de RMS-status op computers te wissen. Er zijn echter enkele legitieme gebeurtenissen die u ertoe dwingen uw tenantsleutel opnieuw in te stellen. Bijvoorbeeld:

-   Uw bedrijf is opgesplitst in twee of meer bedrijven. Wanneer u uw tenantsleutel opnieuw instelt, heeft het nieuwe bedrijf geen toegang tot nieuwe inhoud die uw werknemers publiceren. Wanneer ze over een kopie van de oude tenantsleutel beschikken, hebben ze wel toegang tot de oude inhoud.

-   U denkt dat de oorspronkelijke tenantsleutel (de kopie in uw bezit) is aangetast.

Wanneer u de tenantsleutel opnieuw instelt, wordt nieuwe inhoud beveiligd met de nieuwe tenantsleutel. Dit gebeurt op een gefaseerde manier, waardoor een deel van de nieuwe inhoud nog een bepaalde tijd met de oude tenantsleutel wordt beveiligd. Eerder beveiligde inhoud blijft beveiligd met uw oude tenantsleutel. Voor de ondersteuning van dit scenario wordt uw oude tenantsleutel door Azure RMS bewaard, zodat er licenties voor oude inhoud kunnen worden verleend.

Als u de tenantsleutel opnieuw wilt instellen, maakt en genereert u persoonlijk een sleutel of doet u dit via internet. Volg hiervoor de stappen in het gedeelte [BYOK implementeren (Bring Your Own Key)](..\plan-design\plan-implement-tenant-key.md#implementing-your-azure-rights-management-tenant-key) van het onderwerp [Uw Azure Rights Management-tenantsleutel plannen en implementeren](..\plan-design\plan-implement-tenant-key.md).

## Een back-up van uw tenantsleutel maken en deze herstellen
U bent zelf verantwoordelijk voor het maken van back-ups van uw tenantsleutel. Als u de tenantsleutel hebt gegenereerd in een Thales HSM en u er een back-up van wilt maken, maakt u een back-up van het Tokenized sleutelbestand, het Word-bestand en de beheerderskaarten.

Als u uw sleutel hebt overgedragen door de procedures te volgen in het gedeelte [BYOK (Bring Your Own Key) implementeren](../plan-design/plan-implement-tenant-key.md#implementing-your-azure-rights-management-tenant-key) van het artikel [Uw Azure Rights Management-tenantsleutel plannen en implementeren](../plan-design/plan-implement-tenant-key.md), behoudt Azure RMS het Tokenized sleutelbestand om bescherming te bieden tegen fouten in Azure RMS-knooppunten. U dient dit echter niet te zien als volledige back-up. Als u bijvoorbeeld ooit een platte-tekstkopie nodig hebt van uw sleutel voor gebruik buiten een Thales HMS, kan Azure RMS deze niet voor u ophalen omdat er alleen een niet-herstelbare kopie beschikbaar is.

## Uw tenantsleutel exporteren
Als u BYOK gebruikt, kunt u uw tenantsleutel niet exporteren uit Azure RMS. De kopie in Azure RMS kan niet worden hersteld. Als u deze sleutel wilt verwijderen zodat deze niet meer kan worden gebruikt, neemt u contact op met de Microsoft-klantenondersteuning (CSS).

## Reageren op een schending
Geen enkel beveiligingssysteem, hoe geavanceerd ook, is volledig zonder een proces voor een reactie op een schending. U tenantsleutel is mogelijk gekraakt of gestolen. Zelfs wanneer de sleutel goed is beveiligd, is het mogelijk dat er beveiligingsproblemen in de huidige generatie HSM-technologie of huidige sleutellengten en -algoritmen worden gevonden.

Microsoft beschikt over een speciaal team dat zich bezighoudt met beveiligingsincidenten in producten en services. Zodra er een geloofwaardige melding van een incident wordt gemaakt, onderzoekt dit team het bereik, de hoofdoorzaak en de oplossingen. Als dit incident van invloed is op uw assets, zal Microsoft uw Azure RMS-tenantbeheerders via een e-mail van op de hoogte stellen. Hiervoor wordt het e-mailadres gebruikt dat u hebt opgegeven toen u zich hebt aangemeld.

Welke actie u of Microsoft het beste kan ondernemen in het geval van een schending van de beveiliging, is afhankelijk van het bereik van de schending. Microsoft zal dit proces samen met u doorlopen. De volgende tabel bevat enkele veelvoorkomende situaties en de mogelijke reactie, hoewel de daadwerkelijke reactie afhankelijk is van alle informatie die tijdens het onderzoek aan het licht komt.

|Beschrijving van het incident|Waarschijnlijke reactie|
|------------------------|-------------------|
|Uw tenantsleutel is gelekt.|Uw tenantsleutel opnieuw instellen. Zie [Uw tenantsleutel opnieuw instellen](#re-key-your-tenant-key).|
|Een niet-gemachtigde persoon of bepaalde schadelijke software beschikt over de rechten voor het gebruik van uw tenantsleutel, maar de sleutel zelf is niet gelekt.|In dit geval helpt het niet om de tenantsleutel opnieuw in te stellen en moet de hoofdoorzaak worden geanalyseerd. Als de niet-gemachtigde persoon zich toegang kon verschaffen door een proces- of softwarefout, moet die situatie worden opgelost.|
|Beveiligingslek gedetecteerd in HSM-technologie van de huidige generatie.|Microsoft moet de HSM’s bijwerken. Als er een reden bestaat om te geloven dat er door het lek sleutels zijn gelekt, instrueert Microsoft alle klanten om hun tenantsleutels te vernieuwen.|
|Beveiligingsprobleem ontdekt in het RSA-algoritme of de sleutellengte of er bestaat rekenkundig gezien een kans op een beveiligingsaanval.|Microsoft moet de Azure RMS bijwerken voor de ondersteuning van nieuwe algoritmen en langere sleutellengten die hiertegen bestand zijn, en alle klanten instrueren om hun tenantsleutels te vernieuwen.|





<!--HONumber=Jul16_HO3-->


