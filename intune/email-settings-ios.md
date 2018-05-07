---
title: E-mailinstellingen voor iOS-apparaten in Microsoft Intune
titleSuffix: ''
description: Meer informatie over de Microsoft Intune-instellingen die u kunt gebruiken om e-mailinstellingen op apparaten met iOS te configureren.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 3/2/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0912ec4fdc77b51903b4febd54f9d16972b867a8
ms.sourcegitcommit: dbea918d2c0c335b2251fea18d7341340eafd673
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/26/2018
---
# <a name="email-profile-settings-in-microsoft-intune-for-devices-running-ios"></a>E-mailprofielinstellingen in Microsoft Intune voor apparaten met iOS 

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

In dit artikel ziet u de e-mailprofielinstellingen die u kunt configureren voor uw apparaten met iOS.

## <a name="email-settings"></a>E-mailinstellingen

- **E-mailserver**: de hostnaam van uw Exchange-server.
- **Accountnaam**: de weergavenaam voor het e-mailaccount die wordt weergegeven op de apparaten van de gebruikers.
- **Kenmerk van de gebruikersnaam van AAD**: dit is het kenmerk in Active Directory (AD) of Azure AD dat wordt gebruikt voor het genereren van de gebruikersnaam voor dit e-mailprofiel. Selecteer het **primaire SMTP-adres**, zoals **user1@contoso.com** of de **User Principal Name**, zoals **gebruiker1** of **user1@contoso.com**.
- **Kenmerk van het e-mailadres van AAD**: de manier waarop het e-mailadres voor de gebruiker op elk apparaat wordt gegenereerd. Selecteer **Primair SMTP-adres** om het primaire SMTP-adres te gebruiken voor aanmelding bij Exchange of gebruik **User Principal Name** om de volledige User Principal Name te gebruiken als het e-mailadres.
- **Verificatiemethode**: selecteer **Gebruikersnaam en wachtwoord** of **Certificaten** als verificatiemethode voor het e-mailprofiel. (**Opmerking**: Azure Multi-Factor Authentication wordt niet ondersteund).
    - Als u **Certificaat** hebt geselecteerd, selecteert u een SCEP- of PKCS-clientcertificaatprofiel dat u eerder hebt gemaakt en dat wordt gebruikt voor verificatie van de Exchange-verbinding.
- **SSL**: gebruik SSL-communicatie (Secure Sockets Layer) wanneer u e-mailberichten verzendt, e-mailberichten ontvangt en communiceert met de Exchange-server.
- **S/MIME**: verzend uitgaande e-mail met S/MIME-ondertekening.
    - Als u **Certificaat** hebt geselecteerd, selecteert u een SCEP- of PKCS-clientcertificaatprofiel dat u eerder hebt gemaakt en dat wordt gebruikt voor verificatie van de Exchange-verbinding.
    - Als u een SCEP-certificaat kiest, moet u controleren of er een geldig PFX-certificaat (Personal Information Exchange) is geïnstalleerd op het apparaat.
- **Aantal dagen e-mail voor synchronisatie**: kies het aantal dagen waarvoor u e-mail wilt synchroniseren of selecteer **Onbeperkt** om alle beschikbare e-mail te synchroniseren.
- **Toestaan dat berichten worden verplaatst naar andere e-mailaccounts**: selecteer deze optie om gebruikers toe te staan e-mailberichten te verplaatsen naar andere accounts die op hun apparaat zijn geconfigureerd.
- **Toestaan dat e-mails worden verzonden vanuit toepassingen van derden**: sta de gebruiker toe dit profiel te selecteren als het standaardaccount voor het verzenden van e-mail en sta toepassingen van derden toe e-mail te openen in de systeemeigen e-mail-app, om bijvoorbeeld bestanden als bijlagen aan e-mail toe te voegen.
- **Recent gebruikte e-mailadressen synchroniseren**: met deze functie wordt gebruikers toegestaan de lijst te synchroniseren met e-mailadressen die onlangs zijn gebruikt op het apparaat met de server.
