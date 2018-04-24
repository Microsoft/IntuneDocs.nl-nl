---
title: Groepen maken om gebruikers en apparaten te organiseren | Microsoft Docs
description: Gebruikers en groepen voor uw Intune-abonnement maken
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/14/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5fdf98c8-fe67-4d7a-9837-ed1234348014
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: d8cb15d1b8c1c100f15084e43d2c3c4633fd64b5
ms.openlocfilehash: 434eea4244931f0708eb05cfc39d0c97b4936830
ms.lasthandoff: 03/09/2017


---


# <a name="create-groups-to-organize-users-and-devices"></a>Groepen maken om gebruikers en apparaten in te delen

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

In dit onderwerp wordt aan beheerders uitgelegd hoe ze gebruikersgroepen in Intune kunnen maken.

Groepen in Intune bieden u een hoge mate van flexibiliteit voor het beheren van uw apparaten en gebruikers. U kunt groepen aanpassen aan de behoeften van uw organisatie (bijvoorbeeld per geografische locatie, afdeling of hardware-eigenschappen) en gebruiken om een groot aantal administratieve taken uit te voeren, van het implementeren van beleidsregels voor een groep gebruikers tot het implementeren van toepassingen op een reeks apparaten.

## <a name="group-management-moving-to-azure-ad"></a>Groepsbeheer verplaatsen naar Azure AD

**Vanaf november 2016** beheren nieuwe accounts gebruikers- en apparaatgroepen in de Azure AD-portal (Active Directory). In december 2016 begint het Intune-productteam met de migratie van bestaande klanten naar de nieuwe op Azure AD gebaseerde groepsbeheermethode. Alle gebruikers- en apparaatgroepen zullen worden gemigreerd naar Azure AD-beveiligingsgroepen. De migraties worden pas uitgevoerd als we de invloed op uw dagelijkse werkzaamheden tot een minimum hebben weten te beperken. Naar verwachting zullen uw gebruikers er niets van merken. U ontvangt bericht van ons voordat we uw account gaan migreren.


>[!IMPORTANT]
>
>Als u de werkruimte Groepen opent in de Intune-portal en **Intune user groups are now managed as groups in Azure Active Directory** (Intune-gebruikersgroepen worden nu als groepen beheerd in Azure Active Directory) ziet staan met een koppeling naar de Azure Active Directory-portal, maakt u al gebruik van de *nieuwe* Azure AD-beveiligingsgroepen voor groepsbeheer in Intune. Zie [Groepen beheren in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-groups-create-azure-portal) voor meer informatie over het maken van groepen.
>
>Als u de koppeling naar de Azure AD-portal niet ziet, gebruikt u nog steeds de Intune-portal voor groepsbeheer.

## <a name="group-management-in-the-intune-portal"></a>Groepsbeheer in de Intune-portal

Apparaat- en gebruikersgroepen worden beide gemaakt in de werkruimte Groepen van de Intune-beheerconsole.

![Werkruimte Groepen op de beheerconsole](./media/groups.png)


> [!TIP]
> Zie [Groepen gebruiken voor het beheren van gebruikers en apparaten met Microsoft Intune](/intune/deploy-use/use-groups-to-manage-users-and-devices-with-microsoft-intune) voor meer informatie over het gebruik van groepen.


## <a name="create-a-device-group"></a>Een apparaatgroep maken
Gebruik apparaatgroepen om apps en updates te implementeren en andere onderdelen te configureren. Stel bijvoorbeeld de groep 'Mijn apparaten' in met behulp van de volgende stappen:

1.  Kies in de [Intune-beheerconsole](https://manage.microsoft.com/) **Groepen** > **Overzicht** > **Groep maken**.

2.  Typ 'Mijn apparaten' in **Groepsnaam**, selecteer **Alle apparaten** in de lijst voor de bovenliggende groep en kies **Volgende**.

3.  Selecteer **Alle apparaten** op de pagina **Lidmaatschapscriteria definiëren** om aan te geven dat de groep zowel mobiele apparaten als computers bevat.

4.  Kies **Volgende** op de pagina **Direct lidmaatschap opgeven**. Als u eerder een groep hebt gemaakt die niet alle apparaten bevat, en u specifieke apparaten wilt toevoegen aan de nieuwe groep, kunt u dat hier doen.

5.  Bekijk op de pagina **Samenvatting** de acties die zullen worden uitgevoerd en kies vervolgens **Voltooien**.

U vindt de nieuwe groep in de lijst **Groepen** en in de werkruimte **Groepen** onder **Alle apparaten**. Hier kunt u de groep ook bewerken of verwijderen.

## <a name="create-a-user-group"></a>Een gebruikersgroep maken
Gebruik gebruikersgroepen om software- en apparaatbeleid te implementeren. Stel bijvoorbeeld de groep 'Intune-gebruikers' in met behulp van de volgende stappen:

1.  Kies in de [Intune-beheerconsole](https://manage.microsoft.com/) **Groepen** > **Overzicht** > **Groep maken**.

2.  Typ 'Intune-gebruikers' in **Groepsnaam**, selecteer **Alle gebruikers** in de lijst voor de bovenliggende groep en kies **Volgende**.

3.  Stel op de pagina **Lidmaatschapscriteria definiëren** de optie **Groepslidmaatschap beginnen met** in op **Alle gebruikers in de bovenliggende groep**.

4.  Klik naast **Leden van deze beveiligingsgroepen uitsluiten** op **Bladeren** en selecteer vervolgens **Bedrijfsbeheerder**. Met deze uitsluiting kunt u de groep Intune-gebruikers beheren zonder dat dit van invloed is op het Company Administrator-account (ook wel bekend als de tenantbeheerder).

5.  Kies **Volgende** op de pagina **Direct lidmaatschap opgeven**. U hoeft hier verder niets te doen omdat u wilt dat de groep Intune-gebruikers alle gebruikers bevat, met uitzondering van de Company Administrator.

6.  Bekijk op de pagina **Samenvatting** de acties die zullen worden uitgevoerd en kies vervolgens **Voltooien**.

U vindt de nieuwe groep in de lijst **Groepen** en in de werkruimte **Groepen** onder **Alle gebruikers**. Hier kunt u de groep ook bewerken of verwijderen.

>[!div class="step-by-step"]

>[&larr; **Intune-licenties beheren**](.\start-with-a-paid-subscription-to-microsoft-intune-step-4.md)       [**Beleid en apps maken** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-6.md)  

