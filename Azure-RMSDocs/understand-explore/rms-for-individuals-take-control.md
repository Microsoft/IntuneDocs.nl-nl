---
title: Hoe beheerders accounts kunnen beheren die zijn gemaakt voor RMS voor personen | Azure RMS
description: 
keywords: 
author: cabailey
manager: mbaldwin
ms.date: 04/28/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: a83880d0-f0f9-4a32-9e00-2f6635d7cc8d
ms.reviewer: esaggese
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 0f355da35dff62ecee111737eb1793ae286dc93e
ms.openlocfilehash: df006a27c97884c47c9bb5fb04bfa181a13b7443


---



# Hoe beheerders accounts kunnen beheren die zijn gemaakt voor RMS voor personen

*Van toepassing op: Azure Rights Management*


Als u het RMS voor personen-abonnement van uw organisatie niet wilt converteren naar een betaald abonnement, kunt u toch de gebruikersaccounts beheren in de Azure-map die is gemaakt voor uw organisatie. Dit doet u als volgt:

-   Implementeer oplossingen voor mappenintegratie voor Azure Active Directory en de Active Directory Domain Services-infrastructuur. U kunt accounts en wachtwoorden synchroniseren, zodat gebruikers geen nieuwe accounts hoeven te maken om Rights Management te kunnen gebruiken. Het on-premises wachtwoordbeleid is vervolgens van toepassing op de nieuwe Azure-gebruikersaccounts. U kunt ook wachtwoorden synchroniseren, zodat gebruikers geen ander wachtwoord hoeven te onthouden om Rights Management te kunnen gebruiken.

-   U kunt voorkomen dat gebruikers zich registreren voor het gebruik van Azure Rights Management met het RMS voor personen-abonnement. In de meeste gevallen levert dit niet veel op, omdat gebruikers vervolgens onbeveiligde bestanden kunnen delen (wat een risico kan zijn voor het bedrijf) of bestanden op een andere manier kunnen beveiligen, waarbij de IT-afdeling geen toegang heeft tot de gegevens. Als u echter wilt voorkomen dat gebruikers zich registreren voor het gebruik van RMS voor personen, maakt u uzelf eigenaar van de Azure-map in uw organisatie en voert u vervolgens een van deze handelingen uit:

    -   Voorkom dat gebruikers zich registreren voor selfserviceabonnementen waaronder RMS voor personen.  Dit kan momenteel niet worden ingesteld voor afzonderlijke services. De instelling is van toepassing op alle Azure-abonnementen die gebruikmaken van het selfserviceproces. Stel om dit te doen de parameter **AllowAdHocSubscriptions** in op false met de [Set-MsolCompanySettings](http://technet.microsoft.com/library/dn194127.aspx)-cmdlet uit de Windows PowerShell-module voor Azure Active Directory. Bijvoorbeeld: **Set-MsolCompanySettings -AllowAdHocSubscriptions $false**

    -   Voorkom dat gebruikers een nieuw account maken in Azure. Dit betekent dat alleen gebruikers die al een account hebben in Azure, zich kunnen registreren voor self-serviceabonnementen, waaronder RMS voor personen.  Stel om dit te doen de parameter **AllowEmailVerifiedUsers** in op false met de [Set-MsolCompanySettings](http://technet.microsoft.com/library/dn194127.aspx)-cmdlet uit de Windows PowerShell-module voor Azure Active Directory. Bijvoorbeeld: **Set-MsolCompanySettings -AllowEmailVerifiedUsers $false -AllowAdHocSubscriptions $true**

    -   Synchroniseer de Active Directory Domain Services-infrastructuur met Azure Active Directory. Deze actie voorkomt dat er nieuwe accounts worden gemaakt wanneer gebruikers zich registreren voor selfserviceabonnementen zoals RMS voor personen. U kunt accounts die eerder zijn gemaakt in de Azure-map, verwijderen of uitschakelen.

U dient een Azure-abonnement te hebben en eigenaar van de map te zijn om de gebruikersaccounts in de Azure-map te beheren of om te voorkomen dat gebruikers zich registreren voor RMS voor personen. Als u nog geen Azure-abonnement hebt, kunt u er gratis een krijgen. Als er tijdens het selfserviceproces automatisch een map voor u is gemaakt, maakt u uzelf eigenaar van het domein dat is gebruikt om de map te maken. Als u al eigenaar bent van een Azure-map, maar gebruikers een nieuw domein hebben opgegeven dat u gebruikt in uw organisatie, voegt u dit domein samen met de bestaande map. Zie de instructies in [Wat is selfserviceregistratie voor Azure?](https://azure.microsoft.com/documentation/articles/active-directory-self-service-signup/) (Engelstalig) voor meer informatie.


## Volgende stappen

Als gebruikers (in plaats van beheerders) accounts kunnen maken in Azure Active Directory voor RMS voor personen, hoe kunt u dan nagaan of zij dit hebben gedaan?  Zie [Nagaan of uw gebruikers zich hebben geregistreerd voor RMS voor personen](rms-for-individuals-identify-sign-up.md).



<!--HONumber=Jun16_HO4-->


