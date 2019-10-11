---
title: Apparaten met een Android Enterprise-werkprofiel registreren in Intune
titleSuffix: Microsoft Intune
description: Informatie over hoe u apparaten met een Android Enterprise-werkprofiel registreert in Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 5/13/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: chmaguir
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8c447b6b21021573d95a5ece3297e548f216b7a0
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/02/2019
ms.locfileid: "71723525"
---
# <a name="set-up-enrollment-of-android-enterprise-work-profile-devices"></a>Inschrijving van apparaten met een Android Enterprise-werkprofiel instellen

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Intune helpt u om apps en instellingen te implementeren op apparaten met een Android Enterprise-werkprofiel, om ervoor te zorgen dat werk- en privégegevens gescheiden zijn. Zie [Android Enterprise-vereisten](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012) voor specifieke informatie over Android Enterprise.

Volg deze stappen om Android Enterprise-werkprofielbeheer in te stellen:

1. [Verbind uw Intune-tenantaccount met uw Android Enterprise-account](connect-intune-android-enterprise.md).
2. Geef inschrijvingsinstellingen op voor Android Enterprise-werkprofielen. Android Enterprise-werkprofielen worden [alleen ondersteund op bepaalde Android-apparaten](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012%20style=%22target=new_window%22). Elk apparaat dat ondersteuning biedt voor Android Enterprise-werkprofielen, biedt ook ondersteuning voor beheer van Android-apparaatbeheerders. In Intune kunt u opgeven hoe apparaten met ondersteuning voor Android Enterprise-werkprofielen moeten worden beheerd. Ga hiervoor naar [Inschrijvingsbeperkingen](enrollment-restrictions-set.md).
    - **Blokkeren**:  Alle Android-apparaten, inclusief apparaten die ondersteuning bieden voor Android Enterprise-werkprofielen, worden ingeschreven als apparaten met Android-apparaatbeheerder, tenzij inschrijven voor Android-apparaatbeheerders ook is geblokkeerd. 
    - **Toestaan (standaardinstelling)** : Alle apparaten met ondersteuning voor Android Enterprise-werkprofielen worden ingeschreven als apparaat met een Android Enterprise-werkprofiel. Elk Android-apparaat dat geen ondersteuning biedt voor Android Enterprise-werkprofielen, wordt ingeschreven als apparaat met Android-apparaatbeheerder, tenzij inschrijven voor Android-apparaatbeheerder ook is geblokkeerd. 
> [!NOTE]
> Vanaf juli 2019 is de standaardinstelling **Toestaan** voor nieuwe tenants ingesteld op Waar. Eerdere tenants ondervinden geen wijzigingen in hun inschrijvingsbeperkingen, en zien de beleidsregels die zijn ingesteld in de inschrijvingsbeperkingen. Voor eerdere tenants die nooit wijzigingen in hun inschrijvingsbeperkingen hebben ondervonden, is **Blokkeren** nog steeds de standaardinstelling voor Android Enterprise-werkprofielen.

3. [Vertel uw gebruikers hoe ze hun apparaten moeten registreren](/intune-user-help/create-a-work-profile-and-enroll-your-device-in-intune-android).  

Als u apparaten met een Android Enterprise-werkprofiel wilt inschrijven, maar deze apparaten al zijn ingeschreven voor Android-apparaatbeheerders, moet deze inschrijving eerst ongedaan worden gemaakt. Hierna kunnen de apparaten weer worden ingeschreven.
> [!NOTE]
> Als beheerder kunt u dit extern doen met behulp van de functie **Buiten gebruik stellen**. U vindt deze functie in het actiemenu nadat u het apparaat hebt geselecteerd op de Blade **Alle apparaten**.

Als u apparaten met een Android Enterprise-werkprofiel registreert met een [Device Enrollment Manager](device-enrollment-manager-enroll.md)-account, kunt u per account 10 apparaten registreren.

Zie [Gegevens die Intune naar Google stuurt](../protect/data-intune-sends-to-google.md) voor meer informatie.

## <a name="next-steps-for-android-enterprise-work-profiles"></a>Volgende stappen voor Android Enterprise-werkprofielen
- [Apps voor Android Enterprise-werkprofielen implementeren](../apps/apps-add-android-for-work.md)
- [Configuratiebeleid voor Android Enterprise-werkprofielen toevoegen](../configuration/device-profiles.md)

## <a name="see-also"></a>Zie tevens

[Android Enterprise-apparaten in Microsoft Intune configureren en problemen ermee oplossen](https://support.microsoft.com/help/4476974)
