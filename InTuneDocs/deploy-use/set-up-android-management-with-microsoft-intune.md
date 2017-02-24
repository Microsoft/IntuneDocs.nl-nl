---
title: Android-beheer instellen | Microsoft Docs
description: Schakel het beheer van mobiele apparaten (MDM) in voor Android- en KNOX Standard-apparaten met Microsoft Intune.
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 01/29/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dbe5cad1-3e0d-41a9-966b-738156089700
ms.reviewer: lacranda
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 6b99854e17e00a0dd0f91fa82fd1b79d1dfe5663
ms.openlocfilehash: 8e2588e2bb0537877f0164bc996fa973f25ea4dd


---

# <a name="set-up-android-device-management"></a>Android-beheer instellen met Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Als Intune-beheerder kunt u via de bedrijfsportal het beheer van Android-apparaten, inclusief Samsung Knox Standard-apparaten, inschakelen. Gebruikers kunnen hun apparaten vervolgens registreren met de bedrijfsportal-app die beschikbaar is via Google Play.

Standaard kunnen Android-apparaten worden ingeschreven in Intune. Meld u bij de [Microsoft Intune-accountportal](http://manage.microsoft.com) aan met uw beheerdersreferenties als u de inschrijving van Android-apparaten wilt blokkeren. Kies **Beheer** > **Beheer van mobiele apparaten** > **Inschrijvingsregels** en schakel vervolgens het selectievakje **Android-apparaten toestaan** uit.

1.  **Intune instellen**<br>
    Als u dit nog niet hebt gedaan, moet u het beheer van mobiele apparaten voorbereiden door de [beheerautoriteit voor mobiele apparaten in te stellen](prerequisites-for-enrollment.md#step-2-set-mdm-authority) op **Microsoft Intune** en MDM in te stellen.

2.  **Android-inschrijving ingeschakeld**<br>
    In de Intune-console zijn geen extra configuraties nodig om de inschrijving van mobiele Android-apparaten in te schakelen.

3.  **Vertel uw gebruikers hoe ze hun apparaten moeten registreren om toegang te krijgen tot bedrijfsbronnen.**

    Zie [Uw Android-apparaat inschrijven bij Intune](../enduser/enroll-your-device-in-intune-android.md) voor instructies voor inschrijving van eindgebruikers. Het inschrijvingsproces laat gebruikers weten wat ze kunnen verwachten, en wat IT-beheerders wel en niet kunnen zien op hun apparaten.

    Zie de volgende artikelen voor meer informatie over andere taken voor eindgebruikers:
  - [Bronnen over de eindgebruikerservaring in Microsoft Intune](how-to-educate-your-end-users-about-microsoft-intune.md)
  - [Richtlijnen voor eindgebruikers van Android-apparaten](../enduser/using-your-android-device-with-intune.md)

Vanwege de afwezigheid van Google Play Store in China kunnen Android-apparaten de bedrijfsportal alleen verkrijgen via Chinese app-marktplaatsen. De bedrijfsportal-app voor Android kan nu worden gedownload via de volgende stores:
* [Baidu](https://go.microsoft.com/fwlink/?linkid=836946)
* [Huawei](https://go.microsoft.com/fwlink/?linkid=836948)
* [Tencent](https://go.microsoft.com/fwlink/?linkid=836949)
* [Wandoujia](https://go.microsoft.com/fwlink/?linkid=836950)
* [Xiaomi](https://go.microsoft.com/fwlink/?linkid=836947)

De bedrijfsportal-app voor Android maakt gebruik van Google Play Services om te communiceren met de Microsoft Intune-service. Omdat Google Play Services nog niet beschikbaar is in China, kan het tot wel acht uur duren voordat de volgende taken zijn voltooid. 

|Intune-beheerconsole| Intune bedrijfsportal-app voor Android |Intune-bedrijfsportalwebsite|   
|---|---|---|
|Volledig wissen| Een extern apparaat verwijderen| Apparaat verwijderen (lokaal en extern)|
|Selectief wissen| Apparaat opnieuw instellen| Apparaat opnieuw instellen|
|Nieuwe of bijgewerkte app-implementaties| Installeren van beschikbare line-of-business-apps| Wachtwoordcode van apparaat opnieuw instellen|
|Vergrendelen op afstand|||
|Wachtwoordcode opnieuw instellen|||

### <a name="see-also"></a>Zie tevens
[Vereisten voor het registreren van apparaten in Microsoft Intune](prerequisites-for-enrollment.md)



<!--HONumber=Feb17_HO3-->


