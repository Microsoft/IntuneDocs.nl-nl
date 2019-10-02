---
title: Nalevingsbeleid voor Jamf-apparaten
titleSuffix: Microsoft Intune
description: Gebruik Microsoft Intune-nalevingsbeleid met voorwaardelijke toegang van Azure Active Directory om met Jamf beheerde apparaten te beveiligen.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 01/02/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: c87fd2bd-7f53-4f1b-b985-c34f2d85a7bc
ms.reviewer: elocholi
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 3542d86429293531a22678e14520e59cd9de9dc6
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/02/2019
ms.locfileid: "71721536"
---
# <a name="enforce-compliance-on-macs-managed-with-jamf-pro"></a>Nalevingsbeleid afdwingen op Macs die door Jamf Pro worden beheerd

Van toepassing op: Intune in Azure Portal

U kunt Azure Active Directory en het beleid voor voorwaardelijke toegang van Microsoft Intune gebruiken om ervoor te zorgen dat uw eindgebruikers voldoen aan de vereisten van de organisatie. U kunt deze beleidsregels toepassen op Mac-computers die worden [beheerd door Jamf Pro](conditional-access-integrate-jamf.md). Hiervoor is toegang tot de Intune- en Jamf Pro-consoles vereist.

## <a name="set-up-device-compliance-policies-in-intune"></a>Nalevingsbeleid voor apparaten in Intune instellen

1. Open Microsoft Azure en navigeer naar **Intune** > **Apparaatcompatibiliteit** > **Beleid**. U kunt beleidsregels maken voor macOS, zoals het kiezen van een reeks acties (bijvoorbeeld het versturen van waarschuwingse-mails naar niet-conforme gebruikers en groepen).
2. Selecteer het beleid > Toewijzingen. U kunt Azure Active Directory-beveiligingsgroepen (AD) opnemen of uitsluiten.
3. Kies Geselecteerde groepen om uw Azure AD-beveiligingsgroepen weer te geven. Selecteer de gebruikersgroepen waarop u dit beleid wilt toepassen > kies Opslaan om het beleid voor gebruikers te implementeren.

U hebt het beleid toegepast op gebruikers. De apparaten die worden gebruikt door de gebruikers op wie het beleid is gericht, worden geëvalueerd op naleving en gemarkeerd als compatibel voor de instelling Vereisen dat het apparaat moet worden gemarkeerd als compatibel in Azure Active Directory.

> [!Note]
> Voor Intune moet de schijf volledig worden versleuteld om aan het beleid te voldoen.

## <a name="deploy-the-company-portal-app-for-macos-in-jamf-pro"></a>De bedrijfsportal-app voor macOS in Jamf Pro implementeren

U moet de bedrijfsportal-app voor macOS in Jamf Pro implementeren als achtergrondinstallatie met de onderstaande procedure:

1. Download op een macOS-apparaat de huidige versie van de [bedrijfsportal-app voor macOS](https://go.microsoft.com/fwlink/?linkid=862280). Installeer deze niet; u hebt een kopie van de app nodig om te uploaden naar Jamf Pro.
2. Open Jamf Pro en navigeer naar **Computer management** > **Packages**.
3. Maak een nieuw pakket met de bedrijfsportal-app voor macOS en klik vervolgens op **Save**.
4. Open **Computers** > **Policies** en selecteer **New**.
5. Gebruik de nettolading **General** om instellingen voor het beleid te configureren. Deze instellingen zijn:
   - Trigger: selecteer **Enrollment Complete** en **Recurring Check-in**
   - Uitvoeringsfrequentie: selecteer **Once per computer**
6. Selecteer de nettolading **Packages** en klik op **Configure**.
7. Klik op **Add** om het pakket met de bedrijfsportal-app te selecteren.
8. Kies **Install** in het contextmenu **Action**.
9. Configureer de instellingen voor het pakket.
10. Klik op het tabblad **Scope** om op te geven op welke computers de bedrijfsportal-app moet worden geïnstalleerd. Klik op **Opslaan**. Door het beleid worden apparaten binnen het bereik uitgevoerd de volgende keer dat de geselecteerde trigger plaatsvindt op de computer en voldoet aan de criteria in de nettolading **General**.

## <a name="create-a-policy-in-jamf-pro-to-have-users-register-their-devices-with-azure-active-directory"></a>Een beleid in Jamf Pro maken waarmee gebruikers hun apparaten met Azure Active Directory kunnen registreren

> [!NOTE]
> U moet [de bedrijfsportal implementeren](conditional-access-assign-jamf.md#deploy-the-company-portal-app-for-macos-in-jamf-pro) voor macOS voordat u verdergaat met de volgende stappen.  

Eindgebruikers moeten de bedrijfsportal-app via de selfservice van Jamf starten om het apparaat te registreren bij Azure AD als een apparaat dat wordt beheerd door Jamf Pro. Hiervoor moet uw eindgebruikers actie ondernemen. We raden aan dat u [contact opneemt met uw eindgebruikers](../fundamentals/end-user-educate.md) via e-mail, Jamf Pro-meldingen of op een andere manier om hen te laten weten dat ze op de knop in Jamf Self Service moeten klikken.

> [!WARNING]
> De bedrijfsportal-app moet worden gestart vanuit Jamf Self Service om de apparaatregistratie te starten. <br><br>Als de bedrijfsportal-app handmatig wordt gestart (bijvoorbeeld via de map Toepassingen of Downloads), wordt het apparaat niet geregistreerd. Als een eindgebruiker de bedrijfsportal handmatig start, verschijnt de waarschuwing 'AccountNotOnboarded'.

1. Navigeer in Jamf Pro naar **Computers** > **Policies** en maak een nieuw beleid voor apparaatregistratie.
2. Configureer de nettolading **Microsoft Intune Integration**, inclusief de frequentie voor triggers en uitvoering.
3. Klik op het tabblad **Scope** en pas het beleid toe op alle doelapparaten.
4. Klik op het tabblad **Self Service** om het beleid beschikbaar te maken in de selfservice van Jamf. Neem het beleid op in de categorie **Device Compliance**. Klik op **Opslaan**.

## <a name="removing-a-jamf-managed-device-from-intune"></a>Een door Jamf beheerd apparaat verwijderen uit Intune

U kunt een door Jamf beheerd apparaat verwijderen uit de Intune-console door in de weergave **Alle apparaten** **Verwijderen** te selecteren. Bulkverwijdering van apparaten kan worden ingeschakeld door meerdere apparaten te selecteren en op **Verwijderen** te klikken.

U vindt meer informatie over [het verwijderen van door Jamf beheerde apparaten in de Jamf Pro-documenten](https://www.jamf.com/jamf-nation/articles/80/unmanaging-computers-while-preserving-their-inventory-information). U kunt ook een ondersteuningsticket indienen met [Jamf-ondersteuning](https://www.jamf.com/support/) voor meer informatie. 

## <a name="next-steps"></a>Volgende stappen

- [Voorwaardelijke toegang in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)
- [Aan de slag met voorwaardelijke toegang in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal-get-started)
