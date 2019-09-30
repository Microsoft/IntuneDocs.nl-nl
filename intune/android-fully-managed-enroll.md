---
title: Intune-inschrijving voor volledig beheerde Android Enterprise-apparaten instellen
titleSuffix: Microsoft Intune
description: Meer informatie over het inschrijven van volledig beheerde Android Enterprise-apparaten in Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 1/15/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: priyar
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0035f8d5cd67a995924f7d07a662d8c0671bf063
ms.sourcegitcommit: c19584b36448bbd4c8638d7cab552fe9b3eb3408
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/20/2019
ms.locfileid: "71163785"
---
# <a name="set-up-intune-enrollment-of-android-enterprise-fully-managed-devices"></a>Intune-inschrijving van volledig beheerde Android Enterprise-apparaten instellen 

Volledig beheerde Android Enterprise-apparaten zijn apparaten in bedrijfseigendom voor één gebruiker, die exclusief worden gebruikt voor werk, niet voor persoonlijk gebruik. Beheerders kunnen het hele apparaat beheren en beleidscontroles afdwingen die niet beschikbaar zijn voor werkprofielen, zoals:
- Alleen app-installatie toestaan vanaf beheerde Google Play.
- Verwijdering van beheerde apps blokkeren.
- Voorkomen dat gebruikers fabrieksinstellingen van apparaten terugzetten, enzovoort.

Intune helpt bij het implementeren van apps en het opgeven van instellingen voor Android Enterprise-apparaten, inclusief volledig beheerde Android Enterprise-apparaten. Zie [Android Enterprise-vereisten](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012) voor specifieke informatie over Android Enterprise.

## <a name="technical-requirements"></a>Technische vereisten

U hebt een zelfstandige Intune-tenant nodig om volledig beheerde Android Enterprise-apparaten te beheren. Het beheer van volledig beheerde apparaten is niet beschikbaar in de hybride modus (verbonden met Configuration Manager) of in de verouderde Silverlight-beheerconsole.

Apparaten moeten voldoen aan de volgende vereisten om te worden beheerd als een volledig beheerd Android Enterprise-apparaat:

- Android-besturingssysteemversie 6.0 en hoger.
- Op de apparaten moet een build van Android worden uitgevoerd die connectiviteit met GMS (Google Mobile Services) heeft. Op de apparaten moet GMS beschikbaar zijn en de apparaten moeten in staat zijn om verbinding te maken met GMS.

Er geldt geen beperking voor de apparaatfabrikant/OEM indien aan de bovenstaande vereisten is voldaan.

## <a name="set-up-android-enterprise-fully-managed-device-management"></a>Beheer van volledig beheerd Android Enterprise-apparaat instellen

Volg deze stappen om het beheer van volledig beheerde Android Enterprise-apparaten in te stellen:

1. U moet de MDM-instantie [instellen op **Microsoft Intune**](mdm-authority-set.md) als voorbereiding op het beheer van mobiele apparaten. U stelt de instantie slechts één keer in, wanneer u Intune voor het eerst instelt voor het beheer van mobiele apparaten.
2. [Verbind uw Intune-tenantaccount met uw Android Enterprise-account](connect-intune-android-enterprise.md).
3. [Schakel de apparaten in bedrijfseigendom in](#enable-corporate-owned-user-devices)
4. [Schrijf de volledig beheerde Android-apparaten in](#enroll-the-fully-managed-devices).

### <a name="enable-corporate-owned-user-devices"></a>Apparaten in bedrijfseigendom inschakelen

1. Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) en kies **Apparaatinschrijving** > **Android-inschrijving** > **Bedrijfseigendom, volledig beheerde gebruikersapparaten**.
2. Onder **Allow users to enroll corporate-owned user devices** (Gebruikers toestaan apparaten in bedrijfseigendom in te schrijven) kiest u **Ja**.

> [!NOTE]
> Als u een Azure AD-beleid voor voorwaardelijke toegang hebt gedefinieerd dat gebruikmaakt van de regel *vereisen dat een apparaat moet worden gemarkeerd als compatibel* en dat geldt voor **alle cloud-apps**, **Android** en **browsers**, moet u de cloud-app van **Microsoft Intune** uitsluiten van dit beleid. Dit komt omdat bij Android-installaties gebruik wordt gemaakt van een Chrome-tabblad om de gebruikers bij de inschrijving te verifiëren. Zie [Documentatie voor voorwaardelijke toegang van Azure AD](https://docs.microsoft.com/azure/active-directory/conditional-access/) voor meer informatie.

Wanneer deze instelling is ingesteld op **Ja**, ontvangt u een inschrijvingstoken (een willekeurige tekenreeks) en een QR-code voor uw Intune-tenant. Deze inschrijvingstoken is geldig voor alle gebruikers en verloopt niet. Afhankelijk van het Android-besturingssysteem en de versie van het apparaat kunt u het token of de QR-code gebruiken om het kioskapparaat in te schrijven.

## <a name="enroll-the-fully-managed-devices"></a>De volledig beheerde apparaten inschrijven
U kunt nu [uw volledig beheerde apparaten inschrijven](android-dedicated-devices-fully-managed-enroll.md).

## <a name="next-steps"></a>Volgende stappen
- [Configuratiebeleid voor volledig beheerde Android Enterprise-apparaten toevoegen](device-restrictions-android-for-work.md#device-owner-only)
- [App-configuratiebeleid voor volledig beheerde Android Enterprise-apparaten configureren](app-configuration-policies-use-android.md)

