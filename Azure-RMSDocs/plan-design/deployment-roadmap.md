---
title: Azure Rights Management-implementatieschema | Azure RMS
description: Gebruik de volgende stappen om Azure Rights Management (Azure RMS) voor te bereiden, te implementeren en te beheren voor uw organisatie.
author: cabailey
manager: mbaldwin
ms.date: 08/24/2016
ms.topic: article
ms.prod: 
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: 086600c2-c5d8-47ec-a4c0-c782e1797486
ms.reviewer: esaggese
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 024a29d7c7db2e4c0578a95c93e22f8e7a5b173e
ms.openlocfilehash: 13ec3a88eb1c072bf94b6c54e3e4d97e45cc8eb2


---

# Azure Rights Management-implementatieschema

>*Van toepassing op: Azure Rights Management, Office 365*

Gebruik de volgende stappen om Azure Rights Management (Azure RMS) voor te bereiden, te implementeren en te beheren voor uw organisatie.

Als u Azure RMS alleen snel wilt proberen in plaats van dit uit te rollen in een productieomgeving, raadpleegt u [Zelfstudie voor snel starten met Azure Rights Management](../get-started/quick-start-tutorial.md).

Zie voor een lijst met specifieke scenario's, bijbehorende configuratiestappen en eindgebruikersdocumentatie de [Snelle implementatiehandleiding voor Azure Rights Management](../get-started/rapid-deployment-guide.md).

> [!IMPORTANT]
> Voordat u de volgende stappen uitvoert, zorgt u ervoor dat u [Vereisten voor Azure Rights Management](../get-started/requirements-azure-rms.md) hebt gelezen.

## Stap 1: controleer of u een abonnement hebt met inbegrip van Azure Rights Management
Er is meer dan één type abonnement met inbegrip van [!INCLUDE[aad_rightsmanagement_1](../includes/aad_rightsmanagement_1_md.md)]. Zie [Cloudabonnementen die Azure RMS ondersteunen](../get-started/requirements-subscriptions.md) en controleer of uw abonnement de functionaliteit omvat die u wilt gebruiken in uw organisatie. Hiertoe raadpleegt u de tabel in [Vergelijking van Rights Management Services (RMS)-aanbiedingen](https://technet.microsoft.com/dn858608). U moet een licentie van dit abonnement toewijzen aan elke gebruiker in uw organisatie die bestanden en e-mailberichten gaat beveiligen met Azure RMS.

## Stap 2: bereid de tenant-serviceaccount voor op het gebruik van Rights Management
Voordat u begint met het gebruik van [!INCLUDE[aad_rightsmanagement_2](../includes/aad_rightsmanagement_2_md.md)], doet u ter voorbereiding het volgende:

1.  Zorg ervoor dat uw Azure of Office 365-tenant de gebruikersaccounts en -groepen bevat die worden gebruikt door Azure RMS voor verificatie van gebruikers van uw organisatie. Indien nodig maakt u dit account en deze groepen of synchroniseert u deze vanuit uw lokale map. Zie voor meer informatie [Voorbereiden voor Azure Rights Management](prepare.md).

2.  Beslis of u wilt dat Microsoft uw tenantsleutel beheert (de standaardinstelling) of dat u uw tenantsleutel zelf wilt genereren en beheren (ook bekend als Bring Your Own Key ( BYOK)). Houd er rekening mee dat u op dit moment BYOK niet kunt gebruiken als u Exchange Online gebruikt. Zie [Uw Azure Rights Management-tenantsleutel plannen en implementeren](plan-implement-tenant-key.md) voor meer informatie.

3.  Installeer de Windows PowerShell-module voor [!INCLUDE[aad_rightsmanagement_2](../includes/aad_rightsmanagement_2_md.md)] op ten minste één computer die toegang tot internet heeft. U kunt deze stap nu of later uitvoeren. Zie voor meer informatie [Windows PowerShell voor Azure Rights Management installeren](../deploy-use/install-powershell.md).

4.  Als u momenteel lokale Rights Management Services gebruikt: voer een migratie uit om de sleutels, sjablonen en URL's te verplaatsen naar de cloud. Zie [Migreren van AD RMS naar Azure Rights Management](migrate-from-ad-rms-to-azure-rms.md) voor meer informatie.

5.  Activeer Rights Management, zodat u kunt beginnen met het gebruik van de service. Als een gefaseerde implementatie vereist is, configureert u de besturingselementen voor gebruikersvoorbereiding zodanig dat het gebruik beperkt is tot specifieke gebruikers. Zie voor meer informatie [Azure Rights Management activeren](../deploy-use/activate-service.md).

Overweeg eventueel het volgende te configureren.

-   Aangepaste sjablonen als de standaardrechtenbeleidssjablonen niet geschikt zijn voor uw organisatie. U kunt deze stap nu of later uitvoeren. Zie [Configuring custom templates for Azure Rights Management](../deploy-use/configure-custom-templates.md) (Aangepaste sjablonen configureren voor Azure Rights Management)voor meer informatie.

-   Registreer het gebruik in een logboek zodat u kunt controleren hoe uw organisatie Rights Management gebruikt. U kunt deze stap nu of later uitvoeren. Zie [Azure Rights Management-gebruik analyseren en vastleggen in een logboek](../deploy-use/log-analyze-usage.md) voor meer informatie.

## Stap 3: configureer uw toepassingen en services voor Rights Management
Configuratie van uw toepassingen en services omvat mogelijk het installeren van de Rights Management-toepassing voor delen en het bieden van ondersteuning voor de functies van Information Rights Management (IRM) in SharePoint Online of Exchange Online. Zie [Toepassingen configureren voor Azure Rights Management](../deploy-use/configure-applications.md) voor meer informatie.

Als u bestaande IT-services hebt die bestanden moeten controleren die worden beveiligd door Azure RMS, zoals oplossingen voor preventie van gegevenslekken, gateways voor inhoudversleuteling en antimalwareproducten: configureer de serviceaccounts als supergebruikers voor Azure RMS. Zie [Configuring super users for Azure Rights Management and discovery services or data recovery](../deploy-use/configure-super-users.md) (Supergebruikers configureren voor Azure Rights Management en detectieservices of gegevensherstel) voor meer informatie.

Voor bulksgewijze beveiliging of bulksgewijze opheffing van beveiliging voor alle bestandstypen installeert u het RMS-beveiligingshulpprogramma dat gebruikmaakt van de RMS Protection PowerShell-module. Zie [RMS Protection Cmdlets](https://msdn.microsoft.com/library/mt433195.aspx) (RMS-beveiligingscmdlets) voor meer informatie.

Als u lokale services hebt die u wilt gebruiken met Azure Rights Management, installeert en configureert u de Rights Management-connector. Zie [De Azure Rights Management-connector implementeren](../deploy-use/deploy-rms-connector.md) voor meer informatie.

## Stap 4: publiceer en gebruik inhoud met rechtenbescherming
U bent nu klaar om beveiligde inhoud te publiceren en te gebruiken, en in het logboek te registreren u hoe uw bedrijf Rights Management gebruikt. Zie voor meer informatie [Gebruikers helpen bij het beveiligen van bestanden door gebruik te maken van Azure Rights Management](../deploy-use/help-users.md) en [Azure Rights Management-gebruik analyseren en vastleggen in een logboek](../deploy-use/log-analyze-usage.md).

Als u geïnteresseerd bent in het automatisch beveiligen van bestanden met Infrastructuur voor bestandsclassificatie op een Windows-bestandsserver, raadpleegt u [MS-beveiliging met infrastructuur voor bestandsclassificatie (FCI) voor Windows Server](../rms-client/configure-fci.md).

## Stap 5: beheer Rights Management voor uw tenantaccount, indien nodig
Als u begint met het gebruik van [!INCLUDE[aad_rightsmanagement_2](../includes/aad_rightsmanagement_2_md.md)], is de [!INCLUDE[aad_rightsmanagement_2](../includes/aad_rightsmanagement_2_md.md)]-module voor Windows PowerShell-scripts wellicht nuttig voor scripts of het automatiseren van beheerwijzigingen. Zie voor meer informatie [Beheer van Azure Rights Management met Windows PowerShell](../deploy-use/administer-powershell.md).





<!--HONumber=Aug16_HO4-->


