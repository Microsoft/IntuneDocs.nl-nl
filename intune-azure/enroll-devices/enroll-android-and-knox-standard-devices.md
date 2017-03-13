---
title: Android-apparaten inschrijven in Intune
titleSuffix: Intune Azure preview
description: 'Intune Azure Preview: in dit onderwerp vindt u informatie over het inschrijven van Android-apparaten in Intune Azure Preview.'
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f276d98c-b077-452a-8835-41919d674db5
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: b7188dd8163334429396e7b7c8687810a6e63bb2
ms.lasthandoff: 02/18/2017


---

# <a name="enroll-android-devices"></a>Android-apparaten inschrijven

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Met Intune kunt u Android-apparaten beheren, waaronder Samsung Knox Standard-apparaten. Als u apparaatbeheer wilt inschakelen, moeten uw gebruikers hun apparaat inschrijven door de app Intune-bedrijfsportal te downloaden (die beschikbaar is via Google Play) en vervolgens de app te openen en de prompts voor inschrijving te volgen. Zodra Android-apparaten worden beheerd, kunt u [nalevingsbeleid maken](https://docs.microsoft.com/intune-azure/set-device-compliance/create-a-compliance-policy-for-android), [apps beheren](https://docs.microsoft.com/intune-azure/manage-apps/what-is-app-management) en meer.

## <a name="prerequisite"></a>Vereiste

U moet de MDM-instantie instellen op **Microsoft Intune** als voorbereiding op het beheer van mobiele apparaten. Zie [Set the MDM authority](set-mdm-authority.md) (De MDM-instantie instellen) voor instructies. U stelt de instantie slechts één keer in, wanneer u Intune voor het eerst instelt voor het beheer van mobiele apparaten, dus het kan zijn dat u de instantie al hebt ingesteld. 

## <a name="set-up-android-enrollment"></a>Android-inschrijving instellen

Standaard staat Intune de inschrijving van Android- en Samsung Knox Standard-apparaten toe. 

Zie [Beperkingen voor apparaattypen instellen](https://docs.microsoft.com/intune-azure/enroll-devices/set-enrollment-restrictions#set-device-type-restrictions) als u de inschrijving wilt blokkeren van Android-apparaten of alleen Android-apparaten die het eigendom van de gebruiker zijn. 

Zie [Apparaatlimietbeperkingen instellen](https://docs.microsoft.com/intune-azure/enroll-devices/set-enrollment-restrictions#set-device-limit-restrictions) als u het maximumaantal apparaten wilt instellen dat een gebruiker kan inschrijven.

## <a name="tell-your-users-how-to-enroll-their-devices-to-access-company-resources"></a>Uw gebruikers vertellen hoe ze hun apparaten moeten inschrijven om toegang te krijgen tot bedrijfsresources

U moet uw eindgebruikers vertellen dat ze naar Google Play moeten gaan om de app Intune-bedrijfsportal te downloaden, en vervolgens de app moeten openen en de prompts voor inschrijving van hun apparaat moeten volgen. De app leidt gebruikers door het inschrijvingsproces en legt uit wat gebruikers kunnen verwachten en wat IT-beheerders wel en niet kunnen zien op hun apparaten.

U kunt hen ook een link naar online inschrijvingsstappen sturen: [Uw Android-apparaat inschrijven bij Intune](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-android). 

Zie de volgende artikelen voor meer informatie over andere taken voor eindgebruikers:

- [Bronnen over de eindgebruikerservaring in Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/what-to-tell-your-end-users-about-using-microsoft-intune)
- [Uw Android-apparaat gebruiken met Intune](https://docs.microsoft.com/intune/enduser/using-your-android-device-with-intune)
