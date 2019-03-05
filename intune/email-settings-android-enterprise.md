---
title: E-mailinstellingen voor Android Enterprise in Microsoft Intune - Azure | Microsoft Docs
description: Maak e-mailprofielen voor een apparaatconfiguratie waarbij gebruik wordt gemaakt van Exchange-servers en kenmerken worden opgehaald uit Azure Active Directory. U kunt via Microsoft Intune SSL of SMIME inschakelen, gebruikers verifiëren met certificaten of gebruikersnaam/wachtwoord en e-mail en planningen synchroniseren op apparaten met een Android-werkprofiel.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/10/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: c6939ee44261215cf00805c975889d7d56c4e443
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/02/2019
ms.locfileid: "57236480"
---
# <a name="android-enterprise-device-settings-to-configure-email-authentication-and-synchronization-in-intune"></a>Android Enterprise-apparaatinstellingen voor het configureren van e-mail, verificatie en synchronisatie in Intune

In dit artikel vindt u een overzicht en beschrijving van de verschillende e-mailinstellingen die u kunt beheren op Android Enterprise-apparaten. Gebruik deze instellingen voor het configureren van een e-mailserver, SSL voor het versleutelen van e-mailberichten en nog veel meer als onderdeel van uw beheeroplossing voor mobiele apparaten (MDM).

Als Intune-beheerder kunt u e-mailinstellingen maken en toewijzen aan Android Enterprise-apparaten in het werkprofiel.

Zie voor meer informatie over e-mailprofielen in Intune [Configure email settings](email-settings-configure.md) (E-mailinstellingen configureren).

## <a name="before-you-begin"></a>Voordat u begint

[Maak een apparaatconfiguratieprofiel](email-settings-configure.md#create-a-device-profile) en kies het werkprofiel.

## <a name="android-enterprise"></a>Android Enterprise

- **E-mail-app**: Selecteer **Gmail** of **Nine Work**
- **E-mailserver**: Geef de hostnaam van uw Exchange-server op. Voer bijvoorbeeld `outlook.office365.com` in.
- **Het kenmerk Gebruikersnaam van AAD**: deze naam is het kenmerk dat Intune uit Azure Active Directory (Azure AD) ophaalt. In Intune wordt de gebruikersnaam die wordt gebruikt door dit profiel dynamisch gegenereerd. Uw opties zijn:

  - **User Principal Name**: Hiermee wordt de naam opgehaald, zoals `user1` of `user1@contoso.com`
  - **Gebruikersnaam**: Hiermee wordt alleen de naam opgehaald, zoals `user1`

- **Kenmerk van het e-mailadres van AAD**: Deze naam is het e-mailkenmerk dat Intune uit Azure AD ophaalt. In Intune wordt het e-mailadres dat voor dit profiel wordt gebruikt, dynamisch gegenereerd. Uw opties zijn:
  - **User Principal Name**:  Maakt gebruik van de volledige principal name, zoals `user1@contoso.com` of `user1`, als het e-mailadres.
  - **Primair SMTP-adres**: Maakt gebruik van het primaire SMTP-adres, zoals `user1@contoso.com`, voor aanmelding bij Exchange.

- **Verificatiemethode**: Selecteer **Gebruikersnaam en wachtwoord** of **Certificaten** als verificatiemethode voor het e-mailprofiel.
  - Als u **Certificaat** hebt geselecteerd, selecteert u een SCEP- of PKCS-clientcertificaatprofiel dat u eerder hebt gemaakt voor verificatie van de Exchange-verbinding.
- **SSL**: U kunt deze optie **inschakelen** om SSL-communicatie (Secure Sockets Layer) te gebruiken wanneer u e-mailberichten verstuurt, e-mailberichten ontvangt en communiceert met de Exchange-server.
- **Aantal dagen e-mail voor synchronisatie**: Kies hoeveel dagen e-mail u wilt synchroniseren. Of selecteer **Onbeperkt** om alle beschikbare e-mail te synchroniseren.
- **Inhoudstype voor synchronisatie** (alleen Nine Work): Kies welke gegevens u wilt synchroniseren op de apparaten. Uw opties zijn:
  - **Contactpersonen**: Kies **Inschakelen** zodat eindgebruikers contactpersonen naar hun apparaten kunnen synchroniseren.
  - **Agenda**: Kies **Inschakelen** zodat eindgebruikers de agenda naar hun apparaten kunnen synchroniseren.
  - **Taken**: Kies **Inschakelen** zodat eindgebruikers om het even welke taken naar hun apparaten kunnen synchroniseren.

## <a name="next-steps"></a>Volgende stappen

[Het profiel toewijzen](device-profile-assign.md) en [de status ervan controleren](device-profile-monitor.md).

U kunt ook e-mailprofielen maken voor apparaten met [Android Samsung Knox](email-settings-android.md), [iOS](email-settings-ios.md), [Windows 10 en hoger](email-settings-windows-10.md) en [Windows Phone 8.1](email-settings-windows-phone-8-1.md).
