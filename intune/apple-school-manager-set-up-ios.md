---
title: Inschrijving met het Apple School Manager Program voor iOS-apparaten instellen
titleSuffix: Intune on Azure
description: Meer informatie over het instellen van inschrijving met het Apple School Manager Program voor zakelijke iOS-apparaten met Intune.
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 07/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7981a9c0-168e-4c54-9afd-ac51e895042c
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 7079a22afc04b5674eb8f12a2833961e86939a28
ms.sourcegitcommit: 79116d4c7f11bafc7c444fc9f5af80fa0b21224e
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/03/2017
---
# <a name="enable-ios-device-enrollment-with-apple-school-manager"></a>Inschrijving van iOS-apparaten inschakelen met Apple School Manager

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Met de informatie in dit onderwerp kunnen IT-beheerders iOS-apparaten inschrijven die zijn aangeschaft via het programma [Apple School Manager](https://school.apple.com/). Microsoft Intune kan een inschrijvingsprofiel draadloos implementeren waarmee Apple School Manager-apparaten voor beheer worden ingeschreven. De beheerder hoeft de beheerde apparaten nooit aan te raken. Het inschrijvingsprofiel bevat beheerinstellingen die tijdens de inschrijving op de apparaten worden toegepast, inclusief opties voor de configuratie-assistent.

**Inschrijvingsstappen voor Apple School Manager**
1. [Een Apple School Manager-token downloaden en apparaten toewijzen](#get-the-apple-token-and-assign-devices)
2. [Een registratieprofiel maken](#create-an-apple-enrollment-profile)
3. [Verbinding maken met Schoolgegevens synchroniseren](#connect-school-data-sync) (optioneel)
4. [Door Apple School Manager beheerde apparaten synchroniseren](#sync-managed-devices)
5. [Een Apple School Manager-profiel aan apparaten toewijzen](#assign-a-profile-to-devices)
6. [Apparaten onder gebruikers distribueren](#distribute-devices-to-users)

>[!NOTE]
>Inschrijving van Apple School Manager kan niet worden gebruikt met [DEP van Apple](device-enrollment-program-enroll-ios.md) of de [apparaatinschrijvingsmanager](device-enrollment-manager-enroll.md).

## <a name="get-the-apple-token-and-assign-devices"></a>De Apple-token downloaden en apparaten toewijzen

Voordat u iOS-bedrijfsapparaten met Apple School Manager kunt inschrijven, hebt u een token (.p7m) van Apple nodig. Intune kan met dit token informatie synchroniseren over apparaten die aan Apple School Manager deelnemen. Ook kan Intune hiermee inschrijvingsprofielen naar Apple uploaden en apparaten toewijzen aan die profielen. Als u zich in de Apple-portal bevindt, kunt u ook apparaatserienummers voor beheer toewijzen.

**Vereisten**
- [Apple MDM-pushcertificaat](apple-mdm-push-certificate-get.md)
- Aangemeld voor [Apple School Management](http://school.apple.com)

**Stap 1. Download een openbare-sleutelcertificaat van Intune dat is vereist voor het maken van een Apple-token.**<br>
1. Kies in de Azure [Intune portal](https://aka.ms/intuneportal) achtereenvolgens **Apparaatinschrijving** en **Enrollment Program-token**.
2. Selecteer op de blade **Enrollment Program-token** **Uw openbare-sleutelcertificaat downloaden** en sla het bestand met de versleutelingssleutel (.pem) lokaal op. Het .pem-bestand wordt gebruikt om een vertrouwensrelatiecertificaat bij de portal Apple School Manager aan te vragen.

**Stap 2. Download een token en wijs apparaten toe.**<br>
Selecteer **Een token via Apple School Manager maken** en meld u aan met de Apple id van uw bedrijf. U kunt dit Apple-id gebruiken om uw Apple School Manager-token te verlengen.

   1.  Ga in de [portal Apple School Manager](https://school.apple.com) naar **MDM-servers** en selecteer vervolgens **MDM-server toevoegen** (rechtsboven).
   2.  Voer de **MDM-servernaam** in. De servernaam is voor eigen referentie en dient om de MDM-server te identificeren. Het is niet de naam of URL van de Microsoft Intune-server.
   3.  Selecteer **Bestand uploaden...**  in de Apple-portal, blader naar het .pem-bestand en selecteer **MDM-server opslaan** (rechtsonder).
   4.  Selecteer **Token ophalen** en download het servertokenbestand (.p7m) naar uw computer.
   5. Ga naar **Toewijzingen van apparaten** en **Apparaat kiezen** door handmatige invoer van de **serienummers** of het **volgordenummer**, of selecteer **CSV-bestand uploaden**.
   6.   Selecteer de actie **Toewijzen aan server** en selecteer de **MDM-server** die u hebt gemaakt.
   7. Geef uw apparaat aan onder **Apparaten kiezen** en geef de apparaatgegevens op.
   8. Selecteer **Toewijzen aan server**, kies de &lt;Servernaam&gt; die is opgegeven voor Microsoft Intune en kies vervolgens **OK**.

**Stap 3. Voer de Apple-id in die u hebt gebruikt om uw Apple School Manager-token te maken.**<br>Deze id moet worden gebruikt om uw Apple School Manager-token te verlengen. De id wordt voor toekomstige referentie opgeslagen.

**Stap 4. Uw token zoeken en uploaden.**<br>
Ga naar het certificaatbestand (.p7m), kies **Openen** en kies vervolgens **Uploaden**. Intune synchroniseert automatisch de Apple School Manager-apparaten van Apple.

## <a name="create-an-apple-enrollment-profile"></a>Een Apple-inschrijvingsprofiel maken
Met een inschrijvingsprofiel voor apparaten worden de instellingen gedefinieerd die worden toegepast op een groep apparaten tijdens de inschrijving.

1. Kies in de Intune-portal achtereenvolgens**Apparaatinschrijving** en **Apple-inschrijving**.
2. Selecteer onder **Programma voor inschrijving** **Profielen voor het inschrijvingsprogramma**.
3. Selecteer **Maken** op de blade **Profielen voor het inschrijvingsprogramma**.
4. Voer op de blade **Inschrijvingsprofiel maken** een **naam** en een **beschrijving** in voor het profiel dat wordt weergegeven in de Intune-portal.
5. Geef voor **Gebruikersaffiniteit** aan of u andere apparaten met dit profiel wilt inschrijven met of zonder gebruikersaffiniteit.

 - **Inschrijven met gebruikersaffiniteit**: hiermee wordt het apparaat tijdens de installatie aan een gebruiker gelieerd.

 >[!NOTE]
 >Multi-Factor Authentication (MFA) werkt niet tijdens inschrijving op Apple School Manager-apparaten met gebruikersaffiniteit. Na de inschrijving werkt MFA zoals verwacht op deze apparaten.

  Voor de modus Gedeelde iPad in Apple School Manager moeten gebruikers worden ingeschreven zonder gebruikersaffiniteit.

 >[!NOTE]
    >Voor Apple School Manager met gebruikersaffiniteit moet [WS-Trust 1.3 gebruikersnaam/mixed-eindpunt](https://technet.microsoft.com/library/adfs2-help-endpoints) zijn ingeschakeld om een gebruikerstoken aan te vragen. [Meer informatie over WS-Trust 1.3](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint).

 - **Inschrijven zonder gebruikersaffiniteit**: het apparaat is niet gekoppeld aan een gebruiker. Gebruik deze relatie voor apparaten waarmee taken worden uitgevoerd zonder toegang tot lokale gebruikersgegevens. Apps waarvoor gebruikersaffiniteit is vereist, zoals de bedrijfsportal-app die wordt gebruikt voor het installeren van LOB-apps, werken niet.

6. Selecteer **Instellingen voor apparaatbeheer**. Deze items worden ingesteld tijdens de activering en om deze te wijzigen, moeten de instellingen naar de fabrieksinstellingen worden hersteld. configureer de volgende profielinstellingen en selecteer vervolgens **Opslaan**:

    - **Onder supervisie**: een beheermodus waarmee standaard meer beheeropties worden ingeschakeld en de activeringsvergrendeling wordt uitgeschakeld. Als u het selectievakje leeg laat, hebt u beperkte beheermogelijkheden.

    - **Vergrendelde inschrijving** (vereist Onder supervisie als beheermodus): hiermee worden de iOS-instellingen uitgeschakeld waarmee het beheerprofiel kan worden verwijderd. Als u dit selectievakje leeg laat, kan het beheerprofiel uit het menu Instellingen worden verwijderd.

  - **Gedeelde iPad**: (hiervoor zijn **Inschrijven zonder gebruikersaffiniteit** en de modus **Onder supervisie** vereist.) Hiermee kunnen meerdere gebruikers zich met een beheerde Apple-id aanmelden bij geregistreerde iPads. Beheerde Apple-id's worden gemaakt in de portal Apple School Manager.

  >[!NOTE]
  >Als **Gebruikersaffiniteit** is ingesteld op **Met gebruikersaffiniteit** of als de modus **Onder supervisie** is ingesteld op **Uit**, wordt de modus Gedeelde iPad uitgeschakeld voor het inschrijvingsprofiel.

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
(Optioneel) Apple School Manager biedt ondersteuning voor het synchroniseren van gegevens van het lesrooster met Azure Active Directory (AD) met Microsoft School Data Sync (SDS). Voltooi de volgende stappen voor het gebruik van SDS om schoolgegevens te synchroniseren.

1. Selecteer op de blade **Token voor het inschrijvingsprogramma** de blauwe informatiebanner of **Verbinding maken met SDS**.
2. Selecteer **Toestaan dat dit token wordt gebruikt door Microsoft School Data Sync** waardoor deze instelling wordt **Toegestaan**. Met deze instelling kan Intune verbinding maken met SDS in Office 365.
3. Als u een verbinding tussen Apple School Manager en Azure AD wilt maken, selecteert u **Microsoft School Data Sync instellen**. Meer informatie over [het instellen van Microsoft School Data Sync](https://support.office.com/article/Install-the-School-Data-Sync-Toolkit-8e27426c-8c46-416e-b0df-c29b5f3f62e1).
4. Klik op **OK** om de gegevens op te slaan en door te gaan.

## <a name="sync-managed-devices"></a>Beheerde apparaten synchroniseren
Nu Intune toestemming heeft om uw Apple School Manager-apparaten te beheren, kunt u Intune synchroniseren met de Apple-service om uw beheerde apparaten weer te geven in de Intune-portal.

1. Kies in de Intune-portal achtereenvolgens**Apparaatinschrijving** en **Apple-inschrijving**.
2. Selecteer **Synchroniseren** onder **Apparaten voor het inschrijvingsprogramma**. Op de voortgangsbalk wordt aangegeven hoe lang u moet wachten voordat u opnieuw synchronisatie kunt aanvragen.

    Om te voldoen aan de voorwaarden van Apple voor acceptabel verkeer, worden de volgende beperkingen opgelegd:
     -  Een volledige synchronisatie kan niet vaker dan eens in de zeven dagen worden uitgevoerd. Tijdens een volledige synchronisatie vernieuwt Intune elk serienummer dat door Apple aan Intune is toegewezen, of het serienummer eerder is gesynchroniseerd of niet. Als een volledige synchronisatie wordt uitgevoerd binnen zeven dagen na de vorige volledige synchronisatie, vernieuwt Intune alleen serienummers die nog niet aanwezig zijn in Intune.
     -  Een synchronisatieaanvraag krijgt 15 minuten de tijd om te worden uitgevoerd. Gedurende deze tijd of totdat de aanvraag is geslaagd, is de knop **Synchronisatie** uitgeschakeld.

>[!NOTE]
>U kunt ook Apple School Manager-serienummers toewijzen aan profielen vanaf de blade **Apparaten voor het inschrijvingsprogramma**.

## <a name="assign-a-profile-to-devices"></a>Een profiel aan apparaten toewijzen
Apple School Manager-apparaten die worden beheerd door Intune, moeten een profiel voor het inschrijvingsprogramma toegewezen krijgen voordat ze worden ingeschreven.

1. Kies **Apparaten inschrijven** > **Apple-inschrijving** in de Intune-portal en selecteer vervolgens **Profielen voor het inschrijvingsprogramma**.
2. Selecteer in de lijst met **Profielen voor het inschrijvingsprogramma** het profiel dat u wilt toewijzen aan apparaten en selecteer vervolgens **Toewijzingen van apparaten**
3. Selecteer **Toewijzen** en selecteer vervolgens de Apple School Manager-apparaten die u aan dit profiel wilt toewijzen. U kunt filteren om beschikbare apparaten weer te geven:
  - **niet-toegewezen**
  - **alle**
  - **&lt;Naam Apple School Manager-profiel&gt;**
4. Selecteer de apparaten die u wilt beheren. Het selectievakje boven de kolom selecteert maximaal 1000 apparaten in de lijst. Klik op **Toewijzen**. Als u meer dan 1000 apparaten wilt registreren, herhaalt u de stappen voor toewijzing totdat aan alle apparaten een inschrijvingsprofiel is toegewezen.

## <a name="distribute-devices-to-users"></a>Apparaten onder gebruikers distribueren

U kunt apparaten in bedrijfseigendom nu distribueren aan gebruikers. Wanneer een iOS Apple School Manager-apparaat wordt ingeschakeld, wordt het door Intune ingeschreven voor beheer. Als het apparaat is geactiveerd en gebruikt wordt, kan het profiel kan niet worden toegepast totdat het apparaat wordt ingesteld op de fabrieksinstellingen.

### <a name="how-users-install-and-use-the-company-portal-on-their-devices"></a>Hoe gebruikers de bedrijfsportal op hun apparaten installeren en gebruiken

Op apparaten die zijn geconfigureerd met gebruikersaffiniteit kan de bedrijfsportal-app worden geïnstalleerd en uitgevoerd om apps te downloaden en apparaten te beheren. Nadat gebruikers hun apparaten hebben ontvangen, moeten ze Configuratieassistent uitvoeren en de bedrijfsportal-app installeren.
