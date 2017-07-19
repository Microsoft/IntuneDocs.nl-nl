---
title: iOS-apparaten inschrijven - Apple Configurator en Configuratieassistent
titleSuffix: Intune on Azure
description: In dit onderwerp leest u hoe u Apple Configurator kunt gebruiken om iOS-apparaten die bedrijfseigendom zijn in te schrijven met Configuratieassistent.
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 06/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6d384cd0-b662-41e7-94f5-0c96790ab20a
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1d74fbcebfe89bbafc545d11dd6316cb602db8ee
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/01/2017
---
# <a name="enroll-ios-devices-with-apple-configurator"></a>iOS-apparaten inschrijven met Apple Configurator

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Intune ondersteunt het inschrijven van iOS-apparaten die bedrijfseigendom zijn, met behulp van het hulpprogramma [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) dat wordt uitgevoerd op een Mac-computer. Inschrijving met Apple Configurator vereist dat u voor elk iOS-apparaat een USB-verbinding instelt met een Mac-computer voor het instellen van een zakelijke inschrijving. U kunt apparaten op twee manieren apparaten inschrijven bij Intune met Apple Configurator:
- **Setup Assistant enrollment (Registratie met Configuratieassistent)**: met dit proces wordt het apparaat teruggezet naar de fabrieksinstellingen, wordt het apparaat voorbereid voor uitvoering van Configuratieassistent en worden de bedrijfsbeleidsregels voor de nieuwe gebruiker van het apparaat geïnstalleerd. Voor de meeste scenario's is vereist dat het beleid dat op het iOS-apparaat wordt toegepast, gebruikersaffiniteit bevat, zodat de Intune-bedrijfsportal-app kan worden gebruikt.
- **Direct enrollment (Directe inschrijving)**: met dit proces wordt het apparaat niet teruggezet naar de fabrieksinstellingen en wordt het apparaat met een vooraf gedefinieerd beleid geregistreerd. Deze methode is geschikt voor apparaten **zonder gebruikersaffiniteit**.

>[!NOTE]
>Deze inschrijvingsmethode kan niet worden gebruikt met de methode [Apparaatinschrijvingsmanager](device-enrollment-manager-enroll.md).

Andere methoden voor het registreren van iOS-apparaten worden beschreven in [Choose how to enroll iOS devices in Intune](enrollment-method-choose-ios.md) (Kiezen hoe iOS-apparaten worden geregistreerd in Intune).

## <a name="prerequisites"></a>Vereisten

Voer de volgende vereisten uit voordat u inschrijving van iOS-apparaten instelt:

- [Een Apple MDM-pushcertificaat](apple-mdm-push-certificate-get.md)
- Fysieke toegang tot iOS-apparaten
- Serienummers van apparaten (zie [Een iOS-serienummer opvragen](https://support.apple.com//HT204308))
- USB-verbindingskabels
- Mac-computer met [Apple Configurator 2.0](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12)
- [Apple Configurator-serienummers toevoegen](apple-configurator-serial-numbers-add.md)

## <a name="setup-assistant-enrollment"></a>Inschrijving met iOS-configuratieassistent

### <a name="create-an-apple-configurator-profile-for-devices"></a>Een Apple Configurator-profiel maken voor apparaten

Met een inschrijvingsprofiel voor apparaten worden de instellingen gedefinieerd die worden toegepast op een groep apparaten. De volgende stappen laten zien hoe u een inschrijvingsprofiel kunt maken voor iOS-apparaten die worden ingeschreven met Apple Configurator.

1. Kies in de Intune-portal achtereenvolgens **Apparaatinschrijving** en **Apple-inschrijving**.
2. Selecteer **AC-profielen** onder **Instellingen van de inschrijving van Apple Configurator beheren**.
3. Selecteer **Maken** op de blade **Apple Configurator-inschrijvingsprofielen**.
4. Voer op de blade **Inschrijvingsprofiel maken** een naam en een beschrijving in voor het profiel.
5. Geef voor **Gebruikersaffiniteit** aan of u andere apparaten met dit profiel wilt inschrijven met of zonder gebruikersaffiniteit.

   - **Inschrijven met gebruikersaffiniteit**: het apparaat moet aan een gebruiker worden gekoppeld tijdens de eerste configuratie en kan vervolgens toegang krijgen tot gegevens en e-mail van het bedrijf. Gebruikersaffiniteit moet worden ingesteld voor beheerde apparaten die eigendom zijn van gebruikers en waarvoor de bedrijfsportal moet worden gebruikt voor services als het installeren van apps.
   - **Inschrijven zonder gebruikersaffiniteit**: het apparaat is niet gekoppeld aan een gebruiker. Gebruik deze relatie voor apparaten waarmee taken worden uitgevoerd zonder toegang tot lokale gebruikersgegevens. Apps waarvoor een gebruikersrelatie is vereist, zoals de bedrijfsportal-app die wordt gebruikt voor het installeren van LOB-apps, zullen niet werken.

6. Selecteer **Maken** om het profiel op te slaan.

### <a name="add-apple-configurator-serial-numbers"></a>Apple Configurator-serienummers toevoegen

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Volg deze stappen om serienummers toe te voegen aan Intune als u [door het bedrijf beheerde iOS-apparaten met Apple Configurator wilt inschrijven met de configuratieassistent](apple-configurator-setup-assistant-enroll-ios.md). U kunt serienummers één voor één toevoegen of een bestand met door komma's gescheiden waarden (csv) met serienummers uploaden. Nadat u serienummers hebt toegevoegd, kunt u hieraan een profiel toewijzen. Het profiel bevat specifieke beheerinstellingen die u op apparaten wilt toepassen.

Andere methoden voor het registreren van iOS-apparaten worden beschreven in [Choose how to enroll iOS devices in Intune](enrollment-method-choose-ios.md) (Kiezen hoe iOS-apparaten worden geregistreerd in Intune).

**Apple Configurator-serienummers toevoegen aan Intune**

1. Maak een lijst met twee kolommen met door komma's gescheiden waarden (.csv) zonder koptekst. Voeg de IMEI-id in de linkerkolom toe en de details in de rechterkolom. Een lijst kan momenteel maximaal 500 rijen bevatten. In een teksteditor ziet de .csv-lijst er ongeveer zo uit:

    F7TLWCLBX196, apparaatdetails</br>
    DLXQPCWVGHMJ,apparaatdetails

2. Kies in de Azure Portal achtereenvolgens **Apparaatinschrijving** en **Apple-inschrijving**.
3. Selecteer **Apple Configurator-serienummers** onder **Instellingen van de inschrijving van Apple Configurator beheren**.
4. Selecteer **Toevoegen** op de blade **Apple Configurator-serienummers**.
5. Selecteer op de blade **Serienummers toevoegen** een profiel dat u wilt toepassen op de serienummers die u importeert. Als u een bestand met nieuwe details importeert die de bestaande details overschrijven, selecteert u Details voor bestaande id's overschrijven zodat de nieuwe details de bestaande vervangen.
6. Navigeer naar het .csv-bestand met serienummers en selecteer **Toevoegen**.

### <a name="assign-a-profile-to-specific-serial-numbers"></a>Een profiel toewijzen aan specifieke serienummers

Met Intune kunt u profielen toewijzen vanaf twee verschillende plaatsen in Azure Portal. U kunt toewijzen via het Apple Configurator-profiel of via apparaten.

#### <a name="assign-by-devices"></a>Via apparaten toewijzen
1. Kies in de Intune-portal achtereenvolgens **Apparaatinschrijving** en **Apple-inschrijving**.
3. Selecteer op de blade **Apple Configurator-apparaten** de seriële nummers waaraan u een profiel wilt toewijzen en selecteer vervolgens **Profiel toewijzen**.
4. Selecteer op de blade **Profiel toewijzen** het profiel dat u wilt toewijzen en selecteer vervolgens **Toewijzen**.

#### <a name="assign-by-profiles"></a>Via profielen toewijzen
1. Kies in de Intune-portal achtereenvolgens **Apparaatinschrijving** en **Apple-inschrijving**.
2. Kies **AC-profielen** en selecteer vervolgens het profiel waaraan u serienummers wilt toewijzen.
3. Selecteer op de blade met de naam van het profiel **Serienummers** > **Toewijzen**.
4. Selecteer de serienummers die u aan het profiel wilt toewijzen en selecteer vervolgens de knop **Toewijzen**.

### <a name="export-the-profile-to-ios-devices"></a>De profielen exporteren naar iOS-apparaten
Nadat u het profiel hebt gemaakt en serienummers hebt toegewezen, moet u het profiel als URL of als bestand in de hieronder beschreven indeling exporteren uit Intune. Vervolgens importeert u het profiel handmatig in het Apple Configurator-programma op een Mac, waarna het profiel met het Apple Configurator-programma op de apparaten wordt geïmplementeerd.

1. Kies in de Intune-portal het profiel dat u wilt exporteren op de blade **Apple Configurator-inschrijvingsprofielen**.
2. Selecteer **Profiel exporteren** op de blade voor het profiel.
3. Kopieer de URL van het profiel naar [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) terwijl het iOS-apparaat is aangesloten. U zult deze later in Apple Configurator uploaden om het Intune-profiel te definiëren dat wordt gebruikt door iOS-apparaten.

  In de volgende procedure uploadt u deze profiel-URL met Apple Configurator naar de Apple-service om het Intune-profiel te definiëren dat door iOS-apparaten wordt gebruikt.
4. Upload deze profiel-URL met Apple Configurator naar de Apple-service om het Intune-profiel te definiëren dat door iOS-apparaten wordt gebruikt.
 1.  Open **Apple Configurator2** op een Mac-computer. Kies in de menubalk **Apple Configurator 2** en vervolgens **Voorkeuren**.
  > [!WARNING]
  > De apparaten worden tijdens het inschrijvingsproces opnieuw ingesteld op de fabrieksconfiguraties. U kunt het apparaat het beste opnieuw instellen en inschakelen. U moet het apparaat verbinden wanneer het scherm **Hallo** wordt weergegeven.
  2. Selecteer in het deelvenster met **voorkeuren** **Servers** en kies het plusteken (+) om de wizard voor de MDM-server te starten. Kies **Volgende**.
  3. Voer de **Hostnaam of URL** en de **inschrijvings-URL** in voor de MDM-server onder iOS-apparaten inschrijven via Configuratieassistent in Microsoft Intune. Voer voor de inschrijvings-URL de profiel-URL voor inschrijving in die u hebt geëxporteerd uit Intune. Kies **Volgende**.  

    De waarschuwing 'Server-URL is niet geverifieerd' kunt u zonder problemen negeren. Als u wilt doorgaan, kiest u **Volgende** totdat de wizard is voltooid.
  4.  Verbind de mobiele iOS-apparaten met de Mac-computer met een USB-adapter.
  > [!WARNING]
  > De apparaten worden tijdens het inschrijvingsproces opnieuw ingesteld op de fabrieksconfiguraties. U kunt het apparaat het beste opnieuw instellen en inschakelen. U moet Configuratieassistent starten wanneer het scherm **Hallo** wordt weergegeven.
  5.  Kies **Voorbereiden**. Selecteer in het deelvenster **iOS-apparaat voorbereiden** de optie **Handmatig** en kies vervolgens **Volgende**.
  6. Selecteer in het deelvenster **Registreren bij MDM-server** de naam van de server die u hebt gemaakt en kies vervolgens **Volgende**.
  7. Selecteer in het deelvenster **Apparaten onder supervisie plaatsen** het toezichtsniveau en kies **Volgende**.
  8. Kies de **organisatie** in het deelvenster **Een organisatie maken** of maak een nieuwe organisatie en kies vervolgens **Volgende**.
  9. Kies in het deelvenster **iOS-configuratieassistent configureren** de stappen die de gebruiker te zien krijgt en kies vervolgens **Voorbereiden**. Voer een verificatie uit om de vertrouwensinstellingen bij te werken als dit wordt gevraagd.  
  10. Zodra het iOS-apparaat klaar is met de voorbereidingen, kunt u de USB-kabel verwijderen.  
6.  **Apparaten distribueren**.
    De apparaten zijn nu gereed voor bedrijfsinschrijving. Schakel de apparaten uit en distribueer ze naar gebruikers. Wanneer gebruikers hun apparaten inschakelen, wordt Configuratieassistent gestart.

## <a name="direct-enrollment"></a>Directe inschrijving
Wanneer u iOS-apparaten rechtstreeks inschrijft via Apple Configurator, kunt u een apparaat inschrijven zonder het serienummer van het apparaat in te voeren. U kunt ook het apparaat een naam geven voor identificatiedoeleinden voordat Intune de naam van het apparaat vastlegt tijdens de inschrijving. De bedrijfsportal-app wordt niet ondersteund voor rechtstreeks ingeschreven apparaten. In deze richtlijnen wordt ervan uitgegaan dat u Apple Configurator 2.0 gebruikt op een Mac-computer.

1. Kies in de Intune-portal achtereenvolgens**Apparaatinschrijving**, **Apple-inschrijving** en selecteer vervolgens **AC-profielen**.
2. Selecteer **Maken** op de blade **Apple Configurator-inschrijvingsprofielen**.
3. Voer op de blade **Inschrijvingsprofiel maken** een naam en een beschrijving in voor het profiel.
4. Kies voor **Gebruikersaffiniteit** de optie **Inschrijven zonder gebruikersaffiniteit** om ervoor te zorgen dat het apparaat niet aan een gebruiker is gekoppeld. Gebruik deze relatie voor apparaten waarmee taken worden uitgevoerd zonder toegang tot lokale gebruikersgegevens. Apps waarvoor een gebruikersrelatie is vereist, zoals de bedrijfsportal-app die wordt gebruikt voor het installeren van LOB-apps, zullen niet werken.
5. Selecteer **Maken** om het profiel op te slaan.

### <a name="export-the-profile-as-mobileconfig-to-ios-devices"></a>Het profiel als .mobileconfig exporteren naar iOS-apparaten

1. Download het inschrijvingsprofiel op de blade **Profiel exporteren** naar [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) om dit direct als een beheerprofiel te pushen naar een aangesloten iOS-apparaat. De fabrieksinstellingen hoeven niet te worden teruggezet.
2. Bereid het apparaat met behulp van de volgende stappen voor met Apple Configurator.
  1. Open Apple Configurator 2.0 op een Mac-computer.
  2. Verbind het iOS-apparaat met de Mac-computer met behulp van een USB-kabel. Sluit Foto's, iTunes en andere apps die voor het apparaat worden geopend wanneer het apparaat wordt gedetecteerd.
  3. Kies in Apple Configurator het verbonden iOS-apparaat en kies vervolgens de knop **Toevoegen**. Opties die kunnen worden toegevoegd aan het apparaat, worden weergegeven in de vervolgkeuzelijst. Kies **Profielen**.
  4. Gebruik de bestandskiezer om het .mobileconfig-bestand te selecteren dat u uit Intune hebt geëxporteerd. Kies vervolgens **Toevoegen**. Het profiel wordt toegevoegd aan het apparaat. Als het apparaat niet onder supervisie is, vereist de installatie acceptatie op het apparaat.
3. Voer de volgende stappen uit om het profiel op het iOS-apparaat te installeren. Het apparaat moet de Configuratieassistent al hebben uitgevoerd en gereed zijn voor gebruik. Als inschrijving app-implementaties omvat, moet op het apparaat een Apple ID zijn ingesteld, omdat de app-implementaties vereisen dat u met een Apple ID bent aangemeld voor de App Store.
   1. Ontgrendel het iOS-apparaat.
   2. Kies in het dialoogvenster **Profiel installeren** voor **Beheerprofiel** de optie **Installeren**.
   3. Geef zo nodig een wachtwoordcode of Apple ID op.
   4. Accepteer de **Waarschuwing** en kies **Installeren**.
   5. Accepteer de **Externe waarschuwing** en kies **Vertrouwen**.
   6. Wanneer in het vak **Profiel geïnstalleerd** wordt bevestigd dat het profiel is geïnstalleerd, kiest u **Gereed**.

    4. Open **Instellingen** op het iOS-apparaat en ga naar **Algemeen** > **Apparaatbeheer** > **Beheerprofiel**. Controleer of de profielinstallatie wordt weergegeven en controleer vervolgens de iOS-beleidsbeperkingen en geïnstalleerde apps. Het kan 10 minuten duren voordat beleidsbeperkingen en apps worden weergegeven op het apparaat.

    5. Apparaten distribueren. Het iOS-apparaat is nu ingeschreven bij Intune en wordt beheerd.


## <a name="how-users-install-and-use-the-company-portal-on-their-devices"></a>Hoe gebruikers de bedrijfsportal op hun apparaten installeren en gebruiken

Op apparaten die zijn geconfigureerd met gebruikersaffiniteit kan de bedrijfsportal-app worden geïnstalleerd en uitgevoerd om apps te downloaden en apparaten te beheren. Nadat gebruikers hun apparaten hebben ontvangen, moeten zij de onderstaande extra stappen uitvoeren om Configuratieassistent te voltooien en de bedrijfsportal-app te installeren.
