---
title: Bestandsservers met Windows Server en de infrastructuur voor bestandsclassificatie (FCI) | Azure RMS
description: 
keywords: 
author: cabailey
manager: mbaldwin
ms.date: 04/28/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: 8fdad425-5daf-4ce1-822f-9d2fb0b87df1
ms.reviewer: esaggese
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 0f355da35dff62ecee111737eb1793ae286dc93e
ms.openlocfilehash: 839be5a8a45c2322127694dc0bdc306ff445c314


---


# Bestandsservers met Windows Server en de infrastructuur voor bestandsclassificatie (FCI)

*Van toepassing op: Azure Rights Management, Office 365*


Als u Windows Server configureert voor gebruik van een infrastructuur voor bestandsclassificatie, kan de functie Bestandsserverbronbeheer lokale bestanden scannen en bepalen of ze gevoelige gegevens bevatten. Als er bestanden zijn die aan deze criteria voldoen, worden ze gemarkeerd met de classificatie-eigenschappen die een beheerder definieert. De infrastructuur voor bestandsclassificatie kan dan automatisch actie ondernemen op basis van de classificatie. Een van deze acties omvat het toepassen van informatiebeveiliging met behulp van [!INCLUDE[aad_rightsmanagement_1](../includes/aad_rightsmanagement_1_md.md)] en het implementeren van de Rights Management-connector (ook wel bekend als de RMS-connector). Office-bestanden worden vervolgens automatisch beveiligd door Azure RMS.

Als u alle bestandstypen wilt beveiligen, gebruikt u niet de RMS-connector, maar voert u een Windows PowerShell-script uit met behulp van cmdlets uit het [RMS-beveiligingshulpprogramma](https://www.microsoft.com/en-us/download/details.aspx?id=47256).

De classificatiebeleidsregels kunnen volledig worden geconfigureerd en maximaal worden uitgebreid, zodat u het potentiële lekken van gegevens door niet-machtigde en gemachtigde gebruikers kunt voorkomen. U vermindert hiermee ook het risico dat netwerkbeheerders gegevens lekken, omdat u beleidsregels kunt configureren waarvoor de beheerders geen toegang hoeven te hebben tot de bestanden.

Voor instructies over het implementeren en configureren van de RMS-connector voor Office-bestanden raadpleegt u [De Azure Rights Management-connector implementeren](../deploy-use/deploy-rms-connector.md).

Voor instructies over het gebruik van het Windows PowerShell-script voor alle bestandstypen raadpleegt u [RMS-beveiliging met infrastructuur voor bestandsclassificatie &#40;FCI&#41; voor Windows Server](../rms-client/configure-fci.md).



## Volgende stappen
Nu u begrijpt hoe toepassingen en services ondersteuning bieden voor Azure RMS, bent u mogelijk geïnteresseerd in een vergelijking van Azure RMS met de on-premises versie van Rights Management: Active Directory Rights Management Services (AD RMS). Voor een vergelijking van functies, vereisten en beveiligingsmechanismen raadpleegt u [Azure Rights Management en AD RMS vergelijken](compare-azure-rms-ad-rms.md).





<!--HONumber=Jul16_HO3-->


