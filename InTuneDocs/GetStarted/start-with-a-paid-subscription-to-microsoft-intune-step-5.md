---
title: Groepen maken om gebruikers en apparaten te organiseren | Microsoft Intune
description: Gebruikers en groepen voor uw Intune-abonnement maken
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 08/29/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5fdf98c8-fe67-4d7a-9837-ed1234348014
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 0d422b421c3716ad576c4fc565b181dec28c947e
ms.openlocfilehash: 5972910bf64274685298877da9bf4a0a6c5fd626


---


# Groepen maken om gebruikers en apparaten in te delen
Groepen in Intune bieden u een hoge mate van flexibiliteit voor het beheren van uw apparaten en gebruikers. U kunt groepen aanpassen aan de behoeften van uw organisatie (bijvoorbeeld per geografische locatie, afdeling of hardware-eigenschappen) en gebruiken om een groot aantal administratieve taken uit te voeren, van het implementeren van beleidsregels voor een groep gebruikers tot het implementeren van toepassingen op een reeks apparaten.

Apparaat- en gebruikersgroepen worden beide gemaakt in de werkruimte Groepen van de Intune-beheerconsole.

![Werkruimte Groepen op de beheerconsole](./media/groups.png)


> [!TIP]
> Zie [Groepen gebruiken voor het beheren van gebruikers en apparaten met Microsoft Intune](/intune/deploy-use/use-groups-to-manage-users-and-devices-with-microsoft-intune) voor meer informatie over het gebruik van groepen.


## Een apparaatgroep maken
Gebruik apparaatgroepen om apps en updates te implementeren en andere onderdelen te configureren. Stel bijvoorbeeld de groep 'Mijn apparaten' in met behulp van de volgende stappen:

1.  Kies in de [Intune-beheerconsole](https://manage.microsoft.com/) **Groepen** > **Overzicht** > **Groep maken**.

2.  Typ 'Mijn apparaten' in **Groepsnaam**, selecteer **Alle apparaten** in de lijst voor de bovenliggende groep en kies **Volgende**.

3.  Selecteer **Alle apparaten** op de pagina **Lidmaatschapscriteria definiëren** om aan te geven dat de groep zowel mobiele apparaten als computers bevat.

4.  Kies **Volgende** op de pagina **Direct lidmaatschap opgeven**. Als u eerder een groep hebt gemaakt die niet alle apparaten bevat, en u specifieke apparaten wilt toevoegen aan de nieuwe groep, kunt u dat hier doen.

5.  Bekijk op de pagina **Samenvatting** de acties die zullen worden uitgevoerd en kies vervolgens **Voltooien**.

U vindt de nieuwe groep in de lijst **Groepen** en in de werkruimte **Groepen** onder **Alle apparaten**. Hier kunt u de groep ook bewerken of verwijderen.

## Een gebruikersgroep maken
Gebruik gebruikersgroepen om software- en apparaatbeleid te implementeren. Stel bijvoorbeeld de groep 'Intune-gebruikers' in met behulp van de volgende stappen:

1.  Kies in de [Intune-beheerconsole](https://manage.microsoft.com/) **Groepen** > **Overzicht** > **Groep maken**.

2.  Typ 'Intune-gebruikers' in **Groepsnaam**, selecteer **Alle gebruikers** in de lijst voor de bovenliggende groep en kies **Volgende**.

3.  Stel op de pagina **Lidmaatschapscriteria definiëren** de optie **Groepslidmaatschap beginnen met** in op **Alle gebruikers in de bovenliggende groep**.

4.  Klik naast **Leden van deze beveiligingsgroepen uitsluiten** op **Bladeren** en selecteer vervolgens **Bedrijfsbeheerder**. Met deze uitsluiting kunt u de groep Intune-gebruikers beheren zonder dat dit van invloed is op het Company Administrator-account (ook wel bekend als de tenantbeheerder).

5.  Kies **Volgende** op de pagina **Direct lidmaatschap opgeven**. U hoeft hier verder niets te doen omdat u wilt dat de groep Intune-gebruikers alle gebruikers bevat, met uitzondering van de Company Administrator.

6.  Bekijk op de pagina **Samenvatting** de acties die zullen worden uitgevoerd en kies vervolgens **Voltooien**.

U vindt de nieuwe groep in de lijst **Groepen** en in de werkruimte **Groepen** onder **Alle gebruikers**. Hier kunt u de groep ook bewerken of verwijderen.



### Volgende stappen
Gefeliciteerd. U hebt zojuist stap 5 van de *Snelstartgids voor Intune* voltooid.

>[!div class="step-by-step"]

>[&larr; **Intune-licenties beheren**](.\start-with-a-paid-subscription-to-microsoft-intune-step-4.md)       [**Beleid en apps maken** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-6.md)  



<!--HONumber=Oct16_HO4-->


