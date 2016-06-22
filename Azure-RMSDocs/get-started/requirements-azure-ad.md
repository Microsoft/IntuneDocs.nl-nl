---
# required metadata

title: "Azure RMS-vereisten: Azure AD-map | Azure RMS"
description:
keywords:
author: cabailey
manager: mbaldwin
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: ed25aa83-e272-437b-b445-3f01e985860c

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: esaggese
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Azure RMS-vereisten: Azure AD-map

*Van toepassing op: Azure Rights Management, Office 365*


U moet een Azure AD-map hebben om Azure Rights Management (Azure RMS) te kunnen gebruiken. U meldt zich met het account van uw organisatie voor deze map aan bij de klassieke Azure-portal, waar u onder andere Rights Management-sjablonen kunt configureren en beheren.

Als u nog geen Azure-abonnement voor uw organisatie hebt, kunt u er een krijgen door u aan te melden voor een gratis proefversie. Ga naar de pagina [Aan de slag met Azure](https://account.windowsazure.com/organization) en volg de instructies.

Zie de volgende resources in de Azure Active Directory-documentatie voor meer informatie:

-   [Wat is een Azure AD-map?](/active-directory/active-directory-whatis)

-   [Hoe Azure-abonnementen worden gekoppeld aan Azure Active Directory](/active-directory/active-directory-how-subscriptions-associated-directory)

Als u uw Azure AD-map wilt integreren in uw on-premises AD-forests, raadpleegt u [Uw on-premises identiteiten integreren met Azure Active Directory](/active-directory/active-directory-aadconnect).

> [!NOTE] Als u mobiele apparaten of Mac-computers hebt waarop on-premises verificaties worden uitgevoerd met AD FS of een vergelijkbare verificatieprovider:
> 
> -   U moet AD FS gebruiken op de minimale serverversie van **Windows Server 2012 R2** of een beroep doen op een alternatieve verificatieprovider die het protocol OAuth 2.0 ondersteunt.

## Azure Multi-Factor Authentication (MFA) en Azure RMS
Als u Multi-Factor Authentication (MFA) wilt gebruiken met Azure RMS, hebt u ten minste een van deze producten nodig:

-   Office 2013 (minimumversie):

    -   Als u Office 2013 hebt, moet u ook de [update van 9 juni 2015 voor Office 2013 (KB3054853)](https://support.microsoft.com/kb/3054853) installeren. Voor meer informatie over deze update en over hoe moderne verificatie op Active Directory Authentication Library (ADAL) gebaseerde aanmelding toevoegt aan Office 2013, raadpleegt u [Office 2013: aangekondigd openbaar voorbeeld van moderne verificatie](https://blogs.office.com/2015/03/23/office-2013-modern-authentication-public-preview-announced/) in de Office-blog.

-   Rights Management-toepassing voor delen voor Windows:

    -   U moet minimaal versie 1.0.1908.0 hebben geïnstalleerd. U kunt dit controleren via Configuratiescherm > Programma's en onderdelen. Zie voor meer informatie over de toepassing voor delen [Rights Management-toepassing voor delen voor Windows](../rms-client/sharing-app-windows.md).

-   Rights Management-app voor delen voor mobiele apparaten en Mac-computers:

    -   Zorg ervoor dat u de meest recente versie hebt geïnstalleerd. MFA-ondersteuning is opgenomen in de release van september 2015 van de RMS-app voor delen.

Configureer vervolgens uw MFA-oplossing:

-   Voor door Microsoft beheerde tenants (u hebt Azure Active Directory of Office 365):

    -   Configureer Azure MFA om MFA voor gebruikers af te dwingen. Zie voor instructies [Aan de slag met Azure Multi-Factor Authentication in de cloud](/multi-factor-authentication/multi-factor-authentication-get-started-cloud) in de Multi-factor Authentication-documentatie.

        Zie [Wat is Azure Multi-Factor Authentication?](/multi-factor-authentication/multi-factor-authentication) voor meer informatie.

-   Voor federatieve tenants (u werkt met on-premises federatieve servers):

    -   Configureer uw federatieve servers voor Azure Active Directory of Office 365. Als u bijvoorbeeld AD FS gebruikt, raadpleegt u [Extra verificatiemethoden configureren voor AD FS](https://technet.microsoft.com/library/dn758113.aspx) op TechNet.

        Zie voor meer informatie over dit scenario [Werken met Office 365 – Identiteitsprogramma nu gestroomlijnd](https://blogs.office.com/2014/01/30/the-works-with-office-365-identity-program-now-streamlined/) op de Office-blog.

## Volgende stappen
Zie [Vereisten voor Azure Rights Management](requirements-azure-rms.md) voor informatie over andere vereisten.



<!--HONumber=May16_HO2-->


