---
title: Zimperium MTD integreren met Microsoft Intune | Microsoft Intune
description: Meer informatie over hoe u de Zimperium Mobile Threat Defense-oplossing (MTD) instelt met Microsoft Intune om toegang tot uw bedrijfsresources met mobiele apparaten te beheren.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 12/04/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 363fd280-1865-4a61-855b-eb75c3c62753
ms.reviewer: davidra
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: b12cec7a01d809eb5a6b6523a73dd224c10c972e
ms.sourcegitcommit: bee072b61cf8a1b8ad8d736b5f5aa9bc526e07ec
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/02/2019
ms.locfileid: "53817191"
---
# <a name="integrate-zimperium-with-intune"></a>Zimperium integreren met Intune

Voer de volgende stappen uit om de Zimperium Mobile Threat Defense-oplossing te integreren met Intune.

## <a name="before-you-begin"></a>Voordat u begint

> [!NOTE]
> De volgende stappen moeten worden uitgevoerd in de [Zimperium MTD-console](https://sso.zimperium.com/signon/aad/).

Zorg ervoor dat u de volgende abonnementen en referenties bij de hand hebt voordat u begint met de integratie van Zimperium met Intune:

-   Microsoft Intune-abonnement

-   Globale Azure Active Directory-beheerdersreferenties om de volgende machtigingen te verlenen:

    -   Aanmelden en gebruikersprofiel lezen

    -   Toegang tot de map als de aangemelde gebruiker

    -   Mapgegevens lezen

    -   Gegevens van een apparaat verzenden naar Intune

-   Administrator-referenties voor toegang tot Zimperium MTD-console.

### <a name="zimperium-app-authorization"></a>Zimperium-app-autorisatie

Het autorisatieproces van de Zimperium-app is als volgt:

-   Verleen de Zimperium-service machtigingen om informatie met betrekking tot de status van apparaten naar Intune te communiceren. Hiertoe moet u globale beheerdersreferenties gebruiken. Het verlenen van machtigingen is een eenmalige bewerking. Nadat de machtigingen zijn verleend, zijn de referenties van de globale beheerder niet meer nodig voor dagelijkse bewerkingen.

-   Zimperium wordt gesynchroniseerd met het Azure Active Directory (AD) Enrollment-groepslidmaatschap om de database van het apparaat te vullen.

-   Toestaan dat Zimperium-beheerconsole Azure AD-enkelvoudige aanmelding (SSO) gebruikt.

-   De app Zimperium toestaan zich aan te melden met behulp van Azure AD-eenmalige aanmelding.

Zie voor meer informatie over toestemming en Azure Active Directory-toepassingen [De machtigingen aanvragen bij een directory-beheerder](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent#request-the-permissions-from-a-directory-admin) in het Azure Active Directory-artikel *Machtigingen en toestemming in het Azure Active Directory v2.0-eindpunt*.


## <a name="to-set-up-zimperium-integration"></a>Instellen van Zimperium-integratie

1.  Ga naar [Zimperium MTD-console](https://sso.zimperium.com/signon/aad/) en meld u aan met uw referenties. Om het installatieproces van de Zimperium-integratie uit te voeren, moet u zich aanmelden als een Azure Active Directory-gebruiker die de rol Globale beheerder heeft. Bij deze eenmalige installatiebewerking worden de globale beheerdersrechten gebruikt om de Zimperium-apps in uw organisatie toestemming te verlenen om te communiceren met Intune. 

2.  Kies **Beheer** in het menu links.

3.  Kies het tabblad **MDM-instellingen**.

4.  Kies **MDM toevoegen** selecteer dan **Microsoft Intune** in de lijst **MDM-provider**.

5.  Nadat u Microsoft Intune als MDM-service hebt ingesteld, wordt het venster voor de  **configuratie van Microsoft Intune**  weergegeven. Kies  **Azure Active Directory toevoegen**  voor elke optie: **Zimperium zConsole**-, **zIPS iOS- en Android- apps** om Zimperium te machtigen voor communicatie met Intune en Azure AD via eenmalige aanmelding voor Azure AD.

    > [!IMPORTANT]  
    > U moet de Zimperium zConsole-, zIPS iOS- en Android-apps toevoegen om het integratieproces met Intune te voltooien.

6.  Kies **Accepteren** om de Zimperium-app toe te staan met Intune en Azure Active Directory te communiceren.

7.  Nadat u de **Zimperium-zConsole**- en de **zIPS iOS- en Android**-apps aan Azure AD hebt toegevoegd, voegt u de Azure AD-beveiligingsgroepen toe. Op die manier kan Zimperium de Azure AD-beveiligingsgroep synchroniseren met de eigen service.

8.  Kies **Voltooien** om de configuratie op te slaan en de eerste synchronisatie met Azure AD-beveiligingsgroepen te starten.

9.  Afmelden bij de Zimperium MTD-console.

## <a name="next-steps"></a>Volgende stappen

-   [Zimperium-apps instellen](mtd-apps-ios-app-configuration-policy-add-assign.md)
