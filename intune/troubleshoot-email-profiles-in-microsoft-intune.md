---
title: Problemen met e-mailprofielen oplossen in Microsoft Intune - Azure | Microsoft Docs
description: Problemen met e-mailprofielen en hoe u deze kunt oplossen.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 6/14/2018
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: f5c944ea-32a6-48af-bb57-16d5f1f3c588
ROBOTS: ''
ms.reviewer: tscott
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: ef84241f72f34e0f00516702d0928e0395478929
ms.sourcegitcommit: 916fed64f3d173498a2905c7ed8d2d6416e34061
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 05/23/2019
ms.locfileid: "66044665"
---
# <a name="troubleshoot-email-profiles-in-microsoft-intune"></a>Problemen met e-mailprofielen in Microsoft Intune oplossen

Lees welke problemen met e-mailprofielen zich vaak voordoen en hoe u deze kunt oplossen.

Als deze informatie geen oplossing biedt, kunt u ook [ondersteuning voor Microsoft Intune krijgen](get-support.md).

## <a name="unable-to-send-images-from--email-account"></a>Kan geen afbeeldingen verzenden vanuit e-mailaccount
Van toepassing op Intune in de klassieke Azure-portal.

Gebruikers met automatisch geconfigureerde e-mailaccounts kunnen geen afbeeldingen of foto’s verzenden vanaf hun apparaat. Dit scenario kan zich voordoen als de optie **Toestaan dat e-mails worden verzonden vanuit toepassingen van derden** niet is ingeschakeld.

### <a name="intune-solution"></a>Intune-oplossing

1. Open de Microsoft Intune-beheerconsole en selecteer achtereenvolgens de workload **Beleid** > **Configuratiebeleid**.

2. Selecteer het e-mailprofiel en kies **Bewerken**.

3. Selecteer **Toestaan dat e-mails worden verzonden vanuit toepassingen van derden**.

### <a name="configuration-manager-integrated-with-intune-solution"></a>Configuration Manager geïntegreerd met Intune-oplossing

1. Open de Configuration Manager-console > **Assets en naleving**.

2. Vouw **Overzicht** > **Instellingen voor naleving** > **Toegang tot bedrijfsbronnen** uit en selecteer **E-mailprofielen**.

3. Klik met de rechtermuisknop op het e-mailprofiel en open **Eigenschappen**.

4. Selecteer op het tabblad **Synchronisatie-instellingen** de optie **Toestaan dat e-mails worden verzonden vanuit toepassingen van derden**.

## <a name="device-already-has-an-email-profile-installed"></a>Er is al een e-mailprofiel geïnstalleerd op het apparaat

Als de gebruiker een e-mailprofiel heeft geïnstalleerd voorafgaand aan het inrichten van een Intune-profiel, is het resultaat van de implementatie van het Intune-e-mailprofiel afhankelijk van het apparaatplatform:

- **iOS**: Intune detecteert een bestaand, dubbel e-mailprofiel op basis van hostnaam en e-mailadres. Het duplicaat van het e-mailprofiel dat is gemaakt door de gebruiker, blokkeert de implementatie van een Intune-profiel dat door een beheerder is gemaakt. Dit is een veelvoorkomend probleem, omdat iOS-gebruikers vaak zelf een e-mailprofiel maken en het apparaat vervolgens inschrijven. De bedrijfsportal deelt de gebruiker mee dat deze niet voldoet aan de eisen vanwege het handmatig geconfigureerde e-mailprofiel en vraagt de gebruiker dit profiel te verwijderen. De gebruiker moet het e-mailprofiel verwijderen, zodat het Intune-profiel kan worden geïmplementeerd. Voorkom dit probleem door gebruikers te vertellen dat ze zich moeten inschrijven en Intune toe te staan het profiel te implementeren. Installeer vervolgens het door de gebruiker gemaakte e-mailprofiel.

- **Windows**: Intune detecteert een bestaand, dubbel e-mailprofiel op basis van hostnaam en e-mailadres. Intune overschrijft het bestaande e-mailprofiel dat is gemaakt door de gebruiker.

- **Samsung KNOX Standard**: Intune identificeert een dubbel e-mailaccount op basis van het e-mailadres, en overschrijft het met het Intune-profiel. Als de gebruiker dat account configureert, wordt het opnieuw overschreven door het Intune-profiel. Dit kan leiden tot enige verwarring bij de gebruiker van wie de accountconfiguratie wordt overschreven.

Samsung KNOX gebruikt geen hostnaam om het profiel te identificeren. U kunt het beste niet meerdere e-mailprofielen maken om hetzelfde e-mailadres op verschillende hosts te implementeren, aangezien deze profielen door elkaar worden overschreven.

## <a name="error--0x87d1fde8-for-knox-standard-device"></a>Fout 0x87D1FDE8 voor KNOX Standard-apparaat
**Probleem**: na het maken en implementeren van een Exchange Active Sync-e-mailprofiel voor Samsung KNOX Standard voor verschillende Android-apparaten, wordt door de apparaten de fout **0x87D1FDE8** of de fout **Doorvoeren is mislukt** gemeld op het tabblad Beleid van de eigenschappen van het apparaat.

Controleer de configuratie van uw EAS-profiel voor Samsung KNOX en het bronbeleid. De synchronisatieoptie voor Samsung Notes wordt niet meer ondersteund en deze optie moet niet worden geselecteerd in uw profiel. Geef de apparaten voldoende tijd (maximaal 24 uur) om het beleid te verwerken.

## <a name="next-steps"></a>Volgende stappen
Als deze informatie geen oplossing biedt, kunt u ook [ondersteuning voor Microsoft Intune krijgen](get-support.md).
