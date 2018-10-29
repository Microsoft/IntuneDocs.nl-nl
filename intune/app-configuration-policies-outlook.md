---
title: Outlook-instellingen voor iOS- en Android-apparaten in Microsoft Intune
description: Maak een configuratiebeleid voor Microsoft Outlook-instellingen op iOS- en Android-apparaten.
keywords: ''
author: Erikre
ms.author: erikre
ms.reviewer: smithre4
manager: dougeby
ms.date: 10/04/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 24ed1a895dd3e4cad6111b40913b43fa9c6a3cec
ms.sourcegitcommit: 11bd3dbbc9dd762df7c6d20143f2171799712547
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/10/2018
ms.locfileid: "48903519"
---
# <a name="microsoft-outlook-configuration-settings"></a>Configuratie-instellingen voor Microsoft Outlook 

Gebruik een configuratiebeleid voor Microsoft Outlook-instellingen op iOS- en Android-apparaten. 

Zie [App-configuratiebeleidsregels voor beheerde iOS-apparaten toevoegen](app-configuration-policies-use-ios.md) voor het maken van een app-configuratiebeleid voor beheerde iOS-apparaten. Zie [App-configuratiebeleidsregels toevoegen voor beheerde Android-apparaten](app-configuration-policies-use-android.md) voor het maken van een app-configuratiebeleid voor beheerde Android-apparaten. 

## <a name="configuration-settings"></a>Configuratie-instellingen

Bij het toevoegen van een configuratiebeleid in Intune kunt u specifieke instellingen voor het configureren van Microsoft Outlook instellen. In het deelvenster **Configuratie-instellingen** kunt u de configuratie van het e-mailaccount instellen.

### <a name="basic-authentication-email-account-settings"></a>Instellingen voor basisverificatie van e-mailaccount
Outlook voor iOS en Android biedt Exchange-beheerders de mogelijkheid om accountconfiguraties te 'pushen' naar hun on-premises gebruikers die gebruikmaken van basisverificatie met het ActiveSync-protocol. Zie voor meer informatie [Account setup in Outlook for iOS and Android using Basic authentication](https://docs.microsoft.com/Exchange/clients/outlook-for-ios-and-android/account-setup) (Accounts instellen in Outlook voor iOS en Android met behulp van basisverificatie). Om configuratie van accountinstellingen in te schakelen, kunt u de volgende instellingen configureren:

- **E-mailserver**: voer de hostnaam van uw on-premises Exchange-server in (zoals mail.contoso.com).
- **E-mailaccountnaam**: voer de weergavenaam in voor het e-mailaccount. Deze naam zien gebruikers op hun apparaat.
- **Het kenmerk Gebruikersnaam van AAD**: deze naam is het kenmerk dat Intune ontvangt van Azure Active Directory (Azure AD). In Intune wordt de gebruikersnaam die wordt gebruikt door dit profiel dynamisch gegenereerd. Zijn uw opties:
  - **User Principal Name**: hiermee wordt de naam opgehaald, zoals `user1` of `user1@contoso.com`
  - **Primair SMTP-adres**: haalt de naam op in de indeling van het e-mailadres, zoals `user1@contoso.com`
- **Kenmerk van het e-mailadres van AAD**: kies op welke manier het e-mailadres voor de gebruiker wordt gegenereerd. Selecteer **User principal name** (`user1@contoso.com` of `user1`) om de volledige user principal name als e-mailadres te gebruiken, of **Primair SMTP-adres** (`user1@contoso.com`) om het primaire SMTP-adres te gebruiken om u aan te melden bij Exchange. We raden aan om **Primair SMTP-adres** te selecteren.
- **Accountdomein** (optioneel): het domein van het account.

## <a name="next-steps"></a>Volgende stappen
[E-mailinstellingen configureren in Intune](email-settings-configure.md)

