---
title: Een pagina voor de status van de inschrijving instellen
titleSuffix: Microsoft Intune
description: Heet de gebruikers welkom die Windows 10-apparaten inschrijven.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 5/17/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 8518d8fa-a0de-449d-89b6-8a33fad7b3eb
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: c6604c35cebdad4341f27a51db1a4c735f9a9818
ms.sourcegitcommit: 6bd5867c41fb5288fde114dbfcc127dd206f7148
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/17/2018
ms.locfileid: "34235613"
---
# <a name="set-up-an-enrollment-status-page"></a>Een pagina voor de status van de inschrijving instellen
 
[!INCLUDE [azure_portal](./includes/azure_portal.md)]
 
Tijdens de installatie van het apparaat wordt op de inschrijvingsstatuspagina statusinformatie weergegeven over de installatie op het apparaat van de eindgebruiker. Sommige toepassingen, profielen en certificaten worden mogelijk niet volledig geïnstalleerd tegen de tijd dat een gebruiker is ingeschreven. De statuspagina is handig voor gebruikers om de status van hun apparaat tijdens en na de inschrijving te bekijken. U kunt de statuspagina voor alle gebruikers inschakelen en voorkomen dat gebruikers het apparaat gebruiken totdat alle toegewezen toepassingen en profielen zijn geïnstalleerd.
 
Volg de onderstaande stappen om de pagina voor de status van de inschrijving in te schakelen voor alle eindgebruikers.
 
1.  In [Intune](https://aka.ms/intuneportal) kiest u **Apparaatinschrijving** > **Windows-inschrijving** > **De pagina Inschrijvingsstatus (preview)**.
2.  In de blade **Pagina Status van inschrijving** kiest u **Standaard** > **Instellingen**.
3.  Voor **Voortgang van installatie van app en profiel** kiest u **Ja**.
4.  Kies de andere instellingen die u wilt inschakelen en kies vervolgens **Opslaan**.
 
## <a name="enrollment-status-page-tracking-information"></a>Traceringsinformatie op de pagina Status van inschrijving

Op de statuspagina wordt informatie bijgehouden voor voorbereiding van het apparaat, installatie van het apparaat en installatie van het account.

### <a name="device-preparation"></a>Voorbereiding van het apparaat

Voor voorbereiding van het apparaat worden op de pagina voor de status van de inschrijving TPM-sleutelattestaties (Trusted Platform Module, indien van toepassing), de voortgang van de deelname aan Azure Active Directory en het inschrijven bij Intune bijgehouden.

### <a name="device-setup"></a>Installatie van het apparaat

Voor de installatie van het apparaat worden op de pagina voor de status van de inschrijving de volgende items bijgehouden als deze aan alle apparaten zijn toegewezen:
- Beveiligingsbeleid
    - Eén configuratieprovider (CSP) voor alle inschrijvingen.
    - Werkelijke CSP's die door Intune zijn geconfigureerd, worden hier niet bijgehouden.
- Toepassingen
    - LoB MSI-apps (Line of Business) per apparaat.
    - LoB-opslag-apps met installatiecontext = apparaat.
    - Offline opslag- en LoB-opslag-apps met installatiecontext = apparaat.
- Connectiviteitsprofielen (VPN en Wi-Fi) worden nog niet bijgehouden, dus hierbij wordt altijd ‘0 van 0’ vermeld.
- Certificaten worden nog niet bijgehouden, dus hierbij wordt altijd ‘0 van 0’ vermeld.

### <a name="account-setup"></a>Account instellen
For installatie van het account worden op de pagina voor de status van de inschrijving de volgende items bijgehouden:
- Beveiligingsbeleid
    - Eén CSP voor alle inschrijvingen.
    - Werkelijke CSP's die door Intune zijn geconfigureerd, worden hier niet bijgehouden.
- Toepassingen
    - LoB MSI-apps per gebruiker die worden toegewezen aan alle apparaten, aan alle gebruikers of aan of een gebruikersgroep waarvan de gebruiker die het apparaat inschrijft, lid is.
    - LoB MSI-apps per apparaat die worden toegewezen aan alle gebruikers of aan of een gebruikersgroep waarvan de gebruiker die het apparaat inschrijft, lid is.
    - LoB-opslag-apps die worden toegewezen aan alle apparaten, aan alle gebruikers of aan of een gebruikersgroep waarvan de gebruiker die het apparaat inschrijft, lid is, met installatiecontext = Gebruiker.
    - Online opslag-apps die worden toegewezen aan alle apparaten, aan alle gebruikers of aan of een gebruikersgroep waarvan de gebruiker die het apparaat inschrijft, lid is, met installatiecontext = Gebruiker.
    - Offline opslag-apps die worden toegewezen aan alle apparaten, aan alle gebruikers of aan of een gebruikersgroep waarvan de gebruiker die het apparaat inschrijft, lid is, met installatiecontext = Gebruiker.
- Connectiviteitsprofielen
    - VPN- of Wi-Fi-profielen die worden toegewezen aan alle gebruikers of aan een gebruikersgroep waarvan de gebruiker die het apparaat inschrijft, lid is.
- Certificaten
    - Certificaatprofielen die worden toegewezen aan alle gebruikers of aan een gebruikersgroep waarvan de gebruiker die het apparaat inschrijft, lid is.

## <a name="next-steps"></a>Volgende stappen
Nadat u Windows-inschrijvingspagina's hebt ingesteld, kunt u leren hoe u Windows-apparaten beheert. Zie [Wat is Microsoft Intune-apparaatbeheer?](https://docs.microsoft.com/intune/device-management) voor meer informatie.