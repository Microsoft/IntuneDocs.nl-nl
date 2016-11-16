---
title: Apparaten in bedrijfseigendom beheren | Microsoft Intune
description: Apparaten in bedrijfseigendom kunnen op verschillende manieren worden ingeschreven, afhankelijk van het type apparaat, hoe dit apparaat is aangeschaft en wat de behoeften van de organisatie zijn.
keywords: 
author: NathBarn
manager: angrobe
ms.date: 07/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2b60bbff-25e6-489b-9621-c71b4275fa06
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 88409332d203dc4ee82fdf98f89a94e5a89a7eed
ms.openlocfilehash: c29cd2c0c4c5671a84f7c0b0ba473e6fb32604d9


---

# <a name="enroll-corporateowned-devices-by-using-intune"></a>Apparaten in bedrijfseigendom inschrijven met Intune

Apparaten in organisatie- of bedrijfseigendom kunnen op verschillende manieren worden ingeschreven voor beheer door Intune, afhankelijk van het type apparaat, hoe dit apparaat is aangeschaft en wat de behoeften van de organisatie zijn. Apparaten in bedrijfseigendom kunnen ook worden ingeschreven en beheerd door de bedrijfsportal-app te installeren, zoals in BYOD-scenario's (Bring Your Own Device).

## <a name="enroll-corporateowned-ios-devices"></a>iOS-apparaten in bedrijfseigendom inschrijven

Inschrijvingsmethoden voor apparaten in bedrijfseigendom zijn geschikt voor CYOD-scenario's (Choose Your Own Device). In een CYOD-omgeving betaalt de organisatie voor de apparaten die gebruikers kiezen, maar blijft het beheer van de apparaten bij de organisatie.

Als gebruikers uit verschillende iOS-apparaten kunnen kiezen, kunt u de inschrijving vooraf configureren zodat het apparaat met Intune wordt beheerd vanaf het moment dat de gebruiker dit voor het eerst inschakelt. Intune ondersteunt inschrijving via het [Device Enrollment Program (DEP) van Apple](ios-device-enrollment-program-in-microsoft-intune.md) of met behulp van het hulpprogramma Apple Configurator, dat wordt uitgevoerd op een Mac-computer voor [directe](ios-direct-enrollment-in-microsoft-intune.md) inschrijving of inschrijving met [Configuratieassistent](ios-setup-assistant-enrollment-in-microsoft-intune.md).

Meer informatie over het [inschrijven van iOS-apparaten in bedrijfseigendom](enroll-corporate-owned-ios-devices-in-microsoft-intune.md).

## <a name="create-a-device-enrollment-manager-account"></a>Een apparaatinschrijvingsmanageraccount maken

U kunt Intune gebruiken voor het beheer van een groot aantal mobiele apparaten voor uw organisatie met één gebruikersaccount (een zogenaamd apparaatinschrijvingsmanageraccount). Nadat een apparaatinschrijvingsmanageraccount is gemaakt, kan dit account door een beheerder worden gebruikt om meer apparaten in te schrijven dan de vijf apparaten die standaard zijn toegestaan voor reguliere gebruikers.

De inschrijving van apparaten via een apparaatinschrijvingsmanager werkt alleen voor apparaten die niet worden gebruikt door een specifieke gebruiker. Dergelijke apparaten zijn bijvoorbeeld geschikt voor gebruik in een verkooppunt of met hulpprogramma-apps, maar niet voor gebruikers die toegang nodig hebben tot e-mail of bedrijfsbronnen.

Lees hoe u [apparaten in bedrijfseigendom kunt inschrijven met behulp van een apparaatinschrijvingsmanageraccount](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md).

## <a name="enroll-corporateowned-windows-10-enterprise-devices"></a>Windows 10 Enterprise-desktops in bedrijfseigendom inschrijven

Als uw organisatie werkt met Azure Active Directory Premium of Microsoft Enterprise Mobility Suite, kunt u [Windows 10 Enterprise-apparaten inschrijven](https://docs.microsoft.com/active-directory/active-directory-azureadjoin-windows10-devices-overview). Deze worden automatisch gemarkeerd als 'bedrijfseigendom' wanneer gebruikers hun werk- of schoolaccount toevoegen.

## <a name="import-imei-numbers"></a>IMEI-nummers importeren

Veel fabrikanten van mobiele apparaten gebruiken voor hun apparaten een uniek nummer, ook wel een IMEI-nummer (International Mobile Equipment Identity) genoemd. U kunt IMEI-nummers importeren voor apparaten die eigendom zijn van uw organisatie. Wanneer het apparaat wordt beheerd met Intune, wordt het gelabeld als apparaat in bedrijfseigendom.

Lees hoe u [apparaten in bedrijfseigendom kunt labelen met behulp van IMEI-nummers](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md).

## <a name="identify-a-device-as-corporateowned"></a>Apparaten identificeren als bedrijfseigendom

Apparaten in bedrijfseigendom zijn opgenomen als **Zakelijk** onder **Eigendom** in een lijst met apparaten. Apparaten kunnen op de volgende manieren worden geïdentificeerd als bedrijfseigendom:

 - Het apparaat is [ingeschreven met een apparaatinschrijvingsmanageraccount](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md).
 - Het apparaat is ingeschreven met het apparaatinschrijvingsprogramma van [Apple (DEP)](ios-device-enrollment-program-in-microsoft-intune.md) of met [Apple Configurator](ios-setup-assistant-enrollment-in-microsoft-intune.md).
 - Het [apparaat moet vooraf zijn gedeclareerd met behulp van IMEI-nummers](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md) door de fabrikant.
 - Het apparaat is ingeschreven in [Azure Active Directory of Enterprise Mobility Suite als een Windows 10 Enterprise-apparaat](https://docs.microsoft.com/active-directory/active-directory-azureadjoin-windows10-devices-overview).



<!--HONumber=Nov16_HO1-->


