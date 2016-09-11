---
title: Instellingen voor nalevingsbeleid voor iOS-apparaten | Microsoft Intune
description: 
keywords: 
author: karthikaraman
manager: angrobe
ms.date: 07/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4a59d24f-ed58-49b1-b874-b2d4aea3ec76
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 6b6a5e2435a3cdffeaf27b0045dee9b8263cdc7a
ms.openlocfilehash: 1e2dc1e94870bb53143bee62ccc9696a28285987


---


# Instellingen voor nalevingsbeleid voor iOS-apparaten in Microsoft Intune

De beleidsinstellingen die in dit onderwerp worden beschreven, zijn van toepassing op apparaten met iOS 6 en hoger.

Als u op zoek bent naar informatie over andere platforms, selecteert u een van de volgende opties:
> [!div class="op_single_selector"]
- [Instellingen voor nalevingsbeleid voor Android-apparaten](android-compliance-policy-settings-in-microsoft-intune.md)
- [Instellingen voor nalevingsbeleid voor Windows-apparaten](windows-compliance-policy-settings-in-microsoft-intune.md)

## Systeembeveiligingsinstellingen
### Wachtwoord
- **Een wachtwoord vereisen voor het ontgrendelen van mobiele apparaten:** stel deze optie in op **Ja** als u gebruikers wilt verplichten een wachtwoord in te voeren om toegang te krijgen tot hun apparaat. iOS-apparaten die gebruikmaken van een wachtwoord, zijn versleuteld.

- **Eenvoudige wachtwoorden toestaan:** stel deze optie in op **Ja** zodat gebruikers eenvoudige wachtwoorden kunnen maken, zoals **1234** of **1111**.

-  **Minimale wachtwoordlengte**: hiermee geeft u het minimale aantal cijfers of tekens aan waaruit het wachtwoord van de gebruiker moet bestaan.
- **Vereist wachtwoordtype:** geef aan of gebruikers een **alfanumeriek** of een **numeriek** wachtwoord moeten maken.

- **Minimum aantal tekensets:** als u **Vereist wachtwoordtype** instelt op **Alfanumeriek**, gebruikt u deze instelling om het minimum aantal tekensets op te geven waaruit het wachtwoord moet bestaan. De vier tekensets zijn:
  -   Kleine letters
  -   Hoofdletters
  -   Symbolen
  -   Getallen

  Hoe hoger de waarde is die u instelt, hoe complexer de gebruikers hun wachtwoorden moeten maken.

  Voor iOS-apparaten verwijst deze instelling naar het aantal speciale tekens (bijvoorbeeld **!**, **#**, **&amp;**) dat in het wachtwoord moet worden opgenomen.
- **Minuten inactief voordat wachtwoord is vereist:** hiermee geeft u aan na hoeveel niet-actieve tijd gebruikers hun wachtwoord opnieuw moeten invoeren.

- **Wachtwoord verloopt (in dagen):** selecteer het aantal dagen waarna het wachtwoord van gebruikers verloopt en ze een nieuw wachtwoord moeten maken.

- **Wachtwoordgeschiedenis onthouden:** gebruik deze instelling in combinatie met **Wachtwoorden niet opnieuw gebruiken** om te voorkomen dat gebruikers eerder gebruikte wachtwoorden opnieuw gebruiken.

- **Wachtwoorden niet opnieuw gebruiken:** als **Wachtwoordgeschiedenis onthouden** is geselecteerd, geeft u het aantal eerder gebruikte wachtwoorden op dat niet opnieuw kan worden gebruikt.

- **Een wachtwoord vereisen wanneer het apparaat wordt geactiveerd vanuit een niet-actieve status:** deze instelling moet worden gebruikt samen met de instelling **Minuten van inactiviteit voordat het wachtwoord wordt vereist**. Eindgebruikers wordt gevraagd een wachtwoord op te geven om toegang te krijgen tot een apparaat dat langer inactief is geweest dan de tijd die is opgegeven bij de instelling **Minuten van inactiviteit voordat wachtwoord vereist is**.

### E-mailprofiel
- **E-mailaccount moet worden beheerd door Intune:** wanneer deze optie is ingesteld op **Ja**, moet de niet-compatibele e-mail worden gebruikt die is geïmplementeerd op het apparaat. Het apparaat wordt in de volgende situaties beschouwd als niet compatibel:
  - Het e-mailprofiel moet ook worden geïmplementeerd in dezelfde gebruikersgroep als de doelgroep van het nalevingsbeleid, anders worden de apparaten van de gebruiker aangemerkt als niet-compatibel.
  - Het apparaat wordt gerapporteerd als niet-compatibel als de gebruiker al een e-mailaccount op het apparaat heeft ingesteld dat overeenkomt met een Intune-e-mailprofiel dat op het apparaat is geïmplementeerd. Intune kan het door de gebruiker ingerichte profiel niet overschrijven en kan het daarom niet beheren. De gebruiker moet, om voor compatibiliteit te zorgen, de bestaande e-mailinstellingen verwijderen. Daarna kan Intune het beheerde e-mailprofiel installeren.


- **Selecteer het e-mailprofiel dat moet worden beheerd door Intune:**
   als de instelling **E-mailaccount moet worden beheerd door Intune** is geselecteerd, kiest u **Selecteren** om het e-mailprofiel voor Intune op te geven. Het e-mailprofiel moet aanwezig zijn op het apparaat.

     Zie [De toegang tot zakelijke e-mail configureren met e-mailprofielen bij Microsoft Intune](configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune.md) voor meer informatie over e-mailprofielen.

## Instellingen voor de status van het apparaat

- **Jailbreaken of uitvoeren als rootgebruiker niet toegestaan:** als u deze instelling inschakelt, zijn apparaten waarop jailbreaking is uitgevoerd of die als rootgebruiker worden uitgevoerd niet compatibel.

##  Apparaateigenschappen
- **Minimale versie van het besturingssysteem die is vereist:** wanneer een apparaat niet voldoet aan de minimumvereisten met betrekking tot de versie van het besturingssysteem wordt dit apparaat gerapporteerd als niet-compatibel.
Er wordt een koppeling met informatie over het uitvoeren van een upgrade weergegeven. De eindgebruiker kan dan kiezen om een upgrade van zijn apparaat uit te voeren, waarna hij toegang tot bedrijfsbronnen kan krijgen.

- **Maximale versie van het besturingssysteem die is toegestaan:** wanneer een apparaat een versie van het besturingssysteem gebruikt die hoger is dan de versie die in de regel is opgegeven, wordt de toegang tot bedrijfsresources geblokkeerd en wordt de gebruiker gevraagd contact op te nemen met de IT-beheerder. Tot er een wijziging is doorgevoerd in de regel die de versie van het besturingssysteem toestaat, kan dit apparaat niet worden gebruikt om toegang tot bedrijfsbronnen te krijgen.



<!--HONumber=Aug16_HO5-->


