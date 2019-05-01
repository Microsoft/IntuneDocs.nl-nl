---
title: Het nalevingsbeleid voor apparaten en apps configureren bij een Intune-migratie
titleSuffix: Microsoft Intune
description: In dit artikel wordt beschreven welke stappen u moet uitvoeren om het nalevingsbeleid voor apparaten en het beleid voor appbeheer te configureren bij een Microsoft Intune-migratie.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/02/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 0062d08e-e5b3-4f73-8b64-5ad95adbe945
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 76c6000c375c3128c0832f3dd6b40fe1ed4cf34b
ms.sourcegitcommit: 143dade9125e7b5173ca2a3a902bcd6f4b14067f
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/23/2019
ms.locfileid: "61508204"
---
# <a name="configure-device-compliance-and-app-management-policies-when-migrating-to-microsoft-intune"></a>Het nalevingsbeleid voor apparaten en het beleid voor appbeheer configureren bij een migratie naar Microsoft Intune

Het belangrijkste doel bij het migreren naar Intune is dat alle apparaten worden ingeschreven bij Intune en voldoen aan het voorgeschreven beleid. Met apparaatbeleid kunt u niet alleen apparaten in bedrijfseigendom beheren die bestemd zijn voor één gebruiker, maar ook persoonlijke apparaten (BYOD) en gedeelde apparaten, zoals kiosken, Point Of Sales-apparaten, tablets die worden gedeeld door meerdere studenten in een klaslokaal of apparaten die niet aan een specifieke gebruiker zijn gebonden (alleen iOS).

Voor elk apparaatplatform gelden mogelijk verschillende instellingen, maar het Intune-apparaatbeleid kan met elk apparaatplatform worden gebruikt en biedt daarbij de volgende mogelijkheden voor het beheer van mobiele apparaten:

-   Regulering van het aantal apparaten dat een gebruiker inschrijft.

-   Apparaatinstellingen beheren (zoals versleuteling op apparaatniveau, wachtwoordlengte en cameragebruik).

-   Leveren van apps, e-mailprofielen, VPN-profielen, enzovoort.

-   Het beoordelen van de criteria op apparaatniveau voor het nalevingsbeleid voor de beveiliging.

> [!IMPORTANT]
> Het apparaatbeheerbeleid wordt niet rechtstreeks toegewezen aan de afzonderlijke apparaten of gebruikers, maar aan gebruikersgroepen. Het beleid kan rechtstreeks worden toegepast op een gebruikersgroep en op die manier op het apparaat van de gebruiker. Het beleid kan ook worden toegepast op een apparaatgroep en op die manier op de groepsleden.

## <a name="task-list-for-device-compliance-policies"></a>Takenlijst voor het nalevingsbeleid voor apparaten

### <a name="task-1-add-device-groups-optional"></a>Taak 1: Apparaatgroepen toevoegen (optioneel)

U kunt apparaatgroepen maken wanneer u beheertaken moet uitvoeren op basis van de apparaatidentiteit in plaats van de gebruikersidentiteit.

Apparaatgroepen zijn nuttig voor het beheren van apparaten zonder specifieke gebruiker, zoals kioskapparaten, apparaten die worden gedeeld door werknemers van dezelfde dienst of apparaten die zijn toegewezen aan een specifieke locatie.

Door apparaatgroepen te beheren voordat ze worden ingeschreven, kunt u apparaatcategorieën gebruiken om apparaten bij inschrijving automatisch deel te laten nemen aan groepen. Vervolgens ontvangen de apparaten automatisch het apparaatbeleid. [Aan de slag met groepen](groups-get-started.md).

### <a name="task-2-use-resource-access-profiles-wi-fi-vpn-and-email-certificates"></a>Taak 2: Resourcetoegangsprofielen (certificaten voor Wi-Fi, VPN en e-mail) gebruiken

Door middel van resourcetoegangsprofielen worden certificaten en toegangsconfiguraties verstrekt aan de ingeschreven apparaten. Als u verificatie op basis van een certificaat gebruikt, kunt u [certificaten configureren](certificates-configure.md).

### <a name="task-3-create-and-deploy-device-configuration-profiles"></a>Taak 3: Apparaatconfiguratieprofielen maken en implementeren

U moet een apparaatconfiguratieprofiel maken om instellingen op apparaatniveau door te voeren, zoals de instelling voor het uitschakelen van de camera, de App Store, het configureren van de modus voor één app, het beginscherm, enzovoort. Meer informatie over [apparaatprofielen](device-profiles.md).

####  <a name="directly-import-ios-configuration-profiles-optional"></a>Rechtstreeks iOS-configuratieprofielen importeren (optioneel)

-   **iOS-profielen van Apple Configurator (iOS 7.1 en hoger):** Als uw bestaande MDM-oplossing gebruikmaakt van Apple Configurator-profielen (mobileconfig-bestanden), kunnen deze rechtstreeks door Intune worden geïmporteerd als aangepast configuratiebeleid.

-   **Configuratiebeleid voor mobiele apps voor iOS:** Als uw bestaande MDM-oplossing gebruikmaakt van een configuratiebeleid voor mobiele apps voor iOS, kan dit rechtstreeks door Intune worden geïmporteerd zolang het voldoet aan de XML-indeling die door Apple is opgegeven voor eigenschappenlijsten.

- Meer informatie over het toevoegen van een aangepast beleid voor [iOS](custom-settings-ios.md).

### <a name="task-4-create-and-deploy-device-compliance-policies-optional"></a>Taak 4: Nalevingsbeleid voor apparaten maken en implementeren (optioneel)

Met het nalevingsbeleid voor apparaten worden beveiligingsinstellingen geëvalueerd en wordt rapportage gegenereerd waarin wordt vermeld of de apparaten voldoen aan de bedrijfsnormen. Dergelijke instellingen zijn onder andere:

-   Lengte pincode

-   De status Jailbroken

-   Besturingssysteemversie

Zie aanvullende resources voor de instellingen voor het nalevingsbeleid voor apparaten:

-   Meer informatie over het [nalevingsbeleid voor apparaten](device-compliance.md).

-   Meer informatie over het [maken van een nalevingsbeleid voor apparaten](device-compliance-get-started.md).

### <a name="task-5-publish-and-deploy-apps"></a>Taak 5: Apps publiceren en implementeren

Wanneer u Intune MDM gebruikt, kunt u apps verstrekken door automatische installatie te vereisen of ze beschikbaar te stellen in de bedrijfsportal.

-   [Apps toevoegen](apps-add.md).

-   [Apps implementeren](apps-deploy.md).

### <a name="task-6-enable-device-enrollment"></a>Taak 6: Apparaatinschrijving inschakelen

U moet apparaten inschrijven om ze te kunnen beheren. Meer informatie over [de voorbereiding op het inschrijven van apparaten in bedrijfseigendom en persoonlijke apparaten](device-enrollment.md).

## <a name="next-steps"></a>Volgende stappen

[Beveiligingsbeleid voor apps configureren (optioneel)](migration-guide-app-protection-policies.md).
