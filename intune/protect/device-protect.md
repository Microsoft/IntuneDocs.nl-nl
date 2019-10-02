---
title: Apparaten beveiligen met Microsoft Intune
titleSuffix: Microsoft Intune
description: Informatie over een aantal van de manieren waarop Intune uw apparaten kan beschermen tegen onbevoegde toegang en andere dreigingen.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 07/19/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: angerobe
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 19cad6ede0f3d3fb87e067d6bdcdfa5adf0219bf
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/02/2019
ms.locfileid: "71721406"
---
# <a name="protect-devices-with-microsoft-intune"></a>Apparaten beveiligen met Microsoft Intune

Microsoft Intune helpt bij het beveiligen van de apparaten die u beheert en de gegevens op die apparaten.

## <a name="device-configuration"></a>Apparaatconfiguratie
Met het [configuratiebeleid](../configuration/device-profiles.md) van Intune kunt u apparaten beveiligen en configureren door een groot aantal instellingen en functies te beheren. Bijvoorbeeld:

- U kunt het gebruik van hardwarefuncties op het apparaat beperken, zoals de camera of Bluetooth.
- U kunt compatibele en niet-compatibele apps configureren. U wordt gewaarschuwd als een niet-compatibele app wordt geïnstalleerd (op sommige platforms kan de installatie daadwerkelijk worden geblokkeerd).

## <a name="reset-passcodes-when-users-are-locked-out-of-their-devices"></a>Wachtwoordcodes opnieuw instellen wanneer de apparaten van gebruikers zijn vergrendeld
De eerste stap in het beveiligen van bedrijfsgegevens op mobiele apparaten is het vereisen van een wachtwoordcode om het apparaat te kunnen gebruiken. U zult daarom soms een [wachtwoordcode opnieuw moeten instellen](../remote-actions/device-passcode-reset.md) of een medewerker moeten helpen om dit te doen door een wachtwoordcode te verwijderen of door op afstand een tijdelijke wachtwoordcode in te stellen. U kunt ook [een apparaat op afstand vergrendelen](../remote-actions/device-remote-lock.md) als dit is zoekgeraakt of gestolen.

## <a name="retire-devices-and-remove-data"></a>Apparaten buiten gebruik stellen en gegevens verwijderen
Wanneer een apparaat moet worden [verwijderd uit het beheer van Intune](../remote-actions/devices-wipe.md) (bijvoorbeeld wanneer een gebruiker vertrekt of het apparaat is kwijtgeraakt of gestolen), wilt u waarschijnlijk de gegevens op het apparaat verwijderen. Intune biedt een aantal methoden voor het beveiligen van uw bedrijfsgegevens.

## <a name="require-devices-to-be-compliant"></a>Vereisen dat apparaten aan het beleid voldoen
Intune heeft een [nalevingsbeleid voor apparaten](device-compliance-get-started.md) waarmee u apparaten kunt evalueren (en in sommige gevallen kunt herstellen) die niet compatibel zijn met regels die u opgeeft. U kunt bijvoorbeeld rapporten verkrijgen over:
- opengebroken iOS-apparaten
- versleutelde of niet-versleutelde apparaten
- de status van Windows 10-apparaten (zoals bepaald door de Health Attestation Service).

## <a name="protect-apps-and-the-data-they-use"></a>Apps en de gegevens die ze gebruiken beveiligen
Intune biedt een reeks functies waarmee u apps en de gegevens ervan kunt beveiligen. Met Mobile Application Management-beleid (MAM-beleid) kunt u bijvoorbeeld:
- voorkomen dat er een back-up wordt gemaakt van gegevens uit een beveiligde app
- kopiëren en plakken in andere apps beperken
- een pincode vereisen voor toegang tot een app Zie [Apps en gegevens beschermen met Microsoft Intune](../apps/app-protection-policy.md) voor meer informatie

## <a name="add-an-additional-layer-of-protection-to-devices"></a>Een extra beschermingslaag toevoegen aan apparaten
[Multi-Factor Authentication (MFA)](../enrollment/multi-factor-authentication.md) is een veiligere manier om de identiteit van gebruikers van apparaten op het netwerk te verifiëren.  Met MFA moeten gebruikers hun identiteit niet alleen met een gebruikersnaam en wachtwoord, maar ook via een telefoongesprek of tekstbericht bevestigen.

## <a name="control-windows-hello-for-business-settings-on-windows-devices"></a>Instellingen van Windows Hello voor Bedrijven beheren op Windows-apparaten
Intune biedt de mogelijkheid van integratie met [Windows Hello voor Bedrijven](windows-hello.md). Dit is een alternatieve aanmeldingsmethode voor Windows 10 en hoger, waarbij Active Directory of een Azure Active Directory-account wordt gebruikt ter vervanging van een wachtwoord, smartcard of virtuele smartcard.

## <a name="bypass-activation-lock-on-ios-devices"></a>Bypass van activeringsvergrendeling op iOS-apparaten
Activeringsslot is een functie waarmee de apparaten van gebruikers kunnen worden beveiligd. Bij gebruik van deze functie moet er een Apple ID en wachtwoord worden ingevoerd om het apparaat te kunnen wissen of om het opnieuw te activeren. De functie kan echter leiden tot problemen, bijvoorbeeld wanneer de gebruiker het bedrijf verlaat zonder de vergrendeling te verwijderen. [Bypass van activeringsvergrendeling voor iOS](../remote-actions/device-activation-lock-bypass.md) kan u helpen de vergrendeling te verwijderen van iOS-apparaten die onder supervisie staan, zodat u ze opnieuw kunt toewijzen of kunt wissen.

## <a name="next-steps"></a>Volgende stappen

Meer informatie over [Mobile Threat Defense](mobile-threat-defense.md)
