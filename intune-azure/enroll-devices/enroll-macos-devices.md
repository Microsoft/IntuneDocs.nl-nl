---
title: macOS-apparaten registreren bij Intune | Intune Azure Preview | Microsoft Docs
description: 'Intune Azure Preview: informatie over het registreren van macOS-apparaten bij Intune Azure Preview.'
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 1/3/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 46429114-2e26-4ba7-aa21-b2b1a5643e01
ms.reviewer: chrisbal
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ba2affcdbcdfcd690d671c7b20f9d1e14a74f764
ms.openlocfilehash: 171175689adca027181f3da4d05222117de97e13


---

# <a name="enroll-macos-devices-in-intune-azure-preview"></a>macOS-apparaten registreren bij Intune Azure Preview

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Als Intune-beheerder kunt u macOS-apparaten beheren. Standaard kunnen gebruikers hun macOS-apparaten inschrijven met behulp van Azure Portal. U hoeft uw gebruikers alleen maar te vertellen dat ze naar de [website van de bedrijfsportal](http://portal.manage.microsoft.com) moeten gaan en hun macOS-apparaat moeten inschrijven. 

## <a name="prerequisites"></a>Vereisten

Voer de volgende vereisten uit voordat u inschrijving van macOS-apparaten instelt:

- [Domeinen configureren](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-2)
- [MDM-instantie instellen](set-mdm-authority.md)
- [Groepen maken](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-5)
- [De bedrijfsportal configureren](/intune-azure/manage-apps/company-portal-app.md)
- Gebruikerslicenties toewijzen in de [Office 365-portal](http://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Een Apple MDM-pushcertificaat ophalen](get-an-apple-mdm-push-certificate.md)

## <a name="set-up-macos-enrollment"></a>macOS-inschrijving instellen

Standaard is Intune al ingesteld om registratie van macOS-apparaten toe te staan. 

Als u de instelling voor het toestaan of blokkeren van macOS-apparaten voor registratie wilt bekijken, gaat u naar de blade Intune in Azure Portal en kiest u **Inschrijving** > **Inschrijvingsbeperkingen**. 

## <a name="tell-your-users-how-to-enroll-their-devices-to-access-company-resources"></a>Uw gebruikers vertellen hoe ze hun apparaten moeten inschrijven om toegang te krijgen tot bedrijfsresources

Zie [Uw macOS-apparaat inschrijven bij Intune](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-macos) voor inschrijvingsinstructies voor eindgebruikers. Het inschrijvingsproces laat gebruikers weten wat ze kunnen verwachten, en wat IT-beheerders wel en niet kunnen zien op hun apparaten.

Zie de volgende artikelen voor meer informatie over andere taken voor eindgebruikers:

- [Bronnen over de eindgebruikerservaring in Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/what-to-tell-your-end-users-about-using-microsoft-intune)
- [Uw iOS- of Mac OS-apparaat gebruiken met Intune](https://docs.microsoft.com/intune/enduser/using-your-ios-or-mac-os-x-device-with-intune)


<!--HONumber=Feb17_HO1-->


