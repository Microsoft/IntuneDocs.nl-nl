---
title: Uw eigen tenantsleutel persoonlijk genereren en overdragen | Azure RMS
description: 
keywords: 
author: cabailey
manager: mbaldwin
ms.date: 04/28/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: 3281e45e-cf69-4dc5-946b-3029851d3152
ms.reviewer: esaggese
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 0f355da35dff62ecee111737eb1793ae286dc93e
ms.openlocfilehash: 1acc66e9a73b100268ed722391a0a87651c64abc


---

# Uw eigen tenantsleutel persoonlijk genereren en overdragen

*Van toepassing op: Azure Rights Management, Office 365*


Gebruik de volgende procedures als u hebt besloten om [uw eigen tenantsleutel te beheren](plan-implement-tenant-key.md#choose-your-tenant-key-topology-managed-by-microsoft-the-default-or-managed-by-you-byok-) en u deze niet via internet wilt overdragen, maar dit in plaats daarvan persoonlijk wilt doen.

## Uw tenantsleutel genereren
Voer de volgende drie stappen uit om uw eigen tenantsleutel te genereren:

-   [Stap 1: bereid een werkstation voor met Thales HSM](#step-1-prepare-a-workstation-with-thales-hsm)

-   [Stap 2: maak een beveiligingswereld](#step-2-create-a-security-world)

-   [Stap 3: maak een nieuwe sleutel](#step-3-create-a-new-key)

### Stap 1: bereid een werkstation voor met Thales HSM
Installeer de nCipher-ondersteuningssoftware (Thales) op een Windows-computer. Koppel een Thales HSM aan die computer. Zorg ervoor dat de Thales-hulpprogramma's zich binnen uw pad bevinden. Zie voor meer informatie de handleiding inbegrepen bij de Thales HSM of ga naar de Thales-website voor Azure RMS op [http://www.thales-esecurity.com/msrms/cloud](http://www.thales-esecurity.com/msrms/cloud).

### Stap 2: Maak een beveiligingswereld
Start een opdrachtprompt en voer het nieuwe-wereld-programma van Thales uit.

```
new-world.exe --initialize --cipher-suite=DLf1024s160mRijndael --module=1 --acs-quorum=2/3
```
Dit programma maakt een **Beveiligingswereld**-bestand op %NFAST_KMDATA%\local\world, wat overeenkomt met de map C:\ProgramData\nCipher\Key Management Data\local. U kunt andere waarden gebruiken voor het quorum, maar in ons voorbeeld wordt u gevraagd drie lege kaarten en pincodes voor elk adres in te voeren. Vervolgens hebt u met elke combinatie van twee kaarten volledige toegang tot de beveiligingswereld.  Deze kaarten worden de **Beheerderskaartenset** voor de nieuwe beveiligingswereld.

Ga als volgt verder:

1.  Installeer de Thales CNG-provider zoals beschreven in de Thales-documentatie en configureer deze voor gebruik van de nieuwe beveiligingswereld.

2.  Maak een back-up van het wereldbestand. Beveilig en bescherm het wereldbestand, de beheerderskaarten en de bijbehorende pincodes en zorg ervoor dat niemand toegang heeft tot meer dan één kaart.

U kunt nu een nieuwe sleutel maken die uw RMS-tenantsleutel wordt.

### Stap 3: maak een nieuwe sleutel
Genereer een CNG-sleutel met de Thales-programma’s **generatekey** en **cngimport**.

Voer de volgende opdracht uit om de sleutel te genereren:

```
generatekey --generate simple type=RSA size=2048 protect=module ident=contosokey plainname=contosokey nvram=no pubexp=
```
Volg de volgende instructies om deze opdracht uit te voeren:

-   De parameter **protect** moet worden ingesteld op de waarde **module**, zoals weergegeven. Hiermee maakt u een modulair beveiligde sleutel. De BYOK-toolset biedt geen ondersteuning voor met OCS beveiligde sleutels.

-   We raden 2048 aan als sleutelgrootte, maar ondersteunen ook 1024-bits RSA-sleutels voor bestaande AD RMS-klanten die zulke sleutels hebben en migreren naar Azure RMS.

-   Vervang de waarde van *contosokey* voor de **ident** en **plainname** door een willekeurige tekenreekswaarde. Om administratieve overhead te minimaliseren en de kans op fouten te verkleinen, raden we u aan voor beide dezelfde waarde te gebruiken en altijd kleine letters te hanteren.

-   De pubexp is leeg (standaard) in dit voorbeeld, maar u kunt specifieke waarden opgeven. Zie de Thales-documentatie voor meer informatie.

Voer daarna de volgende opdracht uit om de sleutel in CNG te importeren:

```
cngimport --import –M --key=contosokey --appname=simple contosokey
```
Volg de volgende instructies om deze opdracht uit te voeren:

-   Vervang *contosokey* door dezelfde waarde die u in stap 1 hebt opgegeven.

-   Gebruik de optie **-M**, zodat de sleutel geschikt is voor dit scenario. Zonder deze optie wordt de resulterende sleutel een gebruikersspecifieke sleutel voor de huidige gebruiker.

Met deze opdracht maakt u een Tokenized sleutelbestand in uw map %NFAST_KMDATA%\local met een naam die begint met **key_caping_`_`**, gevolgd door een SID. Bijvoorbeeld: **key_caping_machine--801c1a878c925fd9df4d62ba001b94701c039e2fb**. Dit bestand bevat een versleutelde sleutel.

Maak van deze Tokenized sleutel een back-up op een veilige locatie.

> [!IMPORTANT]
> Wanneer u later uw sleutel overdraagt naar Azure RMS, beschikt Microsoft over een niet-herstelbare kopie van de sleutel. Dit betekent dat niemand uw sleutel uit de HSM's van Microsoft kan ophalen. Hierdoor behoudt u de exclusieve controle over uw tenantsleutel. Het wordt daarom zeer belangrijk dat u een veilige back-up maakt van uw sleutel en beveiligingswereld. Neem contact op met Thales voor richtlijnen en best practices om een back-up van uw sleutel te maken.

U bent nu klaar om uw tenantsleutel over te dragen naar Azure RMS.

## Uw tenantsleutel overdragen naar Azure RMS
Nadat u uw eigen sleutel hebt gegenereerd, moet u deze overdragen naar Azure RMS voordat u de sleutel kunt gebruiken. Voor het hoogste beveiligingsniveau verloopt deze overdracht via een handmatig proces, waarvoor u naar de vestiging van Microsoft in Redmond, (Washington) in de Verenigde Staten moet vliegen. Voer de volgende drie stappen uit om dit proces te voltooien:

-   [Stap 1: breng uw sleutel naar Microsoft](#step-1-bring-your-key-to-microsoft)

-   [Stap 2: draag uw sleutel over aan de beveiligingswereld van Azure RMS](#step-2-transfer-your-key-to-the-azure-rms-security-world)

-   [Stap 3: afsluitende procedures](#step-3-closing-procedures)

### Stap 1: breng uw sleutel naar Microsoft

-   Neem contact op met de klantenondersteuning van Microsoft (CSS) om een afspraak voor de overdracht van een sleutel voor Azure RMS te maken. Breng het volgende mee naar Microsoft in Redmond:

    -   Een quorum van uw beheerkaarten. Als u de voorgaande instructies in [Stap 2: maak een beveiligingswereld](#step-2-create-a-security-world) hebt gevolgd, maakt het niet uit welke twee van de drie kaarten dit zijn.

    -   Medewerkers die gemachtigd zijn om uw beheerkaarten en pincodes te vervoeren, gewoonlijk twee personen (één voor elke kaart).

    -   Uw beveiligingswereldbestand (%NFAST_KMDATA%\local\world) op een USB-station.

    -   Uw Tokenized sleutelbestand op een USB-station.

### Stap 2: draag uw sleutel over aan de beveiligingswereld van Azure RMS

1.  Wanneer u aankomt bij Microsoft om uw sleutel over te dragen, gebeurt er het volgende:

    -   Microsoft biedt u een offline werkstation aan waaraan een Thales HSM is gekoppeld, waarop Thales-software is geïnstalleerd en waarop een Azure RMS-beveiligingswereldbestand is geladen in de map C:\Temp\Destination.

    -   Op dit werkstation kunt u uw beveiligingswereldbestand en Tokenized sleutelbestand vanaf uw USB-station laden in de map C:\Temp\Source.

    -   Azure RMS-operators dragen uw sleutel veilig over naar de Azure RMS-beveiligingswereld met behulp van het Thales-hulpprogramma.

    Dit proces verloopt ongeveer als volgt, waarbij de laatste parameter van key-xfer-im in dit voorbeeld wordt vervangen door de naam van uw Tokenized sleutelbestand:

    **C:\&gt; mk-reprogram.exe --owner c:\Temp\Destination add c:\Temp\Source**

    **C:\&gt; key-xfer-im.exe c:\Temp\Source c:\Temp\Destination --module c:\Temp\Source\key_caping_machine--801c1a878c925fd9df4d62ba001b94701c039e2fb**

2.  Mk-reprogram vraagt u en de Azure RMS-operators om hun respectieve beheerderskaarten en pincodes op te geven. Met deze opdrachten wordt een Tokenized sleutelbestand geplaatst in C:\Temp\Destination, dat uw met Azure RMS-beveiligingswereld beschermde sleutel bevat.

### Stap 3: afsluitende procedures

-   In uw aanwezigheid doen de Azure RMS-operators het volgende:

    -   Een hulpprogramma uitvoeren dat Microsoft heeft ontwikkeld in samenwerking met Thales en waarmee twee machtigingen worden verwijderd: de machtiging om de sleutel te herstellen en de machtiging om machtigingen te wijzigen. Nadat dit is gebeurd, wordt deze kopie van uw sleutel vergrendeld binnen de Azure RMS-beveiligingswereld. Thales HSM's staan niet toe dat Azure RMS-operators met hun beheerderskaarten de platte-tekst-kopie van de sleutel herstellen.

    -   Kopieer het resulterende sleutelbestand naar een USB-station om het later te uploaden naar de Azure RMS-service.

    -   Herstel de fabrieksinstellingen van de HSM en schoon het werkstation op.

U hebt nu alle instructies gevolgd die nodig zijn om uw eigen sleutel persoonlijk mee te brengen, en kunt voor de volgende stappen terugkeren naar uw organisatie. Hierbij gaat u een planning maken voor uw tenantsleutel en deze implementeren.

> [!div class="button"]
[Volgende stappen >>](plan-implement-tenant-key.md#next-steps)






<!--HONumber=Jun16_HO4-->


