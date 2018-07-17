---
title: E-mailinstellingen toevoegen voor Windows 10-apparaten in Microsoft Intune - Azure | Microsoft Docs
description: Het e-mailprofiel van een apparaatconfiguratie maken die gebruikmaakt van Exchange-servers en kenmerken ophaalt uit Azure Active Directory. U kunt ook SSL inschakelen en e-mail en schema's synchroniseren op Windows 10-apparaten met behulp van Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 6/20/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 04834f21e5fd2f6ed0f7454988936397d3249987
ms.sourcegitcommit: 98b444468df3fb2a6e8977ce5eb9d238610d4398
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/07/2018
ms.locfileid: "37904965"
---
# <a name="email-profile-settings-for-devices-running-windows-10---intune"></a>E-mailprofielinstellingen voor apparaten waarop Windows 10 wordt uitgevoerd - Intune

U kunt met de e-mailprofielinstellingen uw apparaten met Windows 10 configureren.

- **E-mailserver**: voer de hostnaam in van uw Exchange-server.
- **Accountnaam**: voer de weergavenaam in voor het e-mailaccount. Deze naam zien gebruikers op hun apparaat.
- **Het kenmerk gebruikersnaam van AAD**: deze naam is het kenmerk dat Intune uit Azure Active Directory (AAD) ophaalt. In Intune wordt de gebruikersnaam die wordt gebruikt door dit profiel dynamisch gegenereerd. Uw opties zijn:
  - **User Principal Name**: haalt de naam op, zoals `user1` of `user1@contoso.com`
  - **Primair SMTP-adres**: haalt de naam op in de indeling van het e-mailadres, zoals `user1@contoso.com`
  - **sAM-accountnaam**: hiervoor is het domein vereist, zoals `domain\user1`.

    Voer ook in:  
    - **Bron van gebruikersdomeinnaam**: kies **AAD** (Azure Active Directory) of **Aangepast**.

      Voer, wanneer u ervoor kiest om de kenmerken op te halen van **AAD**, het volgende in:
      - **Kenmerk voor gebruikersdomeinnaam van AAD**: kies de optie om de **volledige domeinnaam** of het kenmerk **NetBIOS-naam** van de gebruiker op te halen

      Wanneer u ervoor kiest om **aangepaste** kenmerken te gebruiken,moet u het volgende invoeren:
      - **Te gebruiken aangepaste domeinnaam**: voer een waarde in die Intune voor de domeinnaamgebruikt, zoals `contoso.com` of `contoso`

- **Kenmerk van het e-mailadres van AAD**: kies op welke manier het e-mailadres voor de gebruiker gegenereerd. Selecteer **User principal name** (`user1@contoso.com` of `user1`) om de volledige user principal name als e-mailadres te gebruiken, of **Primair SMTP-adres** (`user1@contoso.com`) om het primaire SMTP-adres te gebruiken om u aan te melden bij Exchange.

## <a name="security-settings"></a>Beveiligingsinstellingen

- **SSL**: gebruik SSL-communicatie (Secure Sockets Layer) wanneer u e-mailberichten verzendt, e-mailberichten ontvangt en communiceert met de Exchange-server.

## <a name="synchronization-settings"></a>Synchronisatie-instellingen

- **Aantal dagen e-mail voor synchronisatie**: kies het aantal dagen waarvoor u e-mail wilt synchroniseren. Of selecteer **Onbeperkt** om alle beschikbare e-mail te synchroniseren.
- **Synchronisatieschema**: selecteer het schema voor apparaten om gegevens uit de Exchange-server te synchroniseren. U kunt ook **Wanneer berichten binnenkomen** selecteren als u wilt dat de berichten meteen worden gesynchroniseerd wanneer ze binnenkomen of **Handmatig** selecteren als u wilt dat de gebruiker van het apparaat de synchronisatie zelf in werking stelt.

## <a name="content-sync-settings"></a>Instellingen voor inhoudssynchronisatie

- **Inhoudstype voor synchronisatie**: selecteer de inhoudstypen die u wilt synchroniseren met apparaten. U hebt de volgende opties:
  - **Contactpersonen**
  - **Kalender**
  - **Taken**

## <a name="next-steps"></a>Volgende stappen
[E-mailinstellingen configureren in Intune](email-settings-configure.md)