---
title: iOS-apparaten inschrijven met behulp van Apple Configurator
titlesuffix: Microsoft Intune
description: In dit onderwerp leest u hoe u Apple Configurator kunt gebruiken om iOS-apparaten in bedrijfseigendom in te schrijven met Configuratieassistent.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/05/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 6d384cd0-b662-41e7-94f5-0c96790ab20a
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 5ecdd79a029bc3d434ebb0d8ba62ea0e65215f9e
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2018
---
# <a name="enroll-ios-devices-with-apple-configurator"></a>iOS-apparaten inschrijven met Apple Configurator

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

> [!NOTE]
> ### <a name="temporary-user-interface-differences"></a>Tijdelijke verschillen in de gebruikersinterface
>
>De gebruikersinterfaces voor de functies die op deze pagina worden beschreven, worden op dit moment bijgewerkt. Deze updates moeten tegen het einde van april in alle gebruikersaccounts zijn geïmplementeerd.
>
>Als uw pagina **Apparaatinschrijving** niet op de onderstaande afbeelding lijkt, is uw account nog niet bijgewerkt naar de nieuwe gebruikersinterface en kunt u deze Help-pagina gebruiken.
>
>![Oude Intune-gebruikersinterface](./media/appleenroll-oldui.png)
>
>Als uw pagina **Apparaatinschrijving** op de onderstaande afbeelding lijkt, beschikt u over de bijgewerkte gebruikersinterfaces.  Ga dan naar [deze Help-pagina](apple-configurator-enroll-ios-newui.md).
>
>![Nieuwe Intune-gebruikersinterface](./media/appleenroll-newui.png)

Intune ondersteunt het inschrijven van iOS-apparaten met behulp van het hulpprogramma [Apple Configurator](https://itunes.apple.com/app/apple-configurator-2/id1037126344) dat wordt uitgevoerd op een Mac-computer. Inschrijving met Apple Configurator vereist dat u voor elk iOS-apparaat een USB-verbinding instelt met een Mac-computer voor het instellen van een zakelijke inschrijving. U kunt apparaten op twee manieren apparaten inschrijven bij Intune met Apple Configurator:
- **Inschrijving met iOS-configuratieassistent**: het apparaat wordt naar de fabrieksinstelling teruggezet en voorbereid voor inschrijving tijdens het uitvoeren van Configuratieassistent.
- **Directe inschrijving**: het apparaat wordt niet teruggezet naar de fabrieksinstellingen en het apparaat wordt via iOS-instellingen geregistreerd. Deze methode ondersteunt apparaten **zonder gebruikersaffiniteit**.

Inschrijven met Apple Configurator kan niet worden gebruikt met de [apparaatinschrijvingsmanager](device-enrollment-manager-enroll.md).

## <a name="prerequisites"></a>Vereisten

- Fysieke toegang tot iOS-apparaten
- [MDM-instantie instellen](mdm-authority-set.md)
- [Een Apple MDM-pushcertificaat](apple-mdm-push-certificate-get.md)
- Apparaatserienummers (alleen inschrijving met de iOS-configuratieassistent)
- USB-verbindingskabels
- macOS-computer met [Apple Configurator 2.0](https://itunes.apple.com/app/apple-configurator-2/id1037126344)

## <a name="create-an-apple-configurator-profile-for-devices"></a>Een Apple Configurator-profiel maken voor apparaten

Met een inschrijvingsprofiel voor apparaten worden de instellingen tijdens het inschrijven gedefinieerd. Deze instellingen worden slechts eenmaal toegepast. Volg deze stappen om een inschrijvingsprofiel te maken om iOS-apparaten in te schrijven met Apple Configurator.

1. Meld u aan bij de [Azure-portal](https://portal.azure.com).
2. Kies **Alle services** > **Intune**. Intune bevindt zich in de sectie **Controle en beheer**.
3. Kies **Apparaatinschrijving** > **Apple-inschrijving**.
4. Selecteer **AC-profielen** in **Instellingen van de inschrijving met Apple Configurator beheren**.
5. Selecteer **Maken** onder **Apple Configurator-inschrijvingsprofielen**.
6. Typ een **naam** en **beschrijving** voor het profiel (voor administratieve doeleinden). Gebruikers zien deze gegevens niet. U kunt dit veld Naam gebruiken om een dynamische groep te maken in Azure Active Directory. Gebruik de profielnaam om de parameter enrollmentProfileName te definiëren om apparaten aan dit inschrijvingsprofiel toe te wijzen. Meer informatie over dynamische Azure Active Directory-groepen.


  ![Het scherm Profiel maken met Inschrijven met gebruikersaffiniteit geselecteerd](./media/apple-configurator-profile-create.png)

5. Geef de **gebruikersaffiniteit** op:
   - **Inschrijven met gebruikersaffiniteit**: het apparaat moet aan een gebruiker worden gekoppeld met de iOS-configuratieassistent en kan vervolgens toegang krijgen tot gegevens en e-mail van het bedrijf. Gebruikersaffiniteit is vereist voor beheerde apparaten die eigendom zijn van gebruikers en waarvoor de bedrijfsportal moet worden gebruikt voor services als het installeren van apps. Alleen ondersteund bij inschrijving via Apple Configurator Setup Assistant. Gebruikersaffiniteit vereist [WS-Trust 1.3 gebruikersnaam/gemengd eindpunt](https://technet.microsoft.com/library/adfs2-help-endpoints). [Meer informatie](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint).

   > [!NOTE]
   > Multi-Factor Authentication (MFA) werkt niet tijdens het instellen van inschrijving met gebruikersaffiniteit. Na de inschrijving werkt MFA zoals verwacht op apparaten. Op apparaten wordt de gebruiker niet gevraagd het wachtwoord te wijzigen als ze zich de eerste keer aanmelden. Daarnaast wordt gebruikers met verlopen wachtwoorden niet gevraagd hun wachtwoord opnieuw in te stellen tijdens de inschrijving. Deze gebruikers moeten het wachtwoord vanaf een ander apparaat opnieuw instellen.

   - **Inschrijven zonder gebruikersaffiniteit**: het apparaat is niet gekoppeld aan een gebruiker. Gebruik deze relatie voor apparaten waarmee taken worden uitgevoerd zonder toegang tot lokale gebruikersgegevens. Apps waarvoor een gebruikersrelatie is vereist, zoals de bedrijfsportal-app die wordt gebruikt voor het installeren van LOB-apps, zullen niet werken. Vereist voor directe inschrijving.

6. Selecteer **Maken** om het profiel op te slaan.

## <a name="setup-assistant-enrollment"></a>Inschrijving met iOS-configuratieassistent

### <a name="add-apple-configurator-serial-numbers"></a>Apple Configurator-serienummers toevoegen

**Apple Configurator-serienummers toevoegen aan Intune**

1. Maak een lijst met twee kolommen met door komma's gescheiden waarden (.csv) zonder koptekst. Plaats het serienummers in de linkerkolom en de details in de rechterkolom. De lijst kan momenteel maximaal 5000 rijen bevatten. In een teksteditor ziet de .csv-lijst er zo uit:

   F7TLWCLBX196, apparaatdetails</br>
   DLXQPCWVGHMJ,apparaatdetails

   [Lees hier meer informatie over het vinden van het serienummer van een iOS-apparaat](https://support.apple.com/HT204073).
2. Kies in Intune in [Azure Portal](https://portal.azure.com) achtereenvolgens **Apparaatinschrijving** en **Apple-inschrijving**.
3. Selecteer **Apple Configurator-apparaten** onder **Instellingen van de inschrijving met Apple Configurator beheren**.
4. Selecteer **Toevoegen**.
5. Selecteer een **inschrijvingsprofiel** om toe te passen op de serienummers die u importeert. Als u een bestand met nieuwe details importeert dat de bestaande details overschrijft, selecteert u **Details voor bestaande id's overschrijven**.
6. Ga naar het CSV-bestand met de serienummers en selecteer **Toevoegen**.

### <a name="reassign-a-profile-to-device-serial-numbers"></a>Opnieuw een profiel toewijzen aan apparaatserienummers

U wijst een inschrijvingsprofiel toe als u iOS-serienummers voor inschrijving met Apple Configurator importeert. Met Intune kunt u ook vanaf twee plaatsen in Azure Portal profielen toewijzen.
- **Apple Configurator-apparaten**
- **AC-profielen**

#### <a name="assign-from-apple-configurator-devices"></a>Toewijzen vanaf Apple Configurator-apparaten

1. Kies in Intune in [Azure Portal](https://portal.azure.com) achtereenvolgens **Apparaatinschrijving** en **Apple-inschrijving**.
2. Selecteer onder **Apple Configurator-apparaten** de serienummers waaraan u een profiel wilt toewijzen en selecteer vervolgens **Profiel toewijzen**.
3. Selecteer onder **Profiel toewijzen** het **nieuwe profiel** dat u wilt toewijzen en selecteer vervolgens **Toewijzen**.

#### <a name="assign-from-profiles"></a>Toewijzen vanaf profielen
1. Kies in Intune in [Azure Portal](https://portal.azure.com) achtereenvolgens **Apparaatinschrijving** en **Apple-inschrijving**.
2. Kies **AC-profielen** en selecteer vervolgens het profiel waaraan u serienummers wilt toewijzen.
3. Kies **Toegewezen apparaten** in het profiel en kies vervolgens **Toewijzen**.
4. Filter op de serienummers die u aan het profiel wilt toewijzen, selecteer de apparaten en kies **Toewijzen**.

### <a name="export-the-profile"></a>Het profiel exporteren
Nadat u het profiel hebt gemaakt en de serienummers toegewezen, moet u het profiel vanuit Intune als een URL exporteren. Vervolgens importeert u het profiel in Apple Configurator op een Mac om het met apparaten te implementeren.

1. Kies in Intune in [Azure Portal](https://portal.azure.com) achtereenvolgens **Apparaatinschrijving** > **Apple-inschrijving** > **AC-profielen** en kies vervolgens het profiel dat u wilt exporteren.
2. Selecteer **Profiel exporteren** in het profiel.

   ![Profiel exporteren voor inschrijving met configuratieassistent, waarbij de URL van het profiel is gemarkeerd](./media/ios-apple-configurator-expor-sat.png)
3. Kopieer de profiel-URL. U kunt deze vervolgens later aan Apple Configurator toevoegen om het Intune-profiel te definiëren dat wordt gebruikt door iOS-apparaten.

   Vervolgens importeert u in de volgende procedure dit profiel in Apple Configurator om het Intune-profiel te definiëren dat door iOS-apparaten wordt gebruikt.

### <a name="enroll-devices-with-setup-assistant"></a>Apparaten inschrijven met Configuratieassistent

1. Open **Apple Configurator2** op een Mac-computer. Kies in de menubalk **Apple Configurator 2** en vervolgens **Voorkeuren**.
   > [!WARNING]
   > Apparaten worden tijdens het inschrijvingsproces teruggezet naar de fabrieksinstellingen. U kunt het apparaat het beste opnieuw instellen en inschakelen. U moet het apparaat verbinden wanneer het scherm **Hallo** wordt weergegeven.

2. Selecteer in het deelvenster met **voorkeuren** **Servers** en kies het plusteken (+) om de wizard voor de MDM-server te starten. Kies **Volgende**.
3. Voer de **Hostnaam of URL** en de **inschrijvings-URL** in voor de MDM-server onder iOS-apparaten inschrijven via Configuratieassistent in Microsoft Intune. Voer voor de inschrijvings-URL de profiel-URL voor inschrijving in die u hebt geëxporteerd uit Intune. Kies **Volgende**.  

   De waarschuwing 'Server-URL is niet geverifieerd' kunt u zonder problemen negeren. Als u wilt doorgaan, kiest u **Volgende** totdat de wizard is voltooid.
4. Verbind de mobiele iOS-apparaten met de Mac-computer met een USB-adapter.
5. Selecteer de iOS-apparaten die u wilt beheren en kies vervolgens **Voorbereiden**. Selecteer in het deelvenster **iOS-apparaat voorbereiden** de optie **Handmatig** en kies vervolgens **Volgende**.
6. Selecteer in het deelvenster **Registreren bij MDM-server** de naam van de server die u hebt gemaakt en kies vervolgens **Volgende**.
7. Selecteer in het deelvenster **Apparaten onder supervisie plaatsen** het toezichtsniveau en kies **Volgende**.
8. Kies de **organisatie** in het deelvenster **Een organisatie maken** of maak een nieuwe organisatie en kies vervolgens **Volgende**.
9. Kies in het deelvenster **iOS-configuratieassistent configureren** de stappen die de gebruiker te zien krijgt en kies vervolgens **Voorbereiden**. Voer een verificatie uit om de vertrouwensinstellingen bij te werken als dit wordt gevraagd.  
10. Zodra het iOS-apparaat klaar is met de voorbereidingen, kunt u de USB-kabel verwijderen.  

### <a name="distribute-devices"></a>Apparaten distribueren
De apparaten zijn nu gereed voor bedrijfsinschrijving. Schakel de apparaten uit en distribueer ze naar gebruikers. Wanneer gebruikers hun apparaten inschakelen, wordt Configuratieassistent gestart.

Nadat gebruikers hun apparaten hebben ontvangen, moeten ze Configuratieassistent voltooien. Op apparaten die zijn geconfigureerd met gebruikersaffiniteit kan de bedrijfsportal-app worden geïnstalleerd en uitgevoerd om apps te downloaden en apparaten te beheren.

## <a name="direct-enrollment"></a>Directe inschrijving
Wanneer u iOS-apparaten rechtstreeks inschrijft via Apple Configurator, kunt u een apparaat inschrijven zonder het serienummer van het apparaat in te voeren. U kunt ook het apparaat een naam geven voor identificatiedoeleinden voordat Intune de naam van het apparaat vastlegt tijdens de inschrijving. De bedrijfsportal-app wordt niet ondersteund voor rechtstreeks ingeschreven apparaten. De fabrieksinstellingen hoeven niet te worden teruggezet.

Apps waarvoor een gebruikersrelatie is vereist, zoals de bedrijfsportal-app die wordt gebruikt voor het installeren van LOB-apps, kunnen niet worden geïnstalleerd.

### <a name="export-the-profile-as-mobileconfig-to-ios-devices"></a>Het profiel als .mobileconfig exporteren naar iOS-apparaten
1. Meld u aan bij de [Azure-portal](https://portal.azure.com).
2. Kies **Alle services** > **Intune**. Intune bevindt zich in de sectie **Controle en beheer**.
3. Kies onder **Profiel exporteren** de optie **Profiel downloaden** om het inschrijvingsprofiel te downloaden.


  ![Profiel exporteren voor inschrijving met configuratieassistent, waarbij de URL van het profiel is gemarkeerd](./media/ios-apple-configurator-expor-de.png)

2. Breng het bestand over naar een Mac-computer waarop [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) wordt uitgevoerd om het rechtstreeks als een beheerprofiel naar iOS-apparaten te pushen.
3. Bereid het apparaat met behulp van de volgende stappen voor met Apple Configurator.
   1. Open Apple Configurator 2.0 op een Mac-computer.
   2. Verbind het iOS-apparaat met de Mac-computer met behulp van een USB-kabel. Sluit Foto's, iTunes en andere apps die voor het apparaat worden geopend wanneer het apparaat wordt gedetecteerd.
   3. Kies in Apple Configurator het verbonden iOS-apparaat en kies vervolgens de knop **Toevoegen**. Opties die kunnen worden toegevoegd aan het apparaat, worden weergegeven in de vervolgkeuzelijst. Kies **Profielen**.

      ![Profiel exporteren voor inschrijving met configuratieassistent, waarbij de URL van het profiel is gemarkeerd](./media/ios-apple-configurator-add-profile.png)

   4. Gebruik de bestandskiezer om het .mobileconfig-bestand te selecteren dat u uit Intune hebt geëxporteerd. Kies vervolgens **Toevoegen**. Het profiel wordt toegevoegd aan het apparaat. Als het apparaat niet onder supervisie is, vereist de installatie acceptatie op het apparaat.

4. Voer de volgende stappen uit om het profiel op het iOS-apparaat te installeren. Het apparaat moet de Configuratieassistent al hebben uitgevoerd en gereed zijn voor gebruik. Als inschrijving app-implementaties omvat, moet op het apparaat een Apple-id zijn ingesteld, omdat de app-implementatie vereist dat u met een Apple-id bent aangemeld voor de App Store.
   1. Ontgrendel het iOS-apparaat.
   2. Kies in het dialoogvenster **Profiel installeren** voor **Beheerprofiel** de optie **Installeren**.
   3. Geef zo nodig een wachtwoordcode of Apple-id op.
   4. Accepteer de **Waarschuwing** en kies **Installeren**.
   5. Accepteer de **Externe waarschuwing** en kies **Vertrouwen**.
   6. Wanneer in het vak **Profiel geïnstalleerd** wordt bevestigd dat het profiel is geïnstalleerd, kiest u **Gereed**.

5. Open **Instellingen** op het iOS-apparaat en ga naar **Algemeen** > **Apparaatbeheer** > **Beheerprofiel**. Controleer of de profielinstallatie wordt weergegeven en controleer vervolgens de iOS-beleidsbeperkingen en geïnstalleerde apps. Het kan 10 minuten duren voordat beleidsbeperkingen en apps worden weergegeven op het apparaat.

6. Apparaten distribueren. Het iOS-apparaat is nu ingeschreven bij Intune en wordt beheerd.


