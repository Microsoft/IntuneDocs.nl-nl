---
title: Inschrijving met het Apple School Manager Program voor iOS-apparaten instellen
titleSuffix: Intune on Azure
description: Meer informatie over het instellen van inschrijving met het Apple School Manager Program voor zakelijke iOS-apparaten met Intune.
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 06/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7981a9c0-168e-4c54-9afd-ac51e895042c
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 73556209c88759ffe0747d9927cbcbb49600e0c0
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/01/2017
---
# <a name="enable-ios-device-enrollment-with-apple-school-manager"></a>Inschrijving van iOS-apparaten inschakelen met Apple School Manager

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Met de informatie in dit onderwerp kunnen IT-beheerders iOS-apparaten inschrijven die zijn aangeschaft via het [Apple School Manager](https://school.apple.com/) (ASM) Program. Microsoft Intune kan een inschrijvingsprofiel draadloos implementeren waarmee ASM-apparaten voor beheer worden ingeschreven. De beheerder heeft de beheerde apparaten zelf niet te bedienen. Een ASM-profiel bevat beheerinstellingen die worden toegepast op apparaten tijdens de inschrijving, inclusief opties voor Configuratieassistent.

**Stappen voor ASM-inschrijving**
1. [Een ASM-token ophalen en apparaten toewijzen](#get-the-asm-token-and-assign-devices)
2. [Een inschrijvingsprofiel maken](#create-an-apple-enrollment-profile)
3. [Verbinding maken met Schoolgegevens synchroniseren](#connect-school-data-sync) (optioneel)
4. [ASM-beheerde apparaten synchroniseren](#sync-asm-managed-devices)
5. [ASM-profiel aan apparaten toewijzen](#assign-an-asm-profile-to-devices)
6. [Apparaten onder gebruikers distribueren](#distribute-devices-to-users)

>[!NOTE]
>ASM-inschrijving kan niet worden gebruikt met het Apple [Device Enrollment Program (DEP)](device-enrollment-program-enroll-ios.md) of het [apparaatinschrijvingsmanager](device-enrollment-manager-enroll.md)account van Intune.

## <a name="get-the-apple-asm-token-and-assign-devices"></a>Een ASM-token ophalen en apparaten toewijzen

Voordat u iOS-apparaten van het bedrijf met Apple School Manager (ASM) kunt inschrijven, moet u een ASM-token (.p7m) van Apple ontvangen. Intune kan met dit token informatie synchroniseren over apparaten die aan ASM deelnemen. Ook kan Intune hiermee inschrijvingsprofielen naar Apple uploaden en apparaten toewijzen aan die profielen. Als u zich in de Apple-portal bevindt, kunt u ook apparaatserienummers voor beheer toewijzen.

**Vereisten**
- [Apple MDM-pushcertificaat](apple-mdm-push-certificate-get.md)
- Aangemeld voor [Apple School Management](http://school.apple.com)

**Stap 1. Download een openbare-sleutelcertificaat van Intune dat is vereist voor het maken van een Apple ASM-token.**<br>
1. Kies in de Azure [Intune portal](https://aka.ms/intuneportal) achtereenvolgens **Apparaatinschrijving** en **Enrollment Program-token**.
2. Selecteer op de blade **Enrollment Program-token** **Uw openbare-sleutelcertificaat downloaden** en sla het bestand met de versleutelingssleutel (.pem) lokaal op. Het .pem-bestand wordt gebruikt om een vertrouwensrelatiecertificaat bij de portal Apple School Manager aan te vragen.

**Stap 2. Een ASM-token ophalen en apparaten toewijzen.**<br>
Selecteer **Een token via Apple School Manager maken** en meld u aan met de Apple id van uw bedrijf. Deze Apple ID kunt u gebruiken om uw ASM-token te verlengen.

   1.  Ga in de [portal Apple School Manager](https://school.apple.com) naar **MDM-servers** en selecteer vervolgens **MDM-server toevoegen** (rechtsboven).
   2.  Voer de **MDM-servernaam** in. De servernaam is voor eigen referentie en dient om de MDM-server te identificeren. Het is niet de naam of URL van de Microsoft Intune-server.
   3.  Selecteer **Bestand uploaden...**  in de Apple-portal, blader naar het .pem-bestand en selecteer **MDM-server opslaan** (rechtsonder).
   4.  Selecteer **Token ophalen** en download het servertokenbestand (.p7m) naar uw computer.
   5. Ga naar **Toewijzingen van apparaten** en **Apparaat kiezen** door handmatige invoer van de **serienummers** of het **volgordenummer**, of selecteer **CSV-bestand uploaden**.
   6.   Selecteer de actie **Toewijzen aan server** en selecteer de **MDM-server** die u hebt gemaakt.
   7. Geef een manier op voor **Apparaten kiezen**, voer de apparaatgegevens in en geef details op aan de hand van **serienummer** en **bestelnummer** of voer **CSV-bestand uploaden** uit.
   8. Selecteer **Toewijzen aan server**, kies de &lt;Servernaam&gt; die is opgegeven voor Microsoft Intune en kies vervolgens **OK**.

**Stap 3. Voer de Apple-id in die u hebt gebruikt om uw ASM-token te maken.**<br>Deze id moet worden gebruikt om uw Apple ASM-token te verlengen en wordt voor toekomstige referentie opgeslagen.

**Stap 4. Uw token zoeken en uploaden.**<br>
Ga naar het certificaatbestand (.p7m), kies **Openen** en kies vervolgens **Uploaden**. Intune synchroniseert automatisch de ASM-apparaten van Apple.

## <a name="create-an-apple-enrollment-profile"></a>Een Apple-inschrijvingsprofiel maken
Met een inschrijvingsprofiel voor apparaten worden de instellingen gedefinieerd die worden toegepast op een groep apparaten tijdens de inschrijving.

1. Kies in de Intune-portal achtereenvolgens**Apparaatinschrijving** en **Apple-inschrijving**.
2. Selecteer onder **Programma voor inschrijving** **Profielen voor het inschrijvingsprogramma**.
3. Selecteer **Maken** op de blade **Profielen voor het inschrijvingsprogramma**.
4. Voer op de blade **Inschrijvingsprofiel maken** een **naam** en een **beschrijving** in voor het profiel dat wordt weergegeven in de Intune-portal.
5. Geef voor **Gebruikersaffiniteit** aan of u andere apparaten met dit profiel wilt inschrijven met of zonder gebruikersaffiniteit.

 - **Inschrijven met gebruikersaffiniteit**: het apparaat moet aan een gebruiker worden gekoppeld tijdens de eerste configuratie en kan vervolgens toegang krijgen tot gegevens en e-mail van het bedrijf. Kies de gebruikersaffiniteit voor de ASM-beheerde apparaten waarop gebruikers zich met hun beheerde Apple-id aanmelden.

 >[!NOTE]
 >Multi-Factor Authentication (MFA) werkt niet tijdens inschrijving op ASM-apparaten met gebruikersaffiniteit. Na de inschrijving werkt MFA zoals verwacht op deze apparaten.

  Voor de modus Gedeelde iPad in Apple School Manager moeten gebruiker inschrijven met gebruikersaffiniteit.

 >[!NOTE]
    >Voor ASM met gebruikersaffiniteit moet [WS-Trust 1.3 gebruikersnaam/mixed-eindpunt](https://technet.microsoft.com/library/adfs2-help-endpoints) zijn ingeschakeld om een gebruikerstoken aan te vragen. [Meer informatie over WS-Trust 1.3](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint).

 - **Inschrijven zonder gebruikersaffiniteit**: het apparaat is niet gekoppeld aan een gebruiker. Gebruik deze relatie voor apparaten waarmee taken worden uitgevoerd zonder toegang tot lokale gebruikersgegevens. Apps waarvoor gebruikersaffiniteit is vereist, zoals de bedrijfsportal-app die wordt gebruikt voor het installeren van LOB-apps, zullen niet werken.

6. Selecteer **Instellingen voor apparaatbeheer**. Deze items worden ingesteld tijdens de activering en om deze te wijzigen, moeten de instellingen naar de fabrieksinstellingen worden hersteld. configureer de volgende profielinstellingen en selecteer vervolgens **Opslaan**:

    - **Onder supervisie**: een beheermodus waarmee standaard meer beheeropties worden ingeschakeld en de activeringsvergrendeling wordt uitgeschakeld. Als u het selectievakje leeg laat, hebt u beperkte beheermogelijkheden.

    - **Vergrendelde inschrijving** (vereist Onder supervisie als beheermodus): hiermee worden de iOS-instellingen uitgeschakeld waarmee het beheerprofiel kan worden verwijderd. Als u dit selectievakje leeg laat, kan het beheerprofiel uit het menu Instellingen worden verwijderd.

  - **Gedeelde iPad**: hiervoor zijn **Inschrijven met gebruikersaffiniteit** en de **supervisie**modus vereist.) Hiermee kunnen meerdere gebruikers aanmelden bij geregistreerde iPads met een beheerde Apple-id. Beheerde Apple-id's worden gemaakt in de portal Apple School Manager.

  >[!NOTE]
  >Als de modus **Gedeelde iPad** is ingeschakeld in een profiel en **Gebruikersaffiniteit** of de **supervisie**modus vervolgens wordt ingesteld op **Uit**, wordt de modus Gedeelde iPad uitgeschakeld voor het inschrijvingsprofiel.

  - **Maximum aantal gebruikers in cache**: (hiervoor moet **Gedeelde iPad** = **Ja** zijn ingesteld) hiermee wordt voor elke gebruiker een partitie gemaakt op het apparaat. De aanbevolen waarde is het aantal studenten dat het apparaat waarschijnlijk gaat gebruiken gedurende een bepaalde periode. Als bijvoorbeeld zes studenten het apparaat door de week gebruiken, stelt u dit aantal in op zes.  

    - **Koppelen toestaan**: hiermee wordt aangegeven of iOS-apparaten kunnen worden gesynchroniseerd met computers. Als u **Apple Configurator per certificaat toestaan** kiest, moet u een certificaat kiezen onder **Apple Configurator-certificaten**.

    - **Apple Configurator-certificaten**: als u **Apple Configurator per certificaat toestaan** onder **Koppelen toestaan** hebt gekozen, selecteert u het Apple Configurator-certificaat dat u wilt importeren.

7. Selecteer **Instellingen voor Configuratieassistent**, configureer de volgende profielinstellingen en selecteer vervolgens **Opslaan**:

    - **Naam van afdeling**: wordt weergegeven wanneer gebruikers tijdens de activering op **Over configuratie** tikken.

    - **Telefoonnummer van afdeling**: wordt weergegeven wanneer de gebruiker tijdens de activering de knop Hulp nodig? klikt.
    - **Configuratieassistentopties**: als deze instellingen waren uitgesloten in de configuratieassistentopties, kunnen ze naderhand worden ingesteld in het iOS-menu **Instellingen**.
        - **Wachtwoordcode**: hiermee wordt tijdens de activering gevraagd om de wachtwoordcode. Vraag altijd om een wachtwoordcode tenzij het apparaat wordt beveiligd of de toegang tot het apparaat op een andere manier wordt beheerd (bijvoorbeeld de kioskmodus waarmee op het apparaat maar één app kan worden uitgevoerd).
        - **Locatieservices**: als deze optie is ingeschakeld, wordt tijdens de activering door Configuratieassistent om de service gevraagd
        - **Herstellen**: als deze optie is ingeschakeld, wordt tijdens de activering door Configuratieassistent gevraagd om een iCloud-back-up
        - **Apple-id**: als deze optie is ingeschakeld, worden gebruikers door iOS gevraagd om een Apple-id wanneer Intune een app zonder een id probeert te installeren. Een Apple-id is vereist voor het downloaden van iOS-apps uit de App Store, waaronder de apps die zijn geïnstalleerd door Intune.
        - **Voorwaarden**: als deze optie is ingeschakeld, wordt tijdens de activering door Configuratieassistent gevraagd de voorwaarden van Apple te accepteren
        - **Touch ID**: als deze optie is ingeschakeld, wordt tijdens de activering door Configuratieassistent om deze service gevraagd
        - **Apple Pay**: als deze optie is ingeschakeld, wordt tijdens de activering door Configuratieassistent om deze service gevraagd
        - **In- en uitzoomen**: als deze optie is ingeschakeld, wordt tijdens de activering door Configuratieassistent om deze service gevraagd
        - **Siri**: als deze optie is ingeschakeld, wordt tijdens de activering door Configuratieassistent om deze service gevraagd
        - **Diagnostische gegevens**: als deze optie is ingeschakeld, wordt tijdens de activering door Configuratieassistent om deze service gevraagd.

8. Selecteer **Maken** op de blade **Inschrijvingsprofiel maken** om de profielinstellingen op te slaan.

## <a name="connect-school-data-sync"></a>Verbinding maken met Schoolgegevens synchroniseren
(Optioneel) ASM biedt ondersteuning voor het synchroniseren van gegevens van het lesrooster naar Azure Active Directory (AD) met Microsoft School Data Sync (SDS). Voltooi de volgende stappen voor het gebruik van SDS om schoolgegevens te synchroniseren.

1. Selecteer op de blade **Token voor het inschrijvingsprogramma** de blauwe informatiebanner of **Verbinding maken met SDS**.
2. Selecteer **Toestaan dat dit token wordt gebruikt door Microsoft School Data Sync** waardoor deze instelling wordt **Toegestaan**. Met deze instelling kan Intune verbinding maken met SDS in Office 365.
3. Als u een verbinding tussen ASM en Azure AD wilt maken, selecteert u **Microsoft School Data Sync instellen**. Meer informatie over [het instellen van Microsoft School Data Sync](https://support.office.com/article/Install-the-School-Data-Sync-Toolkit-8e27426c-8c46-416e-b0df-c29b5f3f62e1).
4. Klik op **OK** om de gegevens op te slaan en door te gaan.

## <a name="sync-asm-managed-devices"></a>ASM-beheerde apparaten synchroniseren
Nu Intune toestemming heeft om uw ASM-apparaten te beheren, kunt u Intune synchroniseren met de ASM-service om uw beheerde apparaten weer te geven in de Intune-portal.

1. Kies in de Intune-portal achtereenvolgens**Apparaatinschrijving** en **Apple-inschrijving**.
2. Selecteer **Synchroniseren** onder **Apparaten voor het inschrijvingsprogramma**. Op de voortgangsbalk wordt aangegeven hoe lang u moet wachten voordat u opnieuw synchronisatie kunt aanvragen.

    Om te voldoen aan de voorwaarden van Apple voor acceptabel ASM-verkeer, worden door Intune de volgende beperkingen opgelegd:
     -  Een volledige ASM-synchronisatie kan niet vaker dan eens in de zeven dagen worden uitgevoerd. Tijdens een volledige synchronisatie vernieuwt Intune elk serienummer dat door Apple aan Intune is toegewezen, of het serienummer eerder is gesynchroniseerd of niet. Als een volledige synchronisatie wordt uitgevoerd binnen zeven dagen na de vorige volledige synchronisatie, vernieuwt Intune alleen serienummers die nog niet aanwezig zijn in Intune.
     -  Een synchronisatieaanvraag krijgt 15 minuten de tijd om te worden uitgevoerd. Gedurende deze tijd of totdat de aanvraag is geslaagd, is de knop **Synchronisatie** uitgeschakeld.

>[!NOTE]
>U kunt ook ASM-serienummers toewijzen aan profielen op de blade **Apparaten voor het inschrijvingsprogramma**.

## <a name="assign-an-asm-profile-to-devices"></a>Een ASM-profiel aan apparaten toewijzen
ASM-apparaten die worden beheerd door Intune, moeten een ASM-profiel toegewezen krijgen voordat ze worden ingeschreven.

1. Kies **Apparaten inschrijven** > **Apple-inschrijving** in de Intune-portal en selecteer vervolgens **Profielen voor het inschrijvingsprogramma**.
2. Selecteer in de lijst met **Profielen voor het inschrijvingsprogramma** het profiel dat u wilt toewijzen aan apparaten en selecteer vervolgens **Toewijzingen van apparaten**
3. Selecteer **Toewijzen** en selecteer vervolgens de ASM-apparaten die u aan dit profiel wilt toewijzen. U kunt filteren om beschikbare ASM-apparaten weer te geven:
  - **niet-toegewezen**
  - **alle**
  - **&lt;ASM-profielnaam&gt;**
4. Selecteer de apparaten die u wilt beheren. Het selectievakje boven de kolom selecteert maximaal 1000 apparaten in de lijst. Klik op **Toewijzen**. Als u meer dan 1000 apparaten wilt registreren, herhaalt u de stappen voor toewijzing totdat alle ASM-profielen zijn toegewezen.

## <a name="distribute-devices-to-users"></a>Apparaten onder gebruikers distribueren

U kunt apparaten in bedrijfseigendom nu distribueren aan gebruikers. Wanneer een iOS ASM-apparaat wordt ingeschakeld, wordt het ingeschreven voor beheer door Intune. Als het apparaat is geactiveerd en gebruikt wordt, kan het profiel kan niet worden toegepast totdat het apparaat wordt ingesteld op de fabrieksinstellingen.

### <a name="how-users-install-and-use-the-company-portal-on-their-devices"></a>Hoe gebruikers de bedrijfsportal op hun apparaten installeren en gebruiken

Op apparaten die zijn geconfigureerd met gebruikersaffiniteit kan de bedrijfsportal-app worden geïnstalleerd en uitgevoerd om apps te downloaden en apparaten te beheren. Nadat gebruikers hun apparaten hebben ontvangen, moeten ze Configuratieassistent uitvoeren en de bedrijfsportal-app installeren.
