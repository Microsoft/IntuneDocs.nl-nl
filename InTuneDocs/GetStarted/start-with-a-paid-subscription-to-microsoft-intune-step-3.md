---
title: Active Directory synchroniseren en gebruikers toevoegen aan Intune | Microsoft Intune
description: On-premises gebruikers met Azure AD synchroniseren en beheerdersmachtigingen voor uw Intune-abonnement verlenen
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 08/29/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6e9ec662-465b-4ed4-94c1-cff0fe18f126
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 0d422b421c3716ad576c4fc565b181dec28c947e
ms.openlocfilehash: 786aa2a665a881d13412ecc2d247a8b79a6d09f8


---


# Active Directory synchroniseren en gebruikers toevoegen aan Intune
U kunt adreslijstsynchronisatie configureren voor het importeren van gebruikersaccounts uit de on-premises Active Directory in Microsoft Azure Active Directory (Azure AD). Het koppelen van uw on-premises Active Directory-service aan alle Azure Active Directory-services zorgt ervoor dat het beheer van gebruikersidentiteiten veel eenvoudiger wordt. U kunt ook eenmalige aanmelding configureren om de authenticatie vertrouwd en eenvoudig te maken voor uw gebruikers.

Het wordt u zelfs nog gemakkelijker gemaakt, want wanneer u meerdere services gebruikt met dezelfde [Azure AD-tenant](http://technet.microsoft.com/library/jj573650.aspx#BKMK_WhatIsAnAzureADTenant), zijn de gebruikersaccounts die u eerder hebt gesynchroniseerd, beschikbaar voor alle cloudservices met hetzelfde Azure AD-tenantabonnement.

## On-premises gebruikers synchroniseren met Azure AD
Het enige hulpprogramma dat u nodig hebt om uw gebruikersaccounts te synchroniseren met Azure AD, is de [Azure AD Connect-wizard](https://www.microsoft.com/download/details.aspx?id=47594). De Azure AD Connect-wizard biedt een vereenvoudigde begeleiding voor het verbinden van de on-premises infrastructuur voor identiteiten aan de cloud.  Kies uw topologie en behoeften (een of meer mappen, wachtwoordsynchronisatie of federatie) om alle onderdelen door de wizard te laten implementeren en configureren die nodig zijn om de verbinding te laten werken. Inclusief: synchronisatieservices, Active Directory Federation Services (AD FS) en de Azure AD PowerShell-module.

> [!TIP]
> Azure AD Connect bevat functionaliteit die eerder is uitgebracht als Dirsync en Azure AD Sync. Lees meer over [adreslijstintegratie](http://technet.microsoft.com/library/jj573653.aspx). Zie [Overeenkomsten tussen Active Directory en Azure AD](http://technet.microsoft.com/library/dn518177.aspx) voor meer informatie over de voordelen van het synchroniseren van gebruikersaccounts vanuit de lokale directory naar Azure AD.

## Beheerdersbevoegdheden toekennen
Nadat u gebruikers aan uw Intune-abonnement hebt toegevoegd, raden we u aan om aan enkele gebruikersaccounts [beheerdersreferenties](administrative-accounts-websites-perms.md) te verlenen. De console die u gebruikt om beheerdersreferenties toe te wijzen, is afhankelijk van het type beheerder dat u wilt toewijzen:

-   **Tenantbeheerder**: gebruik de **[!INCLUDE[wit_icp_1](../includes/wit_icp_1_md.md)]** om dit type beheerder toe te wijzen voor het beheren van uw abonnement, met inbegrip van facturering, cloudopslag en het beheren van de gebruikers die [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] kunnen gebruiken.

-   **Servicebeheerder**: gebruik de **[!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)]** om dit type beheerder toe te wijzen voor dagelijkse taken, waaronder het beheer van mobiele apparaten of computers, het implementeren van beleid of software en het uitvoeren van rapporten.


### Volgende stappen
Gefeliciteerd. U hebt zojuist stap 3 van de *Snelstartgids voor Intune* voltooid.

>[!div class="step-by-step"]

>[&larr; **Domeininstellingen**](.\start-with-a-paid-subscription-to-microsoft-intune-step-2.md)     [**Intune-licenties beheren** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-4.md)  



<!--HONumber=Oct16_HO4-->


