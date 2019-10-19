---
title: Problemen met e-mailprofielen oplossen in Microsoft Intune - Azure | Microsoft Docs
description: Bekijk veelvoorkomende problemen met en oplossingen voor e-mailprofielen in Microsoft Intune, waaronder dubbele e-mailprofielen en fouten op Samsung KNOX Standard Android-apparaten.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 06/17/2019
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
ms.openlocfilehash: 101f414955a3b60d22003f61678854fecc16910d
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 10/16/2019
ms.locfileid: "72506576"
---
# <a name="common-issues-and-resolutions-with-email-profiles-in-microsoft-intune"></a>Veelvoorkomende problemen met en oplossingen voor e-mailprofielen in Microsoft Intune

Lees welke problemen met e-mailprofielen zich vaak voordoen en hoe u deze kunt oplossen.

## <a name="what-you-need-to-know"></a>Wat u dient te weten

- E-mail profielen worden geïmplementeerd voor de gebruiker die het apparaat heeft geregistreerd. Als u het e-mail profiel wilt configureren, gebruikt intune de Azure Active Directory (AD)-eigenschappen in het e-mail Profiel van de gebruiker tijdens de inschrijving. Het [toevoegen van e-mail instellingen aan apparaten](email-settings-configure.md) kan een goede bron zijn.
- Na de migratie van Configuration Manager hybride naar de zelfstandige versie van intune, blijft het e-mail Profiel van Configuration Manager hybride gedurende 7 dagen op het apparaat. Dit is normaal. Als u het e-mail profiel eerder wilt verwijderen, neemt u contact op met de [ondersteuning van intune](../fundamentals/get-support.md).
- Voor Android Enter prise implementeert u Gmail of negen voor werk met behulp van de beheerde Google Play Store. [Beheerde Google Play-apps toevoegen](../apps/apps-add-android-for-work.md) worden de stappen weer gegeven.
- Micro soft Outlook voor iOS en Android biedt geen ondersteuning voor e-mail profielen. Implementeer in plaats daarvan een app-configuratie beleid. Zie Outlook-configuratie- [instellingen](../apps/app-configuration-policies-outlook.md)voor meer informatie.
- E-mail profielen die zijn gericht op apparaatgroepen (niet gebruikers groepen), worden mogelijk niet bezorgd op het apparaat. Wanneer het apparaat een primaire gebruiker heeft, zou het doel van het apparaat moeten werken. Als het e-mail profiel gebruikers certificaten bevat, moet u ervoor zorgen dat u gebruikers groepen bereikt.
- Gebruikers wordt mogelijk herhaaldelijk gevraagd om hun wacht woord in te voeren voor het e-mail profiel. In dit scenario controleert u alle certificaten waarnaar wordt verwezen in het e-mail profiel. Als een van de certificaten niet is gericht op een gebruiker, probeert intune het e-mail profiel te implementeren.

## <a name="device-already-has-an-email-profile-installed"></a>Er is al een e-mailprofiel geïnstalleerd op het apparaat

Als gebruikers een e-mail profiel maken voordat ze worden inge schreven in intune of Office 365 MDM, werkt het e-mail profiel dat door intune wordt geïmplementeerd mogelijk niet zoals verwacht:

- **iOS**: Intune detecteert een bestaand, dubbel e-mailprofiel op basis van hostnaam en e-mailadres. Het door de gebruiker gemaakte e-mailprofiel blokkeert de implementatie van het in Intune gemaakte profiel. Dit is een veelvoorkomend probleem, omdat iOS-gebruikers vaak zelf een e-mailprofiel maken en het apparaat vervolgens inschrijven. De bedrijfsportal-app geeft aan dat de gebruiker niet compatibel is en kan de gebruiker vragen om het e-mailprofiel te verwijderen.

  De gebruiker moet het e-mailprofiel verwijderen, zodat het Intune-profiel kan worden geïmplementeerd. Voorkom dit probleem door gebruikers te vertellen dat ze zich moeten inschrijven en Intune toe te staan het e-mailprofiel te implementeren. Vervolgens kunnen gebruikers hun e-mailprofiel aanmaken.

- **Windows**: Intune detecteert een bestaand, dubbel e-mailprofiel op basis van hostnaam en e-mailadres. Intune overschrijft het bestaande e-mailprofiel dat is gemaakt door de gebruiker.

- **Samsung KNOX Standard**: Intune identificeert een dubbel e-mailaccount op basis van het e-mailadres, en overschrijft het met het Intune-profiel. Als de gebruiker dat account configureert, wordt het opnieuw overschreven door het Intune-profiel. Dit kan leiden tot enige verwarring bij de gebruiker van wie de accountconfiguratie wordt overschreven.

Samsung KNOX gebruikt geen hostnaam om het profiel te identificeren. U kunt het beste niet meerdere e-mailprofielen maken om hetzelfde e-mailadres op verschillende hosts te implementeren, aangezien deze profielen door elkaar worden overschreven.

## <a name="error-0x87d1fde8-for-knox-standard-device"></a>Fout 0x87D1FDE8 voor KNOX Standard-apparaat

**Probleem**: na het maken en implementeren van een Exchange Active Sync-e-mailprofiel voor Samsung KNOX Standard voor verschillende Android-apparaten, wordt door de apparaten **0x87D1FDE8** of de fout **Doorvoeren is mislukt** weergegeven in het tabblad Beleid van de eigenschappen van het apparaat.

Controleer de configuratie van uw EAS-profiel voor Samsung KNOX en het bronbeleid. De synchronisatieoptie voor Samsung Notes wordt niet meer ondersteund en deze optie moet niet worden geselecteerd in uw profiel. Geef de apparaten voldoende tijd (maximaal 24 uur) om het beleid te verwerken.

## <a name="unable-to-send-images-from--email-account"></a>Kan geen afbeeldingen verzenden vanuit e-mailaccount

Gebruikers met automatisch geconfigureerde e-mailaccounts kunnen geen afbeeldingen of foto's verzenden vanaf hun apparaat. Dit scenario kan zich voordoen als de optie **Toestaan dat e-mails worden verzonden vanuit toepassingen van derden** niet is ingeschakeld.

### <a name="intune-solution"></a>Intune-oplossing

1. Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Selecteer **Apparaatconfiguratie** > **Profielen**.
3. Selecteer uw e-mail Profiel > **eigenschappen**  > **instellingen**.
4. Stel in **dat de instelling E-mail mag worden verzonden vanuit toepassingen van derden** om in te **scha kelen**.

### <a name="configuration-manager-hybrid"></a>Hybride Configuration Manager

1. Open de Configuration Manager-console > **Assets en naleving**.

2. Vouw **Overzicht** > **Instellingen voor naleving** > **Toegang tot bedrijfsbronnen** uit en selecteer **E-mailprofielen**.

3. Klik met de rechtermuisknop op het e-mailprofiel en open **Eigenschappen**.

4. Selecteer op het tabblad **Synchronisatie-instellingen** de optie **Toestaan dat e-mails worden verzonden vanuit toepassingen van derden**.

## <a name="next-steps"></a>Volgende stappen

Krijg [ondersteuning van Microsoft](../fundamentals/get-support.md) of gebruik de [communityforums](https://social.technet.microsoft.com/Forums/en-US/home?category=microsoftintune).
