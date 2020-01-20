---
title: Beveiligingsbeleid voor apps maken en implementeren
titleSuffix: Microsoft Intune
description: In dit onderwerp wordt beschreven hoe app-beveiligingsbeleid (APP) van Microsoft Intune wordt gemaakt en toegewezen.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/26/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: f31b2964-e932-4cee-95c4-8d5506966c85
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9b5f973e5ce169edcf6149b0588c905d8497cca2
ms.sourcegitcommit: 2506cdbfccefd42587a76f14ee50c3849dad1708
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/11/2020
ms.locfileid: "75885744"
---
# <a name="how-to-create-and-assign-app-protection-policies"></a>App-beveiligingsbeleid maken en toewijzen

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Meer informatie over het maken en toewijzen van app-beveiligingsbeleid (APP) van Microsoft Intune aan gebruikers van uw organisatie. Dit onderwerp beschrijft ook hoe u wijzigingen aanbrengt in bestaande beleidsregels.

## <a name="before-you-begin"></a>Voordat u begint

App-beveiligingsbeleid kan van toepassing zijn op apps die worden uitgevoerd op apparaten die al dan niet door Intune worden beheerd. Voor een gedetailleerde beschrijving van de werking van het app-beveiligingsbeleid en de scenario's die worden ondersteund door het app-beveiligingsbeleid van Intune ziet u [Wat zijn app-beveiligingsbeleidsregels van Microsoft Intune?](app-protection-policy.md)

Zie [MAM apps list (MAM-app-lijst)](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) voor een lijst met ondersteunde MAM-apps.

Zie [Add apps to Microsoft Intune](apps-add.md) (Apps toevoegen aan Microsoft Intune) voor informatie over het toevoegen van LOB-apps (Line-Of-Business) aan Microsoft Intune in voorbereiding op app-beveiligingsbeleid.

## <a name="app-protection-policies-for-iosipados-and-android-apps"></a>Beveiligingsbeleid voor apps voor iOS/iPadOS- en Android-apps

Wanneer u een app-beveiligingsbeleid maakt voor iOS/iPadOS- en Android-apps, volgt u een moderne Intune-processtroom die resulteert in een nieuw beveiligingsbeleid voor apps.

### <a name="create-an-iosipados-or-android-app-protection-policy"></a>Een beveiligingsbeleid voor iOS/iPadOS- of Android-apps maken
1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Kies in de Intune-portal **Apps** > **App-beveiligingsbeleid**. Hiermee opent u de details van het **App-beveiligingsbeleid**, waar u nieuw beleid kunt maken en bestaande beleidsregels kunt bewerken.
3. Selecteer **Beleid maken** en selecteer **iOS/iPadOS** of **Android**. Het deelvenster **Beleid maken** wordt weergegeven.
4. Voeg op de pagina **Basisinformatie** de volgende waarden toe:

    | Waarde | Beschrijving |
    |--------------|------------------------------------------------|
    | Naam | De naam van dit app-beveiligingsbeleid. |
    | Beschrijving | [Optioneel] De beschrijving van dit app-beveiligingsbeleid. |


    De waarde **Platform** wordt ingesteld op basis van de bovenstaande keuze.

    ![Schermopname van de pagina Basisinformatie van het deelvenster Beleid maken](~/apps/media/app-protection-policies/app-protection-add-policies-01.png)

5. Klik op **Volgende** om de pagina **Apps** weer te geven.<br>
    Op de pagina **Apps** kunt u kiezen hoe u dit beleid wilt toepassen op apps op verschillende apparaten. U moet minstens één app toevoegen.<p>
    
    | Waarde/optie | Beschrijving |
    |-------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | Toepassen op apps op alle apparaattypen | Gebruik deze optie om uw beleid te richten op apps op apparaten met een beheerstatus. Kies **Nee** om toe te passen op specifieke apparaattypen. Zie [Beleidsregels voor app-beveiliging toepassen op basis van de apparaatbeheerstatus](#target-app-protection-policies-based-on-device-management-state) voor informatie |
    |     Apparaattypen | Gebruik deze optie om op te geven of dit beleid van toepassing is op door MDM beheerde apparaten of op onbeheerde apparaten. Voor iOS-APP-beleid selecteert u **Niet-beheerde** en **Beheerde** apparaten. Voor Android-APP-beleid maakt u een keuze uit **Niet-beheerd**, **Android-apparaatbeheerder** en **Android Enterprise**.  |
    | Openbare apps | Klik op **Openbare apps selecteren** om de apps te selecteren waarop u het wilt toepassen. |
    | Aangepaste apps | Klik op **Aangepaste apps selecteren** om aangepaste apps te selecteren op basis van een bundel-id. |
    
    De app(s) die u hebt geselecteerd, worden weergegeven in de lijst met openbare en aangepaste apps. 
6. Klik op **Volgende** om de pagina **Gegevensbescherming** weer te geven.<br>
    Deze pagina bevat de DLP-besturingselementen voor preventie van gegevensverlies, inclusief knippen, kopiëren, plakken en beperkingen voor opslaan als. Met deze instellingen bepaalt u hoe gebruikers kunnen werken met gegevens in de apps waarop dit app-beveiligingsbeleid van toepassing is.

    **Instellingen voor gegevensbeveiliging**:<br>
    - **iOS/iPadOS-gegevensbeveiliging**: raadpleeg [Beveiligingsbeleidsinstellingen voor iOS-apps](~/apps/app-protection-policy-settings-ios.md#data-protection) voor informatie.
    - **Android-gegevensbeveiliging**: raadpleeg [Beveiligingsbeleidsinstellingen voor Android-apps](~/apps/app-protection-policy-settings-android.md#data-protection) voor informatie.

7. Klik op **Volgende** om de pagina **Toegangsvereisten** weer te geven.<br>
    Deze pagina bevat instellingen waarmee u de pincode en referentievereisten kunt configureren waaraan gebruikers moeten voldoen om toegang te krijgen tot apps in een werkcontext. 
 
    **Instellingen voor toegangsvereisten**:<br>
    - **Toegangsvereisten voor iOS/iPadOS**: raadpleeg [Beveiligingsbeleidsinstellingen voor iOS-apps - Toegangsvereisten](~/apps/app-protection-policy-settings-ios.md#access-requirements) voor informatie.
    - **Toegangsvereisten voor Android**: raadpleeg [Beveiligingsbeleidsinstellingen voor Android-apps - Toegangsvereisten](~/apps/app-protection-policy-settings-android.md#access-requirements) voor informatie.

8. Klik op **Volgende** om de pagina **Voorwaardelijke start** weer te geven.<br>
    Op deze pagina vindt u instellingen om beveiligingsvereisten voor aanmelden in te stellen voor toegangsbeveiligingsbeleid. Selecteer een **instelling** en voer de **waarde** in waaraan gebruikers moeten voldoen om zich aan te melden bij uw bedrijfsapp. Selecteer vervolgens de **actie** die u wilt uitvoeren als gebruikers niet voldoen aan uw vereisten. In sommige gevallen kunnen meerdere acties worden geconfigureerd voor één instelling.

    **Instellingen voor voorwaardelijk start**:<br>
    - **iOS/iPadOS voorwaardelijke start**: raadpleeg [Beveiligingsbeleidsinstellingen voor iOS-apps - Voorwaardelijke start](~/apps/app-protection-policy-settings-ios.md#conditional-launch) voor informatie.
    - **Android voorwaardelijke start**: raadpleeg [Beveiligingsbeleidsinstellingen voor Android-apps - Voorwaardelijke start](~/apps/app-protection-policy-settings-android.md#conditional-launch) voor informatie.

9. Klik op **Volgende** om de pagina **Toewijzingen** weer te geven.<br>
   Op de pagina **Toewijzingen** kunt u het beveiligingsbeleid voor apps toewijzen aan groepen gebruikers.

10. Klik op **Volgende: Beoordelen en maken** om de waarden en instellingen te bekijken die u hebt ingevoerd voor dit app-beveiligingsbeleid.

11. Wanneer u klaar bent, klikt u op **Maken** om het app-beveiligingsbeleid in Intune te maken. 

    > [!TIP]
    > Deze beleidsinstellingen worden alleen afgedwongen wanneer u apps in de context van het werk gebruikt. Als eindgebruikers de app gebruiken voor een privétaak, worden deze beleidsregels niet toegepast. Let op: wanneer u een nieuw bestand maakt, wordt dit als een privébestand beschouwd. 

Eindgebruikers kunnen de apps downloaden in de App Store of via Google Play. Zie voor meer informatie:
* [Wat u kunt verwachten wanneer uw Android-app wordt beheerd door een app-beveiligingsbeleid](../fundamentals/end-user-mam-apps-android.md)
* [Wat u kunt verwachten wanneer uw iOS-app wordt beheerd door een app-beveiligingsbeleid](../fundamentals/end-user-mam-apps-ios.md)

## <a name="change-existing-policies"></a>Bestaande beleidsregels wijzigen
U kunt een bestaand beleid bewerken en toepassen op de beoogde gebruikers. Wanneer u echter bestaand beleid wijzigt, worden de wijzigingen pas na 8 uur zichtbaar voor gebruikers die al bij de apps zijn aangemeld.

Om het effect van de wijzigingen onmiddellijk te zien, moet de eindgebruiker zich afmelden bij de app en zich daarna opnieuw aanmelden.

### <a name="to-change-the-list-of-apps-associated-with-the-policy"></a>De lijst met aan het beleid gekoppelde apps wijzigen

1. Selecteer het beleid dat u wilt wijzigen op de blade **App-beveiligingsbeleid**.

2. Selecteer **Eigenschappen**in het deelvenster *Intune-app-beveiliging*.

3. Selecteer **Bewerken** naast de sectie *Apps*.

4. Op de pagina **Apps** kunt u kiezen hoe u dit beleid wilt toepassen op apps op verschillende apparaten. U moet minstens één app toevoegen.<p>
    
    | Waarde/optie | Beschrijving |
    |-------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | Toepassen op apps op alle apparaattypen | Gebruik deze optie om uw beleid te richten op apps op apparaten met een beheerstatus. Kies **Nee** om toe te passen op specifieke apparaattypen. Zie [Beleidsregels voor app-beveiliging toepassen op basis van de apparaatbeheerstatus](#target-app-protection-policies-based-on-device-management-state) voor informatie |
    |     Apparaattypen | Gebruik deze optie om op te geven of dit beleid van toepassing is op door MDM beheerde apparaten of op onbeheerde apparaten. Voor iOS-APP-beleid selecteert u **Niet-beheerde** en **Beheerde** apparaten. Voor Android-APP-beleid maakt u een keuze uit **Niet-beheerd**, **Android-apparaatbeheerder** en **Android Enterprise**.  |
    | Openbare apps | Klik op **Openbare apps selecteren** om de apps te selecteren waarop u het wilt toepassen. |
    | Aangepaste apps | Klik op **Aangepaste apps selecteren** om aangepaste apps te selecteren op basis van een bundel-id. |

    De app(s) die u hebt geselecteerd, worden weergegeven in de lijst met openbare en aangepaste apps. 

5. Klik op **Beoordelen en maken** om de apps te controleren die zijn geselecteerd voor dit beleid.

6. Wanneer u klaar bent, klikt u op **Opslaan** om het app-beveiligingsbeleid bij te werken.
 
#### <a name="to-change-the-list-of-user-groups"></a>De lijst met gebruikersgroepen wijzigen

1. Selecteer het beleid dat u wilt wijzigen op de blade **App-beveiligingsbeleid**.

2. Selecteer **Eigenschappen**in het deelvenster *Intune-app-beveiliging*.

3. Selecteer **Bewerken** naast de sectie *Toewijzingen*.

4. Als u een nieuwe gebruikersgroep wilt toevoegen aan het beleid op het tabblad *Opnemen* kiest u **Selecteer groepen om op te nemen** en selecteert u de gebruikersgroep. Kies **Selecteren** om de groep toe te voegen. 

5. Als u een gebruikersgroep wilt uitsluiten, kiest u op het tabblad *Uitsluiten* de optie **Groepen selecteren voor uitsluiten**, en selecteert u de gebruikersgroep. Kies **Selecteren** om de gebruikersgroep te verwijderen.  

6. Als u groepen wilt verwijderen die eerder zijn toegevoegd, selecteert u op het tabblad *Opnemen* of op het tabblad *Uitsluiten* het weglatingsteken (...) en selecteert u **Verwijderen**.

7. Klik op **Beoordelen en maken** om de gebruikersgroepen te controleren die zijn geselecteerd voor dit beleid.

8. Als uw wijzigingen aan de toewijzingen gereed zijn, selecteert u **Opslaan** om de configuratie op te slaan en implementeert u het beleid voor de nieuwe groep gebruikers. Als u **Annuleren** selecteert vóórdat u de configuratie opslaat, worden alle wijzigingen verwijderd die u hebt aangebracht op de tabbladen *Opnemen* en *Uitsluiten*.

### <a name="to-change-policy-settings"></a>Beleidsinstellingen wijzigen

1. Selecteer het beleid dat u wilt wijzigen op de blade **App-beveiligingsbeleid**.

2. Selecteer **Eigenschappen**in het deelvenster *Intune-app-beveiliging*.

3. Selecteer **Bewerken** naast de sectie die overeenkomt met de instellingen die u wilt wijzigen. Wijzig de instellingen vervolgens in nieuwe waarden.

7. Klik op **Beoordelen en maken** om de bijgewerkte instellingen voor dit beleid te controleren.

4. Selecteer **Opslaan** om uw wijzigingen op te slaan. Herhaal de procedure voor het selecteren van een instellingsgebied en breng uw wijzigingen. Sla vervolgens uw wijzigingen op totdat alle wijzigingen zijn voltooid. U kunt het deelvenster *Intune-app-beveiliging* dan sluiten. 

## <a name="target-app-protection-policies-based-on-device-management-state"></a>Beleidsregels voor app-beveiliging toepassen op basis van de apparaatbeheerstatus
In veel organisaties is het gebruikelijk dat eindgebruikers gebruik mogen maken van via Intune MDM (Mobile Device Management) beheerde apparaten zoals apparaten in eigendom van het bedrijf, en van niet-beheerde apparaten die alleen door Intune-app-beveiligingsbeleid worden beschermd. Niet-beheerde apparaten zijn vaak bekend onder de naam BYOD-apparaten (Bring Your Own).

Omdat Intune-app-beveiligingsbeleid op de identiteit van een gebruiker is gericht, worden de beveiligingsinstellingen voor een gebruiker op zowel ingeschreven (via MDM beheerde) als niet-ingeschreven apparaten (geen MDM) toegepast. Daarom kunt u Intune-app-beveiligingsbeleid richten op ofwel in Intune ingeschreven apparaten of iOS- en Android-apparaten waarvan de registratie ongedaan is gemaakt. U mag één beveiligingsbeleid voor niet-beheerde apparaten hebben waarin strenge DLP-besturingselementen voor preventie van gegevensverlies zijn toegepast, en een afzonderlijk beveiligingsbeleid voor via MDM beheerde apparaten waarbij minder strenge DLP-besturingselementen mogelijk zijn. Zie [App-beveiligingsbeleid en werkprofielen](android-deployment-scenarios-app-protection-work-profiles.md) voor meer informatie over hoe dit werkt op persoonlijke Android Enterprise-apparaten.

Voor het maken van deze beleidsregels bladert u naar **Apps** > **App-beveiliging** in de Intune-console en selecteert u **Beleid maken**. U kunt ook een bestaand app-beveiligingsbeleid bewerken. Als u het app-beveiligingsbeleid op zowel beheerde als niet-beheerde apparaten wilt toepassen, gaat u naar de pagina **Apps** en bevestigt u dat **Toepassen op apps op alle apparaattypen** is ingesteld op **Ja**, de standaardwaarde. Als u granulair wilt toewijzen op basis van de beheerstatus, stelt u **Toepassen op apps op alle apparaattypen** in op **Nee**. 

### <a name="device-types"></a>Apparaattypen

- **Onbeheerd**: Niet-beheerde apparaten zijn apparaten waarop Intune MDM niet is gedetecteerd. Dit omvat apparaten die worden beheerd door andere MDM-leveranciers.
- **Door Intune beheerde apparaten**: Beheerde apparaten worden beheerd door Intune MDM.
- **Android-apparaatbeheerder**: Door Intune beheerde apparaten met de Android Device Administration-API.
- **Android Enterprise**: Door Intune beheerde apparaten met Android Enterprise-werkprofielen of volledig apparaatbeheer van Android Enterprise.

> [!NOTE]
> Op Android-apparaten wordt gevraagd of de Intune-bedrijfsportal-app moet worden geïnstalleerd, ongeacht welk apparaattype is gekozen. Als u bijvoorbeeld 'Android Enterprise ' selecteert, wordt deze vraag toch gesteld aan gebruikers met niet-beheerde Android-apparaten.

Voor iOS zijn extra app-configuratie-instellingen vereist om APP-instellingen (beveiligingsbeleid voor apps) te richten op apps op apparaten die zijn ingeschreven bij Intune:

- **IntuneMAMUPN** moet zijn geconfigureerd voor alle met MDM beheerde toepassingen. Zie [Gegevensoverdracht beheren tussen iOS-apps met Microsoft Intune](data-transfer-between-apps-manage-ios.md#configure-user-upn-setting-for-microsoft-intune-or-third-party-emm) voor meer informatie.
- **IntuneMAMDeviceID** moet zijn geconfigureerd voor alle door derden en met line-of-business MDM beheerde toepassingen. **IntuneMAMDeviceID** moet zijn geconfigureerd voor het apparaat-id-token. Bijvoorbeeld `key=IntuneMAMDeviceID, value={{deviceID}}`. Zie [App-configuratiebeleidsregels toevoegen voor beheerde iOS-apparaten](app-configuration-policies-use-ios.md) voor meer informatie.
- Als alleen de **IntuneMAMDeviceID** is geconfigureerd, wordt het apparaat in Intune APP beschouwd als niet-beheerd.

> [!NOTE]
> Zie [MAM-beveiligingsbeleid toepassen op basis van beheerstatus](../fundamentals/whats-new-archive.md#mam-protection-policies-targeted-based-on-management-state) voor specifieke iOS-ondersteuningsinformatie over app-beveiligingsbeleid op basis van de apparaatbeheerstatus.

## <a name="policy-settings"></a>Beleidsinstellingen
Selecteer een van de volgende links voor een volledig overzicht van de beleidsinstellingen voor iOS en Android:

- [iOS-beleid](app-protection-policy-settings-ios.md)
- [Android-beleid](app-protection-policy-settings-android.md)

## <a name="next-steps"></a>Volgende stappen
[Compatibiliteit- en gebruikersstatus controleren](app-protection-policies-monitor.md)

## <a name="see-also"></a>Zie tevens
* [Wat u kunt verwachten wanneer uw Android-app wordt beheerd door een app-beveiligingsbeleid](../fundamentals/end-user-mam-apps-android.md)
* [Wat u kunt verwachten wanneer uw iOS-app wordt beheerd door een app-beveiligingsbeleid](../fundamentals/end-user-mam-apps-ios.md)
