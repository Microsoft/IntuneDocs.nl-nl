---
title: Apparaten met een Android-werkprofiel registreren in Intune
titlesuffix: Microsoft Intune
description: Meer informatie over het registreren van apparaten met Android-werkprofielen in Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 6/21/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 095985bad8f7e35a953383fcce8296716723b8bc
ms.sourcegitcommit: 98b444468df3fb2a6e8977ce5eb9d238610d4398
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/07/2018
ms.locfileid: "37909062"
---
# <a name="set-up-enrollment-of-android-work-profile-devices"></a>Inschrijving van apparaten met een Android-werkprofiel instellen

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Intune helpt u om apps en instellingen te implementeren op apparaten met een Android-werkprofiel om ervoor te zorgen dat werk- en privégegevens gescheiden zijn. Zie [Android Enterprise-vereisten](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012) voor specifieke informatie over Android Enterprise.

Volg deze stappen om Android-werkprofielbeheer in te stellen:

1. [Verbind uw Intune-tenantaccount met uw Android Enterprise-account](connect-intune-android-enterprise.md).
2. Geef inschrijvingsinstellingen op voor Android-werkprofielen. Android-werkprofielen worden [alleen ondersteund op bepaalde Android-apparaten](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012%20style=%22target=new_window%22). Elk apparaat dat ondersteuning biedt voor Android-werkprofielen biedt ook ondersteuning voor conventioneel Android-beheer. In Intune kunt u opgeven hoe apparaten met ondersteuning voor Android-werkprofielen moeten worden beheerd. Ga hiervoor naar [Inschrijvingsbeperkingen](enrollment-restrictions-set.md).
    - **Blokkeren (standaard ingesteld)**: alle Android-apparaten, ook de apparaten met ondersteuning voor Android-werkprofielen, worden ingeschreven als conventionele Android-apparaten.
    - **Toestaan**: alle apparaten met ondersteuning voor Android-werkprofielen worden ingeschreven als apparaat met een Android-werkprofiel. Alle Android-apparaten die geen ondersteuning bieden voor Android-werkprofielen, worden geregistreerd als conventionele Android-apparaten.
3. [Vertel uw gebruikers hoe ze hun apparaten moeten registreren](/intune-user-help/enroll-your-device-in-intune-android.md).


Als u apparaten met een Android-werkprofiel wilt registreren, maar die apparaten al zijn geregistreerd als regulier Android-apparaat, moet die registratie eerst ongedaan worden gemaakt. Daarna kunnen ze weer worden geregistreerd.

Als u apparaten met een Android-werkprofiel registreert met een [Device Enrollment Manager](device-enrollment-manager-enroll.md)-account, kunt u per account 10 apparaten registreren.

Zie [Gegevens die Intune naar Google stuurt](data-intune-sends-to-google.md) voor meer informatie.

## <a name="approve-the-company-portal-app-in-the-managed-google-play-store"></a>De bedrijfsportal-app in de beheerde Google Play Store goedkeuren

Om ervoor te zorgen dat gebruikers altijd toegang hebben tot de meest recente versie van de Bedrijfsportal-app, moet u de Bedrijfsportal-app voor Android goedkeuren in de beheerde Google Play Store. Als u deze goedkeurt, ontvangt elke gebruiker automatisch updates. Als u deze niet goedkeurt, wordt de bedrijfsportal uiteindelijk verouderd en worden er geen nieuwe belangrijke oplossingen voor problemen of nieuwe functies ontvangen wanneer deze door Microsoft worden uitgegeven.

Volg deze stappen voor het goedkeuren van de Intune bedrijfsportal:

1.  Ga naar de bedrijfsportal-app in de [beheerde Google Play Store](https://play.google.com/work/apps/details?id=com.microsoft.windowsintune.companyportal).
2.  Meld u aan bij de beheerde Google Play Store met hetzelfde Google-account dat u hebt gebruikt om de binding voor Android Enterprise te configureren.
3.  Klik op **Goedkeuren** om een nieuw dialoogvenster te openen.
4.  Controleer de machtigingen in dit dialoogvenster en klik vervolgens op **Goedkeuren**. U moet deze machtigingen toestaan om de bedrijfsportal-app het werkprofiel op het apparaat te laten beheren.
5.  Selecteer **Goedgekeurd houden wanneer de app nieuwe machtigingen aanvraagt** en klik vervolgens op **Opslaan.**

## <a name="next-steps-for-android-work-profiles"></a>Volgende stappen voor Android-werkprofielen
- [Apps voor Android-werkprofielen implementeren](store-apps-android.md)
- [Configuratiebeleid voor Android-werkprofielen toevoegen](device-profiles.md)