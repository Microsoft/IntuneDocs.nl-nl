---
title: Beveiligingsbeleid voor apps maken en implementeren
titleSuffix: Microsoft Intune
description: Meer informatie over het maken en toewijzen van app-beveiligingsbeleid van Microsoft Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/30/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f31b2964-e932-4cee-95c4-8d5506966c85
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 2e0331210a10727ff5753e6c227777cd1ebb16d9
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/20/2018
ms.locfileid: "52185956"
---
# <a name="how-to-create-and-assign-app-protection-policies"></a>App-beveiligingsbeleid maken en toewijzen

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Meer informatie over het maken en toewijzen van app-beveiligingsbeleid van Microsoft Intune aan uw gebruikers. Dit onderwerp beschrijft ook hoe u wijzigingen aanbrengt in bestaande beleidsregels.

## <a name="before-you-begin"></a>Voordat u begint

App-beveiligingsbeleid kan van toepassing zijn op apps die worden uitgevoerd op apparaten die al dan niet door Intune worden beheerd. Voor een gedetailleerde beschrijving van de werking van het app-beveiligingsbeleid en de scenario's die worden ondersteund door het app-beveiligingsbeleid van Intune ziet u [Wat zijn app-beveiligingsbeleidsregels van Microsoft Intune?](app-protection-policy.md)

Zie [MAM apps list (MAM-app-lijst)](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) voor een lijst met ondersteunde MAM-apps.

Zie [Add apps to Microsoft Intune](apps-add.md) (Apps toevoegen aan Microsoft Intune) voor informatie over het toevoegen van LOB-apps (Line-Of-Business) aan Microsoft Intune in voorbereiding op app-beveiligingsbeleid.

##  <a name="create-an-app-protection-policy"></a>Beveiligingsbeleid voor apps maken
1. Ga in de Intune-portal naar **Client-apps** > **App-beveiligingsbeleid**. Hiermee opent u de details van het **App-beveiligingsbeleid**, waar u nieuw beleid kunt maken en bestaande beleidsregels kunt bewerken.
2. Selecteer **Beleid maken**.

   ![Schermafbeelding van de blade ‘Een beleid toevoegen’](./media/app-protection-add-policy.png)

3. Geef een naam op voor het beleid, voeg een korte beschrijving toe en selecteer het platformtype voor uw beleid. U kunt meer dan één beleid voor elk platform maken.

4. Selecteer **Apps** om de blade **Apps** te openen, zodat er een lijst met beschikbare apps wordt weergegeven. U kunt een of meer apps in de lijst selecteren die u wilt koppelen aan het beleid dat u maakt. Selecteer minste één app om een beleid te maken.  

5. Wanneer u de apps hebt geselecteerd, kiest u **Selecteren** om uw selectie op te slaan.

6. Kies **Vereiste instellingen configureren** op de blade **Een beleid toevoegen** om **Instellingen** te openen.

   Er zijn drie soorten beleidsinstellingen:
   - **Herlocatie van gegevens**: deze groep bevat de DLP-besturingselementen voor preventie van gegevensverlies, zoals knippen, kopiëren, plakken en beperkingen voor 'opslaan als'. Deze instellingen bepalen hoe gebruikers met gegevens in de apps kunnen werken.
   - **Toegangsvereisten**: deze groep bevat de pincodeopties per app die bepalen hoe de gebruiker toegang heeft tot de apps in een werkcontext.  
   - **Voorwaardelijk starten**: deze groep bevat instellingen zoals de minimale instellingen van het besturingssysteem, detectie van opengebroken of geroote apparaten en offline respijtperioden.

   Om u op gang te hepen, hebben de beleidsinstellingen standaardwaarden. U hoeft niets te wijzigen als de standaardwaarden aan uw vereisten voldoen.

   > [!TIP]
   > Deze beleidsinstellingen worden alleen afgedwongen wanneer u apps in de context van het werk gebruikt. Als eindgebruikers de app gebruiken voor een privétaak, worden deze beleidsregels niet toegepast. Let op: wanneer u een nieuw bestand maakt, wordt dit als een privébestand beschouwd. 

7. Selecteer **OK** om deze configuratie op te slaan. U bent nu terug in het deelvenster **Een beleid toevoegen**.
8. Selecteer **Maken** om het beleid te maken en uw instellingen op te slaan.

Nieuwe beleidsregels die u maakt, worden niet geïmplementeerd voor gebruikers totdat u dit expliciet doet. Zie [Een beleid implementeren naar gebruikers](app-protection-policies.md#deploy-a-policy-to-users) voor het implementeren van een beleid.

## <a name="deploy-a-policy-to-users"></a>Een beleid implementeren naar gebruikers

1. Selecteer een beleid in het deelvenster **App-beveiligingsbeleid**.

2. Open in het deelvenster ***Intune-app-beveiliging** de optie **Toewijzingen** om het deelvenster **Intune-app-beveiliging - Toewijzingen** te openen. Selecteer op het tabblad *Opnemen* de optie **Groepen selecteren om op te nemen**. 

   ![Schermafbeelding van het venster Toewijzingen met de optie Groepen selecteren om op te nemen gemarkeerd](./media/app-protection-policy-add-users.png)

3.  Er wordt een lijst met alle beveiligingsgroepen in uw **Azure Active Directory** weergegeven. Selecteer de gebruikersgroepen waarop u dit beleid wilt toepassen en kies vervolgens **Selecteren**. Als u **Selecteren** kiest, wordt het beleid bij gebruikers geïmplementeerd.

    ![Schermafbeelding van het deelvenster Gebruikersgroep toevoegen waarin de lijst met Azure Active Directory-gebruikers wordt weergegeven](./media/azure-ad-user-group-list.png)

U hebt nu beleid gemaakt en het beleid geïmplementeerd naar gebruikers.

Het beleid is alleen van invloed op gebruikers aan wie Microsoft Intune-licenties zijn toegewezen. Gebruikers in de geselecteerde beveiligingsgroep aan wie geen Intune-licentie is toegewezen, worden niet beïnvloed.

>[!IMPORTANT]
> Als u Intune met Configuration Manager gebruik om uw apparaten te beheren, wordt het beleid alleen direct op gebruikers in de geselecteerde groep toegepast. Leden van de onderliggende groepen binnen de geselecteerde groep worden niet door het beleid beïnvloed.

Eindgebruikers kunnen de apps downloaden in de App Store of via Google Play. Zie voor meer informatie:
* [Wat u kunt verwachten wanneer uw Android-app wordt beheerd door een app-beveiligingsbeleid](app-protection-enabled-apps-android.md)
* [Wat u kunt verwachten wanneer uw iOS-app wordt beheerd door een app-beveiligingsbeleid](app-protection-enabled-apps-ios.md)

##  <a name="change-existing-policies"></a>Bestaande beleidsregels wijzigen
U kunt een bestaand beleid bewerken en toepassen op de beoogde gebruikers. Wanneer u echter bestaand beleid wijzigt, worden de wijzigingen pas na 8 uur zichtbaar voor gebruikers die al bij de apps zijn aangemeld.

Om het effect van de wijzigingen onmiddellijk te zien, moet de eindgebruiker zich afmelden bij de app en zich daarna opnieuw aanmelden.

### <a name="to-change-the-list-of-apps-associated-with-the-policy"></a>De lijst met aan het beleid gekoppelde apps wijzigen

1.  Selecteer het beleid dat u wilt wijzigen op de blade **App-beveiligingsbeleid**.

2.  Selecteer in het deelvenster *Intune-app-beveiliging* de optie **Doel-apps** om de lijst met apps te openen.

3.  Verwijder apps uit de lijst of voeg ze er aan toe en selecteer het pictogram **Opslaan** om uw wijzigingen op te slaan.

### <a name="to-change-the-list-of-user-groups"></a>De lijst met gebruikersgroepen wijzigen


1.  Selecteer het beleid dat u wilt wijzigen op de blade **App-beveiligingsbeleid**.

2.  Selecteer in het deelvenster *Intune-app-beveiliging* de optie **Toewijzingen** om het deelvenster **Intune-app-beveiliging - Toewijzingen** te openen waarin de lijst met huidige gebruikersgroepen die dit beleid hebben wordt weergegeven.

3.  Als u een nieuwe gebruikersgroep wilt toevoegen aan het beleid op het tabblad **Opnemen** kiest u **Selecteer groepen om op te nemen** en selecteert u de gebruikersgroep. Kies **Selecteren** om het beleid te implementeren bij de groep die u hebt geselecteerd.

4.  Als u een gebruikersgroep wilt verwijderen, kiest u op het tabblad **Opnemen** **Groepen selecteren om uit te sluiten** en selecteert u de gebruikersgroep. Kies **Selecteren** om de gebruikersgroep te verwijderen.

### <a name="to-change-policy-settings"></a>Beleidsinstellingen wijzigen

1.  Kies het beleid dat u wilt wijzigen op de blade **App-beveiligingsbeleid**.

2.  Selecteer in het deelvenster *Intune-app-beveiliging* de optie **Eigenschappen** om de lijst met instellingsgebieden te openen die u kunt bewerken. 

3.  Selecteer het instellingsgebied met de instellingen die u wilt wijzigen, zoals **Herlocatie van gegevens** of **Toegangsvereisten**. Wijzig de instellingen vervolgens in nieuwe waarden.

4.  Selecteer het pictogram **Opslaan** om uw wijzigingen op te slaan. Herhaal de procedure voor het selecteren van een instellingsgebied en breng uw wijzigingen. Sla vervolgens uw wijzigingen op totdat alle wijzigingen zijn voltooid. U kunt het deelvenster *Intune-app-beveiliging* dan sluiten. 

## <a name="target-app-protection-policies-based-on-device-management-state"></a>Beleidsregels voor app-beveiliging toepassen op basis van de apparaatbeheerstatus
In veel organisaties is het gebruikelijk dat eindgebruikers gebruik mogen maken van via Intune MDM (Mobile Device Management) beheerde apparaten zoals apparaten in eigendom van het bedrijf, en van niet-beheerde apparaten die alleen door Intune-app-beveiligingsbeleid worden beschermd. Niet-beheerde apparaten zijn vaak bekend onder de naam BYOD-apparaten (Bring Your Own).

Omdat Intune-app-beveiligingsbeleid op de identiteit van een gebruiker is gericht, worden de beveiligingsinstellingen voor een gebruiker op zowel ingeschreven (via MDM beheerde) als niet-ingeschreven apparaten (geen MDM) toegepast. Daarom kunt u Intune-app-beveiligingsbeleid richten op ofwel in Intune ingeschreven apparaten of iOS- en Android-apparaten waarvan de registratie ongedaan is gemaakt. U mag één beveiligingsbeleid voor niet-beheerde apparaten hebben waarin strenge DLP-besturingselementen voor preventie van gegevensverlies zijn toegepast, en een afzonderlijk beveiligingsbeleid voor via MDM beheerde apparaten waarbij minder strenge DLP-besturingselementen mogelijk zijn. 

Voor het maken van deze beleidsregels bladert u naar **Client-apps** > **App-beveiliging** in de Intune-console en selecteert u **Beleid maken**. U kunt ook een bestaand app-beveiligingsbeleid bewerken. Als u het app-beveiligingsbeleid op zowel beheerde als niet-beheerde apparaten wilt toepassen, moet u bevestigen dat **Op alle app-typen toepassen** is ingesteld op **Ja**, de standaardwaarde. Als u granulair wilt toewijzen op basis van de beheerstatus, stelt u **Op alle app-typen toepassen** in op **Nee**. 

![Schermafbeelding van de blade Een beleid toevoegen, waarbij Bedoeld voor alle app-typen is geselecteerd](./media/app-protection-policies-target-all.png)

Voor iOS zijn extra app-configuratie-instellingen vereist om APP-instellingen te richten op apps op apparaten die zijn ingeschreven bij Intune:
- **IntuneMAMUPN** moet zijn geconfigureerd voor alle met MDM beheerde toepassingen. Zie [Gegevensoverdracht beheren tussen iOS-apps met Microsoft Intune](https://docs.microsoft.com/intune/data-transfer-between-apps-manage-ios#configure-user-upn-setting-for-microsoft-intune-or-third-party-emm) voor meer informatie.
- **IntuneMAMDeviceID** moet zijn geconfigureerd voor alle toepassingen van derden en met LOB MDM beheerde toepassingen. **IntuneMAMDeviceID** moet zijn geconfigureerd voor het apparaat-id-token. Voorbeeld: `key=IntuneMAMDeviceID, value={{deviceID}}`. Zie [App-configuratiebeleidsregels toevoegen voor beheerde iOS-apparaten](https://docs.microsoft.com/intune/app-configuration-policies-use-ios) voor meer informatie.
- Als alleen de **IntuneMAMDeviceID** is geconfigureerd, wordt het apparaat in Intune APP beschouwd als niet-beheerd.  

> [!NOTE]
> Zie [MAM-beveiligingsbeleid toepassen op basis van beheerstatus](whats-new-archive.md#mam-protection-policies-targeted-based-on-management-state-) voor specifieke iOS-ondersteuningsinformatie over app-beveiligingsbeleid op basis van de apparaatbeheerstatus.

## <a name="policy-settings"></a>Beleidsinstellingen
Selecteer een van de volgende links voor een volledig overzicht van de beleidsinstellingen voor iOS en Android:

- [iOS-beleid](app-protection-policy-settings-ios.md)
- [Android-beleid](app-protection-policy-settings-android.md)

## <a name="next-steps"></a>Volgende stappen
[Compatibiliteit- en gebruikersstatus controleren](app-protection-policies-monitor.md)

### <a name="see-also"></a>Zie tevens
* [Wat u kunt verwachten wanneer uw Android-app wordt beheerd door een app-beveiligingsbeleid](app-protection-enabled-apps-android.md)
* [Wat u kunt verwachten wanneer uw iOS-app wordt beheerd door een app-beveiligingsbeleid](app-protection-enabled-apps-ios.md)
