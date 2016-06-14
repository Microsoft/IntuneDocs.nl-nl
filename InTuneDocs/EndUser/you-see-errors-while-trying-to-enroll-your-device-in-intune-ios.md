---
# required metadata

title: Er worden fouten weergegeven tijdens het inschrijven van het iOS-apparaat in Intune | Microsoft Intune
description:
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 92a8d06d-0ecb-4912-898b-993e8eaf4e58

# optional metadata

ROBOTS: noindex
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Er worden fouten weergegeven tijdens het inschrijven van het iOS-apparaat in Intune

In de volgende tabel staan fouten die u mogelijk tijdens het inschrijven van een iOS-apparaat in Intune ziet. Deel deze koppeling met uw IT-beheerder. 

|Foutbericht|Probleem|Wat u uw IT-beheerder kunt vertellen|
|-----------------|---------|----------------------------------------------------------------------------------------------------------------------------------------------------------------|
|DeviceCapReached|U hebt al te veel mobiele apparaten ingeschreven.|De gebruiker moet een van zijn momenteel ingeschreven mobiele apparaten verwijderen uit de bedrijfsportal voordat hij een ander mobiel apparaat kan inschrijven.|
|APNSCertificateNotValid|Er is een probleem met het certificaat dat door het mobiele apparaat wordt gebruikt voor communicatie met het netwerk van uw bedrijf.<br /><br />Neem contact op met uw IT-beheerders en vertel dat u het bericht **APNSCertificateNotValid** hebt ontvangen toen u probeerde uw mobiele apparaat in te schrijven. Laat ook de oplossing in deze tabel zien.|De Apple Push Notification Service (APNS) biedt een kanaal om ingeschreven iOS-apparaten te bereiken. Als de stappen om een APNS-certificaat te verkrijgen, niet zijn uitgevoerd of als het APNS-certificaat is verlopen, mislukken pogingen tot inschrijving en wordt dit bericht weergegeven.<br /><br />Lees de informatie over het instellen van gebruikers in [Active Directory synchroniseren en gebruikers toevoegen aan Intune](/Intune/Get-Started/start-with-a-paid-subscription-to-microsoft-intune-step-3) en [Gebruikers en apparaten organiseren](/Intune/Get-Started/start-with-a-paid-subscription-to-microsoft-intune-step-5).|
|AccountNotOnboarded|Er is een probleem met het certificaat dat door het mobiele apparaat wordt gebruikt voor communicatie met het netwerk van uw bedrijf.<br /><br />Neem contact op met uw IT-beheerders en vertel dat u het bericht **APNSNotOnboarded** hebt ontvangen toen u probeerde uw mobiele apparaat in te schrijven. Laat ook de oplossing in deze tabel zien.|De Apple Push Notification Service (APNS) biedt een kanaal om ingeschreven iOS-apparaten te bereiken. Als de stappen om een APNS-certificaat te verkrijgen, niet zijn uitgevoerd of als het APNS-certificaat is verlopen, mislukken pogingen tot inschrijving en wordt dit bericht weergegeven.<br /><br />Zie [iOS- en Mac-beheer instellen met Microsoft Intune](/Intune/Deployuse/set-up-ios-and-mac-management-with-microsoft-intune) voor meer informatie.|
|DeviceTypeNotSupported|Mogelijk hebt u geprobeerd een ander apparaat dan een iOS-apparaat in te schrijven. Het type mobiele apparaat dat u probeert in te schrijven, wordt niet ondersteund.<br /><br />Controleer of iOS-versie 7.1 of hoger op uw apparaat wordt uitgevoerd.<br /><br />Neem contact op met uw IT-beheerders en vertel dat u het bericht **DeviceTypeNotSupported** hebt ontvangen toen u probeerde uw mobiele apparaat in te schrijven. Laat ook de oplossing in deze tabel zien.|Controleer of iOS-versie 7.1 of hoger op het apparaat van de gebruiker wordt uitgevoerd.|
|UserLicenseTypeInvalid|U kunt uw mobiele apparaat niet inschrijven, omdat uw gebruikersaccount nog geen lid is van een vereiste gebruikersgroep.<br /><br />Neem contact op met uw IT-beheerders en vertel dat u het bericht **UserLicenseTypeInvalid** hebt ontvangen toen u probeerde uw mobiele apparaat in te schrijven. Laat ook de oplossing in deze tabel zien.|Gebruikers die hun apparaten willen inschrijven, moeten lid zijn van de juiste gebruikersgroep. Dit bericht betekent dat de gebruiker het verkeerde licentietype heeft voor de aangewezen Mobile Device Management-instantie. Als Intune bijvoorbeeld is aangewezen als de instantie om mobiele apparaten te beheren, maar er een licentie voor System Center 2012 R2 Configuration Manager wordt gebruikt, zien gebruikers deze fout.<br /><br />Controleer het volgende voor meer informatie:<br /><br />Zie [iOS- en Mac-beheer instellen met Microsoft Intune](/Intune/Deploy-use/set-up-ios-and-mac-management-with-microsoft-intune) en informatie over het instellen van gebruikers in [Active Directory synchroniseren en gebruikers toevoegen aan Intune] (/Intune/Get-Started/start-with-a-paid-subscription-to-microsoft-intune-step-3 en [Gebruikers en apparaten organiseren](/Intune/Get-Started/start-with-a-paid-subscription-to-microsoft-intune-step-5).|
|MdmAuthorityNotDefined|Uw IT-beheerder moet de manier configureren waarop mobiele apparaten in uw bedrijf worden beheerd.<br /><br />Neem contact op met uw IT-beheerders en vertel dat u het bericht **MdmAuthorityNotDefined** hebt ontvangen toen u probeerde uw mobiele apparaat in te schrijven. Laat ook de oplossing in deze tabel zien.|De Mobile Device Management-instantie is niet aangewezen in Intune.<br /><br />Lees artikel 1 in de sectie 'Stap 6: mobiele apparaten inschrijven en een app installeren' in [Aan de slag met een evaluatieversie van Microsoft Intune van 30 dagen](/Intune/Understand-explore/get-started-with-a-30-day-trial-of-microsoft-intune).|

### Zie tevens
[Uw iOS- of Mac OS X-apparaat gebruiken met Intune](using-your-ios-or-mac-os-x-device-with-intune.md)

<!--HONumber=May16_HO1-->


