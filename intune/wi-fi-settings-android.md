---
title: Wi-Fi-instellingen configureren voor Android-apparaten in Microsoft Intune - Azure | Microsoft Docs
titleSuffix: ''
description: Maak een configuratieprofiel voor een Wi-Fi-apparaat voor Android of voeg er een toe. Zie de verschillende instellingen, zoals voor het toevoegen van certificaten, voor het kiezen van een EAP-type en het selecteren van een verificatiemethode in Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/18/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: e99b934597806ea8ee4fbc8d37f53e32cf5c9abf
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/07/2019
ms.locfileid: "55842623"
---
# <a name="add-wi-fi-settings-for-devices-running-android-in-microsoft-intune"></a>Wi-Fi-instellingen toevoegen in Microsoft Intune voor Android-apparaten

U kunt een profiel maken met specifieke Wi-Fi-instellingen en dit profiel vervolgens implementeren op uw Android-apparaten. Microsoft Intune biedt veel functies, waaronder het verifiëren bij het netwerk, het toevoegen van een PKS- of SCEP-certificaat en meer.

Deze Wi-Fi-instellingen worden in twee categorieën onderverdeeld: Basisinstellingen en instellingen op zakelijk niveau.

In dit artikel worden deze instellingen beschreven.

## <a name="before-you-begin"></a>Voordat u begint

[Maak een apparaatprofiel](device-profile-create.md).

## <a name="basic-profile"></a>Basic-profiel

- **Wi-Fi-type**: Selecteer **Basic**.
- **SSID**: Afkorting voor **serviceset-id**. Deze instelling is de echte naam van het draadloze netwerk waarmee apparaten verbinding maken.
- **Automatisch verbinding maken**: Kies **Inschakelen** om automatisch verbinding te maken met dit netwerk wanneer het apparaat binnen het bereik daarvan is. Kies **Uitschakelen** om te voorkomen dat apparaten automatisch verbinding maken.
- **Verborgen netwerk**: Kies **Inschakelen** om te voorkomen dat dit netwerk op het apparaat wordt weergegeven in de lijst met beschikbare netwerken. De SSID wordt niet verzonden. Kies **Uitschakelen** om dit netwerk in de lijst met beschikbare netwerken op het apparaat weer te geven.

## <a name="enterprise-profile"></a>Enterprise-profiel

- **Wi-Fi-type**: Kies **Enterprise**.
- **SSID**: Afkorting voor **serviceset-id**. Deze instelling is de echte naam van het draadloze netwerk waarmee apparaten verbinding maken.
- **Automatisch verbinding maken**: Kies **Inschakelen** om automatisch verbinding te maken met dit netwerk wanneer het apparaat binnen het bereik daarvan is. Kies **Uitschakelen** om te voorkomen dat apparaten automatisch verbinding maken.
- **Verborgen netwerk**: Kies **Inschakelen** om te voorkomen dat dit netwerk op het apparaat wordt weergegeven in de lijst met beschikbare netwerken. De SSID wordt niet verzonden. Kies **Uitschakelen** om dit netwerk in de lijst met beschikbare netwerken op het apparaat weer te geven.
- **EAP-type**: Kies het type Extensible Authentication Protocol (EAP) dat wordt gebruikt voor het verifiëren van beveiligde draadloze verbindingen. Uw opties zijn: 

  - **EAP-TLS**: Voer ook in:

    - **Vertrouwelijke server** - **Basiscertificaat voor servervalidatie**: Kies een bestaand profiel voor een vertrouwd basiscertificaat. Dit certificaat wordt aangeboden aan de server wanneer de client verbinding met het netwerk maakt, en wordt gebruikt om de verbinding te verifiëren.

      Selecteer **OK** om uw wijzigingen op te slaan.

    - **Clientverificatie** - **Clientcertificaat voor clientverificatie (identiteitscertificaat)**: Kies het profiel van het SCEP- of PKCS-clientcertificaat dat ook op het apparaat is geïmplementeerd. Dit certificaat is de identiteit die door het apparaat wordt gepresenteerd aan de server om de verbinding te verifiëren.

      Selecteer **OK** om uw wijzigingen op te slaan.

  - **EAP-TTLS**: Voer ook in:

    - **Vertrouwelijke server** - **Basiscertificaat voor servervalidatie**: Kies een bestaand profiel voor een vertrouwd basiscertificaat. Dit certificaat wordt aangeboden aan de server wanneer de client verbinding met het netwerk maakt, en wordt gebruikt om de verbinding te verifiëren.

      Selecteer **OK** om uw wijzigingen op te slaan.

    - **Clientverificatie**: kies een **verificatiemethode**. Uw opties zijn:

      - **Gebruikersnaam en wachtwoord**: De gebruiker wordt gevraagd om een gebruikersnaam en wachtwoord om de verbinding te verifiëren. Voer ook in:
        - **Niet-EAP-methode (interne identiteit)**: Kies hoe de verbinding moet worden geverifieerd. Zorg ervoor dat u hetzelfde protocol kiest dat op uw Wi-Fi-netwerk is geconfigureerd.

          Uw opties zijn: **Niet-versleuteld wachtwoord (PAP)**, **Challenge Handshake Authentication Protocol (CHAP)**, **Microsoft CHAP (MS-CHAP)** of **Microsoft CHAP versie 2 (MS-CHAP v2)**

      - **Certificaten**: Kies het profiel van het SCEP- of PKCS-clientcertificaat dat ook op het apparaat is geïmplementeerd. Dit certificaat is de identiteit die door het apparaat wordt gepresenteerd aan de server om de verbinding te verifiëren.

        Selecteer **OK** om uw wijzigingen op te slaan.

      - **Identiteitsprivacy (externe identiteit)**: Voer de tekst in die wordt verzonden in antwoord op een EAP-identiteitsaanvraag. Deze tekst kan elke waarde hebben, zoals `anonymous`. Tijdens verificatie wordt deze anonieme identiteit in eerste instantie verzonden en wordt deze gevolgd door de echte identificatie in een beveiligde tunnel.

  - **PEAP**: Voer ook in:

    - **Vertrouwelijke server** - **Basiscertificaat voor servervalidatie**: Kies een bestaand profiel voor een vertrouwd basiscertificaat. Dit certificaat wordt aangeboden aan de server wanneer de client verbinding met het netwerk maakt, en wordt gebruikt om de verbinding te verifiëren.

      Selecteer **OK** om uw wijzigingen op te slaan.

    - **Clientverificatie**: kies een **verificatiemethode**. Uw opties zijn:

      - **Gebruikersnaam en wachtwoord**: De gebruiker wordt gevraagd om een gebruikersnaam en wachtwoord om de verbinding te verifiëren. Voer ook in:
        - **Niet-EAP-methode voor verificatie (interne identiteit)**: Kies hoe de verbinding moet worden geverifieerd. Zorg ervoor dat u hetzelfde protocol kiest dat op uw Wi-Fi-netwerk is geconfigureerd.

          Uw opties zijn: **Geen** of **Microsoft CHAP versie 2 (MS-CHAP v2)**

      - **Certificaten**: Kies het profiel van het SCEP- of PKCS-clientcertificaat dat ook op het apparaat is geïmplementeerd. Dit certificaat is de identiteit die door het apparaat wordt gepresenteerd aan de server om de verbinding te verifiëren.

        Selecteer **OK** om uw wijzigingen op te slaan.

      - **Identiteitsprivacy (externe identiteit)**: Voer de tekst in die wordt verzonden in antwoord op een EAP-identiteitsaanvraag. Deze tekst kan elke waarde hebben, zoals `anonymous`. Tijdens verificatie wordt deze anonieme identiteit in eerste instantie verzonden en wordt deze gevolgd door de echte identificatie in een beveiligde tunnel.

Selecteer **OK** > **Maken** om uw wijzigingen op te slaan. Het profiel wordt gemaakt en wordt weergegeven in de lijst met profielen.

## <a name="next-steps"></a>Volgende stappen

Het profiel is gemaakt, maar er gebeurt niets. Vervolgens [wijst u dit profiel toe](device-profile-assign.md).

## <a name="more-resources"></a>Meer bronnen

- [Overzicht Wi-Fi-instellingen](wi-fi-settings-configure.md), met inbegrip van andere platformen.

- Gebruikt u Android Enterprise- of Android-Kiosk-apparaten? Zo ja, raadpleeg dan [Wi-Fi-instellingen voor apparaten met Android Enterprise en Android Kiosk](wi-fi-settings-android-enterprise.md).
