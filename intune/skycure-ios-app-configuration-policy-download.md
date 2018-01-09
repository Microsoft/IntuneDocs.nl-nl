---
title: Het configuratiebeleid voor de iOS-app voor Skycure downloaden voor gebruik met Intune
titlesuffix: Azure portal
description: Download het configuratiebeleid voor de iOS-app voor Skycure voor gebruik met Intune.
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 12/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1bdc2ecf-32d0-4b6a-80b4-dbcdb9909010
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: cbf26b44725f1fa08fbc6766f0560fe91d63d6ca
ms.sourcegitcommit: a3a744ea55f38a360ca9f788c77a5b3018d1add5
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/30/2017
---
# <a name="download-skycure-ios-app-configuration-policy"></a>Het configuratiebeleid voor de iOS-app voor Skycure downloaden

## <a name="before-you-begin"></a>Voordat u begint

U moet zich aanmelden bij de Skycure-beheerconsole en de volgende stappen uitvoeren.

> [!TIP] 
> Als u gebruikmaakt van Microsoft Internet Explorer 11 of Microsoft Edge, moet u de Skycure-beheerconsole mogelijk in InPrivate-modus openen.

## <a name="to-download-the-ios-app-configuration-policy"></a>Het configuratiebeleid voor de iOS-app downloaden

1.  Ga naar de [Skycure-beheerconsole](https://aad.skycure.com).

2.  Voer uw **Skycure-beheerdersreferenties** in en klik vervolgens op **Doorgaan**.

    ![De aanmelding bij de Skycure-beheerconsole](./media/skycure-ios-app-1.png)

    > [!IMPORTANT] 
    > De gebruikersnaam voor de Skycure-beheerder is een e-mailaccount dat een geldig gebruikersaccount moet zijn in Azure Active Directory. Als dat niet het geval is, mislukt de aanmelding. Skycure maakt gebruik van Azure Active Directory om deze gebruikersnaam voor de beheerder te verifiëren door middel van eenmalige aanmelding.

3.  Ga naar **Instellingen** &gt; **Integraties voor apparaatbeheer**  &gt; **Selectie van EMM-integraties**, kies **Microsoft Intune** en sla vervolgens de selectie op.

4.  Klik op de koppeling voor de **installatiebestanden voor de integratie** en sla het gegenereerde bestand \*.zip op. Het ZIP-bestand bevat het bestand **skycure\_configuration.plist**, waarmee het configuratiebeleid voor de iOS-app wordt gemaakt in de klassieke Intune-portal.

![Installatiebestanden voor de integratie van Skycure](./media/skycure-ios-app-2.png)

## <a name="next-steps"></a>Volgende stappen

[Skycure-apps, de Microsoft Authenticator-app en het iOS-configuratiebeleid toevoegen en toewijzen](mtd-apps-ios-app-configuration-policy-add-assign.md)
