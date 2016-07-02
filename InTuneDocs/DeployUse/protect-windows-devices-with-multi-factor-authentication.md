---
title: Windows-apparaten beveiligen met meervoudige verificatie | Microsoft Intune
description: 
keywords: 
author: Nbigman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9b4f197d-bc10-4bee-91c9-19bcc8287d36
ms.reviewer: vinaybha
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 2023d7bc1d35b423a216ece195cdca9a6a542446
ms.openlocfilehash: 15e546b93c2a3aff551efa36ac80ff212ada5812


---

# Protect Windows devices with multi-factor authentication
Microsoft Intune integreert meervoudige verificatie (multi-factor authentication, MFA) om te helpen uw bedrijfsbronnen te beveiligen. MFA vereist verificatiefactoren zoals tekstverificatie naast gebruikersnamen en wachtwoorden. Intune ondersteunt het gebruik van MFA tijdens registratie van Windows 8.1 of hoger, Windows Phone 8.1 en Windows 10 op desktopapparaten en mobiele apparaten. 

## Vereisten voor lokale infrastructuur voor ADFS MFA
Als u Multi-Factor Authentication wilt instellen, hebt u nodig:

-   **Een Active Directory-domein waaraan de ADFS-server is gekoppeld.**

-   **ADFS-server (Active Directory Federation Services) die is geconfigureerd voor MFA.** Een server met Windows Server 2012 R2 die is ingesteld als ADFS-server. Zie voor meer informatie: [Cloud en on-premises bronnen beveiligen met Azure Multi-Factor Authentication-Server met Windows Server 2012 R2 AD FS](https://azure.microsoft.com/en-us/documentation/articles/multi-factor-authentication-get-started-adfs-w2k12/)

Alle hierboven vermelde servers moeten voldoen aan de systeemvereisten die worden genoemd in [System Requirements and Installation Information for Windows Server 2012 R2](http://technet.microsoft.com/library/dn303418.aspx)(Systeemvereisten en installatie-informatie voor Windows Server 2012 R2).

#### MFA met Intune
Als uw organisatie een lokale IT-infrastructuur heeft met een Active Directory-domein met Active Directory Federation Services (ADFS), kunt u MFA configureren op de federatieserver en vervolgens MFA inschakelen voor registratie in Intune. Door MFA in Intune te configureren, hoeven gebruikers tijdens de inschrijving slechts één keer de verificatie te doorlopen en hebben zij daarna toegang tot bedrijfsbronnen zonder dat de MFA-procedure telkens hoeft te worden herhaald.

>[!NOTE]
>MFA kan per gebruiker of per groep worden verplicht op de ADFS-server.  

#### MFA zonder Intune
Als u MFA op uw federatieserver configureert, maar MFA niet inschakelt voor registratie in Intune, moeten gebruikers MFA telkens gebruiken wanneer ze toegang tot bedrijfsbronnen willen (niet alleen bij de registratie van het apparaat).

U kunt ook Azure Active Directory (AAD) MFA gebruiken om elke keer MFA te vereisen wanneer gebruikers toegang willen tot uw bedrijfsbronnen. Deze vereiste kan per gebruiker worden ingesteld. AAD MFA is een cloudservice waarvoor geen lokale IT-infrastructuur nodig is. Zie [Aan de slag met Azure Multi-Factor Authentication in de cloud](https://azure.microsoft.com/en-us/documentation/articles/multi-factor-authentication-get-started-cloud/) om te leren hoe u AAD MFA instelt.

## MFA voor ADFS verplicht stellen bij het inschrijven van Windows-apparaten
Zie [Manage Risk with Additional Multi-Factor Authentication for Sensitive Applications](http://technet.microsoft.com/library/dn280949.aspx)(Risicobeheer met aanvullende Multi-Factor Authentication voor gevoelige toepassingen) voor informatie over het inschakelen van MFA in ADFS.

## MFA voor apparaatregistratie in Intune instellen
>[!Important]  
>Schakel MFA in de tenant-omgeving of on-premises omgeving voor Azure AD in voordat u MFA verplicht stelt voor het inschrijven van Windows-apparaten bij Intune. Als u dit niet doet, ontvangen gebruikers een foutbericht wanneer ze hun Windows-apparaten proberen te registreren of wanneer ze hun apparaten proberen te koppelen aan Azure AD, indien automatische registratie tijdens het koppelen aan Azure AD is geconfigureerd.

1.  Klik in de Intune-beheerconsole op **Beheer** &gt; **Mobile Device Management** &gt; **Multi-factor Authentication**.

2.  Klik op **Multi-factor Authentication configureren** en vervolgens op **Multi-factor Authentication inschakelen**.




<!--HONumber=Jun16_HO4-->


