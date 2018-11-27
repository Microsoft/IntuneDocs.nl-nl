---
title: Uw Intune-account met uw Android Enterprise-account verbinden
titlesuffix: Microsoft Intune
description: Meer informatie over het verbinden van uw Intune-account met uw Android Enterprise-account.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 6/21/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: c32effb645b329c8095ec8757a980b1f3d80a4d7
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/20/2018
ms.locfileid: "52184283"
---
# <a name="connect-your-intune-account-to-your-android-enterprise-account"></a>Uw Intune-account met uw Android Enterprise-account verbinden

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Ter ondersteuning van apparaten met een Android-werkprofiel en Android-kioskapparaten moet u uw Intune-tenantaccount koppelen aan uw Android Enterprise-account. 

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

U kunt Android Enterprise-inschrijving en -beheer uitschakelen. Hiervoor moet u eerst alle geregistreerde apparaten met een Android-werkprofiel buiten gebruik stellen. Kies vervolgens **Verbinding verbreken** in de Intune-beheerconsole om de registratie van alle geregistreerde apparaten met een Android-werkprofiel en de kioskapparaten ongedaan te maken. U verwijdert hiermee ook de relatie tussen het Android Enterprise-account en Intune.

1. Meld u als Intune-beheerder aan bij [Azure Portal](https://portal.azure.com) en kies **Alle services** > **Bewaking en beheer** > **Intune**.
2. Kies **Apparaatinschrijving** > **Android-inschrijving** > **Beheerde Google Play** > **Verbinding verbreken**.
3. Kies **Ja** om de verbinding te verbreken en de registratie van alle Android Enterprise-apparaten bij Intune ongedaan te maken.

## <a name="next-steps"></a>Volgende stappen

Wanneer u verbinding met het Android Enterprise-account hebt gemaakt, kunt u[apparaten met een Android-werkprofiel instellen](android-work-profile-enroll.md) en [Android-kioskapparaten instellen](android-kiosk-enroll.md).
