---
title: Hoe toepassingen ondersteuning bieden voor Azure Rights Management | Azure RMS
description: 
keywords: 
author: cabailey
manager: mbaldwin
ms.date: 05/13/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: 2cdc7bde-4044-4021-b887-11476f99afd9
ms.reviewer: esaggese
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 16c2dbbce4234f41941bd3fd92d264df0ae685e2
ms.openlocfilehash: 15167c4e7dbe0fd401e198c80524b39e4ded250d


---

# Hoe toepassingen ondersteuning bieden voor Azure Rights Management

*Van toepassing op: Azure Rights Management, Office 365*

Gebruik de volgende informatie om te begrijpen hoe de meest gangbare toepassingen (zoals Word, Excel, PowerPoint en Outlook) en services (zoals Exchange en SharePoint) voor eindgebruikers gebruik kunnen maken van Microsoft [!INCLUDE[aad_rightsmanagement_1](../includes/aad_rightsmanagement_1_md.md)] om gegevens van uw organisatie te beveiligen. 
> [!NOTE]
> Zie [Vereisten voor Azure Rights Management](../get-started/requirements-azure-rms.md) om de toepassingen en versies die [!INCLUDE[aad_rightsmanagement_1](../includes/aad_rightsmanagement_1_md.md)] (Azure RMS) ondersteunt te controleren.

In sommige gevallen wordt beveiliging van gegevens automatisch toegepast, volgens de beleidsregels die u configureert. Dit is bijvoorbeeld het geval bij SharePoint-bibliotheken, geclassificeerde bestanden en Exchange-transportregels. In andere gevallen moeten gebruikers gegevensbeveiliging zelf toepassen via hun toepassingen door een sjabloon te selecteren of door specifieke opties te selecteren. Dit is bijvoorbeeld het geval wanneer gebruikers een bestand via e-mail delen of een bestand in-place beveiligen door het beperken van toegang tot of het gebruik door geselecteerde gebruikers of gebruikers buiten de organisatie.

Sjablonen maken het gemakkelijker voor gebruikers (en beheerders die beleid configureren) om het juiste beveiligingsniveau toe te passen en de toegang tot personen binnen uw organisatie te beperken. Hoewel [!INCLUDE[aad_rightsmanagement_1](../includes/aad_rightsmanagement_1_md.md)] wordt geleverd met twee standaardsjablonen, is het vaak een goed idee om aangepaste sjablonen te maken, zodat het aantal keren dat er afzonderlijke opties moeten worden opgegeven, wordt beperkt. Zie [Configuring custom templates for Azure Rights Management](../deploy-use/configure-custom-templates.md) (Aangepaste sjablonen configureren voor Azure Rights Management)voor meer informatie.

Voor de gevallen waarin gebruikers zelf gegevensbeveiliging moeten toepassen, moet u hen voorzien van instructies en richtlijnen over hoe en wanneer dit te doen. De instructies moeten specifiek zijn voor de toepassing, de versies die ze gebruiken en de gebruikswijze. Bovendien moeten de richtlijnen voor wanneer en hoe er gegevensbeveiliging moet worden toegepast, geschikt zijn voor uw bedrijf. Zie [Helping users to protect files by using Azure Rights Management](../deploy-use/help-users.md) (Gebruikers helpen bij het beveiligen van bestanden met Azure Rights Management) voor meer informatie.

Zie [Configuring applications for Azure Rights Management](../deploy-use/configure-applications.md) (Toepassingen configureren voor Azure Rights Management) voor meer informatie over het configureren van deze toepassingen voor Azure RMS.

> [!TIP]
> Zie [Azure RMS in actie: wat beheerders en gebruikers zien](what-admins-users-see.md) voor voorbeelden en schermopnamen van toepassingen die Azure RMS gebruiken.

Zoekservices kunnen op verschillende manieren worden geïntegreerd met Rights Management. Bijvoorbeeld: 

- Exchange Online en Exchange-Server gebruiken indexering aan servicezijde zodat de met RMS beveiligde e-mailberichten van een gebruiker automatisch in de zoekresultaten worden weergegeven. 

- SharePoint Online en SharePoint Server passen alleen RMS-beveiliging toe op bestanden die worden gedownload. Dit betekent dat indexerings- en zoekresultaten in SharePoint niet worden beïnvloed door deze oplossing voor documentbeveiliging. Als u echter een document wilt opslaan in SharePoint dat niet moet worden geretourneerd in de zoekresultaten, moet u het document met RMS beveiligen voordat u dit uploadt naar SharePoint.

- Windows Desktop Search gebruikt een gedeelde index voor verschillende gebruikers van het apparaat. Bestanden die met RMS zijn beveiligd, worden niet geïndexeerd om de gegevens in de beveiligde documenten veilig te houden. Dit betekent dat, hoewel uw zoekresultaten geen bestanden bevatten die u hebt beveiligd, u er zeker van kunt zijn dat uw bestanden met gevoelige gegevens niet worden weergegeven in zoekresultaten voor andere gebruikers die zich aanmelden op of verbinding maken met uw pc. 



## Volgende stappen

Meer informatie over hoe elk van de volgende toepassingen Azure RMS ondersteunt:

-   [De RMS-toepassing voor delen voor Windows- en mobiele platforms](sharing-app-support.md)

-   [Office-toepassingen en -services](office-apps-services-support.md)

-   [Bestandsservers met Windows Server en File Classification Infrastructure (FCI)](file-server-support.md)

-   [Andere toepassingen die de RMS API's ondersteunen](api-support.md)




<!--HONumber=Jun16_HO4-->


