---
# required metadata

title: Voorbereiden voor Azure Rights Management | Azure RMS
description:
keywords:
author: cabailey
manager: mbaldwin
ms.date: 04/28/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: afbca2d6-32a7-4bda-8aaf-9f93f5da5abc

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: esaggese
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Voorbereiden voor Azure Rights Management

*Van toepassing op: Azure Rights Management, Office 365*

Wanneer u zich hebt geregistreerd voor een cloudabonnement en u voor uw organisatie een account hebt geregeld voor [!INCLUDE[o365_1](../includes/o365_1_md.md)] of Azure Active Directory, bent u er klaar voor om de [!INCLUDE[aad_rightsmanagement_2](../includes/aad_rightsmanagement_2_md.md)]-service in te schakelen.

Voordat u dit doet, moet u echter eerst voor de volgende zaken zorgen:

-   Gebruikersaccounts en groepen in de cloud; deze kunt u handmatig maken, maar ze kunnen ook automatisch worden gemaakt en gesynchroniseerd vanuit Active Directory Domain Services (AD DS).

    Wanneer u uw on-premises accounts en groepen synchroniseert, hoeven niet alle kenmerken te worden gesynchroniseerd. Als u op zoek bent naar een lijst kenmerken die voor Azure RMS moeten worden gesynchroniseerd, raadpleegt u het gedeelte [Azure RMS](/active-directory/active-directory-aadconnectsync-attributes-synchronized#azure-rms) in de Azure Active Directory-documentatie. Voor een eenvoudige implementatie raden we u aan [Azure AD Connect](/active-directory/active-directory-aadconnectsync-whatis) te gebruiken om uw on-premises mappen te koppelen aan Azure Active Directory. U kunt alle mapsynchronisatiemethoden gebruiken waarmee dit resultaat wordt bereikt.

-   Groepen met e-mailfunctionaliteit in de cloud die u gaat gebruiken met Rights Management. Dit kunnen ingebouwde groepen of handmatig gemaakte groepen zijn met gebruikers die gebruik gaan maken van Rights Management.

    Als u beschikt over Exchange Online, kunt u groepen met e-mailfunctionaliteit maken en gebruiken via het Exchange-beheercentrum. Als u werkt met AD DS en synchroniseert met Azure AD, kunt u groepen met e-mailfunctionaliteit maken en gebruiken. Dit kunnen beveiligingsgroepen of distributiegroepen zijn.

## Rights Management inschakleen
Standaard is [!INCLUDE[aad_rightsmanagement_2](../includes/aad_rightsmanagement_2_md.md)] uitgeschakeld wanneer u zich registreert voor uw [!INCLUDE[o365_2](../includes/o365_2_md.md)]- of Azure AD-account. Als u [!INCLUDE[aad_rightsmanagement_2](../includes/aad_rightsmanagement_2_md.md)] wilt inschakelen voor uw organisatie, moet u de service activeren. Zie voor meer informatie [Azure Rights Management activeren](../deploy-use/activate-service.md).





<!--HONumber=Apr16_HO4-->


