---
title: Skycure configureren met Intune voor het gebruik van eenmalige aanmelding voor Azure Active Directory
titlesuffix: Azure portal
description: Skycure configureren met Intune voor het gebruik van eenmalige aanmelding voor Azure Active Directory
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e0466ac4-4942-4c4c-b8af-996b597c701d
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 93e7f1a21c9badb3cc3ccdf02432267b271e6e94
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/09/2017
---
# <a name="configure-skycure-to-use-azure-active-directory-single-sign-on-sso"></a>Skycure configureren voor het gebruik van de eenmalige aanmelding voor Azure Active Directory

Eenmalige aanmelding voor Azure Active Directory wordt gebruikt wanneer u Intune integreert met Skycure. Hier volgen enkele belangrijke voordelen:

-   **Beheerders** kunnen dezelfde referenties gebruiken en hoeven deze niet telkens opnieuw in te voeren wanneer ze zich aan- en afmelden bij de Microsoft-portals (Intune, Azure) en de Skycure-beheerconsole.

-   **Eindgebruikers** kunnen dezelfde Azure AD-referenties gebruiken en hoeven deze niet telkens opnieuw in te voeren wanneer ze zich aan- en afmelden bij de Skycure-apps.

Hieronder volgen de stappen voor de integratie van Skycure met de eenmalige aanmelding voor Azure Active Directory.

## <a name="to-retrieve-the-azure-active-directory-tenant-id"></a>De tenant-id voor Azure Active Directory ophalen

U moet de tenant-id voor Azure AD ophalen.

1.  Ga naar de [Azure-portal](https://portal.azure.com/) en meld u aan met uw referenties.

2.  Wanneer het **dashboard** wordt weergegeven, kiest u **Azure Active Directory**.

    ![Azure AD-dashboard](./media/skycure-sso-1.png)

3.  De blade **Azure Active Directory** wordt geopend en u kiest vervolgens **Eigenschappen**.

    ![De blade Eigenschappen voor Azure Active Directory](./media/skycure-sso-2.png)

4.  Klik op het **kopieerpictogram** onder de **Directory-id voor de tenant** op de blade **Eigenschappen voor Azure Active Directory**.

5. Plak de gekopieerde Directory-id in een tekstbestand zodat u deze later kunt gebruiken. De Directory-id is later nodig bij de integratie van Skycure en Intune.

    ![Azure AD-dashboard](./media/skycure-sso-3.png)

## <a name="allow-skycure-to-communicate-with-azure-active-directory"></a>Skycure toestaan om te communiceren met Azure Active Directory

1.  Voer de onderstaande URL in uw browser in. In plaats van **DIRECTORY_ID** voert u uw tenant-id voor Azure Active Directory in die u eerder naar het tekstbestand hebt gekopieerd.

        https://login.microsoftonline.com/<DIRECTORY_ID>/oauth2/authorize?client_id=28fd67fdb1794629a8b0dad420b697c7&prompt=admin_consent&redirect_uri=https%3A%2F%2Fmc.skycure.com%2Fapi%2Fexternal%2Fmdm%2Faad_app_consent%2Fmanagement_callback&response_type=code

2.  U moet zich aanmelden met uw Azure Active Directory-referenties. Klik op **Accepteren** om door te gaan.

![Aanmeldingspagina van Azure AD](./media/skycure-sso-4.png)

## <a name="create-an-azure-ad-security-group-for-skycure-optional"></a>Een Azure AD-beveiligingsgroep maken voor Skycure (optioneel)

U wilt mogelijk een speciale gebruikersgroep maken voor gebruikers met Skycure op hun computer (bijvoorbeeld Skycure-gebruikers). Dit kan nuttig zijn wanneer u Skycure-activiteiten analyseert aan de hand van de rapporten.

-   Meer informatie over [een groep maken en leden toevoegen in Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-groups-create-azure-portal).

> [!NOTE] 
> U kunt ook een bestaande Azure AD-beveiligingsgroep gebruiken.

## <a name="configure-the-azure-ad-account-to-integrate-intune-with-skycure"></a>Het Azure AD-account configureren voor de integratie van Intune met Skycure

1.  Voer in de [Skycure-beheerconsole](https://aad.skycure.com/) de tenant-id voor Azure Active Directory in die u eerder in het tekstbestand hebt opgeslagen.

![Het veld voor de tenant-id van Azure Active Directory in de Skycure-beheerconsole](./media/skycure-sso-5.png)

> [!IMPORTANT] 
> Skycure controleert of de tenant-id voor Azure AD bestaat door een query uit te voeren voor Azure AD. Wanneer Skycure de tenant-id heeft gevonden, kan de beheerder verdergaan met de volgende stap, de eenvoudige integratie.

## <a name="next-steps"></a>Volgende stappen

[Het configuratiebeleid voor de iOS-app voor Skycure downloaden](skycure-ios-app-configuration-policy-download.md)
