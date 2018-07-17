---
title: E-mailinstellingen toevoegen voor Android-apparaten en apparaten met een Android-werkprofiel in Microsoft Intune - Azure | Microsoft Docs
description: Maak een e-mailprofiel voor een apparaatconfiguratie waarbij gebruik wordt gemaakt van Exchange-servers en kenmerken worden opgehaald uit Azure Active Directory. U kunt tevens via Microsoft Intune SSL of SMIME inschakelen, gebruikers verifiëren met certificaten of gebruikersnaam/wachtwoord, en e-mail en planningen synchroniseren op Android-apparaten en apparaten met een Android-werkprofiel.
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
ms.openlocfilehash: 136ccb6079b16c13098c1dbd6ca49e8254c14f89
ms.sourcegitcommit: 98b444468df3fb2a6e8977ce5eb9d238610d4398
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/07/2018
ms.locfileid: "37905764"
---
# <a name="email-profile-settings-for-devices-running-android-and-android-enterprise---intune"></a>E-mailprofielinstellingen voor apparaten met Android en Android Enterprise - Intune

U kunt met de e-mailprofielinstellingen uw apparaten met Android configureren.

Als Intune-beheerder kunt u e-mailinstellingen maken en toewijzen aan de volgende Android-apparaten:

- Android Samsung Knox Standard
- Android Enterprise

## <a name="android-samsung-knox"></a>Android (Samsung Knox)

- **E-mailserver**: voer de hostnaam in van uw Exchange-server.
- **Accountnaam**: voer de weergavenaam in voor het e-mailaccount. Deze naam zien gebruikers op hun apparaat.
- **Het kenmerk gebruikersnaam van AAD**: deze naam is het kenmerk dat Intune uit Azure Active Directory (AAD) ophaalt. In Intune wordt de gebruikersnaam die wordt gebruikt door dit profiel dynamisch gegenereerd. Uw opties zijn:
  - **User Principal Name**: hiermee wordt de naam opgehaald, zoals `user1` of `user1@contoso.com`
  - **Gebruikersnaam**: hiermee wordt alleen de naam opgehaald, zoals `user1`
  - **sAM-accountnaam**: hiervoor is het domein vereist, zoals `domain\user1`. De sAM-accountnaam kan alleen worden gebruikt bij Android-apparaten. Android Enterprise wordt niet ondersteund.

    Voer ook in:  
    - **Bron van gebruikersdomeinnaam**: kies **AAD** (Azure Active Directory) of **Aangepast**.

      Voer, wanneer u ervoor kiest om de kenmerken op te halen van **AAD**, het volgende in:
      - **Kenmerk voor gebruikersdomeinnaam van AAD**: kies de optie om de **volledige domeinnaam** of het kenmerk **NetBIOS-naam** van de gebruiker op te halen

      Wanneer u ervoor kiest om **aangepaste** kenmerken te gebruiken, moet u het volgende invoeren:
      - **Te gebruiken aangepaste domeinnaam**: voer een waarde in die Intune voor de domeinnaam gebruikt, zoals `contoso.com` of `contoso`

- **Kenmerk van het e-mailadres van AAD**: kies op welke manier het e-mailadres voor de gebruiker wordt gegenereerd. Selecteer **User principal name** (`user1@contoso.com` of `user1`) om de volledige user principal name als e-mailadres te gebruiken, of **Primair SMTP-adres** (`user1@contoso.com`) om het primaire SMTP-adres te gebruiken om u aan te melden bij Exchange.

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

- **Inhoudstype voor synchronisatie**: selecteer de inhoudstypen die u wilt synchroniseren met apparaten. U hebt de volgende opties:
  - **Contactpersonen**
  - **Kalender**
  - **Taken**

## <a name="android-enterprise"></a>Android Enterprise

- **E-mail-app**: selecteer **Gmail** of **Nine Work**
- **E-mailserver**: de hostnaam van uw Exchange-server.
- **Kenmerk van de gebruikersnaam van AAD**: deze naam is het kenmerk in Active Directory (AD) of Azure AD dat wordt gebruikt voor het genereren van de gebruikersnaam voor dit e-mailprofiel. Selecteer het **primaire SMTP-adres**, zoals user1@contoso.com of de **User Principal Name**, zoals gebruiker1 of user1@contoso.com.
- **Kenmerk van het e-mailadres van AAD**: de manier waarop het e-mailadres voor de gebruiker op elk apparaat wordt gegenereerd. Selecteer **User Principal Name** om de volledige Principal-naam voor het e-mailadres of voor **Gebruikersnaam** te gebruiken.
- **Verificatiemethode**: selecteer **Gebruikersnaam en wachtwoord** of **Certificaten** als verificatiemethode voor het e-mailprofiel.
  - Als u **Certificaat** hebt geselecteerd, selecteert u een SCEP- of PKCS-clientcertificaatprofiel dat u eerder hebt gemaakt voor verificatie van de Exchange-verbinding.
- **SSL**: gebruik SSL-communicatie (Secure Sockets Layer) wanneer u e-mailberichten verzendt, e-mailberichten ontvangt en communiceert met de Exchange-server.
- **Aantal dagen e-mail voor synchronisatie**: kies het aantal dagen waarvoor u e-mail wilt synchroniseren of selecteer **Onbeperkt** om alle beschikbare e-mail te synchroniseren.
- **Inhoudstype voor synchronisatie** (alleen Nine Work): selecteer de inhoudstypen die u wilt synchroniseren met apparaten. U hebt de volgende opties:
  - **Contactpersonen**
  - **Kalender**
  - **Taken**

## <a name="next-steps"></a>Volgende stappen
[E-mailinstellingen configureren in Intune](email-settings-configure.md)
