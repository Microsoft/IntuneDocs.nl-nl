---
title: iOS-apparaten inschrijven - Device Enrollment Program
titleSuffix: Intune Azure preview
description: 'Intune Azure Preview: in dit onderwerp leest u hoe u iOS-apparaten in bedrijfseigendom kunt inschrijven met het Device Enrollment Program.'
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 04/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7981a9c0-168e-4c54-9afd-ac51e895042c
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 5144b9e7c17a3323667b9ca68cb47829d69866c3
ms.contentlocale: nl-nl
ms.lasthandoff: 05/23/2017


---

# <a name="enroll-ios-devices-using-device-enrollment-program"></a>iOS-apparaten inschrijven met het Device Enrollment Program

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Met de informatie in dit onderwerp kunnen IT-beheerders iOS-apparaten van het bedrijf inschrijven, die zijn aangeschaft via het [Apple Device Enrollment Program (DEP)](https://deploy.apple.com). Microsoft Intune kan een inschrijvingsprofiel implementeren dat DEP draadloos inschrijft, waardoor de beheerder de beheerde apparaten niet eens hoeft te zien. Een DEP-profiel bevat de beheerinstellingen die u op apparaten wilt toepassen tijdens de inschrijving. Het inschrijvingspakket kan Configuratieassistent-opties voor het apparaat bevatten.

>[!NOTE]
>Inschrijving via DEP kan niet worden gebruikt met de [apparaatinschrijvingsmanager](device-enrollment-manager-enroll.md).
>Als gebruikers hun iOS-apparaten inschrijven via de bedrijfsportal-app en de serienummers van deze apparaten vervolgens worden geïmporteerd en toegewezen aan een DEP-profiel, wordt het apparaat uitgeschreven bij Intune.

**Stappen voor DEP-inschrijving**
1. [Een Apple DEP-token ophalen](#get-the-apple-dep-certificate)
2. [Een DEP-profiel maken](#create-an-apple-dep-profile)
3. [Apple DEP-serienummers toewijzen aan uw Intune-server](#assign-apple-dep-serial-numbers-to-your-mdm-server)
4. [Door DEP beheerde apparaten synchroniseren](#synchronize-dep-managed-devices)
5. [DEP-profiel op apparaten toewijzen](#assign-a-dep-profile-to-devices)
6. [Apparaten onder gebruikers distribueren](#distribute-devices-to-users)

## <a name="get-the-apple-dep-certificate"></a>Het Apple DEP-certificaat ophalen
Voordat u iOS-apparaten van het bedrijf met het Apple Device Enrollment Program (DEP) kunt inschrijven, moet u een DEP-certificaatbestand (.p7m) van Apple ontvangen. Intune kan met dit token informatie synchroniseren over apparaten binnen uw bedrijf die aan DEP deelnemen. Ook kan Intune hiermee inschrijvingsprofielen naar Apple uploaden en apparaten toewijzen aan die profielen.

Voor het beheren van iOS-apparaten in bedrijfseigendom met het DEP van Apple moet uw organisatie lid worden van DEP en apparaten verwerven via dat programma. Details van dit proces kunt u vinden op: https://deploy.apple.com. Voordelen van het programma zijn onder andere handsfree instellen, dus zonder dat elk apparaat via een USB-verbinding op een computer moet worden aangesloten.

> [!NOTE]
> Als uw Intune-tenant is gemigreerd van de klassieke Intune-console naar de Azure-portal en u een Apple DEP-token hebt verwijderd uit de Intune-beheerconsole tijdens de migratieperiode, is het DEP-token mogelijk hersteld in uw Intune-account. U kunt het DEP-token opnieuw verwijderen uit Azure Portal verwijderen.

**Stap 1. Download een openbare-sleutelcertificaat van Intune dat is vereist voor het maken van een Apple DEP-token.**<br>
1. Kies in Azure Portal **Meer services** > **Bewaking en beheer** > **Intune**. Kies op de blade Intune **Apparaatinschrijving** > **Apple DEP-token**.
2. Selecteer **Uw openbare-sleutelcertificaat downloaden** en sla het bestand met de versleutelingssleutel (.pem) lokaal op. Het .pem-bestand wordt gebruikt om een vertrouwensrelatiecertificaat bij de portal Apple Device Enrollment Program aan te vragen.

**Stap 2. Download een Apple DEP-token vanaf de betreffende Apple-website.**<br>
Selecteer [Een DEP-token via Apple Deployment Programs maken](https://deploy.apple.com) (https://deploy.apple.com) en meld u aan met de Apple ID van uw bedrijf. Deze Apple ID kunt u gebruiken om uw DEP-token te verlengen.

   1.  Ga in de [Apple Device Enrollment Program Portal](https://deploy.apple.com) naar **Programma apparaatinschrijving** &gt; **Servers beheren** en kies **MDM-server toevoegen**.
   2.  Voer de **MDM-servernaam** in en kies **Volgende**. De servernaam is voor eigen referentie en dient om de MDM-server te identificeren. Het is niet de naam of URL van de Microsoft Intune-server.
   3.  Het dialoogvenster **&lt;Servernaam&gt; toevoegen** wordt geopend. Kies **Bestand selecteren...** om het .pem-bestand te uploaden en kies **Volgende**.
   4.  In het dialoogvenster **&lt;Servernaam&gt; toevoegen** wordt een koppeling met **Uw servertoken** weergegeven. Download het servertokenbestand (.p7m) naar uw computer en kies **Gereed**.

**Stap 3. Voer de Apple ID in die u hebt gebruikt om uw Apple DEP-token te maken. Deze ID kan worden gebruikt om uw Apple DEP-token te verlengen.**

**Stap 4. Blader naar het Apple DEP-token dat u wilt uploaden. Intune voert automatisch een synchronisatie met uw DEP-account uit.**<br>
Ga naar het certificaatbestand (.pem), kies **Openen** en kies vervolgens **Uploaden**. Met het pushcertificaat kan Intune iOS-apparaten inschrijven en beheren door beleid naar geregistreerde mobiele apparaten te pushen.

## <a name="create-an-apple-dep-profile"></a>Een Apple DEP-profiel maken

Met een inschrijvingsprofiel voor apparaten worden de instellingen gedefinieerd die worden toegepast op een groep apparaten. De volgende stappen laten zien hoe u een apparaatinschrijvingsprofiel kunt maken voor iOS-apparaten die worden ingeschreven met DEP.

1. Kies in Azure Portal **Meer services** > **Bewaking en beheer** > **Intune**.
2. Kies **Apparaten inschrijven** op de blade Intune en kies vervolgens **Apple-inschrijving**.
3. Selecteer **DEP-profielen** onder **Instellingen van Apple Device Enrollment Program (DEP) beheren**.
4. Selecteer **Maken** op de blade **Apple DEP-profielen**.
5. Voer op de blade **Inschrijvingsprofiel maken** een naam en een beschrijving in voor het profiel.
6. Geef voor **Gebruikersaffiniteit** aan of u andere apparaten met dit profiel wilt inschrijven met of zonder gebruikersaffiniteit.

 - **Inschrijven met gebruikersaffiniteit**: het apparaat moet aan een gebruiker worden gekoppeld tijdens de eerste configuratie en kan vervolgens toegang krijgen tot gegevens en e-mail van het bedrijf. Kies gebruikersaffiniteit voor DEP-beheerde apparaten die eigendom zijn van gebruikers en waarvoor de bedrijfsportal moet worden gebruikt voor services als het installeren van apps. Houd er rekening mee dat Multi-Factor Authentication (MFA) niet werkt tijdens inschrijving op DEP-apparaten met gebruikersaffiniteit. Na de inschrijving werkt MFA zoals verwacht op deze apparaten. Nieuwe gebruikers die hun wachtwoord moeten wijzigen wanneer ze zich voor het eerst aanmelden, kunnen geen prompt krijgen tijdens de inschrijving voor DEP-apparaten. Daarnaast wordt gebruikers waarvan de wachtwoorden zijn verlopen niet gevraagd hun wachtwoord opnieuw in te stellen tijdens de DEP-inschrijving, en moeten deze het wachtwoord vanaf een ander apparaat opnieuw instellen.

    >[!NOTE]
    >Voor DEP met gebruikersaffiniteit moet [WS-Trust 1.3 gebruikersnaam/mixed-eindpunt](https://technet.microsoft.com/en-us/library/adfs2-help-endpoints) zijn ingeschakeld om een gebruikerstoken aan te vragen. [Meer informatie over WS-Trust 1.3](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint).

 - **Inschrijven zonder gebruikersaffiniteit**: het apparaat is niet gekoppeld aan een gebruiker. Gebruik deze relatie voor apparaten waarmee taken worden uitgevoerd zonder toegang tot lokale gebruikersgegevens. Apps waarvoor een gebruikersrelatie is vereist, zoals de bedrijfsportal-app die wordt gebruikt voor het installeren van LOB-apps, zullen niet werken.

7. Selecteer **Instellingen voor Apparaatbeheer**, configureer de volgende profielinstellingen en selecteer vervolgens **Opslaan**:

    - **Onder supervisie**: een beheermodus waarmee standaard meer beheeropties worden ingeschakeld en de activeringsvergrendeling wordt uitgeschakeld. Als u het selectievakje leeg laat, hebt u beperkte beheermogelijkheden.

    - **Vergrendelde inschrijving** (vereist Onder supervisie als beheermodus): hiermee worden de iOS-instellingen uitgeschakeld waarmee het beheerprofiel kan worden verwijderd. Als u dit selectievakje leeg laat, kan het beheerprofiel uit het menu Instellingen worden verwijderd. Dit item wordt ingesteld tijdens de activering en kan niet worden gewijzigd zonder het apparaat op de fabrieksinstellingen terug te zetten.

    - **Koppelen toestaan**: hiermee wordt aangegeven of iOS-apparaten kunnen worden gesynchroniseerd met computers. Als u **Apple Configurator per certificaat toestaan** kiest, moet u een certificaat kiezen onder **Apple Configurator-certificaten**.

    - **Apple Configurator-certificaten**: als u **Apple Configurator per certificaat toestaan** onder **Koppelen toestaan** hebt gekozen, selecteert u het Apple Configurator-certificaat dat u wilt importeren.

8. Selecteer **Instellingen voor Configuratieassistent**, configureer de volgende profielinstellingen en selecteer vervolgens **Opslaan**:

    - **Naam van afdeling**: wordt weergegeven wanneer gebruikers tijdens de activering op **Over configuratie** tikken.

    - **Telefoonnummer van afdeling**: wordt weergegeven wanneer de gebruiker tijdens de activering de knop Hulp nodig? klikt.
    - **Configuratieassistentopties**: deze instellingen zijn optioneel en kunnen naderhand worden geconfigureerd in het iOS-menu **Instellingen**.
        - **Wachtwoordcode**: hiermee wordt tijdens de activering gevraagd om de wachtwoordcode. Vraag altijd om een wachtwoordcode tenzij het apparaat wordt beveiligd of de toegang tot het apparaat op een andere manier wordt beheerd (bijvoorbeeld de kioskmodus waarmee op het apparaat maar één app kan worden uitgevoerd).
        - **Locatieservices**: als deze optie is ingeschakeld, wordt tijdens de activering door Configuratieassistent om de service gevraagd
        - **Herstellen**: als deze optie is ingeschakeld, wordt tijdens de activering door Configuratieassistent gevraagd om een iCloud-back-up
        - **Apple ID**: als deze optie is ingeschakeld, worden gebruikers door iOS gevraagd om een Apple ID wanneer Intune een app zonder een id probeert te installeren. Een Apple ID is vereist voor het downloaden van iOS-apps uit de App Store, waaronder de apps die zijn geïnstalleerd door Intune.
        - **Voorwaarden**: als deze optie is ingeschakeld, wordt tijdens de activering door Configuratieassistent gevraagd de voorwaarden van Apple te accepteren
        - **Touch ID**: als deze optie is ingeschakeld, wordt tijdens de activering door Configuratieassistent om deze service gevraagd
        - **Apple Pay**: als deze optie is ingeschakeld, wordt tijdens de activering door Configuratieassistent om deze service gevraagd
        - **In- en uitzoomen**: als deze optie is ingeschakeld, wordt tijdens de activering door Configuratieassistent om deze service gevraagd
        - **Siri**: als deze optie is ingeschakeld, wordt tijdens de activering door Configuratieassistent om deze service gevraagd
        - **Diagnostische gegevens**: als deze optie is ingeschakeld, wordt tijdens de activering door Configuratieassistent om deze service gevraagd.

9. Selecteer **Maken** op de blade **Inschrijvingsprofiel maken** om de profielinstellingen op te slaan.

## <a name="assign-apple-dep-serial-numbers-to-your-mdm-server"></a>Apple DEP-serienummers toewijzen aan uw MDM-server
Serienummers van apparaten moeten worden toegewezen aan uw Intune MDM-server in de Apple DEP-webportal, zodat Intune deze apparaten kan beheren.

1. Ga naar de [Device Enrollment Program-portal](https://deploy.apple.com) (https://deploy.apple.com) en meld u aan met de Apple-id van uw bedrijf.

2. Ga naar **Implementatieprogramma** &gt; **Programma apparaatinschrijving** &gt; **Apparaten beheren**.

3. Geef een manier op voor **Apparaten kiezen**, voer de apparaatgegevens in en geef details op aan de hand van **serienummer** en **bestelnummer** of voer **CSV-bestand uploaden** uit.

4. Selecteer **Toewijzen aan server**, kies de &lt;Servernaam&gt; die is opgegeven voor Microsoft Intune en kies vervolgens **OK**.

## <a name="synchronize-dep-managed-devices"></a>Door DEP beheerde apparaten synchroniseren
Nu Intune toestemming heeft om uw DEP-apparaten te beheren, kunt u Intune synchroniseren met de DEP-service om uw beheerde apparaten weer te geven in de Intune-portal.

1. Kies in Azure Portal **Meer services** > **Bewaking en beheer** > **Intune**.

2. Kies **Apparaten inschrijven** op de blade Intune van Azure Portal en kies vervolgens **Apple-inschrijving**.

3. Selecteer **DEP-serienummers** onder **Instellingen van Apple Device Enrollment Program (DEP) beheren**.

4. Selecteer **Synchroniseren** op de blade **Apple DEP-serienummers**.

5. Selecteer **Synchronisatie aanvragen** op de blade **Synchroniseren**. Op de voortgangsbalk wordt aangegeven hoe lang u moet wachten voordat u opnieuw synchronisatie kunt aanvragen.

    Om te voldoen aan de voorwaarden van Apple voor acceptabel DEP-verkeer, worden door Intune de volgende beperkingen opgelegd:
     -    Een volledige DEP-synchronisatie kan niet vaker dan eens in de zeven dagen worden uitgevoerd. Tijdens een volledige synchronisatie vernieuwt Intune elk serienummer dat door Apple aan Intune is toegewezen, of het serienummer eerder is gesynchroniseerd of niet. Als een volledige synchronisatie wordt uitgevoerd binnen zeven dagen na de vorige volledige synchronisatie, vernieuwt Intune alleen serienummers die nog niet aanwezig zijn in Intune.
     -    Een synchronisatieaanvraag krijgt 10 minuten de tijd om te worden uitgevoerd. Gedurende deze tijd of totdat de aanvraag is geslaagd, is de knop **Synchronisatie** uitgeschakeld.

>[!NOTE]
>U kunt ook DEP-serienummers aan profielen toewijzen via de blade **Apple DEP-serienummers**.

## <a name="assign-a-dep-profile-to-devices"></a>DEP-profiel op apparaten toewijzen
DEP-apparaten die worden beheerd door Intune, moeten een DEP-profiel toegewezen krijgen voordat ze worden ingeschreven.

1. Kies in Azure Portal **Meer services** > **Bewaking en beheer** > **Intune**.

2. Kies **Apparaten inschrijven** > **Apple-inschrijving** op de blade Intune van Azure Portal en kies vervolgens **DEP-profielen**.

3. Selecteer in de lijst met **Apple DEP-inschrijvingsprofielen** het profiel dat u wilt toewijzen aan apparaten en selecteer vervolgens **Toewijzingen van apparaten**

4. Selecteer **Toewijzen** en selecteer vervolgens de DEP-apparaten die u aan dit profiel wilt toewijzen. U kunt filteren om beschikbare DEP-apparaten weer te geven:
  - **niet-toegewezen**
  - **alle**
  - **&lt;DEP-profielnaam&gt;**

  ![Schermopname van de knop Toewijzen voor het toewijzen van een DEP-profiel in de Intune-portal](media/dep-profile-assignment.png)

5. Selecteer de apparaten die u wilt beheren. Met het selectievakje boven de kolom selecteert u tot 1000 apparaten in de lijst. Klik vervolgens op **Toewijzen**. Als u meer dan 1000 apparaten wilt registreren, herhaalt u de stappen voor toewijzing totdat alle DEP-profielen zijn toegewezen.

## <a name="distribute-devices-to-users"></a>Apparaten onder gebruikers distribueren

U kunt apparaten in bedrijfseigendom nu distribueren aan gebruikers. Wanneer een iOS DEP-apparaat wordt ingeschakeld, wordt dit ingeschreven voor beheer door Intune. Als het apparaat is geactiveerd en gebruikt wordt, kan het profiel kan niet worden toegepast totdat het apparaat wordt ingesteld op de fabrieksinstellingen.

Zie [Eindgebruikers instructies geven over Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/how-to-educate-your-end-users-about-microsoft-intune). U kunt uw eindgebruikers ook omleiden naar [Uw iOS- of macOS-apparaat gebruiken met Intune](https://docs.microsoft.com/intune/deploy-use/how-to-educate-your-end-users-about-microsoft-intune) 

### <a name="how-users-install-and-use-the-company-portal-on-their-devices"></a>Hoe gebruikers de bedrijfsportal op hun apparaten installeren en gebruiken

Op apparaten die zijn geconfigureerd met gebruikersaffiniteit kan de bedrijfsportal-app worden geïnstalleerd en uitgevoerd om apps te downloaden en apparaten te beheren. Nadat gebruikers hun apparaten hebben ontvangen, moeten zij de onderstaande extra stappen uitvoeren om Configuratieassistent te voltooien en de bedrijfsportal-app te installeren.

