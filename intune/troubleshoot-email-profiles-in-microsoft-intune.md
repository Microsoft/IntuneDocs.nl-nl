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
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: f5c944ea-32a6-48af-bb57-16d5f1f3c588
ROBOTS: ''
ms.reviewer: tscott
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 2246e3f6faa853f620327558a7faf4dc9d6a6e85
ms.sourcegitcommit: 43ba5a05b2e1dc1997126d3574884f65cde449c7
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 06/18/2019
ms.locfileid: "67197515"
---
# <a name="common-issues-and-resolutions-with-email-profiles-in-microsoft-intune"></a>Veelvoorkomende problemen met en oplossingen voor e-mailprofielen in Microsoft Intune

Lees welke problemen met e-mailprofielen zich vaak voordoen en hoe u deze kunt oplossen.

## <a name="what-you-need-to-know"></a>Wat u dient te weten

- E-mailprofielen worden geïmplementeerd voor de gebruiker die het apparaat heeft geregistreerd. Voor het configureren van het e-mailprofiel, Intune maakt gebruik van de Azure Active Directory (AD)-eigenschappen in het e-mailprofiel van de gebruiker tijdens de inschrijving. [E-mailinstellingen op apparaten toevoegen](email-settings-configure.md) mogelijk een goede bron.
- Na de migratie vanuit Configuration Manager hybrid zelfstandige versie van Intune, blijft het e-mailprofiel van Configuration Manager-hybride gedurende zeven dagen op het apparaat. Dit is normaal. Als u het e-mailprofiel dat eerder is verwijderd, neem dan contact op met [ondersteuning voor Intune](get-support.md).
- Voor Android Enterprise, Gmail of negen for Work met behulp van de beheerde Google Play Store te implementeren. [Beheerde Google Play-apps toevoegen](apps-add-android-for-work.md) vermeldt de stappen.
- E-mailprofielen biedt geen ondersteuning voor Microsoft Outlook voor iOS en Android. In plaats daarvan implementeert u een configuratiebeleid voor apps. Zie voor meer informatie, [Outlook-configuratie-instelling](app-configuration-policies-outlook.md).
- E-mailprofielen die zijn gericht op groepen van apparaten (niet gebruikersgroepen) kunnen niet worden bezorgd op het apparaat. Wanneer het apparaat een hoofdgebruiker heeft, klikt u vervolgens apparaat die gericht is op kunnen worden gebruikt. Als het e-mailprofiel gebruikerscertificaten bevat, moet u gebruikersdoelgroepen.
- Gebruikers kunnen herhaaldelijk gevraagd om hun wachtwoord invoeren voor het e-mailprofiel. In dit scenario, controleert u alle certificaten waarnaar wordt verwezen in het e-mailprofiel. Als een van de certificaten is niet bedoeld voor een gebruiker, klikt u vervolgens Intune nieuwe pogingen voor het implementeren van het e-mailprofiel.

## <a name="device-already-has-an-email-profile-installed"></a>Er is al een e-mailprofiel geïnstalleerd op het apparaat

Als gebruikers een e-mailprofiel maken voordat ze zich inschrijven bij Intune of Office 365 MDM, werkt het e-mailprofiel dat is geïmplementeerd door Intune mogelijk niet zoals verwacht:

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
3. Selecteer uw e-mailprofiel > **eigenschappen** > **instellingen**.
4. Stel de **toestaan dat e-mails worden verzonden vanuit toepassingen van derden** instelt op **inschakelen**.

### <a name="configuration-manager-hybrid"></a>Hybride Configuration Manager

1. Open de Configuration Manager-console > **Assets en naleving**.

2. Vouw **Overzicht** > **Instellingen voor naleving** > **Toegang tot bedrijfsbronnen** uit en selecteer **E-mailprofielen**.

3. Klik met de rechtermuisknop op het e-mailprofiel en open **Eigenschappen**.

4. Selecteer op het tabblad **Synchronisatie-instellingen** de optie **Toestaan dat e-mails worden verzonden vanuit toepassingen van derden**.

## <a name="next-steps"></a>Volgende stappen

Krijg [ondersteuning van Microsoft](get-support.md) of gebruik de [communityforums](https://social.technet.microsoft.com/Forums/en-US/home?category=microsoftintune).
