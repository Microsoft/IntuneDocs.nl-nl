---
title: Apparaten beveiligen met Microsoft Intune | Microsoft Docs
description: Informatie over een aantal van de manieren waarop Intune uw apparaten kan beschermen tegen onbevoegde toegang en andere dreigingen.
keywords: 
author: Robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 71e0cbf3-2bfb-412e-8a12-8503df08b4cf
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 10191f27ae7efd097ea6e74b557776f8be8fe6e6
ms.openlocfilehash: 042c5673c48bb19aacd624028260267670f9846e
ms.lasthandoff: 02/21/2017


---

# <a name="protect-devices-with-microsoft-intune"></a>Apparaten beveiligen met Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Microsoft Intune biedt allerlei mogelijkheden waarmee u de apparaten die u beheert en de gegevens op die apparaten kunt beveiligen. Raadpleeg dit onderwerp voor basiskennis over deze mogelijkheden en ontdek hoe u aan meer informatie komt.

## <a name="general-ways-to-protect-all-devices"></a>Algemene manieren om alle apparaten te beveiligen

### <a name="device-configuration"></a>Apparaatconfiguratie
Met het [configuratiebeleid](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md) van Intune kunt u apparaten beveiligen en configureren door een groot aantal instellingen en functies te beheren. Bijvoorbeeld:
- U kunt het gebruik van hardwarefuncties op het apparaat beperken, zoals de camera of Bluetooth.
- U kunt compatibele en niet-compatibele apps configureren. U wordt gewaarschuwd als een niet-compatibele app wordt geïnstalleerd (sommige platformen kunnen de installatie daadwerkelijk blokkeren).

### <a name="reset-passcodes-when-users-are-locked-out-of-their-devices"></a>Wachtwoordcodes opnieuw instellen wanneer de apparaten van gebruikers zijn vergrendeld
De eerste stap in het beveiligen van bedrijfsgegevens op mobiele apparaten is het vereisen van een wachtwoordcode om het apparaat te kunnen gebruiken. U zult daarom soms een [wachtwoordcode opnieuw moeten instellen](use-remote-lock-and-passcode-reset-in-microsoft-intune.md) of een medewerker moeten helpen om dit te doen door een wachtwoordcode te verwijderen of door op afstand een tijdelijke wachtwoordcode in te stellen. U kunt ook [een apparaat vergrendelen op afstand](use-remote-lock-and-passcode-reset-in-microsoft-intune.md) als dit is zoekgeraakt of gestolen.

### <a name="retire-devices-and-remove-data"></a>Apparaten buiten gebruik stellen en gegevens verwijderen
Wanneer een apparaat moet worden [verwijderd uit het beheer van Intune](retire-devices-from-microsoft-intune-management.md) (bijvoorbeeld wanneer een gebruiker vertrekt of het apparaat is kwijtgeraakt of gestolen), wilt u waarschijnlijk de gegevens op het apparaat verwijderen. Intune biedt een aantal methoden voor het beveiligen van uw bedrijfsgegevens.

### <a name="require-devices-to-be-compliant"></a>Vereisen dat apparaten aan het beleid voldoen
Intune heeft een [nalevingsbeleid voor apparaten](introduction-to-device-compliance-policies-in-microsoft-intune.md) waarmee u apparaten kunt evalueren (en in sommige gevallen kunt herstellen) die niet compatibel zijn met regels die u opgeeft. U kunt bijvoorbeeld rapporteren over iOS-apparaten die zijn opengebroken, of apparaten zijn versleuteld of over of Windows 10-apparaten worden gerapporteerd als in orde door de Apparaatstatusverklaring-service.

### <a name="protect-apps-and-the-data-they-use"></a>Apps en de gegevens die ze gebruiken beveiligen
Intune biedt een reeks functies waarmee u apps en de gegevens ervan kunt beveiligen. Met MAM-beleid (Mobile Application Management) kunt u bijvoorbeeld voorkomen dat er een back-up wordt gemaakt van gegevens van een beveiligde app, het kopiëren en plakken naar andere apps beperken, een pincode vereisen voor toegang tot een app en nog veel meer. Zie [Apps en gegevens beveiligen met Microsoft Intune](protect-apps-and-data-with-microsoft-intune.md) voor meer informatie over het beveiligen van apps.

### <a name="add-an-additional-layer-of-protection-to-devices"></a>Een extra beschermingslaag toevoegen aan apparaten
[Multi-Factor Authentication (MFA)](multi-factor-authentication-azure-active-directory.md) is een veiligere manier om de identiteit van gebruikers van apparaten op het netwerk te verifiëren.  Met MFA moeten gebruikers hun identiteit niet alleen met een gebruikersnaam en wachtwoord, maar ook via een telefoongesprek of tekstbericht bevestigen.

## <a name="further-capabilities-for-windows-devices"></a>Meer mogelijkheden voor Windows-apparaten

### <a name="control-windows-hello-for-business-settings-on-windows-devices"></a>Instellingen van Windows Hello voor Bedrijven beheren op Windows-apparaten
Intune biedt de mogelijk van integratie met [Windows Hello voor Bedrijven](control-microsoft-passport-settings-on-devices-with-microsoft-intune.md) (voorheen Microsoft Passport). Dit is een alternatieve aanmeldingsmethode voor Windows 10 en hoger, waarbij Active Directory of een Azure Active Directory-account wordt gebruikt ter vervanging van een wachtwoord, smartcard of virtuele smartcard.

## <a name="further-capabilities-for-ios-devices"></a>Meer mogelijkheden voor iOS-apparaten

### <a name="bypass-activation-lock-on-ios-devices"></a>Bypass van activeringsvergrendeling op iOS-apparaten
Activeringsvergrendeling is een functie waarmee gebruikers apparaten kunnen beveiligen doordat hun Apple ID en wachtwoord moet worden ingevoerd voordat iemand het apparaat kan wissen of opnieuw kan activeren. Dit kan echter leiden tot problemen, bijvoorbeeld wanneer de gebruiker het bedrijf verlaat zonder de vergrendeling te verwijderen. [Bypass van activeringsvergrendeling voor iOS](help-protect-ios-devices-with-activation-lock-bypass-for-microsoft-intune.md) kan u helpen de vergrendeling te verwijderen van iOS-apparaten die onder supervisie staan, zodat u ze opnieuw kunt toewijzen of kunt wissen.



## <a name="protect-windows-pcs-managed-with-the-intune-client"></a>Windows-pc's beveiligen die door de Intune-client worden beheerd
Intune blijft ondersteuning bieden voor beveiligingsbeleid voor Windows-pc's die u niet registreert, maar met de clientsoftware van Intune beheert. Zie [Use policies to help protect Windows PCs that run the Intune client software](policies-to-protect-windows-pcs-in-microsoft-intune.md) (Beleid gebruiken voor het beveiligen van Windows-pc’s waarop de Intune-clientsoftware wordt uitgevoerd) als u wilt weten hoe u dit beleid kunt gebruiken om uw Windows-pc's te beveiligen.

