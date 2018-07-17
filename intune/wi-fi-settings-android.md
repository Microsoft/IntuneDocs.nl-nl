---
title: Wi-Fi-instellingen in Microsoft Intune configureren voor Android-apparaten
titleSuffix: ''
description: Meer informatie over Intune Wi-Fi-configuratie-instellingen op apparaten met Android.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 7/6/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0157815322488525a4ce7a3d6d2c90cbb8d3ff2a
ms.sourcegitcommit: 98b444468df3fb2a6e8977ce5eb9d238610d4398
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/07/2018
ms.locfileid: "37905662"
---
# <a name="configure-wi-fi-settings-in-microsoft-intune-for-devices-running-android-android-work-profiles-and-android-kiosk-devices"></a>Wi-Fi-instellingen configureren in Microsoft Intune voor apparaten met Android, Android-werkprofielen en Android-kioskapparaten

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

In dit artikel komt u meer te weten over de Wi-Fi-instellingen die u in Microsoft Intune kunt configureren voor apparaten met Android en apparaten met een Android-werkprofiel.

## <a name="wi-fi-settings-for-basic-and-enterprise-profiles"></a>Wi-Fi-instellingen voor basis- en ondernemingsprofielen

De volgende Wi-Fi-instellingen zijn beschikbaar voor Android-apparaten en apparaten met een Android-werkprofiel:

- **Netwerknaam**: voer een naam voor deze Wi-Fi-verbinding in. Dit is de naam die gebruikers te zien krijgen in de lijst met beschikbare verbindingen op hun apparaat.
- **SSID**: afkorting voor Service Set Identifier. Dit is de echte naam van het draadloze netwerk waarmee apparaten verbinding maken. Gebruikers zien echter alleen de netwerknaam die u hebt geconfigureerd wanneer ze de verbinding kiezen.
- **Automatisch verbinding maken**: als u deze optie kiest, maakt het apparaat verbinding wanneer het zich in het bereik van dit netwerk bevindt.
- **Verborgen netwerk**: hiermee wordt voorkomen dat dit netwerk wordt weergegeven in de lijst met beschikbare netwerken op het apparaat.

## <a name="wi-fi-settings-available-for-enterprise-kiosk-profiles"></a>Wi-Fi-instellingen die beschikbaar zijn voor Enterprise-kioskprofielen
- **Wi-Fi-type**: deze Wi-Fi-instellingen zijn alleen beschikbaar als u **Profieltype** > **Alleen de eigenaar van het apparaat** > **Wi-Fi** selecteert.
    - **Open (geen verificatie)**
    - **Vooraf gedeelde WEP-sleutel**: u moet het wachtwoord opgeven in het vak **Vooraf gedeelde sleutel**.
    - **Vooraf gedeelde WPA-sleutel**: u moet het wachtwoord opgeven in het vak **Vooraf gedeelde sleutel**

## <a name="wi-fi-settings-for-android-legacy-and-android-work-profiles-only"></a>Wi-Fi-instellingen voor verouderde Android-profielen en Android-werkprofielen

- **EAP-type**: kies het type Extensible Authentication Protocol (EAP) dat wordt gebruikt om beveiligde draadloze verbindingen te verifiëren. U kunt kiezen uit:
    - **EAP-TLS**
    - **EAP-TTLS**
    - **PEAP**

### <a name="further-options-when-you-choose-an-eap-type"></a>Overige opties wanneer u een EAP-type kiest

#### <a name="server-trust"></a>Vertrouwelijke server



|Naam van de instelling|Meer informatie|Wanneer gebruiken|
|-------------|---------------|-----------|
|**Namen van certificaatservers**|Geef een of meer algemene namen op die worden gebruikt in de certificaten die zijn uitgegeven door uw vertrouwde certificeringsinstantie (CA). Als u deze informatie verstrekt, kunt u het dialoogvenster Dynamisch vertrouwen negeren dat wordt weergegeven op apparaten van gebruikers als zij verbinding maken met dit Wi-Fi-netwerk.|EAP-type is **EAP-TLS** of **EAP-TTLS**|
|**Basiscertificaat voor servervalidatie**|Kies het profiel voor een vertrouwd basiscertificaat dat wordt gebruikt om de verbinding te verifiëren. |EAP-type is **EAP-TLS**, **EAP-TTLS** of **PEAP**|
|**Identiteitsprivacy (externe identiteit)**|Geef de tekst op die wordt verzonden in antwoord op een EAP-identiteitsaanvraag. Deze tekst kan elke waarde hebben. Tijdens verificatie wordt deze anonieme identiteit in eerste instantie verzonden en wordt deze gevolgd door de echte identificatie in een beveiligde tunnel.|EAP-type is **PEAP**|


#### <a name="client-authentication"></a>Clientverificatie


|                                     Naam van de instelling                                     |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       Meer informatie                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |                            Wanneer gebruiken                            |
|--------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------|
| <strong>Clientcertificaat voor clientverificatie (identiteitscertificaat)</strong> |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       Kies het SCEP- of PKCS-certificaatprofiel dat wordt gebruikt om de verbinding te verifiëren.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |              EAP-type is <strong>EAP-TLS</strong>              |
|                        <strong>Verificatiemethode</strong>                        | Selecteer de verificatiemethode voor de verbinding:<br>- <strong>Certificaten</strong> om het SCEP- of PKCS-clientcertificaat te selecteren dat het identiteitscertificaat is dat aan de server wordt gepresenteerd.<br><br>- <strong>Gebruikersnaam en wachtwoord</strong> om een andere verificatiemethode op te geven. <br><br>Als u <strong>Gebruikersnaam en wachtwoord</strong> hebt geselecteerd, configureert u het volgende:<br><br>-  <strong>Niet-EAP-methode (interne identiteit)</strong> en selecteer vervolgens hoe u de verbinding verifieert. Kies uit het volgende:<br>- <strong>Geen</strong><br>- <strong>Niet-versleuteld wachtwoord (PAP)</strong><br>- <strong>Challenge Handshake Authentication Protocol (CHAP)</strong><br>- <strong>Microsoft CHAP (MS-CHAP)</strong><br>- <strong>Microsoft CHAP versie 2 (MS-CHAP v2)</strong><br>De beschikbare opties zijn afhankelijk van het geselecteerde EAP-type.<br><br><strong>en</strong><br><br>- <strong>Identiteitsprivacy (externe identiteit)</strong>: geef de tekst op die wordt verzonden als reactie op een EAP-identiteitsaanvraag. Deze tekst kan elke waarde hebben. Tijdens verificatie wordt deze anonieme identiteit in eerste instantie verzonden en wordt deze gevolgd door de echte identificatie in een beveiligde tunnel. | EAP-type is <strong>EAP-TTLS</strong> of <strong>PEAP</strong> |

