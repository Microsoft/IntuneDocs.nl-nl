---
title: Wi-Fi-instellingen voor iOS-apparaten configureren in Microsoft Intune - Azure | Microsoft Docs
titleSuffix: ''
description: Een configuratieprofiel voor een Wi-Fi-apparaat toevoegen of maken voor iOS-apparaten. Zie de verschillende instellingen, zoals voor het toevoegen van certificaten, voor het kiezen van een EAP-type en het selecteren van een verificatiemethode in Microsoft Intune.
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
ms.custom: intune-azure
ms.openlocfilehash: fa81e8979f48a0b027f4860cfc5d2a88e3b30772
ms.sourcegitcommit: cff65435df070940da390609d6376af6ccdf0140
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/18/2018
ms.locfileid: "49425237"
---
# <a name="add-wi-fi-settings-for-ios-devices-in-microsoft-intune"></a>Wi-Fi-instellingen voor iOS-apparaten in Microsoft Intune toevoegen

U kunt een profiel maken met specifieke Wi-Fi-instellingen en dit profiel vervolgens implementeren op uw iOS-apparaten. Microsoft Intune biedt veel functies, waaronder het verifiëren bij het netwerk, het toevoegen van een PKS- of SCEP-certificaat en meer.

Er zijn twee categorieën Wi-Fi-instellingen: instellingen op Basic- en op Enterprise-niveau.

In dit artikel worden deze instellingen beschreven.

## <a name="before-you-begin"></a>Voordat u begint

[Maak een apparaatprofiel](device-profile-create.md).

## <a name="basic-profiles"></a>Basic-profielen

- **Wi-Fi-type**: kies **Basic**.
- **Netwerknaam**: voer een naam in voor deze Wi-Fi-verbinding. Deze waarde krijgen gebruikers te zien in de lijst met beschikbare verbindingen op hun apparaat.
- **SSID**: afkorting voor **Service Set Identifier**. Deze eigenschap is de echte naam van het draadloze netwerk waarmee apparaten verbinding maken. Gebruikers zien echter alleen de netwerknaam die u hebt geconfigureerd wanneer ze de verbinding kiezen.
- **Automatisch verbinding maken**: kies **Inschakelen** om automatisch verbinding te maken met dit netwerk wanneer het apparaat binnen het bereik daarvan is. Kies **Uitschakelen** om te voorkomen dat apparaten automatisch verbinding maken.
- **Verborgen netwerk**: kies **Inschakelen** om te voorkomen dat dit netwerk op het apparaat wordt weergegeven in de lijst met beschikbare netwerken. De SSID wordt niet verzonden. Kies **Uitschakelen** om dit netwerk in de lijst met beschikbare netwerken op het apparaat weer te geven.
- **Beveiligingstype**: selecteer het beveiligingsprotocol voor de verificatie bij het Wi-Fi-netwerk. Uw opties zijn:

  - **Open (geen verificatie)**: gebruik deze optie alleen als het netwerk niet beveiligd is.
  - **WPA/WPA2 - persoonlijk**:voer het wachtwoord in in de **vooraf gedeelde sleutel**. Wanneer het netwerk van uw organisatie is ingesteld of geconfigureerd, wordt er ook een wachtwoord of netwerksleutel geconfigureerd. Voer dit wachtwoord of deze netwerksleutel in voor de PSK-waarde.
  - **WEP**

- **Proxyinstellingen**: uw opties:
  - **Geen**: er zijn geen proxyinstellingen geconfigureerd.
  - **Handmatig**: voer het **adres van de proxyserver** als IP-adres in, samen met het bijbehorende **poortnummer**.
  - **Automatisch**: gebruik een bestand om de proxyserver te configureren. Voer de **URL van de proxyserver** (bijvoorbeeld `http://proxy.contoso.com`) in die het configuratiebestand bevat.

## <a name="enterprise-profiles"></a>Enterprise-profielen

- **Wi-Fi-type**: kies **Enterprise**.
- **SSID**: afkorting voor **Service Set Identifier**. Deze eigenschap is de echte naam van het draadloze netwerk waarmee apparaten verbinding maken. Gebruikers zien echter alleen de netwerknaam die u hebt geconfigureerd wanneer ze de verbinding kiezen.
- **Automatisch verbinding maken**: kies **Inschakelen** om automatisch verbinding te maken met dit netwerk wanneer het apparaat binnen het bereik daarvan is. Kies **Uitschakelen** om te voorkomen dat apparaten automatisch verbinding maken.
- **Verborgen netwerk**: kies **Inschakelen** om te voorkomen dat dit netwerk op het apparaat wordt weergegeven in de lijst met beschikbare netwerken. De SSID wordt niet verzonden. Kies **Uitschakelen** om dit netwerk in de lijst met beschikbare netwerken op het apparaat weer te geven.

- **EAP-type**: kies het type Extensible Authentication Protocol (EAP) dat wordt gebruikt om beveiligde draadloze verbindingen te verifiëren. Uw opties zijn:

  - **EAP-FAST**: voer de **PAC-instellingen (Protected Access Credential)** in. Deze optie gebruikt beveiligde toegangsreferenties om een geverifieerde tunnel tussen de client en de verificatieserver te maken. Uw opties zijn:
    - **(PAC) niet gebruiken**
    - **(PAC) gebruiken**: als er een bestaand PAC-bestand bestaat, gebruik dit dan.
    - **PAC gebruiken en inrichten**: maak het PAC-bestand en voeg het toe aan uw apparaten.
    - **PAC anoniem inrichten en gebruiken**:maak het PAC-bestand en voeg het toe aan uw apparaten zonder verificatie met de server.

  - **EAP-SIM**

  - **EAP-TLS**: voer ook het volgende in:

    - **Vertrouwelijke server** - **Namen van certificaatservers**:**voeg** een of meer algemene namen toe die worden gebruikt in de certificaten die zijn uitgegeven door uw vertrouwde certificeringsinstantie (CA). Wanneer u deze informatie invoert, kunt u het venster Dynamisch vertrouwen negeren dat wordt weergegeven op apparaten van gebruikers wanneer zij verbinding maken met dit Wi-Fi-netwerk.
    - **Basiscertificaat voor servervalidatie**: kies een profiel voor een bestaand vertrouwd basiscertificaat. Dit certificaat wordt aangeboden aan de server wanneer de client verbinding met het netwerk maakt, en wordt gebruikt om de verbinding te verifiëren.

      Selecteer **OK** om uw wijzigingen op te slaan.

    - **Clientverificatie** - **Clientcertificaat voor clientverificatie (identiteitscertificaat)**: kies het profiel van het SCEP- of PKCS-clientcertificaat dat ook op het apparaat wordt geïmplementeerd. Dit certificaat is de identiteit die door het apparaat wordt gepresenteerd aan de server om de verbinding te verifiëren.

      Selecteer **OK** om uw wijzigingen op te slaan.

  - **EAP-TTLS**: voer ook het volgende in:

    - **Vertrouwelijke server** - **Namen van certificaatservers**:**voeg** een of meer algemene namen toe die worden gebruikt in de certificaten die zijn uitgegeven door uw vertrouwde certificeringsinstantie (CA). Wanneer u deze informatie invoert, kunt u het venster Dynamisch vertrouwen negeren dat wordt weergegeven op apparaten van gebruikers wanneer zij verbinding maken met dit Wi-Fi-netwerk.
    - **Basiscertificaat voor servervalidatie**: kies een profiel voor een bestaand vertrouwd basiscertificaat. Dit certificaat wordt aangeboden aan de server wanneer de client verbinding met het netwerk maakt, en wordt gebruikt om de verbinding te verifiëren.

      Selecteer **OK** om uw wijzigingen op te slaan.

    - **Clientverificatie**: kies een **verificatiemethode**. Uw opties zijn:

      - **Gebruikersnaam en wachtwoord**: de gebruiker wordt gevraagd om een gebruikersnaam en wachtwoord om de verbinding te verifiëren. Voer ook in:
        - **Niet-EAP-methode (interne identiteit)**: kies hoe u de verbinding verifieert. Zorg ervoor dat u hetzelfde protocol kiest dat op uw Wi-Fi-netwerk is geconfigureerd.

          Uw opties: **niet-versleuteld wachtwoord (PAP)**, **Challenge Handshake Authentication Protocol (CHAP)**, **Microsoft CHAP (MS-CHAP)** of **Microsoft CHAP versie 2 (MS-CHAP v2)**

      - **Certificaten**: kies het profiel van het SCEP- of PKCS-clientcertificaat dat ook op het apparaat is geïmplementeerd. Dit certificaat is de identiteit die door het apparaat wordt gepresenteerd aan de server om de verbinding te verifiëren.

        Selecteer **OK** om uw wijzigingen op te slaan.

      - **Identiteitsprivacy (externe identiteit)**: voer de tekst in die wordt verzonden als reactie op een EAP-identiteitsaanvraag. Deze tekst kan elke waarde hebben, zoals `anonymous`. Tijdens verificatie wordt deze anonieme identiteit in eerste instantie verzonden en wordt deze gevolgd door de echte identificatie in een beveiligde tunnel.

  - **LEAP**

  - **PEAP**: voer ook het volgende in:

    - **Vertrouwelijke server** - **Namen van certificaatservers**:**voeg** een of meer algemene namen toe die worden gebruikt in de certificaten die zijn uitgegeven door uw vertrouwde certificeringsinstantie (CA). Wanneer u deze informatie invoert, kunt u het venster Dynamisch vertrouwen negeren dat wordt weergegeven op apparaten van gebruikers wanneer zij verbinding maken met dit Wi-Fi-netwerk.
    - **Basiscertificaat voor servervalidatie**: kies een profiel voor een bestaand vertrouwd basiscertificaat. Dit certificaat wordt aangeboden aan de server wanneer de client verbinding met het netwerk maakt, en wordt gebruikt om de verbinding te verifiëren.

      Selecteer **OK** om uw wijzigingen op te slaan.

    - **Clientverificatie**: kies een **verificatiemethode**. Uw opties zijn:

      - **Gebruikersnaam en wachtwoord**: de gebruiker wordt gevraagd om een gebruikersnaam en wachtwoord om de verbinding te verifiëren. 

      - **Certificaten**: kies het profiel van het SCEP- of PKCS-clientcertificaat dat ook op het apparaat is geïmplementeerd. Dit certificaat is de identiteit die door het apparaat wordt gepresenteerd aan de server om de verbinding te verifiëren.

        Selecteer **OK** om uw wijzigingen op te slaan.

      - **Identiteitsprivacy (externe identiteit)**: voer de tekst in die wordt verzonden als reactie op een EAP-identiteitsaanvraag. Deze tekst kan elke waarde hebben, zoals `anonymous`. Tijdens verificatie wordt deze anonieme identiteit in eerste instantie verzonden en wordt deze gevolgd door de echte identificatie in een beveiligde tunnel.

- **Proxyinstellingen**: uw opties:
  - **Geen**: er zijn geen proxyinstellingen geconfigureerd.
  - **Handmatig**: voer het **adres van de proxyserver** als IP-adres in, samen met het bijbehorende **poortnummer**.
  - **Automatisch**: gebruik een bestand om de proxyserver te configureren. Voer de **URL van de proxyserver** (bijvoorbeeld `http://proxy.contoso.com`) in die het configuratiebestand bevat.

Selecteer **OK** > **Maken** om uw wijzigingen op te slaan. Het profiel wordt gemaakt en wordt weergegeven in de lijst met profielen.

## <a name="next-steps"></a>Volgende stappen

Het profiel is gemaakt, maar er gebeurt niets. Vervolgens [wijst u dit profiel toe](device-profile-assign.md).

## <a name="more-resources"></a>Meer bronnen

[Overzicht Wi-Fi-instellingen](wi-fi-settings-configure.md), met inbegrip van andere platforms.