---
title: Verbind uw Intune-account met uw Beheerde Google Play-account.
titleSuffix: Microsoft Intune
description: Meer informaite over het verbinden van uw Intune-account met uw Beheerde Google Play-account.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 5/13/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: enrollment
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: chmaguir
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: a89b94f098292bf44122d6d2d144c7f35967cd32
ms.sourcegitcommit: 556b7ea2049014c9027f0e44affd3f301fab55fc
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/06/2019
ms.locfileid: "73709448"
---
# <a name="connect-your-intune-account-to-your-managed-google-play-account"></a>Uw Intune-account verbinden met uw Beheerde Google Play-account

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Ter ondersteuning van apparaten met een [Android Enterprise-werkprofiel](android-work-profile-enroll.md), [volledig beheerde Android Enterprise-apparaten](android-fully-managed-enroll.md) en [toegewezen Android Enterprise-apparaten](android-kiosk-enroll.md) moet u uw Intune-tenantaccount koppelen aan uw Beheerde Google Play-account.  

In Intune worden automatisch vier veelgebruikte Android Enterprise-apps toegevoegd aan de Intune-beheerconsole, bij het verbinding maken met Google Play, om het u gemakkelijker te maken Android Enterprise-beheer te configureren en te gebruiken. Het betreft de volgende vier Android Enterprise-apps:

- **[Microsoft Intune](https://play.google.com/store/apps/details?id=com.microsoft.intune)** : wordt gebruikt voor scenario's met volledig beheer door Android Enterprise.
- **[Microsoft Authenticator](https://play.google.com/store/apps/details?id=com.azure.authenticator)** : om u aan te melden bij uw accounts als u verificatie in twee stappen gebruikt.
- **[Intune-bedrijfsportal](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal)** : wordt gebruikt voor beleidsregels voor app-beveiliging (APP) en werkprofielscenario's van Android Enterprise.
- [Managed Home Screen](https://play.google.com/store/apps/details?id=com.microsoft.launcher.enterprise): wordt gebruikt voor toegewezen/kiosk-scenario's van Android Enterprise.

> [!NOTE]
> Als gevolg van interactie tussen domeinen van Google en Microsoft moet u in deze stap mogelijk uw browserinstellingen aanpassen.  Zorg ervoor dat 'portal.azure.com' en 'play.google.com' zich in dezelfde beveiligingszone bevinden in uw browser.

1. Als u dit nog niet hebt gedaan, moet u het beheer van mobiele apparaten voorbereiden door [de instantie voor het beheer van mobiele apparaten in te stellen](../fundamentals/mdm-authority-set.md) als **Microsoft Intune**.
2. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431), kies **Apparaatinschrijving** > **Android-inschrijving** > **Beheerde Google Play**.  Als u een aangepaste Intune beheerdersrol gebruikt, zijn voor toegang tot deze rol lees- en bijwerkmachtigingen voor de organisatie vereist.
   
   ![Android Enterprise-inschrijvingsscherm](./media/connect-intune-android-enterprise/android-work-bind.png)

3. Selecteer **Ik ga akkoord** om Microsoft toestemming te geven om [gebruikers- en apparaatgegevens naar Google te verzenden](../protect/data-intune-sends-to-google.md). 
   
4. Kies **Google starten om nu verbinding te maken** om de beheerde Google Play-website te openen. De website wordt op een nieuw tabblad in de browser geopend.
  
5. Meld u aan op de aanmeldingspagina van Google met het Google-account dat wordt gekoppeld aan alle Android Enterprise-beheertaken voor deze tenant. Dit is het Google-account dat de IT-beheerders van uw bedrijf gebruiken voor het beheren en publiceren van apps in de Google Play-console. U kunt een bestaand Google-account gebruiken of een nieuw account maken. Het account dat u kiest moet niet worden gekoppeld aan een G-Suite-domein.
    
    > [!Note]
    > Als u gebruikmaakt van de Microsoft Edge-browser, klikt u op **Aanmelden** in de rechterbovenhoek om aan te melden bij uw Google-account.

6. Geef bij **Organization name** (Organisatienaam) de naam van uw bedrijf op. Bij **Enterprise mobility management (EMM) provider** moet **Microsoft Intune** worden weergegeven.

7. Ga akkoord met de Android-overeenkomst en kies **Bevestigen**. Uw aanvraag wordt verwerkt.

## <a name="disconnect-your-android-enterprise-administrative-account"></a>De verbinding met uw Android Enterprise-beheeraccount verbreken

U kunt Android Enterprise-inschrijving en -beheer uitschakelen. Hiervoor moet u eerst alle ingeschreven Android Enterprise-apparaten buiten gebruik stellen, inclusief de werkprofielapparaten, toegewezen apparaten, en volledig beheerde apparaten. Kies vervolgens **Verbinding verbreken** in de Intune-beheerconsole om de inschrijving van alle ingeschreven apparaten, toegewezen apparaten, en volledig beheerde apparaten met een Android Enterprise-werkprofiel ongedaan te maken. U verwijdert hiermee ook de relatie tussen het Beheerde Google Play-account en Intune.

1. Meld u als een Intune-beheerder aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Kies **Apparaatinschrijving** > **Android-inschrijving** > **Beheerde Google Play** > **Verbinding verbreken**.
3. Kies **Ja** om de verbinding te verbreken en de registratie van alle Android Enterprise-apparaten bij Intune ongedaan te maken.

## <a name="next-steps"></a>Volgende stappen

Wanneer u verbinding hebt gemaakt met het Beheerde Google Play-account, kunt u [apparaten met een Android Enterprise-werkprofiel instellen](android-work-profile-enroll.md), [toegewezen Android Enterprise-apparaten instellen](android-kiosk-enroll.md) en [ volledig beheerde Android Enterprise-apparaten instellen](android-kiosk-enroll.md).
