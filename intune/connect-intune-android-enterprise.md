---
title: Verbind uw Intune-account met uw Beheerde Google Play-account.
titleSuffix: Microsoft Intune
description: Meer informaite over het verbinden van uw Intune-account met uw Beheerde Google Play-account.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 6/21/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 19efd0821deeac0e76c60ee67e6230da554391a0
ms.sourcegitcommit: 484a898d54f5386fdbce300225aaa3495cecd6b0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/01/2019
ms.locfileid: "59567384"
---
# <a name="connect-your-intune-account-to-your-managed-google-play-account"></a>Uw Intune-account verbinden met uw Beheerde Google Play-account

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Ter ondersteuning van apparaten met een [Android Enterprise-werkprofiel](android-work-profile-enroll.md), [volledig beheerde Android Enterprise-apparaten](android-fully-managed-enroll.md) en [toegewezen Android Enterprise-apparaten](android-kiosk-enroll.md) moet u uw Intune-tenantaccount koppelen aan uw Beheerde Google Play-account.  

> [!NOTE]
> Als gevolg van interactie tussen domeinen van Google en Microsoft moet u in deze stap mogelijk uw browserinstellingen aanpassen.  Zorg ervoor dat 'portal.azure.com' en 'play.google.com' zich in dezelfde beveiligingszone bevinden in uw browser.

1. Als u dit nog niet hebt gedaan, moet u het beheer van mobiele apparaten voorbereiden door [de instantie voor het beheer van mobiele apparaten in te stellen](mdm-authority-set.md) als **Microsoft Intune**.
2. Meld u aan bij [Intune in Azure Portal](https://aka.ms/intuneportal), selecteer **Apparaatinschrijving** > **Android-inschrijving** > **Beheerde Google Play**.  Als u een aangepaste Intune beheerdersrol gebruikt, zijn voor toegang tot deze rol lees- en bijwerkmachtigingen voor de organisatie vereist.
   
   ![Android Enterprise-inschrijvingsscherm](./media/android-work-bind.png)

3. Selecteer **Ik ga akkoord** om Microsoft toestemming te geven om [gebruikers- en apparaatgegevens naar Google te verzenden](data-intune-sends-to-google.md). 
   
4. Kies **Google starten om nu verbinding te maken** om de beheerde Google Play-website te openen. De website wordt op een nieuw tabblad in de browser geopend.
  
5. Meld u aan op de aanmeldingspagina van Google met het Google-account dat wordt gekoppeld aan alle Android Enterprise-beheertaken voor deze tenant. Dit is het Google-account dat de IT-beheerders van uw bedrijf gebruiken voor het beheren en publiceren van apps in de Google Play-console. U kunt een bestaand Google-account gebruiken of een nieuw account maken. Het account dat u kiest moet niet worden gekoppeld aan een G-Suite-domein.
    
    > [!Note]
    > Als u gebruikmaakt van de Microsoft Edge-browser, klikt u op **Aanmelden** in de rechterbovenhoek om aan te melden bij uw Google-account.

6. Geef bij **Organization name** (Organisatienaam) de naam van uw bedrijf op. Bij **Enterprise mobility management (EMM) provider** moet **Microsoft Intune** worden weergegeven.

7. Ga akkoord met de Android-overeenkomst en kies **Bevestigen**. Uw aanvraag wordt verwerkt.

## <a name="disconnect-your-android-enterprise-administrative-account"></a>De verbinding met uw Android Enterprise-beheeraccount verbreken

U kunt Android Enterprise-inschrijving en -beheer uitschakelen. Hiervoor moet u eerst alle ingeschreven apparaten met een Android Enterprise-werkprofiel buiten gebruik stellen. Kies vervolgens **Verbinding verbreken** in de Intune-beheerconsole om de inschrijving van alle ingeschreven apparaten met een Android Enterprise-werkprofiel en alle toegewezen apparaten ongedaan te maken. U verwijdert hiermee ook de relatie tussen het Beheerde Google Play-account en Intune.

1. Meld u als Intune-beheerder aan bij [Azure Portal](https://portal.azure.com) en kies **Alle services** > **Bewaking en beheer** > **Intune**.
2. Kies **Apparaatinschrijving** > **Android-inschrijving** > **Beheerde Google Play** > **Verbinding verbreken**.
3. Kies **Ja** om de verbinding te verbreken en de registratie van alle Android Enterprise-apparaten bij Intune ongedaan te maken.

## <a name="next-steps"></a>Volgende stappen

Wanneer u verbinding met het Beheerde Google Play-account hebt gemaakt, kunt u [apparaten met een Android Enterprise-werkprofiel instellen](android-work-profile-enroll.md) en [toegewezen Android Enterprise-apparaten instellen](android-kiosk-enroll.md).
