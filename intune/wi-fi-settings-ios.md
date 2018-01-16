---
title: Wi-Fi-instellingen voor iOS-apparaten in Intune
titleSuffix: Azure portal
description: Meer informatie over de Intune-instellingen die u kunt gebruiken om Wi-Fi-verbindingen op iOS-apparaten te configureren."
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 12/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 89229a5e-3421-4221-a62f-fa800620cc0d
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 087a8ad8ad8d07bee1d00cd6adaca86ede737eb7
ms.sourcegitcommit: a3a744ea55f38a360ca9f788c77a5b3018d1add5
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/30/2017
---
# <a name="wi-fi-settings-for-ios-devices-in-microsoft-intune"></a>Wi-Fi-instellingen voor iOS-apparaten in Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]



## <a name="wi-fi-settings-for-basic-and-enterprise-profiles"></a>Wi-Fi-instellingen voor basis- en ondernemingsprofielen

- **Netwerknaam**: voer een naam voor deze Wi-Fi-verbinding in. Dit is de naam die gebruikers te zien krijgen in de lijst met beschikbare verbindingen op hun apparaat.
- **SSID**: afkorting voor Service Set Identifier. Dit is de echte naam van het draadloze netwerk waarmee apparaten verbinding maken. Gebruikers zien echter alleen de netwerknaam die u hierboven hebt gemaakt, wanneer ze de verbinding kiezen.
- **Automatisch verbinding maken**: als u deze optie kiest, maakt het apparaat verbinding wanneer het zich in het bereik van dit netwerk bevindt.
- **Verborgen netwerk**: hiermee wordt voorkomen dat dit netwerk wordt weergegeven in de lijst met beschikbare netwerken op het apparaat.
- **Proxyinstellingen**: u kunt kiezen uit:
    - **Geen**: er zijn geen proxyinstellingen geconfigureerd.
    - **Handmatig**: voer het **adres van de proxyserver** (als IP-adres) en het bijbehorende **poortnummer** in.
    - **Automatisch**: gebruik een bestand om de proxyserver te configureren. Voer de **URL van de proxyserver** (bijvoorbeeld **http://proxy.contoso.com**) in die het configuratiebestand bevat.

## <a name="wi-fi-settings-for-basic-profiles-only"></a>Wi-Fi-instellingen voor alleen basisprofielen

- **Beveiligingstype**: selecteer het beveiligingsprotocol dat u wilt gebruiken voor verificatie bij het Wi-Fi-netwerk. U kunt kiezen uit:
    - **Open (geen verificatie)**: gebruik deze optie alleen als het netwerk niet beveiligd is.
    - **WPA/WPA2 - Persoonlijk**
    - **WEP**

## <a name="wi-fi-settings-for-enterprise-profiles-only"></a>Wi-Fi-instellingen voor alleen ondernemingsprofielen

- **EAP-type**: kies het type Extensible Authentication Protocol (EAP) dat wordt gebruikt om beveiligde draadloze verbindingen te verifiëren. U kunt kiezen uit:
    - **EAP-FAST**
    - **EAP-SIM**
    - **EAP-TLS**
    - **EAP-TTLS**
    - **LEAP**
    - **PEAP**

### <a name="further-options-when-you-choose-an-eap-type"></a>Overige opties wanneer u een EAP-type kiest


|Naam van de instelling|Meer informatie|Wanneer gebruiken|
|--------------|-------------|----------|
|**PAC-instellingen (Protected Access Credential)**|Selecteer dit om referenties voor beveiligde toegang te gebruiken om een geverifieerde tunnel tussen de client en de verificatieserver tot stand te brengen. Selecteer een van de volgende opties:<br>- **PAC gebruiken**: gebruik een bestaand PAC-bestand, indien aanwezig.<br>- **PAC gebruiken en inrichten**: richt het PAC-bestand in op uw apparaten.<br>- **PAC anoniem gebruiken en inrichten**: richt het PAC-bestand in op uw apparaten en zorg ervoor dat het PAC-bestand wordt ingericht zonder verificatie van de server.|EAP-type is **EAP-FAST**|

#### <a name="server-trust"></a>Vertrouwelijke server


|Naam van de instelling|Meer informatie|Wanneer gebruiken|
|--------------|-------------|----------|
|**Namen van certificaatservers**|Geef een of meer algemene namen op die worden gebruikt in de certificaten die zijn uitgegeven door uw vertrouwde certificeringsinstantie (CA). Als u deze informatie verstrekt, kunt u het dialoogvenster Dynamisch vertrouwen negeren dat wordt weergegeven op apparaten van eindgebruikers als zij verbinding maken met dit Wi-Fi-netwerk.|EAP-type is **EAP-TLS**, **EAP-TTLS** of **PEAP**.|
|**Basiscertificaat voor servervalidatie**|Kies het profiel voor een vertrouwd basiscertificaat dat wordt gebruikt om de verbinding te verifiëren. |EAP-type is **EAP-TLS**, **EAP-TTLS** of **PEAP**|
|**Identiteitsprivacy (externe identiteit)**|Geef de tekst op die wordt verzonden in antwoord op een EAP-identiteitsaanvraag. Deze tekst kan elke waarde hebben. Tijdens verificatie wordt deze anonieme identiteit in eerste instantie verzonden en wordt deze gevolgd door de echte identificatie in een beveiligde tunnel.|EAP-type is **PEAP**|


#### <a name="client-authentication"></a>Clientverificatie


|Naam van de instelling|Meer informatie|Wanneer gebruiken|
|--------------|-------------|----------|
|**Clientcertificaat voor clientverificatie (identiteitscertificaat)**|Kies het SCEP- of PKCS-certificaatprofiel dat wordt gebruikt om de verbinding te verifiëren.|EAP-type is **EAP-TLS**|
|**Verificatiemethode**|Selecteer de verificatiemethode voor de verbinding:<br>- **Certificaten** om het SCEP- of PKCS-clientcertificaat te selecteren dat het identiteitscertificaat is dat aan de server wordt gepresenteerd.<br><br>- **Gebruikersnaam en wachtwoord** om een andere verificatiemethode op te geven. <br><br>Als u **Gebruikersnaam en wachtwoord** hebt geselecteerd, configureert u het volgende:<br><br>-  **Niet-EAP-methode (interne identiteit)** en selecteer vervolgens hoe u de verbinding verifieert. Kies uit het volgende:<br>- **Geen**<br>- **Niet-versleuteld wachtwoord (PAP)**<br>- **Challenge Handshake Authentication Protocol (CHAP)**<br>- **Microsoft CHAP (MS-CHAP)**<br>- **Microsoft CHAP versie 2 (MS-CHAP v2)**<br>De beschikbare opties zijn afhankelijk van het geselecteerde EAP-type.<br><br>**en**<br><br>- **Identiteitsprivacy (externe identiteit)**: geef de tekst op die wordt verzonden als reactie op een EAP-identiteitsaanvraag. Deze tekst kan elke waarde hebben. Tijdens verificatie wordt deze anonieme identiteit in eerste instantie verzonden en wordt deze gevolgd door de echte identificatie in een beveiligde tunnel.|EAP-type is **EAP-TTLS** of *
