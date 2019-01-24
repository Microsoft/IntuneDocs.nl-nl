---
title: Intune-inschrijving voor volledig beheerde Android-apparaten instellen
titlesuffix: Microsoft Intune
description: Meer informatie over het inschrijven van volledig beheerde Android-apparaten in Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 1/15/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.openlocfilehash: 45c1d1f293454b32b97c8147f08809565714743a
ms.sourcegitcommit: 911923e9fe0eed52b1c93e400f776956835e582f
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/17/2019
ms.locfileid: "54387202"
---
# <a name="set-up-intune-enrollment-of-android-fully-managed-devices-preview"></a>Intune-inschrijving van volledig beheerde Android-apparaten instellen (preview)

Volledig beheerde Android-apparaten zijn apparaten in bedrijfseigendom voor één gebruiker, die exclusief worden gebruikt voor werk, niet voor persoonlijk gebruik. Beheerders kunnen het hele apparaat beheren en beleidscontroles afdwingen die niet beschikbaar zijn voor werkprofielen, zoals:
- alleen app-installatie toestaan vanaf beheerde Google Play
- verwijderen van beheerde apps blokkeren
- voorkomen dat gebruikers fabrieksinstellingen van apparaten terugzetten, enzovoort.

Intune helpt bij het implementeren van apps en het opgeven van instellingen voor Android Enterprise-apparaten, inclusief volledig beheerde Android-apparaten. Zie [Android Enterprise-vereisten](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012) voor specifieke informatie over Android Enterprise.

## <a name="technical-requirements"></a>Technische vereisten

U hebt een zelfstandige Intune-tenant nodig om volledig beheerde Android-apparaten te beheren. Volledig beheerd apparaatbeheer is niet beschikbaar in de hybride modus (verbonden met SSCM) of in de verouderde Silverlight-beheerconsole.

Apparaten moeten voldoen aan de volgende vereisten om te worden beheerd als een volledig beheerd Android-apparaat:

- Android-besturingssysteemversie 6.0 en hoger.
- Op de apparaten moet een build van Android worden uitgevoerd die connectiviteit met GMS (Google Mobile Services) heeft. Op de apparaten moet GMS beschikbaar zijn en de apparaten moeten in staat zijn om verbinding te maken met GMS.

Er geldt geen beperking voor de apparaatfabrikant/OEM indien aan de bovenstaande vereisten is voldaan.

## <a name="set-up-android-fully-managed-device-management"></a>Beheer van volledig beheerd Android-apparaat instellen

Volg deze stappen om het beheer van volledig beheerde Android-apparaten in te stellen:

1. U moet de MDM-instantie [instellen op **Microsoft Intune**](mdm-authority-set.md) als voorbereiding op het beheer van mobiele apparaten. U stelt de instantie slechts één keer in, wanneer u Intune voor het eerst instelt voor het beheer van mobiele apparaten.
2. [Verbind uw Intune-tenantaccount met uw Android Enterprise-account](connect-intune-android-enterprise.md).
3. [Schakel de apparaten in bedrijfseigendom in](#enable-corporate-owned-user-devices)
4. [Schrijf de volledig beheerde Android-apparaten in](#enroll-the-fully-managed-devices).

### <a name="enable-corporate-owned-user-devices"></a>Apparaten in bedrijfseigendom inschakelen

1. Kies in de [Intune-portal](https://portal.azure.com) **Apparaatinschrijving** > **Android-inschrijving** > **Bedrijfseigendom, volledig beheerde gebruikersapparaten (preview)**.
2. Onder **Allow users to enroll corporate-owned user devices** (Gebruikers toestaan apparaten in bedrijfseigendom in te schrijven) kiest u **Ja**.

Wanneer deze instelling is ingesteld op **Ja**, ontvangt u een inschrijvingstoken (een willekeurige tekenreeks) en een QR-code voor uw Intune-tenant. Deze inschrijvingstoken is geldig voor alle gebruikers en verloopt niet. Afhankelijk van het Android-besturingssysteem en de versie van het apparaat kunt u het token of de QR-code gebruiken om het kioskapparaat in te schrijven.

## <a name="enroll-the-fully-managed-devices"></a>De volledig beheerde apparaten inschrijven
U kunt nu [uw volledig beheerde apparaten inschrijven](android-dedicated-devices-fully-managed-enroll.md).

## <a name="considerations-for-this-preview-feature"></a>Overwegingen voor deze preview-functie
Deze openbare preview bevat een kernset aan functies voor de oplossing voor volledig beheerde Android-apparaten. We horen graag wat uw ervaringen zijn met het gebruik van de preview-functies met een van uw huidige communicatiekanalen naar het team (zoals [UserVoice](https://microsoftintune.uservoice.com/forums/291681-ideas?category_id=210853)).

Deze preview-versie ondersteunt de volgende functies voor volledig beheerde Android-apparaten:
- Apparaten inschrijven met behulp van NFC, tokenvermelding, QR-code en Zero Touch
- Apparaatconfiguratie voor gebruikersgroepen
- App-distributie en configuratie voor gebruikersgroepen


Houd rekening met het volgende wanneer u deze preview-functies gebruikt:
- De functies in de preview-versie worden niet aanbevolen voor cruciale implementaties of productie-implementaties. 
- Preview-functies zijn geïmplementeerd naar Microsoft Intune-productiestandaarden. Niet alle Intune-functies zijn echter beschikbaar voor volledig beheerde Android-apparaten. De preview-functies zijn duidelijk gemarkeerd met '(preview)' in de Intune-console. 
- De preview-functies worden volledig ondersteund via de gebruikelijke Intune-ondersteuningskanalen.
- De inschrijving van volledig beheerde Android-apparaten met Samsung Knox Mobile Enrollment wordt niet ondersteund in de preview-versie. 
- Het gebruik van de Intune-bedrijfsportal-app wordt niet ondersteund op volledig beheerde Android-apparaten. 
- Intune-functies als voorwaardelijke toegang, beleidsregels voor de beveiliging van apps en certificaatimplementatie, worden niet ondersteund in de preview-versie. 
- Apparaatgroepen die gericht zijn op een profiel of app worden niet ondersteund in de preview-versie. Alleen apparaatgroepen die gericht zijn op een gebruikersgroep worden ondersteund. 
- Er is geen eersteklas gebruikersinterface voor de configuratie van e-mail, Wi-Fi of VPN. Gebruik app-configuratiebeleid om ondersteunde app-configuratie-instellingen te configureren.

## <a name="next-steps"></a>Volgende stappen
- [Configuratiebeleid voor volledig beheerde Android-apparaten toevoegen](device-restrictions-android-for-work.md#device-owner-only)
- [App-configuratiebeleid voor volledig beheerde Android-apparaten configureren](app-configuration-policies-use-android.md)

