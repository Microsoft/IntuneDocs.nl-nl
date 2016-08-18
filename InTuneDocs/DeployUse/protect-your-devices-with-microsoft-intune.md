---
title: Apparaten beveiligen | Microsoft Intune
description: Informatie over een aantal van de manieren waarop Intune uw apparaten kan beschermen tegen onbevoegde toegang en andere dreigingen.
keywords: 
author: Robstackmsft
manager: angrobe
ms.date: 07/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 71e0cbf3-2bfb-412e-8a12-8503df08b4cf
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: c999a852b68762002ac94269e27ecbf46c8f9999
ms.openlocfilehash: 3318590eaedc6f0e96fb463dc016d5786eeb38fb


---

# Apparaten beveiligen met Microsoft Intune
Wanneer u hebt gezorgd dat uw apparaten worden beheerd door Intune, moet u ervoor zorgen dat deze zijn beschermd tegen onbevoegde toegang en andere dreigingen. Hier zijn enkele mogelijkheden van Intune waarmee u deze doelstellingen kunt bereiken.

> [!TIP]
> In dit onderwerp worden niet alle manieren besproken waarop Intune kan helpen bij de beveiliging van uw apparaten. U kunt bijvoorbeeld Intune-beleid gebruiken om veel beveiligingsinstellingen te configureren voor uw apparaten, zoals wachtwoorden, versleutelingsinstellingen en hardwarefuncties als Bluetooth en de camera van het apparaat. Zie [Instellingen en functies op uw apparaten beheren met Microsoft Intune-beleid](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md) voor meer informatie over deze instellingen.

## Wachtwoordcodes opnieuw instellen wanneer de apparaten van gebruikers zijn vergrendeld
De eerste stap in de beveiliging van bedrijfsgegevens op mobiele apparaten is het verplichten van een wachtwoordcode om het apparaat te gebruiken. Soms moet u [een wachtwoordcode opnieuw instellen](use-remote-lock-and-passcode-reset-in-microsoft-intune.md) of een medewerker hierbij helpen door de wachtwoordcode te verwijderen of op afstand een tijdelijke wachtwoordcode in te stellen. U kunt ook [een apparaat vergrendelen op afstand](use-remote-lock-and-passcode-reset-in-microsoft-intune.md) als dit is zoekgeraakt of gestolen.

## Een extra beschermingslaag toevoegen aan Windows-apparaten
[Multi-Factor Authentication (MFA)](protect-windows-devices-with-multi-factor-authentication.md) is een veiligere manier om de identiteit van gebruikers van Windows en Windows Phone-apparaten op het netwerk te verifiëren. Met MFA moeten gebruikers hun identiteit behalve met een gebruikersnaam en wachtwoord nog bevestigen via een telefoongesprek of een tekstbericht.

## Microsoft Passport-instellingen op Windows-apparaten beheren
U kunt Intune integreren met [Microsoft Passport for Work](control-microsoft-passport-settings-on-devices-with-microsoft-intune.md). Dit is een alternatieve aanmeldingsmethode voor Windows 10 en hoger. Voor Microsoft Passport for Work wordt Active Directory of een Azure Active Directory-account gebruikt om een wachtwoord, smartcard of virtuele smartcard te vervangen.

## Bypass van activeringsvergrendeling op iOS-apparaten
Activeringsvergrendeling is een functie waarmee gebruikers apparaten kunnen beveiligen doordat hun Apple-id en wachtwoord moet worden ingevoerd voordat iemand het apparaat kan wissen of opnieuw activeren. Dit kan echter leiden tot problemen, bijvoorbeeld wanneer de gebruiker het bedrijf verlaat zonder de vergrendeling te verwijderen. [Bypass van activeringsvergrendeling voor iOS](help-protect-ios-devices-with-activation-lock-bypass-for-microsoft-intune.md) kan u helpen de vergrendeling te verwijderen van iOS-apparaten die onder supervisie staan, zodat u ze opnieuw kunt toewijzen of kunt wissen.

## Windows-pc's beveiligen die door de Intune-client worden beheerd
Intune blijft ondersteuning bieden voor beveiligingsbeleid voor Windows-pc's die u niet registreert, maar met de clientsoftware van Intune beheert. Zie [Use policies to help protect Windows PCs that run the Intune client software](policies-to-protect-windows-pcs-in-microsoft-intune.md) (Beleid gebruiken voor het beveiligen van Windows-pc’s waarop de Intune-clientsoftware wordt uitgevoerd) als u wilt weten hoe u dit beleid kunt gebruiken om uw Windows-pc's te beveiligen.



<!--HONumber=Aug16_HO2-->


