---
title: Apparaten met een Android Enterprise-werkprofiel registreren in Intune
titleSuffix: Microsoft Intune
description: Informatie over hoe u apparaten met een Android Enterprise-werkprofiel registreert in Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 6/21/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 66574fe66f90b73d8ebf5835c5b16e93276579e4
ms.sourcegitcommit: 484a898d54f5386fdbce300225aaa3495cecd6b0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/01/2019
ms.locfileid: "59568216"
---
# <a name="set-up-enrollment-of-android-enterprise-work-profile-devices"></a>Inschrijving van apparaten met een Android Enterprise-werkprofiel instellen

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Intune helpt u om apps en instellingen te implementeren op apparaten met een Android Enterprise-werkprofiel om ervoor te zorgen dat werk- en privégegevens gescheiden zijn. Zie [Android Enterprise-vereisten](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012) voor specifieke informatie over Android Enterprise.

Volg deze stappen om Android Enterprise-werkprofielbeheer in te stellen:

1. [Verbind uw Intune-tenantaccount met uw Android Enterprise-account](connect-intune-android-enterprise.md).
2. Geef inschrijvingsinstellingen op voor Android Enterprise-werkprofielen. Android Enterprise-werkprofielen worden [alleen ondersteund op bepaalde Android-apparaten](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012%20style=%22target=new_window%22). Elk apparaat dat ondersteuning biedt voor Android Enterprise-werkprofielen biedt ook ondersteuning voor conventioneel Android-beheer. In Intune kunt u opgeven hoe apparaten met ondersteuning voor Android Enterprise-werkprofielen moeten worden beheerd. Ga hiervoor naar [Inschrijvingsbeperkingen](enrollment-restrictions-set.md).
    - **Blokkeren (standaard ingesteld)**:  Alle Android-apparaten, ook de apparaten met ondersteuning voor Android Enterprise-werkprofielen, worden ingeschreven als conventionele Android-apparaten.
    - **Toestaan**: Alle apparaten met ondersteuning voor Android Enterprise-werkprofielen worden ingeschreven als apparaat met een Android Enterprise-werkprofiel. Alle Android-apparaten die geen ondersteuning bieden voor Android Enterprise-werkprofielen, worden geregistreerd als conventionele Android-apparaten.
3. [Vertel uw gebruikers hoe ze hun apparaten moeten registreren](/intune-user-help/enroll-your-device-in-intune-android).


Als u apparaten met een Android Enterprise-werkprofiel wilt registreren, maar die apparaten al zijn geregistreerd als regulier Android-apparaat, moet die registratie eerst ongedaan worden gemaakt. Daarna kunnen ze weer worden geregistreerd.

Als u apparaten met een Android Enterprise-werkprofiel registreert met een [Device Enrollment Manager](device-enrollment-manager-enroll.md)-account, kunt u per account 10 apparaten registreren.

Zie [Gegevens die Intune naar Google stuurt](data-intune-sends-to-google.md) voor meer informatie.

## <a name="approve-the-company-portal-app-in-the-managed-google-play-store"></a>De bedrijfsportal-app in de beheerde Google Play Store goedkeuren

Om ervoor te zorgen dat gebruikers altijd toegang hebben tot de meest recente versie van de Bedrijfsportal-app, moet u de Bedrijfsportal-app voor Android goedkeuren in de beheerde Google Play Store. Als u deze goedkeurt, ontvangt elke gebruiker automatisch updates. Als u deze niet goedkeurt, wordt de bedrijfsportal uiteindelijk verouderd en worden er geen nieuwe belangrijke oplossingen voor problemen of nieuwe functies ontvangen wanneer deze door Microsoft worden uitgegeven.

Volg deze stappen voor het goedkeuren van de Intune bedrijfsportal:

1.  Ga naar de bedrijfsportal-app in de [beheerde Google Play Store](https://play.google.com/work/apps/details?id=com.microsoft.windowsintune.companyportal).
2.  Meld u aan bij de beheerde Google Play Store met hetzelfde Google-account dat u hebt gebruikt om de binding voor Android Enterprise te configureren.
3.  Klik op **Goedkeuren** om een nieuw dialoogvenster te openen.
4.  Controleer de machtigingen in dit dialoogvenster en klik vervolgens op **Goedkeuren**. U moet deze machtigingen toestaan om de bedrijfsportal-app het werkprofiel op het apparaat te laten beheren.
5.  Selecteer **Goedgekeurd houden wanneer de app nieuwe machtigingen aanvraagt** en klik vervolgens op **Opslaan.**

## <a name="next-steps-for-android-enterprise-work-profiles"></a>Volgende stappen voor Android Enterprise-werkprofielen
- [Apps voor Android Enterprise-werkprofielen implementeren](apps-add-android-for-work.md)
- [Configuratiebeleid voor Android Enterprise-werkprofielen toevoegen](device-profiles.md)
