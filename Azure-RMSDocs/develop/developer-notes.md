---
title: Richtlijnen en informatie voor ontwikkelaars | Azure RMS
description: Dit onderwerp bevat informatie over specifieke hulp voor verschillende belangrijke ontwikkelscenario's.
keywords: 
author: bruceperlerms
manager: mbaldwin
ms.date: 04/28/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: 5A9F04FD-0FCD-482F-8671-36FE93B783B0
audience: developer
ms.reviewer: shubhamp
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 91d16ec6e9f9bb359a76562dee7fcb81aac2b44d
ms.openlocfilehash: 2f2323f32327324611df2b2e8a8824e6896546aa


---

# Richtlijnen en informatie voor ontwikkelaars

Deze sectie bevat informatie over specifieke richtlijnen voor verschillende belangrijke ontwikkelscenario's, evenals algemene informatie over het ontwikkelen met deze SDK. De scenario's in deze sectie zijn specifiek voor deze release van de Rights Management Services SDK 2.1 en kunnen worden gewijzigd in toekomstige releases.
- [Instructies: ADAL-verificatie gebruiken](how-to-use-adal-authentication.md) - Verificatie met Azure RMS voor uw app met Azure Active Directory Authentication Library (ADAL).
- [Instructies: expliciete eigendomsrechten toevoegen](add-explicit-owner-rights.md) - De toepassing moet expliciet &quot;eigendomsrechten&quot; toevoegen bij het maken van een nieuw licentie ([IpcCreateLicenseFromScratch](/rights-management/sdk/2.1/api/win/functions#msipc_ipccreatelicensefromscratch)).
- [Instructies: fouten opsporen in een toepassing met rechten](debugging-applications-that-use-ad-rms.md) -In dit onderwerp wordt uitgelegd hoe u fouten opspoort in uw toepassing en de functie Logboeken van Windows gebruikt.
- [Instructies: het bijhouden en intrekken van documenten inschakelen](tracking-content.md) - Dit onderwerp bevat de algemene richtlijnen voor de implementatie van het bijhouden van documentinhoud, evenals voorbeeldcode voor updates van metagegevens en voor het maken van een knop **Gebruik bijhouden** voor uw app.
- [Instructies: e-mailmeldingen inschakelen](how-to-enable-email-notification.md) - Met e-mailmeldingen kunt u de eigenaar van beveiligde inhoud informeren wanneer de inhoud wordt geopend.
- [Instructies: ervoor zorgen dat uw servicetoepassing werkt met RMS in de cloud](how-to-use-file-api-with-aadrm-cloud.md) - Dit onderwerp bevat een overzicht van stappen voor het instellen van uw servicetoepassing voor het gebruik van Azure Rights Management.
- [Instructies: een RMS-server installeren en configureren](how-to-install-and-configure-an-rms-server.md) - In dit onderwerp worden de stappen behandeld voor het verbinding maken met een RMS-server of Azure RMS om uw toepassing met rechten te testen.
- [Instructies: de API-beveiligingsmodus instellen](setting-the-api-security-mode-api-mode.md) - U kunt kiezen in welke beveiligingsmodus uw toepassing met de bestands-API wordt uitgevoerd met behulp van de functie [IpcSetGlobalProperty](/rights-management/sdk/2.1/api/win/functions#msipc_ipcsetglobalproperty).
- [Instructies: werken met versleuteling](working-with-encryption.md) - Dit onderwerp bevat informatie over de versleutelingspakketten en enkele codefragmenten als voorbeeld van hoe u deze kunt gebruiken.
- [Soorten toepassingen](application-types.md): dit onderwerp bevat informatie over de soorten toepassingen met rechten die u kunt maken.
- [Configuratie bestands-API](file-api-configuration.md): het gedrag van bestands-API's kan worden geconfigureerd via instellingen in het register.
- [Ondersteunde bestandsindelingen](supported-file-formats.md): de bestands-API biedt ondersteuning voor systeemeigen indelingen en de Pfile-indeling
- [Ondersteunde platformen](supported-platforms.md): dit onderwerp bevat informatie over de client- en serverplatformen die worden ondersteund door RMS SDK 2.1.
- [Gebruiksbeperkingen begrijpen](understanding-usage-restrictions.md): alle toepassingen waarin RMS is ingeschakeld, moeten gebruiksbeperkingen afdwingen.
- [Overzicht van gebruiksbeperkingen](usage-restriction-reference.md): gebruiksbeperkingen worden gedefinieerd door de constanten die in dit onderwerp staan vermeld.

 
## Verwante onderwerpen ##
* [Overzicht](ad-rms-overview.md)
 

 



<!--HONumber=Jun16_HO4-->


