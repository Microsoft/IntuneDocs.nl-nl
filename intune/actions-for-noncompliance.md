---
title: Melding van niet-compatibele apparaten en acties met Microsoft Intune - Azure | Microsoft Docs
description: Maak een e-mailmelding om te verzenden naar niet-compatibele apparaten. Voeg acties toe nadat een apparaat is gemarkeerd als niet-compatibel, door bijvoorbeeld een respijtperiode toe te voegen om compatibel te worden, of maak een planning om toegang te blokkeren totdat het apparaat compatibel is. U doet dit met Microsoft Intune in Azure.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 05/01/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: bf808a9a7f5a801997f37bd2ecf4c13e3823c332
ms.sourcegitcommit: 4b83697de8add3b90675c576202ef2ecb49d80b2
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/13/2019
ms.locfileid: "67044802"
---
# <a name="automate-email-and-add-actions-for-noncompliant-devices-in-intune"></a>E-mail automatiseren en acties voor niet-compatibele apparaten toevoegen in Intune

Voor apparaten die niet aan uw nalevingsbeleid of -regels voldoen, kunt u **Acties voor niet-naleving** toevoegen. Met deze functie configureert u een reeks chronologische acties, zoals het versturen van e-mailberichten naar eindgebruikers, en meer.

## <a name="overview"></a>Overzicht

Wanneer Intune een apparaat detecteert dat niet compatibel is, markeert Intune standaard het apparaat onmiddellijk als niet-compatibel. [Voorwaardelijke toegang](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) van Azure Active Directory (AD) blokkeert vervolgens het apparaat. Met de **actie voor niet-naleving** beschikt u ook over flexibiliteit om te bepalen wat er gebeurt bij niet-naleving van een apparaat. Blokkeer het apparaat bijvoorbeeld niet onmiddellijk en geef de gebruiker een respijtperiode om ervoor te zorgen dat het apparaat weer compatibel wordt.

Er zijn verschillende soorten acties:

- **E-mail verzenden naar de eindgebruiker**: Pas een e-mailmelding aan voordat u deze naar de eindgebruikers verzendt. U kunt aanpassingen doorvoeren voor de ontvangers, het onderwerp en de berichttekst, inclusief het bedrijfslogo, en contactgegevens.

    Daarnaast geeft Intune meer informatie over het apparaat dat niet compatibel is in het e-mailbericht.

- **U kunt het niet-compatibele apparaat als volgt op afstand vergrendelen**: U kunt apparaten die niet compatibel zijn, extern vergrendelen. De gebruiker wordt vervolgens gevraagd een pincode of wachtwoord in te voeren om het apparaat te ontgrendelen. Meer over de functie [Extern vergrendelen](device-remote-lock.md). 

- **Apparaat markeren als niet-compatibel**: maak een schema (met een aantal dagen) waarna het apparaat wordt gemarkeerd als niet-compatibel. U kunt de actie zodanig configureren dat deze onmiddellijk in werking treedt, maar u kunt de gebruiker ook een respijtperiode bieden om te voldoen aan het nalevingsbeleid.

In dit artikel leest u informatie over:

- Een sjabloon voor berichtmeldingen maken
- Een actie voor niet-naleving maken, zoals het verzenden van een e-mail of het extern vergrendelen van een apparaat


## <a name="before-you-begin"></a>Voordat u begint

- U moet ten minste één nalevingsbeleid voor apparaten hebben gemaakt om acties voor niet-naleving in te stellen. Zie de volgende platformen om een nalevingsbeleid voor apparaten te maken:

  - [Android](compliance-policy-create-android.md)
  - [Android-werkprofielen](compliance-policy-create-android-for-work.md)
  - [iOS](compliance-policy-create-ios.md)
  - [macOS](compliance-policy-create-mac-os.md)
  - [Windows](compliance-policy-create-windows.md)

- Wanneer u nalevingsbeleid gebruikt om toegang tot bedrijfsbronnen door apparaten te blokkeren, moet voorwaardelijke toegang voor Azure AD zijn ingesteld. Zie [Voorwaardelijke toegang in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) of [Gebruikelijke manieren om voorwaardelijke toegang met Intune te gebruiken](conditional-access-intune-common-ways-use.md) voor instructies.

## <a name="create-a-notification-message-template"></a>Een sjabloon voor een meldingsbericht maken

Maak een sjabloon voor berichtmeldingen om een e-mail naar uw gebruikers te versturen. Wanneer een apparaat niet conform is, worden de gegevens die u in de sjabloon invoert, weergegeven in de e-mail die naar uw gebruikers wordt verzonden.

1. Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Selecteer **Apparaatnaleving** > **Meldingen**.
3. Selecteer **Melding maken**. Voer de volgende informatie in:

   - **Naam**
   - **Onderwerp**
   - **Bericht**
   - **E-mailkoptekst - Bedrijfslogo opnemen**
   - **E-mailvoettekst - Bedrijfslogo opnemen**
   - **E-mailvoettekst - Contactgegevens opnemen**

   ![Voorbeeld van een compatibel meldingsbericht in Intune](./media/actionsfornoncompliance-1.PNG)

4. Nadat u klaar bent met het toevoegen van informatie, kiest u **Maken**. De sjabloon voor het meldingsbericht is klaar voor gebruik. Het logo dat u uploadt als onderdeel van de huisstijl voor de bedrijfsportal, zal worden gebruikt voor e-mailsjablonen. Zie [Aanpassing bedrijfshuisstijl](company-portal-app.md#company-identity-branding-customization) voor meer informatie over de huisstijl voor de bedrijfsportal.

> [!NOTE]
> Ook kunt u een bestaande meldingssjabloon die u eerder hebt gemaakt wijzigen of bijwerken.

## <a name="add-actions-for-noncompliance"></a>Acties voor niet-naleving toevoegen

Wanneer u een nalevingsbeleid voor apparaten maakt, maakt Intune automatisch een actie voor niet-naleving. Als een apparaat niet voldoet aan uw nalevingsbeleid, markeert deze actie het apparaat als niet-compatibel. U kunt aanpassen hoe lang het apparaat wordt gemarkeerd als niet compatibel. Deze actie kan niet worden verwijderd.

U kunt ook nog een actie toevoegen wanneer u een nalevingsbeleid maakt of wanneer u een bestaand beleid bijwerkt. 

1. Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) en selecteer **Apparaatcompatibiliteit**.
2. Selecteer **Beleid**, kies een van uw beleidsregels en selecteer vervolgens **Eigenschappen**. 

    Heeft u nog geen beleid? Maak een beleid voor een [Android-](compliance-policy-create-android.md), [iOS-](compliance-policy-create-ios.md), [Windows-](compliance-policy-create-windows.md) platform of een ander platform.
  
    > [!NOTE]
    > JAMF-apparaten en apparaten die worden toegepast op apparaatgroepen kunnen momenteel geen nalevingsacties ontvangen.

3. Selecteer **Acties voor niet-naleving** > **Toevoegen**.
4. Selecteer uw **actie**: 

    - **E-mail verzenden naar eindgebruikers**: Wanneer het apparaat niet compatibel is, kunt u de gebruiker een e-mail sturen. Ook: 
    
         - De **berichtsjabloon** kiezen die u eerder hebt gemaakt
         - Eventuele **extra ontvangers** invoeren door groepen te selecteren
    
    - **U kunt het niet-compatibele apparaat als volgt op afstand vergrendelen**: Als het apparaat niet compatibel is, vergrendelt u het apparaat. De gebruiker moet een pincode of wachtwoord invoeren om het apparaat te ontgrendelen. 
    
5. Een **planning** configureren: Voer het aantal dagen (0 tot 365) na niet-naleving in voor het activeren van de actie op apparaten van gebruikers. Na deze respijtperiode kunt u een beleid voor voorwaardelijke toegang afdwingen. Als u **0** (nul) dagen invoert, wordt de voorwaardelijke toegang **onmiddellijk** van kracht. U kunt bijvoorbeeld onmiddellijk toegang tot bedrijfsbronnen blokkeren als een apparaat niet conform is.

6. Wanneer u klaart bent, selecteert u **Toevoegen** > **OK** om uw wijzigingen op te slaan.

## <a name="next-steps"></a>Volgende stappen

[Controleer uw beleidsregels](compliance-policy-monitor.md).
