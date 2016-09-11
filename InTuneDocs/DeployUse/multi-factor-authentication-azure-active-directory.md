---
title: Multi-Factor Authentication met Azure AD| Microsoft Intune
description: Hoe u in Azure AD Multi-Factor Authentication vereist voor apparaatregistratie.
keywords: 
author: nbigman
manager: angerobe
ms.date: 08/17/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 47abdabd-dcd6-48d8-aade-3f3eefb92ee1
ROBOTS: NOINDEX,NOFOLLOW
translationtype: Human Translation
ms.sourcegitcommit: e7c680c43b8c9120755ec3c652cf7ec1cbcc3472
ms.openlocfilehash: d65846b09ac33fa18db037a6a2c05963607ef53f


---

# Multi-Factor Authentication voor Microsoft Intune

Intune integreert Multi-Factor Authentication (MFA) van Azure AD voor apparaatregistraties om u te helpen uw bedrijfsresources te beveiligen. MFA vereist naast gebruikersnamen en wachtwoorden, ook andere verificatiefactoren, zoals tekstverificatie. Dit wordt ondersteund voor apparaten met iOS, Android, Windows 8.1 of hoger en Windows Phone 8.1 of hoger.

> [!NOTE]
>
> Bij oudere versies van Configuration Manager (ouder dan versie 1610) ziet u nog steeds de MFA-instelling in de beheerconsole van Configuration Manager. Configureer MFA niet in de beheerconsole van Configuration Manager want dat werkt niet. Configureer MFA zoals in dit onderwerp wordt beschreven.

### Intune configureren zodat Multi-Factor Authentication wordt vereist bij het registreren van apparaten
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



<!--HONumber=Aug16_HO4-->


