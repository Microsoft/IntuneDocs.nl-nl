---
title: Melding van niet-compatibele apparaten en acties met Microsoft Intune - Azure | Microsoft Docs
description: Maak een e-mailmelding om te verzenden naar niet-compatibele apparaten. Voeg acties toe nadat een apparaat is gemarkeerd als niet-compatibel, door bijvoorbeeld een respijtperiode toe te voegen om compatibel te worden, of maak een planning om toegang te blokkeren totdat het apparaat compatibel is. U doet dit met Microsoft Intune in Azure.
keywords: 
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/07/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 37a8deca147bbad1e706b814f366a2c3f1247869
ms.sourcegitcommit: 9cf05d3cb8099e4a238dae9b561920801ad5cdc6
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/09/2018
---
# <a name="automate-email-and-add-actions-for-noncompliant-devices---intune"></a>E-mail automatiseren en acties voor niet-compatibele apparaten toevoegen - Intune

Er is een functie **Acties voor niet-naleving** waarmee een op tijd geordende reeks acties worden geconfigureerd. Deze acties zijn van toepassing op apparaten die niet voldoen aan uw nalevingsbeleid. 

## <a name="overview"></a>Overzicht
Wanneer Intune een apparaat detecteert dat niet compatibel is, markeert Intune standaard het apparaat onmiddellijk als niet-compatibel. [Voorwaardelijke toegang](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) van Azure Active Directory (AD) blokkeert vervolgens het apparaat. Met de **acties voor niet-naleving** beschikt u ook over flexibiliteit om te bepalen wat er gebeurt bij niet-naleving van een apparaat. Blokkeer het apparaat bijvoorbeeld niet onmiddellijk en geef de gebruiker een respijtperiode om ervoor te zorgen dat het apparaat weer compatibel wordt.

Er zijn twee soorten acties:

- **Eindgebruikers informeren per e-mail**: u kunt een e-mailmelding aanpassen voordat u deze naar de eindgebruiker verstuurt. U kunt aanpassingen doorvoeren voor de ontvangers, het onderwerp en de berichttekst, inclusief het bedrijfslogo, en contactgegevens.

    Daarnaast geeft Intune meer informatie over het apparaat dat niet compatibel is in het e-mailbericht.

- **Apparaat markeren als niet-compatibel**: maak een schema (met een aantal dagen) waarna het apparaat wordt gemarkeerd als niet-compatibel. U kunt de actie zodanig configureren dat deze onmiddellijk in werking treedt, maar u kunt de gebruiker ook een respijtperiode bieden om te voldoen aan het nalevingsbeleid.

## <a name="before-you-begin"></a>Voordat u begint

- U moet ten minste één nalevingsbeleid voor apparaten hebben gemaakt om acties voor niet-naleving in te stellen. Zie de volgende platformen om een nalevingsbeleid voor apparaten te maken:

  - [Android](compliance-policy-create-android.md)
  - [Android for Work](compliance-policy-create-android-for-work.md)
  - [iOS](compliance-policy-create-ios.md)
  - [macOS](compliance-policy-create-mac-os.md)
  - [Windows](compliance-policy-create-windows.md)

- Wanneer u nalevingsbeleid gebruikt om toegang tot bedrijfsbronnen door apparaten te blokkeren, moet voorwaardelijke toegang voor Azure AD zijn ingesteld. Zie [Voorwaardelijke toegang in Azure Active Directory configureren](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) voor hulp.

- Er moet een sjabloon voor een meldingsbericht worden gemaakt. Om e-mail naar uw gebruikers te sturen, wordt deze sjabloon gebruikt om acties voor niet-naleving te maken.

## <a name="create-a-notification-message-template"></a>Een sjabloon voor een meldingsbericht maken

1. Meld u aan bij [Azure Portal](https://portal.azure.com) met uw Intune-referenties. 
2. Selecteer **Alle services**, filter op **Intune** en selecteer **Microsoft Intune**.
3. Selecteer **Apparaatcompatibiliteit** en vervolgens **Meldingen**. 
4. Selecteer **Melding maken** en voer de volgende gegevens in:

  - Naam
  - Onderwerp
  - Bericht
  - E-mailkoptekst - Bedrijfslogo opnemen
  - E-mailvoettekst - Bedrijfslogo opnemen
  - E-mailvoettekst – Contactgegevens opnemen

  ![Voorbeeld van een compatibel meldingsbericht in Intune](./media/actionsfornoncompliance-1.PNG)

Nadat u klaar bent met het toevoegen van informatie, kiest u **Maken**. De sjabloon voor het meldingsbericht is klaar voor gebruik.

> [!NOTE]
> U kunt ook een eerder gemaakte meldingssjabloon bewerken.

## <a name="add-actions-for-noncompliance"></a>Acties voor niet-naleving toevoegen

Intune maakt automatisch een actie voor niet-naleving. Wanneer een apparaat niet voldoet aan uw nalevingsbeleid, markeert deze actie het apparaat als niet-compatibel. U kunt aanpassen hoe lang het apparaat wordt gemarkeerd als niet compatibel. Deze actie kan niet worden verwijderd.

U kunt een actie toevoegen wanneer u nieuw nalevingsbeleid maakt of wanneer u een bestaand nalevingsbeleid bewerkt. 

1. Open in de [Azure Portal](https://portal.azure.com)**Microsoft Intune** en selecteer **Apparaatnaleving**.
2. Selecteer **Beleid**, kies een van uw beleidsregels en selecteer vervolgens **Eigenschappen**. 

  Heeft u nog geen beleid? Maak een beleid voor een [Android-](compliance-policy-create-android.md), [iOS-](compliance-policy-create-ios.md), [Windows-](compliance-policy-create-windows.md) platform of een ander platform.

3. Selecteer **Acties voor niet-nageleefd** en selecteer **Toevoegen** om de actieparameters in te voeren. U kunt de eerder gemaakte berichtsjabloon kiezen, extra ontvangers toevoegen en de planning voor de respijtperiode bijwerken. Bij het schema kunt u het aantal dagen (0-365) invoeren voor het afdwingen van het beleid voor voorwaardelijke toegang. Als u **0** aantal dagen opgeeft, blokkeert voorwaardelijke toegang **onmiddellijk** toegang tot bedrijfsbronnen.

4. Wanneer u klaart bent, selecteert u **Toevoegen** > **OK** om uw wijzigingen op te slaan.

## <a name="next-steps"></a>Volgende stappen
De activiteiten van de apparaat-naleving controleren door het uitvoeren van de rapporten. In [De apparaatnaleving controleren in Intune](device-compliance-monitor.md) vindt u meer informatie.
