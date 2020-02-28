---
title: Problemen met e-mailprofielen oplossen in Microsoft Intune - Azure | Microsoft Docs
description: Bekijk veelvoorkomende problemen met en oplossingen voor e-mailprofielen in Microsoft Intune, waaronder dubbele e-mailprofielen en fouten op Samsung KNOX Standard Android-apparaten.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/18/2020
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: f5c944ea-32a6-48af-bb57-16d5f1f3c588
ROBOTS: ''
ms.reviewer: tscott
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: a19830130f992a002b73402f5e13a8f062539917
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/20/2020
ms.locfileid: "77512667"
---
# <a name="common-issues-and-resolutions-with-email-profiles-in-microsoft-intune"></a>Veelvoorkomende problemen met en oplossingen voor e-mailprofielen in Microsoft Intune

Lees welke problemen met e-mailprofielen zich vaak voordoen en hoe u deze kunt oplossen.

## <a name="what-you-need-to-know"></a>Wat u dient te weten

- E-mailprofielen worden geïmplementeerd voor de gebruiker die het apparaat heeft geregistreerd. Om het e-mailprofiel te configureren, gebruikt Intune de Azure Active Directory-eigenschappen in het e-mailprofiel van de gebruiker tijdens de inschrijving. [E-mailinstellingen toevoegen aan apparaten](email-settings-configure.md) kan een goede informatiebron voor u zijn.
- Voor Android Enterprise implementeert u Gmail of Nine for Work met behulp van de beheerde Google Play Store. In [Beheerde Google Play-apps toevoegen](../apps/apps-add-android-for-work.md) worden de stappen weergegeven.
- Microsoft Outlook voor iOS/iPadOS en Android bieden geen ondersteuning voor e-mailprofielen. Implementeer in plaats daarvan een app-configuratiebeleid. Zie [Configuratie-instellingen voor Outlook](../apps/app-configuration-policies-outlook.md) voor meer informatie.
- E-mailprofielen die zijn gericht op apparaatgroepen (niet gebruikersgroepen), worden mogelijk niet bezorgd op het apparaat. Wanneer het apparaat een primaire gebruiker heeft, zou targeting van het apparaat moeten werken. Als het e-mailprofiel gebruikerscertificaten bevat, moet u doelgebruikersgroepen gebruiken.
- Gebruikers wordt mogelijk meermaals gevraagd om hun wachtwoord in te voeren voor het e-mailprofiel. In dit scenario controleert u alle certificaten waarnaar wordt verwezen in het e-mailprofiel. Als een van de certificaten niet is gericht op een gebruiker, probeert Intune het e-mailprofiel opnieuw te implementeren.

## <a name="device-already-has-an-email-profile-installed"></a>Er is al een e-mailprofiel geïnstalleerd op het apparaat

Als gebruikers een e-mailprofiel maken voordat ze zich inschrijven in Intune of Office 365 MDM, werkt het e-mailprofiel dat door Intune is geïmplementeerd mogelijk niet zoals verwacht:

- **iOS/iPadOS**: Intune detecteert een bestaand, dubbel e-mailprofiel op basis van hostnaam en e-mailadres. Het door de gebruiker gemaakte e-mailprofiel blokkeert de implementatie van het in Intune gemaakte profiel. Dit is een veelvoorkomend probleem, omdat iOS-/iPadOS-gebruikers vaak zelf een e-mailprofiel maken en het apparaat vervolgens inschrijven. De bedrijfsportal-app geeft aan dat de gebruiker niet compatibel is en kan de gebruiker vragen om het e-mailprofiel te verwijderen.

  De gebruiker moet het e-mailprofiel verwijderen, zodat het Intune-profiel kan worden geïmplementeerd. Voorkom dit probleem door gebruikers te vertellen dat ze zich moeten inschrijven en Intune toe te staan het e-mailprofiel te implementeren. Vervolgens kunnen gebruikers hun e-mailprofiel aanmaken.

- **Windows**: Intune detecteert een bestaand, dubbel e-mailprofiel op basis van hostnaam en e-mailadres. Intune overschrijft het bestaande e-mailprofiel dat is gemaakt door de gebruiker.

- **Samsung KNOX Standard**: Intune identificeert een dubbel e-mailaccount op basis van het e-mailadres, en overschrijft het met het Intune-profiel. Als de gebruiker dat account configureert, wordt het opnieuw overschreven door het Intune-profiel. Dit kan leiden tot enige verwarring bij de gebruiker van wie de accountconfiguratie wordt overschreven.

Samsung KNOX gebruikt geen hostnaam om het profiel te identificeren. U kunt het beste niet meerdere e-mailprofielen maken om hetzelfde e-mailadres op verschillende hosts te implementeren, aangezien deze profielen door elkaar worden overschreven.

## <a name="error-0x87d1fde8-for-knox-standard-device"></a>Fout 0x87D1FDE8 voor KNOX Standard-apparaat

**Probleem**: Na het maken en implementeren van een Exchange Active Sync-e-mailprofiel voor Samsung KNOX Standard voor verschillende Android-apparaten, wordt door de apparaten **0x87D1FDE8** of de fout **Doorvoeren is mislukt** weergegeven in het tabblad Beleid van de eigenschappen van het apparaat.

Controleer de configuratie van uw EAS-profiel voor Samsung KNOX en het bronbeleid. De synchronisatieoptie voor Samsung Notes wordt niet meer ondersteund en deze optie moet niet worden geselecteerd in uw profiel. Geef de apparaten voldoende tijd (maximaal 24 uur) om het beleid te verwerken.

## <a name="unable-to-send-images-from--email-account"></a>Kan geen afbeeldingen verzenden vanuit e-mailaccount

Gebruikers met automatisch geconfigureerde e-mailaccounts kunnen geen afbeeldingen of foto's verzenden vanaf hun apparaat. Dit scenario kan zich voordoen als de optie **Toestaan dat e-mails worden verzonden vanuit toepassingen van derden** niet is ingeschakeld.

1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecteer **Apparaten** > **Configuratieprofielen**.
3. Selecteer uw e-mailprofiel > **Eigenschappen** > **Instellingen**.
4. Stel **Toestaan dat e-mails worden verzonden vanuit toepassingen van derden** in op **Inschakelen**.

## <a name="next-steps"></a>Volgende stappen

Krijg [ondersteuning van Microsoft](../fundamentals/get-support.md) of gebruik de [communityforums](https://social.technet.microsoft.com/Forums/en-US/home?category=microsoftintune).
