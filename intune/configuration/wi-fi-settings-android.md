---
title: Wi-Fi-instellingen configureren voor Android-apparaten in Microsoft Intune - Azure | Microsoft Docs
titleSuffix: ''
description: Maak een configuratieprofiel voor een Wi-Fi-apparaat voor Android of voeg er een toe. Zie de verschillende instellingen, zoals voor het toevoegen van certificaten, voor het kiezen van een EAP-type en het selecteren van een verificatiemethode in Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/24/2020
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.reviewer: maholdaa
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 2ea0a60537bb488d3280990747d3e337e73fddc0
ms.sourcegitcommit: 139853f8d6ea61786da7056cfb9024a6459abd70
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 01/26/2020
ms.locfileid: "76754555"
---
# <a name="add-wi-fi-settings-for-devices-running-android-in-microsoft-intune"></a>Wi-Fi-instellingen toevoegen in Microsoft Intune voor Android-apparaten

U kunt een profiel maken met specifieke Wi-Fi-instellingen en dit profiel vervolgens implementeren op uw Android-apparaten. Microsoft Intune biedt veel functies, waaronder het verifiëren bij het netwerk, het toevoegen van een PKS- of SCEP-certificaat en meer.

Deze Wi-Fi-instellingen worden in twee categorieën onderverdeeld: Basisinstellingen en instellingen op zakelijk niveau.

In dit artikel worden deze instellingen beschreven.

## <a name="before-you-begin"></a>Voordat u begint

[Maak een apparaatprofiel](device-profile-create.md).

## <a name="basic"></a>Basic

- **Wi-Fi-type**: Selecteer **Basic**.
- **SSID**: voer de **serviceset-id** in, wat de echte naam is van het draadloze netwerk waarmee apparaten verbinding maken. Gebruikers zien echter alleen de **netwerknaam** die u hebt geconfigureerd wanneer ze de verbinding kiezen.
- **Verborgen netwerk**: Kies **Inschakelen** om te voorkomen dat dit netwerk op het apparaat wordt weergegeven in de lijst met beschikbare netwerken. De SSID wordt niet verzonden. Kies **Uitschakelen** om dit netwerk in de lijst met beschikbare netwerken op het apparaat weer te geven.

## <a name="enterprise"></a>Enterprise

- **Wi-Fi-type**: Kies **Enterprise**.
- **SSID**: voer de **serviceset-id** in, wat de echte naam is van het draadloze netwerk waarmee apparaten verbinding maken. Gebruikers zien echter alleen de **netwerknaam** die u hebt geconfigureerd wanneer ze de verbinding kiezen.
- **Verborgen netwerk**: Kies **Inschakelen** om te voorkomen dat dit netwerk op het apparaat wordt weergegeven in de lijst met beschikbare netwerken. De SSID wordt niet verzonden. Kies **Uitschakelen** om dit netwerk in de lijst met beschikbare netwerken op het apparaat weer te geven.
- **EAP-type**: Kies het type Extensible Authentication Protocol (EAP) dat wordt gebruikt voor het verifiëren van beveiligde draadloze verbindingen. Uw opties zijn:

  - **EAP-TLS**: Voer ook in:

    - **Vertrouwelijke server** - **Basiscertificaat voor servervalidatie**: Kies een bestaand profiel voor een vertrouwd basiscertificaat. Dit certificaat wordt aan de server gepresenteerd wanneer vanuit de client verbinding wordt gemaakt met het netwerk. Hiermee wordt de verbinding geverifieerd.

    - **Clientverificatie** - **Clientcertificaat voor clientverificatie (identiteitscertificaat)** : Kies het profiel van het SCEP- of PKCS-clientcertificaat dat ook op het apparaat is geïmplementeerd. Dit certificaat is de identiteit die door het apparaat wordt gepresenteerd aan de server om de verbinding te verifiëren.

    - **Identiteitsprivacy (externe identiteit)** : Voer de tekst in die wordt verzonden in antwoord op een EAP-identiteitsaanvraag. Deze tekst kan elke waarde hebben, zoals `anonymous`. Tijdens verificatie wordt deze anonieme identiteit in eerste instantie verzonden en wordt deze gevolgd door de echte identificatie in een beveiligde tunnel.

    - **Proxy-instellingen**: geef de proxyconfiguratie op die door uw organisatie wordt gebruikt. Uw opties zijn:

      - **Geen** : u gebruikt geen proxyserver.
      - **Automatisch**: selecteer deze optie om de instelling *URL van proxyserver* beschikbaar te maken, waarmee u uw proxyserver of een PAC-bestand (Proxy Auto-Configuration) kunt opgeven dat een lijst met uw proxyservers bevat.

    - **URL van proxyserver**: deze instelling is beschikbaar wanneer u *Proxyinstellingen* instelt op *Automatisch*. Geef een van de volgende opties op om apparaten naar uw proxyserver te leiden:

      - IP-adres. bijvoorbeeld `10.0.0.11`
      - Een URL. Bijvoorbeeld `http://proxyserver.contoso.com`.
      - De URL van een PAC-bestand (Proxy Auto-Configuration). Bijvoorbeeld: `http://proxy.contoso.com/proxy.pac`.

      Zie [PAC-bestand (Proxy Auto-Configuration)](https://developer.mozilla.org/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_(PAC)_file) (hiermee opent u een niet-Microsoft-site) voor meer informatie over PAC-bestanden.

  - **EAP-TTLS**: Voer ook in:

    - **Vertrouwelijke server** - **Basiscertificaat voor servervalidatie**: Kies een bestaand profiel voor een vertrouwd basiscertificaat. Dit certificaat wordt aan de server gepresenteerd wanneer vanuit de client verbinding wordt gemaakt met het netwerk. Hiermee wordt de verbinding geverifieerd.

    - **Clientverificatie**: Kies een **Verificatiemethode**. Uw opties zijn:

      - **Gebruikersnaam en wachtwoord**: De gebruiker wordt gevraagd om een gebruikersnaam en wachtwoord om de verbinding te verifiëren. Voer ook in:
        - **Niet-EAP-methode (interne identiteit)** : Kies hoe de verbinding moet worden geverifieerd. Zorg ervoor dat u hetzelfde protocol kiest dat op uw Wi-Fi-netwerk is geconfigureerd. Uw opties zijn:

          - **Niet-versleuteld wachtwoord (PAP)**
          - **Challenge Henshake Authentication Protocol (CHAP)**
          - **Microsoft CHAP (MS-CHAP)**
          - **Microsoft CHAP versie 2 (MS-CHAP v2)**

      - **Certificaten**: Kies het profiel van het SCEP- of PKCS-clientcertificaat dat ook op het apparaat is geïmplementeerd. Dit certificaat is de identiteit die door het apparaat wordt gepresenteerd aan de server om de verbinding te verifiëren.

      - **Identiteitsprivacy (externe identiteit)** : Voer de tekst in die wordt verzonden in antwoord op een EAP-identiteitsaanvraag. Deze tekst kan elke waarde hebben, zoals `anonymous`. Tijdens verificatie wordt deze anonieme identiteit in eerste instantie verzonden en wordt deze gevolgd door de echte identificatie in een beveiligde tunnel.

    - **Proxy-instellingen**: geef de proxyconfiguratie op die door uw organisatie wordt gebruikt. Uw opties zijn:

      - **Geen** : u gebruikt geen proxyserver.
      - **Automatisch**: selecteer deze optie om de instelling *URL van proxyserver* beschikbaar te maken, waarmee u uw proxyserver of een PAC-bestand (Proxy Auto-Configuration) kunt opgeven dat een lijst met uw proxyservers bevat.

    - **URL van proxyserver**: deze instelling is beschikbaar wanneer u *Proxyinstellingen* instelt op *Automatisch*. Geef een van de volgende opties op om apparaten naar uw proxyserver te leiden:

      - IP-adres. bijvoorbeeld `10.0.0.11`
      - Een URL. Bijvoorbeeld `http://proxyserver.contoso.com`.
      - De URL van een PAC-bestand (Proxy Auto-Configuration). Bijvoorbeeld: `http://proxy.contoso.com/proxy.pac`.

      Zie [PAC-bestand (Proxy Auto-Configuration)](https://developer.mozilla.org/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_(PAC)_file) (hiermee opent u een niet-Microsoft-site) voor meer informatie over PAC-bestanden.

  - **PEAP**: Voer ook in:

    - **Vertrouwelijke server** - **Basiscertificaat voor servervalidatie**: Kies een bestaand profiel voor een vertrouwd basiscertificaat. Dit certificaat wordt aan de server gepresenteerd wanneer vanuit de client verbinding wordt gemaakt met het netwerk. Hiermee wordt de verbinding geverifieerd.

    - **Clientverificatie**: Kies een **Verificatiemethode**. Uw opties zijn:

      - **Gebruikersnaam en wachtwoord**: De gebruiker wordt gevraagd om een gebruikersnaam en wachtwoord om de verbinding te verifiëren. Voer ook in:
        - **Niet-EAP-methode voor verificatie (interne identiteit)** : Kies hoe de verbinding moet worden geverifieerd. Zorg ervoor dat u hetzelfde protocol kiest dat op uw Wi-Fi-netwerk is geconfigureerd. Uw opties zijn:

          - **Geen**
          - **Microsoft CHAP versie 2 (MS-CHAP v2)**

      - **Certificaten**: Kies het profiel van het SCEP- of PKCS-clientcertificaat dat ook op het apparaat is geïmplementeerd. Dit certificaat is de identiteit die door het apparaat wordt gepresenteerd aan de server om de verbinding te verifiëren.

      - **Identiteitsprivacy (externe identiteit)** : Voer de tekst in die wordt verzonden in antwoord op een EAP-identiteitsaanvraag. Deze tekst kan elke waarde hebben, zoals `anonymous`. Tijdens verificatie wordt deze anonieme identiteit in eerste instantie verzonden en wordt deze gevolgd door de echte identificatie in een beveiligde tunnel.

      - **Proxy-instellingen**: geef de proxyconfiguratie op die door uw organisatie wordt gebruikt. Uw opties zijn:

        - **Geen** : u gebruikt geen proxyserver.
        - **Automatisch**: selecteer deze optie om de instelling *URL van proxyserver* beschikbaar te maken, waarmee u uw proxyserver of een PAC-bestand (Proxy Auto-Configuration) kunt opgeven dat een lijst met uw proxyservers bevat.

      - **URL van proxyserver**: deze instelling is beschikbaar wanneer u *Proxyinstellingen* instelt op *Automatisch*. Geef een van de volgende opties op om apparaten naar uw proxyserver te leiden:

        - IP-adres. bijvoorbeeld `10.0.0.11`
        - Een URL. Bijvoorbeeld `http://proxyserver.contoso.com`.
        - De URL van een PAC-bestand (Proxy Auto-Configuration). Bijvoorbeeld: `http://proxy.contoso.com/proxy.pac`.

        Zie [PAC-bestand (Proxy Auto-Configuration)](https://developer.mozilla.org/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_(PAC)_file) (hiermee opent u een niet-Microsoft-site) voor meer informatie over PAC-bestanden.

## <a name="next-steps"></a>Volgende stappen

Het profiel is gemaakt, maar er gebeurt niets. Vervolgens [wijst u dit profiel toe](device-profile-assign.md).

## <a name="more-resources"></a>Meer bronnen

- [Overzicht Wi-Fi-instellingen](wi-fi-settings-configure.md), met inbegrip van andere platformen.

- Gebruikt u Android Enterprise- of Android-Kiosk-apparaten? Zo ja, raadpleeg dan [Wifi-instellingen voor apparaten met Android Enterprise en toegewezen apparaten](wi-fi-settings-android-enterprise.md).
