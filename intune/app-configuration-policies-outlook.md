---
title: Outlook-instellingen voor iOS- en Android-apparaten in Microsoft Intune
description: Maak een configuratiebeleid voor Microsoft Outlook-instellingen op iOS- en Android-apparaten.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/04/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 7fc9f34bbd3d14ac4291582247b1e45169c2cccc
ms.sourcegitcommit: d92caead1d96151fea529c155bdd7b554a2ca5ac
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/06/2018
ms.locfileid: "48828727"
---
# <a name="microsoft-outlook-configuration-settings"></a>Configuratie-instellingen voor Microsoft Outlook 

Gebruik een configuratiebeleid voor Microsoft Outlook-instellingen op iOS- en Android-apparaten. 

Zie [App-configuratiebeleidsregels voor beheerde iOS-apparaten toevoegen](app-configuration-policies-use-ios.md) voor het maken van een app-configuratiebeleid voor beheerde iOS-apparaten. Zie [App-configuratiebeleidsregels toevoegen voor beheerde Android-apparaten](app-configuration-policies-use-android.md) voor het maken van een app-configuratiebeleid voor beheerde Android-apparaten. 

## <a name="configuration-settings"></a>Configuratie-instellingen

Bij het toevoegen van een configuratiebeleid in Intune kunt u specifieke instellingen voor het configureren van Microsoft Outlook instellen. In het deelvenster **Configuratie-instellingen** kunt u de configuratie van het e-mailaccount instellen.

### <a name="email-account-settings"></a>E-mailaccountinstellingen

De volgende configuratie-instellingen zijn specifiek voor Microsoft Outlook.

- **E-mailserver**: voer de hostnaam in van uw Exchange-server.
- **E-mailaccountnaam**: voer de weergavenaam in voor het e-mailaccount. Deze naam zien gebruikers op hun apparaat.
- **Het kenmerk gebruikersnaam van AAD**: deze naam is het kenmerk dat Intune uit Azure Active Directory (AAD) ophaalt. In Intune wordt de gebruikersnaam die wordt gebruikt door dit profiel dynamisch gegenereerd. Uw opties zijn:
  - **User Principal Name**: hiermee wordt de naam opgehaald, zoals `user1` of `user1@contoso.com`
  - **Primair SMTP-adres**: haalt de naam op in de indeling van het e-mailadres, zoals `user1@contoso.com`
  - **sAM-accountnaam**: hiervoor is het domein vereist, zoals `domain\user1`.

    Voer ook in:  
    - **Bron van gebruikersdomeinnaam**: kies **AAD** (Azure Active Directory) of **Aangepast**.

      Voer, wanneer u ervoor kiest om de kenmerken op te halen van **AAD**, het volgende in:
      - **Kenmerk voor gebruikersdomeinnaam van AAD**: kies de optie om de **volledige domeinnaam** of het kenmerk **NetBIOS-naam** van de gebruiker op te halen

      Wanneer u ervoor kiest om **aangepaste** kenmerken te gebruiken, moet u het volgende invoeren:
      - **Te gebruiken aangepaste domeinnaam**: voer een waarde in die Intune voor de domeinnaam gebruikt, zoals `contoso.com` of `contoso`

- **Kenmerk van het e-mailadres van AAD**: kies op welke manier het e-mailadres voor de gebruiker wordt gegenereerd. Selecteer **User principal name** (`user1@contoso.com` of `user1`) om de volledige user principal name als e-mailadres te gebruiken, of **Primair SMTP-adres** (`user1@contoso.com`) om het primaire SMTP-adres te gebruiken om u aan te melden bij Exchange.
- **Accountdomein** (optioneel): het domein van het account.

## <a name="next-steps"></a>Volgende stappen
[E-mailinstellingen configureren in Intune](email-settings-configure.md)

