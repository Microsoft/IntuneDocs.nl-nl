---
title: E-mailinstellingen voor Android Enterprise in Microsoft Intune - Azure | Microsoft Docs
description: Maak e-mailprofielen voor een apparaatconfiguratie waarbij gebruik wordt gemaakt van Exchange-servers en kenmerken worden opgehaald uit Azure Active Directory. U kunt via Microsoft Intune SSL of SMIME inschakelen, gebruikers verifiëren met certificaten of gebruikersnaam/wachtwoord en e-mail en planningen synchroniseren op apparaten met een Android-werkprofiel.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 08/07/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.reviewer: maholdaa
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 92d81e383a9964aaecbdd151397879236ffcb726
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 10/16/2019
ms.locfileid: "72493556"
---
# <a name="android-enterprise-device-settings-to-configure-email-authentication-and-synchronization-in-intune"></a>Android Enterprise-apparaatinstellingen voor het configureren van e-mail, verificatie en synchronisatie in Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

In dit artikel vindt u een overzicht en beschrijving van de verschillende e-mailinstellingen die u kunt beheren op Android Enterprise-apparaten. Gebruik deze instellingen voor het configureren van een e-mailserver, SSL voor het versleutelen van e-mailberichten en nog veel meer als onderdeel van uw beheeroplossing voor mobiele apparaten (MDM).

Als Intune-beheerder kunt u e-mailinstellingen maken en toewijzen aan Android Enterprise-apparaten in het werkprofiel.

Zie voor meer informatie over e-mailprofielen in Intune [Configure email settings](email-settings-configure.md) (E-mailinstellingen configureren).

## <a name="before-you-begin"></a>Voordat u begint

Een [configuratie profiel](email-settings-configure.md#create-a-device-profile) voor een apparaat maken (Kies het werk profiel) of een [app-configuratie beleid](../apps/app-configuration-policies-use-android.md)maken.

## <a name="android-enterprise"></a>Android Enterprise

- **E-mail-app**: selecteer **Gmail** of **Nine Work**
- **E-mailserver**: de hostnaam van uw Exchange-server. Voer bijvoorbeeld `outlook.office365.com` in.
- **Het kenmerk Gebruikersnaam van AAD**: deze naam is het kenmerk dat Intune ontvangt van Azure Active Directory (Azure AD). In Intune wordt de gebruikersnaam die wordt gebruikt door dit profiel dynamisch gegenereerd. Uw opties zijn:

  - **User Principal Name**: hiermee wordt de naam opgehaald, zoals `user1` of `user1@contoso.com`
  - **Gebruikersnaam**: hiermee wordt alleen de naam opgehaald, zoals `user1`

- **Het kenmerk e-mailadres van AAD**: deze naam is het e-mailadreskenmerk dat Intune uit Azure AD ophaalt. In Intune wordt het e-mailadres dat voor dit profiel wordt gebruikt, dynamisch gegenereerd. Uw opties zijn:
  - **User principal name**: Maakt gebruik van de volledige principal name, zoals `user1@contoso.com` of `user1`, als het e-mailadres.
  - **Primaire SMTP-adres**: Maakt gebruik van het primaire SMTP-adres, zoals `user1@contoso.com`, voor aanmelding bij Exchange.

- **Verificatiemethode**: selecteer **Gebruikersnaam en wachtwoord** of **Certificaten** als verificatiemethode voor het e-mailprofiel.
  - Als u **Certificaat** hebt geselecteerd, selecteert u een SCEP- of PKCS-clientcertificaatprofiel dat u eerder hebt gemaakt voor verificatie van de Exchange-verbinding.
- **SSL**: u kunt deze optie **inschakelen** om SSL-communicatie (Secure Sockets Layer) te gebruiken wanneer u e-mailberichten verstuurt, e-mailberichten ontvangt en communiceert met de Exchange-server.
- **Aantal dagen e-mail voor synchronisatie**: kies de tijdsperiode waarvoor u e-mailberichten wilt synchroniseren. Of selecteer **Onbeperkt** om alle beschikbare e-mail te synchroniseren.
- **Het inhoudstype voor synchronisatie** (uitsluitend Nine Work): kies welke gegevens u wilt synchroniseren op de apparaten. Uw opties zijn:
  - **Contacten**: kies **Inschakelen** zodat eindgebruikers contactpersonen naar hun apparaten kunnen synchroniseren.
  - **Agenda**: kies **Inschakelen** zodat eindgebruikers de agenda naar hun apparaten kunnen synchroniseren.
  - **Taken**: kies **Inschakelen** zodat eindgebruikers taken naar hun apparaten kunnen synchroniseren.

## <a name="next-steps"></a>Volgende stappen

[Het profiel toewijzen](device-profile-assign.md) en [de status ervan controleren](device-profile-monitor.md).

U kunt ook e-mailprofielen maken voor apparaten met [Android Samsung Knox](email-settings-android.md), [iOS](email-settings-ios.md), [Windows 10 en hoger](email-settings-windows-10.md) en [Windows Phone 8.1](email-settings-windows-phone-8-1.md).
