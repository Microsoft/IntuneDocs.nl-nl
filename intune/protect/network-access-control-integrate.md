---
title: Netwerktoegangsbeheer integreren met Microsoft Intune - Azure | Microsoft Docs
description: De oplossingen voor netwerktoegangsbeheer controleren de inschrijving en naleving voor apparaten met Intune. Netwerktoegangsbeheer omvat bepaalde gedragingen en werkt met voorwaardelijke toegang. Zie de stappen voor het onboarding-proces en een lijst met partneroplossingen.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 04/25/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: aa7ecff7-8579-4009-8fd6-e17074df67de
ms.reviewer: davidra
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6e1d534ed3d631a94296a5f6c76c2a323b00afa4
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/02/2019
ms.locfileid: "71722030"
---
# <a name="network-access-control-nac-integration-with-intune"></a>Netwerktoegangsbeheer integreren met Intune

Intune kan worden geïntegreerd met producten van partners voor netwerktoegangsbeheer (ook wel Network Access Control of kortweg NAC genoemd) om de zakelijke gegevens van organisaties te beveiligen wanneer apparaten proberen toegang te krijgen tot on-premises resources.

## <a name="how-do-intune-and-nac-solutions-help-protect-your-organization-resources"></a>De resources van uw organisatie beveiligen met Intune en NAC-oplossingen

NAC-oplossingen controleren de apparaatregistratie en nalevingsstatus bij Intune om op basis hiervan beslissingen over toegangsbeheer te nemen. Als het apparaat niet is geregistreerd, of wel is geregistreerd maar niet voldoet aan het Intune-nalevingsbeleid voor apparaten, moet het apparaat worden omgeleid naar Intune voor registratie of een compatibiliteitscontrole.

### <a name="example"></a>Voorbeeld

Als het apparaat is geregistreerd en compatibel is met Intune, moet de NAC-oplossing het apparaat toegang geven tot bedrijfsresources. Als gebruikers bijvoorbeeld via Wi-Fi of een VPN toegang proberen te krijgen tot bedrijfsresources, kan dit worden toegestaan of geweigerd.

## <a name="feature-behaviors"></a>Gedrag van de functie

Apparaten die actief worden gesynchroniseerd met Intune, kunnen niet worden omgezet van **Compatibel** / **Niet-compatibel** naar **Niet gesynchroniseerd** (of **Onbekend**). De status **Onbekend** is gereserveerd voor pas geregistreerde apparaten die nog niet zijn geëvalueerd voor naleving.

Voor apparaten die zijn geblokkeerd voor toegang tot resources, moet de blokkerende service alle gebruikers doorsturen naar de [beheerportal](https://portal.manage.microsoft.com) om te bepalen waarom het apparaat is geblokkeerd.  Als de gebruikers deze pagina bezoeken, worden hun apparaten op synchrone wijze opnieuw geëvalueerd voor naleving.

## <a name="nac-and-conditional-access"></a>NAC en voorwaardelijke toegang

NAC werkt met voorwaardelijke toegang om beslissingen voor toegangsbeheer mogelijk te maken. Zie [Common ways to use conditional access with Intune](conditional-access-intune-common-ways-use.md) (Gebruikelijke manieren om voorwaardelijke toegang met Intune te gebruiken) voor meer informatie.

## <a name="how-the-nac-integration-works"></a>De werking van NAC-integratie

Hieronder volgt een overzicht van de manier waarop NAC-integratie werkt in combinatie met Intune. In de eerste drie stappen wordt het onboarding-proces uitgelegd. Zodra de NAC-oplossing in Intune is geïntegreerd, kunt u in de stappen 4-9 de lopende bewerking zien.

![Conceptafbeelding van de manier waarop NAC werkt in combinatie met Intune](./media/network-access-control-integrate/ca-intune-common-ways-2.png)

1. Registreer de NAC-partneroplossing bij Azure Active Directory (AAD) en verleen gedelegeerde machtigingen aan de NAC-API van Intune.
2. Configureer de NAC-partneroplossing met de juiste instellingen, inclusief de detectie-URL van Intune.
3. Configureer de NAC-partneroplossing voor certificaatverificatie.
4. Een gebruiker maakt verbinding met een Wi-Fi-toegangspunt of verstuurt een aanvraag voor een VPN-verbinding.
5. De NAC-partneroplossing stuurt de gegevens van het apparaat door naar Intune en vraagt bij Intune gegevens op over de apparaatregistratie en nalevingsstatus.
6. Als het apparaat niet compatibel is of niet is geregistreerd, krijgt de gebruiker instructies van de NAC-partneroplossing om het apparaat te registreren of compatibel te maken.
7. De compatibiliteit en/of registratiestatus van het apparaat worden/wordt opnieuw geverifieerd, indien van toepassing.
8. Zodra het apparaat is geregistreerd en compatibel is, vraagt de NAC-partneroplossing de status op bij Intune.
9. De verbinding wordt tot stand gebracht en het apparaat heeft nu toegang tot de bedrijfsresources.

## <a name="use-nac-for-vpn-on-your-ios-devices"></a>Netwerktoegangsbeheer (NAC) voor VPN gebruiken op uw iOS-apparaten  

- NAC is beschikbaar op de volgende VPN's zonder NAC te hoeven inschakelen in het VPN-profiel:

  - NAC voor Cisco Legacy AnyConnect
  - Verouderde F5-toegang
  - Citrix VPN

- NAC is ook beschikbaar voor Citrix SSO en F5-toegang. Doe het volgende om NAC voor Citrix SSO in te schakelen:

  - Gebruik Citrix Gateway 12.0.59 of hoger.  
  - Gebruikers moeten Citrix SSO 1.1.6 of later hebben geïnstalleerd.
  - [Integreer NetScaler met Intune voor NAC](https://docs.citrix.com/en-us/netscaler-gateway/12/microsoft-intune-integration/configuring-network-access-control-device-check-for-netscaler-gateway-virtual-server-for-single-factor-authentication-deployment.html) zoals beschreven in de Citrix-productdocumentatie.
  - Ga naar het VPN-profiel, selecteer **Basisinstellingen** > **Netwerktoegangscontrole (NAC) instellen** en selecteer **Ik ga akkoord**.

  De VPN-verbinding wordt elke 24 uur uit veiligheidsoverwegingen verbroken. De VPN-verbinding wordt onmiddellijk hersteld.

- U schakelt NAC als volgt in voor F5-toegang:

  - Gebruik F5 BIG-IP 13.1.1.5. BIG-IP 14 wordt niet ondersteund.
  - Integreer BIG-IP met Intune voor NAC. In de F5-handleiding[Overzicht: APM configureren voor apparaatpostuurcontroles met eindpuntbeheersystemen](https://support.f5.com/kb/en-us/products/big-ip_apm/manuals/product/apm-client-configuration-7-1-6/6.html#guid-0bd12e12-8107-40ec-979d-c44779a8cc89) worden de stappen uitgelegd.
  - Ga naar het VPN-profiel, selecteer **Basisinstellingen** > **Netwerktoegangscontrole (NAC) instellen** en selecteer **Ik ga akkoord**.

  De VPN-verbinding wordt elke 24 uur uit veiligheidsoverwegingen verbroken. De VPN-verbinding wordt onmiddellijk hersteld.

- Netwerktoegangsbeheer wordt niet ondersteund voor de volgende VPN-clients op iOS:
  - Cisco AnyConnect

We werken samen met onze partners om een NAC-oplossing voor deze nieuwere clients uit te brengen. Zodra de oplossingen gereed zijn, wordt dit artikel bijgewerkt met aanvullende informatie.

## <a name="next-steps"></a>Volgende stappen

- [Cisco ISE integreren met Intune](https://www.cisco.com/c/en/us/td/docs/security/ise/2-1/admin_guide/b_ise_admin_guide_21/b_ise_admin_guide_20_chapter_01000.html)
- [Citrix NetScaler integreren met Intune](https://docs.citrix.com/en-us/netscaler-gateway/12/microsoft-intune-integration/configuring-network-access-control-device-check-for-netscaler-gateway-virtual-server-for-single-factor-authentication-deployment.html)
- [F5 BIG-IP-toegangsbeleidbeheer integreren met Intune](https://support.f5.com/kb/en-us/products/big-ip_apm/manuals/product/apm-client-configuration-13-0-0/6.html)
- [HP Aruba ClearPass integreren met Intune](https://support.arubanetworks.com/Documentation/tabid/77/DMXModule/512/Command/Core_Download/Default.aspx?EntryId=31271)
- [Squadra security Removable Media Manager (secRMM) integreren met Intune](http://www.squadratechnologies.com/StaticContent/ProductDownload/secRMM/9.9.0.0/secRMMIntuneAccessControlSetupGuide.pdf)
