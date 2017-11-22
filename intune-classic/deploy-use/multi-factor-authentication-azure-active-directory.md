---
title: Multi-Factor Authentication voor Intune-apparaatinschrijving
description: Hoe u in Azure AD Multi-Factor Authentication vereist voor apparaatregistratie.
keywords: 
author: arob98
ms.author: angrobe
manager: angerobe
ms.date: 02/17/2017
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 47abdabd-dcd6-48d8-aade-3f3eefb92ee1
ROBOTS: NOINDEX,NOFOLLOW
ms.custom: intune-classic
ms.openlocfilehash: 6d8a13033486256da171847646bd95fe77c978c8
ms.sourcegitcommit: f9bfdaed6037bd76f8715fa7ca15a3457d26370a
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/17/2017
---
# <a name="multi-factor-authentication-for-intune-device-enrollments"></a>Meervoudige verificatie voor apparaatinschrijvingen in Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Intune integreert Multi-Factor Authentication (MFA) van Azure AD voor apparaatregistraties om u te helpen uw bedrijfsresources te beveiligen.

MFA vereist twee of meer van de volgende verificatiemethoden: 

- Iets dat u weet (doorgaans een wachtwoord of pincode).
- Iets dat u hebt (een vertrouwd apparaat dat moeilijk kan worden gedupliceerd, zoals een telefoon).
- Iets dat u bent (biometrie).

MFA wordt ondersteund voor apparaten met iOS, Android, Windows 8.1 of hoger en Windows Phone 8.1 of hoger.

> [!NOTE]
> Bij oudere versies van Configuration Manager (ouder dan versie 1610) ziet u nog steeds de MFA-instelling in de beheerconsole van Configuration Manager. Configureer MFA niet in de beheerconsole van Configuration Manager want dat werkt niet. Configureer MFA zoals in dit onderwerp wordt beschreven.

### <a name="configure-intune-to-require-multi-factor-authentication-at-device-enrollment"></a>Intune configureren zodat Multi-Factor Authentication wordt vereist bij het registreren van apparaten
Voer de volgende stappen uit om MFA te vereisen wanneer een apparaat wordt geregistreerd:

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
