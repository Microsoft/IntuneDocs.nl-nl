---
title: Beleid en apps implementeren | Microsoft Docs
description: U kunt instellingen voor beleid inschakelen en apps implementeren die worden toegepast zodra apparaten zijn geregistreerd voor beheer.
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/14/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e0d8e98f-7dd8-4cbf-887c-a9af63ffe970
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: ab6d9b6b296fb4e1fb0aaa9496fede28976728dc
ms.openlocfilehash: 402475d87dc1c57d34669cc9553939521adcd146
ms.lasthandoff: 04/14/2017


---

# <a name="create-policies-and-publish-apps"></a>Beleid maken en apps publiceren

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

In dit onderwerp wordt aan Intune-beheerders uitgelegd hoe ze beleid kunnen maken en apps publiceren die ze vervolgens op beheerde apparaten kunnen implementeren.

Voordat u apps in Intune registreert, kunt u beleidsinstellingen en apps inschakelen die worden geïmplementeerd zodra deze apparaten in beheer komen. Intune-beleid biedt u instellingen waarmee u de beveiligingsinstellingen op mobiele apparaten kunt controleren, Windows Firewall- en Endpoint Protection-instellingen voor computers kunt onderhouden en toepassingen kunt implementeren. U kunt beleid configureren, apps toevoegen en deze apps implementeren zodat apparaten instellingen en apps ontvangen zodra ze in Intune worden geregistreerd.

Beleid en apps zijn platform-specifiek.

## <a name="manage-device-settings"></a>Apparaatinstellingen beheren

 Beleidsinstellingen voor apparaten worden geconfigureerd en beheerd per platform. De volgende koppelingen bevatten lijsten met beschikbare instellingen voor hun respectieve platforms:

- [iOS](https://docs.microsoft.com/intune/deploy-use/ios-policy-settings-in-microsoft-intune)
- [Android en Samsung KNOX Standard](https://docs.microsoft.com/intune/deploy-use/android-policy-settings-in-microsoft-intune)
- [Android for Work](https://docs.microsoft.com/intune/deploy-use/android-for-work-policy-settings-in-microsoft-intune)
- [Windows 10 (PC en mobiel)](https://docs.microsoft.com/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune)
- [Windows 8.1](https://docs.microsoft.com/intune/deploy-use/windows-configuration-policy-settings-in-microsoft-intune)
- [Windows Phone 8.1](https://docs.microsoft.com/intune/deploy-use/windows-phone-8-1-policy-settings-in-microsoft-intune)
- [Windows Team](https://docs.microsoft.com/intune/deploy-use/windows-team-configuration-policy-settings-in-microsoft-intune)
- [Windows-pc's met Intune-softwareclient](https://docs.microsoft.com/intune/deploy-use/policies-to-protect-windows-pcs-in-microsoft-intune)

Meer informatie over [Instellingen en functies op uw apparaten beheren met Microsoft Intune-beleid](https://docs.microsoft.com/intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies).

## <a name="add-and-deploy-apps"></a>Apps maken en implementeren

U kunt op twee manieren apps toevoegen aan Intune en deze vervolgens implementeren op beheerde apparaten:
- **Vereiste installatie**: apps worden automatisch geïnstalleerd op beheerde apparaten
- **Beschikbare installatie**: apps worden weergegeven in de Intune-bedrijfsportal zodat gebruikers kunnen kiezen of ze deze op hun apparaten installeren

### <a name="add-apps"></a>Apps toevoegen

Eerst moet u er op een van de volgende manieren voor zorgen dat apps beschikbaar zijn in Intune:
- [Apps toevoegen voor ingeschreven apparaten](https://docs.microsoft.com/intune/deploy-use/add-apps-for-mobile-devices-in-microsoft-intune)
- [Apps toevoegen voor Intune-softwareclient-pc's](https://docs.microsoft.com/intune/deploy-use/add-apps-for-windows-pcs-in-microsoft-intune)

### <a name="deploy-apps"></a>Apps implementeren

Nu de app beschikbaar is in Intune, kunt u deze implementeren op beheerde apparaten:
- [Apps implementeren op apparaten](https://docs.microsoft.com/intune/deploy-use/deploy-use/deploy-apps-in-microsoft-intune)
- Apps implementeren die zijn gekocht via het volume-aankoopprogramma:
    - [iOS - volume-aankoopprogramma](https://docs.microsoft.com/intune/deploy-use/manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune)
    - [Windows Store voor Bedrijven](https://docs.microsoft.com/intune/deploy-use/manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune)
    - [Android for Work](https://docs.microsoft.com/Intune/deploy-use/android-for-work-apps)

    Als u apps hebt geconfigureerd voor implementatie kunt u [apps configureren](https://docs.microsoft.com/intune/deploy-use/update-apps-using-microsoft-intune) en [apps bewaken](https://docs.microsoft.com/intune/deploy-use/monitor-apps-in-microsoft-intune).

>[!div class="step-by-step"]

>[&larr; **Gebruikers en apparaten organiseren**](.\start-with-a-paid-subscription-to-microsoft-intune-step-5.md)       [**Bedrijfsportal aanpassen** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-7.md)  

