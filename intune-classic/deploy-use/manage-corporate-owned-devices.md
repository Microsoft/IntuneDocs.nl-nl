---
title: Apparaten in bedrijfseigendom beheren
description: Apparaten in bedrijfseigendom kunnen op verschillende manieren worden ingeschreven, afhankelijk van het type apparaat, hoe dit apparaat is aangeschaft en wat de behoeften van de organisatie zijn.
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 01/29/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2b60bbff-25e6-489b-9621-c71b4275fa06
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: a8386261675798fd09a8f423a8723200392246d9
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/10/2017
---
# <a name="enroll-corporate-owned-devices-by-using-intune"></a>Apparaten in bedrijfseigendom inschrijven met Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Apparaten in organisatie- of bedrijfseigendom kunnen op verschillende manieren worden ingeschreven voor beheer door Intune, afhankelijk van het type apparaat, hoe dit apparaat is aangeschaft en wat de behoeften van de organisatie zijn. Apparaten in bedrijfseigendom kunnen ook worden ingeschreven en beheerd door de bedrijfsportal-app te installeren, zoals in BYOD-scenario's (Bring Your Own Device).

Standaard kunnen apparaten voor alle platforms worden ingeschreven in Intune. Meld u bij de [Microsoft Intune-accountportal](https://manage.microsoft.com) aan met uw beheerdersreferenties als u de inschrijving van apparaten wilt blokkeren. Kies **Beheer** > **Beheer van mobiele apparaten** > **Inschrijvingsregels** en schakel de relevante selectievakjes uit voor de platformen die u wilt blokkeren.

## <a name="enroll-corporate-owned-ios-devices"></a>iOS-apparaten in bedrijfseigendom inschrijven

Inschrijvingsmethoden voor apparaten in bedrijfseigendom zijn geschikt voor CYOD-scenario's (Choose Your Own Device). In een CYOD-omgeving betaalt de organisatie voor de apparaten die gebruikers kiezen, maar blijft het beheer van de apparaten bij de organisatie.

Als gebruikers uit verschillende iOS-apparaten kunnen kiezen, kunt u de inschrijving vooraf configureren zodat het apparaat met Intune wordt beheerd vanaf het moment dat de gebruiker dit voor het eerst inschakelt. Intune ondersteunt inschrijving via het [Device Enrollment Program (DEP) van Apple](ios-device-enrollment-program-in-microsoft-intune.md) of met behulp van het hulpprogramma Apple Configurator, dat wordt uitgevoerd op een Mac-computer voor [directe](ios-direct-enrollment-in-microsoft-intune.md) inschrijving of inschrijving met [Configuratieassistent](ios-setup-assistant-enrollment-in-microsoft-intune.md).

Meer informatie over het [inschrijven van iOS-apparaten in bedrijfseigendom](enroll-corporate-owned-ios-devices-in-microsoft-intune.md).

## <a name="create-a-device-enrollment-manager-account"></a>Een apparaatinschrijvingsmanageraccount maken

U kunt Intune gebruiken voor het beheer van een groot aantal mobiele apparaten voor uw organisatie met één gebruikersaccount (een zogenaamd apparaatinschrijvingsmanageraccount). Nadat een apparaatinschrijvingsmanageraccount is gemaakt, kan dit account door een beheerder worden gebruikt om meer apparaten in te schrijven dan de 15 apparaten die standaard zijn toegestaan voor reguliere gebruikers.

De inschrijving van apparaten via een apparaatinschrijvingsmanager werkt alleen voor apparaten die niet worden gebruikt door een specifieke gebruiker. Dergelijke apparaten zijn bijvoorbeeld geschikt voor gebruik in een verkooppunt of met hulpprogramma-apps, maar niet voor gebruikers die toegang nodig hebben tot e-mail of bedrijfsbronnen.

Lees hoe u [apparaten in bedrijfseigendom kunt inschrijven met behulp van een apparaatinschrijvingsmanageraccount](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md).

## <a name="enroll-corporate-owned-windows-10-enterprise-devices"></a>Windows 10 Enterprise-desktops in bedrijfseigendom inschrijven

Als uw organisatie werkt met Azure Active Directory Premium of Microsoft Enterprise Mobility Suite, kunt u [Windows 10 Enterprise-apparaten inschrijven](https://docs.microsoft.com/active-directory/active-directory-azureadjoin-windows10-devices-overview). Deze worden automatisch gemarkeerd als 'bedrijfseigendom' wanneer gebruikers hun werk- of schoolaccount toevoegen.

## <a name="import-imei-numbers"></a>IMEI-nummers importeren

Veel fabrikanten van mobiele apparaten gebruiken voor hun apparaten een uniek nummer, ook wel een IMEI-nummer (International Mobile Equipment Identity) genoemd. U kunt IMEI-nummers importeren voor apparaten die eigendom zijn van uw organisatie. Wanneer het apparaat wordt beheerd met Intune, wordt het gelabeld als apparaat in bedrijfseigendom.

Lees hoe u [apparaten in bedrijfseigendom kunt labelen met behulp van IMEI-nummers](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md).

## <a name="identify-a-device-as-corporate-owned"></a>Apparaten identificeren als bedrijfseigendom

Intune herkent een apparaat als 'bedrijfseigendom' als aan een van de volgende voorwaarden wordt voldaan:

 - Het apparaat is [ingeschreven met een DEM-account](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md) (alle platforms).
 - Het apparaat is ingeschreven met het apparaatinschrijvingsprogramma van [Apple (DEP)](ios-device-enrollment-program-in-microsoft-intune.md) of met [Apple Configurator](ios-setup-assistant-enrollment-in-microsoft-intune.md) (alleen iOS).
 - De fabrikant van het apparaat [heeft het apparaat vooraf gedecladereerd met behulp van IMEI-nummers](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md) (alle platforms met IMEI-nummers).
 - Het apparaat is ingeschreven in [Azure Active Directory of Enterprise Mobility Suite als een Windows 10 Enterprise-apparaat](https://docs.microsoft.com/active-directory/active-directory-azureadjoin-windows10-devices-overview) (alleen Windows 10).

Wanneer een apparaat is gemarkeerd als bedrijfseigendom, ziet u **Bedrijf** in de kolom **Eigendom** kolom voor dat apparaatrecord in de beheerconsole. 
