---
title: macOS-apparaten registreren bij Intune
titleSuffix: Intune Azure preview
description: 'Intune Azure Preview: informatie over het registreren van macOS-apparaten bij Intune Azure Preview.'
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/14/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 46429114-2e26-4ba7-aa21-b2b1a5643e01
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 3758df744311392528be01c826527c2a9d879975
ms.openlocfilehash: 6fcbeb30fb11b6bc8def3a1c245bff56b3f7cca4
ms.contentlocale: nl-nl
ms.lasthandoff: 05/10/2017


---

# <a name="enroll-macos-devices-in-intune-azure-preview"></a>macOS-apparaten registreren bij Intune Azure Preview

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Met Intune kunt u macOS-apparaten beheren. Als u apparaatbeheer wilt inschakelen, moeten uw gebruikers hun apparaat inschrijven door naar de [website van de bedrijfsportal](http://portal.manage.microsoft.com) te gaan en de prompts te volgen. Zodra macOS-apparaten worden beheerd, kunt u [aangepaste instellingen voor macOS-apparaten maken](../configure-devices/custom-for-macos.md). Binnenkort zijn er nog meer mogelijkheden beschikbaar.

## <a name="prerequisites"></a>Vereisten

Voer de volgende vereisten uit voordat u inschrijving van macOS-apparaten instelt:

- [Domeinen configureren](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-2)
- [MDM-instantie instellen](set-mdm-authority.md)
- [Groepen maken](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-5)
- [De bedrijfsportal configureren](../manage-apps/company-portal-app.md)
- Gebruikerslicenties toewijzen in de [Office 365-portal](http://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Een Apple MDM-pushcertificaat ophalen](get-an-apple-mdm-push-certificate.md)

## <a name="set-up-macos-enrollment"></a>macOS-inschrijving instellen

Standaard staat Intune toe dat macOS-apparaten kunnen worden ingeschreven.

Zie [Beperkingen voor apparaattypen instellen](set-enrollment-restrictions.md#set-device-type-restrictions) als u de inschrijving van macOS-apparaten wilt blokkeren.

Zie [Apparaatlimietbeperkingen instellen](set-enrollment-restrictions.md#set-device-limit-restrictions) als u het maximumaantal apparaten wilt instellen dat een gebruiker kan inschrijven.

## <a name="tell-your-users-how-to-enroll-their-devices-to-access-company-resources"></a>Uw gebruikers vertellen hoe ze hun apparaten moeten inschrijven om toegang te krijgen tot bedrijfsresources

U moet uw gebruikers vertellen dat ze naar de [website van de bedrijfsportal](http://portal.manage.microsoft.com) moeten gaan en de prompts moeten volgen om hun apparaat in te schrijven. U kunt hen ook een link naar online inschrijvingsstappen sturen: [Uw macOS-apparaat inschrijven bij Intune](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-macos).

Zie de volgende artikelen voor meer informatie over andere taken voor eindgebruikers:

- [Bronnen over de eindgebruikerservaring in Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/how-to-educate-your-end-users-about-microsoft-intune)
- [Uw iOS- of Mac OS-apparaat gebruiken met Intune](https://docs.microsoft.com/intune/enduser/using-your-ios-or-mac-os-x-device-with-intune)

