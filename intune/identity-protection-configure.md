---
title: Gebruik een pincode om u aan te melden bij Windows 10-apparaten met Microsoft Intune - Azure | Microsoft Docs
description: Gebruik Windows Hello voor Bedrijven, zodat gebruikers zich bij apparaten kunnen aanmelden met een pincode, vingerafdruk en meer. Maak met deze instellingen in Intune een configuratieprofiel voor identiteitsbeveiliging voor Windows 10-apparaten en wijs het profiel toe aan gebruikersgroepen en apparaatgroepen.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 01/29/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: c917294ac11f8f0a19c0f8f361df8d2910cb461c
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/07/2019
ms.locfileid: "55838000"
---
# <a name="use-windows-hello-for-business-on-windows-10-devices-with-microsoft-intune"></a>Gebruik Windows Hello voor Bedrijven op Windows 10-apparaten met Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Windows Hello voor Bedrijven is een aanmeldmethode voor Windows-apparaten die wachtwoorden, smartcards en virtuele smartcards vervangt. Intune bevat ingebouwde instellingen, zodat beheerders Windows Hello voor Bedrijven kunnen configureren en gebruiken. Zo kunt u deze instellingen gebruiken om:

- Windows Hello voor Bedrijven in te schakelen voor apparaten en gebruikers
- Pinvereisten voor het apparaat in te stellen, waaronder een minimum- of maximumlengte van de pincode
- Gebaren, zoals een vingerafdruk, toe te staan die gebruikers (al dan niet) kunnen gebruiken om zich aan te melden bij apparaten

Deze functie is van toepassing op apparaten met:

- Windows 10 en hoger
- Windows 10 Mobile
- Windows Holographic for Business

Intune maakt gebruik van configuratieprofielen om deze instellingen te maken voor en af te stemmen op de behoeften van uw organisatie. Voeg deze functies aan een profiel toe en push of implementeer deze instellingen vervolgens naar gebruikers- en apparaatgroepen binnen uw organisatie.

In dit artikel wordt beschreven hoe u een apparaatconfiguratieprofiel maakt. Zie [Windows 10 device settings to enable Windows Hello for Business](identity-protection-windows-settings.md) (Instellingen voor Windows 10-apparaten om Windows Hello voor Bedrijven in te schakelen) voor een volledig overzicht van alle instellingen en wat ze doen.

## <a name="create-the-device-profile"></a>Maak het apparaatprofiel

1. Selecteer in de [Azure-portal](https://portal.azure.com) **Alle services** > filter op **Intune** en selecteer **Microsoft Intune**.
2. Selecteer **Apparaatconfiguratie** > **Profielen** > **Profiel maken**.
3. Voer de volgende eigenschappen in:

    - **Naam**: Voer een beschrijvende naam in voor het nieuwe profiel.
    - **Beschrijving**: Voer een beschrijving in voor het profiel. Deze instelling is optioneel, maar wordt aanbevolen.
    - **Platform**: Kies **Windows 10 en hoger**. Windows Hello voor Bedrijven wordt alleen ondersteund op apparaten met Windows 10 en hoger.
    - **Profieltype**: Selecteer **Identiteitsbescherming**.
    - **Windows Hello voor Bedrijven configureren**: Kies hoe u Windows Hello voor Bedrijven wilt configureren. Uw opties zijn:

        - **Niet geconfigureerd**: [Richt Windows Hello voor Bedrijven in](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-how-it-works-provisioning) op het apparaat. Bij het toewijzen van profielen voor identiteitsbescherming voor alleen gebruikers wordt de apparaatcontext standaard ingesteld op **Niet geconfigureerd**.
        - **Uitgeschakeld**: Als u Windows Hello voor Bedrijven niet wilt gebruiken, selecteert u deze optie. Deze optie schakelt Windows Hello voor Bedrijven voor alle gebruikers uit.
        - **Ingeschakeld**: Selecteer deze optie voor het [inrichten]((https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-how-it-works-provisioning)) en configureren van Windows Hello voor Bedrijven-instellingen in Intune. Voer de instellingen in die u wilt configureren. Voor een lijst van alle instellingen en wat ze doen raadpleegt u:

            - [Windows 10 device settings to enable Windows Hello for Business](identity-protection-windows-settings.md) (Instellingen voor Windows 10-apparaten om Windows Hello voor Bedrijven in te schakelen)

4. Wanneer u klaar bent, selecteert u **OK** > **Maken** om uw wijzigingen op te slaan.

Het profiel wordt gemaakt en verschijnt in de profielenlijst. [Wijs](device-profile-assign.md) dit profiel vervolgens naar behoefte toe aan gebruikers- en apparaatgroepen.

<!--  Removing image as part of design review; retaining source until we known the disposition.

## Example of device restriction settings

In this high-level example, you'll create a device restriction policy that blocks the use of the built-in camera app on Android devices.

![How to disable the camera on Android devices](./media/disable-android-camera.png)

-->

## <a name="next-steps"></a>Volgende stappen

- Bekijk een overzicht van alle [instellingen en wat ze doen](identity-protection-windows-settings.md).
- [Het profiel toewijzen](device-profile-assign.md) en [de status ervan controleren](device-profile-monitor.md).
