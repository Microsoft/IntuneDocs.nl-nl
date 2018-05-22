---
title: Voordelen van de Intune App SDK
titlesuffix: Microsoft Intune
description: De Microsoft Intune App SDK is beschikbaar voor zowel het iOS-platform als het Android-platform en maakt Mobile App Management-functies mogelijk met Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 05/15/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: cd9f05e7-26e6-45e0-8d38-67d8232b1cae
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 33e1cb6953891fa6d62841d10bc8011768938ee1
ms.sourcegitcommit: 34e96e57af6b861ecdfea085acf3c44cff1f3d43
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/17/2018
---
# <a name="intune-app-sdk-overview"></a>Overzicht van de Intune App SDK
Met de Intune App SDK voor iOS en Android kan uw app worden in geschakeld voor Intune-beleid voor app-beveiliging. Deze streeft ernaar om het aantal door de app-ontwikkelaar vereiste codewijzigingen zo klein mogelijk te maken. U ziet dat u de meeste van de SDK-functies kunt inschakelen zonder het gedrag van uw app te wijzigen. U kunt de API's gebruiken voor het aanpassen van uw app-gedrag voor functies waarvoor de deelname van uw app is vereist, voor een verbeterde ervaring voor eindgebruikers en IT-beheerders.

Als u uw app hebt ingeschakeld voor beleid voor app-beveiliging, kunnen IT-beheerders deze beleidsregels implementeren om de bedrijfsgegevens in de app te beveiligen.

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
IT-beheerders kunnen afdwingen dat webkoppelingen in de app worden geopend met de [Intune Managed Browser-app](/intune-classic/deploy-use/manage-internet-access-using-managed-browser-policies). Deze functionaliteit zorgt ervoor dat de koppelingen die worden weergegeven in een bedrijfsomgeving binnen het domein van door Intune beheerde apps worden gehouden.

### <a name="enforce-a-pin-policy"></a>Een pincodebeleid afdwingen
IT-beheerders kunnen vereisen dat eindgebruikers een pincode invoeren om bedrijfsgegevens in de app te openen. Dit zorgt ervoor dat de persoon die de app gebruikt, dezelfde is als degene die zich aanvankelijk heeft aangemeld met een werk- of schoolaccount. Wanneer eindgebruikers hun pincode configureren, gebruikt Intune App SDK Azure Active Directory om te controleren of de referenties van eindgebruikers overeenkomen met het ingeschreven Intune account.

### <a name="require-users-to-sign-in-with-work-or-school-account-for-app-access"></a>Instellen dat gebruikers zich alleen met een werk-of schoolaccount kunnen aanmelden voor app-toegang
IT-beheerders kunnen vereisen dat gebruikers zich aanmelden met hun werk- of schoolaccount om toegang tot de app te krijgen. De Intune App SDK gebruikt Azure Active Directory voor eenmalige aanmelding, waarbij de referenties, nadat deze zijn opgegeven, opnieuw worden gebruikt bij alle daaropvolgende aanmeldingen. We bieden ook ondersteuning voor verificatie van oplossingen voor identiteitsbeheer die zijn gefedereerd met Azure Active Directory.

### <a name="check-device-health-and-compliance"></a>De status en compatibiliteit van apparaten controleren
IT-beheerders kunnen een status en de compatibiliteit van apparaten met Intune-beleid controleren voordat eindgebruikers toegang tot de app krijgen. In iOS controleert dit beleid of het apparaat jailbroken, ofwel gekraakt, is. In Android controleert dit beleid of het apparaat geroot is.

### <a name="multi-identity-support"></a>Ondersteuning voor meerdere identiteiten
Ondersteuning voor meerdere identiteiten is een functie van de SDK die co-existentie van door beleid beheerde (zakelijke) accounts en niet-beheerde (privé-)accounts in één enkele app mogelijk maakt.

Zo configureren veel gebruikers bijvoorbeeld zowel bedrijfs- als persoonlijke e‑mailaccounts in de mobiele Office-app voor iOS en Android. Wanneer een gebruiker zich toegang verschaft tot gegevens in een bedrijfsaccount, moet de IT-beheerder erop kunnen vertrouwen dat het beleid voor app-beveiliging wordt toegepast. Wanneer een gebruiker zich echter toegang wil verschaffen tot een persoonlijk e-mailaccount, moeten die gegevens buiten de controle van de IT-beheerder blijven. De Intune App SDK bereikt dit door het beleid voor app-beveiliging **alleen** toe te passen op de bedrijfsidentiteit in de app.

De functie voor het gebruik van meerdere identiteiten helpt bij het oplossen van het gegevensbeveiligingsprobleem waarmee organisaties worden geconfronteerd door het gebruik van store-apps die ondersteuning bieden voor zowel privé- als werkaccounts.
 
### <a name="app-protection-without-device-enrollment"></a>App-beveiliging zonder apparaatregistratie

>[!IMPORTANT]
>App-beveiligingsbeleid van Intune zonder apparaatregistratie is beschikbaar voor de Intune App Wrapping Tool, Intune App SDK voor Android, Intune App SDK voor iOS en Intune App SDK Xamarin Bindings.

Veel gebruikers met privé-apparaten willen toegang tot bedrijfsgegevens zonder hun privé-apparaat te moeten registreren met een Mobile Device Management-provider (MDM-product). Omdat voor MDM-registratie algemeen beheer van het apparaat is vereist, willen gebruikers de algemene controle over hun persoonlijk apparaat niet altijd aan hun bedrijf geven.

Met app-beheer zonder apparaatregistratie kan de Microsoft Intune-service het beleid voor app-beveiliging rechtstreeks voor een app implementeren zonder voor de implementatie van het beleid afhankelijk te zijn van apparaatbeheer.
