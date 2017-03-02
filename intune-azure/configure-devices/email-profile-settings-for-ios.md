---
title: Intune-e-mailinstellingen voor iOS-apparaten | Intune Azure Preview | Microsoft Docs
description: 'Intune Azure Preview: meer informatie over de Intune-instellingen die u kunt gebruiken om e-mailverbindingen op iOS-apparaten te configureren.'
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9f0fa6af-3669-439a-bd0d-75d8b1a0b135
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b4d095506215b775d56d172e9aabae1737757310
ms.openlocfilehash: 186630903a606842406ff1d76115c1fa7d1c962e
ms.lasthandoff: 02/16/2017


---

# <a name="email-profile-settings-for-ios-devices-in-microsoft-intune"></a>E-mailprofielinstellingen voor iOS-apparaten in Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]



- **E-mailserver**: de hostnaam van uw Exchange-server.
- **Accountnaam**: de weergavenaam voor het e-mailaccount die wordt weergegeven op de apparaten van de gebruikers.
- **Kenmerk van de gebruikersnaam van AAD**: dit is het kenmerk in Active Directory (AD) of Azure AD dat wordt gebruikt voor het genereren van de gebruikersnaam voor dit e-mailprofiel. Selecteer het **primaire SMTP-adres**, zoals **user1@contoso.com** of de **User Principal Name**, zoals **gebruiker1** of **user1@contoso.com**.
- **Kenmerk van het e-mailadres van AAD**: de manier waarop het e-mailadres voor de gebruiker op elk apparaat wordt gegenereerd. Selecteer **Primair SMTP-adres** om het primaire SMTP-adres te gebruiken voor aanmelding bij Exchange of gebruik **User Principal Name** om de volledige User Principal Name te gebruiken als het e-mailadres.
- **Verificatiemethode**: selecteer **Gebruikersnaam en wachtwoord** of **Certificaten** als verificatiemethode voor het e-mailprofiel.
    - Als u **Certificaat** hebt geselecteerd, selecteert u een SCEP- of PKCS-clientcertificaatprofiel dat u eerder hebt gemaakt en dat wordt gebruikt voor verificatie van de Exchange-verbinding.
- **SSL**: gebruik SSL-communicatie (Secure Sockets Layer) wanneer u e-mailberichten verzendt, e-mailberichten ontvangt en communiceert met de Exchange-server.
- **S/MIME**: hiermee verzendt u uitgaande e-mail met S/MIME-versleuteling.
    - Als u **Certificaat** hebt geselecteerd, selecteert u een SCEP- of PKCS-clientcertificaatprofiel dat u eerder hebt gemaakt en dat wordt gebruikt voor verificatie van de Exchange-verbinding.
- **Aantal dagen e-mail voor synchronisatie**: kies het aantal dagen waarvoor u e-mail wilt synchroniseren of selecteer **Onbeperkt** om alle beschikbare e-mail te synchroniseren.
- **Toestaan dat berichten worden verplaatst naar andere e-mailaccounts**: selecteer deze optie om gebruikers toe te staan e-mailberichten te verplaatsen naar andere accounts die op hun apparaat zijn geconfigureerd.
- **Toestaan dat e-mails worden verzonden vanuit toepassingen van derden**: sta de gebruiker toe dit profiel te selecteren als het standaardaccount voor het verzenden van e-mail en sta toepassingen van derden toe e-mail te openen in de systeemeigen e-mail-app, om bijvoorbeeld bestanden als bijlagen aan e-mail toe te voegen.
- **Recent gebruikte e-mailadressen synchroniseren**: met deze functie wordt gebruikers toegestaan de lijst te synchroniseren met e-mailadressen die onlangs zijn gebruikt op het apparaat met de server.

