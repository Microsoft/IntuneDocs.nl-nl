---
title: Wat is er nieuw in klassieke Microsoft Intune-portal (archief)
description: Wat is er nieuw in Microsoft Intune-aankondigingen (archief)
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 06/08/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ed2db991-4729-49a7-a1e6-be2ffa0d03d1
ROBOTS: noindex,nofollow
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.openlocfilehash: 5a76a54de62ead26ec4b3c7a8e34db3cd639b6c1
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/20/2018
ms.locfileid: "52181697"
---
# <a name="whats-new-in-the-intune-classic-portal---previous-months"></a>Wat is er nieuw in de klassieke Intune-portal - vorige maanden

[!INCLUDE [classic-portal](./includes/classic-portal.md)]

Deze pagina bevat nieuwe functies en meldingen die eerder werden aangekondigd op de [Wat is er nieuw-pagina](whats-new.md) voor de klassieke Intune-portal.

## <a name="april-2017"></a>April 2017

### <a name="new-capabilities"></a>Nieuwe mogelijkheden

#### <a name="myapps-available-for-managed-browser---822308-822303--"></a>MyApps beschikbaar voor Managed Browser <!--822308, 822303-->

Betere ondersteuning voor Microsoft MyApps in de Managed Browser. Gebruikers van Managed Browser die niet hoeven te worden beheerd gaan direct naar de MyApps-service, waar ze toegang hebben tot hun door de beheerder beschikbaar gestelde SaaS-apps. Gebruikers die wel moeten worden beheerd door Intune blijven MyApps gebruiken via de ingebouwde bladwijzer in Managed Browser.

#### <a name="new-icons-for-the-managed-browser-and-the-company-portal---918433-918431-971473--"></a>Nieuwe pictogrammen voor de Managed Browser en bedrijfsportal <!--918433, 918431, 971473-->

Zowel de Android- als iOS-versie van de Managed Browser heeft een nieuw pictogram. Dit nieuwe pictogram bevat het bijgewerkte Intune-logo, om het consistent te maken met de andere apps in Enterprise Mobility + Security (EM+S). U kunt het nieuwe pictogram voor de Managed Browser zien op de [pagina Wat is er nieuw in de gebruikersinterface van de Intune-app?](whats-new-app-ui.md)

De pictogrammen voor de Android-, iOS- en Windows-versies van de app in de bedrijfsportal worden ook vernieuwd, voor meer consistentie met de andere apps in EM+S. Deze pictogrammen worden in de periode van april tot eind mei geleidelijk in gebruik genomen op de verschillende platforms.

#### <a name="sign-in-progress-indicator-in-android-company-portal---953374--"></a>Voortgangsindicator voor aanmelden bij Android-bedrijfsportal <!--953374-->

De Android-bedrijfsportal-app is bijgewerkt met een voortgangsindicator voor het aanmelden wanneer de gebruiker de app opent of hervat. De indicator geeft de verschillende statussen weer, beginnend bij ‘Verbinden...’, gevolgd door ‘Aanmelden...’ en ‘Beveiligingseisen controleren...’, voordat de gebruiker de app kan gebruiken. U kunt de nieuwe schermen voor de bedrijfsportal-app voor Android zien op de [pagina Wat is er nieuw in de gebruikersinterface van de Intune-app?](whats-new-app-ui.md)

#### <a name="block-apps-from-accessing-sharepoint-online----679339---"></a>Apps blokkeren voor toegang tot SharePoint Online<!-- 679339 -->

U kunt een beleid voor voorwaardelijke toegang op basis van een app maken om apps waarop geen app-beveiligingsbeleid is toegepast te blokkeren tegen toegang tot [SharePoint Online](/intune-classic/deploy-use/mam-ca-for-sharepoint-online). In het scenario voor voorwaardelijke toegang op basis van apps kunt u via Azure Portal de apps opgeven die u toegang wilt verlenen tot SharePoint Online.

#### <a name="single-sign-on-support-from-the-company-portal-for-ios-to-outlook-for-ios---834012--"></a>Ondersteuning voor eenmalige aanmelding in bedrijfsportal-app voor iOS voor Outlook voor iOS <!--834012-->
Gebruikers hoeven zich niet langer aan te melden bij de Outlook-app als ze op hetzelfde apparaat en met hetzelfde account zijn aangemeld bij de bedrijfsportal-app voor iOS. Wanneer gebruikers de Outlook-app starten, kunnen ze hun account selecteren en worden ze automatisch aangemeld. In de toekomst wordt deze functionaliteit ook toegevoegd aan andere Microsoft-apps.

#### <a name="improved-status-messaging-in-the-company-portal-app-for-ios---744866--"></a>Verbeterde statusberichten in de bedrijfsportal-app voor iOS <!--744866-->
Er worden nieuwe, specifiekere foutberichten weergegeven in de bedrijfsportal-app voor iOS, die meer toegankelijke informatie bieden over wat er gebeurt op apparaten. Deze foutsituaties maakten eerder deel uit van een algemeen foutbericht met de titel “Bedrijfsportal is tijdelijk niet beschikbaar”. Als een gebruiker nu de bedrijfsportal-app in iOS opent zonder internetverbinding, wordt er een permanente statusbalk weergegeven op de startpagina met de tekst “Geen internetverbinding”.

#### <a name="improved-app-install-status-for-the-windows-10-company-portal-app---676495--"></a>Verbeterde app-installatiestatus voor de Windows 10-bedrijfsportal-app <!--676495-->

De volgende verbeteringen voor de app-installaties die zijn gestart in de bedrijfsportal van Windows 10 zijn doorgevoerd:
-   Snellere rapportage over installatievoortgang voor MSI-pakketten
-   Snellere rapportage over installatievoortgang voor moderne apps op apparaten met Windows 10 Jubileumupdate en hoger
-   Nieuwe voortgangsbalk voor de installatie van moderne apps op apparaten met Windows 10 Jubileumupdate en hoger

U kunt de nieuwe voortgangsbalk zien op de [pagina Wat is er nieuw in de gebruikersinterface van de Intune-app](whats-new-app-ui.md)?

#### <a name="bulk-enroll-windows-10-devices----747607---"></a>Windows 10-apparaten bulksgewijs inschrijven <!-- 747607 -->

U kunt nu grote aantallen apparaten waarop de Windows 10-makersupdate wordt uitgevoerd toevoegen aan Azure Active Directory en Intune met Windows Configuration Designer (WCD). Als u [bulksgewijze MDM-registratie](/intune-classic/deploy-use/bulk-enroll-windows) voor uw Azure AD-tenant wilt inschakelen, maakt u een inrichtingspakket waarmee apparaten worden toegevoegd aan uw Azure AD-tenant met Windows Configuration Designer. Vervolgens past u het pakket toe op apparaten die bedrijfseigendom zijn en die u bulksgewijs wilt registreren en beheren. Zodra het pakket is toegepast op de apparaten, worden deze toegevoegd aan Azure AD, ingeschreven bij Intune en zijn ze klaar voor aanmelding door uw Azure AD-gebruikers.  Azure AD-gebruikers zijn standaardgebruikers op deze apparaten en ontvangen toegewezen beleid en de vereiste apps. Scenario's voor Selfservice portal en bedrijfsportal worden momenteel niet ondersteund.

### <a name="whats-new-in-the-public-preview-of-intune-in-the-azure-portal--736542--"></a>Wat is er nieuw in de openbare evaluatieversie van Intune in de Azure portal<!--736542-->

Aan het begin van kalenderjaar 2017 migreren we de volledige functionaliteit voor beheerders naar Azure, voor krachtig en geïntegreerd beheer van EMS-kernwerkstromen op een modern serviceplatform dat kan worden uitgebreid met Graph API’s.

Vanaf deze maand zal de openbare preview-versie van de nieuwe beheerderservaring te zien zijn voor nieuwe evaluatietenants in de Azure-portal. Tijdens de preview-periode worden de mogelijkheden en pariteit met de bestaande Intune-console iteratief geleverd.

De beheerderservaring in de Azure-portal zal gebruikmaken van de eerder aangekondigde nieuwe functionaliteit voor groepen en targeting. Wanneer uw bestaande tenant wordt gemigreerd naar de nieuwe ervaring voor groepen, vindt ook de migratie plaats naar de preview-versie van de nieuwe beheerderservaring. Als u in de tussentijd de nieuwe functionaliteit wilt testen of bekijken totdat de migratie van uw tenant is voltooid, kunt u zich aanmelden voor een nieuw Intune-evaluatieaccount of de [nieuwe documentatie](whats-new.md) raadplegen.

U kunt [hier](whats-new.md) vinden wat er nieuw is in de Intune-preview-versie in Azure.

### <a name="notices"></a>Mededelingen

#### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Rechtstreekse toegang tot Apple-scenario's voor inschrijving <!--951869-->

Voor Intune-accounts die na januari 2017 zijn gemaakt, heeft Intune rechtstreekse toegang ingeschakeld tot Apple-inschrijvingsscenario's. Hiervoor is de werkstroom voor het inschrijven van apparaten gebruikt in de Azure Preview Portal. Voorheen was de Apple-inschrijvingspreview alleen toegankelijk via koppelingen in de Azure-portal. Intune-accounts die vóór januari 2017 zijn gemaakt, moeten eenmalig worden gemigreerd om de functies in Azure beschikbaar te maken. De planning voor de migratie is nog niet aangekondigd, maar de informatie wordt zo snel mogelijk beschikbaar gemaakt. Het wordt aangeraden om een testaccount te maken om de nieuwe ervaring te testen, als u met uw bestaande account geen toegang hebt tot de preview.

#### <a name="whats-coming-for-appx-in-intune-in-the-azure-portal----1000270---"></a>Binnenkort in Appx in Intune in de Azure-portal <!-- 1000270 -->

Als onderdeel van de migratie naar Intune in de Azure-portal, worden de volgende wijzigingen aangebracht in appx:

1. Er wordt een nieuw type appx-app toegevoegd in de Intune-console, die alleen kan worden geïmplementeerd op bij MDM ingeschreven apparaten.
2. Het bestaande appx-app-type wordt alleen nog gebruikt voor pc’s die worden beheerd via de Intune-pc-agent.
3. Alle bestaande appx’s worden geconverteerd naar MDM-appx’s bij de migratie.

##### <a name="how-does-this-affect-me"></a>Wat betekent dit voor mij?

Dit heeft geen gevolgen voor uw bestaande implementaties op apparaten die worden beheerd door de Intune-pc-agent. Na de migratie kunt u die gemigreerde appx’s echter niet implementeren op nieuwe apparaten die worden beheerd door de Intune-pc-agent en waarop de appx’s eerder niet waren gericht.

##### <a name="what-action-do-i-need-to-take"></a>Wat moet ik doen?

Na de migratie moet u de appx opnieuw uploaden als een pc-appx, als u deze wilt implementeren op nieuwe pc’s. Zie [Appx changes in Intune on Azure](https://aka.ms/appxchange) (Appx-wijzigingen in Intune in de Azure-portal) op het blog van het Intune-ondersteuningsteam voor meer informatie.  

#### <a name="administration-roles-being-replaced-in-azure-portal"></a>Beheerdersrollen die worden vervangen in Azure Portal

De bestaande MAM-beheerdersrollen (Mobile Application Management), namelijk Inzender, Eigenaar en Alleen-lezen, die in de klassieke Intune-portal (Silverlight) worden gebruikt, worden vervangen door een volledig nieuw op rollen gebaseerd toegangsbeheer in Intune Azure Portal. Wanneer u naar Azure Portal bent gemigreerd, moet u uw beheerders opnieuw toewijzen aan deze nieuwe beheerdersrollen. Zie [Op rollen gebaseerd toegangsbeheer voor Microsoft Intune](role-based-access-control.md) voor meer informatie over op rollen gebaseerd toegangsbeheer en de nieuwe rollen.

### <a name="whats-coming"></a>Binnenkort

#### <a name="improved-sign-in-experience-across-company-portal-apps-for-all-platforms---user-story-1132123--"></a>Verbeterde aanmeldervaring in de bedrijfsportal-apps voor alle platformen <!--User Story 1132123-->

Dit is de aankondiging van een wijziging die in de komende maanden wordt geïntroduceerd en waarmee de aanmeldervaring wordt verbeterd voor apps in de Intune-bedrijfsportal voor Android, iOS en Windows. De nieuwe gebruikerservaring wordt automatisch toegepast op alle platformen voor de bedrijfsportal-app wanneer deze wijziging wordt doorgevoerd in Azure AD. Bovendien kunnen gebruikers nu zich aanmelden bij de bedrijfsportal vanaf een ander apparaat met een gegenereerde code voor eenmalig gebruik. Dit is vooral nuttig in gevallen wanneer gebruikers zich moeten aanmelden zonder referenties.

Op de pagina [Wat is er nieuw in de app-interface](whats-new-app-ui.md) ziet u schermafbeeldingen van de vorige aanmeldingservaring, de nieuwe aanmeldingservaring met referenties en de nieuwe aanmeldingservaring vanaf een ander apparaat.

#### <a name="plan-for-change-intune-is-changing-the-intune-partner-portal-experience----1050016---"></a>Geplande wijziging: Intune verandert in de Intune Partner Portal-ervaring<!-- 1050016 -->

De pagina Intune Partner wordt verwijderd uit manage.microsoft.com die begint met de service-update halverwege mei 2017.  

Als u een partnerbeheerder bent, kunt u niet langer weergeven of actie ondernemen namens uw klanten vanaf de pagina Intune Partner. U moet zich aanmelden bij een van de twee andere partnerportals bij Microsoft.

U kunt zich bij het [Microsoft Partner Center](https://partnercenter.microsoft.com/) en het [Microsoft Office 365-partnerbeheercentrum](https://portal.office.com/) aanmelden bij de klantaccounts die u beheert. Gebruik in de toekomst als partner een van deze sites voor het beheren van uw klanten.


#### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Apple vereist updates voor Application Transport Security <!--748318-->

Apple heeft aangekondigd dat specifieke vereisten gaan gelden voor Application Transport Security (ATS). ATS wordt gebruikt om betere beveiliging af te dwingen voor alle app-communicatie die verloopt via HTTPS. Deze wijziging heeft gevolgen voor Intune-klanten die de bedrijfsportal-app gebruiken op iOS.

Een versie van de bedrijfsportal-app is beschikbaar gemaakt voor iOS via het Apple TestFlight-programma waarmee naleving van de nieuwe ATS-vereisten wordt afgedwongen. Als u dit wilt proberen zodat u uw ATS-compatibiliteit kunt testen, stuurt u een e-mail naar <a href="mailto:CompanyPortalBeta@microsoft.com?subject=Register to TestFlight ATS Company Portal app"> CompanyPortalBeta@microsoft.com </a> met uw voornaam, achternaam, e-mailadres en bedrijfsnaam. Bekijk ons [Intune-ondersteuningsblog](https://aka.ms/compportalats) voor meer informatie.

## <a name="march-2017"></a>Maart 2017

### <a name="new-capabilities"></a>Nieuwe mogelijkheden

#### <a name="support-for-skycure"></a>Ondersteuning voor Skycure

U kunt nu de toegang van mobiele apparaten tot bedrijfsresources beheren door middel van voorwaardelijke toegang op basis van een risicoanalyse die door Skycure wordt uitgevoerd. Skycure is een oplossing voor de beveiliging tegen bedreigingen op mobiele apparaten die met Microsoft Intune is geïntegreerd. Risico's worden beoordeeld op basis van telemetrische gegevens die zijn verzameld op apparaten met Skycure, zoals:

- Fysieke beveiliging
- Netwerkbeveiliging
- Toepassingsbeveiliging
- Beveiliging tegen zwakke plekken

U kunt het EMS-beleid voor voorwaardelijke toegang configureren op basis van de risicoanalyse van Skycure die wordt ingeschakeld via het Intune-nalevingsbeleid voor apparaten. U kunt aan de hand van dit beleid de toegang van apparaten die niet voldoen aan het beleid tot bedrijfsresources toestaan of blokkeren op basis van de gedetecteerde bedreigingen. Zie [Skycure Mobile Threat Defense-connector](/intune-classic/deploy-use/skycure-mobile-threat-defense-connector) voor meer informatie.

#### <a name="new-user-experience-for-the-company-portal-app-for-android---621622--"></a>Nieuwe gebruikerservaring voor de bedrijfsportal-app voor Android <!--621622-->

Voor de bedrijfsportal-app voor Android wordt een update uitgevoerd voor de gebruikersinterface om deze er moderner te laten uitzien en om een betere gebruikerservaring te bieden. De belangrijkste updates zijn:

- Kleuren: de tabbladkoppen van de bedrijfsportal-app hebben de kleuren van de door de IT opgegeven huisstijl.
- Apps: op het tabblad **Apps** zijn de knoppen **Aanbevolen apps** en **Alle apps** bijgewerkt.
- Zoeken: op het tabblad **Apps** is de knop **Zoeken** nu een zwevende actieknop.
- Navigeren door apps: in de weergave **Alle apps** wordt tabbladen getoond voor de opties **Aanbevolen**, **Alle** en **Categorieën** om de navigatie te vereenvoudigen.
- Ondersteuning: de tabbladen **Mijn apparaten** en **Contact opnemen met IT** zijn bijgewerkt om de leesbaarheid te vergroten.

Zie [UI-updates voor Intune-apps voor eindgebruikers](whats-new-app-ui.md) voor meer informatie over deze wijzigingen.

#### <a name="non-managed-devices-can-access-assigned-apps---664691--"></a>Niet-beheerde apparaten hebben toegang tot toegewezen apps <!--664691-->

Als onderdeel van de ontwerpwijzigingen op de bedrijfsportalwebsite kunnen iOS- en Android-gebruikers op hun niet-beheerde apparaten apps installeren die aan hen zijn toegewezen als 'beschikbaar zonder inschrijving'. Gebruikers kunnen zich met behulp van hun Intune-referenties aanmelden bij de bedrijfsportalwebsite en de lijst met aan hen toegewezen apps bekijken. De app-pakketten van de 'beschikbaar zonder inschrijving'-apps kunnen worden gedownload via de bedrijfsportalwebsite. Deze wijziging is niet van toepassing op apps die pas na inschrijving kunnen worden geïnstalleerd, omdat gebruikers wordt gevraagd hun apparaat in te schrijven als zij deze apps willen installeren.

#### <a name="signing-script-for-windows-10-company-portal---941642--"></a>Ondertekeningsscript voor de Windows 10-bedrijfsportal <!--941642-->

Als u de Windows 10-bedrijfsportal-app moet downloaden en sideloaden, kunt u nu een script gebruiken om het proces voor het ondertekenen van apps voor uw organisatie te vereenvoudigen en stroomlijnen.   Raadpleeg [Microsoft Intune Signing Script](https://aka.ms/win10cpscript) (Ondertekeningsscript voor Microsoft Intune) voor de Windows 10-bedrijfsportal in de TechNet-galerie voor het downloaden van het script en meer informatie over het gebruik ervan. Raadpleeg [Updating your Windows 10 Company Portal app](https://blogs.technet.microsoft.com/intunesupport/2017/03/13/updating-your-windows-10-company-portal-app/) (Uw Windows 10-bedrijfsportal-app bijwerken) in het Intune Support-teamweblog voor meer informatie over deze mededeling.


### <a name="notices"></a>Mededelingen

#### <a name="support-for-ios-103"></a>Ondersteuning voor iOS 10.3

Op 27 maart 2017 is begonnen met het uitrollen van de iOS 10.3-release voor iOS-gebruikers. Alle bestaande Intune MDM- en MAM-scenario's zijn compatibel met de nieuwste versie van het besturingssysteem van Apple. We verwachten dat alle bestaande Intune-functies die momenteel beschikbaar zijn voor het beheer van iOS-apparaten gewoon blijven werken wanneer de gebruikers hun apparaten en apps upgraden naar iOS 10.3.

Er zijn momenteel geen problemen bekend. Als u problemen ondervindt met iOS 10.3, neemt u contact op met het [Intune-ondersteuningsteam](/intune-classic/troubleshoot/contact-assisted-phone-support-for-microsoft-intune).

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
De bedrijfsportalwebsite ondersteunt apps die zijn gericht op gebruikers die geen beheerde apparaten hebben. De website wordt in overeenstemming gebracht met andere Microsoft-producten en -services met een nieuw contrasterend kleurenschema, dynamische illustraties en een 'hamburgermenu', ![Kleine afbeelding van het hamburgermenu dat nu is toegevoegd in de linkerbovenhoek van de bedrijfsportalwebsite](./media/CP_hamburger_menu.png).

### <a name="notices"></a>Mededelingen

#### <a name="group-migration-will-not-require-any-updates-to-groups-or-policies-for-ios-devices---898837--"></a>Bij groepsmigratie zijn geen updates voor groepen of beleidsregels vereist voor iOS-apparaten <!--898837-->
Voor elke Intune-apparaatgroep die vooraf is toegewezen door een inschrijvingsprofiel voor bedrijfsapparaten, wordt tijdens de migratie naar Azure Active Directory-apparaatgroepen een overeenkomende dynamische apparaatgroep in AAD gemaakt op basis van de naam van het inschrijvingsprofiel. Dit zorgt ervoor dat apparaten wanneer ze worden ingeschreven automatisch worden gegroepeerd en hetzelfde beleid en dezelfde apps ontvangen als de oorspronkelijke Intune-groep.

Wanneer een tenant in het migratieproces wordt ingevoerd voor groepering en targeting, wordt in Intune automatisch een dynamische AAD-groep gemaakt die overeenkomt met een Intune-groep waarop een inschrijvingsprofiel voor bedrijfsapparaten is gericht. Als de Intune-beheerder de betreffende Intune-groep verwijdert, wordt de overeenkomende dynamische AAD-groep niet verwijderd. Leden van de groep en de dynamische query worden gewist, maar de groep zelf blijft aanwezig totdat de IT-beheerder deze via de AAD-portal verwijdert.

Ook als de IT-beheerder de Intune-groep wijzigt waarop een inschrijvingsprofiel voor bedrijfsapparaten is gericht, wordt in Intune een nieuwe dynamische groep gemaakt op basis van de nieuwe profieltoewijzing en wordt de dynamische groep die werd gemaakt voor de oude toewijzing niet verwijderd.

### <a name="defaulting-to-managing-windows-desktop-devices-through-windows-settings---663050--"></a>Standaardinstelling voor het beheren van Windows-desktops via Windows-instellingen <!--663050-->
Het standaardgedrag voor het registreren van Windows 10-desktops verandert. Nieuwe registraties volgen het standaardproces van registratie via de MDM-agent in plaats van via de pc-agent. De bedrijfsportalwebsite biedt gebruikers van Windows 10-desktops registratie-instructies om ze te helpen bij het toevoegen van Windows 10-desktopcomputers als mobiele apparaten. Dit heeft geen gevolgen voor momenteel ingeschreven pc's en met behulp van de pc-agent kan uw organisatie nog altijd Windows 10-desktops beheren [als u dat liever hebt](/intune-classic/deploy-use/set-up-windows-device-management-with-microsoft-intune).

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

De [pagina met UI-updates](whats-new-app-ui.md) bevat voor-en-na afbeeldingen.

### <a name="associate-multiple-management-tools-with-the-microsoft-store-for-business---926135--"></a>Meerdere beheerhulpprogramma's koppelen aan Microsoft Store voor Bedrijven <!--926135-->
Als u meer dan één beheerhulpprogramma voor het implementeren van Microsoft Store voor Bedrijven-apps gebruikt, kon u voorheen slechts één van deze programma’s koppelen met Microsoft Store voor Bedrijven. U kunt nu meerdere beheerhulpprogramma's met de Store koppelen, bijvoorbeeld Intune en Configuration Manager. Zie [Apps die u hebt aangeschaft in Microsoft Store voor Bedrijven, beheren met Microsoft Intune](/intune-classic/deploy-use/manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune#associate-your-windows-store-for-business-account-with-intune) voor meer informatie.

## <a name="whats-new-in-the-public-preview-of-intune-in-the-azure-portal---736542--"></a>Wat is er nieuw in de openbare evaluatieversie van Intune in de Azure portal <!--736542-->

Aan het begin van kalenderjaar 2017 migreren we de volledige functionaliteit voor beheerders naar Azure, voor krachtig en geïntegreerd beheer van EMS-kernwerkstromen op een modern serviceplatform dat kan worden uitgebreid met Graph API’s.

Vanaf deze maand zal de openbare preview-versie van de nieuwe beheerderservaring te zien zijn voor nieuwe evaluatietenants in de Azure-portal. Tijdens de preview-periode worden de mogelijkheden en pariteit met de bestaande Intune-console iteratief geleverd.

De beheerderservaring in de Azure-portal zal gebruikmaken van de eerder aangekondigde nieuwe functionaliteit voor groepen en targeting. Wanneer uw bestaande tenant wordt gemigreerd naar de nieuwe ervaring voor groepen, vindt ook de migratie plaats naar de preview-versie van de nieuwe beheerderservaring. Als u in de tussentijd de nieuwe functionaliteit wilt testen of bekijken totdat de migratie van uw tenant is voltooid, kunt u zich aanmelden voor een nieuw Intune-evaluatieaccount of de [nieuwe documentatie](whats-new.md) raadplegen.

U kunt [hier](whats-new.md) vinden wat er nieuw is in de Intune-preview-versie in Azure.

## <a name="january-2017"></a>Januari 2017

### <a name="new-capabilities"></a>Nieuwe mogelijkheden

#### <a name="in-console-reports-for-mam-without-enrollment---677961--"></a>Interne consolerapporten voor MAM zonder registratie<!--677961-->
Er zijn nieuwe rapporten voor app-beveiliging toegevoegd voor zowel geregistreerde als niet-geregistreerde apparaten. [Meer informatie over hoe u MAM-beleid met Intune kunt bewaken vindt u hier](/intune-classic/deploy-use/monitor-mobile-app-management-policies-with-microsoft-intune).

#### <a name="android-711-support---694397--"></a>Android 7.1.1-ondersteuning <!--694397-->
Intune biedt nu volledige ondersteuning en volledig beheer voor Android 7.1.1.

#### <a name="resolve-issue-where-ios-devices-are-inactive-or-the-admin-console-cannot-communicate-with-them---unknown--"></a>Oplossing voor het probleem waarbij iOS-apparaten inactief zijn of waarbij de beheerconsole er niet mee kan communiceren <!--unknown-->
Wanneer het contact tussen de apparaten van gebruikers en Intune verloren gaat, kunt u de gebruikers stappen voor probleemoplossing aandragen waarmee ze weer toegang krijgen tot de bedrijfsresources. Zie [Apparaten zijn inactief of de beheerconsole kan er niet mee communiceren](/intune-classic/troubleshoot/troubleshoot-device-enrollment-in-intune#devices-are-inactive-or-the-admin-console-cannot-communicate-with-them).

### <a name="notices"></a>Mededelingen

#### <a name="defaulting-to-managing-windows-desktop-devices-through-windows-settings---663050--"></a>Standaardinstelling voor het beheren van Windows-desktops via Windows-instellingen <!--663050-->
Het standaardgedrag voor het registreren van Windows 10-desktops verandert. Nieuwe registraties volgen het standaardproces van registratie via de MDM-agent in plaats van via de pc-agent.

De bedrijfsportalwebsite biedt gebruikers van Windows 10-desktops registratie-instructies om ze te helpen bij het toevoegen van Windows 10-desktopcomputers als mobiele apparaten. Dit heeft geen gevolgen voor momenteel ingeschreven pc's en met behulp van de pc-agent kan uw organisatie nog altijd Windows 10-desktops beheren [als u dat liever hebt](/intune-classic/deploy-use/set-up-windows-device-management-with-microsoft-intune).

#### <a name="improving-mobile-app-management-support-for-selective-wipe---581242--"></a>Verbetering van MAM-ondersteuning voor selectief wissen <!--581242-->
Eindgebruikers krijgen extra informatie over het verkrijgen van toegang tot werk- of schoolgegevens als die gegevens automatisch worden verwijderd op basis van het beleid 'Offline interval voordat app-gegevens worden gewist'.<!--, or the removal of the Intune Company Portal on Android.-->

#### <a name="company-portal-for-ios-links-open-inside-the-app---665954--"></a>Bedrijfsportal voor iOS-koppelingen openen in de app <!--665954-->
Koppelingen in de bedrijfsportal-app voor iOS, inclusief koppelingen naar documentatie en apps, worden rechtstreeks in de bedrijfsportal-app geopend met behulp van in-app-weergave van Safari. Deze update wordt afzonderlijk van de service-update in januari verzonden.

#### <a name="modernizing-the-company-portal-website---753980--"></a>De bedrijfsportalwebsite moderniseren <!--753980-->
Te beginnen in februari ondersteunt de bedrijfsportalwebsite apps die zijn gericht op gebruikers die geen beheerde apparaten hebben. De website wordt in overeenstemming gebracht met andere Microsoft-producten en -services met een nieuw contrasterend kleurenschema, dynamische illustraties en een 'hamburgermenu', ![Hamburger-menu van bedrijfsportalwebsite](./media/CP_hamburger_menu.png).

#### <a name="new-documentation-for-app-protection-policies---583398--"></a>Nieuwe documentatie voor app-beveiligingsbeleid<!--583398-->
We hebben de documentatie bijgewerkt voor beheerders en app-ontwikkelaars die beleid voor app-beveiliging (ook wel MAM-beleid genoemd) willen inschakelen in hun iOS- en Android-apps met behulp van de Intune App Wrapping Tool of Intune App SDK.

De volgende artikelen zijn bijgewerkt:

* [Bepalen hoe u apps voorbereidt op Mobile Application Management met Microsoft Intune](apps-prepare-mobile-application-management.md)
* [iOS-apps voorbereiden voor Mobile Application Management met de Intune App Wrapping Tool](app-wrapper-prepare-ios.md)
* [Aan de slag met de Microsoft Intune App SDK](app-sdk-get-started.md)
* [Ontwikkelaarshandleiding voor Intune App SDK voor iOS](app-sdk-ios.md)

De volgende artikelen zijn nieuwe toevoegingen aan de documentenbibliotheek:

* [Intune App SDK Cordova-invoegtoepassing](app-sdk-cordova.md)
* [Intune App SDK Xamarin-onderdeel](app-sdk-xamarin.md)

#### <a name="progress-bar-when-launching-the-company-portal-on-ios---665978--"></a>Voortgangsbalk bij het starten van de bedrijfsportal in iOS <!--665978-->
De bedrijfsportal voor iOS introduceert een voortgangsbalk op het startscherm met informatie voor de gebruiker over het laden van processen die optreden. Er is een gefaseerde rollout van de voortgangsbalk als vervanging van het kringveld. Dit betekent dat sommige van uw gebruikers de nieuwe voortgangsbalk te zien krijgen, terwijl anderen blijven het kringveld blijven zien.

## <a name="december-2016"></a>December 2016

### <a name="public-preview-of-intune-in-the-azure-portal--736542--"></a>Openbare evaluatieversie van Intune in de Azure portal<!--736542-->
Aan het begin van kalenderjaar 2017 migreren we de volledige functionaliteit voor beheerders naar Azure, voor krachtig en geïntegreerd beheer van EMS-kernwerkstromen op een modern serviceplatform dat kan worden uitgebreid met Graph API’s. Voordat deze portal algemeen beschikbaar wordt voor alle Intune-tenants, zullen we later deze maand een preview van deze nieuwe beheerderservaring uitrollen voor een select aantal tenants.

De beheerderservaring in de Azure-portal zal gebruikmaken van de eerder aangekondigde nieuwe functionaliteit voor groepen en targeting. Wanneer uw bestaande tenant wordt gemigreerd naar de nieuwe ervaring voor groepen, vindt ook de migratie plaats naar de preview-versie van de nieuwe beheerderservaring. In de tussentijd vindt u in Azure Portal [nieuwe documentatie](/intune/what-is-intune) met meer informatie over wat we in petto hebben voor Microsoft Intune.

__Integratie van systemen voor onkostenbeheer voor telecom in de openbare preview van Azure Portal__ <!--747605--> We beginnen nu met proeven met de integratie met externe systemen voor onkostenbeheer voor telecom (TEM) in Azure Portal. U kunt Intune gebruiken om limieten in te stellen voor gegevensgebruik, voor zowel nationaal als roaming. Hierbij beginnen we met [Saaswedo](http://www.saaswedo.com/). Als u deze functie in uw proeftenant wilt inschakelen, neemt u [contact op met Microsoft-ondersteuning](/intune-classic/troubleshoot/how-to-get-support-for-microsoft-intune).

### <a name="new-capabilities"></a>Nieuwe mogelijkheden

__Multi-Factor Authentication op alle platformen__ <!--747590--> U kunt nu Multi-Factor Authentication (MFA) afdwingen voor een geselecteerde groep gebruikers, wanneer zij een apparaat met iOS, Android, Windows 8.1+ of Windows Phone 8.1+ inschrijven bij de Azure-beheerportal. Dit doet u door MFA te configureren voor Microsoft Intune-inschrijving in Azure Active Directory.

__Mogelijkheid om de inschrijving van mobiele apparaten te beperken__ <!--747596--> Er zijn in Intune nieuwe inschrijvingsbeperkingen toegevoegd waarmee u bepaalt welke platformen voor mobiele apparaten kunnen worden ingeschreven. Intune onderscheidt platforms voor mobiele apparaten als iOS, Mac OS, Android, Windows en Windows Mobile.
* Een beperking voor de registratie van mobiele apparaten, betekent niet dat de PC-clientregistratie ook is beperkt.
* Alleen voor iOS geldt er een extra optie voor het blokkeren van de inschrijving van apparaten die in persoonlijk eigendom zijn.

Intune markeert alle nieuwe apparaten als persoonlijk, tenzij de IT-beheerder actie onderneemt om deze te markeren als bedrijfseigen, zoals uitgelegd in [dit artikel](/intune-classic/deploy-use/manage-corporate-owned-devices).

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

Met de nieuwe app kunnen gebruikers van Windows 10-apparaten ook gebruikmaken van aanvullende functies van het platform, zoals eenmalige aanmelding (SSO) en verificatie op basis van certificaten. De app wordt beschikbaar gesteld als een upgrade van de bestaande Windows 8.1-bedrijfsportal en Windows Phone 8.1-bedrijfsportal in Microsoft Store. Zie [aka.ms/intunecp_universalapp](http://aka.ms/intunecp_universalapp) voor meer informatie.

> [!IMPORTANT]
> __Een update voor Intune en Android for Work__ Hoewel u Android for Work-apps kunt implementeren met de actie __Vereist__, kunt u apps alleen implementeren als __Beschikbaar__ als uw Intune-groepen zijn gemigreerd naar de nieuwe functie voor groepen van Azure AD.

__De invoegtoepassing Intune App SDK voor Cordova biedt nu ondersteuning voor MAM zonder registratie__ App-ontwikkelaars kunnen de invoegtoepassing Intune App SDK voor Cordova nu gebruiken om MAM-functionaliteit zonder apparaatinschrijving in te schakelen in hun op Cordova gebaseerde apps voor Android en iOS. U vindt de Intune App SDK Cordova-invoegtoepassing [hier](https://github.com/msintuneappsdk/cordova-plugin-ms-intune-mam).

__Het onderdeel Intune App SDK Xamarin biedt nu ondersteuning voor MAM zonder registratie__ App-ontwikkelaars kunnen het Intune App SDK Xamarin-onderdeel nu gebruiken om MAM-functionaliteit zonder apparaatinschrijving in te schakelen in hun op Xamarin gebaseerde apps voor Android en iOS. U vindt het Intune App SDK Xamarin-onderdeel [hier](https://github.com/msintuneappsdk/intune-app-sdk-xamarin).

### <a name="notices"></a>Mededelingen

__Een Symantec-handtekeningcertificaat vereist geen ondertekend Windows Phone 8-bedrijfsportal meer voor uploaden__ Voor het uploaden van een Symantec-handtekeningcertificaat is geen ondertekend Windows Phone 8-bedrijfsportal-app meer nodig. Het certificaat kan afzonderlijk worden geüpload.

### <a name="deprecations"></a>Afschaffingen

__Ondersteuning voor de Windows Phone 8-bedrijfsportal__ Ondersteuning voor de Windows Phone 8-bedrijfsportal wordt nu afgeschaft. Ondersteuning voor het Windows Phone 8- en Windows RT-platform is afgeschaft in oktober 2016. Ondersteuning voor de Windows 8-bedrijfsportal is ook in oktober 2016 afgeschaft.


### <a name="see-also"></a>Zie ook
Zie [Wat is er nieuw in Microsoft Intune?](whats-new.md) voor meer informatie over recente ontwikkelingen.
