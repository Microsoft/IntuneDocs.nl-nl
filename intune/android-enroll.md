mdm-authority-set---
# <a name="required-metadata"></a>Vereiste metagegevens

titel: Android apparaten inschrijven in Intune titleSuffix: 'Intune Azure Preview' beschrijving: Intune Azure Preview: meer informatie over het inschrijven van Android-apparaten in Intune Azure Preview.'
keywords: author: nathbarn ms.author: nathbarn manager: angrobe ms.date: 04/12/2017 ms.topic: article ms.prod: ms.service: microsoft-intune ms.technology: ms.assetid: f276d98c-b077-452a-8835-41919d674db5

# <a name="optional-metadata"></a>Optionele metagegevens

#<a name="robots"></a>ROBOTS:
#<a name="audience"></a>Doelgroep:
#<a name="msdevlang"></a>ms.devlang:
ms.reviewer: chrisbal ms.suite: ems
#<a name="mstgtpltfrm"></a>ms.tgt_pltfrm:
ms.custom: intune-azure

---

# <a name="enroll-android-devices"></a>Android-apparaten inschrijven

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Als Intune-beheerder kunt u met Intune Android-apparaten beheren, waaronder Samsung Knox Standard-apparaten. U kunt ook het werkprofiel op [Android for Work-apparaten](#enable-enrollment-of-android-for-work-devices) beheren.

Apparaten waarop Samsung KNOX Standard wordt uitgevoerd, bieden ondersteuning voor beheer van meerdere gebruikers in Intune. Dit betekent dat eindgebruikers zich kunnen aan- en afmelden bij het apparaat met hun Azure AD-referenties, en dat het apparaat centraal wordt beheerd, ongeacht of het wordt gebruikt of niet. Wanneer eindgebruikers zich aanmelden, hebben ze toegang tot apps en wordt er een eventueel beleid toegepast. Wanneer ze zich afmelden, worden alle app-gegevens gewist.

## <a name="prerequisite"></a>Vereiste

U moet de MDM-instantie instellen op **Microsoft Intune** als voorbereiding op het beheer van mobiele apparaten. Zie [Set the MDM authority](mdm-authority-set.md) (De MDM-instantie instellen) voor instructies. U stelt de instantie slechts één keer in, wanneer u Intune voor het eerst instelt voor het beheer van mobiele apparaten, dus het kan zijn dat u de instantie al hebt ingesteld.

## <a name="set-up-android-enrollment"></a>Android-inschrijving instellen

Standaard staat Intune de registratie van Android- en Samsung Knox Standard-apparaten toe.

Zie [Beperkingen voor apparaattypen instellen](enrollment-restrictions-set.md#set-device-type-restrictions) als u de inschrijving wilt blokkeren van Android-apparaten of alleen Android-apparaten die het eigendom van de gebruiker zijn.

Zie [Apparaatlimietbeperkingen instellen](enrollment-restrictions-set.md#set-device-limit-restrictions) als u het maximumaantal apparaten wilt instellen dat een gebruiker kan inschrijven.

Als u apparaatbeheer wilt inschakelen, moeten uw gebruikers hun apparaat inschrijven door de app Intune-bedrijfsportal te downloaden (die beschikbaar is via Google Play) en vervolgens de app te openen en de prompts voor inschrijving te volgen. Zodra Android-apparaten worden beheerd, kunt u [nalevingsbeleid toewijzen](compliance-policy-create-android.md), [apps beheren](app-management.md) en meer.

## <a name="enable-enrollment-of-android-for-work-devices"></a>Registratie van Android for Work-apparaten inschakelen

Als u het werkprofiel op apparaten met [ondersteuning voor Android for Work](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012) wilt beheren, moet u een Android for Work-binding toevoegen aan Intune. Om apparaten te registreren die ondersteuning bieden voor Android for Work, maar die eerder zijn geregistreerd als gewone Android-apparaten, moet u de registratie van de apparaten eerst ongedaan maken en ze vervolgens opnieuw registreren.

## <a name="add-android-for-work-binding-for-intune"></a>Android for Work-binding toevoegen voor Intune

1. **Intune MDM instellen**<br>
Als u dit nog niet hebt gedaan, moet u het beheer van mobiele apparaten voorbereiden door [de instantie voor het beheer van mobiele apparaten in te stellen](mdm-authority-set.md) als **Microsoft Intune**.

2. **Android for Work-binding configureren**<br>
    Meld u als Intune-beheerder aan bij Azure Portal en kies **Meer services** > **Bewaking en beheer** > **Intune**.

    1. Kies op de blade **Intune** de optie **Apparaatinschrijving** > **Inschrijving van Android for Work** en klik op **Configureren** om de Android for Work-website van Google Play te openen. Deze wordt geopend in een nieuw tabblad in de browser.
  ![Schermopname met een koppeling om de Android for Work-binding configureren](./media/android-work-bind.png)

    2. **Aanmelden bij Google**<br>
   Meld u aan op de aanmeldingspagina van Google met het Google-account dat wordt gekoppeld aan alle Android for Work-beheertaken voor deze tenant. Dit is het Google-account dat door de IT-beheerders in uw organisatie wordt gebruikt voor het beheren en publiceren van apps in de Play for Work-console.

    3. **Organisatiegegevens opgeven**<br>
   Geef bij **Organization name** (Organisatienaam) de naam van uw bedrijf op. Bij **Enterprise mobility management (EMM) provider** moet *Microsoft Intune* worden weergegeven. Ga akkoord met de overeenkomst voor Android for Work, en klik op **Confirm** (Bevestigen). Uw aanvraag wordt verwerkt.

## <a name="specify-android-for-work-enrollment-settings"></a>Registratie-instellingen voor Android for Work opgeven
   Android for Work wordt alleen ondersteund op bepaalde Android-apparaten. Zie de [vereisten voor Android for Work](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012 style="target=new_window") van Google voor meer informatie. Elk apparaat dat ondersteuning biedt voor Android for Work, biedt ook ondersteuning voor conventioneel Android-beheer.  In Intune kunt u opgeven hoe apparaten met ondersteuning voor Android for Work moeten worden beheerd:

   - **Alle apparaten beheren als Android-apparaten**: alle Android-apparaten, ook de apparaten met ondersteuning voor Android for Work, worden geregistreerd als conventionele Android-apparaten.
   - **Ondersteunde apparaten beheren als Android for Work-apparaten**: alle apparaten met ondersteuning voor Android for Work worden geregistreerd als Android for Work-apparaten. Alle Android-apparaten die geen ondersteuning bieden voor Android for Work, worden geregistreerd als conventionele Android-apparaten.
   - **Ondersteunde apparaten alleen beheren als Android for Work-apparaten voor gebruikers in deze gebruikersgroepen**: hiermee kunt u Android for Work-beheer beperken tot bepaalde gebruikers. Alleen voor leden van de geselecteerde groepen worden apparaten met ondersteuning voor Android for Work geregistreerd als Android for Work-apparaten. Alle overige apparaten worden geregistreerd als Android-apparaten. Dit is nuttig tijdens een Android for Work-testfase.

<!--  ## Next steps for Android for Work
After configuring the Android for Work binding and settings, you can do the following:
- [Deploy Android for Work apps](android-for-work-apps.md)
- [Add Android for Work configuration policies](android-for-work-policy-settings-in-microsoft-intune.md)  -->

## <a name="tell-your-users-how-to-enroll-their-devices-to-access-company-resources"></a>Uw gebruikers vertellen hoe ze hun apparaten moeten inschrijven om toegang te krijgen tot bedrijfsresources

U moet uw eindgebruikers vertellen dat ze naar Google Play moeten gaan om de app Intune-bedrijfsportal te downloaden, en vervolgens de app moeten openen en de prompts voor inschrijving van hun apparaat moeten volgen. De app leidt gebruikers door het inschrijvingsproces en legt uit wat gebruikers kunnen verwachten en wat IT-beheerders wel en niet kunnen zien op hun apparaten.

U kunt hen ook een link naar online inschrijvingsstappen sturen: [Uw Android-apparaat inschrijven bij Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android).

Zie de volgende artikelen voor meer informatie over andere taken voor eindgebruikers:

- [Bronnen over de eindgebruikerservaring in Microsoft Intune](https://docs.microsoft.com/intune-classic/deploy-use/how-to-educate-your-end-users-about-microsoft-intune)
- [Uw Android-apparaat gebruiken met Intune](https://docs.microsoft.com/intune-user-help/using-your-android-device-with-intune)

## <a name="unbinding-your-android-for-work-administrative-account"></a>Binding van uw Android for Work-beheerdersaccount ongedaan maken

U kunt Android for Work-registratie en -beheer uitschakelen. Door in de Intune-beheerconsole op **Binding ongedaan maken** te klikken, worden alle geregistreerde Android for Work-apparaten en de relatie tussen het Android for Work-account en Intune verwijderd.

### <a name="how-to-unbind-an-android-for-work-account"></a>Binding van een Android for Work-account ongedaan maken

1. **Android for Work-binding ongedaan maken**<br>
    Meld u als Intune-beheerder aan bij Azure Portal en kies **Meer services** > **Bewaking en beheer** > **Intune**.  Kies op de blade **Intune** de optie **Apparaatinschrijving** > **Inschrijving van Android for Work** en klik op **Binding verwijderen**.

2. **Verwijderen van Android for Work-binding bevestigen**<br>
  Klik op **Ja** om de binding te verwijderen en de registratie van alle Android for Work-apparaten in Intune ongedaan te maken.
