---
title: Wi-Fi-instellingen voor macOS-apparaten configureren in Microsoft Intune - Azure | Microsoft Docs
titleSuffix: ''
description: Een configuratieprofiel voor een Wi-Fi-apparaat voor macOS-apparaten toevoegen of maken. Zie de verschillende instellingen, zoals voor het toevoegen van certificaten, voor het kiezen van een EAP-type en het selecteren van een verificatiemethode in Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 09/09/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: a479bfa7b6a572ab2191fb651ce04145d8508c4b
ms.sourcegitcommit: e166b9746fcf0e710e93ad012d2f52e2d3ed2644
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 12/19/2019
ms.locfileid: "75206989"
---
# <a name="add-wi-fi-settings-for-macos-devices-in-microsoft-intune"></a>Wi-Fi-instellingen voor macOS-apparaten in Microsoft Intune toevoegen



U kunt een profiel maken met specifieke Wi-Fi-instellingen en dit profiel vervolgens implementeren op uw macOS-apparaten. Microsoft Intune biedt veel functies, waaronder het verifiëren bij het netwerk, het toevoegen van een PKS- of SCEP-certificaat en meer.

Deze Wi-Fi-instellingen worden in twee categorieën onderverdeeld: Basisinstellingen en instellingen op zakelijk niveau.

In dit artikel worden deze instellingen beschreven.

## <a name="before-you-begin"></a>Voordat u begint

[Maak een apparaatprofiel](device-profile-create.md).

> [!NOTE]
> Deze instellingen zijn beschikbaar voor alle inschrijvings typen. Zie voor meer informatie over de inschrijvings typen [macOS-inschrijving](../enrollment/macos-enroll.md).

## <a name="basic-profiles"></a>Basic-profielen

- **Wi-Fi-type**: Selecteer **Basic**.
- **Netwerknaam**: Voer een naam in voor deze Wi-Fi-verbinding. Deze waarde krijgen gebruikers te zien in de lijst met beschikbare verbindingen op hun apparaat.
- **SSID**: Afkorting voor **serviceset-id**. Deze eigenschap is de echte naam van het draadloze netwerk waarmee apparaten verbinding maken. Gebruikers zien echter alleen de netwerknaam die u hebt geconfigureerd wanneer ze de verbinding kiezen.
- **Automatisch verbinding maken**: Kies **Inschakelen** om automatisch verbinding te maken met dit netwerk wanneer het apparaat binnen het bereik daarvan is. Kies **Uitschakelen** om te voorkomen dat apparaten automatisch verbinding maken.
- **Verborgen netwerk**: Kies **Inschakelen** om te voorkomen dat dit netwerk op het apparaat wordt weergegeven in de lijst met beschikbare netwerken. De SSID wordt niet verzonden. Kies **Uitschakelen** om dit netwerk in de lijst met beschikbare netwerken op het apparaat weer te geven.
- **Beveiligingstype**: Selecteer het beveiligingsprotocol voor de verificatie bij het Wi-Fi-netwerk. Uw opties zijn:

  - **Open (geen verificatie)** : Gebruik deze optie alleen als het netwerk niet beveiligd is.
  - **WPA/WPA2 - persoonlijk**: voer het wachtwoord in in de **vooraf gedeelde sleutel**. Wanneer het netwerk van uw organisatie is ingesteld of geconfigureerd, wordt er ook een wachtwoord of netwerksleutel geconfigureerd. Voer dit wachtwoord of deze netwerksleutel in voor de PSK-waarde.
  - **WEP**

- **Proxyinstellingen**: Uw opties zijn:
  - **Geen**: Er zijn geen proxyinstellingen geconfigureerd.
  - **Handmatig**: Voer het **adres van de proxyserver** als IP-adres in, samen met het bijbehorende **poortnummer**.
  - **Automatisch**: Gebruik een bestand om de proxyserver te configureren. Voer de **URL van de proxyserver** (bijvoorbeeld `http://proxy.contoso.com`) in die het configuratiebestand bevat.

## <a name="enterprise-profiles"></a>Enterprise-profielen

- **Wi-Fi-type**: Kies **Enterprise**.
- **SSID**: Afkorting voor **serviceset-id**. Deze eigenschap is de echte naam van het draadloze netwerk waarmee apparaten verbinding maken. Gebruikers zien echter alleen de netwerknaam die u hebt geconfigureerd wanneer ze de verbinding kiezen.
- **Automatisch verbinding maken**: Kies **Inschakelen** om automatisch verbinding te maken met dit netwerk wanneer het apparaat binnen het bereik daarvan is. Kies **Uitschakelen** om te voorkomen dat apparaten automatisch verbinding maken.
- **Verborgen netwerk**: Kies **Inschakelen** om te voorkomen dat dit netwerk op het apparaat wordt weergegeven in de lijst met beschikbare netwerken. De SSID wordt niet verzonden. Kies **Uitschakelen** om dit netwerk in de lijst met beschikbare netwerken op het apparaat weer te geven.

- **EAP-type**: Kies het type Extensible Authentication Protocol (EAP) dat wordt gebruikt voor het verifiëren van beveiligde draadloze verbindingen. Uw opties zijn:

  - **EAP-FAST**: Voer de **PAC-instellingen (Protected Access Credential)** in. Deze optie gebruikt beveiligde toegangsreferenties om een geverifieerde tunnel tussen de client en de verificatieserver te maken. Uw opties zijn:
    - **(PAC) niet gebruiken**
    - **(PAC) gebruiken**: Als er een al PAC-bestand bestaat, gebruik dit dan.
    - **PAC gebruiken en inrichten**: Maak het PAC-bestand en voeg dit toe aan uw apparaten.
    - **PAC anoniem inrichten en gebruiken**: maak het PAC-bestand en voeg het toe aan uw apparaten zonder verificatie met de server.

  - **EAP-SIM**

  - **EAP-TLS**: Voer ook in:

    - **Vertrouwelijke server** - **Namen van certificaatservers**: **voeg** een of meer algemene namen toe die worden gebruikt in de certificaten die zijn uitgegeven door uw vertrouwde certificeringsinstantie (CA). Wanneer u deze informatie invoert, kunt u het venster Dynamisch vertrouwen negeren dat wordt weergegeven op apparaten van gebruikers wanneer zij verbinding maken met dit Wi-Fi-netwerk.
    - **Basiscertificaat voor servervalidatie**: Kies een bestaand profiel voor een vertrouwd basiscertificaat. Dit certificaat wordt aangeboden aan de server wanneer de client verbinding met het netwerk maakt, en wordt gebruikt om de verbinding te verifiëren.

    - **Clientverificatie** - **Clientcertificaat voor clientverificatie (identiteitscertificaat)** : Kies het profiel van het SCEP- of PKCS-clientcertificaat dat ook op het apparaat is geïmplementeerd. Dit certificaat is de identiteit die door het apparaat wordt gepresenteerd aan de server om de verbinding te verifiëren.

  - **EAP-TTLS**: Voer ook in:

    - **Vertrouwelijke server** - **Namen van certificaatservers**: **voeg** een of meer algemene namen toe die worden gebruikt in de certificaten die zijn uitgegeven door uw vertrouwde certificeringsinstantie (CA). Wanneer u deze informatie invoert, kunt u het venster Dynamisch vertrouwen negeren dat wordt weergegeven op apparaten van gebruikers wanneer zij verbinding maken met dit Wi-Fi-netwerk.
    - **Basiscertificaat voor servervalidatie**: Kies een bestaand profiel voor een vertrouwd basiscertificaat. Dit certificaat wordt aangeboden aan de server wanneer de client verbinding met het netwerk maakt, en wordt gebruikt om de verbinding te verifiëren.

    - **Clientverificatie**: kies een **verificatiemethode**. Uw opties zijn:

      - **Gebruikersnaam en wachtwoord**: De gebruiker wordt gevraagd om een gebruikersnaam en wachtwoord om de verbinding te verifiëren. Voer ook in:
        - **Niet-EAP-methode (interne identiteit)** : Kies hoe de verbinding moet worden geverifieerd. Zorg ervoor dat u hetzelfde protocol kiest dat op uw Wi-Fi-netwerk is geconfigureerd.

          Uw opties zijn: **Niet-versleuteld wachtwoord (PAP)** , **Challenge Handshake Authentication Protocol (CHAP)** , **Microsoft CHAP (MS-CHAP)** of **Microsoft CHAP versie 2 (MS-CHAP v2)**

      - **Certificaten**: Kies het profiel van het SCEP- of PKCS-clientcertificaat dat ook op het apparaat is geïmplementeerd. Dit certificaat is de identiteit die door het apparaat wordt gepresenteerd aan de server om de verbinding te verifiëren.

      - **Identiteitsprivacy (externe identiteit)** : Voer de tekst in die wordt verzonden in antwoord op een EAP-identiteitsaanvraag. Deze tekst kan elke waarde hebben, zoals `anonymous`. Tijdens verificatie wordt deze anonieme identiteit in eerste instantie verzonden en wordt deze gevolgd door de echte identificatie in een beveiligde tunnel.

  - **LEAP**

  - **PEAP**: Voer ook in:

    - **Vertrouwelijke server** - **Namen van certificaatservers**: **voeg** een of meer algemene namen toe die worden gebruikt in de certificaten die zijn uitgegeven door uw vertrouwde certificeringsinstantie (CA). Wanneer u deze informatie invoert, kunt u het venster Dynamisch vertrouwen negeren dat wordt weergegeven op apparaten van gebruikers wanneer zij verbinding maken met dit Wi-Fi-netwerk.
    - **Basiscertificaat voor servervalidatie**: Kies een bestaand profiel voor een vertrouwd basiscertificaat. Dit certificaat wordt aangeboden aan de server wanneer de client verbinding met het netwerk maakt, en wordt gebruikt om de verbinding te verifiëren.

    - **Clientverificatie**: kies een **verificatiemethode**. Uw opties zijn:

      - **Gebruikersnaam en wachtwoord**: De gebruiker wordt gevraagd om een gebruikersnaam en wachtwoord om de verbinding te verifiëren. 

      - **Certificaten**: Kies het profiel van het SCEP- of PKCS-clientcertificaat dat ook op het apparaat is geïmplementeerd. Dit certificaat is de identiteit die door het apparaat wordt gepresenteerd aan de server om de verbinding te verifiëren.

      - **Identiteitsprivacy (externe identiteit)** : Voer de tekst in die wordt verzonden in antwoord op een EAP-identiteitsaanvraag. Deze tekst kan elke waarde hebben, zoals `anonymous`. Tijdens verificatie wordt deze anonieme identiteit in eerste instantie verzonden en wordt deze gevolgd door de echte identificatie in een beveiligde tunnel.

- **Proxyinstellingen**: Uw opties zijn:
  - **Geen**: Er zijn geen proxyinstellingen geconfigureerd.
  - **Handmatig**: Voer het **adres van de proxyserver** als IP-adres in, samen met het bijbehorende **poortnummer**.
  - **Automatisch**: Gebruik een bestand om de proxyserver te configureren. Voer de **URL van de proxyserver** (bijvoorbeeld `http://proxy.contoso.com`) in die het configuratiebestand bevat.

## <a name="next-steps"></a>Volgende stappen

Het profiel is gemaakt, maar er gebeurt niets. Vervolgens moet u [dit profiel toewijzen](device-profile-assign.md) en [de status ervan controleren](device-profile-monitor.md).

Wi-Fi-instellingen configureren op [Android](wi-fi-settings-android.md)-, [Android Enter prise](wi-fi-settings-android-enterprise.md)-, [IOS](wi-fi-settings-ios.md)-en [Windows 10](wi-fi-settings-windows.md) -apparaten.
