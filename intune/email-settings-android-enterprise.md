---
title: E-mailinstellingen voor Android Enterprise in Microsoft Intune - Azure | Microsoft Docs
description: Maak e-mailprofielen voor een apparaatconfiguratie waarbij gebruik wordt gemaakt van Exchange-servers en kenmerken worden opgehaald uit Azure Active Directory. U kunt via Microsoft Intune SSL of SMIME inschakelen, gebruikers verifiëren met certificaten of gebruikersnaam/wachtwoord en e-mail en planningen synchroniseren op apparaten met een Android-werkprofiel.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/10/2019
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: b6c6c6e3e999e44ad6a07b4d8bdc1ddf9c400cf7
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 03/14/2019
ms.locfileid: "57565448"
---
# <a name="android-enterprise-device-settings-to-configure-email-authentication-and-synchronization-in-intune"></a>Android Enterprise-apparaatinstellingen voor het configureren van e-mail, verificatie en synchronisatie in Intune

In dit artikel vindt u een overzicht en beschrijving van de verschillende e-mailinstellingen die u kunt beheren op Android Enterprise-apparaten. Gebruik deze instellingen voor het configureren van een e-mailserver, SSL voor het versleutelen van e-mailberichten en nog veel meer als onderdeel van uw beheeroplossing voor mobiele apparaten (MDM).

Als Intune-beheerder kunt u e-mailinstellingen maken en toewijzen aan Android Enterprise-apparaten in het werkprofiel.

Zie voor meer informatie over e-mailprofielen in Intune [Configure email settings](email-settings-configure.md) (E-mailinstellingen configureren).

## <a name="before-you-begin"></a>Voordat u begint

[Maak een apparaatconfiguratieprofiel](email-settings-configure.md#create-a-device-profile) en kies het werkprofiel.

## <a name="android-enterprise"></a>Android Enterprise

- **E-mail-app**: selecteer **Gmail** of **Nine Work**
- **E-mailserver**: de hostnaam van uw Exchange-server. Voer bijvoorbeeld `outlook.office365.com` in.
- **Het kenmerk Gebruikersnaam van AAD**: deze naam is het kenmerk dat Intune ontvangt van Azure Active Directory (Azure AD). In Intune wordt de gebruikersnaam die wordt gebruikt door dit profiel dynamisch gegenereerd. Uw opties zijn:

  - **User Principal Name**: hiermee wordt de naam opgehaald, zoals `user1` of `user1@contoso.com`
  - **Gebruikersnaam**: hiermee wordt alleen de naam opgehaald, zoals `user1`

- **E-mailadreskenmerk van AAD**: deze naam is het e-kenmerk dat Intune uit Azure AD ophaalt. In Intune wordt het e-mailadres dat voor dit profiel wordt gebruikt, dynamisch gegenereerd. Uw opties zijn:
  - **User principal name**: Maakt gebruik van de volledige principal name, zoals `user1@contoso.com` of `user1`, als het e-mailadres.
  - **Primair SMTP-adres**: maakt gebruik van het primaire SMTP-adres, zoals `user1@contoso.com`, zich aanmelden bij Exchange.

- **Verificatiemethode**: selecteer **Gebruikersnaam en wachtwoord** of **Certificaten** als verificatiemethode voor het e-mailprofiel.
  - Als u **Certificaat** hebt geselecteerd, selecteert u een SCEP- of PKCS-clientcertificaatprofiel dat u eerder hebt gemaakt voor verificatie van de Exchange-verbinding.
- **SSL**: u kunt deze optie **inschakelen** om SSL-communicatie (Secure Sockets Layer) te gebruiken wanneer u e-mailberichten verstuurt, e-mailberichten ontvangt en communiceert met de Exchange-server.
- **Aantal dagen e-mail om te synchroniseren**: Kies de tijdsduur van e-mailbericht dat u wilt synchroniseren. Of selecteer **Onbeperkt** om alle beschikbare e-mail te synchroniseren.
- **Inhoudstype voor synchronisatie** (alleen Nine Work): Kies welke gegevens u wilt synchroniseren op de apparaten. Uw opties zijn:
  - **Contacten**: kies **Inschakelen** zodat eindgebruikers contactpersonen naar hun apparaten kunnen synchroniseren.
  - **Agenda**: kies **Inschakelen** zodat eindgebruikers de agenda naar hun apparaten kunnen synchroniseren.
  - **Taken**: kies **Inschakelen** zodat eindgebruikers taken naar hun apparaten kunnen synchroniseren.

## <a name="next-steps"></a>Volgende stappen

[Het profiel toewijzen](device-profile-assign.md) en [de status ervan controleren](device-profile-monitor.md).

U kunt ook e-mailprofielen maken voor apparaten met [Android Samsung Knox](email-settings-android.md), [iOS](email-settings-ios.md), [Windows 10 en hoger](email-settings-windows-10.md) en [Windows Phone 8.1](email-settings-windows-phone-8-1.md).
