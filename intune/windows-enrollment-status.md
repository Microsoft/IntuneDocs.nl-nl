---
title: Een pagina voor de status van de inschrijving instellen
titleSuffix: Microsoft Intune
description: Heet de gebruikers welkom die Windows 10-apparaten inschrijven.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 10/5/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 8518d8fa-a0de-449d-89b6-8a33fad7b3eb
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f5460db2d646d8bd417baa50d8188acbf69a251d
ms.sourcegitcommit: d92caead1d96151fea529c155bdd7b554a2ca5ac
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/06/2018
ms.locfileid: "48827986"
---
# <a name="set-up-an-enrollment-status-page"></a>Een pagina voor de status van de inschrijving instellen
 
[!INCLUDE [azure_portal](./includes/azure_portal.md)]
 
Tijdens de installatie van het apparaat wordt op de inschrijvingsstatuspagina informatie over de installatie weergegeven op het apparaat. Sommige apps, profielen en certificaten zijn mogelijk niet volledig geïnstalleerd tegen de tijd dat een gebruiker is ingeschreven. Een statuspagina is handig voor gebruikers om de status van hun apparaat tijdens en na de inschrijving te bekijken. U kunt de statuspagina voor alle gebruikers inschakelen of profielen maken om u op specifieke gebruikersgroepen te richten.  U kunt profielen zo instellen dat de installatievoortgang wordt weergegeven, dat gebruik wordt geblokkeerd tot de installatie is voltooid, dat opnieuw instellen wordt toegestaan, enzovoort.
 
## <a name="turn-on-default-enrollment-status-page-for-all-users"></a>De standaardpagina Status van de inschrijving voor alle gebruikers inschakelen

Volg de onderstaande stappen om de pagina Status van de inschrijving in te schakelen voor alle eindgebruikers.
 
1.  In [Intune](https://aka.ms/intuneportal) kiest u **Apparaatinschrijving** > **Windows-inschrijving** > **Pagina Status van de inschrijving (preview)**.
2.  In de blade **Pagina Status van de inschrijving** kiest u **Standaard** > **Instellingen**.
3.  Bij **Voortgang van installatie van app en profiel weergeven** kiest u **Ja**.
4.  Kies de andere instellingen die u wilt inschakelen en kies vervolgens **Opslaan**.

## <a name="create-enrollment-status-page-profile-to-target-specific-users"></a>Profiel voor pagina Status van de inschrijving maken om u op specifieke gebruikers te richten

1.  In [Intune](https://aka.ms/intuneportal) kiest u **Apparaatinschrijving** > **Windows-inschrijving** > **Pagina Status van de inschrijving (preview)** > **Profiel maken**.
2. Geef een **naam** en **beschrijving** op.
3. Kies **Maken**.
4. Kies het nieuwe profiel in de lijst **Pagina Status van de inschrijving**.
5. Kies **Toewijzingen** > **Groepen selecteren** > kies de groepen waarvoor u dit profiel wilt instellen > **Selecteren** > **Opslaan**.
6. Kies **Instellingen** > kies de instellingen die u op dit profiel wilt toepassen > **Opslaan**.


## <a name="enrollment-status-page-tracking-information"></a>Traceringsinformatie op de pagina Status van de inschrijving

Op de statuspagina wordt informatie bijgehouden voor voorbereiding van het apparaat, installatie van het apparaat en installatie van het account.

### <a name="device-preparation"></a>Voorbereiding van het apparaat

Voor voorbereiding van het apparaat worden op de pagina voor de status van de inschrijving TPM-sleutelattestaties (Trusted Platform Module, indien van toepassing), de voortgang van de deelname aan Azure Active Directory en het inschrijven bij Intune bijgehouden.

### <a name="device-setup"></a>Installatie van het apparaat

Voor de installatie van het apparaat worden op de pagina voor de status van de inschrijving de volgende items bijgehouden als deze aan alle apparaten zijn toegewezen:
- Beveiligingsbeleid
    - Eén configuratieprovider (CSP) voor alle inschrijvingen.
    - Werkelijke CSP's die door Intune zijn geconfigureerd, worden hier niet bijgehouden.
- Toepassingen
    - LOB (Line-of-Business) MSI-apps per apparaat.
    - LOB (Line-of-Business) opslag-apps met installatiecontext = apparaat.
    - Offline opslag- en LOB (Line-of-Business) opslag-apps met installatiecontext = apparaat.
- Connectiviteitsprofielen (VPN en Wi-Fi) worden nog niet bijgehouden, dus hierbij wordt altijd '0 van 0' vermeld.
- Certificaten worden nog niet bijgehouden, dus hierbij wordt altijd '0 van 0' vermeld.

### <a name="account-setup"></a>Account instellen
Voor het installeren van het account worden op de pagina voor de status van de inschrijving de volgende items bijgehouden:
- Beveiligingsbeleid
    - Eén CSP voor alle inschrijvingen.
    - Werkelijke CSP's die door Intune zijn geconfigureerd, worden hier niet bijgehouden.
- Toepassingen
    - LOB (Line-of-Business) MSI-apps per gebruiker die worden toegewezen aan alle apparaten, aan alle gebruikers of aan een gebruikersgroep waarvan de gebruiker die het apparaat inschrijft, lid is.
    - LOB (Line-of-Business) MSI-apps per apparaat die worden toegewezen aan alle gebruikers of aan een gebruikersgroep waarvan de gebruiker die het apparaat inschrijft, lid is.
    - LOB (Line-of-Business) store-apps, online store-apps en offline store-apps die aan een van de volgende zijn toegewezen:
        - Alle apparaten
        - Alle gebruikers
        - een gebruikersgroep waarvan de gebruiker die het apparaat inschrijft, lid is, met de installatiecontext ingesteld op Gebruiker.
- Connectiviteitsprofielen
    - VPN- of Wi-Fi-profielen die worden toegewezen aan alle gebruikers of aan een gebruikersgroep waarvan de gebruiker die het apparaat inschrijft, lid is.
- Certificaten
    - Certificaatprofielen die worden toegewezen aan alle gebruikers of aan een gebruikersgroep waarvan de gebruiker die het apparaat inschrijft, lid is.

## <a name="next-steps"></a>Volgende stappen
Nadat u Windows-inschrijvingspagina's hebt ingesteld, kunt u leren hoe u Windows-apparaten beheert. Zie [Wat is Microsoft Intune-apparaatbeheer?](https://docs.microsoft.com/intune/device-management) voor meer informatie.