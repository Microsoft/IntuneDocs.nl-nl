---
title: iOS-apparaten inschrijven - Device Enrollment Program | Intune Azure Preview | Microsoft Docs
description: 'Intune Azure Preview: in dit onderwerp leest u hoe u iOS-apparaten in bedrijfseigendom kunt inschrijven met het Device Enrollment Program.'
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7981a9c0-168e-4c54-9afd-ac51e895042c
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 08dad848a48adad7d9c6f0b5b3286f6550a266bd
ms.openlocfilehash: da6d377c94ce5db7bbfa1cb3fc165581d649a1fb
ms.lasthandoff: 02/15/2017


---

# <a name="enroll-ios-devices-using-device-enrollment-program"></a>iOS-apparaten inschrijven met het Device Enrollment Program

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Microsoft Intune kan 'draadloos' een inschrijvingsprofiel implementeren op iOS-apparaten die via het Device Enrollment Program zijn aangeschaft. Een profiel bevat de beheerinstellingen die u op apparaten wilt toepassen. Het inschrijvingspakket kan Configuratieassistent-opties voor het apparaat bevatten. Gebruikers kunnen de inschrijving niet opheffen wanneer de apparaten zijn ingeschreven via DEP.

>[!NOTE]
>Deze inschrijvingsmethode kan niet worden gebruikt met de methode [Apparaatinschrijvingsmanager](enroll-devices-using-device-enrollment-manager.md).

Voor het beheren van iOS-apparaten in bedrijfseigendom met het Device Enrollment Program (DEP) van Apple moet uw organisatie lid worden van DEP en apparaten verwerven via dat programma. Details van dit proces kunt u vinden op: [https://deploy.apple.com](https://deploy.apple.com). Voordelen van het programma zijn onder andere handsfree instellen, dus zonder dat elk apparaat via een USB-verbinding op een computer moet worden aangesloten.

Voordat u iOS-apparaten in bedrijfseigendom met DEP kunt inschrijven, moet u [een DEP-token ontvangen](get-apple-dep-token.md) van Apple. Intune kan met dit token informatie synchroniseren over apparaten binnen uw bedrijf die aan DEP deelnemen. Ook kan Intune hiermee inschrijvingsprofielen naar Apple uploaden en apparaten toewijzen aan die profielen.

Andere methoden voor het registreren van iOS-apparaten worden beschreven in [Choose how to enroll iOS devices in Intune](choose-ios-enrollment-method.md) (Kiezen hoe iOS-apparaten worden geregistreerd in Intune).

## <a name="prerequisites"></a>Vereisten

Voer de volgende vereisten uit voordat u inschrijving van iOS-apparaten instelt:

- [Domeinen configureren](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-2)
- [MDM-instantie instellen](set-mdm-authority.md)
- [Groepen maken](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-5)
- Gebruikerslicenties toewijzen in de [Office 365-portal](http://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Een Apple MDM-pushcertificaat ophalen](get-an-apple-mdm-push-certificate.md)
- [Een Apple DEP-token ophalen](get-apple-dep-token.md)

## <a name="create-an-apple-dep-profile-for-devices"></a>Een Apple DEP-profiel maken voor apparaten

Met een inschrijvingsprofiel voor apparaten worden de instellingen gedefinieerd die worden toegepast op een groep apparaten. De volgende stappen laten zien hoe u een apparaatinschrijvingsprofiel kunt maken voor iOS-apparaten die worden ingeschreven met DEP.

1. Kies in Azure Portal **Meer services** > **Bewaking en beheer** > **Intune**.

2. Kies **Apparaten inschrijven** op de blade Intune en kies vervolgens **Apple-inschrijving**.

3. Selecteer **DEP-profielen** onder **Instellingen van Apple Device Enrollment Program (DEP) beheren**.

4. Selecteer **Maken** op de blade **Apple DEP-profielen**.

5. Voer op de blade **Inschrijvingsprofiel maken** een naam en een beschrijving in voor het profiel.

6. Geef voor **Gebruikersaffiniteit** aan of u andere apparaten met dit profiel wilt inschrijven met of zonder gebruikersaffiniteit.

 - **Inschrijven met gebruikersaffiniteit**: het apparaat moet aan een gebruiker worden gekoppeld tijdens de eerste configuratie en kan vervolgens toegang krijgen tot gegevens en e-mail van het bedrijf. Kies gebruikersaffiniteit voor DEP-beheerde apparaten die eigendom zijn van gebruikers en waarvoor de bedrijfsportal moet worden gebruikt voor services als het installeren van apps. Houd er rekening mee dat Multi-Factor Authentication (MFA) niet werkt tijdens inschrijving op DEP-apparaten met gebruikersaffiniteit. Na de inschrijving werkt MFA zoals verwacht op deze apparaten.

    >[!NOTE]
    >Voor DEP met gebruikersaffiniteit moet WS-Trust 1.3 gebruikersnaam/mixed-eindpunt zijn ingeschakeld om een gebruikerstoken aan te vragen.

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

1. Ga naar de [Device Enrollment Program-portal](https://deploy.apple.com) (https://deploy.apple.com) en meld u aan met de Apple-id van uw bedrijf. 

2. Ga naar **Implementatieprogramma** &gt; **Programma apparaatinschrijving** &gt; **Apparaten beheren**. 

3. Geef een manier op voor **Apparaten kiezen**, voer de apparaatgegevens in en geef details op aan de hand van **serienummer** en **bestelnummer** of voer **CSV-bestand uploaden** uit. 

4. Selecteer **Toewijzen aan server**, kies de &lt;Servernaam&gt; die is opgegeven voor Microsoft Intune en kies vervolgens **OK**.

## <a name="synchronize-dep-managed-devices"></a>Met DEP-beheerde apparaten synchroniseren

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

## <a name="distribute-devices-to-users"></a>Apparaten onder gebruikers distribueren

U kunt apparaten in bedrijfseigendom nu distribueren aan gebruikers. Wanneer een iOS-apparaat wordt ingeschakeld, wordt dit ingeschreven voor beheer door Intune.


## <a name="how-users-install-and-use-the-company-portal-on-their-devices"></a>Hoe gebruikers de bedrijfsportal op hun apparaten installeren en gebruiken

Op apparaten die zijn geconfigureerd met gebruikersaffiniteit kan de bedrijfsportal-app worden geïnstalleerd en uitgevoerd om apps te downloaden en apparaten te beheren. Nadat gebruikers hun apparaten hebben ontvangen, moeten zij de onderstaande extra stappen uitvoeren om Configuratieassistent te voltooien en de bedrijfsportal-app te installeren.

### <a name="how-users-enroll-corporate-owned-ios-devices-with-user-affinity"></a>iOS-apparaten in bedrijfseigendom inschrijven met gebruikersaffiniteit 

1. Wanneer gebruikers hun apparaat inschakelen, wordt ze gevraagd de Configuratieassistent te voltooien. Tijdens de installatie wordt er naar de referenties van de gebruikers gevraagd. Ze moeten de referenties (de unieke naam of de UPN) van het Intune-abonnement gebruiken.

2. Tijdens de installatie wordt er naar de Apple ID van de gebruikers gevraagd. Er moet een Apple ID worden opgegeven zodat de bedrijfsportal op het apparaat kan worden geïnstalleerd. Ze kunnen ook de id in het iOS-instellingenmenu opgeven nadat de installatie is voltooid.

3. Nadat het instellen is voltooid, moeten gebruikers de bedrijfsportal-app vanuit de App Store installeren.

4. Gebruikers kunnen zich nu aanmelden bij de bedrijfsportal met behulp van de UPN die is gebruikt bij het instellen van het apparaat.

5. Na het aanmelden wordt gebruikers gevraagd hun apparaat in te schrijven. De eerste stap is het identificeren van het apparaat. De app geeft een lijst met iOS-apparaten weer die al voor het bedrijf zijn ingeschreven en zijn toegewezen aan het Intune-account van de eindgebruiker. De gebruiker moet het desbetreffende apparaat kiezen. Als dit apparaat nog niet voor het bedrijf is ingeschreven, moeten ze 'nieuw apparaat' kiezen om door te gaan met de standaardinschrijving.

6. In het volgende scherm moeten gebruikers het serienummer van het nieuwe apparaat bevestigen. Hiervoor moeten ze de weergegeven koppeling selecteren. Hiermee wordt de app Instellingen gestart, waarmee gebruikers hun serienummer kunnen controleren. Gebruikers moeten vervolgens de laatste vier tekens van het serienummer invoeren in de bedrijfsportal-app.

   Met deze stap wordt gecontroleerd of het apparaat het bedrijfsapparaat is dat is ingeschreven in Intune. Als het serienummer op het apparaat niet overeenkomt, heeft de gebruiker het verkeerde apparaat geselecteerd. De gebruiker moet teruggaan naar het vorige scherm en een ander apparaat selecteren.

7. Wanneer het serienummer is geverifieerd, wordt de gebruiker door de bedrijfsportal-app omgeleid naar de website van de bedrijfsportal om de inschrijving te voltooien. Vervolgens wordt gebruikers gevraagd om terug te gaan naar de app.

De inschrijving is nu voltooid en gebruikers kunnen dit apparaat nu gebruiken met de volledige set mogelijkheden.

