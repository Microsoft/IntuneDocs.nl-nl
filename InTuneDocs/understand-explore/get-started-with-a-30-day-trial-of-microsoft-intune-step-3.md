---
title: Groepen maken om gebruikers en apparaten te organiseren in de gratis proefversie | Microsoft Docs
description: Apparaat- en gebruikersgroepen maken wanneer u zich aanmeldt voor een gratis evaluatieversie van Microsoft Intune van 30 dagen.
keywords: 
author: lindavr
ms.author: lindavr
manager: angrobe
ms.date: 11/28/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7162cad3-5c14-43f3-a760-833ffd7786b1
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 89e190e6a3e514c0f38b33409cde2abea0776885
ms.openlocfilehash: 0cdf5bf8f9fad1f44dbb0ef11de71aea55949d89


---

# <a name="create-groups-to-organize-evaluation-subscription-users-and-devices"></a>Groepen maken om gebruikers en apparaten voor de evaluatieversie in te delen

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Groepen in Intune bieden u een hoge mate van flexibiliteit voor het beheren van uw apparaten en gebruikers. U kunt groepen aanpassen aan de behoeften van uw organisatie (bijvoorbeeld per geografische locatie, afdeling of hardware-eigenschappen) en gebruiken om een breed scala aan administratieve taken uit te voeren, van het instellen van beleidsregels voor een groep gebruikers tot het implementeren van toepassingen op een reeks apparaten.

## <a name="create-a-device-group"></a>Een apparaatgroep maken
Gebruik apparaatgroepen om software en updates te implementeren, en beleidsregels voor Microsoft Intune Agent-instellingen en voor Windows Firewall-instellingen te configureren. Stel bijvoorbeeld de groep 'Mijn proefapparaten' in met behulp van de volgende stappen:

1.  Kies in de [Intune-beheerconsole](https://manage.microsoft.com/) **Groepen** &gt; **Overzicht** &gt; **Groep maken**.

2.  Typ 'Mijn proefapparaten' in **Groepsnaam**, selecteer **Alle apparaten** in de lijst voor de bovenliggende groep en kies vervolgens **Volgende**.

3.  Selecteer **Alle apparaten** op de pagina **Lidmaatschapscriteria definiëren** om aan te geven dat de groep zowel mobiele apparaten als computers bevat.

4.  Kies **Volgende** op de pagina **Direct lidmaatschap opgeven**. Als u eerder een groep hebt gemaakt die niet alle apparaten bevat, en u specifieke apparaten wilt toevoegen aan de nieuwe groep, kunt u dat hier doen.

5.  Bekijk op de pagina **Samenvatting** de acties die zullen worden uitgevoerd en kies vervolgens **Voltooien**.

U vindt de nieuwe groep in de lijst **Groepen** en in de werkruimte **Groepen** onder **Alle apparaten**. Hier kunt u de groep ook bewerken of verwijderen.

## <a name="create-a-user-group"></a>Een gebruikersgroep maken
Gebruik gebruikersgroepen om software- en apparaatbeleid te implementeren. Stel bijvoorbeeld de groep 'Mijn proefgebruikers' in met behulp van de volgende stappen:

1.  Kies in de [Intune-beheerconsole](https://manage.microsoft.com/) **Groepen** &gt; **Overzicht** &gt; **Groep maken**.

2.  Typ 'Mijn proefgebruikers' in **Groepsnaam**, selecteer **Alle gebruikers** in de lijst voor de bovenliggende groep en kies vervolgens **Volgende**.

3.  Stel op de pagina **Lidmaatschapscriteria definiëren** de optie **Groepslidmaatschap beginnen met** in op **Alle gebruikers in de bovenliggende groep**.

4.  Klik naast **Leden van deze beveiligingsgroepen uitsluiten** op **Bladeren** en selecteer vervolgens **Bedrijfsbeheerder**. Met deze uitsluiting kunt u de groep Mijn proefgebruikers beheren zonder dat dit van invloed is op het Company Administrator-account (ook wel bekend als de tenantbeheerder).

5.  Kies **Volgende** op de pagina **Direct lidmaatschap opgeven**. U hoeft niet hier verder niets te doen omdat u wilt dat de groep Mijn proefgebruikers alle gebruikers bevat, met uitzondering van de Company Administrator.

6.  Bekijk op de pagina **Samenvatting** de acties die zullen worden uitgevoerd en kies vervolgens **Voltooien**.

U vindt de nieuwe groep in de lijst **Groepen** en in de werkruimte **Groepen** onder **Alle gebruikers**. Hier kunt u de groep ook bewerken of verwijderen.

Zie [Groepen gebruiken voor het beheren van gebruikers en apparaten met Microsoft Intune](/Intune/Deploy-Use/use-groups-to-manage-users-and-devices-with-microsoft-intune) voor meer informatie over het gebruik van groepen.

## <a name="next-steps"></a>Volgende stappen
[Beleidsregels maken](get-started-with-a-30-day-trial-of-microsoft-intune-step-4.md)  



<!--HONumber=Jan17_HO1-->


