---
title: Multi-Factor Authentication met Azure AD| Microsoft Docs
description: Hoe u in Azure AD Multi-Factor Authentication vereist voor apparaatregistratie.
keywords: 
author: robstackmsft
ms.author: robstack
manager: angerobe
ms.date: 12/12/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 47abdabd-dcd6-48d8-aade-3f3eefb92ee1
ROBOTS: 
translationtype: Human Translation
ms.sourcegitcommit: 85462d6cb5e3dc6ce8e94fe8fd1bc1c1c2b6e4f3
ms.openlocfilehash: 6e20eca60886781ae884107a224245639c5f107c


---

# <a name="multi-factor-authentication-for-microsoft-intune"></a>Multi-Factor Authentication voor Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Intune integreert Multi-Factor Authentication (MFA) van Azure AD voor apparaatregistraties om u te helpen uw bedrijfsresources te beveiligen. MFA vereist naast gebruikersnamen en wachtwoorden, ook andere verificatiefactoren, zoals tekstverificatie. Dit wordt ondersteund voor apparaten met iOS, Android, Windows 8.1 of hoger en Windows Phone 8.1 of hoger.

> [!NOTE]
>
> Dit is de nieuwe werkwijze voor MFA in Intune. De oudere werkwijze, waarbij klanten worden gemigreerd, wordt beschreven in [Windows-apparaten beveiligen met meervoudige verificatie (multi-factor authentication, MFA)](protect-windows-devices-with-multi-factor-authentication.md).
>
> Bij oudere versies van Configuration Manager (ouder dan versie 1610) ziet u nog steeds de MFA-instelling in de beheerconsole van Configuration Manager. Configureer MFA niet in de beheerconsole van Configuration Manager want dat werkt niet. Configureer MFA zoals in dit onderwerp wordt beschreven.

### <a name="configuring-intune-to-require-multi-factor-authentication-at-device-enrollment"></a>Intune configureren zodat Multi-Factor Authentication wordt vereist bij het registreren van apparaten
Als u MFA wilt vereisten bij het registreren van apparaten, volgt u deze stappen:

1. Meld u met uw beheerdersreferenties aan bij [Microsoft Azure Portal](https://manage.windowsazure.com).
2. Kies uw tenant.
2. Selecteer het tabblad **Toepassingen**. U ziet een lijst met services waarvoor u Azure AD-beveiligingsfuncties kunt configureren.
3. Kies **Microsoft Intune-inschrijving**.
4. Kies **Configureren**. 
5. Onder **Multi-Factor Authentication en locatie gebaseerde toegangsregels** kunt u:
    
    -  De toegangsregels inschakelen
    -  Kies of u de regels wilt toepassen op alle gebruikers of alleen op specifieke Azure AD-beveiligingsgroepen.
    -  Vereis Multi-Factor Authentication voor alle apparaatregistraties.
    -  Vereis Multi-Factor Authentication voor registraties waarbij het apparaat niet op het werk is.
    -  Kies **Toegang tot bedrijfsresources blokkeren** om te voorkomen dat apparaten worden geregistreerde wanneer ze niet zijn verbonden met het bedrijfsnetwerk. 
4. U kunt ook klikken op de koppeling om **uw werknetwerklocatie te definiëren/bewerken** om de netwerkverbindingsvereisten te configureren voor apparaatregistratie.

> [!IMPORTANT]
> 
> Configureer geen **op het apparaat gebaseerde toegangsregels** voor Microsoft Intune-registratie.



<!--HONumber=Dec16_HO3-->


