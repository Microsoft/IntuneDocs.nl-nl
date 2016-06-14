---
# required metadata

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

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Windows-apparaten beveiligen met meervoudige verificatie
Microsoft Intune integreert meervoudige verificatie (multi-factor authentication, MFA) om te helpen uw bedrijfsbronnen te beveiligen. MFA vereist verificatiefactoren zoals tekstverificatie naast gebruikersnamen en wachtwoorden. Intune ondersteunt het gebruik van MFA tijdens registratie van Windows 8.1 of hoger, Windows Phone 8.1 en Windows 10 op desktopapparaten en mobiele apparaten. 

## Vereisten voor lokale infrastructuur voor ADFS MFA
Als u Multi-Factor Authentication wilt instellen, hebt u nodig:

-   **Een Active Directory-domein waaraan de ADFS-server is gekoppeld.**

-   **ADFS-server (Active Directory Federation Services) die is geconfigureerd voor MFA.** Een server met Windows Server 2012 R2 die is ingesteld als ADFS-server. Zie voor meer informatie: [Cloud en on-premises bronnen beveiligen met Azure Multi-Factor Authentication-Server met Windows Server 2012 R2 AD FS](https://azure.microsoft.com/en-us/documentation/articles/multi-factor-authentication-get-started-adfs-w2k12/)

Alle hierboven vermelde servers moeten voldoen aan de systeemvereisten die worden genoemd in [Systeemvereisten en installatie-informatie voor Windows Server 2012 R2](http://technet.microsoft.com/library/dn303418.aspx).

#### MFA met Intune
Als uw organisatie een lokale IT-infrastructuur heeft met een Active Directory-domein met Active Directory Federation Services (ADFS), kunt u MFA configureren op de federatieserver en vervolgens MFA inschakelen voor inschrijving in Intune. Door MFA in Intune te configureren, hoeven gebruikers tijdens de inschrijving slechts één keer de verificatie te doorlopen en hebben zij daarna toegang tot bedrijfsbronnen zonder dat de MFA-procedure telkens hoeft te worden herhaald.

>[!NOTE]
>MFA kan per gebruiker of per groep worden verplicht op de ADFS-server.  

#### MFA zonder Intune
Als u MFA op uw federatieserver configureert, maar MFA niet inschakelt voor inschrijving in Intune, moeten gebruikers MFA telkens gebruiken wanneer ze toegang tot bedrijfsbronnen willen (niet alleen bij de inschrijving van het apparaat).

U kunt ook Azure Active Directory (AAD) MFA gebruiken om elke keer MFA te vereisen wanneer gebruikers toegang willen tot uw bedrijfsbronnen. Deze vereiste kan per gebruiker worden ingesteld. AAD MFA is een cloudservice waarvoor geen lokale IT-infrastructuur nodig is. Zie [Aan de slag met Azure Multi-Factor Authentication in de cloud](https://azure.microsoft.com/en-us/documentation/articles/multi-factor-authentication-get-started-cloud/) om te leren hoe u AAD MFA instelt..

## MFA voor ADFS verplicht stellen bij het inschrijven van Windows-apparaten
Zie [Risicobeheer met aanvullende Multi-Factor Authentication voor gevoelige toepassingen](http://technet.microsoft.com/library/dn280949.aspx) voor informatie over het inschakelen van MFA in ADFS.

## MFA voor apparaatinschrijving in Intune instellen
>[!Important]  
>Schakel MFA in de tenant-omgeving of on-premises omgeving voor Azure AD in voordat u MFA verplicht stelt voor het inschrijven van Windows-apparaten bij Intune. Als u dit niet doet, ontvangen gebruikers een foutbericht wanneer ze hun Windows-apparaten proberen in te schrijven of wanneer ze hun apparaten proberen te koppelen aan Azure AD, indien automatische inschrijving tijdens het koppelen aan Azure AD is geconfigureerd.

1.  Klik in de Intune-beheerconsole op **Beheer** &gt; **Mobiele apparaten beheren** &gt; **Multi-factor authentication**.

2.  Klik op **Multi-factor Authentication configureren** en vervolgens op **Multi-factor Authentication inschakelen**.



<!--HONumber=May16_HO1-->


