---
title: Vroege editie | Microsoft Docs
description: 
keywords: 
author: mtillman
ms.author: mtillman
manager: angrobe
ms.date: 03/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 1ba0dab35e0da6cfe744314a4935221a206fcea7
ms.openlocfilehash: 3b355d43d4be05535f256d88a8648c2e67035882
ms.lasthandoff: 03/13/2017


---


# <a name="the-early-edition-for-microsoft-intune---march-2017"></a>De vroege editie voor Microsoft Intune - maart 2017

De **Vroege editie** bevat een lijst met functies die worden toegevoegd aan toekomstige releases van Microsoft Intune. Deze informatie wordt in zeer beperkte mate onder geheimhoudingsverklaring verstrekt en kan worden gewijzigd. Sommige functies die hier worden vermeld, zullen mogelijk niet beschikbaar zijn op de sluitingsdatum en worden mogelijk beschikbaar gesteld in een latere release. Andere functies worden getest in een proefversie, zodat we zeker weten dat ze in gebruik kunnen worden genomen. Neem bij vragen contact op met uw contactpersoon voor Intune/projectmanagement.

Deze pagina wordt regelmatig bijgewerkt. Controleer op andere updates.

> [!Note]
> De volgende wijzigingen worden momenteel ontwikkeld voor Intune. Al deze functies worden uiteindelijk ondersteund voor implementaties voor hybride klanten (Configuration Manager met Intune). Bekijk voor meer informatie over nieuwe hybride functies onze [Wat is er nieuw-pagina voor hybride](https://docs.microsoft.com/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

## <a name="new-capabilities"></a>Nieuwe mogelijkheden

### <a name="new-user-experience-for-the-company-portal-app-for-android---621622--"></a>Nieuwe gebruikerservaring voor de bedrijfsportal-app voor Android <!--621622-->

Voor de bedrijfsportal-app voor Android wordt een update uitgevoerd voor de gebruikersinterface om deze er moderner te laten uitzien en om een betere gebruikerservaring te bieden. De belangrijkste updates zijn:

- Kleuren: de tabbladkoppen van de bedrijfsportal-app hebben de kleuren van de door de IT opgegeven huisstijl.
- Apps: op het tabblad **Apps** zijn de knoppen **Aanbevolen apps** en **Alle apps** bijgewerkt.
- Zoeken: op het tabblad **Apps** is de knop **Zoeken** nu een zwevende actieknop.
- Navigeren door apps: in de weergave **Alle apps** wordt tabbladen getoond voor de opties **Aanbevolen**, **Alle** en **Categorieën** om de navigatie te vereenvoudigen.
- Ondersteuning: de tabbladen **Mijn apparaten** en **Contact opnemen met IT** zijn bijgewerkt om de leesbaarheid te vergroten.

Ga naar de [app UI updates page](whats-new-in-intune-app-ui.md] voor meer informatie over deze wijzigingen.

### <a name="signing-script-for-windows-10-company-portal---941642--"></a>Ondertekeningsscript voor de Windows 10-bedrijfsportal <!--941642-->

Voor klanten die de Windows 10-bedrijfsportal-app moeten downloaden en sideloaden, kunt u nu een script gebruiken om het proces voor het ondertekenen van apps voor uw organisatie te vereenvoudigen en stroomlijnen.   Raadpleeg [Microsoft Intune Signing Script](https://aka.ms/win10cpscript) (Ondertekeningsscript voor Microsoft Intune) voor de Windows 10-bedrijfsportal in de TechNet-galerie voor het downloaden van het script en meer informatie over het gebruik ervan. Raadpleeg [Updating your Windows 10 Company Portal app](https://blogs.technet.microsoft.com/intunesupport/2017/03/13/updating-your-windows-10-company-portal-app/) (Uw Windows 10-bedrijfsportal-app bijwerken) in het Intune Support-teamweblog voor meer informatie over deze mededeling. 

## <a name="notices"></a>Mededelingen

### <a name="improved-support-for-android-users-based-in-china---720444--"></a>Verbeterde ondersteuning voor Android-gebruikers in China <!--720444-->

Vanwege de afwezigheid van de Google Play Store in China kunnen Android-apparaten apps alleen verkrijgen via Chinese-marktplaatsen. De bedrijfsportal ondersteunt deze werkstroom door Android-gebruikers in China om te leiden zodat ze de bedrijfsportal- en Outlook-apps kunnen downloaden in lokale App Stores. Dit verbetert de gebruikerservaring wanneer beleidsregels voor voorwaardelijke toegang zijn ingeschakeld, zowel voor Mobile Device Management als voor Mobile Application Management. De bedrijfsportal- en Outlook-apps voor Android zijn beschikbaar via de volgende Chinese App Stores:

- [Baidu](https://go.microsoft.com/fwlink/?linkid=836946)
- [Xiaomi](https://go.microsoft.com/fwlink/?linkid=836947)
- [Tencent](https://go.microsoft.com/fwlink/?linkid=836949)
- [Huawei](https://go.microsoft.com/fwlink/?linkid=836948)
- [Wandoujia](https://go.microsoft.com/fwlink/?linkid=836950)

### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Apple vereist updates voor Application Transport Security <!--748318-->

Apple heeft aangekondigd dat vanaf het voorjaar van 2017 specifieke vereisten gaan gelden voor Application Transport Security (ATS). ATS wordt gebruikt om betere beveiliging af te dwingen voor alle app-communicatie die verloopt via HTTPS. Deze wijziging heeft gevolgen voor Intune-klanten die de bedrijfsportal-app gebruiken op iOS. Bekijk ons [Intune-ondersteuningsblog](https://aka.ms/compportalats) voor meer informatie.

## <a name="public-preview-of-the-new-intune-admin-experience-on-azure---736542--"></a>Openbare preview-versie van de nieuwe Intune-ervaring voor beheerders op Azure <!--736542-->

Aan het begin van kalenderjaar 2017 migreren we de volledige functionaliteit voor beheerders naar Azure, voor krachtig en geïntegreerd beheer van EMS-kernwerkstromen op een modern serviceplatform dat kan worden uitgebreid met Graph API’s.

Vanaf deze maand zal de openbare preview-versie van de nieuwe beheerderservaring te zien zijn voor nieuwe evaluatietenants in de Azure-portal. Tijdens de preview-periode worden de mogelijkheden en pariteit met de bestaande Intune-console iteratief geleverd.

De beheerderservaring in de Azure-portal zal gebruikmaken van de eerder aangekondigde nieuwe functionaliteit voor groepen en targeting. Wanneer uw bestaande tenant wordt gemigreerd naar de nieuwe ervaring voor groepen, vindt ook de migratie plaats naar de preview-versie van de nieuwe beheerderservaring. Als u in de tussentijd de nieuwe functionaliteit wilt testen of bekijken totdat de migratie van uw tenant is voltooid, kunt u zich aanmelden voor een nieuw Intune-evaluatieaccount of de [nieuwe documentatie](https://docs.microsoft.com/intune-azure/introduction/what-is-microsoft-intune) raadplegen.

### <a name="non-managed-devices-can-access-assigned-apps---664691--"></a>Niet-beheerde apparaten hebben toegang tot toegewezen apps <!--664691-->

Als onderdeel van de ontwerpwijzigingen op de bedrijfsportalwebsite kunnen iOS- en Android-gebruikers op hun niet-beheerde apparaten apps installeren die aan hen zijn toegewezen als 'beschikbaar zonder inschrijving'. Gebruikers kunnen zich met behulp van hun Intune-referenties aanmelden bij de bedrijfsportalwebsite en de lijst met aan hen toegewezen apps bekijken. De app-pakketten van de 'beschikbaar zonder inschrijving'-apps kunnen worden gedownload via de bedrijfsportalwebsite. Deze wijziging is niet van toepassing op apps die pas na inschrijving kunnen worden geïnstalleerd, omdat gebruikers wordt gevraagd hun apparaat in te schrijven als zij deze apps willen installeren.

### <a name="improvements-to-device-actions-report---677150--"></a>Verbeteringen aan het rapport Apparaatacties <!--677150-->

Er zijn verbeteringen aangebracht aan het rapport Apparaatacties voor betere prestaties. Bovendien kunt u het rapport nu filteren op basis van status. U kunt het rapport bijvoorbeeld filteren zodat alleen de apparaatacties worden weergegeven die zijn voltooid.

### <a name="actions-for-non-compliance---730266--"></a>Acties voor niet-naleving <!--730266-->

**Acties voor niet-naleving** is een nieuwe functie van nalevingsbeleid waarmee u actie kunt ondernemen voor apparaten die niet meer compatibel zijn. U kunt een of meer acties opgeven, samen met de tijdsduur waarbinnen deze acties moeten plaatsvinden. U kunt bijvoorbeeld gebruikers van niet-compatibele apparaten een melding via e-mail sturen onmiddellijk nadat de compatibiliteit van de apparaten is opgeheven, of u kunt de toegang van niet-compatibele apparaten tot bedrijfsbronnen blokkeren na een respijtperiode van 3 dagen via voorwaardelijke toegang.

### <a name="custom-app-categories---748805--"></a>Aangepaste app-categorieën <!--748805-->

U kunt nu categorieën maken, bewerken en toewijzen voor apps die u aan Intune toevoegt. Categorieën kunnen momenteel alleen worden opgegeven in het Engels.
Zie [Een app toevoegen aan Intune](/intune-azure/manage-apps/add-apps).

### <a name="assign-lob-apps-to-users-with-unenrolled-devices---748823--"></a>LOB-apps toewijzen aan gebruikers met niet-ingeschreven apparaten <!--748823-->

U kunt nu Line-Of-Business-apps uit de store toewijzen aan gebruikers, ongeacht of hun apparaten zijn ingeschreven bij Intune. Als een apparaat van een gebruiker niet is geregistreerd bij Intune, moet deze daarvoor de bedrijfsportalwebsite gebruiken en niet de bedrijfsportal-app.

### <a name="new-compliance-reports---846671--"></a>Nieuwe nalevingsrapporten <!--846671-->

U hebt nu nalevingsrapporten die u informatie bieden over de naleving van apparaten in uw bedrijf. U kunt dan ook snel aan naleving gerelateerde problemen oplossen waar uw gebruikers mee te maken krijgen. U kunt informatie bekijken over

- De algemene nalevingsstatus van apparaten
- De nalevingsstatus voor een specifieke instelling
- De nalevingsstatus voor een specifiek beleid

U kunt deze rapporten ook gebruiken om in te zoomen op een specifiek appraat, om op die manier te bekijken welke instellingen en beleidsregels van invloed zijn op dat apparaat.

### <a name="additional-windows-10-upgrade-paths---903672--"></a>Aanvullende upgradepaden voor Windows 10 <!--903672-->

U kunt nu een versie-upgradebeleid maken om apparaten te upgraden naar de volgende aanvullende Windows 10-versies:

- Windows 10 Professional
- Windows 10 Professional N
- Windows 10 Professional Education
- Windows 10 Professional Education N


### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Rechtstreekse toegang tot Apple-scenario's voor inschrijving <!--951869-->

Voor Intune-accounts die na januari 2017 zijn gemaakt, heeft Intune rechtstreekse toegang ingeschakeld tot Apple-inschrijvingsscenario's. Hiervoor is de werkstroom voor het inschrijven van apparaten gebruikt in de Azure Preview Portal. Voorheen was de Apple-inschrijvingspreview alleen toegankelijk via koppelingen in de klassieke Intune-portal. Intune-accounts die vóór januari 2017 zijn gemaakt, moeten eenmalig worden gemigreerd om de functies in Azure beschikbaar te maken. De planning voor de migratie is nog niet aangekondigd, maar de informatie wordt zo snel mogelijk beschikbaar gemaakt. Het wordt aangeraden om een testaccount te maken om de nieuwe ervaring te testen, als u met uw bestaande account geen toegang hebt tot de preview.

### <a name="see-also"></a>Zie tevens
Zie [Wat is er nieuw in Microsoft Intune?](whats-new-in-microsoft-intune.md) voor meer informatie over recente ontwikkelingen.

