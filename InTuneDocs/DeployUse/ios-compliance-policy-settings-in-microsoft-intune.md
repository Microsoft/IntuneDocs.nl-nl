---
# required metadata

title: Instellingen voor nalevingsbeleid voor iOS-apparaten | Microsoft Intune
description:
keywords:
author: karthikaraman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 4a59d24f-ed58-49b1-b874-b2d4aea3ec76

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Instellingen voor nalevingsbeleid voor iOS-apparaten in Microsoft Intune

De beleidsinstellingen die in dit onderwerp worden beschreven, zijn van toepassing op apparaten met iOS 6 en hoger.

Als u op zoek bent naar informatie over andere platforms, selecteert u een van de volgende opties:
> [!div class="op_single_selector"]
- [Instellingen voor nalevingsbeleid voor Android-apparaten](android-compliance-policy-settings-in-microsoft-intune.md)
- [Instellingen voor nalevingsbeleid voor Windows-apparaten](windows-compliance-policy-settings-in-microsoft-intune.md)

## Systeembeveiligingsinstellingen
### Wachtwoord
- **Wachtwoord vereisen voor het ontgrendelen van mobiele apparaten**: stel deze optie in op **Ja** om te vereisen dat gebruikers een wachtwoord invoeren om
  toegang te krijgen tot hun apparaat. iOS-apparaten die gebruikmaken van een wachtwoord, zijn versleuteld.

- **Eenvoudige wachtwoorden toestaan**: stel deze optie
   in op **Ja** om gebruikers toe te staan om eenvoudige wachtwoorden te maken,
   bijvoorbeeld '**1234**' of '**1111**'.

-  **Minimale wachtwoordlengte:**
  Geef het minimale aantal cijfers of tekens op dat
  het wachtwoord van de gebruiker moet bevatten.
- **Vereist wachtwoordtype:** geef op of gebruikers
een **alfanumeriek** of een **numeriek** wachtwoord moeten instellen.

- **Minimum aantal tekensets**: als u **Vereist wachtwoordtype** instelt op
**Alfanumeriek**, kunt u met deze instelling het minimumaantal
tekensets opgeven dat het wachtwoord moet bevatten. De vier tekensets zijn:
  -   Kleine letters
  -   Hoofdletters
  -   Symbolen
  -   Getallen

  Hoe hoger de waarde is die u instelt, hoe complexer gebruikers hun wachtwoorden moeten maken.

  Voor iOS-apparaten verwijst deze instelling naar het aantal speciale tekens (bijvoorbeeld **!**, **#**, **&amp;**) dat in het wachtwoord moet worden opgenomen.
- **Minuten inactief voordat wachtwoord is vereist:** hiermee geeft u aan na hoeveel niet-actieve tijd gebruikers hun wachtwoord opnieuw moeten invoeren.

- **Verlopen van wachtwoorden (dagen)**: selecteer het aantal dagen waarna het wachtwoord van gebruikers verloopt
en ze een nieuw wachtwoord moeten maken.

- **Wachtwoordgeschiedenis onthouden**: gebruik deze instelling in combinatie met **Wachtwoorden niet opnieuw gebruiken** om te voorkomen dat gebruikers
eerder gebruikte wachtwoorden opnieuw gebruiken.

- **Wachtwoorden niet opnieuw gebruiken**: als **Wachtwoordgeschiedenis onthouden** is geselecteerd, geeft u op
hoeveel eerder gebruikte wachtwoorden niet opnieuw mogen worden gebruikt.

- **Wachtwoord vereisen wanneer het apparaat wordt geactiveerd vanuit een niet-actieve status:**
Deze instelling moet worden gebruikt in combinatie met de instelling **Minuten inactief voordat wachtwoord is vereist**. Eindgebruikers wordt gevraagd een wachtwoord op te geven als ze toegang willen krijgen tot een apparaat dat inactief is geweest gedurende de periode die is opgegeven in de
instelling **Minuten inactief voordat wachtwoord vereist is**.

### E-mailprofiel
- **E-mailaccount moet worden beheerd door Intune:** wanneer deze optie is ingesteld op **Ja**, moet de niet-compatibele e-mail worden gebruikt die is geïmplementeerd op het apparaat. Het apparaat wordt in de volgende situaties beschouwd als niet compatibel:
  - Het e-mailprofiel moet ook worden geïmplementeerd in dezelfde gebruikersgroep als de doelgroep van het nalevingsbeleid, anders worden de apparaten van de gebruiker aangemerkt als niet-compatibel.
  - Het apparaat wordt gerapporteerd als niet-compatibel als de gebruiker al een e-mailaccount op het apparaat heeft ingesteld dat overeenkomt met een Intune-e-mailprofiel dat op het apparaat is geïmplementeerd. Intune kan het door de gebruiker ingerichte profiel niet overschrijven en
  kan het daarom niet beheren. Om compatibiliteit te garanderen, moet de gebruiker de
  bestaande e-mailinstellingen verwijderen. Daarna kan Intune het beheerde
  e-mailprofiel installeren.


- **Ga als volgt te werk om het e-mailprofiel te selecteren dat moet worden beheerd door Intune:**
     Als de instelling **E-mailaccount moet worden beheerd door Intune** is geselecteerd,
     kiest u **Selecteren** om het Intune-e-mailprofiel op te geven. Het e-mailprofiel moet aanwezig zijn op het apparaat.

     Zie voor meer informatie over e-mailprofielen [Toegang tot
     zakelijke e-mail via e-mailprofielen inschakelen met Microsoft Intune](configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune.md)..

## Instellingen voor de status van het apparaat

- **Het apparaat mag niet gekraakt of geroot zijn**: als u deze instelling inschakelt,
zijn opengebroken apparaten niet compatibel.

##  Apparaateigenschappen
- **Minimale versie van het besturingssysteem dat is vereist**: wanneer een apparaat niet voldoet aan de vereisten voor de
minimale besturingssysteemversie, wordt het apparaat gemarkeerd als niet-compatibel.
Er wordt een koppeling met informatie over het uitvoeren van een upgrade weergegeven. De eindgebruiker kan dan kiezen om een upgrade van zijn apparaat uit te voeren, waarna hij toegang tot bedrijfsbronnen kan krijgen.

- **Maximale versie van het besturingssysteem dat is toegestaan**: wanneer een apparaat gebruikmaakt van
een versie van het besturingssysteem die hoger is dan wat in de regel is bepaald, wordt de toegang tot bedrijfsbronnen geblokkeerd en wordt de gebruiker gevraagd contact op te nemen met zijn IT-beheerder. Tot er een wijziging is doorgevoerd in de regel die de versie van het besturingssysteem toestaat, kan dit apparaat niet worden gebruikt om toegang tot bedrijfsbronnen te krijgen.


<!--HONumber=May16_HO1-->


