---
title: De vroege editie | Microsoft Docs
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 12/21/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 18d47678b0fbdbd98502f2d3b469b202b567b2e7
ms.openlocfilehash: 3c7edc236878232c6f4c0ae993733c967946e765


---

# <a name="the-early-edition-for-microsoft-intune---january"></a>De vroege editie voor Microsoft Intune - januari

De **Vroege editie** bevat een lijst met functies die worden toegevoegd aan toekomstige releases van Microsoft Intune. Deze informatie wordt in zeer beperkte mate onder geheimhoudingsverklaring verstrekt en kan worden gewijzigd. Sommige functies die hier worden vermeld, zullen mogelijk niet beschikbaar zijn op de sluitingsdatum en worden mogelijk beschikbaar gesteld in een latere release. Andere functies worden getest in een proefversie, zodat we zeker weten dat ze in gebruik kunnen worden genomen. Neem bij vragen contact op met uw contactpersoon voor Intune/projectmanagement.

Deze pagina wordt regelmatig bijgewerkt. Controleer op andere updates.

> [!Note]
> De volgende wijzigingen worden momenteel ontwikkeld voor Intune. Al deze functies worden uiteindelijk ondersteund voor implementaties voor hybride klanten (Configuration Manager met Intune). Bekijk voor meer informatie over nieuwe hybride functies onze [Wat is er nieuw-pagina voor hybride](https://docs.microsoft.com/en-us/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

## <a name="new-capabilities"></a>Nieuwe mogelijkheden

### <a name="actions-for-non-compliance---730266--"></a>Acties voor niet-naleving <!--730266-->
_Acties voor niet-naleving_ is een nieuwe functie van nalevingsbeleid waarmee u actie kunt ondernemen voor apparaten die niet meer compatibel zijn. U kunt een of meer acties opgeven, samen met de tijdsduur waarbinnen deze acties moeten plaatsvinden. U kunt bijvoorbeeld gebruikers van niet-compatibele apparaten een melding via e-mail sturen onmiddellijk nadat de compatibiliteit van de apparaten is opgeheven, of u kunt de toegang van niet-compatibele apparaten tot bedrijfsbronnen blokkeren na een respijtperiode van 3 dagen via voorwaardelijke toegang.

### <a name="in-console-reports-for-mam-without-enrollment---677961--"></a>Interne consolerapporten voor MAM zonder registratie<!--677961-->
Er zijn nieuwe rapporten voor app-beveiliging toegevoegd voor zowel geregistreerde als niet-geregistreerde apparaten. [Meer informatie over hoe u MAM-beleid met Intune kunt bewaken vindt u hier](https://docs.microsoft.com/en-us/intune/deploy-use/monitor-mobile-app-management-policies-with-microsoft-intune).

### <a name="conditional-access-for-mam-with-sharepoint-online---679339--"></a>Voorwaardelijke toegang voor MAM met SharePoint Online <!--679339-->
U kunt de toegang tot SharePoint Online blokkeren voor apps die niet worden ondersteund door de beleidsregels voor Mobile App Management (MAM) in Intune.  U kunt aan de slag gaan met Mobile App Management in Intune via de Azure-portal. De sectie __Voorwaardelijke toegang__ op de blade __Instellingen__ bevat de optie voor SharePoint Online. Deze functie wordt afzonderlijk geleverd van de rest van de servicerelease. <!--Find out more about this new feature [here](https://docs.microsoft.com/intune/deploy-use/mam-ca-for-sharepoint-online).-->

### <a name="android-711-support---694397--"></a>Android 7.1.1-ondersteuning <!--694397-->
Intune biedt nu volledige ondersteuning en volledig beheer voor Android 7.1.1.

## <a name="notices"></a>Mededelingen

### <a name="defaulting-to-managing-windows-desktop-devices-through-windows-settings---663050--"></a>Standaardinstelling voor het beheren van Windows-desktops via Windows-instellingen <!--663050-->
Het standaardgedrag voor het registreren van Windows 10-desktops verandert. Nieuwe registraties volgen het standaardproces van registratie via de MDM-agent in plaats van via de pc-agent.

De bedrijfsportalwebsite biedt gebruikers van Windows 10-desktops registratie-instructies om ze te helpen bij het toevoegen van Windows 10-desktopcomputers als mobiele apparaten. Dit heeft geen gevolgen voor momenteel ingeschreven pc's en met behulp van de pc-agent kan uw organisatie nog altijd Windows 10-desktops beheren [als u dat liever hebt](https://docs.microsoft.com/en-us/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune).

### <a name="company-portal-for-ios-links-open-inside-the-app---665954--"></a>Bedrijfsportal voor iOS-koppelingen openen in de app <!--665954-->
Koppelingen in de bedrijfsportal-app voor iOS, inclusief koppelingen naar documentatie en apps, worden rechtstreeks in de bedrijfsportal-app geopend met behulp van in-app-weergave van Safari. Deze update wordt afzonderlijk van de service-update in januari verzonden.

### <a name="improving-mobile-app-management-support-for-selective-wipe---581242--"></a>Verbetering van MAM-ondersteuning voor selectief wissen <!--581242-->
Eindgebruikers krijgen extra informatie over het verkrijgen van toegang tot werk- of schoolgegevens als die gegevens automatisch worden verwijderd op basis van het beleid 'Offline interval voordat app-gegevens worden gewist'.<!--, or the removal of the Intune Company Portal on Android.-->

### <a name="new-documentation-for-app-protection-policies---583398--"></a>Nieuwe documentatie voor app-beveiligingsbeleid<!--583398-->
We hebben de documentatie bijgewerkt voor beheerders en app-ontwikkelaars die beleid voor app-beveiliging (ook wel MAM-beleid genoemd) willen inschakelen in hun iOS- en Android-apps met behulp van de Intune App Wrapping Tool of Intune App SDK.

De volgende artikelen zijn bijgewerkt:

* [Bepalen hoe u apps voorbereidt op Mobile Application Management met Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune)
* [iOS-apps voorbereiden voor Mobile Application Management met de Intune App Wrapping Tool](https://docs.microsoft.com/intune/deploy-use/prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool)
* [Aan de slag met de Microsoft Intune App SDK](https://docs.microsoft.com/intune/develop/intune-app-sdk-get-started)
* [Ontwikkelaarshandleiding voor Intune App SDK voor iOS](https://docs.microsoft.com/intune/develop/intune-app-sdk-ios)

De volgende artikelen zijn nieuwe toevoegingen aan de documentenbibliotheek:

* [Intune App SDK Cordova-invoegtoepassing](https://docs.microsoft.com/intune/develop/intune-app-sdk-cordova)
* [Intune App SDK Xamarin-onderdeel](https://docs.microsoft.com/intune/develop/intune-app-sdk-xamarin)

### <a name="progress-bar-when-launching-the-company-portal-on-ios---665978--"></a>Voortgangsbalk bij het starten van de bedrijfsportal in iOS <!--665978-->
De bedrijfsportal voor iOS introduceert een voortgangsbalk op het startscherm met informatie voor de gebruiker over het laden van processen die optreden. Er is een gefaseerde rollout van de voortgangsbalk als vervanging van het kringveld. Dit betekent dat sommige van uw gebruikers de nieuwe voortgangsbalk te zien krijgen, terwijl anderen blijven het kringveld blijven zien.

## <a name="public-preview-of-the-new-intune-admin-experience-on-azure---736542--"></a>Openbare preview-versie van de nieuwe Intune-ervaring voor beheerders op Azure <!--736542-->

Aan het begin van kalenderjaar 2017 migreren we de volledige functionaliteit voor beheerders naar Azure, voor krachtig en geïntegreerd beheer van EMS-kernwerkstromen op een modern serviceplatform dat kan worden uitgebreid met Graph API’s.

Vanaf deze maand zal de openbare preview-versie van de nieuwe beheerderservaring te zien zijn voor nieuwe evaluatietenants in de Azure-portal. Tijdens de preview-periode worden de mogelijkheden en pariteit met de bestaande Intune-console iteratief geleverd.

De beheerderservaring in de Azure-portal zal gebruikmaken van de eerder aangekondigde nieuwe functionaliteit voor groepen en targeting. Wanneer uw bestaande tenant wordt gemigreerd naar de nieuwe ervaring voor groepen, vindt ook de migratie plaats naar de preview-versie van de nieuwe beheerderservaring. Als u in de tussentijd de nieuwe functionaliteit wilt testen of bekijken totdat de migratie van uw tenant is voltooid, kunt u zich aanmelden voor een nieuw Intune-evaluatieaccount of de [nieuwe documentatie](https://docs.microsoft.com/en-us/intune-azure/introduction/what-is-microsoft-intune) raadplegen.

Als u vragen hebt over de planning van de migratie van uw tenant, neemt u contact op met het migratieteam via [intunegrps@microsoft.com](mailto:intunegrps@microsoft.com).

### <a name="january-2017"></a>Januari 2017

#### <a name="custom-app-categories---748805--"></a>Aangepaste app-categorieën <!--748805-->
U kunt nu categorieën maken, bewerken en toewijzen voor apps die u aan Intune toevoegt. Categorieën kunnen momenteel alleen worden opgegeven in het Engels.

#### <a name="assign-line-of-business-apps-whether-or-not-devices-are-enrolled---748803--"></a>Toewijzen van line-of-business-apps, ongeacht of apparaten al dan niet zijn geregistreerd <!--748803-->
U kunt nu line-of-business-apps uit de store toewijzen aan gebruikers, ongeacht of hun apparaten al dan niet zijn geregistreerd bij Intune. Als een apparaat van gebruikers niet is geregistreerd bij Intune, moeten ze daarvoor de bedrijfsportalwebsite gebruiken en niet de bedrijfsportal-app.

### <a name="december-2016"></a>December 2016

#### <a name="telecom-expense-management-integration-in-public-preview-of-azure-portal--747605--"></a>Integratie van onkostenbeheer voor telecom in de openbare preview-versie van Azure-portal<!--747605-->
We beginnen nu met preview-versies van de integratie met externe systemen voor onkostenbeheer voor telecom (TEM) in de Azure-portal. U kunt Intune gebruiken om limieten in te stellen voor gegevensgebruik, voor zowel nationaal als roaming. Hierbij beginnen we met [Saaswedo](http://www.saaswedo.com). Als u deze functie in uw proeftenant wilt inschakelen, neemt u [contact op met Microsoft-ondersteuning](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune).

### <a name="see-also"></a>Zie tevens
Zie [Wat is er nieuw in Microsoft Intune?](whats-new-in-microsoft-intune.md) voor meer informatie over recente ontwikkelingen.



<!--HONumber=Dec16_HO4-->


