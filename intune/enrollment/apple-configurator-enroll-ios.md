---
title: iOS-/iPadOS-apparaten inschrijven - Apple Configurator en Configuratieassistent
titleSuffix: Microsoft Intune
description: In dit onderwerp leest u hoe u Apple Configurator kunt gebruiken om iOS-/iPadOS-apparaten in bedrijfseigendom in te schrijven met Configuratieassistent.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 05/04/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: enrollment
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 671e4d76-0c61-11e8-ba89-0ed5f89f718b
ms.reviewer: tisilver
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8ccd41b6ebc9bdf62c1603e508cb881a1be62ee7
ms.sourcegitcommit: 51591b862d97904291af7aa53a6eb341b11a761e
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/17/2020
ms.locfileid: "77415389"
---
# <a name="set-up-iosipados-device-enrollment-with-apple-configurator"></a>Registratie van iOS-/iPadOS-apparaten instellen met Apple Configurator

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Intune ondersteunt het inschrijven van iOS-/iPadOS-apparaten met behulp van het hulpprogramma [Apple Configurator](https://itunes.apple.com/app/apple-configurator-2/id1037126344) dat wordt uitgevoerd op een Mac-computer. Inschrijving met Apple Configurator vereist dat u elk iOS-/iPadOS-apparaat via USB verbindt met een Mac-computer voor het instellen van een zakelijke inschrijving. U kunt apparaten op twee manieren apparaten inschrijven bij Intune met Apple Configurator:
- **Inschrijving met iOS-configuratieassistent**: het apparaat wordt gewist en voorbereid voor inschrijving tijdens het uitvoeren van Configuratieassistent.
- **Directe inschrijving**: het apparaat wordt niet gewist en het apparaat wordt via iOS-/iPadOS-instellingen ingeschreven. Deze methode ondersteunt apparaten **zonder gebruikersaffiniteit**.

Inschrijven met Apple Configurator kan niet worden gebruikt met de [apparaatinschrijvingsmanager](device-enrollment-manager-enroll.md).

## <a name="prerequisites"></a>Vereisten

- Fysieke toegang tot iOS-/iPadOS-apparaten
- [MDM-instantie instellen](../fundamentals/mdm-authority-set.md)
- [Een Apple MDM-pushcertificaat](apple-mdm-push-certificate-get.md)
- Apparaatserienummers (alleen inschrijving met de iOS-configuratieassistent)
- USB-verbindingskabels
- macOS-computer met [Apple Configurator 2.0](https://itunes.apple.com/app/apple-configurator-2/id1037126344)

## <a name="create-an-apple-configurator-profile-for-devices"></a>Een Apple Configurator-profiel maken voor apparaten

Met een inschrijvingsprofiel voor apparaten worden de instellingen tijdens het inschrijven gedefinieerd. Deze instellingen worden slechts eenmaal toegepast. Volg deze stappen om een inschrijvingsprofiel te maken om iOS-/iPadOS-apparaten in te schrijven met Apple Configurator.

1. Kies in het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431) de opties **Apparaten** > **iOS** > **iOS-inschrijving** > **Apple Configurator** > **Profielen** > **Maken**.

    ![Een profiel maken voor Apple Configurator](./media/apple-configurator-enroll-ios/apple-config-create-profile.png)

2. Typ onder **Inschrijvingsprofiel maken** een **naam** en **beschrijving** voor het profiel (voor administratieve doeleinden). Gebruikers zien deze gegevens niet. U kunt dit veld Naam gebruiken om een dynamische groep te maken in Azure Active Directory. Gebruik de profielnaam om de parameter enrollmentProfileName te definiëren om apparaten aan dit inschrijvingsprofiel toe te wijzen. Meer informatie over dynamische Azure Active Directory-groepen.

    ![Schermafbeelding van het scherm Profiel maken met Inschrijven met gebruikersaffiniteit geselecteerd](./media/apple-configurator-enroll-ios/apple-configurator-profile-create.png)

3. Geef voor **Gebruikersaffiniteit** aan of andere apparaten met dit profiel met of zonder toegewezen gebruiker moeten worden ingeschreven.

    - **Inschrijven met gebruikersaffiniteit**: kies deze optie voor apparaten die eigendom zijn van gebruikers en die de bedrijfsportal willen gebruiken voor services zoals het installeren van apps. Het apparaat moet met de Configuratieassistent aan een gebruiker worden gekoppeld en kan vervolgens toegang krijgen tot bedrijfsgegevens en -e-mail. Alleen ondersteund bij inschrijving via Apple Configurator Setup Assistant. Gebruikersaffiniteit vereist [WS-Trust 1.3 gebruikersnaam/gemengd eindpunt](https://technet.microsoft.com/library/adfs2-help-endpoints). [Meer informatie](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint).

    - **Inschrijven zonder gebruikersaffiniteit**: kies deze optie voor apparaten die niet aan één gebruiker zijn gelieerd. Gebruik dit voor apparaten waarmee taken worden uitgevoerd zonder toegang tot lokale gebruikersgegevens. Apps waarvoor een gebruikersrelatie is vereist, zoals de bedrijfsportal-app die wordt gebruikt voor het installeren van LOB-apps, zullen niet werken. Vereist voor directe inschrijving.

     > [!NOTE]
     > Als **Inschrijven met gebruikersaffiniteit** is geselecteerd, zorgt u ervoor dat het apparaat, binnen 24 na de inschrijving ervan, met Configuratieassistent is gekoppeld aan een gebruiker. Anders mislukt de inschrijving en is er een herstel naar fabrieksinstellingen nodig om het apparaat in te schrijven.

4. Als u kiest voor **Inschrijven met gebruikersaffiniteit**, hebt u de optie om gebruikers zich te laten verifiëren met de bedrijfsportal in plaats van de Apple-configuratieassistent.

    > [!NOTE]
    > Als u een van de volgende handelingen wilt uitvoeren, stelt u **Verifiëren met bedrijfsportal in plaats van Apple-configuratieassistent** in op **Ja**.
    >    - meervoudige verificatie gebruiken
    >    - gebruikers vragen het wachtwoord te wijzigen als ze zich de eerste keer aanmelden
    >    - gebruikers vragen om hun verlopen wachtwoorden tijdens het inschrijven te herstellen
    >
    > Deze worden niet ondersteund bij het verifiëren met Apple-configuratieassistent.


6. Kies **Maken** om het profiel op te slaan.

## <a name="setup-assistant-enrollment"></a>Inschrijving met iOS-configuratieassistent

### <a name="add-apple-configurator-serial-numbers"></a>Apple Configurator-serienummers toevoegen

1. Maak een lijst met twee kolommen met door komma's gescheiden waarden (.csv) zonder koptekst. Plaats het serienummers in de linkerkolom en de details in de rechterkolom. De lijst kan momenteel maximaal 5000 rijen bevatten. In een teksteditor ziet de .csv-lijst er zo uit:

    F7TLWCLBX196, apparaatdetails</br>
    DLXQPCWVGHMJ,apparaatdetails

   [Lees hier meer informatie over het vinden van het serienummer van een iOS-/iPadOS-apparaat](https://support.apple.com/HT204073).
2. Kies in het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431) de opties **Apparaten** > **iOS** > **iOS-inschrijving** > **Apple Configurator** > **Apparaten** > **Maken**.

5. Selecteer een **inschrijvingsprofiel** om toe te passen op de serienummers die u importeert. Als u wilt dat bestaande details worden overschreven door de nieuwe details van serienummers, kiest u **Details voor bestaande id's overschrijven**.
6. Zoek onder **Apparaten importeren** naar het CSV-bestand met serienummers en selecteer **Toevoegen**.

### <a name="reassign-a-profile-to-device-serial-numbers"></a>Opnieuw een profiel toewijzen aan apparaatserienummers

U kunt een inschrijvingsprofiel toewijzen als u iOS-/iPadOS-serienummers importeert voor inschrijving met Apple Configurator. U kunt ook profielen toewijzen vanaf twee plaatsen in Azure Portal:
- **Apple Configurator-apparaten**
- **AC-profielen**

#### <a name="assign-from-apple-configurator-devices"></a>Toewijzen vanaf Apple Configurator-apparaten
1. Kies in het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431) de opties **Apparaten** > **iOS** > **iOS-inschrijving** > **Apple Configurator** > **Apparaten** > kies de serienummers > **Profiel toewijzen**.
2. Kies onder **Profiel toewijzen** voor het **nieuwe profiel** dat u wilt toewijzen en kies vervolgens voor **Toewijzen**.

#### <a name="assign-from-profiles"></a>Toewijzen vanaf profielen
1. Kies in het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431) de opties **Apparaten** > **iOS** > **iOS-inschrijving** > **Apple Configurator** > **Profielen** > kies een profiel.
2. Kies **Toegewezen apparaten** in het profiel en kies vervolgens **Toewijzen**.
3. Filter op de serienummers die u aan het profiel wilt toewijzen, selecteer de apparaten en kies **Toewijzen**.

### <a name="export-the-profile"></a>Het profiel exporteren
Nadat u het profiel hebt gemaakt en de serienummers toegewezen, moet u het profiel vanuit Intune als een URL exporteren. Vervolgens importeert u het profiel in Apple Configurator op een Mac om het met apparaten te implementeren.

1. Kies in het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431) de opties **Apparaten** > **iOS** > **iOS-inschrijving** > **Apple Configurator** > **Profielen** > kies het profiel dat u wilt exporteren.
2. Selecteer **Profiel exporteren** in het profiel.
3. Kopieer de **profiel-URL**. U kunt deze vervolgens aan Apple Configurator toevoegen om het Intune-profiel te definiëren dat wordt gebruikt door iOS-/iPadOS-apparaten.

   Vervolgens importeert u in de volgende procedure dit profiel in Apple Configurator om het Intune-profiel te definiëren dat door iOS-/iPadOS-apparaten wordt gebruikt.

### <a name="enroll-devices-with-setup-assistant"></a>Apparaten inschrijven met Configuratieassistent

1. Open **Apple Configurator2** op een Mac-computer. Kies in de menubalk **Apple Configurator 2** en vervolgens **Voorkeuren**.
    > [!WARNING]
    > Apparaten worden tijdens het inschrijvingsproces teruggezet naar de fabrieksinstellingen. U kunt het apparaat het beste opnieuw instellen en inschakelen. U moet het apparaat verbinden wanneer het scherm **Hallo** wordt weergegeven.
    > Als het apparaat al is ingeschreven met het Apple ID-account, moet het apparaat worden verwijderd uit de Apple-iCloud voordat het inschrijvingsproces wordt gestart. De promptfout is: Kan [apparaatnaam] niet activeren.

2. Selecteer in het deelvenster met **voorkeuren** **Servers** en kies het plusteken (+) om de wizard voor de MDM-server te starten. Kies **Volgende**.
3. Voer de **hostnaam of URL** en de **inschrijvings-URL** in voor de MDM-server onder iOS-/iPadOS-apparaten inschrijven via Configuratieassistent in Microsoft Intune. Voer voor de inschrijvings-URL de profiel-URL voor inschrijving in die u hebt geëxporteerd uit Intune. Kies **Volgende**.  
    De waarschuwing 'Server-URL is niet geverifieerd' kunt u zonder problemen negeren. Als u wilt doorgaan, kiest u **Volgende** totdat de wizard is voltooid.
4. Verbind de iOS-/iPadOS-apparaten via een USB-adapter met de Mac-computer.
5. Selecteer de iOS-/iPadOS-apparaten die u wilt beheren en kies vervolgens **Voorbereiden**. Selecteer in het deelvenster **iOS-/iPadOS-apparaat voorbereiden** de optie **Handmatig** en kies vervolgens **Volgende**.
6. Selecteer in het deelvenster **Registreren bij MDM-server** de naam van de server die u hebt gemaakt en kies vervolgens **Volgende**.
7. Selecteer in het deelvenster **Apparaten onder supervisie plaatsen** het toezichtsniveau en kies **Volgende**.
8. Kies de **organisatie** in het deelvenster **Een organisatie maken** of maak een nieuwe organisatie en kies vervolgens **Volgende**.
9. Kies in het deelvenster **iOS-/iPadOS-configuratieassistent configureren** de stappen die de gebruiker te zien krijgt en kies vervolgens **Voorbereiden**. Voer een verificatie uit om de vertrouwensinstellingen bij te werken als dit wordt gevraagd.  
10. Zodra het iOS-/iPadOS-apparaat klaar is met de voorbereidingen, kunt u de USB-kabel verwijderen.  

### <a name="distribute-devices"></a>Apparaten distribueren
De apparaten zijn nu gereed voor bedrijfsinschrijving. Schakel de apparaten uit en distribueer ze naar gebruikers. Wanneer gebruikers hun apparaten inschakelen, wordt Configuratieassistent gestart.

Nadat gebruikers hun apparaten hebben ontvangen, moeten ze Configuratieassistent voltooien. Op apparaten die zijn geconfigureerd met gebruikersaffiniteit kan de bedrijfsportal-app worden geïnstalleerd en uitgevoerd om apps te downloaden en apparaten te beheren.

## <a name="direct-enrollment"></a>Directe inschrijving
Wanneer u iOS-/iPadOS-apparaten rechtstreeks inschrijft via Apple Configurator, kunt u een apparaat inschrijven zonder het serienummer van het apparaat in te voeren. U kunt ook het apparaat een naam geven voor identificatiedoeleinden voordat Intune de naam van het apparaat vastlegt tijdens de inschrijving. De bedrijfsportal-app wordt niet ondersteund voor rechtstreeks ingeschreven apparaten. Via deze methode wordt het apparaat niet gewist.

Apps waarvoor een gebruikersrelatie is vereist, zoals de bedrijfsportal-app die wordt gebruikt voor het installeren van LOB-apps, kunnen niet worden geïnstalleerd.

### <a name="export-the-profile-as-mobileconfig-to-iosipados-devices"></a>Het profiel als .mobileconfig exporteren naar iOS-/iPadOS-apparaten

1. Kies in het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431) de opties **Apparaten** > **iOS** > **iOS-inschrijving** > **Apple Configurator** > **Profielen** > kies het profiel dat u wilt exporteren > **Profiel exporteren**.
2. Kies onder **Directe inschrijving** voor **Profiel downloaden** en sla het bestand op. Een inschrijvingsprofielbestand is slechts twee weken geldig. Na die tijd moet u weer een nieuw bestand maken.
3. Breng het bestand over naar een Mac-computer waarop [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) wordt uitgevoerd om het rechtstreeks als een beheerprofiel naar iOS-/iPadOS-apparaten te pushen.
4. Bereid het apparaat aan de hand van de volgende stappen voor met Apple Configurator:
    1. Open Apple Configurator 2.0 op een Mac-computer.
    2. Verbind het iOS-/iPadOS-apparaat met de Mac-computer met behulp van een USB-kabel. Sluit Foto's, iTunes en andere apps die voor het apparaat worden geopend wanneer het apparaat wordt gedetecteerd.
    3. Kies in Apple Configurator het verbonden iOS-/iPadOS-apparaat en kies vervolgens de knop **Toevoegen**. Opties die kunnen worden toegevoegd aan het apparaat, worden weergegeven in de vervolgkeuzelijst. Kies **Profielen**.

        ![Schermafbeelding Profiel Exporteren voor Inschrijving met iOS-configuratieassistent met Profiel-URL gemarkeerd](./media/apple-configurator-enroll-ios/ios-apple-configurator-add-profile.png)

    4. Gebruik de bestandskiezer om het .mobileconfig-bestand te selecteren dat u uit Intune hebt geëxporteerd. Kies vervolgens **Toevoegen**. Het profiel wordt toegevoegd aan het apparaat. Als het apparaat niet onder supervisie is, vereist de installatie acceptatie op het apparaat.
5. Voer de volgende stappen uit om het profiel op het iOS-/iPadOS-apparaat te installeren. Het apparaat moet de Configuratieassistent al hebben uitgevoerd en gereed zijn voor gebruik. Als inschrijving app-implementaties omvat, moet op het apparaat een Apple-id zijn ingesteld, omdat de app-implementatie vereist dat u met een Apple-id bent aangemeld voor de App Store.
    1. Ontgrendel het iOS-/iPadOS-apparaat.
    2. Kies in het dialoogvenster **Profiel installeren** voor **Beheerprofiel** de optie **Installeren**.
    3. Geef zo nodig een wachtwoordcode of Apple-id op.
    4. Accepteer de **Waarschuwing** en kies **Installeren**.
    5. Accepteer de **Externe waarschuwing** en kies **Vertrouwen**.
    6. Wanneer in het vak **Profiel geïnstalleerd** wordt bevestigd dat het profiel is geïnstalleerd, kiest u **Gereed**.

6. Open **Instellingen** op het iOS-/iPadOS-apparaat en ga naar **Algemeen** > **Apparaatbeheer** > **Beheerprofiel**. Controleer of de profielinstallatie wordt weergegeven en controleer vervolgens de iOS-/iPadOS-beleidsbeperkingen en geïnstalleerde apps. Het kan 10 minuten duren voordat beleidsbeperkingen en apps worden weergegeven op het apparaat.

7. Apparaten distribueren. Het iOS-/iPadOS-apparaat is nu ingeschreven bij Intune en wordt beheerd.





