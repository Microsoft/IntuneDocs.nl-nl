## <a name="march-2017"></a>Maart 2017

### <a name="new-capabilities"></a>Nieuwe mogelijkheden

#### <a name="support-for-skycure"></a>Ondersteuning voor Skycure

U kunt nu de toegang van mobiele apparaten tot bedrijfsresources beheren door middel van voorwaardelijke toegang op basis van een risicoanalyse die door Skycure wordt uitgevoerd. Skycure is een oplossing voor de beveiliging tegen bedreigingen op mobiele apparaten die met Microsoft Intune is geïntegreerd. Risico's worden beoordeeld op basis van telemetrische gegevens die zijn verzameld op apparaten met Skycure, zoals:

- Fysieke beveiliging
- Netwerkbeveiliging
- Toepassingsbeveiliging
- Beveiliging tegen zwakke plekken

U kunt het EMS-beleid voor voorwaardelijke toegang configureren op basis van de risicoanalyse van Skycure die wordt ingeschakeld via het Intune-nalevingsbeleid voor apparaten. U kunt aan de hand van dit beleid de toegang van apparaten die niet voldoen aan het beleid tot bedrijfsresources toestaan of blokkeren op basis van de gedetecteerde bedreigingen. Zie [Skycure Mobile Threat Defense-connector](/intune/deploy-use/skycure-mobile-threat-defense-connector) voor meer informatie.

#### <a name="new-user-experience-for-the-company-portal-app-for-android---621622--"></a>Nieuwe gebruikerservaring voor de bedrijfsportal-app voor Android <!--621622-->

Voor de bedrijfsportal-app voor Android wordt een update uitgevoerd voor de gebruikersinterface om deze er moderner te laten uitzien en om een betere gebruikerservaring te bieden. De belangrijkste updates zijn:

- Kleuren: de tabbladkoppen van de bedrijfsportal-app hebben de kleuren van de door de IT opgegeven huisstijl.
- Apps: op het tabblad **Apps** zijn de knoppen **Aanbevolen apps** en **Alle apps** bijgewerkt.
- Zoeken: op het tabblad **Apps** is de knop **Zoeken** nu een zwevende actieknop.
- Navigeren door apps: in de weergave **Alle apps** wordt tabbladen getoond voor de opties **Aanbevolen**, **Alle** en **Categorieën** om de navigatie te vereenvoudigen.
- Ondersteuning: de tabbladen **Mijn apparaten** en **Contact opnemen met IT** zijn bijgewerkt om de leesbaarheid te vergroten.

Zie [UI-updates voor Intune-apps voor eindgebruikers](/intune/whats-new/whats-new-in-intune-app-ui) voor meer informatie over deze wijzigingen.

#### <a name="non-managed-devices-can-access-assigned-apps---664691--"></a>Niet-beheerde apparaten hebben toegang tot toegewezen apps <!--664691-->

Als onderdeel van de ontwerpwijzigingen op de bedrijfsportalwebsite kunnen iOS- en Android-gebruikers op hun niet-beheerde apparaten apps installeren die aan hen zijn toegewezen als 'beschikbaar zonder inschrijving'. Gebruikers kunnen zich met behulp van hun Intune-referenties aanmelden bij de bedrijfsportalwebsite en de lijst met aan hen toegewezen apps bekijken. De app-pakketten van de 'beschikbaar zonder inschrijving'-apps kunnen worden gedownload via de bedrijfsportalwebsite. Deze wijziging is niet van toepassing op apps die pas na inschrijving kunnen worden geïnstalleerd, omdat gebruikers wordt gevraagd hun apparaat in te schrijven als zij deze apps willen installeren.

#### <a name="signing-script-for-windows-10-company-portal---941642--"></a>Ondertekeningsscript voor de Windows 10-bedrijfsportal <!--941642-->

Als u de Windows 10-bedrijfsportal-app moet downloaden en sideloaden, kunt u nu een script gebruiken om het proces voor het ondertekenen van apps voor uw organisatie te vereenvoudigen en stroomlijnen.   Raadpleeg [Microsoft Intune Signing Script](https://aka.ms/win10cpscript) (Ondertekeningsscript voor Microsoft Intune) voor de Windows 10-bedrijfsportal in de TechNet-galerie voor het downloaden van het script en meer informatie over het gebruik ervan. Raadpleeg [Updating your Windows 10 Company Portal app](https://blogs.technet.microsoft.com/intunesupport/2017/03/13/updating-your-windows-10-company-portal-app/) (Uw Windows 10-bedrijfsportal-app bijwerken) in het Intune Support-teamweblog voor meer informatie over deze mededeling.


### <a name="notices"></a>Mededelingen

#### <a name="support-for-ios-103"></a>Ondersteuning voor iOS 10.3

Op 27 maart 2017 is begonnen met het uitrollen van de iOS 10.3-release voor iOS-gebruikers. Alle bestaande Intune MDM- en MAM-scenario's zijn compatibel met de nieuwste versie van het besturingssysteem van Apple. We verwachten dat alle bestaande Intune-functies die momenteel beschikbaar zijn voor het beheer van iOS-apparaten gewoon blijven werken wanneer de gebruikers hun apparaten en apps upgraden naar iOS 10.3.

Er zijn momenteel geen problemen bekend. Als u problemen ondervindt met iOS 10.3, neemt u contact op met het [Intune-ondersteuningsteam](/intune/troubleshoot/contact-assisted-phone-support-for-microsoft-intune).

#### <a name="improved-support-for-android-users-based-in-china---720444--"></a>Verbeterde ondersteuning voor Android-gebruikers in China <!--720444-->

Vanwege de afwezigheid van de Google Play Store in China kunnen Android-apparaten apps alleen verkrijgen via Chinese-marktplaatsen. De bedrijfsportal ondersteunt deze werkstroom door Android-gebruikers in China om te leiden zodat ze de bedrijfsportal- en Outlook-apps kunnen downloaden in lokale App Stores. Dit verbetert de gebruikerservaring wanneer beleidsregels voor voorwaardelijke toegang zijn ingeschakeld, zowel voor Mobile Device Management als voor Mobile Application Management. De bedrijfsportal- en Outlook-apps voor Android zijn beschikbaar via de volgende Chinese App Stores:

- [Baidu](https://go.microsoft.com/fwlink/?linkid=836946)
- [Xiaomi](https://go.microsoft.com/fwlink/?linkid=836947)
- [Tencent](https://go.microsoft.com/fwlink/?linkid=836949)
- [Huawei](https://go.microsoft.com/fwlink/?linkid=836948)
- [Wandoujia](https://go.microsoft.com/fwlink/?linkid=836950)

#### <a name="best-practice-make-sure-your-company-portal-apps-are-up-to-date---879465--"></a>Aanbevolen procedure: zorg ervoor dat de bedrijfsportal-apps zijn bijgewerkt<!--879465-->

In December 2016 is een update uitgebracht waarmee Multi-Factor Authentication (MFA) kan worden afgedwongen op een groep gebruikers wanneer deze een iOS-, Android-, Windows 8.1+- of Windows Phone 8.1+-apparaat inschrijven. Deze functie kan niet werken zonder bepaalde basislijnversies van de bedrijfsportal-app voor Android (v5.0.3419.0 +) en iOS (v2.1.17 +).

Microsoft verbetert Intune voortdurend door het toevoegen van nieuwe functies aan zowel de console als de bedrijfsportal-apps op alle ondersteunde platforms. Microsoft publiceert als gevolg hiervan alleen oplossingen voor problemen die in de huidige versie van de bedrijfsportal-app worden aangetroffen. Het wordt daarom aanbevolen de nieuwste versies van de bedrijfsportal-apps te gebruiken voor de beste gebruikerservaring.

>[!Tip]
> Laat uw gebruikers hun apparaten zodanig instellen dat deze automatisch apps bijwerken uit de betreffende app store. Als u de Android-bedrijfsportal-app beschikbaar hebt gesteld op een netwerkshare, kunt u de meest recente versie downloaden van [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=49140).

#### <a name="microsoft-teams-is-now-enabled-for-mam-on-ios-and-android"></a>Microsoft Teams is nu ingeschakeld voor MAM op iOS en Android

Microsoft heeft de algemene beschikbaarheid van Microsoft Teams aangekondigd. De bijgewerkte Microsoft Teams-apps voor iOS en Android zijn nu beschikbaar met de mogelijkheden van Intune Mobile App Management (MAM), zodat u uw teams in staat kunt stellen op verschillende apparaten te werken, terwijl conversaties en bedrijfsgegevens altijd beveiligd blijven. Zie [de aankondiging over Microsoft Teams](https://blogs.technet.microsoft.com/enterprisemobility/2017/03/14/microsoft-teams-is-now-generally-available-and-mam-enabled-on-ios-and-android/) op het Enterprise Mobility and Security Blog voor meer informatie.


## <a name="february-2017"></a>Februari 2017

### <a name="new-capabilities"></a>Nieuwe mogelijkheden

### <a name="modernizing-the-company-portal-website---753980--"></a>De bedrijfsportalwebsite moderniseren <!--753980-->
De bedrijfsportalwebsite ondersteunt apps die zijn gericht op gebruikers die geen beheerde apparaten hebben. De website wordt in overeenstemming gebracht met andere Microsoft-producten en -services met een nieuw contrasterend kleurenschema, dynamische illustraties en een 'hamburgermenu', ![Kleine afbeelding van het hamburgermenu dat nu is toegevoegd in de linkerbovenhoek van de bedrijfsportalwebsite](/intune/whats-new/media/CP_hamburger_menu.png) dat contactgegevens van de helpdesk bevat, alsmede informatie over bestaande beheerde apparaten. De landingspagina wordt opnieuw ingedeeld om de nadruk te leggen op apps die beschikbaar zijn voor gebruikers, met carrousels voor uitgelichte en recent bijgewerkte apps. De [pagina met UI-updates](/intune/whats-new/whats-new-in-intune-app-ui) bevat voor-en-na afbeeldingen.

### <a name="notices"></a>Mededelingen

#### <a name="group-migration-will-not-require-any-updates-to-groups-or-policies-for-ios-devices---898837--"></a>Bij groepsmigratie zijn geen updates voor groepen of beleidsregels vereist voor iOS-apparaten <!--898837-->
Voor elke Intune-apparaatgroep die vooraf is toegewezen door een inschrijvingsprofiel voor bedrijfsapparaten, wordt tijdens de migratie naar Azure Active Directory-apparaatgroepen een overeenkomende dynamische apparaatgroep in AAD gemaakt op basis van de naam van het inschrijvingsprofiel. Dit zorgt ervoor dat apparaten wanneer ze worden ingeschreven automatisch worden gegroepeerd en hetzelfde beleid en dezelfde apps ontvangen als de oorspronkelijke Intune-groep.

Wanneer een tenant in het migratieproces wordt ingevoerd voor groepering en targeting, wordt in Intune automatisch een dynamische AAD-groep gemaakt die overeenkomt met een Intune-groep waarop een inschrijvingsprofiel voor bedrijfsapparaten is gericht. Als de Intune-beheerder de betreffende Intune-groep verwijdert, wordt de overeenkomende dynamische AAD-groep niet verwijderd. Leden van de groep en de dynamische query worden gewist, maar de groep zelf blijft aanwezig totdat de IT-beheerder deze via de AAD-portal verwijdert.

Ook als de IT-beheerder de Intune-groep wijzigt waarop een inschrijvingsprofiel voor bedrijfsapparaten is gericht, wordt in Intune een nieuwe dynamische groep gemaakt op basis van de nieuwe profieltoewijzing en wordt de dynamische groep die werd gemaakt voor de oude toewijzing niet verwijderd.

### <a name="defaulting-to-managing-windows-desktop-devices-through-windows-settings---663050--"></a>Standaardinstelling voor het beheren van Windows-desktops via Windows-instellingen <!--663050-->
Het standaardgedrag voor het registreren van Windows 10-desktops verandert. Nieuwe registraties volgen het standaardproces van registratie via de MDM-agent in plaats van via de pc-agent. De bedrijfsportalwebsite biedt gebruikers van Windows 10-desktops registratie-instructies om ze te helpen bij het toevoegen van Windows 10-desktopcomputers als mobiele apparaten. Dit heeft geen gevolgen voor momenteel ingeschreven pc's en met behulp van de pc-agent kan uw organisatie nog altijd Windows 10-desktops beheren [als u dat liever hebt](/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune).

#### <a name="improving-mobile-app-management-support-for-selective-wipe---581242--"></a>Verbetering van MAM-ondersteuning voor selectief wissen <!--581242-->
Eindgebruikers krijgen extra informatie over het verkrijgen van toegang tot werk- of schoolgegevens als die gegevens automatisch worden verwijderd op basis van het beleid 'Offline interval voordat app-gegevens worden gewist'.<!--, or the removal of the Intune Company Portal on Android.-->

#### <a name="company-portal-for-ios-links-open-inside-the-app---665954--"></a>Bedrijfsportal voor iOS-koppelingen openen in de app <!--665954-->
Koppelingen in de bedrijfsportal-app voor iOS, inclusief koppelingen naar documentatie en apps, worden rechtstreeks in de bedrijfsportal-app geopend met behulp van in-app-weergave van Safari. Deze update wordt afzonderlijk van de service-update in januari verzonden.

#### <a name="new-mdm-server-address-for-windows-devices---893007--"></a>Nieuw MDM-serveradres voor Windows-apparaten <!--893007-->
Wanneer Windows- en Windows Phone-gebruikers een apparaat willen inschrijven, mislukt dit als ze (desgevraagd) __manage.microsoft.com__ invullen als het MDM-serveradres. Het MDM-serveradres is gewijzigd van __manage.microsoft.com__ in __enrollment.manage.microsoft.com__. Stel uw gebruikers ervan op de hoogte dat ze __enrollment.manage.microsoft.com__ moeten gebruiken als het MDM-serveradres als dit wordt gevraagd tijdens het inschrijven van een Windows- of Windows Phone-apparaat. Uw CNAME-instellingen hoeven niet te worden gewijzigd. Ga voor meer informatie over deze wijziging naar [aka.ms/intuneenrollsvrchange](https://aka.ms/intuneenrollsvrchange).

#### <a name="new-user-experience-for-the-company-portal-app-for-android---621622--"></a>Nieuwe gebruikerservaring voor de bedrijfsportal-app voor Android <!--621622-->
Vanaf maart volgt de bedrijfsportal-app voor Android [richtlijnen voor het ontwerpen van materiaal](https://material.io/guidelines/material-design/introduction.html) voor een moderne vormgeving. Deze verbeterde gebruikerservaring omvat het volgende:

* __Kleuren__: tabbladkoppen kunnen worden gekleurd volgens uw aangepaste kleurenpalet.
* __Interface__: de knoppen Aanbevolen apps en Alle apps op het tabblad Apps zijn bijgewerkt. De knop Zoeken is nu een zwevende actieknop.
* __Navigatie__: Alle apps biedt een tabbladweergave van de opties Aanbevolen, Alle en Categorieën om de navigatie te vereenvoudigen.
* __Service__: de leesbaarheid van de tabbladen Mijn apparaten en Contact opnemen met IT is verbeterd.

De [pagina met UI-updates](/intune/whats-new/whats-new-in-intune-app-ui) bevat voor-en-na afbeeldingen.

### <a name="associate-multiple-management-tools-with-the-windows-store-for-business---926135--"></a>Meerdere beheerhulpprogramma's koppelen aan de Windows Store voor Bedrijven<!--926135-->
Als u meer dan één beheerhulpprogramma voor het implementeren van Windows Store voor Bedrijven-apps gebruikt, kon u voorheen slechts één van deze programma’s koppelen met de Windows Store voor Bedrijven. U kunt nu meerdere beheerhulpprogramma's met de Store koppelen, bijvoorbeeld Intune en Configuration Manager. Zie [Apps die u hebt aangeschaft in de Windows Store voor Bedrijven, beheren met Microsoft Intune](/intune/deploy-use/manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune#associate-your-windows-store-for-business-account-with-intune) voor meer informatie.

## <a name="whats-new-in-the-public-preview-of-the-intune-admin-experience-on-azure---736542--"></a>Wat is er nieuw in de openbare preview-versie van de nieuwe Intune-ervaring voor beheerders in Azure <!--736542-->

Aan het begin van kalenderjaar 2017 migreren we de volledige functionaliteit voor beheerders naar Azure, voor krachtig en geïntegreerd beheer van EMS-kernwerkstromen op een modern serviceplatform dat kan worden uitgebreid met Graph API’s.

Vanaf deze maand zal de openbare preview-versie van de nieuwe beheerderservaring te zien zijn voor nieuwe evaluatietenants in de Azure-portal. Tijdens de preview-periode worden de mogelijkheden en pariteit met de bestaande Intune-console iteratief geleverd.

De beheerderservaring in de Azure-portal zal gebruikmaken van de eerder aangekondigde nieuwe functionaliteit voor groepen en targeting. Wanneer uw bestaande tenant wordt gemigreerd naar de nieuwe ervaring voor groepen, vindt ook de migratie plaats naar de preview-versie van de nieuwe beheerderservaring. Als u in de tussentijd de nieuwe functionaliteit wilt testen of bekijken totdat de migratie van uw tenant is voltooid, kunt u zich aanmelden voor een nieuw Intune-evaluatieaccount of de [nieuwe documentatie](/intune-azure/introduction/whats-new) raadplegen.

U kunt [hier](/intune-azure/introduction/whats-new) vinden wat er nieuw is in de Intune-preview-versie in Azure.

## <a name="january-2017"></a>Januari 2017

### <a name="new-capabilities"></a>Nieuwe mogelijkheden

#### <a name="in-console-reports-for-mam-without-enrollment---677961--"></a>Interne consolerapporten voor MAM zonder registratie<!--677961-->
Er zijn nieuwe rapporten voor app-beveiliging toegevoegd voor zowel geregistreerde als niet-geregistreerde apparaten. [Meer informatie over hoe u MAM-beleid met Intune kunt bewaken vindt u hier](/intune/deploy-use/monitor-mobile-app-management-policies-with-microsoft-intune).

#### <a name="android-711-support---694397--"></a>Android 7.1.1-ondersteuning <!--694397-->
Intune biedt nu volledige ondersteuning en volledig beheer voor Android 7.1.1.

#### <a name="resolve-issue-where-ios-devices-are-inactive-or-the-admin-console-cannot-communicate-with-them---unknown--"></a>Oplossing voor het probleem waarbij iOS-apparaten inactief zijn of waarbij de beheerconsole er niet mee kan communiceren <!--unknown-->
Wanneer het contact tussen de apparaten van gebruikers en Intune verloren gaat, kunt u de gebruikers stappen voor probleemoplossing aandragen waarmee ze weer toegang krijgen tot de bedrijfsresources. Zie [Apparaten zijn inactief of de beheerconsole kan er niet mee communiceren](/intune/troubleshoot/troubleshoot-device-enrollment-in-intune#devices-are-inactive-or-the-admin-console-cannot-communicate-with-them).

### <a name="notices"></a>Mededelingen

#### <a name="defaulting-to-managing-windows-desktop-devices-through-windows-settings---663050--"></a>Standaardinstelling voor het beheren van Windows-desktops via Windows-instellingen <!--663050-->
Het standaardgedrag voor het registreren van Windows 10-desktops verandert. Nieuwe registraties volgen het standaardproces van registratie via de MDM-agent in plaats van via de pc-agent.

De bedrijfsportalwebsite biedt gebruikers van Windows 10-desktops registratie-instructies om ze te helpen bij het toevoegen van Windows 10-desktopcomputers als mobiele apparaten. Dit heeft geen gevolgen voor momenteel ingeschreven pc's en met behulp van de pc-agent kan uw organisatie nog altijd Windows 10-desktops beheren [als u dat liever hebt](/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune).

#### <a name="improving-mobile-app-management-support-for-selective-wipe---581242--"></a>Verbetering van MAM-ondersteuning voor selectief wissen <!--581242-->
Eindgebruikers krijgen extra informatie over het verkrijgen van toegang tot werk- of schoolgegevens als die gegevens automatisch worden verwijderd op basis van het beleid 'Offline interval voordat app-gegevens worden gewist'.<!--, or the removal of the Intune Company Portal on Android.-->

#### <a name="company-portal-for-ios-links-open-inside-the-app---665954--"></a>Bedrijfsportal voor iOS-koppelingen openen in de app <!--665954-->
Koppelingen in de bedrijfsportal-app voor iOS, inclusief koppelingen naar documentatie en apps, worden rechtstreeks in de bedrijfsportal-app geopend met behulp van in-app-weergave van Safari. Deze update wordt afzonderlijk van de service-update in januari verzonden.

#### <a name="modernizing-the-company-portal-website---753980--"></a>De bedrijfsportalwebsite moderniseren <!--753980-->
Te beginnen in februari ondersteunt de bedrijfsportalwebsite apps die zijn gericht op gebruikers die geen beheerde apparaten hebben. De website wordt in overeenstemming gebracht met andere Microsoft-producten en -services met een nieuw contrasterend kleurenschema, dynamische illustraties en een ‘hamburgermenu’, ![hamburgermenu van de bedrijfsportalwebsite](/intune/whats-new/media/CP_hamburger_menu.png) dat contactgegevens van de helpdesk bevat, alsmede informatie over bestaande beheerde apparaten. De landingspagina wordt opnieuw ingedeeld om de nadruk te leggen op apps die beschikbaar zijn voor gebruikers, met carrousels voor uitgelichte en recent bijgewerkte apps. U kunt voor-en-na-afbeeldingen vinden op de pagina [What's new in the Intune app UI](/intune/whats-new/whats-new-in-intune-app-ui).

#### <a name="new-documentation-for-app-protection-policies---583398--"></a>Nieuwe documentatie voor app-beveiligingsbeleid<!--583398-->
We hebben de documentatie bijgewerkt voor beheerders en app-ontwikkelaars die beleid voor app-beveiliging (ook wel MAM-beleid genoemd) willen inschakelen in hun iOS- en Android-apps met behulp van de Intune App Wrapping Tool of Intune App SDK.

De volgende artikelen zijn bijgewerkt:

* [Bepalen hoe u apps voorbereidt op Mobile Application Management met Microsoft Intune](/intune/deploy-use/decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune)
* [iOS-apps voorbereiden voor Mobile Application Management met de Intune App Wrapping Tool](/intune/deploy-use/prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool)
* [Aan de slag met de Microsoft Intune App SDK](/intune/develop/intune-app-sdk-get-started)
* [Ontwikkelaarshandleiding voor Intune App SDK voor iOS](/intune/develop/intune-app-sdk-ios)

De volgende artikelen zijn nieuwe toevoegingen aan de documentenbibliotheek:

* [Intune App SDK Cordova-invoegtoepassing](/intune/develop/intune-app-sdk-cordova)
* [Intune App SDK Xamarin-onderdeel](/intune/develop/intune-app-sdk-xamarin)

#### <a name="progress-bar-when-launching-the-company-portal-on-ios---665978--"></a>Voortgangsbalk bij het starten van de bedrijfsportal in iOS <!--665978-->
De bedrijfsportal voor iOS introduceert een voortgangsbalk op het startscherm met informatie voor de gebruiker over het laden van processen die optreden. Er is een gefaseerde rollout van de voortgangsbalk als vervanging van het kringveld. Dit betekent dat sommige van uw gebruikers de nieuwe voortgangsbalk te zien krijgen, terwijl anderen blijven het kringveld blijven zien.

## <a name="december-2016"></a>December 2016

### <a name="public-preview-of-the-new-intune-admin-experience-on-azure---736542--"></a>Openbare preview-versie van de nieuwe Intune-ervaring voor beheerders op Azure <!--736542-->
Aan het begin van kalenderjaar 2017 migreren we de volledige functionaliteit voor beheerders naar Azure, voor krachtig en geïntegreerd beheer van EMS-kernwerkstromen op een modern serviceplatform dat kan worden uitgebreid met Graph API’s. Voordat deze portal algemeen beschikbaar wordt voor alle Intune-tenants, zullen we later deze maand een preview van deze nieuwe beheerderservaring uitrollen voor een select aantal tenants.

De beheerderservaring in de Azure-portal zal gebruikmaken van de eerder aangekondigde nieuwe functionaliteit voor groepen en targeting. Wanneer uw bestaande tenant wordt gemigreerd naar de nieuwe ervaring voor groepen, vindt ook de migratie plaats naar de preview-versie van de nieuwe beheerderservaring. In de tussentijd vindt u in Azure Portal [nieuwe documentatie](/intune-azure/introduction/what-is-microsoft-intune) met meer informatie over wat we in petto hebben voor Microsoft Intune.

__Integratie van systemen voor onkostenbeheer voor telecom in de openbare preview van Azure Portal__ <!--747605--> We beginnen nu met proeven met de integratie met externe systemen voor onkostenbeheer voor telecom (TEM) in Azure Portal. U kunt Intune gebruiken om limieten in te stellen voor gegevensgebruik, voor zowel nationaal als roaming. Hierbij beginnen we met [Saaswedo](http://www.saaswedo.com). Als u deze functie in uw proeftenant wilt inschakelen, neemt u [contact op met Microsoft-ondersteuning](/intune/troubleshoot/how-to-get-support-for-microsoft-intune).

### <a name="new-capabilities"></a>Nieuwe mogelijkheden

__Multi-Factor Authentication op alle platformen__ <!--747590--> U kunt nu Multi-Factor Authentication (MFA) afdwingen voor een geselecteerde groep gebruikers, wanneer zij een apparaat met iOS, Android, Windows 8.1+ of Windows Phone 8.1+ inschrijven bij de Azure-beheerportal. Dit doet u door MFA te configureren voor Microsoft Intune-inschrijving in Azure Active Directory.

__Mogelijkheid om de inschrijving van mobiele apparaten te beperken__ <!--747596--> Er zijn in Intune nieuwe inschrijvingsbeperkingen toegevoegd waarmee u bepaalt welke platformen voor mobiele apparaten kunnen worden ingeschreven. Intune onderscheidt platforms voor mobiele apparaten als iOS, Mac OS, Android, Windows en Windows Mobile.
* Een beperking voor de registratie van mobiele apparaten, betekent niet dat de PC-clientregistratie ook is beperkt.
* Alleen voor iOS geldt er een extra optie voor het blokkeren van de inschrijving van apparaten die in persoonlijk eigendom zijn.

Intune markeert alle nieuwe apparaten als persoonlijk, tenzij de IT-beheerder actie onderneemt om deze te markeren als bedrijfseigen, zoals uitgelegd in [dit artikel](/intune/deploy-use/manage-corporate-owned-devices).

### <a name="notices"></a>Mededelingen

__Multi-Factor Authentication voor inschrijving verplaatst naar Azure Portal__ <!--VSO 750545--> Tot nu toe maakten beheerders gebruik van de Intune-console of de Configuration Manager-console (vóór de release oktober 2016) om Multi-Factor Authentication in te stellen voor Intune-inschrijvingen. Met deze bijgewerkte functie kunt u zich aanmelden bij de [Microsoft Azure-portal](https://manage.windowsazure.com) met uw Intune-referenties en de instellingen voor meervoudige verificatie configureren via Azure AD. Meer informatie hierover vindt u [hier](https://aka.ms/mfa_ad).

__Bedrijfsportal-app voor Android is nu beschikbaar in China__  <!--VSO 658093--> De bedrijfsportal-app voor Android kan vanaf nu worden gedownload in China. Vanwege de afwezigheid van Google Play Store in China kunnen Android-apparaten apps alleen verkrijgen via Chinese app-marktplaatsen. De bedrijfsportal-app voor Android kan nu worden gedownload via de volgende stores:
* [Baidu](https://go.microsoft.com/fwlink/?linkid=836946)
* [Huawei](https://go.microsoft.com/fwlink/?linkid=836948)
* [Tencent](https://go.microsoft.com/fwlink/?linkid=836949)
* [Wandoujia](https://go.microsoft.com/fwlink/?linkid=836950)
* [Xiaomi](https://go.microsoft.com/fwlink/?linkid=836947)

De bedrijfsportal-app voor Android maakt gebruik van Google Play Services om te communiceren met de Microsoft Intune-service. Omdat Google Play Services nog niet beschikbaar is in China, kan het tot wel acht uur duren voordat de volgende taken zijn voltooid. 

|Intune-beheerconsole| Intune bedrijfsportal-app voor Android |Intune-bedrijfsportalwebsite|   
|---|---|---|
|Volledig wissen| Een extern apparaat verwijderen| Apparaat verwijderen (lokaal en extern)|
|Selectief wissen| Apparaat opnieuw instellen| Apparaat opnieuw instellen|
|Nieuwe of bijgewerkte app-implementaties| Installeren van beschikbare line-of-business-apps| Wachtwoordcode van apparaat opnieuw instellen|
|Vergrendelen op afstand|||
|Wachtwoordcode opnieuw instellen|||

### <a name="deprecations"></a>Afschaffingen

__Firefox biedt geen ondersteuning meer voor Silverlight__ <!--VSO TBA--> Mozilla verwijdert per maart 2017 de ondersteuning voor Silverlight in versie 52 van de [Firefox-browser](https://www.mozilla.org/firefox). Als gevolg hiervan kunt u zich niet meer aanmelden bij de bestaande Intune-console wanneer u een latere versie dan Firefox 51 gebruikt. U kunt het beste Internet Explorer 10 of 11 voor toegang tot de beheerconsole, of een [eerdere versie dan Firefox 52](https://ftp.mozilla.org/pub/firefox/releases/). Met de overgang van Intune naar Azure Portal worden een aantal [moderne browsers](/azure/azure-preview-portal-supported-browsers-devices) ondersteund zonder afhankelijkheid van Silverlight.

__Verwijdering van het beleid voor mobiele postvakken van Exchange Online__ <!--770687--> Vanaf december kunnen beheerders het beleid voor mobiele postvakken van Exchange Online (EAS) niet langer weergeven en configureren in de Intune-console. Deze wijziging wordt geïmplementeerd voor alle Intune-tenants in december en januari. De configuratie van bestaande beleidsregels blijft onveranderd. Voor het configureren van nieuw beleid maakt u gebruikt van de Exchange Management Shell. Meer informatie vindt u [hier](https://technet.microsoft.com/library/bb123783%28v=exchg.150%29.aspx).

__Intune AV-speler, de afbeeldingsviewer en de PDF-viewer worden niet meer ondersteund op Android__ <!--747553--> Vanaf half december 2016 zijn de Intune AV-speler, afbeeldingsviewer en PDF-viewer niet langer beschikbaar voor gebruikers. Deze apps zijn vervangen door de app Azure Information Protection. Meer informatie over Azure Information Protection vindt u [hier](/information-protection/rms-client/mobile-app-faq).

## <a name="november-2016"></a>November 2016

### <a name="new-capabilities"></a>Nieuwe mogelijkheden

__Nieuwe Microsoft Intune-bedrijfsportal voor Windows 10-apparaten__ Microsoft heeft een nieuwe [Microsoft Intune-bedrijfsportal voor Windows 10-apparaten](https://www.microsoft.com/store/apps/9wzdncrfj3pz) uitgebracht. Deze app maakt gebruik van de Windows 10 Universal-indeling en biedt gebruikers een bijgewerkte gebruikerservaring in de app zelf, en een identieke gebruikerservaring op alle Windows 10-apparaten (pc en mobiel), met behoud van de functionaliteit die ze momenteel gebruiken.

Met de nieuwe app kunnen gebruikers van Windows 10-apparaten ook gebruikmaken van aanvullende functies van het platform, zoals eenmalige aanmelding (SSO) en verificatie op basis van certificaten. De app wordt beschikbaar gesteld als een upgrade van de bestaande Windows 8.1-bedrijfsportal en Windows Phone 8.1-bedrijfsportal in de Windows Store. Zie [aka.ms/intunecp_universalapp](http://aka.ms/intunecp_universalapp) voor meer informatie.

> [!IMPORTANT]
> __Een update voor Intune en Android for Work__ Hoewel u Android for Work-apps kunt implementeren met de actie __Vereist__, kunt u apps alleen implementeren als __Beschikbaar__ als uw Intune-groepen zijn gemigreerd naar de nieuwe functie voor groepen van Azure AD.

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

[Lees de aankondiging van Microsoft over ondersteuning van Intune voor Android for Work](https://blogs.technet.microsoft.com/enterprisemobility/2016/09/12/microsoft-intune-support-for-android-for-work/).

De volgende onderwerpen voor Intune zijn nieuw, of bijgewerkt met informatie over Android for Work:

Voor IT-professionals:
- [Android for Work installeren](/intune/deploy-use/set-up-android-for-work)
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

Eindgebruikers van apparaten die niet voldoen aan het beleid, moeten hun apparaten inschrijven en de Lookout for Work-toepassing op Android-apparaten installeren, de app activeren en bedreigingen verhelpen die zijn gerapporteerd in de Lookout for Work-toepassing om toegang te krijgen. Zie voor meer informatie [Toegang beperken op basis van apparaat, netwerk en toepassingsrisico](/intune/deploy-use/device-threat-protection).


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
We hebben een nieuw [woordenlijstitem](/intune/understand-explore/intune-glossary) toegevoegd aan de bibliotheek om meer duidelijkheid te geven over de termen die worden gebruikt bij het Intune-product.

## <a name="august-2016"></a>Augustus 2016
### <a name="app-management"></a>Appbeheer

__Verborgen en weergegeven apps voor iOS 9.3__ Voor apparaten waarop iOS 9.3 of hoger wordt uitgevoerd, kunt u de lijst met verborgen of weergegeven apps in het algemene configuratiebeleid voor iOS gebruiken om het volgende te doen:
- Een lijst opstellen met apps die verborgen zijn voor gebruikers. Gebruikers kunnen deze apps niet weergeven of starten.
- Een lijst opstellen met apps die gebruikers kunnen weergeven en starten. Andere apps kunnen niet worden weergegeven of gestart.

De apps die u kunt opgeven zijn zowel apps die u hebt geïmplementeerd als de ingebouwde iOS-apps, zoals Berichten en Notities. Zie [Instellingen voor iOS-beleid in Microsoft Intune](/intune/deploy-use/ios-policy-settings-in-microsoft-intune) voor meer informatie.
<!---TFS 1279009 checked--->
__Beleid voor toegestane en geblokkeerde apps voor Samsung KNOX-apparaten__ U kunt nu een aangepast beleid voor Samsung KNOX-apparaten configureren om het volgende te maken:
- Een lijst met apps die niet kunnen worden uitgevoerd op het apparaat. Apps in deze lijst kunnen niet op het apparaat worden geactiveerd, ongeacht of ze daarop zijn geïnstalleerd.
- Een lijst met apps die gebruikers van het apparaat kunnen installeren uit de Google Play Store. Geen andere apps kunnen worden geïnstalleerd uit de Store.

Deze instellingen kunnen alleen worden gebruikt door apparaten met Samsung KNOX.
Zie [Aangepaste beleidsregels gebruiken om apps toe te staan of te blokkeren voor Samsung KNOX-apparaten](/intune/deploy-use/custom-policy-to-allow-and-block-samsung-knox-apps) voor meer informatie.
<!---TFS 1311629 checked --->

__Nieuwe apps die compatibel zijn met de beleidsregels van Mobile Application Management (MAM)__ De app Yammer voor [iOS](https://itunes.apple.com/app/yammer/id289559439?mt=8) en [Android](https://play.google.com/store/apps/details?id=com.yammer.v1) is nu compatibel met de [Intune MAM-beleidsregels (Mobile Application Management)](/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune), ongeacht of het apparaat is ingeschreven of niet.

Zie de website [Microsoft Intune-toepassingspartners](https://www.microsoft.com/cloud-platform/microsoft-intune-partners) voor een volledige lijst met apps die compatibel zijn met MAM.
<!--- TFS 1252335 & 1252336 checked--->

__Intune-viewer-apps__ Met het uitbrengen van de nieuwe RMS-app voor delen worden de volgende Intune-viewer-apps vanaf augustus 2016 verwijderd:
- Intune AV-viewer
- Intune PDF-viewer
- Intune-afbeeldingsviewer voor Android van Google Play

In plaats van de viewer-apps van Intune kunt u beter de nieuwe [Rights Management-app (RMS sharing) voor Android](/intune/deploy-use/end-user-experience-for-mam-enabled-apps-with-microsoft-intune#viewing-media-files-with-the-rights-management-sharing-app) gebruiken, zodat u één app in plaats van drie afzonderlijke apps kunt implementeren om veilig bedrijfsbestanden op Android-apparaten te bekijken. Als de Intune-viewer-app niet meer wordt ondersteund, wordt deze verwijderd uit de Google Store en zal deze niet meer beschikbaar zijn voor toekomstig gebruik.

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

- **Wijzigingen in de ondersteuning voor de iOS-bedrijfsportal-app**<br/>
In september moeten alle gebruikers van de Microsoft Intune-bedrijfsportal-app voor iOS overstappen naar de nieuwste versie. Nieuwe gebruikers kunnen alleen de nieuwste versie downloaden en bestaande gebruikers moeten bijwerken naar de nieuwe versie. De meest recente versie vereist iOS 8.0 of hoger, zodat apparaten met oudere versies van iOS de bedrijfsportal niet kunnen gebruiken en niet kunnen registreren totdat ze hun apparaat naar hebben bijgewerkt naar iOS 8.0 of hoger en vervolgens de bedrijfsportal-app bijwerken naar de nieuwste versie. Geregistreerde apparaten met een versie lager dan iOS 8.0 worden gewoon nog worden beheerd met en vermeld in de Intune-beheerconsole.  

- **Minimale iOS Managed Browser-versie is bijgewerkt naar 8.0**<br/>
In augustus brengt Intune een bijgewerkte Microsoft Intune Managed Browser-app uit voor iOS die alleen apparaten ondersteund waarop iOS 8.0 of later wordt uitgevoerd. Hoewel iOS 7.1-apparaten nog steeds de bestaande Managed Browser-app kunnen gebruiken, dient u uw gebruikers aan te moedigen bij te werken naar iOS 8.0 of later om volledig te kunnen profiteren van nieuwe functies van Managed Browser.  
<!---TFS 1313253--->

- **Bedrijfsportal-apps voor Windows 8 en Windows Phone 8 worden vanaf september 2016 afgeschaft** <br/>
Vanaf september 2016 biedt Microsoft Intune geen ondersteuning meer voor de Microsoft Intune-bedrijfsportal-apps voor Windows Phone 8 en Windows 8. Apparaten bijwerken naar Windows 8.1 en Windows Phone 8.1 en de bijbehorende bedrijfsportal-app voor Windows 8.1 en Windows Phone 8.1 gebruiken om door te gaan met het distribueren van apps naar deze apparaten.
<!---TFS 1255391--->
