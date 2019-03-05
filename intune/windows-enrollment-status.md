---
title: Een pagina voor de status van de inschrijving instellen
titleSuffix: Microsoft Intune
description: Stel een begroetingspagina in voor gebruikers die Windows 10-apparaten registreren.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 10/5/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 8518d8fa-a0de-449d-89b6-8a33fad7b3eb
ms.reviewer: damionw
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7fd91a3537b9350b1cf647f203fb1454cd17a62d
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/02/2019
ms.locfileid: "57238962"
---
# <a name="set-up-an-enrollment-status-page"></a>Een pagina voor de status van de inschrijving instellen
 
[!INCLUDE [azure_portal](./includes/azure_portal.md)]
 
Tijdens de installatie van het apparaat met Intune wordt op de pagina Status van de registratie informatie over de installatie weergegeven op het apparaat. Sommige toepassingen, profielen en certificaten zijn mogelijk niet geïnstalleerd op het moment dat een gebruiker de out-of-box-registratie op het apparaat voltooit. Een pagina Status van de registratie is handig voor gebruikers om de status van hun apparaat tijdens de installatie van het apparaat te bekijken. U kunt voor de pagina Status van de registratie meerdere profielen maken en deze toepassen op verschillende groepen. Profielen kunnen worden ingesteld op:
- De voortgang van de installatie weergeven.
- Gebruik blokkeren totdat de installatie is voltooid.
- Opgeven wat een gebruiker kan doen als de installatie van het apparaat mislukt.

U kunt ook de volgorde van prioriteit voor elk profiel instellen om problemen met conflicterende profieltoewijzingen aan dezelfde gebruiker of hetzelfde apparaat te voorkomen.

 
## <a name="turn-on-default-enrollment-status-page-for-all-users"></a>De standaardpagina Status van de inschrijving voor alle gebruikers inschakelen

Volg de onderstaande stappen om de pagina Status van de registratie in te schakelen.
 
1. In [Intune](https://aka.ms/intuneportal) kiest u **Apparaatinschrijving** > **Windows-inschrijving** > **Pagina Status van de inschrijving (preview)**.
2. In de blade **Pagina Status van de inschrijving** kiest u **Standaard** > **Instellingen**.
3. Bij **Voortgang van installatie van app en profiel weergeven** kiest u **Ja**.
4. Kies de andere instellingen die u wilt inschakelen en kies vervolgens **Opslaan**.

## <a name="create-enrollment-status-page-profile-and-assign-to-a-group"></a>Profiel voor pagina Status van de registratie maken en dit aan een groep toewijzen

1. In [Intune](https://aka.ms/intuneportal) kiest u **Apparaatinschrijving** > **Windows-inschrijving** > **Pagina Status van de inschrijving (preview)** > **Profiel maken**.
2. Geef een **naam** en **beschrijving** op.
3. Kies **Maken**.
4. Kies het nieuwe profiel in de lijst **Pagina Status van de inschrijving**.
5. Kies **Toewijzingen** > **Groepen selecteren** > kies de groepen waarvoor u dit profiel wilt instellen > **Selecteren** > **Opslaan**.
6. Kies **Instellingen** > kies de instellingen die u op dit profiel wilt toepassen > **Opslaan**.

## <a name="set-the-enrollment-status-page-priority"></a>De prioriteit instellen voor de pagina Status van de registratie

Een apparaat of gebruiker kan zich in meerdere groepen bevinden en meerdere profielen hebben voor de pagina Status van de registratie. U kunt de prioriteiten voor elk profiel instellen om problemen met dergelijke conflicten te voorkomen. Als iemand meer dan een profiel heeft voor de pagina Status van de registratie, wordt alleen het profiel met de hoogste prioriteit toegepast.

1. In [Intune](https://aka.ms/intuneportal) kiest u **Apparaatinschrijving** > **Windows-inschrijving** > **Pagina Status van de inschrijving (preview)**.
2. Beweeg de muisaanwijzer over het profiel in de lijst.
3. Sleep met behulp van de drie verticale puntjes het profiel naar de gewenste positie in de lijst.

## <a name="block-access-to-a-device-until-a-specific-application-is-installed"></a>Toegang blokkeren tot een apparaat tot een bepaalde toepassing is geïnstalleerd

U kunt opgeven welke apps moeten worden geïnstalleerd voordat de gebruiker toegang krijgt tot het bureaublad.

1. Kies in Intune **Apparaatinschrijving** > **Windows-inschrijving** > **Pagina Status van de inschrijving (preview)**.
2. Kies een profiel > **Instellingen**.
3. Kies **Ja** bij **Voortgang van installatie van app en profiel weergeven**.
4. Kies **Ja** bij **Apparaatgebruik blokkeren totdat alle apps en profielen zijn geïnstalleerd**.
5. Kies **Geselecteerd** bij **Apparaatgebruik blokkeren totdat deze vereiste apps zijn geïnstalleerd als ze worden toegewezen aan de gebruiker/apparaat**.
 6. Kies **Apps selecteren** > kies de apps > **selecteer** > **Opslaan**.

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
- Connectiviteitsprofielen
    - VPN- of Wi-Fi-profielen die zijn toegewezen aan **Alle apparaten** of een groep apparaten waarvan het apparaat dat wordt geregistreerd lid is, maar alleen voor Autopilot-apparaten
- Certificaatprofielen die zijn toegewezen aan **Alle apparaten** of een groep apparaten waarvan het apparaat dat wordt geregistreerd lid is, maar alleen voor Autopilot-apparaten

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
