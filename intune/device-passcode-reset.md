---
title: Wachtwoordcodes van apparaten opnieuw instellen met Microsoft Intune - Azure | Microsoft Docs
description: Verwijder de wachtwoordcode of stel deze opnieuw in met de actie Wachtwoordcode verwijderen op apparaten die u beheert of bewaakt met Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 09/18/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 47181d19-4049-4c7a-a8de-422206c4027e
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: aecc509a0a98f277de0fc550317151d71b4ecb2d
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/07/2019
ms.locfileid: "55839654"
---
# <a name="reset-or-remove-a-device-passcode-in-intune"></a>De wachtwoordcode van een apparaat opnieuw instellen of verwijderen via Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

In dit document bespreken we het opnieuw instellen van wachtwoordcodes op apparaatniveau en het opnieuw instellen van wachtwoordcodes voor werkprofielen op zakelijke Android-apparaten (voorheen Android for Work of AfW genoemd). Het is belangrijk om u bewust te zijn van dit onderscheid, aangezien de vereisten voor beide kunnen variëren. Bij het opnieuw instellen van wachtwoordcodes op apparaatniveau wordt de wachtwoordcode voor het gehele apparaat opnieuw ingesteld. Bij het opnieuw instellen van wachtwoordcodes voor werkprofielen wordt de wachtwoordcode alleen voor het werkprofiel van de gebruiker op zakelijke Android-apparaten opnieuw ingesteld.

## <a name="supported-platforms-for-device-level-passcode-reset"></a>Ondersteunde platformen voor het opnieuw instellen van wachtwoordcodes op apparaatniveau

| Platform | Ondersteund? |
| ---- | ---- |
| Android-apparaten met versie 6.x of lager | Ja |
| Zakelijke Android-apparaten in de kioskmodus | Ja |
| iOS-apparaten | Ja |
| Android-apparaten die zijn ingeschreven met een werkprofiel, versie 7.0 en lager | Nee |
| Android-apparaten met versie 7.0 of lager | Nee |
| macOS | Nee |
| Windows | Nee |

Voor Android-apparaten betekent dit dat het opnieuw instellen van wachtwoordcodes op apparaatniveau alleen wordt ondersteund op apparaten waarop 6.x of eerder wordt uitgevoerd of op zakelijke Android-apparaten die in de kioskmodus worden uitgevoerd. Dit komt doordat Google ondersteuning voor het opnieuw instellen van de wachtwoordcode/het wachtwoord van een Android 7-apparaat vanuit een door de apparaatbeheerder toegekende app heeft verwijderd. Dit is van toepassing op alle MDM-leveranciers.

## <a name="supported-platforms-for-android-enterprise-work-profile-passcode-reset"></a>Ondersteunde platformen voor het opnieuw instellen van wachtwoordcodes voor werkprofielen op zakelijke Android-apparaten

| Platform | Ondersteund? |
| ---- | ---- |
| Zakelijke Android-apparaten die met een werkprofiel zijn ingeschreven en waarop versie 8.0 of later wordt uitgevoerd | Ja |
| Zakelijke Android-apparaten die met een werkprofiel zijn ingeschreven en waarop versie 7.x of eerder wordt uitgevoerd | Nee |
| Android-apparaten waarop versie 7.x of eerder wordt uitgevoerd | Nee |
| iOS | Nee |
| macOS | Nee |

Als u een nieuwe wachtwoordcode voor het werkprofiel wilt maken, gebruikt u de actie Wachtwoordcode opnieuw instellen. Deze actie zorgt ervoor dat de wachtwoordcode opnieuw wordt ingesteld en een nieuwe, tijdelijke wachtwoordcode voor alleen het werkprofiel wordt gemaakt. 

## <a name="reset-a-passcode"></a>Een wachtwoordcode opnieuw instellen


1. Meld u aan bij [Azure Portal](https://portal.azure.com) met een van de volgende rollen: Globale beheerder van Azure Active Directory, Azure Active Directory Intune-servicebeheerder, helpdeskmedewerker of rolbeheerder. Raadpleeg de [Intune RBAC-tabel](https://gallery.technet.microsoft.com/Intune-RBAC-table-2e3c9a1a) voor een volledige lijst met rollen en machtigingen.
2. Selecteer **Alle services**, filter op **Intune** en selecteer **Microsoft Intune**.
3. Selecteer **Apparaten** en selecteer vervolgens **Alle apparaten**.
4. Selecteer een apparaat in de lijst met apparaten die u beheert en kies **...Meer**. Kies vervolgens de externe apparaatactie **Wachtwoordcode verwijderen**.

## <a name="reset-android-work-profile-passcodes"></a>Wachtwoordcodes voor Android-werkprofielen opnieuw instellen

Ondersteunde Android Enterprise-apparaten waarop een werkprofiel is ingeschreven, ontvangen een nieuw wachtwoord om het beheerde profiel te ontgrendelen of een beheerde gebruikersvraag voor eindgebruikers.

Voor zakelijke Android-apparaten waarop versie 8.x of later wordt uitgevoerd en die met een werkprofiel zijn ingeschreven, worden eindgebruikers geïnformeerd om hun wachtwoordcode opnieuw in te stellen zodra de inschrijving is voltooid. De melding wordt weergegeven als een wachtwoord voor een werkprofiel is vereist en is ingesteld. Zodra de wachtwoordcode is ingevoerd, wordt de melding verwijderd.


## <a name="remove-ios-passcodes"></a>iOS-wachtwoordcodes verwijderen

In plaats van opnieuw te worden ingesteld, worden wachtwoordcodes verwijderd uit iOS-apparaten. Als er een nalevingsbeleid voor wachtwoordcodes is ingesteld, wordt de gebruiker gevraagd om bij Instellingen een nieuwe wachtwoordcode in te stellen.

## <a name="next-steps"></a>Volgende stappen

Als u de status wilt weergeven van de actie die u zojuist hebt uitgevoerd, kiest u in **Apparaten** de optie **Apparaatacties**.
