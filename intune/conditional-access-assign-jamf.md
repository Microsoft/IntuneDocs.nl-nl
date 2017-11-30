---
title: Nalevingsbeleid toepassen op door Jamf beheerde apparaten
titlesuffix: Azure portal
description: Gebruik nalevingsbeleid voor het beveiligen van apparaten die door Jamf worden beheerd.
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 11/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c87fd2bd-7f53-4f1b-b985-c34f2d85a7bc
ms.reviewer: elocholi
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: dd84812a7e7dcf83f01c8d4d2b613706f7700775
ms.sourcegitcommit: b2a6678a0e9617f94ee8c65e7981211483b30ee7
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/22/2017
---
# <a name="enforce-compliance-on-macs-managed-with-jamf-pro"></a>Nalevingsbeleid afdwingen op Macs die door Jamf Pro worden beheerd

|Van toepassing op: Intune in Azure Portal |
|--|
|Op zoek naar documentatie over Intune in de klassieke portal? Klik [hier](/intune/introduction-intune?toc=/intune-classic/toc.json).|
| |

|Momenteel alleen als beperkte preview|
|--|
|De functies die in dit onderwerp worden beschreven, zijn alleen beschikbaar voor klanten die momenteel over de beperkte preview-versie beschikken. Dit bericht wordt verwijderd wanneer de functies voor alle klanten zijn vrijgegeven.|
| |

U kunt Azure Active Directory en het beleid voor voorwaardelijke toegang van Microsoft Intune gebruiken om ervoor te zorgen dat uw eindgebruikers voldoen aan de vereisten van de organisatie. U kunt deze beleidsregels toepassen op Mac-computers die worden [beheerd door Jamf Pro](conditional-access-integrate-jamf.md). Hiervoor is toegang tot de Intune- en Jamf Pro-consoles vereist.

## <a name="set-up-device-compliance-policies-in-intune"></a>Nalevingsbeleid voor apparaten in Intune instellen

1. Open Microsoft Azure en navigeer naar **Intune** > **Apparaatcompatibiliteit** > **Beleid**. U kunt beleidsregels maken voor macOS, zoals het kiezen van een reeks acties (bijvoorbeeld het versturen van waarschuwings-e-mails naar niet-compatibele gebruikers en groepen).
2. Zoek de gewenste groepen en pas daar het beleid op toe.

## <a name="require-the-company-portal-app-for-macos"></a>De bedrijfsportal-app voor macOS vereisen

1. Op een macOS-apparaat gaat u naar https://aka.ms/macoscompanyportal om de huidige versie van de bedrijfsportal-app voor macOS te downloaden.
2. Open Jamf Pro en navigeer naar **Computer management** > **Packages**.
3. Maak een nieuw pakket met de bedrijfsportal-app voor macOS en klik vervolgens op **Save**.
4. Open **Computers** > **Policies** en selecteer **New**.
5. Gebruik de nettolading **General** om instellingen voor het beleid te configureren, met inbegrip van de frequentie voor triggers en uitvoering.
6. Selecteer de nettolading **Packages** en klik op **Configure**.
7. Klik op **Add** om het pakket met de bedrijfsportal-app te selecteren.
8. Kies **Install** in het contextmenu **Action**.
9. Configureer de instellingen voor het pakket.
10. Klik op het tabblad **Scope** om op te geven op welke computers de bedrijfsportal-app moet worden geïnstalleerd. Klik op **Opslaan**. Door het beleid worden apparaten binnen het bereik uitgevoerd de volgende keer dat de geselecteerde trigger plaatsvindt op de computer en voldoet aan de criteria in de nettolading **General**.

## <a name="direct-your-users-to-register-jamf-pro-managed-devices-with-azure-active-directory"></a>Laat uw gebruikers door Jamf Pro beheerde apparaten registreren bij Azure Active Directory

> [!NOTE]
> U moet [de bedrijfsportal implementeren](conditional-access-assign-jamf.md#require-the-company-portal-app-for-macos) voor macOS voordat u verdergaat met de volgende stappen.  

Eindgebruikers moeten de bedrijfsportal-app via de selfservice van Jamf starten om het apparaat te registreren bij Azure AD als een apparaat dat wordt beheerd door Jamf Pro.

1. Navigeer in Jamf Pro naar **Computers** > **Policies** en maak een nieuw beleid voor apparaatregistratie.
2. Configureer de nettolading **Conditional Access**, met inbegrip van de frequentie voor triggers en uitvoering. Stel de prioriteit in op **After**.
3. Klik op het tabblad **Scope** en pas het beleid toe op alle doelapparaten.
4. Klik op het tabblad **Self Service** om het beleid beschikbaar te maken in de selfservice van Jamf. Neem het beleid op in de categorie **Device Compliance**. Klik op **Opslaan**.

## <a name="next-steps"></a>Volgende stappen

- [Voorwaardelijke toegang in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)
- [Aan de slag met voorwaardelijke toegang in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal-get-started)
