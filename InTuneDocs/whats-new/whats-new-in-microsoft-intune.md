---
title: Wat is er nieuw? | Microsoft Docs
description: Ontdek wat er nieuw is in de release van Microsoft Intune van deze maand en in oudere releases
keywords: 
author: mtillman
ms.author: mtillman
manager: angrobe
ms.date: 03/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c
ms.reviewer: priyar
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: c473a1f05b0a7b0ce5205598b2b9a9b86bfe6c1d
ms.openlocfilehash: bddd8c0dc74835f74a71af1d900d43d84aab894c
ms.lasthandoff: 03/29/2017


---
# <a name="whats-new-in-microsoft-intune---march-2017"></a>Wat is er nieuw in Microsoft Intune - maart 2017
Ontdek wat er nieuw is in deze release van Microsoft Intune. U vindt hier ook informatie over toekomstige wijzigingen waar u rekening mee moet houden én informatie over oudere releases.

> [!Note]
> Al deze functies worden uiteindelijk ondersteund voor implementaties voor hybride klanten (Configuration Manager met Intune). Bekijk voor meer informatie over nieuwe hybride functies onze [Wat is er nieuw-pagina voor hybride](https://docs.microsoft.com/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

## <a name="new-capabilities"></a>Nieuwe mogelijkheden

### <a name="support-for-skycure"></a>Ondersteuning voor Skycure

U kunt nu de toegang van mobiele apparaten tot bedrijfsresources beheren door middel van voorwaardelijke toegang op basis van een risicoanalyse die door Skycure wordt uitgevoerd. Skycure is een oplossing voor de beveiliging tegen bedreigingen op mobiele apparaten die met Microsoft Intune is geïntegreerd. Risico's worden beoordeeld op basis van telemetrische gegevens die zijn verzameld op apparaten met Skycure, zoals:

- Fysieke beveiliging
- Netwerkbeveiliging
- Toepassingsbeveiliging
- Beveiliging tegen zwakke plekken

U kunt het EMS-beleid voor voorwaardelijke toegang configureren op basis van de risicoanalyse van Skycure die wordt ingeschakeld via het Intune-nalevingsbeleid voor apparaten. U kunt aan de hand van dit beleid de toegang van apparaten die niet voldoen aan het beleid tot bedrijfsresources toestaan of blokkeren op basis van de gedetecteerde bedreigingen. Zie [Skycure Mobile Threat Defense-connector](/intune/deploy-use/skycure-mobile-threat-defense-connector) voor meer informatie.

### <a name="new-user-experience-for-the-company-portal-app-for-android---621622--"></a>Nieuwe gebruikerservaring voor de bedrijfsportal-app voor Android <!--621622-->

Voor de bedrijfsportal-app voor Android wordt een update uitgevoerd voor de gebruikersinterface om deze er moderner te laten uitzien en om een betere gebruikerservaring te bieden. De belangrijkste updates zijn:

- Kleuren: de tabbladkoppen van de bedrijfsportal-app hebben de kleuren van de door de IT opgegeven huisstijl.
- Apps: op het tabblad **Apps** zijn de knoppen **Aanbevolen apps** en **Alle apps** bijgewerkt.
- Zoeken: op het tabblad **Apps** is de knop **Zoeken** nu een zwevende actieknop.
- Navigeren door apps: in de weergave **Alle apps** wordt tabbladen getoond voor de opties **Aanbevolen**, **Alle** en **Categorieën** om de navigatie te vereenvoudigen.
- Ondersteuning: de tabbladen **Mijn apparaten** en **Contact opnemen met IT** zijn bijgewerkt om de leesbaarheid te vergroten.

Zie [UI-updates voor Intune-apps voor eindgebruikers](whats-new-in-intune-app-ui.md) voor meer informatie over deze wijzigingen.

### <a name="non-managed-devices-can-access-assigned-apps---664691--"></a>Niet-beheerde apparaten hebben toegang tot toegewezen apps <!--664691-->

Als onderdeel van de ontwerpwijzigingen op de bedrijfsportalwebsite kunnen iOS- en Android-gebruikers op hun niet-beheerde apparaten apps installeren die aan hen zijn toegewezen als 'beschikbaar zonder inschrijving'. Gebruikers kunnen zich met behulp van hun Intune-referenties aanmelden bij de bedrijfsportalwebsite en de lijst met aan hen toegewezen apps bekijken. De app-pakketten van de 'beschikbaar zonder inschrijving'-apps kunnen worden gedownload via de bedrijfsportalwebsite. Deze wijziging is niet van toepassing op apps die pas na inschrijving kunnen worden geïnstalleerd, omdat gebruikers wordt gevraagd hun apparaat in te schrijven als zij deze apps willen installeren.

### <a name="signing-script-for-windows-10-company-portal---941642--"></a>Ondertekeningsscript voor de Windows 10-bedrijfsportal <!--941642-->

Als u de Windows 10-bedrijfsportal-app moet downloaden en sideloaden, kunt u nu een script gebruiken om het proces voor het ondertekenen van apps voor uw organisatie te vereenvoudigen en stroomlijnen.   Raadpleeg [Microsoft Intune Signing Script](https://aka.ms/win10cpscript) (Ondertekeningsscript voor Microsoft Intune) voor de Windows 10-bedrijfsportal in de TechNet-galerie voor het downloaden van het script en meer informatie over het gebruik ervan. Raadpleeg [Updating your Windows 10 Company Portal app](https://blogs.technet.microsoft.com/intunesupport/2017/03/13/updating-your-windows-10-company-portal-app/) (Uw Windows 10-bedrijfsportal-app bijwerken) in het Intune Support-teamweblog voor meer informatie over deze mededeling.


## <a name="notices"></a>Mededelingen

### <a name="support-for-ios-103"></a>Ondersteuning voor iOS 10.3

Op 27 maart 2017 is begonnen met het uitrollen van de iOS 10.3-release voor iOS-gebruikers. Alle bestaande Intune MDM- en MAM-scenario's zijn compatibel met de nieuwste versie van het besturingssysteem van Apple. We verwachten dat alle bestaande Intune-functies die momenteel beschikbaar zijn voor het beheer van iOS-apparaten gewoon blijven werken wanneer de gebruikers hun apparaten en apps upgraden naar iOS 10.3.

Er zijn momenteel geen problemen bekend. Als u problemen ondervindt met iOS 10.3, neemt u contact op met het [Intune-ondersteuningsteam](/intune/troubleshoot/contact-assisted-phone-support-for-microsoft-intune).

### <a name="improved-support-for-android-users-based-in-china---720444--"></a>Verbeterde ondersteuning voor Android-gebruikers in China <!--720444-->

Vanwege de afwezigheid van de Google Play Store in China kunnen Android-apparaten apps alleen verkrijgen via Chinese-marktplaatsen. De bedrijfsportal ondersteunt deze werkstroom door Android-gebruikers in China om te leiden zodat ze de bedrijfsportal- en Outlook-apps kunnen downloaden in lokale App Stores. Dit verbetert de gebruikerservaring wanneer beleidsregels voor voorwaardelijke toegang zijn ingeschakeld, zowel voor Mobile Device Management als voor Mobile Application Management. De bedrijfsportal- en Outlook-apps voor Android zijn beschikbaar via de volgende Chinese App Stores:

- [Baidu](https://go.microsoft.com/fwlink/?linkid=836946)
- [Xiaomi](https://go.microsoft.com/fwlink/?linkid=836947)
- [Tencent](https://go.microsoft.com/fwlink/?linkid=836949)
- [Huawei](https://go.microsoft.com/fwlink/?linkid=836948)
- [Wandoujia](https://go.microsoft.com/fwlink/?linkid=836950)

### <a name="best-practice-make-sure-your-company-portal-apps-are-up-to-date---879465--"></a>Aanbevolen procedure: zorg ervoor dat de bedrijfsportal-apps zijn bijgewerkt<!--879465-->

In December 2016 is een update uitgebracht waarmee Multi-Factor Authentication (MFA) kan worden afgedwongen op een groep gebruikers wanneer deze een iOS-, Android-, Windows 8.1+- of Windows Phone 8.1+-apparaat inschrijven. Deze functie kan niet werken zonder bepaalde basislijnversies van de bedrijfsportal-app voor Android (v5.0.3419.0 +) en iOS (v2.1.17 +).

Microsoft verbetert Intune voortdurend door het toevoegen van nieuwe functies aan zowel de console als de bedrijfsportal-apps op alle ondersteunde platforms. Microsoft publiceert als gevolg hiervan alleen oplossingen voor problemen die in de huidige versie van de bedrijfsportal-app worden aangetroffen. Het wordt daarom aanbevolen de nieuwste versies van de bedrijfsportal-apps te gebruiken voor de beste gebruikerservaring.

>[!Tip]
> Laat uw gebruikers hun apparaten zodanig instellen dat deze automatisch apps bijwerken uit de betreffende app store. Als u de Android-bedrijfsportal-app beschikbaar hebt gesteld op een netwerkshare, kunt u de meest recente versie downloaden van [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=49140).

### <a name="microsoft-teams-is-now-enabled-for-mam-on-ios-and-android"></a>Microsoft Teams is nu ingeschakeld voor MAM op iOS en Android

Microsoft heeft de algemene beschikbaarheid van Microsoft Teams aangekondigd. De bijgewerkte Microsoft Teams-apps voor iOS en Android zijn nu beschikbaar met de mogelijkheden van Intune Mobile App Management (MAM), zodat u uw teams in staat kunt stellen op verschillende apparaten te werken, terwijl conversaties en bedrijfsgegevens altijd beveiligd blijven. Zie [de aankondiging over Microsoft Teams](https://blogs.technet.microsoft.com/enterprisemobility/2017/03/14/microsoft-teams-is-now-generally-available-and-mam-enabled-on-ios-and-android/) op het Enterprise Mobility and Security Blog voor meer informatie.


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
* [Roadmap voor cloudplatform](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Wat is nieuw in de Azure-preview?](https://docs.microsoft.com/intune-azure/introduction/whats-new)
* [Wat is er nieuw in de gebruikersinterface van de bedrijfsportal?](https://docs.microsoft.com/intune/whats-new/whats-new-in-company-portal-ui)
* [Wat is er nieuw (archief)](whats-new-archive.md)

