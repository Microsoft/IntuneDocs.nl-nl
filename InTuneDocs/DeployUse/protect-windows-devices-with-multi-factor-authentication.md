---
title: Meervoudige verificatie voor Windows | Microsoft Intune
description: Intune integreert meervoudige verificatie (multi-factor authentication, MFA) om te helpen uw bedrijfsbronnen te beveiligen.
keywords: 
author: Nbigman
manager: angrobe
ms.date: 09/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9b4f197d-bc10-4bee-91c9-19bcc8287d36
ms.reviewer: vinaybha
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 0ced62efd04803943cbbfd8cecef907409a03c0b
ms.openlocfilehash: 00d63fa55cd29c938dd082e2eff240f08319e01a


---

# Protect Windows devices with multi-factor authentication
Microsoft Intune integreert meervoudige verificatie (multi-factor authentication, MFA) om te helpen uw bedrijfsbronnen te beveiligen. MFA vereist naast gebruikersnamen en wachtwoorden, ook andere verificatiefactoren, zoals tekstverificatie. Intune ondersteunt het gebruik van MFA tijdens registratie van Windows 8.1 of hoger, Windows Phone 8.1 en Windows 10 op desktopapparaten en mobiele apparaten.

## Vereisten voor lokale infrastructuur voor ADFS MFA
Als u Multi-Factor Authentication wilt instellen, hebt u nodig:

-   Automatische registratie, zoals beschreven in [Windows-apparaatbeheer instellen](set-up-windows-device-management-with-microsoft-intune.md).
-   **Een Active Directory-domein waaraan de ADFS-server is gekoppeld.**

-   **ADFS-server (Active Directory Federation Services) die is geconfigureerd voor MFA.** Een server waarop Windows Server 2012 R2 wordt uitgevoerd en die is ingesteld als een ADFS-server. Zie voor meer informatie: [Cloud en on-premises bronnen beveiligen met Azure Multi-Factor Authentication-Server met Windows Server 2012 R2 AD FS](https://azure.microsoft.com/en-us/documentation/articles/multi-factor-authentication-get-started-adfs-w2k12/)

De servers moeten voldoen aan de systeemvereisten in [Systeemvereisten en installatie-informatie voor Windows Server 2012 R2](http://technet.microsoft.com/library/dn303418.aspx).

 


#### MFA met Intune
Als uw organisatie een lokale IT-infrastructuur heeft met een Active Directory-domein met Active Directory Federation Services (ADFS), kunt u MFA instellen op de federatieserver en vervolgens MFA inschakelen voor inschrijving in Intune. Als u MFA in Intune instelt, hoeven gebruikers tijdens de inschrijving slechts één keer de verificatieprocedure te doorlopen en hebben zij daarna toegang tot bedrijfsbronnen zonder dat de MFA-procedure telkens hoeft te worden herhaald.

>[!NOTE]
>MFA kan per gebruiker of per groep worden verplicht op de ADFS-server.  

#### MFA zonder Intune
Als u MFA op uw federatieserver instelt, maar MFA niet inschakelt voor inschrijving in Intune, moeten gebruikers MFA telkens gebruiken wanneer ze toegang tot bedrijfsbronnen willen (en niet alleen bij de inschrijving van het apparaat).

U kunt ook Azure Active Directory (Azure AD) MFA gebruiken om elke keer per gebruiker MFA te vereisen wanneer gebruikers toegang willen tot uw bedrijfsbronnen. Azure AD MFA is een cloudservice waarvoor geen lokale IT-infrastructuur nodig is. Zie [Aan de slag met Azure Multi-Factor Authentication in de cloud](https://azure.microsoft.com/en-us/documentation/articles/multi-factor-authentication-get-started-cloud/) om te leren hoe u Azure AD MFA instelt.

## MFA voor ADFS verplicht stellen bij het inschrijven van Windows-apparaten
Zie [Manage Risk with Additional Multi-Factor Authentication for Sensitive Applications](http://technet.microsoft.com/library/dn280949.aspx)(Risicobeheer met aanvullende Multi-Factor Authentication voor gevoelige toepassingen) voor informatie over het inschakelen van MFA in ADFS.

## MFA voor apparaatregistratie in Intune instellen
>[!Important]  
>Schakel MFA in de tenant-omgeving of on-premises omgeving voor Azure AD in voordat u MFA verplicht stelt voor het inschrijven van Windows-apparaten bij Intune. Als u dit niet doet, krijgen gebruikers een foutbericht wanneer ze hun Windows-apparaten proberen te in te schrijven of proberen te koppelen aan Azure AD, indien automatische inschrijving tijdens het koppelen aan Azure AD is ingesteld.

1.  Kies **Beheer** &gt; **Mobile Device Management** &gt; **Multi-Factor Authentication** in de Intune-beheerconsole.

2.  Kies **Multi-factor Authentication configureren** en vervolgens **Multi-factor Authentication inschakelen**.



<!--HONumber=Sep16_HO3-->


