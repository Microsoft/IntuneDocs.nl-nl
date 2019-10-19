---
title: E-mailinstellingen van Android in Microsoft Intune - Azure | Microsoft Docs
description: Maak e-mailprofielen voor een apparaatconfiguratie waarbij gebruik wordt gemaakt van Exchange-servers en kenmerken worden opgehaald uit Azure Active Directory. U kunt via Microsoft Intune SSL of SMIME inschakelen, gebruikers verifiëren met certificaten of gebruikersnaam/wachtwoord, en e-mail en planningen synchroniseren op Android Samsung Knox-apparaten.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/15/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 43a2b00ae824656621c8a586e41ba6425c69ed40
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 10/16/2019
ms.locfileid: "72506765"
---
# <a name="android-device-settings-to-configure-email-authentication-and-synchronization-in-intune"></a>Android-apparaatinstellingen voor het configureren van e-mail, verificatie en synchronisatie in Intune

Dit artikel bevat een overzicht en beschrijving van de verschillende e-mailinstellingen die u kunt beheren op Android Samsung Knox-apparaten in Intune. Gebruik deze instellingen voor het configureren van een e-mailserver, SSL voor het versleutelen van e-mailberichten en nog veel meer als onderdeel van uw beheeroplossing voor mobiele apparaten (MDM).

Als Intune-beheerder kunt u e-mailinstellingen maken en toewijzen aan Android Samsung Knox Standard-apparaten.

Zie voor meer informatie over e-mailprofielen in Intune [Configure email settings](email-settings-configure.md) (E-mailinstellingen configureren).

## <a name="before-you-begin"></a>Voordat u begint

[Maak een apparaatconfiguratieprofiel](email-settings-configure.md#create-a-device-profile).

## <a name="android-samsung-knox"></a>Android (Samsung Knox)

- **E-mailserver**: voer de hostnaam in van uw Exchange-server. Voer bijvoorbeeld `outlook.office365.com` in.
- **Accountnaam**: voer de weergavenaam in voor het e-mailaccount. Deze naam zien gebruikers op hun apparaat.
- **Het kenmerk Gebruikersnaam van AAD**: deze naam is het kenmerk dat Intune ontvangt van Azure Active Directory (Azure AD). In Intune wordt de gebruikersnaam die wordt gebruikt door dit profiel dynamisch gegenereerd. Uw opties zijn:
  - **User Principal Name**: hiermee wordt de naam opgehaald, zoals `user1` of `user1@contoso.com`
  - **Gebruikersnaam**: hiermee wordt alleen de naam opgehaald, zoals `user1`
  - **sAM-accountnaam**: hiervoor is het domein vereist, zoals `domain\user1`. De sAM-accountnaam wordt alleen gebruikt bij Android-apparaten.

    Voer ook in:  
    - **Bron van gebruikersdomeinnaam**: kies **AAD** (Azure Active Directory) of **Aangepast**.

      Voer, wanneer u ervoor kiest om de kenmerken op te halen van **AAD**, het volgende in:
      - **Kenmerk voor gebruikersdomeinnaam van AAD**: kies de optie om de **volledige domeinnaam** of het kenmerk **NetBIOS-naam** van de gebruiker op te halen

      Wanneer u ervoor kiest om **aangepaste** kenmerken te gebruiken, moet u het volgende invoeren:
      - **Te gebruiken aangepaste domeinnaam**: voer een waarde in die Intune voor de domeinnaam gebruikt, zoals `contoso.com` of `contoso`

- **Het kenmerk e-mailadres van AAD**: deze naam is het e-mailadreskenmerk dat Intune uit Azure AD ophaalt. In Intune wordt het e-mailadres dat voor dit profiel wordt gebruikt, dynamisch gegenereerd. Uw opties zijn:
  - **User principal name**: Maakt gebruik van de volledige principal name, zoals `user1@contoso.com` of `user1`, als het e-mailadres.
  - **Primaire SMTP-adres**: Maakt gebruik van het primaire SMTP-adres, zoals `user1@contoso.com`, voor aanmelding bij Exchange.

- **Verificatiemethode**: selecteer **Gebruikersnaam en wachtwoord** of **Certificaten** als verificatiemethode voor het e-mailprofiel.
  - Als u **Certificaat** hebt geselecteerd, selecteert u een SCEP- of PKCS-clientcertificaatprofiel dat u eerder hebt gemaakt voor verificatie van de Exchange-verbinding.

### <a name="security-settings"></a>Beveiligingsinstellingen

- **SSL**: gebruik SSL-communicatie (Secure Sockets Layer) wanneer u e-mailberichten verzendt, e-mailberichten ontvangt en communiceert met de Exchange-server.
- **S/MIME**: hiermee verzendt u uitgaande e-mails met S/MIME-versleuteling.
  - Als u **Certificaat** hebt geselecteerd, selecteert u een SCEP- of PKCS-clientcertificaatprofiel dat u eerder hebt gemaakt voor verificatie van de Exchange-verbinding.

### <a name="synchronization-settings"></a>Synchronisatie-instellingen

- **Aantal dagen e-mail voor synchronisatie**: kies het aantal dagen waarvoor u e-mail wilt synchroniseren of selecteer **Onbeperkt** om alle beschikbare e-mail te synchroniseren.
- **Synchronisatieschema**: selecteer het schema dat voor apparaten wordt gebruikt om gegevens van de Exchange-server te synchroniseren. U kunt ook **Wanneer berichten binnenkomen** selecteren als u wilt dat de berichten meteen worden gesynchroniseerd wanneer ze binnenkomen. Als u wilt dat de gebruiker van het apparaat de synchronisatie zelf uitvoert, selecteert u **Handmatig**.

### <a name="content-sync-settings"></a>Instellingen voor inhoudssynchronisatie

- **Inhoudstype voor synchronisatie**: selecteer de inhoudstypen die u wilt synchroniseren op de apparaten. **Niet geconfigureerd** zorgt ervoor dat deze instelling wordt uitgeschakeld. Wanneer deze optie is ingesteld op **Niet geconfigureerd** en een eindgebruiker synchronisatie op het apparaat inschakelt, wordt de synchronisatie uitgeschakeld wanneer het apparaat wordt gesynchroniseerd met Intune, omdat het beleid opnieuw wordt afgedwongen. 

  U kunt de volgende inhoud synchroniseren:  
  - **Contacten**: Kies **Inschakelen** zodat eindgebruikers contactpersonen naar hun apparaten kunnen synchroniseren.
  - **Agenda**: kies **Inschakelen** zodat eindgebruikers de agenda naar hun apparaten kunnen synchroniseren.
  - **Taken**: kies **Inschakelen** zodat eindgebruikers taken naar hun apparaten kunnen synchroniseren.

## <a name="next-steps"></a>Volgende stappen

[Het profiel toewijzen](device-profile-assign.md) en [de status ervan controleren](device-profile-monitor.md).

U kunt ook e-mailprofielen maken voor [Android Enterprise - werkprofiel](email-settings-android-enterprise.md), [iOS](email-settings-ios.md), [Windows 10 en hoger](email-settings-windows-10.md) en [Windows Phone 8.1](email-settings-windows-phone-8-1.md).
