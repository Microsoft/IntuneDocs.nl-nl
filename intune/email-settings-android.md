---
title: Microsoft Intune-e-mailinstellingen voor apparaten met Android for Work en Android
titleSuffix: 
description: Meer informatie over de Microsoft Intune-instellingen die u kunt gebruiken om e-mailinstellingen te configureren op apparaten met Android en Android for Work.
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 3/6/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f989f9fafa4766ab71843c9dddef2bf3e18c5134
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/08/2018
---
# <a name="email-profile-settings-in-microsoft-intune-for-devices-running-android-and-android-for-work"></a>E-mailprofielinstellingen in Microsoft Intune voor apparaten met Android en Android for Work

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

In dit artikel ziet u de e-mailprofielinstellingen die u kunt configureren voor uw apparaten met Android.

Als Intune-beheerder kunt u e-mailinstellingen maken en toewijzen aan de volgende Android-apparaten:
- [Android Samsung Knox Standard](#android-samsung-knox-standard-email-settings)
- [Android for Work](#android-for-work-email-settings)

## <a name="android-samsung-knox-standard-email-settings"></a>E-mailinstellingen voor Android Samsung Knox Standard
- **E-mailserver**: de hostnaam van uw Exchange-server.
- **Accountnaam**: de weergavenaam voor het e-mailaccount die wordt weergegeven op de apparaten van de gebruikers.
- **Kenmerk van de gebruikersnaam van AAD**: deze naam is het kenmerk in Active Directory (AD) of Azure AD dat wordt gebruikt om de gebruikersnaam voor dit e-mailprofiel te genereren. Selecteer het **primaire SMTP-adres**, zoals user1@contoso.com of de **User Principal Name**, zoals gebruiker1 of user1@contoso.com.
- **Kenmerk van het e-mailadres van AAD**: de manier waarop het e-mailadres voor de gebruiker op elk apparaat wordt gegenereerd. Selecteer **Primair SMTP-adres** om het primaire SMTP-adres te gebruiken voor aanmelding bij Exchange of gebruik **User Principal Name** om de volledige Principal-naam te gebruiken als het e-mailadres.
- **Verificatiemethode**: selecteer **Gebruikersnaam en wachtwoord** of **Certificaten** als verificatiemethode voor het e-mailprofiel.
    - Als u **Certificaat** hebt geselecteerd, selecteert u een SCEP- of PKCS-clientcertificaatprofiel dat u eerder hebt gemaakt voor verificatie van de Exchange-verbinding.

### <a name="security-settings"></a>Beveiligingsinstellingen

- **SSL**: gebruik SSL-communicatie (Secure Sockets Layer) wanneer u e-mailberichten verzendt, e-mailberichten ontvangt en communiceert met de Exchange-server.
- **S/MIME**: hiermee verzendt u uitgaande e-mail met S/MIME-versleuteling.
    - Als u **Certificaat** hebt geselecteerd, selecteert u een SCEP- of PKCS-clientcertificaatprofiel dat u eerder hebt gemaakt voor verificatie van de Exchange-verbinding.

### <a name="synchronization-settings"></a>Synchronisatie-instellingen

- **Aantal dagen e-mail voor synchronisatie**: kies het aantal dagen waarvoor u e-mail wilt synchroniseren of selecteer **Onbeperkt** om alle beschikbare e-mail te synchroniseren.
- **Synchronisatieschema**: selecteer het schema dat voor apparaten wordt gebruikt om gegevens van de Exchange-server te synchroniseren. U kunt ook **Wanneer berichten binnenkomen** selecteren als u wilt dat de berichten meteen worden gesynchroniseerd wanneer ze binnenkomen. Als u wilt dat de gebruiker van het apparaat de synchronisatie zelf uitvoert, selecteert u **Handmatig**.

### <a name="content-sync-settings"></a>Instellingen voor inhoudssynchronisatie

- **Inhoudstype voor synchronisatie**: selecteer de inhoudstypen die u wilt synchroniseren met apparaten. U hebt de volgende opties:
    - **Contactpersonen**
    - **Kalender**
    - **Taken**

## <a name="android-for-work-email-settings"></a>E-mailinstellingen voor Android for Work

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
