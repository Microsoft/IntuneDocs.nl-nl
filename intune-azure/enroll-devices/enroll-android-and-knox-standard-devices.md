---
title: Android-apparaten registreren bij Intune | Intune Azure Preview | Microsoft Docs
description: 'Intune Azure Preview: in dit onderwerp vindt u informatie over het inschrijven van Android-apparaten in Intune Azure Preview.'
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 12/16/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f276d98c-b077-452a-8835-41919d674db5
ms.reviewer: chrisbal
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 990062ecf03a117dad74eb71e3f40abb79f22be6
ms.openlocfilehash: edd6303f3bb05dfff758cbb7d4bd08e21f083998


---

# <a name="enroll-android-devices"></a>Android-apparaten inschrijven

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Als Intune-beheerder kunt u via de bedrijfsportal het beheer van Android-apparaten, inclusief Samsung Knox Standard-apparaten, inschakelen. Gebruikers kunnen hun apparaten vervolgens registreren met de bedrijfsportal-app die beschikbaar is via Google Play.

## <a name="prerequisite"></a>Vereiste

U moet de MDM-instantie instellen op **Microsoft Intune** als voorbereiding op het beheer van mobiele apparaten. Zie [Set the MDM authority](set-mdm-authority.md) (De MDM-instantie instellen) voor instructies. U stelt de instantie slechts één keer in, wanneer u Intune voor het eerst instelt voor het beheer van mobiele apparaten, dus het kan zijn dat u de instantie al hebt ingesteld. 

## <a name="set-up-android-enrollment"></a>Android-inschrijving instellen

Intune is standaard ingesteld voor het toestaan van inschrijving van Android- en Samsung Knox Standard-apparaten. 

Als u de instelling voor het toestaan of blokkeren van Android-apparaten voor inschrijving wilt bekijken, gaat u naar de blade Intune in Azure Portal en kiest u **Inschrijving** > **Inschrijvingsbeperkingen**. 

## <a name="tell-your-users-how-to-enroll-their-devices-to-access-company-resources"></a>Uw gebruikers vertellen hoe ze hun apparaten moeten inschrijven om toegang te krijgen tot bedrijfsresources

Zie [Uw Android-apparaat inschrijven bij Intune](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-android) voor instructies voor inschrijving van eindgebruikers. Het inschrijvingsproces laat gebruikers weten wat ze kunnen verwachten, en wat IT-beheerders wel en niet kunnen zien op hun apparaten.

Zie de volgende artikelen voor meer informatie over andere taken voor eindgebruikers:

- [Bronnen over de eindgebruikerservaring in Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/what-to-tell-your-end-users-about-using-microsoft-intune)
- [Uw Android-apparaat gebruiken met Intune](https://docs.microsoft.com/intune/enduser/using-your-android-device-with-intune)


<!--HONumber=Feb17_HO1-->


