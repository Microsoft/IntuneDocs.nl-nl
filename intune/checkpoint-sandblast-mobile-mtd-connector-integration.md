---
title: Check Point SandBlast MTD met Microsoft Intune
titlesuffix: ''
description: Meer informatie over hoe u Check Point Sandblast Mobile Threat Defense (MTD) instelt met Intune om toegang tot uw bedrijfsbronnen met mobiele apparaten te beheren.
keywords: ''
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 07/03/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 1e9b1576-b239-48cc-a672-da6b5fb7be0a
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b864d78fd7bfd7fb4e177b568b3587bc1e28b209
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/08/2018
ms.locfileid: "29777224"
---
# <a name="integrate-check-point-sandblast-mobile-with-intune"></a>Check Point SandBlast Mobile integreren met Intune

## <a name="before-you-begin"></a>Voordat u begint

> [!NOTE] 
> De onderstaande stappen dienen te worden genomen in de [Check Point SandBlast Mobile MTD-console](https://intune-4.eu1.locsec.net/).

Zorg ervoor dat u het volgende hebt voordat u begint met de integratie van Check Point SandBlast Mobile met Intune:

-   Microsoft Intune-abonnement

-   Azure Active Directory-beheerdersreferenties om de volgende machtigingen te verlenen:

    -   Aanmelden en gebruikersprofiel lezen

    -   Toegang tot de map als de aangemelde gebruiker

    -   Mapgegevens lezen

    -   Gegevens van een apparaat verzenden naar Intune

-   Administrator-referenties voor toegang tot de Check Point SandBlast Mobile MTD-console.

### <a name="check-point-sandblast-app-authorization"></a>Check Point SandBlast-app-autorisatie

Het autorisatieproces van de Check Point SandBlast-app bestaat uit het volgende:

-   De Check Point SandBlast Mobile-service toestaan informatie met betrekking tot de status van apparaten naar Intune te communiceren.

-   Check Point SandBlast Mobile wordt gesynchroniseerd met Azure AD Enrollment-groepslidmaatschap om de database van het apparaat te vullen.

-   Toestaan dat Check Point SandBlast-beheerconsole Azure AD-enkelvoudige aanmelding (SSO) gebruikt.

-   Toestaan dat de Check Point SandBlast Mobile-app kan aanmelden met behulp van Azure AD-eenmalige aanmelding.

## <a name="to-set-up-check-point-sandblast-mobile-integration"></a>Check Point SandBlast Mobile-integratie instellen

1.  Ga naar [Check Point SandBlast Mobile MTD-console](https://intune-4.eu1.locsec.net/) en meld u aan met uw referenties.

2.  Klik op het tabblad**Instellingen**.

3.  Kies **Apparaatbeheer** en vervolgens **Instellingen**.

4.  Kies **Microsoft Intune** in de vervolgkeuzelijst **MDM Service**.

5.  Als u Microsoft Intune als MDM-Service hebt ingesteld, verschijnt het venster **Configuratie van Microsoft Intune**. Kies **Toevoegen aan mijn organisatie** voor elk apparaatplatform: iOS, Android en Windows om Check Point SandBlast Mobile te autoriseren te communiceren met Intune en Azure AD.

    ![Afbeelding van Intune-configuratie van Check Point MTD](./media/checkpoint-MTD-1.PNG)

    > [!IMPORTANT]
    > U moet alle apparaatplatformen toevoegen om door te gaan met de volgende stap.

6.  Kies **Accepteren** om de Check Point SandBlast Mobile-app te autoriseren te communiceren met Intune en Azure Active Directory.

7.  Nadat u alle apparaatplatformen hebt ingeschakeld, moet u de Azure AD-beveiligingsgroep invoeren.

8.  Kies **Controleren** en kies **Opslaan** nadat de Azure AD-beveiligingsgroep is geverifieerd.

## <a name="next-steps"></a>Volgende stappen

- [Check Point SandBlast Mobile-apps instellen](mtd-apps-ios-app-configuration-policy-add-assign.md)