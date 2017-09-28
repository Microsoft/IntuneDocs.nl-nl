---
title: Zimperium integreren met Intune
titleSuffix: Intune on Azure
description: Intune integreren met Zimperium
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 09/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 363fd280-1865-4a61-855b-eb75c3c62753
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1b4adb2db14c2e1c83be8e7b3644944c1910cb97
ms.sourcegitcommit: d434dfab7ef7a6c4082d675717fa22d5581b4f51
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/19/2017
---
# <a name="integrate-zimperium-with-intune"></a>Zimperium integreren met Intune

U moet de volgende stappen volgen om de Zimperium Mobile Threat Defense-oplossing te integreren met Intune.

## <a name="before-you-begin"></a>Voordat u begint

> [!NOTE]
> De volgende stappen dienen te worden genomen in de [Zimperium MTD-console](https://staging2-console.zimperium.com).

Zorg ervoor dat u het volgende hebt voordat u begint met de integratie van Zimperium met Intune:

-   Microsoft Intune-abonnement

-   Azure Active Directory-beheerdersreferenties om de volgende machtigingen te verlenen:

    -   Aanmelden en gebruikersprofiel lezen

    -   Toegang tot de map als de aangemelde gebruiker

    -   Mapgegevens lezen

    -   Gegevens van een apparaat verzenden naar Intune

-   Administrator-referenties voor toegang tot Zimperium MTD-console.

### <a name="zimperium-app-authorization"></a>Zimperium-app-autorisatie

Het autorisatieproces van de Zimperium-app bestaat uit het volgende:

-   De Zimperium-service toestaan informatie met betrekking tot de status van apparaten naar Intune te communiceren.

-   Zimperium wordt gesynchroniseerd met het Azure AD Enrollment-groepslidmaatschap om de database van het apparaat te vullen.

-   Toestaan dat Zimperium-beheerconsole Azure AD-enkelvoudige aanmelding (SSO) gebruikt.

-   De app Zimperium toestaan zich aan te melden met behulp van Azure AD-eenmalige aanmelding.

## <a name="to-set-up-zimperium-integration"></a>Instellen van Zimperium-integratie

1.  Ga naar [Zimperium MTD-console](https://staging2-console.zimperium.com) en meld u aan met uw referenties.

2.  Kies **Beheer** in het menu links.

3.  Kies het tabblad **MDM-instellingen**.

4.  Kies **MDM toevoegen** selecteer dan **Microsoft Intune** in de lijst **MDM-provider**.

5.  Als u Microsoft Intune als MDM-service hebt ingesteld, verschijnt het venster **Configuratie van Microsoft Intune**, kies **Azure Active Directory toevoegen** voor elke volgende optie: **Zimperium zConsole**, **zIPS iOS- en Android-apps** om Zimperium te autoriseren te communiceren met Intune en Azure AD via Azure AD eenmalige aanmelding.

    > [!IMPORTANT]
    > U moet de Zimperium-zConsole, zIPS iOS- en Android-apps toevoegen om het integratieproces met Intune te voltooien.

6.  Kies **Accepteren** om de Zimperium-app te autoriseren te communiceren met Intune en Azure Active Directory.

7.  Nadat u de **Zimperium-zConsole** en de **zIPS iOS- en Android-**apps aan Azure AD hebt toegevoegd, moet u de beveiligingsgroepen van Azure AD toevoegen, zodat Zimperium de Azure AD-beveiligingsgroep kan synchroniseren met de eigen service.

8.  Kies **Voltooien** om de configuratie op te slaan en de eerste synchronisatie met Azure AD-beveiligingsgroepen te starten.

## <a name="next-steps"></a>Volgende stappen

-   [Zimperium-apps instellen](mtd-apps-ios-app-configuration-policy-add-assign.md)
