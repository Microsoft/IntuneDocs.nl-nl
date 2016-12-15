---
title: Wat is er nieuw? | Microsoft Intune
description: Ontdek wat er nieuw is in de release van Microsoft Intune van deze maand en in oudere releases
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 12/08/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c
ms.reviewer: priyar
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 9fd309a10d9eb020795c5ce46df124b13dc1a006
ms.openlocfilehash: d117c929fbde4dd0a39503b8da695aa9c9ea91ad


---
# <a name="whats-new-in-microsoft-intune---december-2016"></a>Wat is er nieuw in Microsoft Intune - december 2016
Ontdek wat er nieuw is in deze release van Microsoft Intune. U vindt hier ook informatie over toekomstige wijzigingen waar u rekening mee moet houden én informatie over oudere releases.

> [!Note]
> Al deze functies worden uiteindelijk ondersteund voor implementaties voor hybride klanten (Configuration Manager met Intune). Bekijk voor meer informatie over nieuwe hybride functies onze [Wat is er nieuw-pagina voor hybride](https://docs.microsoft.com/en-us/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

## <a name="public-preview-of-the-new-intune-admin-experience-on-azure--736542--"></a>Openbare preview-versie van de nieuwe Intune-ervaring voor beheerders op Azure<!--736542-->
Aan het begin van kalenderjaar 2017 migreren we de volledige functionaliteit voor beheerders naar Azure, voor krachtig en geïntegreerd beheer van EMS-kernwerkstromen op een modern serviceplatform dat kan worden uitgebreid met Graph API’s. Voordat deze portal algemeen beschikbaar wordt voor alle Intune-tenants, zullen we later deze maand een preview van deze nieuwe beheerderservaring uitrollen voor een select aantal tenants.

De beheerderservaring in de Azure-portal zal gebruikmaken van de eerder aangekondigde nieuwe functionaliteit voor groepen en targeting. Wanneer uw bestaande tenant wordt gemigreerd naar de nieuwe ervaring voor groepen, vindt ook de migratie plaats naar de preview-versie van de nieuwe beheerderservaring. In de tussentijd vindt u in Azure Portal [nieuwe documentatie](https://docs.microsoft.com/intune-azure/introduction/what-is-microsoft-intune) met meer informatie over wat we in petto hebben voor Microsoft Intune.

Als u vragen hebt over de planning van de migratie van uw tenant, neemt u contact op met het migratieteam via [intunegrps@microsoft.com](mailto:intunegrps@microsoft.com).

### <a name="telecom-expense-management-integration-in-public-preview-of-azure-portal--747605--"></a>Integratie van onkostenbeheer voor telecom in de openbare preview-versie van Azure-portal<!--747605-->
We beginnen nu met preview-versies van de integratie met externe systemen voor onkostenbeheer voor telecom (TEM) in de Azure-portal. U kunt Intune gebruiken om limieten in te stellen voor gegevensgebruik, voor zowel nationaal als roaming. Hierbij beginnen we met [Saaswedo](http://www.saaswedo.com).

## <a name="new-capabilities"></a>Nieuwe mogelijkheden

### <a name="multi-factor-authentication-across-all-platforms---747590--"></a>Meervoudige verificatie voor alle platformen <!--747590-->
U kunt nu meervoudige verificatie (MFA) afdwingen voor een geselecteerde groep gebruikers, wanneer zij een apparaat met iOS, Android, Windows 8.1+ of Windows Phone 8.1+ inschrijven bij de Azure-beheerportal. Dit doet u door MFA te configureren voor Microsoft Intune-inschrijving in Azure Active Directory.

<!--VSO 679339, awaiting chrisgre for go-live--><!--### Conditional access for MAM with SharePoint Online
U kunt de toegang tot SharePoint Online blokkeren voor apps die niet worden ondersteund door de beleidsregels voor Mobile App Management (MAM) in Intune.  U kunt aan de slag gaan met Mobile App Management in Intune via de Azure-portal. De sectie __Voorwaardelijke toegang__ op de blade __Instellingen__ bevat de optie voor SharePoint Online. Deze functie wordt afzonderlijk geleverd van de rest van de servicerelease. U vindt [hier](https://docs.microsoft.com/intune/deploy-use/mam-ca-for-sharepoint-online) meer informatie over deze nieuwe functie.-->

### <a name="ability-to-restrict-mobile-device-enrollment--747596--"></a>Mogelijkheid om de registratie van mobiele apparaten te beperken<!--747596-->
Er zijn in Intune nieuwe inschrijvingsbeperkingen toegevoegd die bepalen welke platforms voor mobiele apparaten kunnen worden ingeschreven. Intune onderscheidt platforms voor mobiele apparaten als iOS, Mac OS, Android, Windows en Windows Mobile.
* Een beperking voor de registratie van mobiele apparaten, betekent niet dat de PC-clientregistratie ook is beperkt.
* Alleen voor iOS geldt er een extra optie voor het blokkeren van de inschrijving van apparaten die in persoonlijk eigendom zijn.

Intune markeert alle nieuwe apparaten als persoonlijk, tenzij de IT-beheerder actie onderneemt om deze te markeren als bedrijfseigen, zoals uitgelegd in [dit artikel](https://docs.microsoft.com/en-us/intune/deploy-use/manage-corporate-owned-devices).


## <a name="notices"></a>Mededelingen

### <a name="multi-factor-authentication-on-enrollment-moving-to-the-azure-portal---vso-750545--"></a>Meervoudige verificatie voor inschrijving wordt verplaatst naar de Azure-portal. <!--VSO 750545-->
Tot nu toe maakten beheerders gebruik van de Intune-console of de Configuration Manager-console (vóór de release oktober 2016) om meervoudige verificatie in te stellen voor Intune-registraties. Met deze bijgewerkte functie kunt u zich aanmelden bij de [Microsoft Azure-portal](https://manage.windowsazure.com) met uw Intune-referenties en de instellingen voor meervoudige verificatie configureren via Azure AD. Meer informatie hierover vindt u [hier](https://aka.ms/mfa_ad).

### <a name="company-portal-app-for-android-now-available-in-china---vso-658093--"></a>Bedrijfsportal-app voor Android nu beschikbaar in China <!--VSO 658093-->
De bedrijfsportal-app voor Android kan vanaf nu worden gedownload in China. Vanwege de afwezigheid van Google Play Store in China kunnen Android-apparaten apps alleen verkrijgen via Chinese app-marktplaatsen. De bedrijfsportal-app voor Android kan nu worden gedownload via de volgende stores:
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

## <a name="deprecations"></a>Afschaffingen

### <a name="firefox-to-no-longer-support-silverlight--vso-tba--"></a>Firefox biedt geen ondersteuning meer voor Silverlight<!--VSO TBA-->
Mozilla verwijdert per maart 2017 de ondersteuning voor Silverlight in versie 52 van de [Firefox-browser](https://www.mozilla.org/firefox). Als gevolg hiervan kunt u zich niet meer aanmelden bij de bestaande Intune-console wanneer u een latere versie dan Firefox 51 gebruikt. U kunt het beste Internet Explorer 10 of 11 voor toegang tot de beheerconsole, of een [eerdere versie dan Firefox 52](https://ftp.mozilla.org/pub/firefox/releases/). Met de overgang van Intune naar Azure Portal worden een aantal [moderne browsers](https://docs.microsoft.com/en-us/azure/azure-preview-portal-supported-browsers-devices) ondersteund zonder afhankelijkheid van Silverlight.

### <a name="removal-of-exchange-online-mobile-inbox-policies---770687--"></a>Verwijderen van beleid voor mobiele postvakken van Exchange Online <!--770687-->
Vanaf december kunnen beheerders het beleid voor mobiele postvakken van Exchange Online (EAS) niet langer weergeven en configureren in de Intune-console. Deze wijziging wordt geïmplementeerd voor alle Intune-tenants in december en januari. De configuratie van bestaande beleidsregels blijft onveranderd. Voor het configureren van nieuw beleid maakt u gebruikt van de Exchange Management Shell. Meer informatie vindt u [hier](https://technet.microsoft.com/en-us/library/bb123783%28v=exchg.150%29.aspx).

### <a name="intune-av-player-image-viewer-and-pdf-viewer-apps-are-no-longer-supported-on-android---747553--"></a>De AV-speler, afbeeldingsviewer en PDF-viewer van Intune worden niet meer ondersteund op Android <!--747553-->
Vanaf half december 2016 zijn de Intune AV-speler, afbeeldingsviewer en PDF-viewer niet langer beschikbaar voor gebruikers. Deze apps zijn vervangen door de app Azure Information Protection. Meer informatie over Azure Information Protection vindt u [hier](https://docs.microsoft.com/information-protection/rms-client/mobile-app-faq).

### <a name="see-also"></a>Zie tevens
* [Microsoft Intune-blog](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Roadmap voor cloudplatform](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Vorige versies van Intune](whats-new-archive.md)



<!--HONumber=Dec16_HO2-->


