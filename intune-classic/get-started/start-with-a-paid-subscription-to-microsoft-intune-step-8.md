---
title: Apparaatregistratie inschakelen | Microsoft Docs
description: MDM-instantie instellen en registratie inschakelen voor iOS, Windows-, Android- en Mac-apparaten.
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/14/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5d3215e7-0a5c-44bd-afb0-aeafce98c43f
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 76d6000c87843d1a785cd1027eb927f565784ca2
ms.contentlocale: nl-nl
ms.lasthandoff: 05/23/2017


---

# <a name="enable-enrollment-for-mobile-devices"></a>Registratie inschakelen voor mobiele apparaten

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

In dit onderwerp wordt beschreven hoe een Intune-beheerder de registratie van mobiele apparaten kan inschakelen. Zie [Werk gedaan krijgen met beheerde apparaten](https://docs.microsoft.com/intune-user-help/company-portal-frequently-asked-questions) voor meer informatie over het gebruik van Intune op uw telefoon.

Als u beheer van mobiele apparaten met Intune wilt instellen, moet u eerst de *instantie voor beheer van mobiele apparaten* instellen, waarmee de service wordt geïdentificeerd waarmee u de apparaten beheert die zijn gekoppeld aan uw account. In deze richtlijnen wordt ervan uitgegaan dat u de Intune-service gebruikt in plaats van System Center Configuration Manager. Zodra de MDM-instantie is ingesteld, kunt u beheer voor apparaatplatformen inschakelen en uw apparaten registreren bij de app bedrijfsportal.

## <a name="enable-device-enrollment"></a>Apparaatinschrijving inschakelen

1. **Intune als de instantie voor het beheer van mobiele apparaten instellen**
    Kies in de [Intune-beheerconsole](https://manage.microsoft.com/) **Beheer** > **Beheer van mobiele apparaten** en kies vervolgens **MDM-instantie instellen** onder **Taken**.  

2. Klik in het dialoogvenster MDM-instantie op **Ja**.

    ![Beheerconsole. MDM instellen op Intune](./media/mdmAuthority.png)

## <a name="choose-how-to-enroll-devices"></a>Kiezen hoe u apparaten registreert

Intune kan apparaten op verschillende manieren beheren, al naar gelang de vereisten van uw bedrijf. BYOD-apparaten (Bring your own device), apparaten in bedrijfseigendom, CYOD-apparaten (Choose your own device) en apparaten in kioskmodus zijn een paar beschikbare registratiescenario's.

Volg deze stappen om te [kiezen hoe u apparaten registreert](choose-how-to-enroll-devices1.md).

## <a name="enable-mdm-for-your-device-platform"></a>MDM inschakelen voor uw apparaatplatform
Inschrijving moet worden ingeschakeld voor iOS-, Mac- en Android for Work-apparaten, om een relatie tot stand te brengen tussen de platformprovider en de Intune-tenant. Voor Windows- en Android-apparaten zijn deze extra stappen niet vereist, maar voor Windows-apparaten kunt u apparaatinschrijving voor uw gebruikers vereenvoudigen door een speciale DNS-registervermelding te maken.

Schakel apparateninschrijving in voor het apparaatplatform dat u wilt beheren. Afhankelijk van uw platform zijn er andere vereisten van toepassing:

- [iOS en Mac OS](/intune-classic/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune)
- [Windows 10 en Windows Phone](/intune-classic/deploy-use/set-up-windows-device-management-with-microsoft-intune)
- [Window-pc](/intune-classic/deploy-use/manage-windows-pcs-with-microsoft-intune) (Intune-softwareclient)
- [Android for Work](/intune-classic/deploy-use/set-up-android-for-work)

Zodra inschrijving is ingeschakeld, kunnen gebruikers de bedrijfsportal-app naar het apparaat downloaden en het registratieproces van het apparaat voltooien.

### <a name="enable-company-owned-device-enrollment"></a>Inschrijving van bedrijfsapparaten inschakelen
U kunt ook een aantal verschillende scenario’s voor [inschrijving van bedrijfsapparaten](/intune-classic/deploy-use/manage-corporate-owned-devices) inschakelen, zoals:
- [Apple Device Enrollment Program](/intune-classic/deploy-use/ios-device-enrollment-program-in-microsoft-intune)
- [Inschrijving via Apple Configurator Setup Assistant](/intune-classic/deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune)
- [Directe inschrijving met Apple Configurator](/intune-classic/deploy-use/ios-direct-enrollment-in-microsoft-intune)
- [Apparaatinschrijvingsmanager](/intune-classic/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune)

### <a name="next-steps"></a>Volgende stappen
Gefeliciteerd. U hebt zojuist de laatste stap van de *Snelstartgids voor Intune* voltooid. Nu de eerste configuratie is voltooid, kunt u overwegen om aanvullende MDM-functionaliteit in te schakelen.

>[!div class="step-by-step"]
>[&larr; **Apparaten inschrijven**](.\start-with-a-paid-subscription-to-microsoft-intune-step-8.md)     [**Taken na configuratie** &rarr;](.\post-configuration-tasks.md)  

