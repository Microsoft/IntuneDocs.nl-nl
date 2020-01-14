---
title: iOS-apps met beveiligingsbeleid voor apps
description: In dit onderwerp wordt beschreven wat u kunt verwachten wanneer uw iOS-app wordt beheerd door een app-beveiligingsbeleid.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 11/18/2019
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
ms.openlocfilehash: 165ce160339647e396b9cfc3a8374f21c77665f8
ms.sourcegitcommit: f9dc50642efa8656054ef67f9335b9b46b655f93
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/02/2020
ms.locfileid: "75606618"
---
# <a name="what-to-expect-when-your-ios-app-is-managed-by-app-protection-policies"></a>Wat u kunt verwachten wanneer uw iOS-app wordt beheerd door een app-beveiligingsbeleid

Het Intune-app-beveiligingsbeleid is van toepassing op apps die worden gebruikt voor werk of school. Dit betekent dat wanneer uw werknemers en studenten hun apps in een privécontext gebruiken, er geen verschil is in hun ervaring. Als ze apps voor werk of school gebruiken, kunnen ze echter de vraag krijgen accountbeslissingen te nemen, hun instellingen bij te werken of contact met u op te nemen voor hulp. Gebruik dit artikel voor meer informatie over wat er gebeurt als uw gebruikers proberen toegang te krijgen tot apps die zijn beveiligd met Intune.  

## <a name="access-apps"></a>Toegang tot apps

Als het apparaat **niet is geregistreerd bij Intune**, wordt de gebruiker gevraagd de app opnieuw te starten wanneer deze voor het eerst wordt gebruikt. Er moet opnieuw worden opgestart zodat het app-beveiligingsbeleid kan worden toegepast op de app.

<!--- The following screenshot from the Skype app illustrates this restart request: --->

<!---  ![Screenshot of the iOS device showing PIN prompt](./media/end-user-mam-apps-ios/iOS_AppPINPrompt.png) --->

Op apparaten die zijn **ingeschreven voor beheer in Intune**, wordt een bericht aan de gebruiker weergegeven dat de app nu wordt beheerd.

## <a name="use-apps-with-multi-identity-support"></a>Apps met ondersteuning voor meerdere identiteiten gebruiken

Met apps die ondersteuning bieden voor meerdere identiteiten, kunt u verschillende werk- en privéaccounts gebruiken om toegang te krijgen tot dezelfde apps. App-beveiligingsbeleid, zoals het invoeren van een pincode voor het apparaat, wordt geactiveerd wanneer gebruikers deze apps openen voor werk of school.   

Het kan voorkomen dat gebruikers op verschillende manieren wordt gevraagd hun pincode in te voeren voor hun apps, afhankelijk van hoe u het beleid configureert.  U kunt uw beleid bijvoorbeeld zodanig configureren dat:       
* Microsoft Outlook de gebruiker vraagt een pincode in te voeren bij het starten van de app. 
* OneDrive de gebruiker vraagt om een pincode wanneer hij zich aanmeldt bij zijn werkaccount.  
* Microsoft Word, PowerPoint en Excel de gebruiker om een pincode vraagt wanneer deze documenten opent die zijn opgeslagen op de OneDrive voor Bedrijven-locatie van het bedrijf.  

- Meer informatie over de apps die ondersteuning bieden voor [app-beveiliging en meervoudige identiteiten](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) met Intune.  

## <a name="manage-user-accounts-on-the-device"></a>Gebruikersaccounts op het apparaat beheren  

Met Intune-app-beveiligingsbeleid worden gebruikers beperkt tot één beheerd werk- of schoolaccount per app. Het beveiligingsbeleid voor apps beperkt het aantal niet-beheerde accounts dat een gebruiker kan toevoegen.   

- Als een gebruiker een tweede beheerd account probeert toe te voegen, moet de gebruiker selecteren welk beheerd account moet worden gebruikt. Als de gebruiker het tweede account toevoegt, wordt het eerste account verwijderd.
- Als u beveiligingsbeleid toevoegt aan een ander gebruikersaccount, wordt de gebruiker gevraagd welk beheerd account moet worden gebruikt. Het andere account wordt verwijderd. 

Sommige gebruikers krijgen de optie niet om te schakelen tussen beheerde accounts of deze te selecteren. De optie is niet beschikbaar op apparaten die:
* worden beheerd door Intune  
* worden beheerd door externe oplossingen voor bedrijfsmobiliteitsbeheer en die zijn geconfigureerd met de instelling IntuneMAMUPN 

Het volgende voorbeeldscenario beschrijft hoe meerdere gebruikersaccounts worden behandeld:  

Gebruiker A werkt voor twee bedrijven: **bedrijf X** en **bedrijf Y**. Gebruiker A heeft voor elk bedrijf een werkaccount en voor beide accounts wordt gebruikgemaakt van Intune om app-beveiligingsbeleid te implementeren. **Bedrijf X** implementeert app-beveiligingsbeleid **voordat** **bedrijf Y** dat doet. Het account dat is gekoppeld aan **bedrijf X** krijgt als eerste het app-beveiligingsbeleid. Als u wilt dat het gebruikersaccount dat is gekoppeld aan bedrijf Y door het app-beveiligingsbeleid wordt beheerd, moet u het gebruikersaccount dat is gekoppeld aan bedrijf X verwijderen en het gebruikersaccount toevoegen dat is gekoppeld aan bedrijf Y.  

## <a name="next-steps"></a>Volgende stappen

[Wat u kunt verwachten wanneer uw Android-app wordt beheerd door een app-beveiligingsbeleid](end-user-mam-apps-android.md)
