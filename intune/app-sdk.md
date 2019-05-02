---
title: Voordelen van de Intune App SDK
titleSuffix: Microsoft Intune
description: De Microsoft Intune App SDK is beschikbaar voor zowel het iOS-platform als het Android-platform en maakt Mobile App Management-functies mogelijk met Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 04/08/2019
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: cd9f05e7-26e6-45e0-8d38-67d8232b1cae
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 046c82a1b149f33e20a21adf931a30cc812e3f10
ms.sourcegitcommit: 364a7dbc7eaa414c7a9c39cf53eb4250e1ad3151
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/09/2019
ms.locfileid: "59292446"
---
# <a name="microsoft-intune-app-sdk-overview"></a>Overzicht van de Microsoft Intune App SDK
Met de Intune App SDK voor iOS en Android kan uw app worden in geschakeld voor ondersteuning van [Intune-beleid voor app-beveiliging](app-protection-policy.md). Wanneer uw app heeft de app-beveiligingsbeleid is toegepast, kunnen worden beheerd door Intune en wordt herkend door Intune als een beheerde app. De SDK streeft ernaar om het aantal door de app-ontwikkelaar vereiste codewijzigingen zo klein mogelijk te maken. U ziet dat u de meeste van de SDK-functies kunt inschakelen zonder het gedrag van uw app te wijzigen. U kunt de API's van de SDK gebruiken voor het aanpassen van uw app-gedrag voor ondersteuning van functies waarvoor de deelname van uw app is vereist, voor een verbeterde ervaring voor eindgebruikers en IT-beheerders.

Als u uw app hebt ingeschakeld voor ondersteuning van het Intune-beleid voor app-beveiliging, kunnen IT-beheerders deze beleidsregels implementeren om de bedrijfsgegevens in de app te beveiligen.

## <a name="app-protection-features"></a>Functies voor app-beveiliging

Hier volgen enkele voorbeelden van functies voor Intune-beleid voor app-beveiliging die kunnen worden ingeschakeld met de SDK.

### <a name="control-users-ability-to-move-corporate-files"></a>Bepalen of gebruikers bedrijfsdocumenten kunnen verplaatsen
IT-beheerders kunnen bepalen waar werk- of schoolgegevens in de app naartoe kunnen worden verplaatst. Ze kunnen bijvoorbeeld een beleid implementeren waarbij de app geen back-up in de cloud kan maken van bedrijfsgegevens.

### <a name="configure-clipboard-restrictions"></a>Beperkingen van Klembord configureren
IT-beheerders kunnen het gedrag van het Klembord in door Intune beheerde apps configureren. Ze kunnen bijvoorbeeld een beleid implementeren om te voorkomen dat eindgebruikers gegevens uit de app knippen of kopiëren en deze in een niet-beheerde, persoonlijke app plakken.

### <a name="enforce-encryption-on-saved-data"></a>Versleuteling van opgeslagen gegevens afdwingen
IT-beheerders kunnen beleid afdwingen dat ervoor zorgt dat de gegevens die door de app op het apparaat worden opgeslagen, worden versleuteld.

### <a name="remotely-wipe-corporate-data"></a>Bedrijfsgegevens op afstand wissen
IT-beheerders kunnen op afstand bedrijfsgegevens wissen uit een met Intune beheerde app. Deze functie is op de identiteit gebaseerd en verwijdert alleen bestanden die betrekking hebben op de zakelijke identiteit van de eindgebruiker. Hiertoe vereist de functie deelname van de app. De app aangeven voor welke identiteit het wissen moet plaatsvinden op basis van de instellingen van de gebruiker. Als dergelijke instellingen niet door de gebruiker in de app zijn opgegeven, is het standaardgedrag om de toepassingsmap te wissen en de eindgebruiker te informeren dat de toegang is verwijderd.

### <a name="enforce-the-use-of-a-managed-browser"></a>Het gebruik van een beheerde browser afdwingen
IT-beheerders kunnen afdwingen dat webkoppelingen in de app worden geopend met de [Intune Managed Browser-app](app-configuration-managed-browser.md). Deze functionaliteit zorgt ervoor dat de koppelingen die worden weergegeven in een bedrijfsomgeving binnen het domein van door Intune beheerde apps worden gehouden.

### <a name="enforce-a-pin-policy"></a>Een pincodebeleid afdwingen
IT-beheerders kunnen vereisen dat eindgebruikers een pincode invoeren om bedrijfsgegevens in de app te openen. Dit zorgt ervoor dat de persoon die de app gebruikt, dezelfde is als degene die zich aanvankelijk heeft aangemeld met een werk- of schoolaccount. Wanneer eindgebruikers hun pincode configureren, gebruikt Intune App SDK Azure Active Directory om te controleren of de referenties van eindgebruikers overeenkomen met het ingeschreven Intune account.

### <a name="require-users-to-sign-in-with-a-work-or-school-account-for-app-access"></a>Instellen dat gebruikers zich alleen met een werk-of schoolaccount kunnen aanmelden voor app-toegang
IT-beheerders kunnen vereisen dat gebruikers zich aanmelden met hun werk- of schoolaccount om toegang tot de app te krijgen. De Intune App SDK gebruikt Azure Active Directory voor eenmalige aanmelding, waarbij de referenties, nadat deze zijn opgegeven, opnieuw worden gebruikt bij alle daaropvolgende aanmeldingen. We bieden ook ondersteuning voor verificatie van oplossingen voor identiteitsbeheer die zijn gefedereerd met Azure Active Directory.

### <a name="check-device-health-and-compliance"></a>De status en compatibiliteit van apparaten controleren
IT-beheerders kunnen een status en de compatibiliteit van apparaten met Intune-beleid controleren voordat eindgebruikers toegang tot de app krijgen. In iOS controleert dit beleid of het apparaat jailbroken, ofwel gekraakt, is. In Android controleert dit beleid of het apparaat geroot is.

### <a name="support-multi-identity"></a>Meerdere identiteiten ondersteunen
Ondersteuning voor meerdere identiteiten is een functie van de SDK die co-existentie van door beleid beheerde (zakelijke) accounts en niet-beheerde (privé-)accounts in één enkele app mogelijk maakt.

Zo configureren veel gebruikers bijvoorbeeld zowel bedrijfs- als persoonlijke e‑mailaccounts in de mobiele Office-app voor iOS en Android. Wanneer een gebruiker zich toegang verschaft tot gegevens in een bedrijfsaccount, moet de IT-beheerder erop kunnen vertrouwen dat het beleid voor app-beveiliging wordt toegepast. Wanneer een gebruiker zich echter toegang wil verschaffen tot een persoonlijk e-mailaccount, moeten die gegevens buiten de controle van de IT-beheerder blijven. De Intune App SDK bereikt dit door het beleid voor app-beveiliging **alleen** toe te passen op de bedrijfsidentiteit in de app.

De functie voor het gebruik van meerdere identiteiten helpt bij het oplossen van het gegevensbeveiligingsprobleem waarmee organisaties worden geconfronteerd door het gebruik van store-apps die ondersteuning bieden voor zowel privé- als werkaccounts.
 
### <a name="app-protection-without-device-enrollment"></a>App-beveiliging zonder apparaatregistratie

>[!IMPORTANT]
>App-beveiligingsbeleid van Intune zonder apparaatregistratie is beschikbaar voor de Intune App Wrapping Tool, Intune App SDK voor Android, Intune App SDK voor iOS en Intune App SDK Xamarin Bindings.

Veel gebruikers met privé-apparaten willen toegang tot bedrijfsgegevens zonder hun privé-apparaat te moeten registreren met een Mobile Device Management-provider (MDM-product). Omdat voor MDM-registratie algemeen beheer van het apparaat is vereist, willen gebruikers de algemene controle over hun persoonlijk apparaat niet altijd aan hun bedrijf geven.

Met app-beheer zonder apparaatregistratie kan de Microsoft Intune-service het beleid voor app-beveiliging rechtstreeks voor een app implementeren zonder voor de implementatie van het beleid afhankelijk te zijn van apparaatbeheer.

### <a name="on-demand-application-vpn-connections-with-citrix-mvpn"></a>VPN-verbindingen met Citrix mVPN op aanvraag voor toepassingen 
U kunt apparaten en apps beheren met een combinatie van Citrix XenMobile MDX en Microsoft Intune. Deze combinatie betekent dat u apps kunt beheren met het Intune-beveiligingsbeleid voor apps met behulp van de mVPN-technologie van Citrix. De integratie met Citrix is beschikbaar voor de Intune App SDK voor iOS en Android, en met de Intune App Wrapping Tool voor iOS en Android (met de citrix-vlag).
 
Zie [Informatie over de MDX Toolkit](https://docs.citrix.com/en-us/mdx-toolkit/10/about-mdx-toolkit.html), [Citrix MDX App Wrapper voor iOS](https://docs.citrix.com/en-us/mdx-toolkit/10/xmob-mdx-kit-app-wrap-ios.html) en de [Citrix MDX App Wrapper voor Android](https://docs.citrix.com/en-us/mdx-toolkit/10/xmob-mdx-kit-app-wrap-android.html) voor meer informatie over Citrix MDX.

## <a name="next-steps"></a>Volgende stappen

- [Aan de slag met de Microsoft Intune App SDK](app-sdk-get-started.md).
