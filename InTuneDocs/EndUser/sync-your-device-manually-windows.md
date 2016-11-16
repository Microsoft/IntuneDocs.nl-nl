---
title: Uw Windows-apparaat handmatig synchroniseren | Microsoft Intune
description: 
keywords: 
author: Staciebarker
ms.author: stabar
manager: angrobe
ms.date: 10/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 443c6de7-5187-4dc4-b844-6085a0c659bd
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: priyar
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 2d7630d71505fadc22ab135ff0c8988b314793ad
ms.openlocfilehash: e0f18e4e1077f7843b4f8d8ea6d9e485f715bc3c


---


# Uw Windows-apparaat handmatig synchroniseren
Als de installatie van de app te lang duurt, kunt u proberen om uw apparaat handmatig te synchroniseren. Dit kan helpen om de installatie te versnellen.

Alleen de volgende versies worden ondersteund. Volg de instructies voor het type apparaat dat u hebt.

* [Windows 10 Mobile](#windows-10-mobile)
* [Windows 10-bureaublad](#windows-10-desktop)
* [Windows Phone 8,1](#windows-phone-8-1)


## Windows 10 Mobile
Ga als volgt te werk als u uw Windows 10 Mobile-apparaat handmatig wilt synchroniseren om een trage installatie van de app te versnellen:

1. Ga naar **Alle apps** > **Instellingen** > **Accounts**.

    ![Accounts kiezen op het scherm Instellingen](./media/win10m-sync-1-settings-accounts.png)

2. Kies **Toegang via het werknetwerk**.

    ![Toegang via het werknetwerk kiezen als het accounttype](./media/win10m-sync-2-work-access.png)

3. Kies onder **Registreren voor apparaatbeheer** de naam van uw bedrijf.

    ![De naam van het bedrijf kiezen voor apparaatbeheer](./media/win10m-sync-3-tap-comp-name.png)

4. Kies het pictogram **Synchroniseren**.

    ![Het pictogram Synchroniseren kiezen](./media/win10m-sync-4-tap-sync.png)

    Boven in het scherm wordt het bericht 'Uw account wordt gesynchroniseerd' weergegeven. De knop **Synchroniseren** is pas beschikbaar nadat de synchronisatie van het apparaat is voltooid.

## Windows 10-bureaublad
Omdat er meer dan één versie van Windows 10 is, zijn er twee sets met stappen. Bekijk de schermafbeeldingen om te zien welke stappen u het beste kunt gebruiken en volg dan de stappen die betrekking hebben op uw apparaat. 

1. Kies de knop **Start** en kies vervolgens **Instellingen**.

    ![De knop Start](./media/win10pc-sync-1-start-button.png)

2. Kies op de pagina **Instellingen** de optie **Accounts**.

    ![Accounts kiezen op de pagina Instellingen](./media/win10pc-sync-2-settings-accounts.png)

3. Bekijk de volgende twee schermen en kies het scherm dat lijkt op het scherm op uw apparaat. Volg de stappen die bij het scherm horen dat u op het apparaat ziet.

    Als u dit scherm met de melding 'Toegang tot werk of school' ziet, volgt u de instructies in [Stappen om te volgen als u Toegang tot werk of school ziet](#steps-to-follow-if-you-see-access-work-or-school).

    ![Te volgen stappen als u Toegang tot werk of school ziet](./media/w10-enroll-rs1-connect-to-work-or-school.png)

    Als u dit scherm met de melding 'Toegang via het werknetwerk' ziet, volgt u de stappen in [Stappen om te volgen als u Toegang via het werknetwerk ziet](#steps-to-follow-if-you-see-your-account).

    ![Toegang via het werknetwerk kiezen als het accounttype](./media/win10pc-sync-3-work-access.png) 

### Stappen om te volgen als u Toegang tot werk of school ziet

1. Kies op de pagina **Accounts** de optie **Toegang tot werk of school**.

    ![Kies Toegang tot werk of school](./media/w10-enroll-rs1-connect-to-work-or-school.png)

2. Kies uw werk- of schoolaccount. Afhankelijk van hoe uw IT-beheerder een en ander heeft ingesteld, ziet u mogelijk twee accounts die op het voorbeeld hieronder lijken. Naast het ene account wordt een aktetas weergegeven en naast het andere account ziet u het Microsoft-logo. 

    - Als u het account met de aktetas ziet, selecteert u dat account en zoekt u naar een **Info**-knop daaronder. 
    - Als u het account met het Microsoft-logo ziet, selecteert u dat account en zoekt u naar een **Info**-knop daaronder.

    ![Kies de naam van het account naast de aktetas of het Microsoft-logo](./media/win10pc-rs1-sync-info-button.png)

3. Kies de **Info**-knop. Er wordt een dialoogvenster geopend dat op het voorbeeld hieronder lijkt.

    ![Kies de naam van het account naast de aktetas of het Microsoft-logo](./media/win10pc-rs1-sync-button.png)

4. Kies de knop **Synchroniseren**. Het apparaat wordt gesynchroniseerd met Intune.

### Te volgen stappen als u Toegang via het werknetwerk ziet
    
1. Kies op de pagina **Accounts** de optie **Toegang via het werknetwerk**.

    ![Toegang via het werknetwerk kiezen als het accounttype](./media/win10pc-sync-3-work-access.png)

2. Kies in de sectie **Registreren voor apparaatbeheer** de naam van uw bedrijf.

    ![De naam van het bedrijf kiezen voor apparaatbeheer](./media/win10pc-sync-4-tap-com-name.png)

3. Kies de knop **Synchroniseren**.

    ![De knop Synchroniseren kiezen](./media/win10pc-sync-5-tap-sync.png)

   De knop wordt uitgeschakeld totdat de synchronisatie is voltooid.

## Windows Phone 8,1
Ga als volgt te werk als u uw Windows Phone 8.1-apparaat handmatig wilt synchroniseren om een trage installatie van de app te versnellen:

1. Ga naar **Alle apps** > **Instellingen** > **Werkplek**.

    ![Lijst met instellingen](./media/wp81-1-sync-settings-workplace.png)

2. Kies de naam van uw bedrijf.

    ![De naam van het bedrijf kiezen voor het werkplekaccount](./media/wp81-2-sync-tap-compname.png)

3. Kies het pictogram **Synchroniseren**.

    ![Het pictogram Synchroniseren kiezen](./media/wp81-3-sync-tap-sync-button.png)

   Boven in het scherm wordt het bericht 'Uw account wordt gesynchroniseerd' weergegeven tot het apparaat is gesynchroniseerd.

Nog hulp nodig? Neem contact op met uw IT-beheerder. Controleer of hun contactgegevens beschikbaar zijn op de [bedrijfsportalwebsite](http://portal.manage.microsoft.com).



<!--HONumber=Oct16_HO3-->


