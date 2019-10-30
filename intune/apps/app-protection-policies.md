---
title: Beveiligingsbeleid voor apps maken en implementeren
titleSuffix: Microsoft Intune
description: In dit onderwerp wordt beschreven hoe app-beveiligingsbeleid (APP) van Microsoft Intune wordt gemaakt en toegewezen.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/16/2019
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
ms.openlocfilehash: a8e105dae43c4e7139c8e44a8c6535baebe31cc4
ms.sourcegitcommit: 0be25b59c8e386f972a855712fc6ec3deccede86
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/18/2019
ms.locfileid: "72585484"
---
# <a name="how-to-create-and-assign-app-protection-policies"></a>App-beveiligingsbeleid maken en toewijzen

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Meer informatie over het maken en toewijzen van app-beveiligingsbeleid (APP) van Microsoft Intune aan gebruikers van uw organisatie. Dit onderwerp beschrijft ook hoe u wijzigingen aanbrengt in bestaande beleidsregels.

## <a name="before-you-begin"></a>Voordat u begint

App-beveiligingsbeleid kan van toepassing zijn op apps die worden uitgevoerd op apparaten die al dan niet door Intune worden beheerd. Voor een gedetailleerde beschrijving van de werking van het app-beveiligingsbeleid en de scenario's die worden ondersteund door het app-beveiligingsbeleid van Intune ziet u [Wat zijn app-beveiligingsbeleidsregels van Microsoft Intune?](app-protection-policy.md)

Zie [MAM apps list (MAM-app-lijst)](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) voor een lijst met ondersteunde MAM-apps.

Zie [Add apps to Microsoft Intune](apps-add.md) (Apps toevoegen aan Microsoft Intune) voor informatie over het toevoegen van LOB-apps (Line-Of-Business) aan Microsoft Intune in voorbereiding op app-beveiligingsbeleid.

Momenteel is de processtroom voor het maken van een beveiligingsbeleid voor apps afhankelijk van het platform:
- Beveiligingsbeleid voor apps voor iOS/iPadOS- en Android-apps
- Beveiligingsbeleid voor Windows 10-apps

## <a name="app-protection-policies-for-iosipados-and-android-apps"></a>Beveiligingsbeleid voor apps voor iOS/iPadOS- en Android-apps

Wanneer u een app-beveiligingsbeleid maakt voor iOS/iPadOS- en Android-apps, volgt u een moderne Intune-processtroom die resulteert in een nieuw beveiligingsbeleid voor apps.

### <a name="create-an-iosipados-or-android-app-protection-policy"></a>Een beveiligingsbeleid voor iOS/iPadOS- of Android-apps maken
1. Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Kies in de Intune-portal **Client-apps** > **App-beveiligingsbeleid**. Hiermee opent u de details van het **App-beveiligingsbeleid**, waar u nieuw beleid kunt maken en bestaande beleidsregels kunt bewerken.
3. Selecteer **Beleid maken** en selecteer **iOS/iPadOS** of **Android**. De blade **Beleid maken** wordt weergegeven.
4. Voeg op de pagina **Basisinformatie** de volgende waarden toe:

    | Waarde | Beschrijving |
    |--------------|------------------------------------------------|
    | Naam | De naam van dit app-beveiligingsbeleid. |
    | Beschrijving | [Optioneel] De beschrijving van dit app-beveiligingsbeleid. |


    De waarde **Platform** wordt ingesteld op basis van de bovenstaande keuze.

    ![Schermopname van de pagina Basisinformatie van de blade Beleid maken](~/apps/media/app-protection-policies/app-protection-add-policies-01.png)

5. Klik op **Volgende** om de pagina **Apps** weer te geven.<br>
    Op de pagina **Apps** kunt u kiezen hoe u dit beleid wilt toepassen op apps op verschillende apparaten. U moet minstens één app toevoegen.<p>
    
    | Waarde/optie | Beschrijving |
    |-------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | Toepassen op apps op alle apparaattypen | Gebruik deze optie om uw beleid te richten op apps op apparaten met een beheerstatus. Kies **Nee** om toe te passen op specifieke apparaattypen. |
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

7. Klik op **Volgende** om de pagina **Toewijzingen** weer te geven.<br>
   Op de pagina **Toewijzingen** kunt u het beveiligingsbeleid voor apps toewijzen aan groepen gebruikers. 
8. Klik op **Volgende: Beoordelen en maken** om de waarden en instellingen te bekijken die u hebt ingevoerd voor dit app-beveiligingsbeleid.
9. Wanneer u klaar bent, klikt u op **Maken** om het app-beveiligingsbeleid in Intune te maken. 

## <a name="app-protection-policies-for-windows-10-apps"></a>Beveiligingsbeleid voor Windows 10-apps

Wanneer u een app-beveiligingsbeleid maakt voor Windows 10-apps, volgt u een klassieke Intune-processtroom.

### <a name="create-a-windows-10-app-protection-policy"></a>Een Windows 10-beveiligingsbeleid voor apps maken
1. Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Kies in de Intune-portal **Client-apps** > **App-beveiligingsbeleid**. Hiermee opent u de details van het **App-beveiligingsbeleid**, waar u nieuw beleid kunt maken en bestaande beleidsregels kunt bewerken.
3. Selecteer **Beleid maken**.

    <img alt="Screenshot of the 'Create policy' blade for Windows 10" src="~/apps/media/app-protection-policies/app-protection-add-policy.png" width="350">

4. Geef een naam op voor het beleid, voeg een korte beschrijving toe en selecteer het platformtype voor uw beleid. U kunt meer dan één beleid voor elk platform maken.

4. U kunt **Toepassen op alle app-typen** kiezen. Met deze optie kunt u uw beleid richten op apps op apparaten met een beheerstatus. Tijdens het oplossen van beleidsconflicten wordt deze instelling vervangen als een gebruiker een beleid heeft dat is gericht op een specifieke beheerstatus. Zie [Beleidsregels voor app-beveiliging toepassen op basis van de apparaatbeheerstatus](~/apps/app-protection-policies.md#target-app-protection-policies-based-on-device-management-state) voor meer informatie.

5. Selecteer **Apps** om de blade **Apps** te openen, zodat er een lijst met beschikbare apps wordt weergegeven. U kunt een of meer apps in de lijst selecteren die u wilt koppelen aan het beleid dat u maakt. Selecteer minste één app om een beleid te maken.  

6. Wanneer u de apps hebt geselecteerd, kiest u **Selecteren** om uw selectie op te slaan.

7. Kies **Vereiste instellingen configureren** op de blade **Een beleid toevoegen** om **Instellingen** te openen.

   Er zijn drie soorten beleidsinstellingen:
   - **Gegevensbeveiliging**: deze groep bevat de DLP-besturingselementen voor preventie van gegevensverlies, zoals knippen, kopiëren, plakken en beperkingen voor opslaan als. Deze instellingen bepalen hoe gebruikers met gegevens in de apps kunnen werken.
   - **Toegangsvereisten**: deze groep bevat de pincodeopties per app die bepalen hoe de gebruiker toegang heeft tot de apps in een werkcontext.  
   - **Voorwaardelijk starten**: deze groep bevat instellingen zoals de minimale instellingen van het besturingssysteem, detectie van opengebroken of geroote apparaten en offline respijtperioden.

   Om u op gang te hepen, hebben de beleidsinstellingen standaardwaarden. U hoeft niets te wijzigen als de standaardwaarden aan uw vereisten voldoen.

   > [!TIP]
   > Deze beleidsinstellingen worden alleen afgedwongen wanneer u apps in de context van het werk gebruikt. Als eindgebruikers de app gebruiken voor een privétaak, worden deze beleidsregels niet toegepast. Let op: wanneer u een nieuw bestand maakt, wordt dit als een privébestand beschouwd. 

8. Selecteer **OK** om deze configuratie op te slaan. U bent nu terug in het deelvenster **Een beleid toevoegen**.
9. Selecteer **Maken** om het beleid te maken en uw instellingen op te slaan.

Nieuwe Windows 10-beleidsregels die u maakt, worden pas toegewezen aan gebruikers wanneer u dit expliciet doet. Raadpleeg [Een Windows 10-beleid toewijzen aan gebruikers](~/apps/app-protection-policies.md#assign-a-windows-10-policy-to-users) als u een Windows 10-beleid wilt toewijzen

### <a name="assign-a-windows-10-policy-to-users"></a>Een Windows 10-beleid toewijzen aan gebruikers 

1. Selecteer een beleid in het deelvenster **App-beveiligingsbeleid**.

2. Open in het deelvenster ***Intune-app-beveiliging** de optie **Toewijzingen** om het deelvenster **Intune-app-beveiliging - Toewijzingen** te openen. Selecteer op het tabblad *Opnemen* de optie **Groepen selecteren om op te nemen**. 

   ![Schermopname van het deelvenster Toewijzingen met het menu Groepen selecteren om op te nemen](./media/app-protection-policies/app-protection-policy-add-users.png)

3. Er wordt een lijst met alle beveiligingsgroepen in uw **Azure Active Directory** weergegeven. Selecteer de gebruikersgroepen waarop u dit beleid wilt toepassen en kies vervolgens **Selecteren**. 

    ![Schermopname van het deelvenster Gebruikersgroep toevoegen met een lijst met Azure AD-gebruikers](./media/app-protection-policies/azure-ad-user-group-list.png)

4. Nadat u groepen hebt opgenomen en uitgesloten, selecteert u **Opslaan** om de configuratie op te slaan en het beleid te implementeren voor gebruikers. Als u **Verwijderen** selecteert vóórdat u de configuratie opslaat, worden alle wijzigingen verwijderd die u hebt aangebracht op de tabbladen *Opnemen* en *Uitsluiten*.   
 
     ![Schermopname van de opties Opslaan en Verwijderen](./media/app-protection-policies/save-assignment.png)
  
U hebt nu beleid gemaakt en het beleid geïmplementeerd naar gebruikers.

Het beleid is alleen van invloed op gebruikers aan wie Microsoft Intune-licenties zijn toegewezen. Gebruikers in de geselecteerde beveiligingsgroep aan wie geen Intune-licentie is toegewezen, worden niet beïnvloed.

>[!IMPORTANT]
> Als u Intune met Configuration Manager gebruik om uw apparaten te beheren, wordt het beleid alleen direct op gebruikers in de geselecteerde groep toegepast. Leden van de onderliggende groepen binnen de geselecteerde groep worden niet door het beleid beïnvloed.

Eindgebruikers kunnen de apps downloaden in de App Store of via Google Play. Zie voor meer informatie:
* [Wat u kunt verwachten wanneer uw Android-app wordt beheerd door een app-beveiligingsbeleid](../fundamentals/end-user-mam-apps-android.md)
* [Wat u kunt verwachten wanneer uw iOS-app wordt beheerd door een app-beveiligingsbeleid](../fundamentals/end-user-mam-apps-ios.md)

### <a name="change-existing-windows-10-policies"></a>Bestaande Windows 10-beleidsregels wijzigen
U kunt een bestaand beleid bewerken en toepassen op de beoogde gebruikers. Wanneer u echter bestaand beleid wijzigt, worden de wijzigingen pas na 8 uur zichtbaar voor gebruikers die al bij de apps zijn aangemeld.

Om het effect van de wijzigingen onmiddellijk te zien, moet de eindgebruiker zich afmelden bij de app en zich daarna opnieuw aanmelden.

### <a name="to-change-the-list-of-apps-associated-with-the-policy"></a>De lijst met aan het beleid gekoppelde apps wijzigen

1. Selecteer het beleid dat u wilt wijzigen op de blade **App-beveiligingsbeleid**.

2. Selecteer in het deelvenster *Intune-app-beveiliging* de optie **Doel-apps** om de lijst met apps te openen.

3. Verwijder apps uit de lijst of voeg ze er aan toe en selecteer het pictogram **Opslaan** om uw wijzigingen op te slaan.

#### <a name="to-change-the-list-of-user-groups"></a>De lijst met gebruikersgroepen wijzigen

1. Selecteer het beleid dat u wilt wijzigen op de blade **App-beveiligingsbeleid**.

2. Selecteer in het deelvenster *Intune-app-beveiliging* de optie **Toewijzingen** om het deelvenster **Intune-app-beveiliging - Toewijzingen** te openen waarin de lijst met huidige gebruikersgroepen die dit beleid hebben wordt weergegeven.

3. Als u een nieuwe gebruikersgroep wilt toevoegen aan het beleid op het tabblad *Opnemen* kiest u **Selecteer groepen om op te nemen** en selecteert u de gebruikersgroep. Kies **Selecteren** om de groep toe te voegen. 

4. Als u een gebruikersgroep wilt uitsluiten, kiest u op het tabblad *Uitsluiten* de optie **Groepen selecteren voor uitsluiten**, en selecteert u de gebruikersgroep. Kies **Selecteren** om de gebruikersgroep te verwijderen.  

5. Als u groepen wilt verwijderen die eerder zijn toegevoegd, selecteert u op het tabblad *Opnemen* of op het tabblad *Uitsluiten* het weglatingsteken (...) en selecteert u **Verwijderen**. 

5. Als uw wijzigingen aan de toewijzingen gereed zijn, selecteert u **Opslaan** om de configuratie op te slaan en implementeert u het beleid voor de nieuwe groep gebruikers. Als u **Verwijderen** selecteert vóórdat u de configuratie opslaat, worden alle wijzigingen verwijderd die u hebt aangebracht op de tabbladen *Opnemen* en *Uitsluiten*.

### <a name="to-change-windows-10-policy-settings"></a>Windows 10-beleidsinstellingen wijzigen

1. Kies het beleid dat u wilt wijzigen op de blade **App-beveiligingsbeleid**.

2. Selecteer in het deelvenster *Intune-app-beveiliging* de optie **Eigenschappen** om de lijst met instellingsgebieden te openen die u kunt bewerken. 

3. Selecteer het instellingsgebied met de instellingen die u wilt wijzigen, zoals **Herlocatie van gegevens** of **Toegangsvereisten**. Wijzig de instellingen vervolgens in nieuwe waarden.

4. Selecteer het pictogram **Opslaan** om uw wijzigingen op te slaan. Herhaal de procedure voor het selecteren van een instellingsgebied en breng uw wijzigingen. Sla vervolgens uw wijzigingen op totdat alle wijzigingen zijn voltooid. U kunt het deelvenster *Intune-app-beveiliging* dan sluiten. 

## <a name="target-app-protection-policies-based-on-device-management-state"></a>Beleidsregels voor app-beveiliging toepassen op basis van de apparaatbeheerstatus
In veel organisaties is het gebruikelijk dat eindgebruikers gebruik mogen maken van via Intune MDM (Mobile Device Management) beheerde apparaten zoals apparaten in eigendom van het bedrijf, en van niet-beheerde apparaten die alleen door Intune-app-beveiligingsbeleid worden beschermd. Niet-beheerde apparaten zijn vaak bekend onder de naam BYOD-apparaten (Bring Your Own).

Omdat Intune-app-beveiligingsbeleid op de identiteit van een gebruiker is gericht, worden de beveiligingsinstellingen voor een gebruiker op zowel ingeschreven (via MDM beheerde) als niet-ingeschreven apparaten (geen MDM) toegepast. Daarom kunt u Intune-app-beveiligingsbeleid richten op ofwel in Intune ingeschreven apparaten of iOS- en Android-apparaten waarvan de registratie ongedaan is gemaakt. U mag één beveiligingsbeleid voor niet-beheerde apparaten hebben waarin strenge DLP-besturingselementen voor preventie van gegevensverlies zijn toegepast, en een afzonderlijk beveiligingsbeleid voor via MDM beheerde apparaten waarbij minder strenge DLP-besturingselementen mogelijk zijn. Zie [App-beveiligingsbeleid en werkprofielen](android-deployment-scenarios-app-protection-work-profiles.md) voor meer informatie over hoe dit werkt op persoonlijke Android Enterprise-apparaten.

Voor het maken van deze beleidsregels bladert u naar **Client-apps** > **App-beveiliging** in de Intune-console en selecteert u **Beleid maken**. U kunt ook een bestaand app-beveiligingsbeleid bewerken. Als u het app-beveiligingsbeleid op zowel beheerde als niet-beheerde apparaten wilt toepassen, gaat u naar de pagina **Apps** en bevestigt u dat **Toepassen op apps op alle apparaattypen** is ingesteld op **Ja**, de standaardwaarde. Als u granulair wilt toewijzen op basis van de beheerstatus, stelt u **Toepassen op apps op alle apparaattypen** in op **Nee**. 

![Schermopname van de blade Een beleid toevoegen, waarbij Bedoeld voor alle app-typen is geselecteerd](./media/app-protection-policies/app-protection-policies-target-all.png)

### <a name="app-types"></a>App-typen

- **Apps op niet-beheerde apparaten**: Niet-beheerde apparaten zijn apparaten waarop Intune MDM niet is gedetecteerd. Dit omvat MDM-leveranciers van derden.
- **Apps op door Intune beheerde apparaten**: Beheerde apparaten worden beheerd door Intune MDM.
- **Apps in Android-werkprofiel**: Beheerde apparaten die zijn ingeschreven als apparaten met Android Enterprise-werkprofielen.

> Op Android-apparaten wordt gevraagd of de Intune-bedrijfsportal-app moet worden geïnstalleerd, ongeacht welk app-type is gekozen. Ook als u bijvoorbeeld Apps op door Intune-beheerde apparaten selecteert, wordt deze vraag nog steeds gesteld aan gebruikers met niet-beheerde Android-apparaten.

Voor iOS zijn extra app-configuratie-instellingen vereist om APP-instellingen (beveiligingsbeleid voor apps) te richten op apps op apparaten die zijn ingeschreven bij Intune:

- **IntuneMAMUPN** moet zijn geconfigureerd voor alle met MDM beheerde toepassingen. Zie [Gegevensoverdracht beheren tussen iOS-apps met Microsoft Intune](data-transfer-between-apps-manage-ios.md#configure-user-upn-setting-for-microsoft-intune-or-third-party-emm) voor meer informatie.
- **IntuneMAMDeviceID** moet zijn geconfigureerd voor alle toepassingen van derden en met LOB MDM beheerde toepassingen. **IntuneMAMDeviceID** moet zijn geconfigureerd voor het apparaat-id-token. Voorbeeld: `key=IntuneMAMDeviceID, value={{deviceID}}`. Zie [App-configuratiebeleidsregels toevoegen voor beheerde iOS-apparaten](app-configuration-policies-use-ios.md) voor meer informatie.
- Als alleen de **IntuneMAMDeviceID** is geconfigureerd, wordt het apparaat in Intune APP beschouwd als niet-beheerd.

> [!NOTE]
> Zie [MAM-beveiligingsbeleid toepassen op basis van beheerstatus](../fundamentals/whats-new-archive.md#mam-protection-policies-targeted-based-on-management-state-) voor specifieke iOS-ondersteuningsinformatie over app-beveiligingsbeleid op basis van de apparaatbeheerstatus.

## <a name="policy-settings"></a>Beleidsinstellingen
Selecteer een van de volgende links voor een volledig overzicht van de beleidsinstellingen voor iOS en Android:

- [iOS-beleid](app-protection-policy-settings-ios.md)
- [Android-beleid](app-protection-policy-settings-android.md)

## <a name="next-steps"></a>Volgende stappen
[Compatibiliteit- en gebruikersstatus controleren](app-protection-policies-monitor.md)

## <a name="see-also"></a>Zie tevens
* [Wat u kunt verwachten wanneer uw Android-app wordt beheerd door een app-beveiligingsbeleid](../fundamentals/end-user-mam-apps-android.md)
* [Wat u kunt verwachten wanneer uw iOS-app wordt beheerd door een app-beveiligingsbeleid](../fundamentals/end-user-mam-apps-ios.md)
