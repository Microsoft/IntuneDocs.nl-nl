---
title: Wi-Fi-instellingen toevoegen voor Windows 10-apparaten in Microsoft Intune - Azure | Microsoft Docs
description: Voeg een Wi-Fi-configuratieprofiel toe of maak een Wi-Fi-configuratieprofiel met behulp van Wi-Fi-instellingen voor apparaten met Windows 10 en hoger in Microsoft Intune. U kunt eenvoudige basisinstellingen of instellingen op ondernemingsniveau configureren.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/8/2018
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.reviewer: tycast
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 3bbd90b5a317629bd5b4d87b619d89023053518d
ms.sourcegitcommit: 7c251948811b8b817e9fe590b77f23aed95b2d4e
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 07/15/2019
ms.locfileid: "67884245"
---
# <a name="add-wi-fi-settings-for-windows-10-and-later-devices-in-intune"></a>Wi-Fi-instellingen toevoegen voor apparaten met Windows 10 en hoger in Intune

U kunt een profiel maken met specifieke Wi-Fi-instellingen en dit profiel vervolgens implementeren op uw apparaten met Windows 10 of hoger. Microsoft Intune bevat veel functies, waaronder het verifiëren bij uw netwerk, het gebruik van een vooraf gedeelde sleutel en meer.

In dit artikel worden deze instellingen beschreven.

## <a name="before-you-begin"></a>Voordat u begint

[Maak een apparaatprofiel](device-profile-create.md).

## <a name="basic-profile"></a>Basic-profiel

- **Wi-Fi-type**: kies **Basic**. 

- **Wi-Fi-naam (SSID)** : afkorting voor Service Set Identifier. Deze waarde is de echte naam van het draadloze netwerk waarmee apparaten verbinding maken. Gebruikers zien echter alleen de **Verbindingsnaam** die u hebt geconfigureerd wanneer ze de verbinding kiezen.

- **Verbindingsnaam**: voer een gebruikersvriendelijke naam voor deze Wi-Fi-verbinding in. De tekst die u invoert, is de naam die gebruikers op hun apparaat te zien krijgen in de lijst met beschikbare verbindingen.

- **Automatisch verbinding maken binnen bereik**: wanneer **Ja** is geselecteerd, maken apparaten automatisch verbinding als ze binnen het bereik van dit netwerk komen. Wanneer **Nee** is geselecteerd, maken apparaten niet automatisch verbinding.

  - **Verbinding maken met voorkeursnetwerk indien beschikbaar**: als de apparaten zich binnen het bereik van een voorkeursnetwerk bevinden, kiest u **Ja** om het voorkeursnetwerk te gebruiken. Kies **Nee** om het Wi-Fi-netwerk in dit configuratieprofiel te gebruiken.

    U maakt bijvoorbeeld een Wi-Fi-netwerk met de naam **ContosoCorp** en gebruikt **ContosoCorp** binnen dit configuratieprofiel. Ook het Wi-Fi-netwerk **ContosoGuest** ligt binnen bereik. Wanneer de bedrijfsapparaten binnen het bereik vallen, wilt u dat deze automatisch verbinding maken met **ContosoCorp**. In dit scenario stelt u de eigenschap **Verbinding maken met voorkeursnetwerk indien beschikbaar** in op **Nee**.

  - **Verbinding maken met dit netwerk, zelfs wanneer deze niet de SSID uitzendt**: kies **Ja** als u wilt dat het configuratieprofiel automatisch verbinding maakt met uw netwerk, zelfs wanneer het netwerk verborgen is (wat betekent dat de SSID niet openbaar wordt uitgezonden). Kies **Nee** als u niet wilt dat dit configuratieprofiel verbinding maakt met uw verborgen netwerk.

- **Verbinding met een datalimiet**: een beheerder kan kiezen hoe het verkeer van het netwerk wordt gemeten. Toepassingen kunnen vervolgens hun gedrag voor netwerkverkeer aanpassen op basis van deze instelling. Uw opties zijn:

  - **Onbeperkt**: standaard. De verbinding niet wordt gemeten en er zijn geen beperkingen op het verkeer.
  - **Vast**: gebruik deze optie als het netwerk is geconfigureerd met een vaste limiet voor het netwerkverkeer. Nadat deze limiet is bereikt, is toegang tot het netwerk niet meer toegestaan.
  - **Variabel**: gebruik deze optie als het netwerkverkeer per byte in rekening wordt gebracht (kosten per byte).

- **Draadloos beveiligingstype**: voer het beveiligingsprotocol in dat wordt gebruikt om apparaten in uw netwerk te verifiëren. Uw opties zijn:
  - **Open (geen verificatie)** : gebruik deze optie alleen als het netwerk niet beveiligd is.
  - **WPA/WPA2-Personal**: dit is een veiligere optie die doorgaans wordt gebruikt voor Wi-Fi-connectiviteit. Voor betere beveiliging kunt u ook een vooraf gedeelde wachtwoordsleutel of netwerksleutel invoeren. 

    - **Vooraf gedeelde sleutel** (pre-shared key - PSK): optioneel. Dit wordt weergegeven wanneer u de optie **WPA/WPA2-Personal** kiest als beveiligingstype. Wanneer het netwerk van uw organisatie is ingesteld of geconfigureerd, wordt er ook een wachtwoord of netwerksleutel geconfigureerd. Voer dit wachtwoord of deze netwerksleutel in voor de PSK-waarde. Voer een tekenreeks in van minimaal 8 en maximaal 64 tekens. Als het wachtwoord of de netwerksleutel 64 tekens lang is, voert u hexadecimale tekens in.
    
      > [!NOTE]
      > Wanneer u het Wi-Fi-profiel opslaat, worden de door u ingevoerde waarde voor PSK om beveiligingsredenen niet weergegeven. In de vooraf gedeelde watermerk van de sleutel wordt nog steeds **Niet geconfigureerd** weergegeven, zelfs als de PSK in het profiel is opgeslagen. Als u wilt de PSK wijzigen, voert u een nieuwe sleutel in en slaat u het profiel op. Als u een PSK opslaat, het beleid bewerkt en de PSK leeg laat, wordt nog steeds de bestaande PSK gebruikt.

- **Bedrijfsproxyinstellingen**: kies deze optie om de proxyinstellingen binnen uw organisatie te gebruiken. Uw opties zijn:
  - **Geen**: er zijn geen proxyinstellingen geconfigureerd.
  - **Handmatig configureren**: voer het **IP-adres van de proxyserver** en het bijbehorende **poortnummer** in.
  - **Automatisch configureren**: voer de URL in die naar een proxyscript voor automatische configuratie (PAC) verwijst. Voer bijvoorbeeld `http://proxy.contoso.com/proxy.pac` in.

Selecteer **OK** > **Maken** om uw wijzigingen op te slaan. Het profiel wordt gemaakt en wordt weergegeven in de lijst met profielen.

## <a name="enterprise-profile"></a>Enterprise-profiel

- **Wi-Fi-type**: kies **Enterprise**. 

- **Wi-Fi-naam (SSID)** : afkorting voor Service Set Identifier. Deze waarde is de echte naam van het draadloze netwerk waarmee apparaten verbinding maken. Gebruikers zien echter alleen de **Verbindingsnaam** die u hebt geconfigureerd wanneer ze de verbinding kiezen.

- **Verbindingsnaam**: voer een gebruikersvriendelijke naam voor deze Wi-Fi-verbinding in. De tekst die u invoert, is de naam die gebruikers op hun apparaat te zien krijgen in de lijst met beschikbare verbindingen.

- **Automatisch verbinding maken binnen bereik**: wanneer **Ja** is geselecteerd, maken apparaten automatisch verbinding als ze binnen het bereik van dit netwerk komen. Wanneer **Nee** is geselecteerd, maken apparaten niet automatisch verbinding.
  - **Verbinding maken met voorkeursnetwerk indien beschikbaar**: als de apparaten zich binnen het bereik van een voorkeursnetwerk bevinden, kiest u **Ja** om het voorkeursnetwerk te gebruiken. Kies **Nee** om het Wi-Fi-netwerk in dit configuratieprofiel te gebruiken.

    U maakt bijvoorbeeld een Wi-Fi-netwerk met de naam **ContosoCorp** en gebruikt **ContosoCorp** binnen dit configuratieprofiel. Ook het Wi-Fi-netwerk **ContosoGuest** ligt binnen bereik. Wanneer de bedrijfsapparaten binnen het bereik vallen, wilt u dat deze automatisch verbinding maken met **ContosoCorp**. In dit scenario stelt u de eigenschap **Verbinding maken met voorkeursnetwerk indien beschikbaar** in op **Nee**.

  - **Verbinding maken met dit netwerk, zelfs wanneer deze niet de SSID uitzendt**: kies **Ja** als u wilt dat het configuratieprofiel automatisch verbinding maakt met uw netwerk, zelfs wanneer het netwerk verborgen is (wat betekent dat de SSID niet openbaar wordt uitgezonden). Kies **Nee** als u niet wilt dat dit configuratieprofiel verbinding maakt met uw verborgen netwerk.

- **Verbinding met een datalimiet**: een beheerder kan kiezen hoe het verkeer van het netwerk wordt gemeten. Toepassingen kunnen vervolgens hun gedrag voor netwerkverkeer aanpassen op basis van deze instelling. Uw opties zijn:

  - **Onbeperkt**: standaard. De verbinding niet wordt gemeten en er zijn geen beperkingen op het verkeer.
  - **Vast**: gebruik deze optie als het netwerk is geconfigureerd met een vaste limiet voor het netwerkverkeer. Nadat deze limiet is bereikt, is toegang tot het netwerk niet meer toegestaan.
  - **Variabel**: gebruik deze optie als het netwerkverkeer per byte in rekening wordt gebracht.

- **Eenmalige aanmelding (SSO)** : hiermee kunt u eenmalige aanmelding (SSO) configureren, waarbij referenties worden gedeeld voor aanmelden via een computer en via een Wi-Fi-netwerk. Uw opties zijn:
  - **Uitschakelen**: hiermee schakelt u SSO-gedrag uit. De gebruiker moet afzonderlijk bij het netwerk worden geverifieerd.
  - **Inschakelen voordat de gebruiker zich aanmeldt bij apparaat**: gebruik eenmalige aanmelding om te verifiëren bij het netwerk net vóór het aanmeldingsproces voor de gebruiker.
  - **Inschakelen nadat de gebruiker zich aanmeldt bij apparaat**: gebruik eenmalige aanmelding om te verifiëren bij het netwerk direct nadat het aanmeldingsproces voor de gebruiker is voltooid.
  - **Maximale tijd om te verifiëren voordat de time-out optreedt**: geef het maximum aantal seconden op dat moet worden gewacht voordat de verificatie bij het netwerk wordt uitgevoerd, tussen 1 en 120 seconden.
  - **Toestaan dat Windows de gebruiker om aanvullende verificatiereferenties vraagt**: als u **Ja** kiest, staat u toe dat het Windows-systeem de gebruiker om aanvullende verificatiereferenties vraagt als dit conform de verificatiemethode is vereist. Kies **Nee** om deze vragen te verbergen.

- **Caching van Pairwise Master Key (PMK) inschakelen**: selecteer **Ja** om de PMK die in de verificatie is gebruikt in de cache te plaatsen. Doorgaans zorgt plaatsing in de cache ervoor dat verificatie bij het netwerk sneller kan worden voltooid. Kies **Nee** om de verificatiehandshake af te dwingen wanneer u verbinding met het Wi-Fi-netwerk maakt.

  - **Maximale tijd dat een PMK in de cache wordt opgeslagen**: voer het aantal minuten in dat een Pairwise Master Key (PMK) wordt opgeslagen in de cache, tussen 5 en 1440 minuten.
  - **Maximum aantal PMK’s dat in cache is opgeslagen**: voer het aantal sleutels in dat is opgeslagen in de cache, tussen 1 en 255.

- **Verificatie vooraf inschakelen**: door verificatie vooraf kan het profiel verifiëren bij alle toegangspunten voor het netwerk in het profiel voordat u verbinding maakt. Bij het verplaatsen tussen toegangspunten kunnen gebruikers of apparaten door verificatie vooraf sneller opnieuw verbinding maken. Kies **Ja** als u wilt dat het profiel verifieert bij alle toegangspunten voor dit netwerk die binnen het bereik vallen. Kies **Nee** als u wilt vereisen dat gebruikers of apparaten bij elk toegangspunt afzonderlijk verifiëren.

  - **Maximum aantal pogingen voor verificatie vooraf**: voer in hoe vaak verificatie vooraf mag worden geprobeerd, tussen 1 en 16.

- **EAP-type**: kies het type Extensible Authentication Protocol (EAP) dat wordt gebruikt om beveiligde draadloze verbindingen te verifiëren. Uw opties zijn:

  - **EAP-SIM**
  - **EAP-TLS**
  - **EAP-TTLS**
  - **Beveiligde PEAP** (PEAP)

    **Extra instellingen EAP-TLS, EAP-TTLS en PEAP**:
    
    > [!NOTE]
    > Momenteel worden alleen SCEP-certificaatprofielen ondersteund bij het gebruik van een EAP-type. PKCS-certificaatprofielen worden niet ondersteund. Steeds wanneer een gebruiker wordt gevraagd een certificaat in te voeren, moet u een SCEP-certificaat kiezen.

    - **Server Trust**  

      **Namen van certificaatserver**: gebruiken met EAP-typen **EAP-TLS**, **EAP-TTLS** of **PEAP**. Voer een of meer algemene namen in die worden gebruikt in de certificaten die zijn uitgegeven door uw vertrouwde certificeringsinstantie (CA). Als u deze informatie verstrekt, kunt u het dialoogvenster Dynamisch vertrouwen negeren dat wordt weergegeven op apparaten van gebruikers als zij verbinding maken met dit Wi-Fi-netwerk.  

      **Basiscertificaat voor servervalidatie**: gebruiken met EAP-typen **EAP-TLS**, **EAP-TTLS** of **PEAP**. Kies het profiel voor een vertrouwd basiscertificaat dat wordt gebruikt om de verbinding te verifiëren.  

      **Identiteitsprivacy (externe identiteit)** : gebruiken met EAP-type **PEAP**. Voer de tekst in die wordt verzonden in antwoord op een EAP-identiteitsaanvraag. Deze tekst kan elke waarde hebben. Tijdens verificatie wordt deze anonieme identiteit in eerste instantie verzonden en wordt deze gevolgd door de echte identificatie in een beveiligde tunnel.  

    - **Clientauthenticatie**

      **Clientcertificaat voor clientverificatie (identiteitscertificaat)** : gebruiken met EAP-type **PEAP-TLS**. Kies het certificaatprofiel dat wordt gebruikt om de verbinding te verifiëren.

      **Verificatiemethode**: gebruiken met EAP-type **EAP-TTLS**. Selecteer de verificatiemethode voor de verbinding:  

      - **Certificaten**: selecteer het clientcertificaat dat het identiteitscertificaat is dat aan de server wordt gepresenteerd.
      - **Gebruikersnaam en wachtwoord**: voer een **niet-EAP-methode (interne identiteit)** in voor verificatie. Uw opties zijn:

        - **Niet-versleuteld wachtwoord (PAP)**
        - **Challenge Handshake (CHAP)**
        - **Microsoft CHAP (MS-CHAP)**
        - **Microsoft CHAP versie 2 (MS-CHAP v2)**

      **Identiteitsprivacy (externe identiteit)** : gebruiken met EAP-type **EAP-TTLS**. Voer de tekst in die wordt verzonden in antwoord op een EAP-identiteitsaanvraag. Deze tekst kan elke waarde hebben. Tijdens verificatie wordt deze anonieme identiteit in eerste instantie verzonden en wordt deze gevolgd door de echte identificatie in een beveiligde tunnel.

- **Bedrijfsproxyinstellingen**: kies deze optie om de proxyinstellingen binnen uw organisatie te gebruiken. Uw opties zijn:
  - **Geen**: er zijn geen proxyinstellingen geconfigureerd.
  - **Handmatig configureren**: voer het **IP-adres van de proxyserver** en het bijbehorende **poortnummer** in.
  - **Automatisch configureren**: voer de URL in die naar een proxyscript voor automatische configuratie (PAC) verwijst. Voer bijvoorbeeld `http://proxy.contoso.com/proxy.pac` in.

- **Naleving van Wi-Fi-profiel afdwingen met de Federal Information Processing Standard (FIPS)** : kies **Ja** wanneer u wilt valideren op basis van de FIPS 140-2-standaard. Deze standaard is vereist voor alle instanties van de Amerikaanse federale overheid die beveiligingssystemen op basis van cryptografie gebruiken om gevoelige, niet-geclassificeerde informatie te beveiligen die digitaal is opgeslagen. Kies **Nee** om niet FIPS-compatibel te zijn.

Selecteer **OK** > **Maken** om uw wijzigingen op te slaan. Het profiel wordt gemaakt en wordt weergegeven in de lijst met profielen.

## <a name="use-an-imported-settings-file"></a>Een bestand met geïmporteerde instellingen gebruiken

Voor alle instellingen die niet beschikbaar zijn in Intune, kunt u Wi-Fi-instellingen exporteren vanaf een ander Windows-apparaat. Bij deze export wordt een XML-bestand met daarin alle instellingen gemaakt. Importeer vervolgens dit bestand in Intune en gebruik dit als het Wi-Fi-profiel. Zie [Wi-Fi-instellingen voor Windows-apparaten exporteren en importeren](wi-fi-settings-import-windows-8-1.md).

## <a name="next-steps"></a>Volgende stappen

Het profiel is gemaakt, maar er gebeurt niets. Vervolgens [wijst u dit profiel toe](device-profile-assign.md).

## <a name="more-resources"></a>Meer bronnen

- Zie de instellingen die beschikbaar zijn voor [Windows 8.1](wi-fi-settings-import-windows-8-1.md).
- [Overzicht Wi-Fi-instellingen](wi-fi-settings-configure.md), met inbegrip van andere platformen
