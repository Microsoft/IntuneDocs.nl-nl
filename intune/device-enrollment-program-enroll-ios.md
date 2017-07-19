---
title: iOS-apparaten inschrijven - Device Enrollment Program
titleSuffix: Intune on Azure
description: Meer informatie over het registreren van iOS-apparaten in bedrijfseigendom met het Device Enrollment Program (DEP) van Apple.
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 06/30/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7981a9c0-168e-4c54-9afd-ac51e895042c
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f509f5332b2f8b5f6745816f8795a9a54c10ce2d
ms.sourcegitcommit: fd2e8f6f8761fdd65b49f6e4223c2d4a013dd6d9
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/03/2017
---
# <a name="set-up-ios-device-enrollment-with-device-enrollment-program"></a>Registratie van iOS-apparaten instellen met het Device Enrollment Program

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Met de informatie in dit onderwerp kunnen IT-beheerders iOS-apparaten registreren die zijn gekocht via het [Device Enrollment Program (DEP)](https://deploy.apple.com) van Apple. Microsoft Intune kan een inschrijvingsprofiel 'draadloos' implementeren op apparaten die zijn gekocht via DEP. De beheerder hoeft de beheerde apparaten nooit aan te raken. Een DEP-profiel bevat beheerinstellingen die worden toegepast op apparaten tijdens de inschrijving, inclusief opties voor de configuratie-assistent.

Voor het inschakelen van DEP-inschrijving moet u zowel de Intune-portal als de Apple DEP-portal gebruiken. Daarnaast hebt u een lijst met id's of inkoopordernummers van de DEP-apparaten nodig, zodat u de apparaten in de Apple-portal onder beheer van Intune kunt stellen.

>[!NOTE]
>Inschrijving via DEP kan niet worden gebruikt met de [apparaatinschrijvingsmanager](device-enrollment-manager-enroll.md).

**Stappen voor het inschakelen van inschrijvingsprogramma's van Apple**
1. [Een Apple DEP-token ophalen en apparaten toewijzen](#get-the-apple-dep-certificate)
2. [Een registratieprofiel maken](#create-anapple-enrollment-profile)
3. [Door DEP beheerde apparaten synchroniseren](#sync-dep-managed-devices)
4. [DEP-profiel op apparaten toewijzen](#assign-a-dep-profile-to-devices)
5. [Apparaten onder gebruikers distribueren](#distribute-devices-to-users)

## <a name="get-the-apple-dep-token"></a>Het Apple DEP-token ophalen

Voordat u iOS-apparaten van het bedrijf met het Apple Device Enrollment Program (DEP) kunt inschrijven, moet u een DEP-tokenbestand (.p7m) van Apple ontvangen. Intune kan met dit token informatie synchroniseren over apparaten binnen uw bedrijf die aan DEP deelnemen. Ook kan Intune hiermee inschrijvingsprofielen naar Apple uploaden en apparaten toewijzen aan die profielen.

> [!NOTE]
> Als uw Intune-tenant is gemigreerd van de klassieke Intune-console naar de Azure-portal en u een Apple DEP-token hebt verwijderd uit de Intune-beheerconsole tijdens de migratieperiode, is het DEP-token mogelijk hersteld in uw Intune-account. U kunt het DEP-token opnieuw verwijderen uit Azure Portal verwijderen.

**Vereisten**
- [Apple MDM-pushcertificaat](apple-mdm-push-certificate-get.md)
- Aangemeld voor het [Apple Device Enrollment Program](http://deploy.apple.com)

**Stap 1. Download een openbare-sleutelcertificaat van Intune dat is vereist voor het maken van een Apple DEP-token.**<br>
1. Kies in de Intune-portal achtereenvolgens **Apparaatinschrijving**, **Apple-inschrijving** en **Token voor het inschrijvingsprogramma**.
![Schermopname van het deelvenster Token voor het inschrijvingsprogramma in de werkruimte Apple-certificaten.](./media/enrollment-program-token-add.png)
2. Selecteer **Uw openbare-sleutelcertificaat downloaden** en sla het bestand met de versleutelingssleutel (.pem) lokaal op. Het .pem-bestand wordt gebruikt om een vertrouwensrelatiecertificaat bij de portal Apple Device Enrollment Program aan te vragen.
![Schermopname van het deelvenster Token voor het inschrijvingsprogramma in de werkruimte Apple-certificaten voor het downloaden van de openbare sleutel.](./media/enrollment-program-token-download.png)

**Stap 2. Maak en download een Apple DEP-token.**<br>
Selecteer **Een token via Apple Device Enrollment Program maken** om de Deployment Program-portal van Apple te openen en meld u aan met uw Apple ID. Deze Apple ID kunt u gebruiken om uw DEP-token te verlengen.
  ![Schermopname van het deelvenster Token voor het inschrijvingsprogramma in de werkruimte Apple-certificaten.](./media/enrollment-program-token-create.png)

  ![Schermopname van het deelvenster Token voor het inschrijvingsprogramma in de werkruimte Apple-certificaten voor het downloaden van de openbare sleutel.](./media/enrollment-program-token-sign.png)
   1.  Selecteer **Aan de slag** bij **Device Enrollment Program** in de [Deployment Programs-portal](https://deploy.apple.com) van Apple.
   ![Schermopname met een pijl naar Aan de slag voor het Device Enrollment Program.](./media/enrollment-program-token-started.png)
   2. Kies **MDM-server toevoegen** op de pagina **Servers beheren**.
   3. Voer de **MDM-servernaam** in en kies **Volgende**. De servernaam is voor eigen referentie en dient om de MDM-server te identificeren. Het is niet de naam of URL van de Microsoft Intune-server.

   ![Schermopname van het toevoegen van een MDM-servernaam voor DEP en een pijl naar Volgende.](./media/enrollment-program-token-add-server.png)
   4.  Het dialoogvenster **Voeg &lt;servernaam&gt;** wordt geopend, met de instructie dat u uw**** openbare sleutel moet uploaden. Kies **Bestand selecteren...** om het .pem-bestand te uploaden en kies **Volgende**.
   ![Schermopname van het kiezen van de knop voor het uploaden van de openbare sleutel en een pijl naar Volgende.](./media/enrollment-program-token-choose-file.png)
   4.  In het dialoogvenster **&lt;Servernaam&gt; toevoegen** wordt een koppeling met **Uw servertoken** weergegeven. Download het servertokenbestand (.p7m) naar uw computer en kies **Gereed**.
   ![Schermopname van het kiezen van de knop voor het uploaden van de openbare sleutel en een pijl naar Volgende.](./media/enrollment-program-token-your-token.png)
   5. Ga naar **Deployment Programs** &gt; **Device Enrollment Program** &gt; **Apparaten beheren**.
   6. Geef onder **Kies apparaten op** aan hoe apparaten worden geïdentificeerd:
    - **Serienummer**
    - **Ordernummer**
    - **CSV-bestand uploaden**

   ![Schermopname van het opgeven van apparaten op serienummer, het kiezen van een actie zoals toewijzen aan server en de naam van de server selecteren.](./media/enrollment-program-token-specify-serial.png)

   7. Selecteer bij **Kies actie** **Toewijzen aan server**, selecteer de**** servernaam die is opgegeven voor Microsoft Intune en kies vervolgens &lt;OK&gt;. De opgegeven apparaten worden voor beheer toegewezen aan de Intune-server en er verschijnt een melding dat de**** toewijzing is voltooid.

   Ga in de Apple-portal **Deployment Programs** &gt; **Device Enrollment Program** &gt; **Toewijzingsgeschiedenis weergeven** om een lijst van apparaten en hun toewijzing aan de MDM-server te bekijken.

**Stap 3. Voer de Apple ID in die u hebt gebruikt om het token voor het inschrijvingsprogramma te maken.**<br>Voer in de Intune-portal de Apple ID in, zodat u deze altijd kunt terugvinden. Gebruik deze ID voor het vernieuwen van het token voor het inschrijvingsprogramma, om te voorkomen dat u alle apparaten opnieuw moet inschrijven.
![Schermopname van het invoeren van de Apple ID die is gebruikt voor het maken van het token voor het inschrijvingsprogramma en het uploaden van het token.](./media/enrollment-program-token-apple-id.png)
**Stap 4. Blader naar het token voor het inschrijvingsprogramma om dit te uploaden.**<br>
Ga naar het certificaatbestand (.pem), kies **Openen** en kies vervolgens **Uploaden**. Met het pushcertificaat kan Intune iOS-apparaten inschrijven en beheren door beleid naar geregistreerde mobiele apparaten te pushen. Intune wordt automatisch gesynchroniseerd met Apple om het account voor het inschrijvingsprogramma weer te geven.

## <a name="create-an-apple-enrollment-profile"></a>Een Apple-inschrijvingsprofiel maken

Met een inschrijvingsprofiel voor apparaten worden de instellingen gedefinieerd die worden toegepast op een groep apparaten tijdens de inschrijving.

1. Kies in de Intune-portal achtereenvolgens**Apparaatinschrijving** en **Apple-inschrijving**.
2. Selecteer **Profielen voor het inschrijvingsprogramma** onder **Inschrijvingsprogramma voor Apple** en selecteer vervolgens **Maken** op de blade **Profielen voor het inschrijvingsprogramma**.
![Schermopname van het kiezen van de koppeling voor het maken van een nieuw profiel voor het inschrijvingsprogramma.](./media/enrollment-program-profile-create.png)
3. Voer op de blade **Inschrijvingsprofiel maken** voor administratieve doeleinde een**** naam**** en een beschrijving in voor het profiel. Gebruikers zien deze gegevens niet.
![Schermopname van het invoeren van een naam en beschrijving, en het vervolgens selecteren van Inschrijven met gebruikersaffiniteit voor een nieuw profiel voor het inschrijvingsprogramma.](./media/enrollment-program-profile-name.png)
Geef voor **Gebruikersaffiniteit** aan of u andere apparaten met dit profiel wilt inschrijven met of zonder gebruikersaffiniteit.

 - **Inschrijven met gebruikersaffiniteit**: gebruikers worden tijdens de configuratie gekoppeld aan een apparaat en kunnen vervolgens toegang krijgen tot gegevens en e-mail van het bedrijf. Kies deze**** optie voor apparaten die eigendom zijn van gebruikers en waarvoor de bedrijfsportal moet worden gebruikt voor services als het installeren van apps.

<<<<<<< HEAD
 > [!NOTE]
 > Meervoudige verificatie werkt niet tijdens inschrijving op apparaten met gebruikersaffiniteit die via een inschrijvingsprogramma worden beheerd. Na de inschrijving werkt MFA zoals verwacht op deze apparaten. Nieuwe gebruikers die hun wachtwoord moeten wijzigen wanneer ze zich voor het eerst aanmelden, kunnen geen prompt krijgen tijdens de inschrijving van apparaten. Daarnaast wordt gebruikers met verlopen wachtwoorden niet gevraagd hun wachtwoord opnieuw in te stellen tijdens de inschrijving. Deze gebruikers moeten het wachtwoord vanaf een ander apparaat opnieuw instellen.

 >[!NOTE]
 >Voor beheer met een inschrijvingsprogramma met gebruikersaffiniteit moet [de gebruikersnaam/het gemengde eindpunt voor WS-Trust 1.3](https://technet.microsoft.com/library/adfs2-help-endpoints) zijn ingeschakeld om gebruikerstokens te kunnen aanvragen. [Meer informatie over WS-Trust 1.3](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint).
=======
    >[!NOTE]
    >Voor DEP met gebruikersaffiniteit moet [WS-Trust 1.3 gebruikersnaam/mixed-eindpunt](https://technet.microsoft.com/library/adfs2-help-endpoints) zijn ingeschakeld om een gebruikerstoken aan te vragen. [Meer informatie over WS-Trust 1.3](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint).
>>>>>>> 0c3fe0dee88e8ef4d8ad8ad28c0f8957831dd5b3

 - **Inschrijven zonder gebruikersaffiniteit**: het apparaat is niet gekoppeld aan een gebruiker. Gebruik deze relatie voor apparaten waarmee taken worden uitgevoerd zonder toegang tot lokale gebruikersgegevens. Apps waarvoor een gebruikersrelatie is vereist, zoals de bedrijfsportal-app die wordt gebruikt voor het installeren van LOB-apps, zullen niet werken.

4. Selecteer **Instellingen voor apparaatbeheer** om de volgende profielinstellingen te configureren: ![Schermopname van het kiezen van de beheermodus met de opties Onder supervisie en Vergrendelde inschrijving, met Koppelen toestaan ingesteld op Alles weigeren en Apple Configurator-certificaten lichter gekleurd voor een nieuw profiel voor het inschrijvingsprogramma.](./media/enrollment-program-profile-mode.png)
    - **Onder supervisie**: een beheermodus waarmee standaard meer beheeropties worden ingeschakeld en de activeringsvergrendeling wordt uitgeschakeld. Als u het selectievakje leeg laat, hebt u beperkte beheermogelijkheden.

    - **Vergrendelde inschrijving** (vereist Onder supervisie als beheermodus): hiermee worden de iOS-instellingen uitgeschakeld waarmee het beheerprofiel kan worden verwijderd. Als u dit selectievakje leeg laat, kan het beheerprofiel uit het menu Instellingen worden verwijderd. Dit item wordt ingesteld tijdens de activering en kan niet worden gewijzigd zonder het apparaat op de fabrieksinstellingen terug te zetten.

    - **Koppelen toestaan**: hiermee wordt aangegeven of iOS-apparaten kunnen worden gesynchroniseerd met computers. Als u **Apple Configurator per certificaat toestaan** kiest, moet u een certificaat kiezen onder **Apple Configurator-certificaten**.

    - **Apple Configurator-certificaten**: als u **Apple Configurator per certificaat toestaan** onder **Koppelen toestaan** hebt gekozen, selecteert u het Apple Configurator-certificaat dat u wilt importeren.

  Kies **Opslaan**.

5. Selecteer **Instellingen voor Configuratieassistent** om de volgende profielinstellingen te configureren: ![Schermopname van het kiezen van de configuratie-instellingen met de beschikbare instellingen voor een nieuw profiel voor het inschrijvingsprogramma.](./media/enrollment-program-profile-settings.png)
    - **Naam van afdeling**: wordt weergegeven wanneer gebruikers tijdens de activering op **Over configuratie** tikken.

    - **Telefoonnummer van afdeling**: wordt weergegeven wanneer de gebruiker tijdens de activering de knop Hulp nodig? klikt.
    - **Configuratieassistentopties**: deze instellingen zijn optioneel en kunnen naderhand worden geconfigureerd in het iOS-menu **Instellingen**.
        - **Wachtwoordcode**: hiermee wordt tijdens de activering gevraagd om de wachtwoordcode. Vraag altijd om een wachtwoordcode tenzij het apparaat wordt beveiligd of de toegang tot het apparaat op een andere manier wordt beheerd (bijvoorbeeld de kioskmodus waarmee op het apparaat maar één app kan worden uitgevoerd).
        - **Locatieservices**: als deze optie is ingeschakeld, wordt tijdens de activering door Configuratieassistent om de service gevraagd
        - **Herstellen**: als deze optie is ingeschakeld, wordt tijdens de activering door Configuratieassistent gevraagd om een iCloud-back-up
        - **Apple-id**: als deze optie is ingeschakeld, worden gebruikers door iOS gevraagd om een Apple-id wanneer Intune een app zonder een id probeert te installeren. Een Apple ID is vereist voor het downloaden van iOS-apps uit de App Store, waaronder de apps die zijn geïnstalleerd door Intune.
        - **Voorwaarden**: als deze optie is ingeschakeld, wordt tijdens de activering door Configuratieassistent gevraagd de voorwaarden van Apple te accepteren
        - **Touch ID**: als deze optie is ingeschakeld, wordt tijdens de activering door Configuratieassistent om deze service gevraagd
        - **Apple Pay**: als deze optie is ingeschakeld, wordt tijdens de activering door Configuratieassistent om deze service gevraagd
        - **In- en uitzoomen**: als deze optie is ingeschakeld, wordt tijdens de activering door Configuratieassistent om deze service gevraagd
        - **Siri**: als deze optie is ingeschakeld, wordt tijdens de activering door Configuratieassistent om deze service gevraagd
        - **Diagnostische gegevens**: als deze optie is ingeschakeld, wordt tijdens de activering door Configuratieassistent om deze service gevraagd.

    Kies **Opslaan**.
9. Selecteer **Maken** op de blade **Inschrijvingsprofiel maken** om de profielinstellingen op te slaan. Het inschrijvingsprofiel wordt weergegeven in de lijst met inschrijvingsprofielen voor Apple Enrollment Program.

## <a name="sync-managed-devices"></a>Beheerde apparaten synchroniseren
Nu Intune toestemming heeft om uw apparaten te beheren, kunt u Intune synchroniseren met Apple om uw beheerde apparaten weer te geven in de Intune-portal.

1. Kies in de Intune-portal **Apparaatinschrijving** &gt; **Apple-inschrijving** &gt; **Apparaten voor het inschrijvingsprogramma**.
2. Selecteer **Synchroniseren** onder **Apparaten voor het inschrijvingsprogramma**. De blade **Synchroniseren** wordt weergegeven.
![Schermopname van het geselecteerde knooppunt Apparaten voor het inschrijvingsprogramma en een pijl naar de koppeling Synchroniseren.](./media/enrollment-program-device-sync.png)
3. Selecteer **Synchronisatie aanvragen** op de blade **Synchroniseren**. Op de voortgangsbalk wordt aangegeven hoe lang u moet wachten voordat u opnieuw synchronisatie kunt aanvragen.
![Schermopname van de blade Synchroniseren met een pijl naar de koppeling Synchronisatie aanvragen.](./media/enrollment-program-device-request-sync.png)
    Om te voldoen aan de voorwaarden van Apple voor acceptabel verkeer van het inschrijvingsprogramma, worden door Intune de volgende beperkingen opgelegd:
     -  Een volledige synchronisatie kan niet vaker dan eens in de zeven dagen worden uitgevoerd. Tijdens een volledige synchronisatie vernieuwt Intune elk serienummer dat door Apple aan Intune is toegewezen, of het serienummer eerder is gesynchroniseerd of niet. Als een volledige synchronisatie wordt uitgevoerd binnen zeven dagen na de vorige volledige synchronisatie, vernieuwt Intune alleen serienummers die nog niet aanwezig zijn in Intune.
     -  Een synchronisatieaanvraag krijgt 15 minuten de tijd om te worden uitgevoerd. Gedurende deze tijd of totdat de aanvraag is geslaagd, is de knop **Synchronisatie** uitgeschakeld.
4. Kies in de werkruimte Apparaten voor het inschrijvingsprogramma **Vernieuwen** om uw apparaten weer te geven.

## <a name="assign-an-enrollment-profile-to-devices"></a>Een inschrijvingsprofiel toewijzen aan apparaten
Apparaten die worden beheerd door Intune, moeten een profiel voor het inschrijvingsprogramma toegewezen krijgen voordat ze worden ingeschreven.

>[!NOTE]
>U kunt ook serienummers aan profielen toewijzen via de blade **Apple-serienummers**.

1. Kies **Apparaten inschrijven** > **Apple-inschrijving** in de Intune-portal en selecteer vervolgens **Profielen voor het inschrijvingsprogramma**.
2. Selecteer in de lijst **Profielen voor het inschrijvingsprogramma** het profiel dat u wilt toewijzen aan apparaten en selecteer vervolgens **Apparaten toewijzen**.
![Schermopname van de blade Synchroniseren met een pijl naar de koppeling Synchronisatie aanvragen.](./media/enrollment-program-device-assign.png)
3. Selecteer **Toewijzen** en selecteer vervolgens de apparaten die u aan dit profiel wilt toewijzen. U kunt filteren om beschikbare apparaten weer te geven:
  - **niet-toegewezen**
  - **alle**
  - **&lt;profielnaam&gt;**
4. Selecteer de apparaten die u wilt beheren. Met het selectievakje boven de kolom selecteert u tot 1000 apparaten in de lijst. Klik vervolgens op **Toewijzen**. Als u meer dan 1000 apparaten wilt registreren, herhaalt u de stappen voor toewijzing totdat aan alle apparaten een inschrijvingsprofiel is toegewezen.

  ![Schermopname van de knop Toewijzen voor het toewijzen van een profiel voor het inschrijvingsprogramma in de Intune-portal](media/dep-profile-assignment.png)

## <a name="end-user-experience-with-managed-devices"></a>Ervaring van eindgebruikers met beheerde apparaten

De apparaten kunnen nu worden uitgedeeld aan de gebruikers. Voor apparaten met gebruikersaffiniteit moet aan elke gebruiker een Intune-licentie worden toegewezen. Als het apparaat is geactiveerd en gebruikt wordt, kan het profiel kan niet worden toegepast totdat het apparaat wordt ingesteld op de fabrieksinstellingen. De gebruiker ziet het volgende na inschakeling van een iOS-apparaat dat via een inschrijvingsprogramma wordt beheerd:  

1. **iOS-apparaat instellen**: gebruikers kunnen kiezen uit de volgende opties:
  - **Instellen als nieuw apparaat**
  - **Terugzetten vanaf iCloud-back-up**
  - **Terugzetten vanaf iTunes-back-up**
2. Gebruikers zien een bericht**** dat het apparaat automatisch zal worden geconfigureerd door Microsoft. Daarnaast wordt informatie van deze strekking weergegeven:

  **Configuratie maakt het mogelijk voor Microsoft om dit apparaat draadloos te beheren.**

  **Een beheerder kan u helpen bij het instellen van e-mail- en netwerkaccounts, het installeren en configureren van apps, en het op afstand beheren van instellingen.**

  **Een beheerder kan functies uitschakelen, apps installeren en verwijderen, uw internetverkeer bewaken en beperken en dit apparaat op afstand wissen.**

  **De configuratie wordt uitgevoerd door:<br> MicrosoftIntune iOS Team<br> One Microsoft Way, Redmond, WA 98052 (VS)**

3. Gebruikers wordt gevraagd om de gebruikersnaam en het wachtwoord voor hun werk- of schoolaccount.
4. Gebruikers wordt gevraagd om hun Apple ID. Een Apple ID is vereist voor de installatie van de Intune-bedrijfsportal-app en andere apps. Nadat de referenties zijn opgegeven, wordt er op het apparaat een beheerprofiel geïnstalleerd dat niet kan worden verwijderd. Het beheerprofiel van Intune wordt weergegeven in **Instellingen** > **Algemeen** > **Apparaatbeheer** op het apparaat.

Gebruikers kunnen nu het instellen van hun apparaat in bedrijfseigendom voltooien met behulp van de Intune-bedrijfsportal of de configuratie-assistent van Apple.
