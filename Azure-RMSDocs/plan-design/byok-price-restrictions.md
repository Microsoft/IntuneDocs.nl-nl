---
title: BYOK-prijzen en -beperkingen | Azure RMS
description: 
keywords: 
author: cabailey
manager: mbaldwin
ms.date: 08/17/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: f5930ed3-a6cf-4eac-b2ec-fcf63aa4e809
ms.reviewer: esaggese
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 437afd88efebd9719a3db98f8ab0ae07403053f7
ms.openlocfilehash: ece615912d69eda78107c60245620ed36c0affd2


---

# BYOK-prijzen en -beperkingen

*Van toepassing op: Azure Rights Management, Office 365*


Organisaties die een abonnement hebben waarin Azure Rights Management is opgenomen, kunnen door de klant beheerde sleutels (BYOK) in Azure Key Vault gebruiken en het gebruik hiervan gratis registreren. U moet echter een Azure-abonnement hebben dat ondersteuning biedt voor Key Vault met HSM-beveiligde sleutels voor het gebruik van Azure Key Vault. Het gebruik van een sleutel in Azure Key Vault brengt maandelijkse kosten met zich mee. Zie de [pagina met prijzen van Azure Key Vault](https://azure.microsoft.com/en-us/pricing/details/key-vault/) voor meer informatie.

Als er gebruikers zijn die zich hebben aangemeld voor een gratis account voor het gebruik van RMS voor individuele gebruikers, kunt u BYOK en logboekregistratie niet gebruiken omdat er geen tenantbeheerder beschikbaar is om deze functies te configureren.


> [!NOTE]
> Zie voor meer informatie over RMS voor personen [RMS voor personen en Azure Rights Management](../understand-explore/rms-for-individuals.md).

![BYOK biedt geen ondersteuning voor Exchange Online.](../media/RMS_BYOK_noExchange.png)

BYOK en logboekregistratie werken naadloos met elke toepassing die in Azure RMS kan worden geïntegreerd. Dit omvat cloudservices, zoals SharePoint Online, on-premises servers met Exchange en SharePoint die met Azure RMS werken via de RMS-connector, en clienttoepassingen zoals Office 2016 en Office 2013. U krijgt logboeken over sleutelgebruik, ongeacht welke toepassing aanvragen doet bij Azure RMS.

Er is één uitzondering: momenteel **is Azure RMS BYOK niet compatibel met Exchange Online**. Als u Exchange Online wilt gebruiken, raden wij u aan Azure RMS te implementeren in de standaardmodus voor sleutelbeheer, waarbij Microsoft uw sleutel genereert en beheert. U hebt de mogelijkheid om later over te stappen naar BYOK, bijvoorbeeld wanneer Exchange Online Azure RMS BYOK ondersteunt. Als u echter niet kunt wachten, is een andere mogelijkheid Azure RMS nu te implementeren met BYOK, met verminderde RMS-functionaliteit voor Exchange Online (niet-beveiligde e-mailberichten en niet-beveiligde bijlagen blijven volledig functioneel):

-   Beveiligde e-mailberichten of beveiligde bijlagen in Outlook Web Access kunnen niet worden weergegeven.

-   Beveiligde e-mailberichten op mobiele apparaten die gebruikmaken van Exchange ActiveSync IRM, kunnen niet worden weergegeven.

-   Transportontsleuteling (bijvoorbeeld om te scannen op schadelijke software) en logboekontsleuteling zijn niet mogelijk, zodat beveiligde e-mailberichten en beveiligde bijlagen worden overgeslagen.

-   Regels voor transportbeveiliging en preventie van gegevensverlies (DLP) die IRM afdwingen, zijn niet mogelijk, zodat de RMS-beveiliging niet kan worden toegepast met behulp van deze methoden.

-   De server doorzoeken op beveiligde e-mailberichten, zodat beveiligde e-mailberichten worden overgeslagen.

Als u Azure RMS BYOK gebruikt met verminderde RMS-functionaliteit voor Exchange Online, werkt RMS met e-mailclients in Outlook op Windows en Mac, en op andere e-mailclients die geen gebruik maken van Exchange ActiveSync IRM.

Als u vanaf AD RMS migreert naar Azure RMS, hebt u uw sleutel mogelijk als een Trusted Publishing Domain (TPD) geïmporteerd in Exchange Online (in Exchange-terminologie ook aangeduid als BYOK; dit is echter niet hetzelfde als Azure Key Vault BYOK). In dit scenario moet u het TPD verwijderen uit Exchange Online om conflicterende sjablonen en beleidsregels te voorkomen. Zie voor meer informatie [Remove-RMSTrustedPublishingDomain](https://technet.microsoft.com/library/jj200720%28v=exchg.150%29.aspx) in de cmdlets-bibliotheek van Exchange Online.

Soms is de Azure RMS BYOK-uitzondering voor Exchange Online in de praktijk geen probleem. Organisaties die BYOK en logboekregistratie nodig hebben, voeren bijvoorbeeld hun gegevenstoepassingen (Exchange, SharePoint, Office) lokaal uit en gebruiken Azure RMS voor functies die niet zo gemakkelijk beschikbaar zijn bij gebruik van lokale AD RMS (bijvoorbeeld samenwerking met andere bedrijven en toegang vanaf mobiele clients). BYOK en logboekregistratie werken in dit scenario goed en geven de organisatie volledige controle over hun abonnement op Azure RMS.

## Volgende stappen

Als u de beslissing hebt genomen om uw eigen sleutel te beheren, gaat u naar [Uw Azure Rights Management-tenantsleutel implementeren](plan-implement-tenant-key.md#implementing-your-azure-rights-management-tenant-key).

Als u hebt besloten om de standaardconfiguratie te handhaven, waarbij Microsoft uw tenantsleutel beheert, raadpleegt u de sectie [Volgende stappen](plan-implement-tenant-key.md#next-steps) van het artikel 'Uw Azure Rights Management-tenantsleutel plannen en implementeren'.




<!--HONumber=Aug16_HO3-->


