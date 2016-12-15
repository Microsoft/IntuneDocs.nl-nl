## <a name="november-2016"></a>November 2016

### <a name="new-capabilities"></a>Nieuwe mogelijkheden

<!--### View App States for All Platforms in Real Time
App installation status is now shown in real-time in the console. When you previously deployed an app, you had to wait for a targeted device to report back before the app install status was displayed in the Intune console.

### Streamline iOS App Management for your End Users
Intune can now automatically take over management of the previously installed app and no end user action is required.

Previously, if the end user of an enrolled iOS device installed an app from the App Store before you deployed that same app with a deployment action of __Available__, then the end user had to:

1. Open the __Company Portal__.
2. Select the app.
3. Tap __Install__ to enable Intune to take over management of the app.-->

__Nieuwe Microsoft Intune-bedrijfsportal voor Windows 10-apparaten__ Microsoft heeft een nieuwe [Microsoft Intune-bedrijfsportal voor Windows 10-apparaten](https://www.microsoft.com/store/apps/9wzdncrfj3pz) uitgebracht. Deze app maakt gebruik van de Windows 10 Universal-indeling en biedt gebruikers een bijgewerkte gebruikerservaring in de app zelf, en een identieke gebruikerservaring op alle Windows 10-apparaten (pc en mobiel), met behoud van de functionaliteit die ze momenteel gebruiken.

Met de nieuwe app kunnen gebruikers van Windows 10-apparaten ook gebruikmaken van aanvullende functies van het platform, zoals eenmalige aanmelding (SSO) en verificatie op basis van certificaten. De app wordt beschikbaar gesteld als een upgrade van de bestaande Windows 8.1-bedrijfsportal en Windows Phone 8.1-bedrijfsportal in de Windows Store. Zie [aka.ms/intunecp_universalapp](http://aka.ms/intunecp_universalapp) voor meer informatie.

<!--### Support for Windows Store for Business Apps Being Deployed as Available
You can now deploy apps you synchronized from the Windows Store for Business (WSfB) with a deployment action of __Available__ or __Required__. After syncing WSfB apps into Intune, administrators will be able to target those apps as available installs to groups of users. End users will see the deployed WSfB apps as available for install in the Universal Company Portal, where they can choose whether they would like to acquire the apps.

### Conditional Access for MAM with SharePoint Online

You can block apps that are not supported by Intune mobile app management (MAM) policies from accessing SharePoint online.  You can get started in Intune mobile app management via the Azure portal. Look for the  Conditional Access section in the “Settings” blade which now includes the option for SharePoint online.-->

> [!IMPORTANT]

> __Een update voor Intune en Android for Work__

> Hoewel u Android for Work-apps kunt implementeren met de actie __Vereist__, kunt u apps alleen implementeren als __Beschikbaar__ als uw Intune-groepen zijn gemigreerd naar de nieuwe functie voor groepen van Azure AD.

__De invoegtoepassing Intune App SDK voor Cordova biedt nu ondersteuning voor MAM zonder registratie__ App-ontwikkelaars kunnen de invoegtoepassing Intune App SDK voor Cordova nu gebruiken om MAM-functionaliteit zonder apparaatinschrijving in te schakelen in hun op Cordova gebaseerde apps voor Android en iOS. U vindt de Intune App SDK Cordova-invoegtoepassing [hier](https://github.com/msintuneappsdk/cordova-plugin-ms-intune-mam).

__Het onderdeel Intune App SDK Xamarin biedt nu ondersteuning voor MAM zonder registratie__ App-ontwikkelaars kunnen het Intune App SDK Xamarin-onderdeel nu gebruiken om MAM-functionaliteit zonder apparaatinschrijving in te schakelen in hun op Xamarin gebaseerde apps voor Android en iOS. U vindt het Intune App SDK Xamarin-onderdeel [hier](https://github.com/msintuneappsdk/intune-app-sdk-xamarin).

### <a name="notices"></a>Mededelingen

__Een Symantec-handtekeningcertificaat vereist geen ondertekend Windows Phone 8-bedrijfsportal meer voor uploaden__ Voor het uploaden van een Symantec-handtekeningcertificaat is geen ondertekend Windows Phone 8-bedrijfsportal-app meer nodig. Het certificaat kan afzonderlijk worden geüpload.

###<a name="deprecations"></a>Afschaffingen

__Ondersteuning voor de Windows Phone 8-bedrijfsportal__ Ondersteuning voor de Windows Phone 8-bedrijfsportal wordt nu afgeschaft. Ondersteuning voor het Windows Phone 8- en Windows RT-platform is afgeschaft in oktober 2016. Ondersteuning voor de Windows 8-bedrijfsportal is ook in oktober 2016 afgeschaft.

## <a name="october-2016"></a>Oktober 2016

### <a name="conditional-access-for-mobile-application-management"></a>Voorwaardelijke toegang voor beheer van mobiele toepassingen
U kunt de toegang tot Exchange Online beperken, zodat toegang alleen mogelijk is vanuit apps waarin beheerbeleid voor mobiele toepassingen met Intune wordt ondersteund, zoals Outlook. [Deze nieuwe functie](/intune/deploy-use/allow-policy-managed-apps-access-to-o365) past perfect bij het Intune MAM-beleid (Mobile App Management), aangezien u de toegang tot ingebouwde e-mailclients of andere apps die niet zijn geconfigureerd met het Intune MAM-beleid, kunt blokkeren. Hiermee zorgt u ervoor dat uw gebruikers de gegevens van uw organisatie gebruiken met apps die kunnen worden beveiligd met Intune MAM. U kunt aan de slag gaan met Intune Mobile App Management via Azure Portal. De nieuwe sectie Voorwaardelijke toegang kunt u in de blade Instellingen vinden.

### <a name="conditional-access-for-windows-pcs"></a>Voorwaardelijke toegang voor Windows-pc's
U kunt nu voorwaardelijk toegangsbeleid creëren via de beheerdersconsole van Intune. Zo kunt u voorkomen dat Windows-pc's toegang hebben tot [Exchange Online](/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune) en [SharePoint Online](/intune/deploy-use/restrict-access-to-sharepoint-online-with-microsoft-intune). Ook kunt u voorwaardelijke toegang creëren om de toegang te blokkeren tot Office- desktop en universele toepassingen.

### <a name="android-for-work-support"></a>Ondersteuning van Android for Work

> [!IMPORTANT]

> Hoewel u Android for Work-apps kunt implementeren met de actie __Vereist__, kunt u apps alleen implementeren als __Beschikbaar__ als uw Intune-groepen zijn gemigreerd naar de nieuwe functie voor groepen van Azure AD.

Intune is nu onderdeel van het AfW-programma (Android for Work). Vanaf deze maand beginnen we met het implementeren van ondersteuning voor AfW-functies. Dit zal enkele maanden duren. Houd er rekening mee dat bij de beschikbare app-implementatie van AfW gebruik wordt gemaakt van de nieuwe groeperings- en targetingervaring. Nieuw ingerichte Intune-serviceaccounts kunnen deze functie gebruiken zodra AfW voor de accounts beschikbaar is.

<!--Existing Intune customers can use this feature in production once their tenant has been migrated. Existing customers are welcome to create a trial Intune account to plan for and test this feature until their tenant has been migrated. Any questions on grouping and targeting timelines, please contact our [migration team](mailto:intunegrps@microsoft.com).-->

[Lees de aankondiging van Microsoft over ondersteuning van Intune voor Android for Work](https://blogs.technet.microsoft.com/enterprisemobility/2016/09/12/microsoft-intune-support-for-android-for-work/).

De volgende onderwerpen voor Intune zijn nieuw, of bijgewerkt met informatie over Android for Work:

Voor IT-professionals:
- [Android for Work installeren](/intune/deploy-use/set-up-android-for-work)
<!--- [Nathan Bigman's resource access topics]()-->
- [E-mailtoegang beperken tot Exchange Online en het nieuwe Exchange Online-specifiek met Intune](/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune)
- [E-mailtoegang beperken tot Exchange On-Premises en het oude Exchange Online-specifiek met Intune](/intune/deploy-use/restrict-access-to-exchange-onpremises-with-microsoft-intune)
- [Instellingen voor Android for Work-nalevingsbeleid](/intune/deploy-use/afw-compliance-policy-settings-in-microsoft-intune)
- [Android for Work-apps implementeren](/intune/deploy-use/android-for-work-apps)
- [Android for Work-apps configureren met beleid voor de configuratie van mobiele apps](/intune/deploy-use/afw-app-configuration-policy)
- [Android for Work-beleidsinstellingen](/intune/deploy-use/android-for-work-policy-settings-in-microsoft-intune)

Voor eindgebruikers:
- [Wat gebeurt er wanneer u een werkprofiel maakt](/intune/enduser/what-happens-when-you-create-a-work-profile-android)
- [Een werkprofiel maken en uw apparaat registreren bij Intune](/intune/enduser/create-a-work-profile-and-enroll-your-device-in-intune-android)

### <a name="lookout-integration-to-protect-ios-devices"></a>Lookout-integratie om iOS-apparaten te beveiligen
In oktober integreert Microsoft met de oplossing voor beveiliging tegen mobiele bedreigingen van Lookout, om mobiele iOS-apparaten te beveiligen door detectie van bijvoorbeeld malware en riskante apps op apparaten. De oplossing van Lookout helpt u het (configureerbare) risiconiveau te bepalen. U kunt een beleidsregel in Intune maken om de apparaatnaleving te bepalen op basis van de risicoanalyse door Lookout. Met behulp van beleid voor voorwaardelijke toegang kunt u toegang tot bedrijfsbronnen toestaan of blokkeren op basis van de apparaatnalevingsstatus.

Eindgebruikers van iOS-apparaten die niet voldoen aan het beleid, moeten hun apparaten inschrijven en de Lookout for Work-toepassing op hun apparaten installeren, de app activeren en bedreigingen verhelpen die zijn gerapporteerd in de Lookout for Work-toepassing om toegang te krijgen tot bedrijfsgegevens. Lees hoe u [Lookout for Work-apps kunt configureren en implementeren](/intune/deploy-use/configure-and-deploy-lookout-for-work-apps).
<!--TFS 1319493-->

<!--### New Microsoft Intune Company Portal available for Windows 10 devices
Microsoft is releasing a new [Microsoft Intune Company Portal for Windows 10 devices](https://go.microsoft.com/fwlink/?linkid=830663). This app, which leverages the new Windows 10 Universal format, will provide the user with an updated user experience within the app and identical experiences across all Windows 10 devices, PC and Mobile alike, while still enabling all the same functionality that they are using today.

The new app will also allow users to leverage additional platform features like single sign-on (SSO) and certificate-based authentication on Windows 10 devices. The app will be made available as an upgrade to the existing Windows 8.1 Company Portal and Windows Phone 8.1 Company Portal installs from the Windows Store.-->

### <a name="intune-app-wrapping-tool-for-android"></a>Intune App Wrapping Tool voor Android
U kunt uw apps gebruik laten maken van Mobile Application Management-beleid (MAM) van Intune door de Intune App Wrapping Tool te gebruiken. Ondersteuning voor MAM-beleid van Intune zonder apparaatregistratie is nu beschikbaar.

### <a name="manage-printing-from-apps-managed-using-mam-policies"></a>Afdrukbeheer voor apps die worden beheerd met MAM-beleid
U kunt nu voorkomen dat bedrijfsgegevens worden afgedrukt met apps waarop een MAM-beleid van toepassing is. Deze instelling is beschikbaar op de [Azure-portal](/Intune/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune) en werkt met zowel [iOS](/Intune/deploy-use/ios-mam-policy-settings)- als [Android](/Intune/deploy-use/android-mam-policy-settings)-apparaten.
<!--TFS 1014328-->

### <a name="support-for-fingerprints-on-android-devices"></a>Ondersteuning voor vingerafdrukken op Android-apparaten
Gebruikers kunnen met het MAM-beleid (Mobile App Management) voor Android nu met hun vingerafdruk toegang tot een app krijgen in plaats van een pincode te typen. Raadpleeg dit en andere [beleidsinstellingen voor het beheer van mobiele apps voor Android hier](/Intune/deploy-use/android-mam-policy-settings).

### <a name="notices"></a>Mededelingen

__Compatibiliteit van Android Samsung KNOX met Intune__ Bepaalde modellen van de Samsung Galaxy Ace-telefoon kunnen niet als Samsung KNOX-apparaat worden beheerd door Intune. Wanneer u deze apparaten registreert bij Intune, worden ze beheerd als standaard Android-apparaten.

De betrokken modelnummers zijn:

* SM-G313HU
* SM-G313HY
* SM-G313M
* SM-G313MY
* SM-G313U

U en uw eindgebruikers hoeven niets te doen. Ga voor meer informatie naar de [Samsung KNOX](https://www.samsungknox.com)-website.

__De bedrijfsportal-app voor Windows 8 wordt afgeschaft; ondersteuning voor Windows Phone 8 en Windows RT-platformen wordt afgeschaft__ Vanaf oktober 2016 biedt Microsoft Intune geen ondersteuning meer voor de Windows 8-bedrijfsportal. Microsoft Intune biedt dan ook geen ondersteuning meer voor het Windows Phone 8- en Windows RT-platform. Als gevolg hiervan kunt u geen Windows Phone 8- of Windows RT-apparaten meer registreren of bijwerken.

U kunt Windows Phone 8-, Windows RT- en Windows 8-apparaten die al zijn geregistreerd blijven beheren. Werk Windows 8- en Windows Phone 8-apparaten bij naar Windows 8.1 en Windows Phone 8.1. Gebruik de bijbehorende bedrijfsportalapps voor Windows 8.1 en Windows Phone 8.1 om zonder onderbrekingen door te gaan met het distribueren van apps naar deze apparaten.

Vanaf november 2016 bieden we geen ondersteuning meer voor de Windows Phone 8-bedrijfsportal.
<!--TFS 1255391-->

### <a name="whats-coming"></a>Binnenkort

__Nieuwe Microsoft Intune-bedrijfsportal voor Windows 10-apparaten__ Microsoft brengt een nieuwe Microsoft Intune-bedrijfsportal uit voor Windows 10-apparaten. Deze app maakt gebruik van de Windows 10 Universal-indeling en biedt gebruikers een bijgewerkte gebruikerservaring in de app zelf, en een identieke gebruikerservaring op alle Windows 10-apparaten (pc en mobiel), met behoud van de functionaliteit die ze momenteel gebruiken.

Met de nieuwe app kunnen gebruikers van Windows 10-apparaten ook gebruikmaken van aanvullende functies van het platform, zoals eenmalige aanmelding (SSO) en verificatie op basis van certificaten. De app wordt beschikbaar gesteld als een upgrade van de bestaande Windows 8.1-bedrijfsportal en Windows Phone 8.1-bedrijfsportal in de Windows Store. Zie [aka.ms/intunecp_universalapp](http://aka.ms/intunecp_universalapp) voor meer informatie.
<!--TFS 1016502-->

## <a name="september-2016"></a>September 2016
### <a name="new-features-announcements-and-information"></a>Nieuwe functies, aankondigingen en informatie
* [Voorwaardelijke toegang tot Windows](#windows-conditional-access)
* [Ondersteuning voor iOS 10](#ios-10-support)
* [App Wrapping Tool ondersteunt MAM zonder apparaatinschrijving voor Android en iOS](#app-wrapping-tool-supports-mam-without-device-enrollment-for-android-and-ios)
* [Intune-groepen beginnen in september met het overstappen naar Azure Active Directory](#intune-groups-begin-transitioning-to-azure-active-directory-in-september)
* [Lookout-integratie om Android-apparaten te beveiligen](#lookout-integration-to-protect-android-devices)
* [Bedrijfsportalupdates voor Android, iOS en Windows](#company-portal-updates)
* [Verklarende woordenlijst voor Intune](#intune-glossary)
* [Binnenkort](#whats-coming)

### <a name="windows-conditional-access"></a>Voorwaardelijke toegang tot Windows
U kunt nu voorwaardelijk toegangsbeleid creëren via de beheerdersconsole van Intune. Zo kunt u voorkomen dat Windows-pc's toegang hebben tot Exchange Online en SharePoint Online. Ook kunt u voorwaardelijke toegang creëren om de toegang te blokkeren tot Office- desktop en universele toepassingen.

### <a name="ios-10-support"></a>Ondersteuning voor iOS 10
Bestaande Intune MDM- en MAM-scenario's zijn compatibel met iOS 10. Raadpleeg voor tips de [Intune-teamblog voor ondersteuning](https://blogs.technet.microsoft.com/intunesupport/2016/09/13/support-tip-intune-support-for-ios-10/).

### <a name="app-wrapping-tool-supports-mam-without-device-enrollment-for-android-and-ios"></a>App Wrapping Tool ondersteunt MAM zonder apparaatinschrijving voor Android en iOS
Intune App Wrapping Tool is een opdrachtregelprogramma dat wordt gebruikt voor het inschakelen van Intune MAM voor LOB-apps (Line-Of-Business) voor iOS en Android. Dit is de eenvoudigste manier om de Intune MAM SDK in uw app op te nemen, zodat in uw app MAM-beleid kan worden afgedwongen dat is geïmplementeerd via Intune. Met MAM-beleid kunt u het volgende doen:

1. De gegevens van de app versleutelen.
2. De informatiemedewerker vragen een pincode in te voeren bij het starten van de app.
3. Toestaan dat met de app alleen gegevens worden overgebracht naar andere beheerde apps.
4. Voorkomen dat met de app een back-up wordt opgeslagen in Android, iTunes of iCloud.
5. Knippen, kopiëren en plakken in en uit andere beheerde apps toestaan.

De openbare preview-versie van de bijgewerkte Intune App Wrapping Tool ondersteunt nu MAM zonder apparaatinschrijving voor interne LOB-apps voor iOS en Android. Dit betekent dat uw eindgebruikers hun apparaten niet hoeven in te schrijven met Intune om voor MAM geschikte LOB-apps te gebruiken.

Iedereen kan de openbare preview-software testen en nuttige documentatie in msintuneappsdk's GitHub lezen:

<p style="margin-left: 40px">http://www.github.com/msintuneappsdk/intune-app-wrapper-ios-preview

<p style="margin-left: 40px">http://www.github.com/msintuneappsdk/intune-app-wrapper-android-preview

Voordat u Microsoft Intune App Wrapper voor Android en iOS Pre-Release installeert en gebruikt, moet u:

* De licentievoorwaarden van Microsoft voor Microsoft Intune App Wrapping Tool voor Android en iOS Pre-Release lezen;
* Een exemplaar van de licentievoorwaarden voor uw administratie afdrukken en bewaren. Door Microsoft Intune App Wrapping Tool voor Android Pre-Release te downloaden en gebruiken, geeft u aan dat u akkoord gaat met deze licentievoorwaarden. Als u deze niet accepteert, moet u de software niet gebruiken.
<!---TFS 1235607--->

### <a name="intune-groups-begin-transitioning-to-azure-active-directory-in-september"></a>Intune-groepen beginnen in september met het overstappen naar Azure Active Directory
Sommige nieuwe Intune-accounts gebruiken Azure Active Directory-beveiligingsgroepen in plaats van Intune-gebruikersgroepen. U zult merken dat u met beveiligingsgroepen werkt, doordat de pagina voor Intune-portalgroepen dan een koppeling heeft die u doorstuurt naar de Azure-beheerportal.

### <a name="lookout-integration-to-protect-android-devices"></a>Lookout-integratie om Android-apparaten te beveiligen
Microsoft is aan het integreren met de oplossing voor beveiliging tegen mobiele bedreigingen van Lookout om mobiele Android-apparaten te beveiligen door malware, riskante apps enzovoort op apparaten te detecteren. De oplossing van Lookout helpt u het (configureerbare) risiconiveau te bepalen. U kunt een beleidsregel in Intune maken om de apparaatnaleving te bepalen op basis van de risicoanalyse door Lookout. Met behulp van beleid voor voorwaardelijke toegang kunt u toegang tot bedrijfsbronnen toestaan of blokkeren op basis van de apparaatnalevingsstatus.

Eindgebruikers van apparaten die niet voldoen aan het beleid, moeten hun apparaten inschrijven en de Lookout for Work-toepassing op Android-apparaten installeren, de app activeren en bedreigingen verhelpen die zijn gerapporteerd in de Lookout for Work-toepassing om toegang te krijgen. Zie voor meer informatie [Toegang beperken op basis van apparaat, netwerk en toepassingsrisico](https://docs.microsoft.com/en-us/intune/deploy-use/restrict-access-based-on-device-network-app-risk).


### <a name="company-portal-updates"></a>Updates voor de bedrijfsportal

__Android__

<p style="margin-left: 40px">**Toevoeging van 'Meldingen' aan de bedrijfsportal voor Android**<br/>
<p style="margin-left: 40px">Er is op de startpagina een nieuw meldingenpictogram toegevoegd aan de bedrijfsportal voor Android. Door op dit pictogram te tikken wordt de pagina Meldingen geopend waar de eindgebruikers alle items zien die aandacht vereisen in de bedrijfsportal-app, zoals niet-compatibele apparaten, inschrijvingsupdates en activering van inschrijvingen. Met de iOS-bedrijfsportal-app kunt u de meldingen al zien. Door de introductie van de pagina Meldingen zien gebruikers niet langer de pagina Bedrijfstoegang instellen wanneer zij de bedrijfsportal starten of hervatten als het apparaat al is geregistreerd. Als u uw eigen richtlijnen voor eindgebruikers maakt, is het raadzaam om uw documentatie bij te werken met deze wijziging. Zoek [hier](https://aka.ms/androidcpupdate) naar bijgewerkte schermafbeeldingen.  

__iOS__
<p style="margin-left: 40px">**Wijzigingen in de ondersteuning voor de iOS-bedrijfsportal-app**<br/>
<p style="margin-left: 40px">Alle gebruikers van de Microsoft Intune-bedrijfsportal-app voor iOS moeten nu overstappen naar de nieuwste versie. Nieuwe gebruikers kunnen alleen de nieuwste versie downloaden en bestaande gebruikers moeten bijwerken naar de nieuwe versie. De meest recente versie vereist iOS 8.0 of hoger, zodat apparaten met oudere versies van iOS de bedrijfsportal niet kunnen gebruiken en niet kunnen registreren totdat ze hun apparaat hebben bijgewerkt naar iOS 8.0 of hoger en vervolgens de Bedrijfsportal-app bijwerken naar de nieuwste versie. Geregistreerde apparaten met een versie lager dan iOS 8.0 worden gewoon nog worden beheerd met en vermeld in de Intune-beheerconsole.
<!---TFS 1283165--->

<p style="margin-left: 40px">**Verbeteringen aan hoe iOS-eindgebruikers hun apps verkrijgen**<br/>
<p style="margin-left: 40px">De volgende wijzigingen zijn aangebracht in de app-tegels in de Bedrijfsportal-app voor iOS, zodat gebruikers op één locatie (de Bedrijfsportal-website) naar verschillende weergaven worden verwezen voor alle apps. Het wordt door Apple verboden om LOB- (Line-Of-Business) en beheerde App Store-apps te vermelden in de Bedrijfsportal-app en gebruikers moeten verschillende weergaven openen om al hun apps te vinden.

<p style="margin-left: 40px">De tegel **Bedrijfsapps** verwees eerder naar alle apps op het tabblad ALLE van de Bedrijfsportal-website, en deze blijft op dezelfde manier werken. De naam van de tegel is gewijzigd in **Alle apps**.

<p style="margin-left: 40px">De tegel **Andere apps** verwees eerder naar een weergave in de bedrijfsportal-app waarin alle apps worden vermeld die van Apple mogen worden weergegeven in de app. De naam van de tegel is gewijzigd in **Aanbevolen apps**. Wanneer gebruikers op de tegel tikken, gaan ze naar het tabblad AANBEVOLEN van de bedrijfsportal-website.

<p style="margin-left: 40px">De tegel **Categorieën** verwees eerder naar een weergave in de bedrijfsportal-app waarin app-categorieën worden vermeld. De naam van de tegel is niet gewijzigd, maar de tegel verwijst nu naar het tabblad CATEGORIEËN van de bedrijfsportal-website. U vindt [hier](https://gallery.technet.microsoft.com/Improvements-in-how-iOS-d1104186) bijgewerkte schermafbeeldingen.
  <!---TFS 1317133--->

<p style="margin-left: 40px">**Vragen om de iOS-app voor de Managed Browser te installeren als de IT-professional dat vereist voor een app**<br/>
<p style="margin-left: 40px">Als u hebt geconfigureerd dat webclips alleen worden geopend in Managed Browser en Managed Browser niet is geïnstalleerd op een apparaat, krijgen gebruikers via de Bedrijfsportal-app op het apparaat de instructie om Managed Browser te installeren. Daarna kunnen ze de webclip pas openen.
  <!---TFS 1228570--->

__Windows__
<p style="margin-left: 40px">**De knop Feedback is toegevoegd aan de bedrijfsportal-app voor Windows Phone 8.1**<br/>
<p style="margin-left: 40px">Via de bedrijfsportal-app voor Windows Phone 8.1 kunnen eindgebruikers feedback over de app verzenden met een nieuwe knop Feedback verzenden. Gebruikers vinden de knop door te tikken op het menu met drie punten rechtsonder in het scherm van de bedrijfsportal-app en vervolgens te tikken op **feedback verzenden**. De verzamelde, geanonimiseerde feedback helpt Microsoft bij het verbeteren van de gebruikerservaring van de bedrijfsportal-app.
<!---TFS 1317806--->

### <a name="intune-glossarybr"></a>Verklarende woordenlijst voor Intune</br>
We hebben een nieuw [woordenlijstitem](https://docs.microsoft.com/intune/understand-explore/intune-glossary) toegevoegd aan de bibliotheek om meer duidelijkheid te geven over de termen die worden gebruikt bij het Intune-product.

## <a name="august-2016"></a>Augustus 2016
### <a name="app-management"></a>Appbeheer
<!---@Barry, I created the buckets of App management, Device management, etc but am not tied to them. Just wanted to break up and organize the feature list. If you're going to take over the Company Portal section, please talk to Stacie about how she's been organizing it. --->

__Verborgen en weergegeven apps voor iOS 9.3__ Voor apparaten waarop iOS 9.3 of hoger wordt uitgevoerd, kunt u de lijst met verborgen of weergegeven apps in het algemene configuratiebeleid voor iOS gebruiken om het volgende te doen:
- Een lijst opstellen met apps die verborgen zijn voor gebruikers. Gebruikers kunnen deze apps niet weergeven of starten.
- Een lijst opstellen met apps die gebruikers kunnen weergeven en starten. Andere apps kunnen niet worden weergegeven of gestart.

De apps die u kunt opgeven zijn zowel apps die u hebt geïmplementeerd als de ingebouwde iOS-apps, zoals Berichten en Notities. Zie [Instellingen voor iOS-beleid in Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/ios-policy-settings-in-microsoft-intune) voor meer informatie.
<!---TFS 1279009 checked--->
__Beleid voor toegestane en geblokkeerde apps voor Samsung KNOX-apparaten__ U kunt nu een aangepast beleid voor Samsung KNOX-apparaten configureren om het volgende te maken:
- Een lijst met apps die niet kunnen worden uitgevoerd op het apparaat. Apps in deze lijst kunnen niet op het apparaat worden geactiveerd, ongeacht of ze daarop zijn geïnstalleerd.
- Een lijst met apps die gebruikers van het apparaat kunnen installeren uit de Google Play Store. Geen andere apps kunnen worden geïnstalleerd uit de Store.

Deze instellingen kunnen alleen worden gebruikt door apparaten met Samsung KNOX.
Zie [Aangepaste beleidsregels gebruiken om apps toe te staan of te blokkeren voor Samsung KNOX-apparaten](https://docs.microsoft.com/en-us/intune/deploy-use/custom-policy-to-allow-and-block-samsung-knox-apps) voor meer informatie.
<!---TFS 1311629 checked --->

__Nieuwe apps die compatibel zijn met de beleidsregels van Mobile Application Management (MAM)__ De app Yammer voor [iOS](https://itunes.apple.com/app/yammer/id289559439?mt=8) en [Android](https://play.google.com/store/apps/details?id=com.yammer.v1) is nu compatibel met de [Intune MAM-beleidsregels (Mobile Application Management)](/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune), ongeacht of het apparaat is ingeschreven of niet.

Zie de website [Microsoft Intune-toepassingspartners](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-partners) voor een volledige lijst met apps die compatibel zijn met MAM.
<!--- TFS 1252335 & 1252336 checked--->


<!--- I started putting TFS numbers in the What's Coming topic and found it helpful when updating the What's New. Up to you if you want to continue. --->

__Intune-viewer-apps__ Met het uitbrengen van de nieuwe RMS-app voor delen worden de volgende Intune-viewer-apps vanaf augustus 2016 verwijderd:
- Intune AV-viewer
- Intune PDF-viewer
- Intune-afbeeldingsviewer voor Android van Google Play

In plaats van de viewer-apps van Intune kunt u beter de nieuwe [Rights Management-app (RMS sharing) voor Android](https://docs.microsoft.com/en-us/intune/deploy-use/end-user-experience-for-mam-enabled-apps-with-microsoft-intune#viewing-media-files-with-the-rights-management-sharing-app) gebruiken, zodat u één app in plaats van drie afzonderlijke apps kunt implementeren om veilig bedrijfsbestanden op Android-apparaten te bekijken. Als de Intune-viewer-app niet meer wordt ondersteund, wordt deze verwijderd uit de Google Store en zal deze niet meer beschikbaar zijn voor toekomstig gebruik.

### <a name="device-management"></a>Apparaatbeheer
__Android 7.0-ondersteuning__ Intune biedt vanaf dag één ondersteuning voor het toekomstige Android 7.0-besturingssysteem voor mobiele apparaten.
<!---TFS 1262053--->
### <a name="google-removal-of-remote-passcode-reset-capability-on-android-70-devices"></a>Google verwijdert het op afstand opnieuw instellen van de wachtwoordcode voor Android 7.0-apparaten
Google verwijdert de mogelijkheid van IT-beheerders en eindgebruikers om de wachtwoordcode van Android 7.0-apparaten op afstand opnieuw in te stellen. Voorheen konden IT-beheerders op afstand de wachtwoordcode van een gebruiker opnieuw instellen, en konden eindgebruikers hun wachtwoordcodes opnieuw instellen via de bedrijfsportalwebsite.



### <a name="company-portal-updates"></a>Updates voor de bedrijfsportal
__Bedrijfsportalwebsite__
- **Feedbackkoppeling van de bedrijfsportal naar Microsoft** <br/>
Op de website van de bedrijfsportal kunnen eindgebruikers tikken op de nieuwe koppeling Feedback onder aan de pagina en zo feedback verzenden naar Microsoft over hun ervaringen met de site. De verzamelde, geanonimiseerde feedback helpt Microsoft bij het verbeteren van de gebruikerservaring van de bedrijfsportalwebsite.
<!--- TFS 1313657 checked--->

__iOS__
- **Minimale iOS Managed Browser-versie is bijgewerkt naar 8.0**<br/>
De Microsoft Intune Managed Browser-app voor iOS is bijgewerkt voor ondersteuning van apparaten met iOS 8.0 of hoger. Hoewel op iOS 7.1-apparaten nog steeds de bestaande Managed Browser-app kan worden gebruikt, is het verstandig om uw gebruikers aan te raden hun apparaat bij te werken naar iOS 8.0 of hoger, zodat ze volledig kunnen profiteren van de nieuwe Managed Browser-functies.  
<!---TFS 1313253 checked--->

### <a name="whats-coming"></a>Binnenkort
__Intune-groepen stappen met ingang van september 2016 over naar Azure Active Directory-groepen__ Intune is bezig met het creëren van een nieuwe ervaring voor het beheer van groepen die gebruikmaakt van Azure Active Directory (AAD)-beveiligingsgroepen als gebruikers- en apparaatgroepen in Intune. Deze groepen worden gebruikt voor alle groepsbeheer en voor implementatie van beleid en profielen **wanneer wij het nieuwe op Azure gebaseerde Intune-beheerportal introduceren**.

Door deze nieuwe ervaring hoeft u niet langer groepen te dupliceren tussen services, **hebt u toegang tot een aantal nieuwe groepsfuncties van Azure Active Directory Premium (AADP)**, en profiteert u van uitbreidbaarheid met behulp van PowerShell en Graph. Dit zorgt tevens voor een uniforme ervaring voor groepsbeheer voor het gehele beheer van bedrijfsmobiliteit.

Om de overstap naar beveiligingsgroepen mogelijk te maken, wordt de ervaring in de **huidige beheerconsole** ietwat gewijzigd. **Deze wijzigingen, en het gebruik van AAD-beveiligingsgroepen, worden beschreven in de Intune-documentatie**.

Voor nieuwe Intune-klanten worden bepaalde **wijzigingen van beveiligingsgroepen eerder doorgevoerd dan voor bestaande klanten**.

Naast de wijzigingen in het groepsbeheer, **wordt de volgende functionaliteit afgeschaft**:
- Uitsluiten van leden of groepen tijdens het maken van een nieuwe groep
- Groepen van **Niet-gegroepeerde gebruikers** en **Niet-gegroepeerde apparaten**
- **Groepen beheren** in de rol van servicebeheerder
- Aangepaste waarschuwingen op basis van groepen voor meldingsregels
- Draaien met groepen in rapporten
<!--- TFS 1295329--->

__Toevoeging van 'Meldingen' aan de bedrijfsportal voor Android__ In september brengen wij een update uit van de bedrijfsportal voor Android, waarmee een nieuw pictogram **Meldingen** wordt geïntroduceerd op de startpagina. Door op dit pictogram te tikken wordt de pagina **Meldingen** geopend waar de eindgebruiker alle items ziet die aandacht vereisen in de bedrijfsportal-app, zoals niet-compatibele apparaten, inschrijvingsupdates en activering van inschrijvingen. Als u ook de iOS-bedrijfsportal-app gebruikt, kunt u de meldingen al zien. Door de introductie van de pagina **Meldingen** ziet u niet langer de pagina **Bedrijfstoegang instellen** wanneer u de bedrijfsportal voor Android start of hervat als het apparaat reeds is ingeschreven. Wij weten dat velen van u een handleiding hebben gemaakt voor eindgebruikers en stellen het op prijs wanneer u ons tijdig informeert wanneer uw handleiding en/of schermafbeeldingen moeten worden bijgewerkt. Werk uw documentatie bij zodat toekomstige wijzigingen in de gebruikerservaring goed worden beschreven. Bijgewerkte schermafbeeldingen vindt u hier: https://aka.ms/androidcpupdate.  

### <a name="service-deprecation"></a>Serviceafschaffing
<!---@Barry, we started listing service deprecations earlier this summer. --->
- **Wijzigingen in de ondersteuning voor de iOS-bedrijfsportal-app**<br/>
In september moeten alle gebruikers van de Microsoft Intune-bedrijfsportal-app voor iOS overstappen naar de nieuwste versie. Nieuwe gebruikers kunnen alleen de nieuwste versie downloaden en bestaande gebruikers moeten bijwerken naar de nieuwe versie. De meest recente versie vereist iOS 8.0 of hoger, zodat apparaten met oudere versies van iOS de bedrijfsportal niet kunnen gebruiken en niet kunnen registreren totdat ze hun apparaat naar hebben bijgewerkt naar iOS 8.0 of hoger en vervolgens de bedrijfsportal-app bijwerken naar de nieuwste versie. Geregistreerde apparaten met een versie lager dan iOS 8.0 worden gewoon nog worden beheerd met en vermeld in de Intune-beheerconsole.  

- **Minimale iOS Managed Browser-versie is bijgewerkt naar 8.0**<br/>
In augustus brengt Intune een bijgewerkte Microsoft Intune Managed Browser-app uit voor iOS die alleen apparaten ondersteund waarop iOS 8.0 of later wordt uitgevoerd. Hoewel iOS 7.1-apparaten nog steeds de bestaande Managed Browser-app kunnen gebruiken, dient u uw gebruikers aan te moedigen bij te werken naar iOS 8.0 of later om volledig te kunnen profiteren van nieuwe functies van Managed Browser.  
<!---TFS 1313253--->

- **Bedrijfsportal-apps voor Windows 8 en Windows Phone 8 worden vanaf september 2016 afgeschaft** <br/>
Vanaf september 2016 biedt Microsoft Intune geen ondersteuning meer voor de Microsoft Intune-bedrijfsportal-apps voor Windows Phone 8 en Windows 8. Apparaten bijwerken naar Windows 8.1 en Windows Phone 8.1 en de bijbehorende bedrijfsportal-app voor Windows 8.1 en Windows Phone 8.1 gebruiken om door te gaan met het distribueren van apps naar deze apparaten.
<!---TFS 1255391--->

<!--- - **Custom Group Targeting of Notification Rules Removal.**<br/>
Intune notification rules define who an email alert will be sent to from Intune. Currently, you can configure notification rules to send emails to all users of devices in an Intune device group that you created. From around June 1st 2016 moving forward, targeting user-created groups will no longer be supported.

    Today, to target a notification rule to a group you created from the Microsoft Intune administration console, you would take the following steps:

    In the **Admin** workspace, click **Notification Rules** > **Create New Rule**

    In step two of the Create Notification Rule Wizard, select the device groups which the rule will target. This step, “select device groups”, is being removed from the Intune Console.

    The preliminary timeline for this change is as follows:
    - In August, 2016, new tenants will not see step two of the Create Notification Rule Wizard. Exiting tenants are unaffected.
    - Around September, 2016, some existing tenants will not see the “select device groups” in the wizard.
    - Around November, 2016, we expect that all tenants will not see the “select device groups” in the wizard.

--->

## <a name="july-2016"></a>Juli 2016
### <a name="app-management"></a>Appbeheer

__De update-ervaring van het inrichtingsprofiel van de app verbeteren__ Apple iOS mobiele Line-Of-Business-apps zijn gebouwd met een inrichtingsprofiel en code die is ondertekend met een certificaat. Wanneer de app wordt uitgevoerd op een iOS-apparaat, bevestigt iOS de integriteit van de iOS-app en worden beleidsregels afgedwongen die zijn gedefinieerd door het inrichtingsprofiel.

Het handtekeningcertificaat voor ondernemingen dat u gebruikt om apps te ondertekenen is doorgaans 3 jaar geldig. Het inrichtingsprofiel verloopt echter na één jaar. Met deze update biedt Intune u de hulpmiddelen om proactief een nieuw beleid voor inrichtingsprofielen te implementeren op apparaten met apps die bijna zijn verlopen terwijl het certificaat nog geldig is. Zie voor meer informatie [iOS-beleid voor mobiele inrichtingsprofielen gebruiken om uw Line-Of-Business-apps up-to-date te houden](/intune/deploy-use/ios-mobile-app-provisioning-profiles).
<!--- TFS 1280247--->

__Xamarin SDK voor Intune-apps is beschikbaar__ Met het onderdeel Intune App SDK Xamarin kunt u de beheerfuncties voor Intune Mobile App inschakelen in mobiele iOS- en Android-apps die zijn gebouwd met Xamarin. U vindt het onderdeel in de [Xamarin Store](https://components.xamarin.com/view/Microsoft.Intune.MAM) of op de [Microsoft Intune Github-pagina](https://github.com/msintuneappsdk).
<!--- TFS 1061478 --->

### <a name="device-management"></a>Apparaatbeheer
__Verbeterde limieten voor apparaatinschrijvingen__ Intune heeft de maximaal configureerbare limiet voor apparaatinschrijvingen verhoogd van 5 naar 15 apparaten per gebruiker.
<!---TFS 1289896 --->

__TeamViewer-integratie voor Windows-pc's met de Intune-clientsoftware__
[TeamViewer](https://www.teamviewer.com) voor Windows-pc's die worden beheerd met de Intune-client kunt u, ter ondersteuning van uw helpdeskafdeling, sessies voor hulp op afstand met Windows-pc's uitvoeren. Dit is van toepassing op Windows 7, 8, 8.1 en 10. Zie [Algemene beheertaken voor Windows-pc’s met de Microsoft Intune-computerclient voor meer informatie](/intune/deploy-use/common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client).
<!---TFS 1284856--->

### <a name="company-portal-updates"></a>Updates voor de bedrijfsportal

__Bedrijfsportalwebsite__
- **Verbeterde ervaring voor de eindgebruiker bij het inschrijven van Windows-apparaten**<br/>
Wanneer u voorwaardelijke toegang gebruikt, zijn de stappen voor inschrijving voor Windows 8.1, Windows 10 Desktop en Windows 10 Mobile verbeterd op de bedrijfsportalwebsite. Gebruikers zien nu de afzonderlijke stappen 'Apparaatinschrijving' en 'Workplace Join', waardoor de status van hun apparaat beter zichtbaar is en het proces eenvoudiger kan worden voltooid wanneer er een fout optreedt met Workplace Join (WPJ). De afzonderlijke stappen vereenvoudigen tevens de probleemoplossing voor IT-beheerders. Wanneer eindgebruikers voorheen probeerden in te schrijven en alle inschrijvingsstappen waren geslaagd behalve WPJ, dan werd het ingeschreven apparaat niet weergegeven in de lijst met apparaten voor gebruikers, wat verwarrend was voor gebruikers.

__Android__
- **Android-bedrijfsportal-app**<br/>
Als Android-eindgebruikers een foutmelding krijgen dat er een vereist certificaat ontbreekt voor hun apparaat, dan kunnen zij op een knop 'Oplossing' tikken voor [stappen](/intune/enduser/your-device-is-missing-a-required-certificate-android#your-device-is-missing-a-certificate-required-by-your-it-administrator) om het ontbrekende certificaat te installeren. Als gebruikers de stappen voltooien, maar er nogmaals een foutmelding over een ontbrekend certificaat wordt weergegeven, dan wordt hen gevraagd contact op te nemen met de IT-beheerder en deze [koppeling](/intune/troubleshoot/troubleshoot-device-enrollment-in-intune#android-certificate-issues) door te geven die de stappen bevat waarmee IT-beheerders het certificaatprobleem kunnen oplossen.

- **Beperken van extern geladen (ofwel 'side-loaded') app-installaties op ingeschreven apparaten**<br/>
Android-apparaten kunnen geen toepassingen meer installeren via de bedrijfsportalwebsite tenzij deze apparaten zijn ingeschreven bij Intune via de Intune-bedrijfsportal-app voor Android.
<!---TFS 1299082--->

__iOS__
- **Wijzigingen in de beheeraccounts voor apparaatinschrijving in de iOS-bedrijfsportal-app**<br/>
Om de prestaties en schaalbaarheid te verbeteren, worden in het deelvenster **Mijn apparaten** van de iOS-bedrijfsportal-app niet meer alle Device Enrollment Managers (DEM)-apparaten weergegeven door Intune. Alleen het lokale apparaat waarop de app wordt uitgevoerd, wordt weergegeven en wel alleen als het apparaat is geregistreerd via de bedrijfsportal-app.

De DEM-gebruiker kan acties op het lokale apparaat uitvoeren, maar extern beheer van andere geregistreerde apparaten kan alleen worden uitgevoerd vanuit de Intune-beheerconsole. Daarnaast is het gebruik in Intune van DEM-accounts met het Apple Device Enrollment Program of het hulpprogramma Apple Configurator beëindigd. Deze twee registratiemethoden bieden al ondersteuning voor gebruikersloze registratie voor gedeelde iOS-apparaten.

Gebruik alleen DEM-accounts wanneer gebruikersloze registratie voor gedeelde apparaten niet beschikbaar is. Zie voor meer informatie [Apparaten in bedrijfseigendom inschrijven met de apparaatinschrijvingsbeheerder in Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune).
<!---TFS 1233681--->

### <a name="change-of-names-for-windows-features"></a>Wijziging van de namen voor Windows-functies
- [Microsoft Passport for Windows](/intune/deploy-use/control-microsoft-passport-settings-on-devices-with-microsoft-intune) is nu bekend als **Windows Hello voor Bedrijven**.
- [Ondernemingsgegevensbescherming](https://technet.microsoft.com/itpro/windows/keep-secure/create-edp-policy-using-intune) is nu bekend als **Windows Information Protection**.

## <a name="june-2016"></a>Juni 2016
### <a name="intune-service-health"></a>Servicestatus van Intune
Servicestatusgegevens voor Intune is verplaatst naar een centrale locatie met andere Microsoft-services. U vindt deze informatie nu in de Office 365-beheerportal onder Servicestatus. Lees [dit blogbericht](https://blogs.technet.microsoft.com/enterprisemobility/2016/04/28/intune-service-health-is-now-available-in-the-office-365-portal/) voor meer informatie.

### <a name="app-management"></a>Appbeheer
- **Verbeterde ervaring voor configuratie van Windows 10-beleid voor ondernemingsgegevens.** Er zijn verbeteringen aangebracht in de ervaring voor configuratie van het Windows 10-beleid voor ondernemingsgegevensbescherming. Deze verbeteringen hebben betrekking op het maken van app-regels, het opgeven van netwerkdefinities en op andere instellingen voor ondernemingsgegevensbescherming. Zie [Een Enterprise Data Protection-beleid (EDP) maken met Microsoft Intune](https://technet.microsoft.com/itpro/windows/keep-secure/create-edp-policy-using-intune) voor meer informatie.


### <a name="device-management"></a>Apparaatbeheer
- **Windows Defender-beleidsinstelling voor beveiliging tegen mogelijk ongewenste apps.** **Detectie van mogelijk ongewenste toepassingen** is een nieuwe Windows Defender-instelling die toegevoegd aan het algemene configuratiebeleid voor Windows 10 Desktop en Mobile. U kunt deze instelling gebruiken als u geregistreerde Windows-desktopcomputers wilt beveiligen tegen het uitvoeren van software die door Windows Defender als mogelijk ongewenst is gedefinieerd. U kunt voorkomen dat deze toepassingen worden uitgevoerd, of de controlemodus gebruiken om te rapporteren wanneer een mogelijk ongewenste toepassing wordt geïnstalleerd. Zie [Windows 10-beleidsinstellingen in Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune) voor meer informatie.
<!---TFS 1244478--->

### <a name="conditional-access"></a>Voorwaardelijke toegang
- **Cisco ISE-netwerktoegangscontrolebeleid voor Intune.**  Klanten die Cisco Identity Service Engine (ISE) 2.1 en Microsoft Intune gebruiken, kunnen een netwerktoegangsbeleid instellen in ISE.

    Met dit beleid moeten apparaten die via Wi-Fi of VPN verbinding willen maken met het netwerk, voldoen aan de volgende voorwaarden voordat ze toegang krijgen:

    * Moeten worden beheerd met Intune
    * Moeten voldoen aan geïmplementeerd Intune-nalevingsbeleid

 Eindgebruikers van niet-compatibele apparaten wordt gevraagd zich te registreren en nalevingsproblemen op te lossen om toegang te krijgen.
- **Voorwaardelijke toegang voor de browser.** U kunt een beleid voor voorwaardelijke toegang instellen voor [Exchange Online](/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune) en [SharePoint Online](/intune/deploy-use/restrict-access-to-sharepoint-online-with-microsoft-intune), zodat deze alleen toegankelijk zijn via ondersteunde webbrowsers op beheerde en compatibele iOS- en Android-apparaten. Eindgebruikers die proberen zich met iOS- en Android-apparaten aan te melden bij Outlook Web Access (OWA) en SharePoint-sites, wordt gevraagd hun apparaat te registreren bij Intune en eventuele problemen met de compatibiliteit op te lossen. Hierna kan de aanmelding worden voltooid.
<!---TFS 1175844--->

- **Dynamics CRM Online biedt ondersteuning voor voorwaardelijke toegang.** U kunt beleid voor voorwaardelijke toegang instellen voor [Dynamics CRM Online](/intune/deploy-use/restrict-access-to-dynamics-crm-online-with-microsoft-intune), zodat dit alleen toegankelijk is voor beheerde en compatibele iOS- en Android-apparaten. Eindgebruikers die zich op iOS en Android willen aanmelden bij de mobiele app Dynamics CRM, moeten zich registreren bij Intune en eventuele problemen met de naleving oplossen voordat de aanmelding wordt voltooid.
<!---TFS1295358--->

### <a name="intune-company-portal-updates"></a>Updates voor de Intune-bedrijfsportal

__Android-bedrijfsportal-app__

- Wanneer IT-beheerders het nieuwe beleid Vereisen dat apparaten de installatie van apps van onbekende bronnen niet toestaan (Android 4.0+) toepassen, krijgen eindgebruikers met een apparaat met Android 4.0 of hoger het volgende bericht te zien: De installatie vanuit onbekende bronnen moet worden uitgeschakeld. Gebruikers moeten naar **Instellingen** > **Beveiliging** gaan en **Onbekende bronnen** uitschakelen. Via een koppeling in het nalevingsbericht kunnen gebruikers meer [informatie](/Intune/EndUser/you-are-asked-to-turn-off-unknown-sources-android) verkrijgen over het bericht en over waarom ze de instelling moeten uitschakelen.

- Wanneer IT-beheerders het nieuwe beleid Vereisen dat apparaten het scannen van apps op beveiligingsrisico's inschakelen (Android 4.0+) toepassen, krijgen eindgebruikers met een apparaat met Android 4.0 of hoger het volgende bericht te zien: Apparaat scannen op beveiligingsrisico's. Gebruikers moeten naar **Instellingen** > **Google** > **Beveiliging** gaan en **Apparaat scannen op beveiligingsrisico's** inschakelen. Via een koppeling in het nalevingsbericht kunnen gebruikers meer [informatie](/Intune/EndUser/you-are-asked-to-turn-on-scan-device-for-security-threats-android) verkrijgen over het bericht en over waarom ze de instelling moeten inschakelen.

- Wanneer IT-beheerders het nieuwe beleid Vereisen dat USB-foutopsporing wordt uitgeschakeld (Android 4.2+) toepassen, krijgen eindgebruikers met een apparaat met Android 4.2 of hoger het volgende bericht te zien: USB-foutopsporing moet worden uitgeschakeld. Gebruikers moeten naar **Instellingen** > **Opties voor ontwikkelaars** gaan en **USB-foutopsporing** uitschakelen. Via een koppeling in het nalevingsbericht kunnen gebruikers meer [informatie](/Intune/EndUser/you-are-asked-to-turn-off-usb-debugging-android) verkrijgen over het bericht en over waarom ze de instelling moeten uitschakelen.

- Wanneer IT-beheerders het nieuwe beleid Minimaal niveau voor de Android-beveiligingspatch (Android 6.0+) toepassen, krijgen eindgebruikers met een apparaat met Android 6.0 of hoger het volgende bericht te zien: Dit apparaat voldoet niet aan het minimale Android-beveiligingspatchniveau. Gebruikers moeten de vereiste beveiligingspatch installeren. Via een koppeling in het nalevingsbericht kunnen gebruikers meer [informatie](/Intune/EndUser/you-are-asked-to-turn-on-scan-device-for-security-threats-android) verkrijgen over hoe de vereiste beveiligingspatch moet worden geïnstalleerd en over welke beveiligingspatch momenteel is geïnstalleerd.

__iOS-bedrijfsportal-app__

- Eindgebruikers die LOB-apps installeren, hebben nu een verbeterde ervaring tijdens de installatie van deze apps. Als de app-installatie lang duurt, kunnen gebruikers hun apparaat handmatig synchroniseren om hervatting van het synchronisatieproces af te dwingen. Zie [Sync your iOS device manually](/Intune/EndUser/sync-your-device-manually-ios) (Uw iOS-apparaat handmatig synchroniseren) voor de instructies voor eindgebruikers.

- De Microsoft Intune-bedrijfsportal-app voor iOS is bijgewerkt. Nu wordt iOS-versie 8.0 en hoger ondersteund. Deze update betekent dat eindgebruikers de bedrijfsportal-app kunnen installeren en alleen nieuwe apparaten kunnen registreren bij Intune als het apparaat iOS-versie 8.0 of hoger heeft. Gebruikers die werken met eerder ingeschreven apparaten met niet-ondersteunde versie van iOS kunnen de bedrijfsportal-app die op hun apparaat is geïnstalleerd blijven gebruiken.


<!--HONumber=Dec16_HO1-->


