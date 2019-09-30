---
title: Registreren of aanmelden bij Microsoft Intune
description: Zo kunt u zich registreren voor een Microsoft Intune-abonnement of u aanmelden om met uw abonnement aan de slag te gaan.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 01/02/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 0f3ce07a-b718-42a9-bace-f99a8b8abd94
ms.reviewer: angerobe
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 22e5c38be9dc5a8a09888651e471f64bf6739c72
ms.sourcegitcommit: 1494ff4b33c13a87f20e0f3315da79a3567db96e
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/20/2019
ms.locfileid: "71238890"
---
# <a name="sign-up-or-sign-in-to-microsoft-intune"></a>Registreren of aanmelden bij Microsoft Intune

[!INCLUDE [both-portals](./includes/note-for-both-portals.md)]

In dit onderwerp wordt aan systeembeheerders uitgelegd hoe u zich kunt aanmelden voor een Intune-account.

Voordat u zich voor Intune aanmeldt, moet u bepalen of u al een Microsoft Online Services-account, Enterprise Agreement of equivalente volumelicentieovereenkomst hebt. Een Microsoft-volumelicentieovereenkomst of ander Microsoft-cloudservices-abonnement, zoals Office 365 omvat gewoonlijk een werk- of schoolaccount.

Als u al een werk- of schoolaccount hebt **meld u dan aan** met dat account en voeg Intune toe aan uw abonnement. Anders kunt u zich **registreren** voor een nieuw account om Intune te gebruiken voor uw organisatie.

>[!WARNING]
>U kunt een bestaand werk- of schoolaccount niet combineren nadat u zich hebt aangemeld voor een nieuw account.

## <a name="how-to-sign-up-for-intune"></a>Aanmelden voor Intune

1. Ga naar de [Registratiepagina van Intune](https://admin.microsoft.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0%20).

   ![Schermafbeelding van de registratiewebpagina van de evaluatieversie van het Microsoft Intune-account](./media/account-sign-up-site.png)

2. Op de Registratiepagina kunt u zich aanmelden of registreren om een nieuw abonnement van Intune te beheren.

## <a name="post-sign-up-considerations"></a>Overwegingen voor na uw registratie
Nadat u zich hebt geregistreerd voor een nieuw abonnement, ontvangt u een e-mailbericht met gegevens over uw account op het e-mailadres dat u hebt opgegeven tijdens het registratieproces. In deze e-mail wordt bevestigd dat uw abonnement actief is.

Wanneer het registratieproces is voltooid, wordt u omgeleid naar het Microsoft 365-beheercentrum waarin u gebruikers kunt toevoegen en hen licenties kunt toewijzen. Als u alleen cloudgebaseerde accounts hebt met de standaarddomeinnaam onmicrosoft.com, kunt u direct verder gaan om gebruikers toe te voegen en licenties toe te wijzen. Als u echter van plan bent de [aangepaste domeinnaam](custom-domain-name-configure.md) van uw organisatie te gebruiken of [gebruikersaccountgegevens](users-add.md#sync-active-directory-and-add-users-to-intune) vanuit on-premises Active Directory wilt synchroniseren, kunt u dat browservenster sluiten.

## <a name="sign-in-to-microsoft-intune"></a>Aanmelden bij Microsoft Intune
Zodra u zich hebt aangemeld voor Intune, kunt u elk apparaat met een [ondersteunde browser](supported-devices-browsers.md#intune-supported-web-browsers) gebruiken om u aan te melden bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) om de service te beheren.

Standaard moet uw account een van de volgende machtigingen hebben in Azure AD:
- Hoofdbeheerder
- Intune-servicebeheerder (ook wel bekend als Intune-beheerder)

Als u toegang wilt verlenen tot het beheer van de service voor gebruikers met andere machtigingen, raadpleegt u [Op rollen gebaseerd toegangsbeheer](role-based-access-control.md)

### <a name="intune-admin-portal-url"></a>URL van de Intune-beheerportal

Microsoft 365-beheercentrum: https://devicemanagement.microsoft.com

Intune Azure-portal: https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade

Intune voor onderwijs: https://intuneeducation.portal.azure.com

Klassieke Intune-portal: https://manage.microsoft.com De klassieke Intune-portal wordt alleen gebruikt voor het beheren van apparaten die zijn ingeschreven bij de Intune-softwareclient voor pc's

### <a name="urls-for-intune-services-provided-by-office-365"></a>URL's voor Intune-services van Office 365

Microsoft 365 Business: https://portal.microsoft.com/adminportal

Beheer van mobiele apparaten van Office 365: https://portal.office.com/adminportal/home#/MifoDevices

## <a name="see-also"></a>Zie tevens
[U kunt zich niet aanmelden bij Office 365, Azure of Intune](https://support.microsoft.com/help/2412085)
