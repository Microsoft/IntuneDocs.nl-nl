---
title: Inschrijving voor macOS-apparaten instellen
titlesuffix: Microsoft Intune
description: Meer informatie over hoe u de inschrijving voor iOS-apparaten in Intune instelt.
keywords: 
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/15/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 46429114-2e26-4ba7-aa21-b2b1a5643e01
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: c1fb846dc65ee14315edf7b9ba15e0e24998a3a2
ms.sourcegitcommit: 21db583d6a9d3c15a8a8ee5579309dff1cfe1f8b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/16/2018
---
# <a name="set-up-enrollment-for-macos-devices-in-intune"></a>Inschrijving voor macOS-apparaten instellen in Intune

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

## <a name="user-owned-ios-devices-byod"></a>iOS-apparaten die het eigendom van gebruikers zijn (BYOD)

U kunt gebruikers hun persoonlijke apparaten laten inschrijven voor Intune-beheer, wat 'Bring Your Own Device' of BYOD wordt genoemd. Zodra u aan de vereisten hebt voldaan en gebruikerslicenties hebt toegewezen, kunnen ze in de App Store de macOS-bedrijfsportal-app downloaden en in de app de inschrijvingsinstructies volgen.

## <a name="company-owned-ios-devices"></a>iOS-apparaten die bedrijfseigendom zijn
Voor organisaties die apparaten voor hun gebruikers aanschaffen, ondersteunt Intune de inschrijving van macOS-apparaten die bedrijfseigendom zijn met een [apparaatinschrijvingsmanager](device-enrollment-manager-enroll.md)-account.

## <a name="set-up-macos-enrollment"></a>macOS-inschrijving instellen

Standaard staat Intune toe dat macOS-apparaten kunnen worden ingeschreven.

Zie [Beperkingen voor apparaattypen instellen](enrollment-restrictions-set.md) als u de inschrijving van macOS-apparaten wilt blokkeren.

## <a name="tell-your-users-how-to-enroll-their-devices-to-access-company-resources"></a>Uw gebruikers vertellen hoe ze hun apparaten moeten inschrijven om toegang te krijgen tot bedrijfsresources

Meld uw gebruikers dat ze naar de [website van de bedrijfsportal](https://portal.manage.microsoft.com) moeten gaan en de prompts moeten volgen om hun apparaat in te schrijven. U kunt hen ook een link naar online inschrijvingsstappen sturen: [Uw macOS-apparaat inschrijven bij Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-macos).

Zie de volgende artikelen voor meer informatie over andere taken voor eindgebruikers:

- [Bronnen over de eindgebruikerservaring in Microsoft Intune](end-user-educate.md)
- [Uw macOS-apparaat gebruiken met Intune](/intune-user-help/using-your-macos-device-with-intune)

## <a name="enroll-virtual-macos-machines-for-testing"></a>Virtuele macOS-machines inschrijven voor testen

> [!NOTE]
> Virtuele macOS-machines worden alleen ondersteund voor het testen. Gebruik geen virtuele macOS-machines als productieapparaten voor uw eindgebruikers. 

U kunt virtuele macOS-machines inschrijven voor het testen met ofwel Parallels Desktop of VMware Fusion. 

Voor Parallels Desktop moet u het hardwaretype en het serienummer voor de virtuele machines instellen zodat deze kunnen worden herkend door Intune. Volg de instructies van Parallels voor [het instellen van het hardwaretype](http://kb.parallels.com/123594) en [serienummer](http://kb.parallels.com/123455) om de vereiste instellingen voor het testen op te geven. U wordt aangeraden het hardwaretype van het apparaat waarop de virtuele machines worden uitgevoerd, af te stemmen op het hardwaretype van de virtuele machines die u maakt. U vindt dit hardwaretype in **Apple-menu** > **Over deze Mac** > **Systeeminformatie** > **Modelnaam**. 

Voor VMware Fusion moet u [het VMX-bestand bewerken](https://kb.vmware.com/s/article/1014782) om het hardwaremodel en serienummer van de virtuele machine in te stellen. U wordt aangeraden het hardwaretype van het apparaat waarop de virtuele machines worden uitgevoerd, af te stemmen op het hardwaretype van de virtuele machines die u maakt. U vindt dit hardwaretype in **Apple-menu** > **Over deze Mac** > **Systeeminformatie** > **Modelnaam**. 
