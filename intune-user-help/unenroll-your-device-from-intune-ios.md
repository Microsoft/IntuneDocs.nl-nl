---
title: Uw iOS-apparaat uit Intune verwijderen | Microsoft Docs
description: Hierin wordt beschreven hoe u een iOS-apparaat uit Intune kunt verwijderen
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 04/02/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 28914db1-3e62-45f5-9632-b0d2a808a44d
searchScope:
- User help
ROBOTS: ''
ms.reviewer: esmich
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: 210a11cbd6e2c3be85ed0b0f97c2bb4ab59d11e6
ms.sourcegitcommit: bccfbf1e3bdc31382189fc4489d337d1a554e6a1
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 07/03/2019
ms.locfileid: "67546600"
---
# <a name="remove-your-ios-device-from-intune"></a>Uw iOS-apparaat uit Intune verwijderen

Wanneer u uw iOS-apparaat uit Intune verwijdert, heeft uw apparaat geen toegang meer tot bedrijfsresources en wordt uw apparaat niet meer beheerd met Intune.


## <a name="removing-the-device-from-my-devices"></a>Het apparaat verwijderen uit Mijn apparaten

Voer deze stappen uit of bekijk deze video om uw apparaat uit Intune te verwijderen:


1. Tik in de bedrijfsportal-app op **Apparaten** en selecteer het apparaat waarvoor u de registratie ongedaan wilt maken. Als u slechts één apparaat hebt en op **Apparaten** tikt, gaat u rechtstreeks naar het scherm met details voor dat apparaat.

2. Tik naast **NAAM WIJZIGEN** op de knop met het beletselteken > **Apparaat verwijderen** > **Verwijderen**.  

    |![Schermopname van het scherm Apparaten in de bedrijfsportal-app, met de opties die beschikbaar zijn nadat de gebruiker op Verwijderen heeft geklikt. Toont de knoppen Apparaat verwijderen, Fabrieksinstellingen terugzetten en Annuleren.](/intune-user-help/media/cp_ios_unenroll_after_1804_001.png)|

    |![Schermopname van het scherm Apparaten in de bedrijfsportal-app, met de opties die beschikbaar zijn nadat de gebruiker op de knop Apparaat verwijderen heeft geklikt. Toont de in het rood gemarkeerde knop Verwijderen en de in het blauw gemarkeerde knoppen Meer informatie en Annuleren.](/intune-user-help/media/cp_ios_unenroll_after_1804_002.png)|


  Wanneer u uw apparaat bij Intune uitschrijft, gebeurt het volgende:

  - Het apparaat wordt niet meer in de bedrijfsportal weergegeven.

  - U kunt geen apps meer van de bedrijfsportal installeren.

  - Alle instellingen die op het apparaat zijn gewijzigd toen u dit hebt toegevoegd (bijvoorbeeld het uitschakelen van de camera of een vereiste wachtwoordlengte) zijn niet meer van toepassing.

  - Mogelijk hebt u vanaf het apparaat geen toegang meer tot een aantal bedrijfsresources, zoals bestandsshares of interne websites.

  - U kunt geen bedrijfs-apps en bedrijfsgegevens meer op het apparaat gebruiken.

  - Mogelijk kunt u geen verbinding meer met uw bedrijfsnetwerk maken met behulp van Wi-Fi of een virtueel particulier netwerk (VPN).

  - Bedrijfse-mailprofielen worden verwijderd van het apparaat.

  - Apparaten die alleen zijn geconfigureerd voor e-mail worden niet meer in de bedrijfsportal-app of op de website weergegeven.
  
  - Apps worden verwijderd. Gegevens van bedrijfs-apps worden verwijderd.

## <a name="removing-data-collected-by-the-company-portal-app"></a>Gegevens verwijderen die door de bedrijfsportal-app zijn verzameld

Er zijn drie locaties waar de bedrijfsportal lokale gegevens op uw apparaat opslaat.

- **Informatielogboeken**: standaardinformatie over de appactiviteit die door Microsoft wordt verzameld, bijvoorbeeld hoe lang de app was geopend of is gecrasht. Deze informatie wordt automatisch gewist wanneer u het apparaat uit de bedrijfsportal verwijdert.

- **Apple Analytics**: standaardinformatie over crashactiviteiten van de app die door Apple worden verzameld. Deze gegevens kunnen alleen worden verwijderd door de fabrieksinstellingen van uw apparaat te herstellen. Hiermee worden alle persoonsgegevens op uw apparaat gewist. Open hiervoor **Instellingen** > **Algemeen** > **Opnieuw instellen** > **Alle inhoud en instellingen wissen**.

- **Sleutelketen**: uw apparaat bewaart uw wachtwoorden en andere informatie die wordt gebruikt voor aanmeldingen in de sleutelketen. Microsoft-apps delen uw aanmeldgegevens in alle door Microsoft ontwikkelde apps die op uw apparaat staan, inclusief Microsoft Outlook en Microsoft Authenticator. Net zoals bij Apple Analytics kunnen deze gegevens alleen worden verwijderd door de fabrieksinstellingen van uw apparaat te herstellen. Hiermee worden alle persoonsgegevens op uw apparaat gewist. Open hiervoor **Instellingen** > **Algemeen** > **Opnieuw instellen** > **Alle inhoud en instellingen wissen**.


Nog hulp nodig? Neem contact op met het ondersteuningsteam van uw bedrijf. Controleer of de contactgegevens beschikbaar zijn op de [bedrijfsportalwebsite](https://go.microsoft.com/fwlink/?linkid=2010980).
