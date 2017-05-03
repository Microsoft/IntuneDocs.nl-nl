---
title: Wat is er nieuw? | Microsoft Docs
description: Ontdek wat er nieuw is in de release van Microsoft Intune van deze maand en in oudere releases
keywords: 
author: mtillman
ms.author: mtillman
manager: angrobe
ms.date: 04/20/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c
ms.reviewer: priyar
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 62dcb40ad5a7921c514a9d41da14b991e39f3bcd
ms.openlocfilehash: b3cf8d8f60482be2d4d903d1b2c00c1a3a392b73
ms.lasthandoff: 04/20/2017


---
# <a name="whats-new-in-microsoft-intune---april-2017"></a>Wat is er nieuw in Microsoft Intune - april 2017
Ontdek wat er nieuw is in deze release van Microsoft Intune. U vindt hier ook informatie over toekomstige wijzigingen waar u rekening mee moet houden én informatie over oudere releases.

> [!Note]
> Al deze functies worden uiteindelijk ondersteund voor implementaties voor hybride klanten (Configuration Manager met Intune). Bekijk voor meer informatie over nieuwe hybride functies onze [Wat is er nieuw-pagina voor hybride](https://docs.microsoft.com/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

## <a name="new-capabilities"></a>Nieuwe mogelijkheden

### <a name="improved-sign-in-experience-across-company-portal-apps-for-all-platforms---user-story-1132123--"></a>Verbeterde aanmeldervaring in de bedrijfsportal-apps voor alle platformen <!--User Story 1132123-->

De aanmeldingservaring voor de Intune-bedrijfsportal-apps voor Android, iOS eDe aanmeldingservaring voor de Intune-bedrijfsportal-apps voor Android, iOS en Windows wordt verbeterd.n Windows wordt verbeterd. De nieuwe gebruikerservaring wordt automatisch toegepast op alle platformen voor de bedrijfsportal-app wanneer deze wijziging wordt doorgevoerd in Azure AD.De nieuwe gebruikerservaring wordt automatisch toegepast op alle platformen voor de bedrijfsportal-app wanneer deze wijziging wordt doorgevoerd in Azure AD. Bovendien kunnen gebruikers nu zich aanmelden bij de bedrijfsportal vanaf een ander apparaat met een gegenereerde code voor eenmalig gebruik. Dit is vooral nuttig in gevallen wanneer gebruikers zich moeten aanmelden zonder referenties.

Op de pagina [Wat is er nieuw in de app-interface](whats-new-in-intune-app-ui.md) ziet u schermafbeeldingen van de vorige aanmeldingservaring, de nieuwe aanmeldingservaring met referenties en de nieuwe aanmeldingservaring vanaf een ander apparaat.

### <a name="myapps-available-for-managed-browser---822308-822303--"></a>MyApps beschikbaar voor Managed Browser <!--822308, 822303-->

Betere ondersteuning voor Microsoft MyApps in de Managed Browser. Gebruikers van Managed Browser die niet hoeven te worden beheerd gaan direct naar de MyApps-service, waar ze toegang hebben tot hun door de beheerder beschikbaar gestelde SaaS-apps. Gebruikers die wel moeten worden beheerd door Intune blijven MyApps gebruiken via de ingebouwde bladwijzer in Managed Browser.

### <a name="new-icons-for-the-managed-browser-and-the-company-portal---918433-918431-971473--"></a>Nieuwe pictogrammen voor de Managed Browser en bedrijfsportal <!--918433, 918431, 971473-->

Zowel de Android- als iOS-versie van de Managed Browser heeft een nieuw pictogram. Dit nieuwe pictogram bevat het bijgewerkte Intune-logo, om het consistent te maken met de andere apps in Enterprise Mobility + Security (EM+S). U kunt het nieuwe pictogram voor de Managed Browser zien op de [pagina Wat is er nieuw in de gebruikersinterface van de Intune-app?](whats-new-in-intune-app-ui.md)

De pictogrammen voor de Android-, iOS- en Windows-versies van de app in de bedrijfsportal worden ook vernieuwd, voor meer consistentie met de andere apps in EM+S. Deze pictogrammen worden in de periode van april tot eind mei geleidelijk in gebruik genomen op de verschillende platformen.

### <a name="sign-in-progress-indicator-in-android-company-portal---953374--"></a>Voortgangsindicator voor aanmelden bij Android-bedrijfsportal <!--953374-->

De Android-bedrijfsportal-app is bijgewerkt met een voortgangsindicator voor het aanmelden wanneer de gebruiker de app opent of hervat. De indicator geeft de verschillende statussen weer, beginnend bij ‘Verbinden...’, gevolgd door ‘Aanmelden...’ en ‘Beveiligingseisen controleren...’, voordat de gebruiker de app kan gebruiken. U kunt de nieuwe schermen voor de bedrijfsportal-app voor Android zien op de [pagina Wat is er nieuw in de gebruikersinterface van de Intune-app?](whats-new-in-intune-app-ui.md)

### <a name="block-apps-from-accessing-sharepoint-online----679339---"></a>Apps blokkeren voor toegang tot SharePoint Online<!-- 679339 -->

U kunt een beleid voor voorwaardelijke toegang op basis van een app maken om apps waarop geen app-beveiligingsbeleid is toegepast te blokkeren tegen toegang tot [SharePoint Online](/InTune/deploy-use/mam-ca-for-sharepoint-online). In het scenario voor voorwaardelijke toegang op basis van apps kunt u via Azure Portal de apps opgeven die u toegang wilt verlenen tot SharePoint Online.

### <a name="bulk-enroll-windows-10-devices----747607---"></a>Windows 10-apparaten bulksgewijs inschrijven <!-- 747607 -->

U kunt nu grote aantallen apparaten waarop de Windows 10-makersupdate wordt uitgevoerd toevoegen aan Azure Active Directory en Intune met Windows Configuration Designer (WCD). Als u [bulksgewijze MDM-registratie](/intune/deploy-use/bulk-enroll-windows) voor uw Azure AD-tenant wilt inschakelen, maakt u een inrichtingspakket waarmee apparaten worden toegevoegd aan uw Azure AD-tenant met Windows Configuration Designer. Vervolgens past u het pakket toe op apparaten die bedrijfseigendom zijn en die u bulksgewijs wilt registreren en beheren. Zodra het pakket is toegepast op de apparaten, worden deze toegevoegd aan Azure AD, ingeschreven bij Intune en zijn ze klaar voor aanmelding door uw Azure AD-gebruikers.  Azure AD-gebruikers zijn standaardgebruikers op deze apparaten en ontvangen toegewezen beleid en de vereiste apps. Scenario’s voor Selfservice portal en bedrijfsportal worden momenteel niet ondersteund.

## <a name="notices"></a>Mededelingen

### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Rechtstreekse toegang tot Apple-scenario's voor inschrijving <!--951869-->

Voor Intune-accounts die na januari 2017 zijn gemaakt, heeft Intune rechtstreekse toegang ingeschakeld tot Apple-inschrijvingsscenario's. Hiervoor is de werkstroom voor het inschrijven van apparaten gebruikt in de Azure Preview Portal. Voorheen was de Apple-inschrijvingspreview alleen toegankelijk via koppelingen in de klassieke Intune-portal. Intune-accounts die vóór januari 2017 zijn gemaakt, moeten eenmalig worden gemigreerd om de functies in Azure beschikbaar te maken. De planning voor de migratie is nog niet aangekondigd, maar de informatie wordt zo snel mogelijk beschikbaar gemaakt. Het wordt aangeraden om een testaccount te maken om de nieuwe ervaring te testen, als u met uw bestaande account geen toegang hebt tot de preview.

### <a name="whats-coming-for-appx-in-intune-on-azure----1000270---"></a>Binnenkort in Appx in Intune op Azure <!-- 1000270 -->

Als onderdeel van de migratie naar Intune op Azure, worden de volgende wijzigingen aangebracht in appx:

1. Er wordt een nieuw type appx-app toegevoegd in de klassieke Intune-console, die alleen kan worden geïmplementeerd op bij MDM ingeschreven apparaten.
2. Het bestaande appx-app-type wordt alleen nog gebruikt voor pc’s die worden beheerd via de Intune-pc-agent.
3. Alle bestaande appx’s worden geconverteerd naar MDM-appx’s bij de migratie.

#### <a name="how-does-this-affect-me"></a>Wat betekent dit voor mij?

Dit heeft geen gevolgen voor uw bestaande implementaties op apparaten die worden beheerd door de Intune-pc-agent. Na de migratie kunt u die gemigreerde appx’s echter niet implementeren op nieuwe apparaten die worden beheerd door de Intune-pc-agent en waarop de appx’s eerder niet waren gericht.

#### <a name="what-action-do-i-need-to-take"></a>Wat moet ik doen?

Na de migratie moet u de appx opnieuw uploaden als een pc-appx, als u deze wilt implementeren op nieuwe pc’s. Zie [Appx changes in Intune on Azure](https://aka.ms/appxchange) (Appx-wijzigingen in Intune op Azure) op het blog van het Intune-ondersteuningsteam voor meer informatie.  


## <a name="whats-new-in-the-public-preview-of-the-intune-admin-experience-on-azure---736542--"></a>Wat is er nieuw in de openbare preview-versie van de nieuwe Intune-ervaring voor beheerders in Azure <!--736542-->

Aan het begin van kalenderjaar 2017 migreren we de volledige functionaliteit voor beheerders naar Azure, voor krachtig en geïntegreerd beheer van EMS-kernwerkstromen op een modern serviceplatform dat kan worden uitgebreid met Graph API’s.

Vanaf deze maand zal de openbare preview-versie van de nieuwe beheerderservaring te zien zijn voor nieuwe evaluatietenants in de Azure-portal. Tijdens de preview-periode worden de mogelijkheden en pariteit met de bestaande Intune-console iteratief geleverd.

De beheerderservaring in de Azure-portal zal gebruikmaken van de eerder aangekondigde nieuwe functionaliteit voor groepen en targeting. Wanneer uw bestaande tenant wordt gemigreerd naar de nieuwe ervaring voor groepen, vindt ook de migratie plaats naar de preview-versie van de nieuwe beheerderservaring. Als u in de tussentijd de nieuwe functionaliteit wilt testen of bekijken totdat de migratie van uw tenant is voltooid, kunt u zich aanmelden voor een nieuw Intune-evaluatieaccount of de [nieuwe documentatie](/intune-azure/introduction/whats-new) raadplegen.

> [!Note]
> Voor de Azure Portal Preview worden de updates voor deze maand uitgerold. De wijzigingen zijn echter mogelijk niet meteen beschikbaar vanwege de manier waarop de Intune-service wordt uitgerold.  Verschillende onderdelen van de service moeten opeenvolgend worden bijgewerkt voordat de nieuwe functies van de portal beschikbaar zijn. U zult de wijzigingen zien in Azure Portal Preview wanneer ze later deze maand worden uitgerold. Zie [Wat is er nieuw in Microsoft Intune Preview](/intune-azure/introduction/whats-new) voor een volledige lijst met wijzigingen.

### <a name="administration-roles-being-replaced-in-azure-portal"></a>Beheerdersrollen die worden vervangen in Azure Portal

De bestaande MAM-beheerdersrollen (Mobile Application Management), namelijk Inzender, Eigenaar en Alleen-lezen, die in de klassieke Intune-portal (Silverlight) worden gebruikt, worden vervangen door een volledig nieuw op rollen gebaseerd toegangsbeheer in Intune Azure Portal. Wanneer u naar Azure Portal bent gemigreerd, moet u uw beheerders opnieuw toewijzen aan deze nieuwe beheerdersrollen. Zie [Op rollen gebaseerd toegangsbeheer voor Microsoft Intune](/intune-azure/access-control/role-based-access-control) voor meer informatie over op rollen gebaseerd toegangsbeheer en de nieuwe rollen.


## <a name="whats-coming"></a>Binnenkort

### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Apple vereist updates voor Application Transport Security <!--748318-->

Apple heeft aangekondigd dat vanaf het voorjaar van 2017 specifieke vereisten gaan gelden voor Application Transport Security (ATS). ATS wordt gebruikt om betere beveiliging af te dwingen voor alle app-communicatie die verloopt via HTTPS. Deze wijziging heeft gevolgen voor Intune-klanten die de bedrijfsportal-app gebruiken op iOS. Bekijk ons [Intune-ondersteuningsblog](https://aka.ms/compportalats) voor meer informatie.

### <a name="see-also"></a>Zie tevens
* [Microsoft Intune-blog](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Roadmap voor cloudplatform](https://www.microsoft.com/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Wat is nieuw in de Azure-preview?](https://docs.microsoft.com/intune-azure/introduction/whats-new)
* [Wat is er nieuw in de gebruikersinterface van de bedrijfsportal?](https://docs.microsoft.com/intune/whats-new/whats-new-in-company-portal-ui)
* [Wat is er nieuw (archief)](whats-new-archive.md)

