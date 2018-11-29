---
title: Zimperium MTD integreren met Microsoft Intune
titleSuffix: ''
description: Meer informatie over hoe u de Zimperium Mobile Threat Defense-oplossing (MTD) instelt met Microsoft Intune om toegang tot uw bedrijfsresources met mobiele apparaten te beheren.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 12/29/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 363fd280-1865-4a61-855b-eb75c3c62753
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 68896a363cab37aabe9a597872da0fe75c44c473
ms.sourcegitcommit: 3903f20cb5686532ccd8c36aa43c5150cee7cca2
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/21/2018
ms.locfileid: "52267234"
---
# <a name="integrate-zimperium-with-intune"></a>Zimperium integreren met Intune

Voer de volgende stappen uit om de Zimperium Mobile Threat Defense-oplossing te integreren met Intune.

## <a name="before-you-begin"></a>Voordat u begint

> [!NOTE]
> De volgende stappen moeten worden uitgevoerd in de [Zimperium MTD-console](https://sso.zimperium.com/signon/aad/).

Zorg ervoor dat u de volgende abonnementen en referenties bij de hand hebt voordat u begint met de integratie van Zimperium met Intune:

-   Microsoft Intune-abonnement

-   Azure Active Directory-beheerdersreferenties om de volgende machtigingen te verlenen:

    -   Aanmelden en gebruikersprofiel lezen

    -   Toegang tot de map als de aangemelde gebruiker

    -   Mapgegevens lezen

    -   Gegevens van een apparaat verzenden naar Intune

-   Administrator-referenties voor toegang tot Zimperium MTD-console.

### <a name="zimperium-app-authorization"></a>Zimperium-app-autorisatie

Het autorisatieproces van de Zimperium-app is als volgt:

-   De Zimperium-service toestaan informatie met betrekking tot de status van apparaten naar Intune te communiceren.

-   Zimperium wordt gesynchroniseerd met het Azure Active Directory (AD) Enrollment-groepslidmaatschap om de database van het apparaat te vullen.

-   Toestaan dat Zimperium-beheerconsole Azure AD-enkelvoudige aanmelding (SSO) gebruikt.

-   De app Zimperium toestaan zich aan te melden met behulp van Azure AD-eenmalige aanmelding.

## <a name="to-set-up-zimperium-integration"></a>Instellen van Zimperium-integratie

1.  Ga naar [Zimperium MTD-console](https://sso.zimperium.com/signon/aad/) en meld u aan met uw referenties.

2.  Kies **Beheer** in het menu links.

3.  Kies het tabblad **MDM-instellingen**.

4.  Kies **MDM toevoegen** selecteer dan **Microsoft Intune** in de lijst **MDM-provider**.

5.  Nadat u Microsoft Intune als MDM-service hebt ingesteld, wordt het venster **Configuratie van Microsoft Intune** weergegeven. Kies **Azure Active Directory toevoegen** voor elke volgende optie: **Zimperium zConsole**, **zIPS iOS- en Android-apps** om toe te staan dat Zimperium via eenmalige aanmelding voor Azure AD communiceert met Intune en Azure AD.

    > [!IMPORTANT]
    > U moet de Zimperium-zConsole, zIPS iOS- en Android-apps toevoegen om het integratieproces met Intune te voltooien.

6.  Kies **Accepteren** om de Zimperium-app toe te staan met Intune en Azure Active Directory te communiceren.

7.  Nadat u de **Zimperium-zConsole** en de **zIPS iOS- en Android-** apps aan Azure AD hebt toegevoegd, voegt u de beveiligingsgroepen van Azure AD toe. Op die manier kan Zimperium de Azure AD-beveiligingsgroep synchroniseren met de eigen service.

8.  Kies **Voltooien** om de configuratie op te slaan en de eerste synchronisatie met Azure AD-beveiligingsgroepen te starten.

## <a name="next-steps"></a>Volgende stappen

-   [Zimperium-apps instellen](mtd-apps-ios-app-configuration-policy-add-assign.md)
