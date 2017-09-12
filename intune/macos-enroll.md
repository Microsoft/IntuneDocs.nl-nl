---
title: macOS-apparaten registreren bij Intune
titlesuffix: Azure portal
description: Meer informatie over het registreren van Mac OS-apparaten in Intune."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 06/14/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 46429114-2e26-4ba7-aa21-b2b1a5643e01
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: bdf29fdc9c7098572ca9f06a65dc23320f7a08fb
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/09/2017
---
# <a name="enroll-macos-devices-in-intune"></a>macOS-apparaten registreren bij Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Met Intune kunt u macOS-apparaten beheren. Als u apparaatbeheer wilt inschakelen, moeten uw gebruikers hun apparaat inschrijven door naar de [website van de bedrijfsportal](http://portal.manage.microsoft.com) te gaan en de prompts te volgen. Zodra macOS-apparaten worden beheerd, kunt u [aangepaste instellingen voor macOS-apparaten maken](custom-settings-macos.md). Binnenkort zijn er nog meer mogelijkheden beschikbaar.

## <a name="prerequisites"></a>Vereisten

Voer de volgende vereisten uit voordat u inschrijving van macOS-apparaten instelt:

- [Domeinen configureren](custom-domain-name-configure.md)
- [MDM-instantie instellen](mdm-authority-set.md)
- [Groepen maken](https://docs.microsoft.com/intune-classic/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-5)
- [De bedrijfsportal configureren](company-portal-app.md)
- Gebruikerslicenties toewijzen in de [Office 365-portal](http://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Een Apple MDM-pushcertificaat ophalen](apple-mdm-push-certificate-get.md)

## <a name="set-up-macos-enrollment"></a>macOS-inschrijving instellen

Standaard staat Intune toe dat macOS-apparaten kunnen worden ingeschreven.

Zie [Beperkingen voor apparaattypen instellen](enrollment-restrictions-set.md) als u de inschrijving van macOS-apparaten wilt blokkeren.

## <a name="tell-your-users-how-to-enroll-their-devices-to-access-company-resources"></a>Uw gebruikers vertellen hoe ze hun apparaten moeten inschrijven om toegang te krijgen tot bedrijfsresources

U moet uw gebruikers vertellen dat ze naar de [website van de bedrijfsportal](http://portal.manage.microsoft.com) moeten gaan en de prompts moeten volgen om hun apparaat in te schrijven. U kunt hen ook een link naar online inschrijvingsstappen sturen: [Uw macOS-apparaat inschrijven bij Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-macos).

Zie de volgende artikelen voor meer informatie over andere taken voor eindgebruikers:

- [Bronnen over de eindgebruikerservaring in Microsoft Intune](end-user-educate.md)
- [Uw iOS- of Mac OS-apparaat gebruiken met Intune](https://docs.microsoft.com/intune-user-help/using-your-ios-or-mac-os-x-device-with-intune)
