---
title: Ondersteunde mobiele apparaten en browsers | Microsoft Intune
description: Mobiele apparaten en computers die door Intune worden ondersteund
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 11/22/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: aeeccfa4-0f14-447e-a3df-c8435c8a4bb2
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 149f3a3310907d131affeaad4bd372aa60be9206
ms.openlocfilehash: 80541567c535cfeb7fca3eda3c9143f4b11d7abb


---

# <a name="supported-mobile-devices-and-computers"></a>Ondersteunde mobiele apparaten en computers

U kunt de volgende apparaattypen registreren en vervolgens beheren:

[!INCLUDE[mdm-supported-devices](../includes/mdm-supported-devices.md)]

Als u apparaten registreert, kunt u gebruikmaken van [deze functies](/Intune/get-started/choose-how-to-manage-devices).

U kunt Windows-pc’s ook beheren met de Intune-pc-clientsoftware. De Intune-pc-clientsoftware biedt ondersteuning voor Windows 7 en hoger, met uitzondering van Windows 10 Home. Als u pc‘s beheert met de clientsoftware, kunt u gebruikmaken van de [volgende mogelijkheden](https://docs.microsoft.com/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune).

Klanten met Enterprise Management Suite kunnen ook Azure Active Directory (Azure AD) gebruiken voor het registreren van Windows 10-apparaten.

## <a name="microsoft-intune-supported-web-browsers"></a>Door Intune ondersteunde webbrowsers

Voor de verschillende beheertaken moet u een van de volgende beheerwebsites gebruiken.

- [Office 365-portal](http://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Microsoft Intune-beheerdersconsole](https://admin.manage.microsoft.com/)

> [!Note]
> Microsoft Edge en mobiele browsers worden niet ondersteund voor de beheerconsole omdat ze geen ondersteuning bieden voor [Microsoft Silverlight](https://msdn.microsoft.com/en-us/library/cc838158(v=vs.95).aspx). De Intune-console zal op een gegeven moment geen ondersteuning meer bieden voor Silverlight. Uiteindelijk worden alle Intune-functies voor het beheer van mobiele apparaten en toepassingen [beschikbaar gesteld in de nieuwe Microsoft Azure-portal](https://blogs.technet.microsoft.com/enterprisemobility/2015/11/17/enhancing-managed-mobile-productivity/).

|Intune-functie |Ondersteunde browsers|
|---------|---------|
|Intune-beheerconsole     |  Internet Explorer 10 of hoger<br /><br />Google Chrome (versies voorafgaand aan versie 42)<br /><br />Mozilla Firefox met Silverlight ingeschakeld<br /><br />**Opmerking:** Microsoft Edge en mobiele browsers worden niet ondersteund voor de beheerconsole.                      
|Office 365-beheerportal     |Alle browsers, inclusief mobiele browsers en beheerde browsers  |
|Bedrijfsportalwebsite     |**Op mobiele apparaten:** gebruik de standaardwebbrowser voor elk ondersteund platform   <br /><br />**Op Windows-pc's:** Internet Explorer 10 of hoger, of Microsoft Edge<br /><br />**Mac OS X 10.9 of hoger:** Apple Safari    |

> [!Note]
> Microsoft Edge en mobiele browsers worden niet ondersteund voor de beheerconsole omdat ze geen ondersteuning bieden voor [Microsoft Silverlight](https://msdn.microsoft.com/en-us/library/cc838158(v=vs.95).aspx). De Intune-console zal op een gegeven moment geen ondersteuning meer bieden voor Silverlight. Uiteindelijk worden alle Intune-functies voor het beheer van mobiele apparaten en toepassingen [beschikbaar gesteld in de nieuwe Microsoft Azure-portal](https://blogs.technet.microsoft.com/enterprisemobility/2015/11/17/enhancing-managed-mobile-productivity/).

### <a name="office-365-portalhttpgomicrosoftcomfwlinkplinkid698854"></a>[Office 365-portal](http://go.microsoft.com/fwlink/p/?LinkId=698854)

**Als tenantbeheerder gebruikt u deze portal om uw abonnement te beheren**, met inbegrip van de volgende taken wanneer dit wordt toegestaan door uw beheerdersrol:

- Gebruikersaccounts voor het abonnement beheren en directory-synchronisatie configureren vanuit uw lokale Active Directory.
- Groepen gebruikers, genaamd beveiligingsgroepen, beheren.
- Licenties toewijzen aan Intune-gebruikers.
- De domeinnaam configureren die u bij uw abonnement wilt gebruiken. De domeinnaam bepaalt het account waarmee gebruikers zich aanmelden.
- Facturering en aankoopgegevens voor uw abonnement beheren, waaronder het aantal licenties dat u hebt, of de hoeveelheid opslagruimte in de cloud die u kunt gebruiken.
- Koppelingen zoeken om de status van de Intune-service weer te geven.
- Als tenantbeheerder kunt u zich bij de Office 365-portal aanmelden om het abonnement te beheren, zelfs wanneer aan uw account geen licentie is toegewezen voor het gebruik van Intune.
- Elke gebruiker die een licentie voor Intune heeft maar geen beheerder is, kan deze portal gebruiken om zijn/haar accountwachtwoord opnieuw in te stellen en zijn/haar profiel te bewerken.
- Voor toegang tot de Office 365-portal moet uw account de aanmeldingsstatus **Toegestaan** hebben. Deze status is niet hetzelfde als wanneer u een licentie voor het abonnement hebt. Standaard hebben alle gebruikersaccounts de status **Toegestaan**.


### <a name="microsoft-intune-administrator-consolehttpsmanagemicrosoftcom"></a>[Microsoft Intune-beheerdersconsole](https://manage.microsoft.com/)

**Als servicebeheerder gebruikt u deze portal om dagelijkse taken te beheren**, waaronder:

- Beleid voor computers en mobiele apparaten instellen.
- Software, zoals software-updates en apps, uploaden en implementeren.
- Endpoint Protection op computers beheren.
- Apparaatstatus weergeven en rapporten uitvoeren.
- Aanmelden bij deze portal. Als u zich wilt aanmelden bij deze portal, moet u beheerdersmachtigingen hebben voor de service of een tenantbeheerder zijn met de rol Algemene beheerder.


Alleen gebruikers met servicebeheerdersmachtigingen en tenantbeheerders met de rol Algemene beheerder kunnen zich bij deze portal aanmelden. Voor toegang tot de beheerconsole moet uw account een licentie voor het gebruik van Intune en de aanmeldingsstatus **Toegestaan** hebben.



<!--HONumber=Nov16_HO4-->


