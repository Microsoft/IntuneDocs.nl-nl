---
title: De vroege editie | Microsoft Intune
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 11/30/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 6dd584397451d38be86fa0780efff435ffb9b2af
ms.openlocfilehash: d70ebf87bc930f853741ddc0d572d2174c636dac


---

# <a name="the-early-edition-for-microsoft-intune---december"></a>De vroege editie voor Microsoft Intune - december

De **Vroege editie** bevat een lijst met functies die worden toegevoegd aan toekomstige releases van Microsoft Intune. Deze informatie wordt in zeer beperkte mate onder geheimhoudingsverklaring verstrekt en kan worden gewijzigd. Sommige functies die hier worden vermeld, zullen mogelijk niet beschikbaar zijn op de sluitingsdatum en worden mogelijk beschikbaar gesteld in een latere release. Andere functies worden getest in een proefversie, zodat we zeker weten dat ze in gebruik kunnen worden genomen. Neem bij vragen contact op met uw contactpersoon voor Intune/projectmanagement.

Deze pagina wordt regelmatig bijgewerkt. Controleer op andere updates.

De volgende wijzigingen worden momenteel ontwikkeld voor Intune. Al deze functies worden uiteindelijk ondersteund voor implementaties voor hybride klanten (Configuration Manager met Intune). Bekijk voor meer informatie over nieuwe hybride functies onze [Wat is er nieuw-pagina voor hybride](https://technet.microsoft.com/en-US/library/mt718155(TechNet.10).aspx).

<!--736542-->
## <a name="public-preview-of-the-new-intune-admin-experience-on-azure"></a>Openbare preview-versie van de nieuwe Intune-ervaring voor beheerders op Azure

Aan het begin van kalenderjaar 2017 migreren we de volledige functionaliteit voor beheerders naar Azure, voor krachtig en geïntegreerd beheer van EMS-kernwerkstromen op een modern serviceplatform dat kan worden uitgebreid met Graph API’s.

Vanaf deze maand zal de openbare preview-versie van de nieuwe beheerderservaring te zien zijn voor nieuwe evaluatietenants in de Azure-portal. Tijdens de preview-periode worden de mogelijkheden en pariteit met de bestaande Intune-console iteratief geleverd.

De beheerderservaring in de Azure-portal zal gebruikmaken van de eerder aangekondigde nieuwe functionaliteit voor groepen en targeting. Wanneer uw bestaande tenant wordt gemigreerd naar de nieuwe ervaring voor groepen, vindt ook de migratie plaats naar de preview-versie van de nieuwe beheerderservaring. Als u in de tussentijd de nieuwe functionaliteit wilt testen of bekijken totdat de migratie van uw tenant is voltooid, kunt u zich aanmelden voor een nieuwe Intune-evaluatieaccount of de documentatie raadplegen.

Als u vragen hebt over de planning van de migratie van uw tenant, neemt u contact op met het migratieteam via [intunegrps@microsoft.com](mailto:intunegrps@microsoft.com).

### <a name="telecom-expense-management-integration-in-public-preview-of-azure-portal--747605--"></a>Integratie van onkostenbeheer voor telecom in de openbare preview-versie van Azure-portal<!--747605-->
We beginnen nu met preview-versies van de integratie met externe systemen voor onkostenbeheer voor telecom (TEM) in de Azure-portal. U kunt Intune gebruiken om limieten in te stellen voor gegevensgebruik, voor zowel nationaal als roaming. Hierbij beginnen we met [Saaswedo](http://www.saaswedo.com).

## <a name="new-capabilities"></a>Nieuwe mogelijkheden

### <a name="multi-factor-authentication-across-all-platforms---747590--"></a>Meervoudige verificatie voor alle platformen <!--747590-->
U kunt nu meervoudige verificatie (MFA) afdwingen voor een geselecteerde groep gebruikers, wanneer zij een apparaat met iOS, Android, Windows 8.1+ of Windows Phone 8.1+ inschrijven bij de Azure-beheerportal. Dit doet u door MFA te configureren voor Microsoft Intune-inschrijving in Azure Active Directory.

### <a name="conditional-access-for-mam-with-sharepoint-online---vso-679339--"></a>Voorwaardelijke toegang voor MAM met SharePoint Online <!--VSO 679339-->
U kunt de toegang tot SharePoint Online blokkeren voor apps die niet worden ondersteund door de beleidsregels voor Mobile App Management (MAM) in Intune.  U kunt aan de slag gaan met Mobile App Management in Intune via de Azure-portal. De sectie __Voorwaardelijke toegang__ op de blade __Instellingen__ bevat de optie voor SharePoint Online. Deze functie wordt afzonderlijk geleverd van de rest van de servicerelease.

### <a name="ability-to-restrict-intune-mobile-device-enrollment"></a>Mogelijkheid om de inschrijving van mobiele apparaten voor Intune te beperken
Er zijn in Intune nieuwe inschrijvingsbeperkingen toegevoegd die bepalen welke platforms voor mobiele apparaten kunnen worden ingeschreven. Intune onderscheidt platforms voor mobiele apparaten als iOS, Mac OS, Android, Windows en Windows Mobile. 
* Mac OS en Windows 8.1 of hoger worden mogelijk niet toegelaten voor inschrijving als platform voor mobiele apparaten. 
* Uitsluiting van inschrijving van mobiele apparaten betekent geen uitsluiting van inschrijving als pc-agent. 
* Alleen voor iOS geldt er een extra optie voor het blokkeren van de inschrijving van apparaten die in persoonlijk eigendom zijn. Intune markeert alle nieuwe apparaten als persoonlijk, tenzij de IT-beheerder actie onderneemt om deze te markeren als bedrijfseigen, zoals uitgelegd in [dit artikel](https://docs.microsoft.com/en-us/intune/deploy-use/manage-corporate-owned-devices).


## <a name="notices"></a>Mededelingen

### <a name="multi-factor-authentication-on-enrollment-moving-to-the-azure-portal---vso-750545--"></a>Meervoudige verificatie voor inschrijving wordt verplaatst naar de Azure-portal. <!--VSO 750545-->
Tot nu toe maakten beheerders gebruik van de Intune-console of de Configuration Manager-console (vóór release 1610) om meervoudige verificatie in te stellen voor Intune-inschrijvingen. Met deze bijgewerkte functie kunt u zich aanmelden bij de [Microsoft Azure-portal](https://manage.windowsazure.com) met uw Intune-referenties en de instellingen voor meervoudige verificatie configureren via Azure AD. Meer informatie hierover vindt u [hier](https://aka.ms/mfa_ad).

### <a name="company-portal-app-for-android-now-available-in-china---vso-658093--"></a>Bedrijfsportal-app voor Android nu beschikbaar in China <!--VSO 658093-->
De bedrijfsportal-app voor Android kan vanaf nu worden gedownload in China. Vanwege de afwezigheid van Google Play Store in China kunnen Android-apparaten apps alleen verkrijgen via Chinese app-marktplaatsen. De bedrijfsportal-app voor Android kan nu worden gedownload van 360, Tencent, Xiaomi, Wandoujia en Huawei. 

De bedrijfsportal-app voor Android maakt gebruik van Google Play Services om te communiceren met de Microsoft Intune-service. Omdat Google Play Services nog niet beschikbaar is in China, kan het tot wel acht uur duren voordat de volgende taken zijn voltooid. 

|Intune-beheerconsole| Intune bedrijfsportal-app voor Android |Intune-bedrijfsportalwebsite|   
|---|---|---|
|Volledig wissen| Een extern apparaat verwijderen| Apparaat verwijderen (lokaal en extern)|
|Selectief wissen| Apparaat opnieuw instellen| Apparaat opnieuw instellen|
|Nieuwe of bijgewerkte app-implementaties| Installeren van beschikbare line-of-business-apps| Wachtwoordcode van apparaat opnieuw instellen|
|Vergrendelen op afstand|||
|Wachtwoordcode opnieuw instellen|||

## <a name="deprecations"></a>Afschaffingen

### <a name="removal-of-exchange-online-mobile-inbox-policies---770687--"></a>Verwijderen van beleid voor mobiele postvakken van Exchange Online <!--770687-->
Vanaf december kunnen beheerders het beleid voor mobiele postvakken van Exchange Online (EAS) niet langer weergeven en configureren in de Intune-console. Deze wijziging wordt geïmplementeerd voor alle Intune-tenants in december en januari. De configuratie van bestaande beleidsregels blijft onveranderd. Voor het configureren van nieuw beleid maakt u gebruikt van de Exchange Management Shell. Meer informatie vindt u [hier](https://technet.microsoft.com/en-us/library/bb123783%28v=exchg.150%29.aspx).

### <a name="intune-av-player-image-viewer-and-pdf-viewer-apps-are-no-longer-supported-on-android---747553--"></a>De AV-speler, afbeeldingsviewer en PDF-viewer van Intune worden niet meer ondersteund op Android <!--747553-->
Vanaf half december 2016 zijn de Intune AV-speler, afbeeldingsviewer en PDF-viewer niet langer beschikbaar voor gebruikers. Deze apps zijn vervangen door de app Azure Information Protection. Meer informatie over Azure Information Protection vindt u [hier](https://docs.microsoft.com/information-protection/rms-client/mobile-app-faq).

### <a name="see-also"></a>Zie tevens
Zie [Wat is er nieuw in Microsoft Intune?](whats-new-in-microsoft-intune.md) voor meer informatie over recente ontwikkelingen.



<!--HONumber=Nov16_HO5-->


