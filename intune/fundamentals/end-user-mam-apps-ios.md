---
title: iOS-apps met beveiligingsbeleid voor apps
description: In dit onderwerp wordt beschreven wat u kunt verwachten wanneer uw iOS-app wordt beheerd door een app-beveiligingsbeleid.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 02/15/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.assetid: b57e6525-b57c-4cb4-a84c-9f70ba1e8e19
ms.reviewer: andcerat
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: a1a3dcd7068a004f94b97b5ec6c43c609662a76d
ms.sourcegitcommit: 60f0ff6d2efbae0f2ce14b9a9f3f9267309e209b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/01/2019
ms.locfileid: "73414564"
---
# <a name="what-to-expect-when-your-ios-app-is-managed-by-app-protection-policies"></a>Wat u kunt verwachten wanneer uw iOS-app wordt beheerd door een app-beveiligingsbeleid

 In dit onderwerp wordt de gebruikerservaring beschreven voor het gebruik van apps waarop app-beveiligingsbeleid is toegepast. App-beveiligingsbeleid wordt alleen toegepast wanneer apps worden gebruikt in een werkcontext, bijvoorbeeld wanneer de gebruiker apps gebruikt met een werkaccount of bestanden opent die zijn opgeslagen in de OneDrive voor Bedrijven-locatie van uw bedrijf.

## <a name="access-apps"></a>Toegang tot apps

Als het apparaat **niet is geregistreerd bij Intune**, wordt de gebruiker gevraagd de app opnieuw te starten wanneer deze voor het eerst wordt gebruikt. Er moet opnieuw worden opgestart zodat het app-beveiligingsbeleid kan worden toegepast op de app.

<!--- The following screenshot from the Skype app illustrates this restart request: --->

<!---  ![Screenshot of the iOS device showing PIN prompt](./media/end-user-mam-apps-ios/iOS_AppPINPrompt.png) --->

Op apparaten die zijn **ingeschreven voor beheer in Intune**, wordt een bericht aan de gebruiker weergegeven dat de app nu wordt beheerd.

## <a name="use-apps-with-multi-identity-support"></a>Apps met ondersteuning voor meerdere identiteiten gebruiken

Met apps die ondersteuning bieden voor meerdere identiteiten, kunt u verschillende accounts (zakelijk en persoonlijk) gebruiken voor toegang tot dezelfde apps, terwijl beveiligingsbeleid voor apps wordt toegepast wanneer de apps worden gebruikt in zakelijke context.  

De gebruiker moet bijvoorbeeld een pincode invoeren bij het openen van werkgegevens. Voor de **Outlook-app** wordt de gebruiker gevraagd een pincode in te voeren bij het starten van de app. Voor de **OneDrive app** wordt de gebruiker om een pincode gevraagd wanneer deze het werkaccount typt.  Bij Microsoft **Word**, **PowerPoint** en **Excel** wordt de gebruiker om een pincode gevraagd wanneer deze documenten opent die zijn opgeslagen op de OneDrive voor Bedrijven-locatie van het bedrijf.

- Meer informatie over de apps die ondersteuning bieden voor [app-beveiliging en meervoudige identiteiten](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) met Intune.

App-beveiligingsbeleid wordt alleen toegepast in een werkcontext. Daarom is het mogelijk dat de app zich anders gedraagt, afhankelijk of het om een persoonlijke of werkcontext gaat.

## <a name="manage-user-accounts-on-the-device"></a>Gebruikersaccounts op het apparaat beheren

Met toepassingen met meerdere identiteiten kunnen gebruikers meerdere accounts toevoegen.  Intune-app-beveiliging ondersteunt slechts één beheerd account.  Intune-app-beveiliging beperkt niet het aantal niet-beheerde accounts.

Wanneer er een beheerd account in een toepassing is:

- Als een gebruiker een tweede beheerd account probeert toe te voegen, moet de gebruiker selecteren welk beheerd account moet worden gebruikt.  Het andere account wordt verwijderd.
- Als de IT-beheerder een beleid toevoegt aan een tweede bestaand account, moet de gebruiker selecteren welk beheerd account moet worden gebruikt.  Het andere account wordt verwijderd.

Lees het volgende voorbeeldscenario om meer inzicht te krijgen in hoe meerdere gebruikersaccounts worden behandeld.

Gebruiker A werkt voor twee bedrijven: **bedrijf X** en **bedrijf Y**. Gebruiker A heeft voor elk bedrijf een werkaccount en voor beide accounts wordt gebruikgemaakt van Intune om app-beveiligingsbeleid te implementeren. **Bedrijf X** implementeert app-beveiligingsbeleid **voordat** **bedrijf Y** dat doet. Het account dat is gekoppeld aan **bedrijf X** krijgt als eerste het app-beveiligingsbeleid. Als u wilt dat het gebruikersaccount dat is gekoppeld aan bedrijf Y door het app-beveiligingsbeleid wordt beheerd, moet u het gebruikersaccount dat is gekoppeld aan bedrijf X verwijderen en het gebruikersaccount toevoegen dat is gekoppeld aan bedrijf Y.

### <a name="add-a-second-account"></a>Een tweede account toevoegen

Als u een iOS-apparaat gebruikt en u een tweede werkaccount op dat apparaat probeert toe te voegen, ziet u mogelijk een blokkeringsbericht. De accounts worden weergegeven en u kunt kiezen welk account u wilt verwijderen.

## <a name="next-steps"></a>Volgende stappen

[Wat u kunt verwachten wanneer uw Android-app wordt beheerd door een app-beveiligingsbeleid](end-user-mam-apps-android.md)
