---
title: E-mailinstellingen voor Android en Android Enterprise in Microsoft Intune - Azure | Microsoft Docs
description: Maak e-mailprofielen voor een apparaatconfiguratie waarbij gebruik wordt gemaakt van Exchange-servers en kenmerken worden opgehaald uit Azure Active Directory. U kunt via Microsoft Intune SSL of SMIME inschakelen, gebruikers verifiëren met certificaten of gebruikersnaam/wachtwoord, en e-mail en planningen synchroniseren op Android-apparaten en apparaten met een Android-werkprofiel.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/15/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.openlocfilehash: b96363d679a6f09327bf9a1b46421e786d1956a8
ms.sourcegitcommit: 912aee714432c4a1e8efeee253ca2be4f972adaa
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/15/2019
ms.locfileid: "54316879"
---
# <a name="android-and-android-enterprise-device-settings-to-configure-email-authentication-and-synchronization-in-intune"></a>Android- en Android Enterprise-apparaatinstellingen voor het configureren van e-mail, verificatie en synchronisatie in Intune

Dit artikel bevat een overzicht en beschrijving van de verschillende e-mailinstellingen die u kunt beheren op Android- en Android Enterprise-apparaten. Gebruik deze instellingen voor het configureren van een e-mailserver, SSL voor het versleutelen van e-mailberichten en nog veel meer als onderdeel van uw beheeroplossing voor mobiele apparaten (MDM).

Als Intune-beheerder kunt u e-mailinstellingen maken en toewijzen aan de volgende Android-apparaten:

- Android Samsung Knox Standard
- Android Enterprise

## <a name="before-you-begin"></a>Voordat u begint

[Maak een apparaatconfiguratieprofiel](email-settings-configure.md).

## <a name="android-samsung-knox"></a>Android (Samsung Knox)

- **E-mailserver**: Voer de hostnaam van uw Exchange-server in.
- **Accountnaam**: Voer de weergavenaam voor het e-mailaccount in. Deze naam zien gebruikers op hun apparaat.
- **Het kenmerk Gebruikersnaam van AAD**: Deze naam is het kenmerk dat Intune uit Azure Active Directory (AAD) ophaalt. In Intune wordt de gebruikersnaam die wordt gebruikt door dit profiel dynamisch gegenereerd. Uw opties zijn:
  - **User Principal Name**: Hiermee wordt de naam opgehaald, zoals `user1` of `user1@contoso.com`
  - **Gebruikersnaam**: Hiermee wordt alleen de naam opgehaald, zoals `user1`
  - **sAM-accountnaam**: Hiervoor is het domein vereist, zoals `domain\user1`. De sAM-accountnaam kan alleen worden gebruikt bij Android-apparaten. Android Enterprise wordt niet ondersteund.

    Voer ook in:  
    - **Bron van gebruikersdomeinnaam**: Kies **AAD** (Azure Active Directory) of **Aangepast**.

      Voer, wanneer u ervoor kiest om de kenmerken op te halen van **AAD**, het volgende in:
      - **Het kenmerk Gebruikersdomeinnaam van AAD**: Kies de optie om de **volledige domeinnaam** of het kenmerk **NetBIOS-naam** van de gebruiker op te halen

      Wanneer u ervoor kiest om **aangepaste** kenmerken te gebruiken, moet u het volgende invoeren:
      - **Te gebruiken aangepaste domeinnaam**: Voer een waarde in die Intune voor de domeinnaam gebruikt, zoals `contoso.com` of `contoso`

- **Kenmerk van het e-mailadres van AAD**: Kies op welke manier het e-mailadres voor de gebruiker wordt gegenereerd. Selecteer **User principal name** (`user1@contoso.com` of `user1`) om de volledige user principal name als e-mailadres te gebruiken, of **Primair SMTP-adres** (`user1@contoso.com`) om het primaire SMTP-adres te gebruiken om u aan te melden bij Exchange.

- **Verificatiemethode**: Selecteer **Gebruikersnaam en wachtwoord** of **Certificaten** als verificatiemethode voor het e-mailprofiel.
  - Als u **Certificaat** hebt geselecteerd, selecteert u een SCEP- of PKCS-clientcertificaatprofiel dat u eerder hebt gemaakt voor verificatie van de Exchange-verbinding.

### <a name="security-settings"></a>Beveiligingsinstellingen

- **SSL**: Gebruik SSL-communicatie (Secure Sockets Layer) wanneer u e-mailberichten verzendt, e-mailberichten ontvangt en communiceert met de Exchange-server.
- **S/MIME**: Verzend uitgaande e-mail met S/MIME-versleuteling.
  - Als u **Certificaat** hebt geselecteerd, selecteert u een SCEP- of PKCS-clientcertificaatprofiel dat u eerder hebt gemaakt voor verificatie van de Exchange-verbinding.

### <a name="synchronization-settings"></a>Synchronisatie-instellingen

- **Aantal dagen e-mail voor synchronisatie**: Kies het aantal dagen waarvoor u e-mail wilt synchroniseren of selecteer **Onbeperkt** om alle beschikbare e-mail te synchroniseren.
- **Synchronisatieschema**: Selecteer het schema dat voor apparaten wordt gebruikt om gegevens van de Exchange-server te synchroniseren. U kunt ook **Wanneer berichten binnenkomen** selecteren als u wilt dat de berichten meteen worden gesynchroniseerd wanneer ze binnenkomen. Als u wilt dat de gebruiker van het apparaat de synchronisatie zelf uitvoert, selecteert u **Handmatig**.

### <a name="content-sync-settings"></a>Instellingen voor inhoudssynchronisatie

- **Inhoudstype voor synchronisatie**: Selecteer de inhoudstypen die u wilt synchroniseren op de apparaten. **Niet geconfigureerd** zorgt ervoor dat deze instelling wordt uitgeschakeld. Wanneer deze optie is ingesteld op **Niet geconfigureerd** en een eindgebruiker synchronisatie op het apparaat inschakelt, wordt de synchronisatie uitgeschakeld wanneer het apparaat wordt gesynchroniseerd met Intune, omdat het beleid opnieuw wordt afgedwongen. 

  U kunt de volgende inhoud synchroniseren: 
  - **Contactpersonen**
  - **Kalender**
  - **Taken**

## <a name="android-enterprise"></a>Android Enterprise

- **E-mail-app**: Selecteer **Gmail** of **Nine Work**
- **E-mailserver**: Geef de hostnaam van uw Exchange-server op.
- **Het kenmerk Gebruikersnaam van AAD**: Deze naam is het kenmerk in Active Directory (AD) of Azure AD dat wordt gebruikt voor het genereren van de gebruikersnaam voor dit e-mailprofiel. Selecteer het **primaire SMTP-adres**, zoals user1@contoso.com of de **User Principal Name**, zoals gebruiker1 of user1@contoso.com.
- **Kenmerk van het e-mailadres van AAD**: Hoe het e-mailadres voor de gebruiker op elk apparaat wordt gegenereerd. Selecteer **User Principal Name** om de volledige Principal-naam voor het e-mailadres of voor **Gebruikersnaam** te gebruiken.
- **Verificatiemethode**: Selecteer **Gebruikersnaam en wachtwoord** of **Certificaten** als verificatiemethode voor het e-mailprofiel.
  - Als u **Certificaat** hebt geselecteerd, selecteert u een SCEP- of PKCS-clientcertificaatprofiel dat u eerder hebt gemaakt voor verificatie van de Exchange-verbinding.
- **SSL**: Gebruik SSL-communicatie (Secure Sockets Layer) wanneer u e-mailberichten verzendt, e-mailberichten ontvangt en communiceert met de Exchange-server.
- **Aantal dagen e-mail voor synchronisatie**: Kies het aantal dagen waarvoor u e-mail wilt synchroniseren of selecteer **Onbeperkt** om alle beschikbare e-mail te synchroniseren.
- **Inhoudstype voor synchronisatie** (alleen Nine Work): Selecteer de inhoudstypen die u wilt synchroniseren op de apparaten. **Niet geconfigureerd** zorgt ervoor dat deze instelling wordt uitgeschakeld. Wanneer deze optie is ingesteld op **Niet geconfigureerd** en een eindgebruiker synchronisatie op het apparaat inschakelt, wordt de synchronisatie uitgeschakeld wanneer het apparaat wordt gesynchroniseerd met Intune, omdat het beleid opnieuw wordt afgedwongen. 

  U kunt de volgende inhoud synchroniseren: 
  - **Contactpersonen**
  - **Kalender**
  - **Taken**

## <a name="next-steps"></a>Volgende stappen
[E-mailinstellingen configureren in Intune](email-settings-configure.md)
