---
title: iOS-apparaten inschrijven - Apple Configurator - Configuratieassistent | Intune Azure Preview | Microsoft Docs
description: 'Intune Azure Preview: in dit onderwerp leest u hoe u Apple Configurator kunt gebruiken om iOS-apparaten die bedrijfseigendom zijn in te schrijven met Configuratieassistent.'
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6d384cd0-b662-41e7-94f5-0c96790ab20a
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 08dad848a48adad7d9c6f0b5b3286f6550a266bd
ms.openlocfilehash: 888e7b7af7dcca4154f67a1de781eb7908d9a187
ms.lasthandoff: 02/15/2017


---

# <a name="enroll-ios-devices-with-apple-configurator-and-setup-assistant"></a>iOS-apparaten inschrijven met Apple Configurator en Configuratieassistent 

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Intune ondersteunt het inschrijven van iOS-apparaten die bedrijfseigendom zijn, met behulp van het hulpprogramma [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) dat wordt uitgevoerd op een Mac-computer. Met dit proces wordt het apparaat teruggezet naar de fabrieksinstellingen, wordt het apparaat voorbereid voor uitvoering van Configuratieassistent en worden de bedrijfsbeleidsregels voor de nieuwe gebruiker van het apparaat geïnstalleerd.

>[!NOTE]
>Deze inschrijvingsmethode kan niet worden gebruikt met de methode [Apparaatinschrijvingsmanager](enroll-devices-using-device-enrollment-manager.md).

Met behulp van Apple Configurator kunt u de fabrieksinstellingen van iOS-apparaten terugzetten en deze apparaten voorbereiden op de nieuwe gebruiker van het apparaat. Voor deze methode is vereist dat u met het iOS-apparaat een USB-verbinding met een Mac-computer maakt om bedrijfsinschrijving in te stellen en wordt ervan uitgegaan dat u Apple Configurator 2.0 gebruikt. Voor de meeste scenario's is vereist dat het beleid dat op het iOS-apparaat wordt toegepast, gebruikersaffiniteit bevat, zodat de Intune-bedrijfsportal-app kan worden gebruikt.

Andere methoden voor het registreren van iOS-apparaten worden beschreven in [Choose how to enroll iOS devices in Intune](choose-ios-enrollment-method.md) (Kiezen hoe iOS-apparaten worden geregistreerd in Intune).

## <a name="prerequisites"></a>Vereisten

Voer de volgende vereisten uit voordat u inschrijving van iOS-apparaten instelt:

- [Domeinen configureren](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-2)
- [MDM-instantie instellen](set-mdm-authority.md)
- [Groepen maken](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-5)
- [De bedrijfsportal configureren](/intune-azure/manage-apps/company-portal-app.md)
- Gebruikerslicenties toewijzen in de [Office 365-portal](http://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Een Apple MDM-pushcertificaat ophalen](get-an-apple-mdm-push-certificate.md)
- Fysieke toegang tot de iOS-apparaten
- Serienummers van apparaten (zie [Een iOS-serienummer opvragen](https://support.apple.com//HT204308))
- USB-verbindingskabels
- Een Mac-computer waarop [Apple Configurator 2.0](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) is geïnstalleerd
- [Apple Configurator-serienummers toevoegen](add-apple-configurator-serial-numbers.md)


## <a name="create-an-apple-configurator-profile-for-devices"></a>Een Apple Configurator-profiel maken voor apparaten

Met een inschrijvingsprofiel voor apparaten worden de instellingen gedefinieerd die worden toegepast op een groep apparaten. De volgende stappen laten zien hoe u een inschrijvingsprofiel kunt maken voor iOS-apparaten die worden ingeschreven met Apple Configurator.

1. Kies in Azure Portal **Meer services** > **Bewaking en beheer** > **Intune**.

2. Kies **Apparaten inschrijven** op de blade Intune en kies vervolgens **Apple-inschrijving**.

3. Selecteer **AC-profielen** onder **Instellingen van de inschrijving van Apple Configurator beheren**.

4. Selecteer **Maken** op de blade **Apple Configurator-inschrijvingsprofielen**.

5. Voer op de blade **Inschrijvingsprofiel maken** een naam en een beschrijving in voor het profiel.

6. Geef voor **Gebruikersaffiniteit** aan of u andere apparaten met dit profiel wilt inschrijven met of zonder gebruikersaffiniteit.

   - **Inschrijven met gebruikersaffiniteit**: het apparaat moet aan een gebruiker worden gekoppeld tijdens de eerste configuratie en kan vervolgens toegang krijgen tot gegevens en e-mail van het bedrijf. Gebruikersaffiniteit moet worden ingesteld voor DEP-beheerde apparaten die eigendom zijn van gebruikers en waarvoor de bedrijfsportal moet worden gebruikt voor services als het installeren van apps.

   - **Inschrijven zonder gebruikersaffiniteit**: het apparaat is niet gekoppeld aan een gebruiker. Gebruik deze relatie voor apparaten waarmee taken worden uitgevoerd zonder toegang tot lokale gebruikersgegevens. Apps waarvoor een gebruikersrelatie is vereist, zoals de bedrijfsportal-app die wordt gebruikt voor het installeren van LOB-apps, zullen niet werken.

7. Selecteer **Maken** om het profiel op te slaan.

## <a name="assign-serial-numbers-to-an-apple-configurator-profile"></a>Serienummers toewijzen aan een Apple Configurator-profiel

Nadat u Apple Configurator-profielen hebt gemaakt, kunt u apparaatserienummers aan de profielen toewijzen. Om serienummers te kunnen toewijzen, moet u deze eerst aan Intune toevoegen. Volg hiervoor de stappen in [Apple Configurator-serienummers toevoegen](add-apple-configurator-serial-numbers.md).

### <a name="assign-serial-numbers-to-apple-configurator-profiles"></a>Serienummers toewijzen aan Apple Configurator-profielen

1. Kies in Azure Portal **Meer services** > **Bewaking en beheer** > **Intune**.

2. Selecteer op de blade **Apple Configurator-inschrijvingsprofielen** het profiel waaraan u serienummers wilt toewijzen.

3. Selecteer op de blade met de naam van het profiel **Serienummers** > **Toewijzen**.

4. Selecteer de serienummers die u aan het profiel wilt toewijzen en selecteer vervolgens de knop **Toewijzen**.

## <a name="export-the-profile-to-ios-devices"></a>De profielen exporteren naar iOS-apparaten

Nadat u het profiel hebt gemaakt en serienummers hebt toegewezen, moet u het profiel als URL of als bestand in de hieronder beschreven indeling exporteren uit Intune. Vervolgens importeert u het profiel handmatig in het Apple Configurator-programma op een Mac, waarna het profiel met het Apple Configurator-programma op de apparaten wordt geïmplementeerd.

### <a name="export-a-profile-using-setup-assistant-enrollment"></a>Een profiel exporteren met inschrijving via Configuratieassistent

1. Kies in Azure Portal **Meer services** > **Bewaking en beheer** > **Intune**.

2. Kies het profiel dat u wilt exporteren op de blade **Apple Configurator-inschrijvingsprofielen**.

3. Selecteer **Profiel exporteren** op de blade voor het profiel.

4. Kopieer de URL van het profiel naar [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) terwijl het iOS-apparaat is aangesloten. U zult deze later in Apple Configurator uploaden om het Intune-profiel te definiëren dat wordt gebruikt door iOS-apparaten.

  Voor ondersteuning van Apple Configurator 2 moet u de profiel-URL 2.0 bewerken. Als u dit wilt doen, vervangt u deze code:
    ```
    https://manage.microsoft.com/EnrollmentServer/Discovery.svc/iOS/ESProxy?id=
    ```
    Door deze code:

    ```
    https://appleconfigurator2.manage.microsoft.com/MDMServiceConfig?id=
    ```

   In de volgende procedure gaat u deze profiel-URL met Apple Configurator uploaden naar de Apple DEP-service om het Intune-profiel te definiëren dat door iOS-apparaten wordt gebruikt.

5. Upload deze profiel-URL met Apple Configurator naar de Apple DEP-service om het Intune-profiel te definiëren dat door iOS-apparaten wordt gebruikt.


    1.  Open **Apple Configurator2** op een Mac-computer. Kies in de menubalk **Apple Configurator 2** en vervolgens **Voorkeuren**.

         > [!WARNING]
         > De apparaten worden tijdens het inschrijvingsproces opnieuw ingesteld op de fabrieksconfiguraties. U kunt het apparaat het beste opnieuw instellen en inschakelen. U moet het apparaat verbinden wanneer het scherm **Hallo** wordt weergegeven.

    2. Selecteer **Servers** in het deelvenster met **voorkeuren** en kies het plusteken (+) om de wizard voor de MDM-server te starten. Kies **Volgende**.

    3. Voer de **naam** en de **inschrijvings-URL** in voor de MDM-server uit stap 6 in 'iOS-apparaten inschrijven via Configuratieassistent in Microsoft Intune'. Voer voor de inschrijvings-URL de profiel-URL voor inschrijving in die u hebt geëxporteerd uit Intune. Kies **Volgende**.  

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

## <a name="how-users-install-and-use-the-company-portal-on-their-devices"></a>Hoe gebruikers de bedrijfsportal op hun apparaten installeren en gebruiken

Op apparaten die zijn geconfigureerd met gebruikersaffiniteit kan de bedrijfsportal-app worden geïnstalleerd en uitgevoerd om apps te downloaden en apparaten te beheren. Nadat gebruikers hun apparaten hebben ontvangen, moeten zij de onderstaande extra stappen uitvoeren om Configuratieassistent te voltooien en de bedrijfsportal-app te installeren.

### <a name="how-users-enroll-corporate-owned-ios-devices-with-user-affinity"></a>iOS-apparaten in bedrijfseigendom inschrijven met gebruikersaffiniteit

1. Wanneer gebruikers hun apparaat inschakelen, wordt ze gevraagd de Configuratieassistent te voltooien. Tijdens de installatie wordt er naar de referenties van de gebruikers gevraagd. Ze moeten de referenties (de unieke naam of de UPN) van het Intune-abonnement gebruiken.

2. Tijdens de installatie wordt er naar de Apple ID van de gebruikers gevraagd. Er moet een Apple ID worden opgegeven zodat de bedrijfsportal op het apparaat kan worden geïnstalleerd. Ze kunnen ook de id in het iOS-instellingenmenu opgeven nadat de installatie is voltooid.

3. Nadat het instellen is voltooid, moet de bedrijfsportal-app op het iOS-apparaat worden geïnstalleerd vanuit de App Store.

4. De gebruiker kan zich nu aanmelden bij de bedrijfsportal met behulp van de UPN die is gebruikt bij het instellen van het apparaat.

5. Na het aanmelden wordt gebruikers gevraagd hun apparaat in te schrijven. De eerste stap is het identificeren van het apparaat. De app geeft een lijst met iOS-apparaten weer die al voor het bedrijf zijn ingeschreven en zijn toegewezen aan het Intune-account van de eindgebruiker. De gebruiker moet het desbetreffende apparaat kiezen. Als dit apparaat nog niet voor het bedrijf is ingeschreven, moeten ze 'nieuw apparaat' kiezen om door te gaan met de standaardinschrijving.

6. In het volgende scherm moeten gebruikers het serienummer van het nieuwe apparaat bevestigen. Gebruikers kunnen op de koppeling Bevestig het serienummer tikken om de app Instellingen te starten, waarmee het serienummer wordt geverifieerd. Gebruikers moeten vervolgens de laatste vier tekens van het serienummer invoeren in de bedrijfsportal-app.

    Met deze stap wordt gecontroleerd of het apparaat het bedrijfsapparaat is dat is ingeschreven in Intune. Als het serienummer op het apparaat niet overeenkomt, is het verkeerde apparaat geselecteerd. De gebruiker moet teruggaan naar het vorige scherm en een ander apparaat selecteren.

7. Wanneer het serienummer is geverifieerd, wordt de gebruiker door de bedrijfsportal-app omgeleid naar de website van de bedrijfsportal om de inschrijving te voltooien. Vervolgens wordt gebruikers gevraagd om terug te gaan naar de app.

De inschrijving is nu voltooid en gebruikers kunnen dit apparaat nu gebruiken met de volledige set mogelijkheden.

