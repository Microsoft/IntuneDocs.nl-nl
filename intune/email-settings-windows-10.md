---
title: E-mailinstellingen toevoegen voor Windows 10-apparaten in Microsoft Intune - Azure | Microsoft Docs
description: Het e-mailprofiel van een apparaatconfiguratie maken die gebruikmaakt van Exchange-servers en kenmerken ophaalt uit Azure Active Directory. U kunt ook SSL inschakelen en e-mail en schema's synchroniseren op Windows 10-apparaten met behulp van Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/29/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: bf9581fe81aea3d2671da0adb2d37bbc203875c8
ms.sourcegitcommit: 4bd992da609b8bcc85edc2d64fe8128546aa4617
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/30/2019
ms.locfileid: "55303528"
---
# <a name="email-profile-settings-for-devices-running-windows-10---intune"></a>E-mailprofielinstellingen voor apparaten waarop Windows 10 wordt uitgevoerd - Intune

U kunt met de e-mailprofielinstellingen de Mail-app op uw apparaten met Windows 10 configureren.

- **E-mailserver**: Voer de hostnaam van uw Exchange-server in.
- **Accountnaam**: Voer de weergavenaam voor het e-mailaccount in. Deze naam zien gebruikers op hun apparaat.
- **Het kenmerk Gebruikersnaam van AAD**: Deze naam is het kenmerk dat Intune uit Azure Active Directory (AAD) ophaalt. In Intune wordt de gebruikersnaam die wordt gebruikt door dit profiel dynamisch gegenereerd. Uw opties zijn:
  - **User Principal Name**: Hiermee wordt de naam opgehaald, zoals `user1` of `user1@contoso.com`
  - **Primair SMTP-adres**: Hiermee haalt u de naam op in de indeling van het e-mailadres, zoals `user1@contoso.com`
  - **sAM-accountnaam**: Hiervoor is het domein vereist, zoals `domain\user1`.

    Voer ook in:  
    - **Bron van gebruikersdomeinnaam**: Kies **AAD** (Azure Active Directory) of **Aangepast**.

      Voer, wanneer u ervoor kiest om de kenmerken op te halen van **AAD**, het volgende in:
      - **Het kenmerk Gebruikersdomeinnaam van AAD**: Kies de optie om de **volledige domeinnaam** of het kenmerk **NetBIOS-naam** van de gebruiker op te halen

      Wanneer u ervoor kiest om **aangepaste** kenmerken te gebruiken, moet u het volgende invoeren:
      - **Te gebruiken aangepaste domeinnaam**: Voer een waarde in die Intune voor de domeinnaam gebruikt, zoals `contoso.com` of `contoso`

- **Kenmerk van het e-mailadres van AAD**: Kies op welke manier het e-mailadres voor de gebruiker wordt gegenereerd. Selecteer **User principal name** (`user1@contoso.com` of `user1`) om de volledige user principal name als e-mailadres te gebruiken, of **Primair SMTP-adres** (`user1@contoso.com`) om het primaire SMTP-adres te gebruiken om u aan te melden bij Exchange.

## <a name="security-settings"></a>Beveiligingsinstellingen

- **SSL**: Gebruik SSL-communicatie (Secure Sockets Layer) wanneer u e-mailberichten verzendt, e-mailberichten ontvangt en communiceert met de Exchange-server.

## <a name="synchronization-settings"></a>Synchronisatie-instellingen

- **Aantal dagen e-mail voor synchronisatie**: Kies het aantal dagen waarvoor u e-mail wilt synchroniseren. Of selecteer **Onbeperkt** om alle beschikbare e-mail te synchroniseren.
- **Synchronisatieschema**: Selecteer het schema voor apparaten om gegevens uit de Exchange-server te synchroniseren. U kunt ook **Wanneer berichten binnenkomen** selecteren als u wilt dat de berichten meteen worden gesynchroniseerd wanneer ze binnenkomen of **Handmatig** selecteren als u wilt dat de gebruiker van het apparaat de synchronisatie zelf in werking stelt.

## <a name="content-sync-settings"></a>Instellingen voor inhoudssynchronisatie

- **Inhoudstype voor synchronisatie**: Selecteer de inhoudstypen die u wilt synchroniseren met apparaten. U hebt de volgende opties:
  - **Contactpersonen**
  - **Kalender**
  - **Taken**

## <a name="next-steps"></a>Volgende stappen
[E-mailinstellingen configureren in Intune](email-settings-configure.md)
