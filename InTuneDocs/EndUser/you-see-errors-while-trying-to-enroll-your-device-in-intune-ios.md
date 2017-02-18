---
title: Er worden fouten weergegeven tijdens het registreren van het iOS-apparaat | Microsoft Docs
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 01/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 92a8d06d-0ecb-4912-898b-993e8eaf4e58
searchScope:
- Company Portal
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: esmich
ms.suite: ems
ms.custom: intune-enduser
translationtype: Human Translation
ms.sourcegitcommit: a87fe0cf9591040f1455d71b1f40cd0705ba8abf
ms.openlocfilehash: 06866b9db458851dbb23d5ccf741cad3e1d4c5d0


---

# <a name="you-see-errors-while-trying-to-enroll-your-ios-device-in-intune"></a>Er worden fouten weergegeven tijdens het registreren van het iOS-apparaat in Intune

In de volgende tabel staan fouten die u mogelijk tijdens het registreren van een iOS-apparaat in Intune ziet. Deel deze koppeling met uw IT-beheerder. Ga naar de [bedrijfsportalwebsite](http://portal.manage.microsoft.com) voor de betreffende contactgegevens.

|Foutbericht|Probleem|Wat u uw IT-beheerder kunt vertellen|
|-----------------|---------|----------------------------------------------------------------------------------------------------------------------------------------------------------------|
|NoEnrollmentPolicy|Geen registratiebeleid|Controleer of alle vereisten voor registratie zijn geconfigureerd, zoals het Apple Push Notification Service-certificaat (APNs) en of iOS als platform is ingeschakeld. Zie [iOS- en Mac-apparaatbeheer instellen](/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune) voor instructies.|
|DeviceCapReached|U hebt al te veel mobiele apparaten geregistreerd.|De gebruiker moet een van zijn momenteel geregistreerd mobiele apparaten verwijderen uit de bedrijfsportal voordat hij een ander mobiel apparaat kan registreren. Zie de instructies voor het type apparaat dat u gebruikt: [Android](unenroll-your-device-from-intune-android.md), [iOS](unenroll-your-device-from-intune-ios.md), [Windows](unenroll-your-device-from-intune-windows.md).|
|APNSCertificateNotValid|Er is een probleem met het certificaat dat door het mobiele apparaat wordt gebruikt voor communicatie met het netwerk van uw bedrijf.<br /><br />Neem contact op met uw IT-beheerders en meld dat u het bericht **APNSCertificateNotValid** hebt ontvangen toen u probeerde uw mobiele apparaat te registreren. Laat ook de oplossing in deze tabel zien.|De Apple Push Notification Service (APNs) biedt een kanaal om ingeschreven iOS-apparaten te bereiken. Als de stappen om een APNs-certificaat te verkrijgen, niet zijn uitgevoerd of als het APNs-certificaat is verlopen, mislukken pogingen tot registratie en wordt dit bericht weergegeven.<br /><br />Lees de informatie over het instellen van gebruikers in [Active Directory synchroniseren en gebruikers toevoegen aan Intune](/Intune/Get-Started/start-with-a-paid-subscription-to-microsoft-intune-step-3) en [Gebruikers en apparaten organiseren](/Intune/Get-Started/start-with-a-paid-subscription-to-microsoft-intune-step-5).|
|AccountNotOnboarded|Er is een probleem met het certificaat dat door het mobiele apparaat wordt gebruikt voor communicatie met het netwerk van uw bedrijf.<br /><br />Neem contact op met uw IT-beheerders en meld dat u het bericht **APNSNotOnboarded** hebt ontvangen toen u probeerde uw mobiele apparaat te registreren. Laat ook de oplossing in deze tabel zien.|De Apple Push Notification Service (APNs) biedt een kanaal om ingeschreven iOS-apparaten te bereiken. Als de stappen om een APNs-certificaat te verkrijgen, niet zijn uitgevoerd of als het APNs-certificaat is verlopen, mislukken pogingen tot registratie en wordt dit bericht weergegeven.<br /><br />Zie [iOS- en Mac-beheer instellen met Microsoft Intune](/Intune/Deploy-use/set-up-ios-and-mac-management-with-microsoft-intune) voor meer informatie.|
|DeviceTypeNotSupported|Mogelijk hebt u geprobeerd een niet-iOS-apparaat te registreren. Het type mobiele apparaat dat u probeert te registreren, wordt niet ondersteund.<br /><br />Controleer of iOS-versie 8.0 of hoger op uw apparaat wordt uitgevoerd.<br /><br />Neem contact op met uw IT-beheerders en meld dat u het bericht **DeviceTypeNotSupported** hebt ontvangen toen u probeerde uw mobiele apparaat te registreren. Laat ook de oplossing in deze tabel zien.|Controleer of iOS-versie 8.0 of hoger op het apparaat van de gebruiker wordt uitgevoerd.|
|UserLicenseTypeInvalid|U kunt uw mobiele apparaat niet registreren, omdat uw gebruikersaccount nog geen lid is van een vereiste gebruikersgroep.<br /><br />Neem contact op met uw IT-beheerders en meld dat u het bericht **UserLicenseTypeInvalid** hebt ontvangen toen u probeerde uw mobiele apparaat te registreren. Laat ook de oplossing in deze tabel zien.|Gebruikers die hun apparaten willen registreren, moeten lid zijn van de juiste gebruikersgroep. Dit bericht betekent dat de gebruiker het verkeerde licentietype heeft voor de aangewezen Mobile Device Management-instantie. Als Intune bijvoorbeeld is aangewezen als de instantie om mobiele apparaten te beheren, maar er een licentie voor System Center 2012 R2 Configuration Manager wordt gebruikt, zien gebruikers deze fout.<br /><br />Controleer het volgende voor meer informatie:<br /><br />Zie [iOS- en Mac-beheer instellen met Microsoft Intune](/Intune/Deploy-use/set-up-ios-and-mac-management-with-microsoft-intune) en informatie over het instellen van gebruikers in [Active Directory synchroniseren en gebruikers toevoegen aan Intune](/Intune/Get-Started/start-with-a-paid-subscription-to-microsoft-intune-step-3) en [Gebruikers en apparaten organiseren](/Intune/Get-Started/start-with-a-paid-subscription-to-microsoft-intune-step-5).|
|MdmAuthorityNotDefined|Uw IT-beheerder moet de manier configureren waarop mobiele apparaten in uw bedrijf worden beheerd.<br /><br />Neem contact op met uw IT-beheerders en meld dat u het bericht **MdmAuthorityNotDefined** hebt ontvangen toen u probeerde uw mobiele apparaat te registreren. Laat ook de oplossing in deze tabel zien.|De Mobile Device Management-instantie is niet aangewezen in Intune.<br /><br />Lees artikel 1 in de sectie 'Stap 6: mobiele apparaten registreren en een app installeren' in [Aan de slag met een evaluatieversie van Microsoft Intune van 30 dagen](/Intune/Understand-explore/get-started-with-a-30-day-trial-of-microsoft-intune).|



<!--HONumber=Jan17_HO4-->


