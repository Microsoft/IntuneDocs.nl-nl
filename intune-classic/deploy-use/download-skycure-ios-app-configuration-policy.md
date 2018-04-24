---
title: Het configuratiebeleid voor de iOS-app voor Skycure downloaden
description: Download het configuratiebeleid voor de iOS-app voor Skycure dat moet worden gebruikt met de iOS-app voor Skycure die voor de eindgebruikers is geïmplementeerd.
keywords: ''
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 03/16/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: d211b876-4d3a-473c-999f-843c0a16cd22
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 2f3cf3b2b18eeadf6779b7a8e96d75e569e6e3be
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2018
---
# <a name="download-skycure-ios-app-configuration-policy"></a>Het configuratiebeleid voor de iOS-app voor Skycure downloaden

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

## <a name="before-you-begin"></a>Voordat u begint

U moet zich aanmelden bij de Skycure-beheerconsole en de volgende stappen uitvoeren.

> [!TIP] 
> Als u gebruikmaakt van Microsoft Internet Explorer 11 of Microsoft Edge, moet u de Skycure-beheerconsole mogelijk in InPrivate-modus openen.

## <a name="to-download-the-ios-app-configuration-policy"></a>Het configuratiebeleid voor de iOS-app downloaden

1.  Ga naar de [Skycure-beheerconsole](https://aad.skycure.com).

2.  Voer uw **Skycure-beheerdersreferenties** in en klik vervolgens op **Doorgaan**.

    ![De aanmelding bij de Skycure-beheerconsole](../media/mtp/skycure-ios-app-1.png)

    > [!IMPORTANT] 
    > De gebruikersnaam voor de Skycure-beheerder is een e-mailaccount dat een geldig gebruikersaccount moet zijn in Azure Active Directory. Als dat niet het geval is, mislukt de aanmelding. Skycure maakt gebruik van Azure Active Directory om deze gebruikersnaam voor de beheerder te verifiëren door middel van eenmalige aanmelding.

3.  Ga naar **Instellingen** &gt; **Integraties voor apparaatbeheer**  &gt; **Selectie van EMM-integraties**, kies **Microsoft Intune** en sla vervolgens de selectie op.

2.  Klik op de koppeling voor de **installatiebestanden voor de integratie** en sla het gegenereerde bestand \*.zip op. Het ZIP-bestand bevat het bestand **skycure\_configuration.plist**, waarmee het configuratiebeleid voor de iOS-app wordt gemaakt in de klassieke Intune-portal.

![Installatiebestanden voor de integratie van Skycure](../media/mtp/skycure-ios-app-2.png)

## <a name="next-steps"></a>Volgende stappen

[Skycure-apps, de Microsoft Authenticator-app en het iOS-configuratiebeleid toevoegen](/intune-classic/deploy-use/add-skycure-apps-microsoft-authenticator-and-ios-app-configuration-policy)
