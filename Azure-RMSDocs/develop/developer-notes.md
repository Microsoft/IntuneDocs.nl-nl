---
# required metadata

title: Opmerkingen voor ontwikkelaars | Azure RMS
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
# optional metadata

#ROBOTS:
audience: developer
#ms.devlang:
ms.reviewer: shubhamp
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Opmerkingen voor ontwikkelaars

Deze sectie bevat informatie over specifieke hulp voor verschillende belangrijke ontwikkelscenario's. De scenario's in deze sectie zijn specifiek voor deze release van de Rights Management Services SDK 2.1 en kunnen worden gewijzigd in toekomstige releases.

- [Expliciete eigendomsrechten toevoegen](add-explicit-owner-rights.md): de toepassing moet expliciet rechten voor de eigenaar toevoegen bij het maken van een nieuw licentie ([IpcCreateLicenseFromScratch](/rights-management/sdk/2.1/api/win/functions#msipc_ipccreatelicensefromscratch)).
- [Algemene fouten en oplossingen](common-error-conditions-and-solutions.md): de meestvoorkomende foutberichten die u kunt tegenkomen wanneer u de RMS SDK 2.1 ontwikkelhulpprogramma's gebruikt.
- [E-mailmeldingen inschakelen](how-to-enable-email-notification.md): met e-mailmeldingen kunt u de eigenaar van beveiligde inhoud informeren wanneer zijn of haar inhoud wordt geopend.
- [Configuratie bestands-API](file-api-configuration.md): het gedrag van bestands-API's kan worden geconfigureerd via instellingen in het register.
- [IPCHelloWorld - een voorbeeldtoepassing](how-to-build-your-first-application.md): dit onderwerp bevat instructies voor het maken van een voorbeeldtoepassing met rechtenbescherming.
- [De API-beveiligingsmodus instellen](setting-the-api-security-mode-api-mode.md): u kunt kiezen in welke beveiligingsmodus uw toepassing met de bestands-API wordt uitgevoerd met behulp van de functie [IpcSetGlobalProperty](/rights-management/sdk/2.1/api/win/functions#msipc_ipcsetglobalproperty).
- [Ondersteunde bestandsindelingen](supported-file-formats.md): de bestands-API biedt ondersteuning voor systeemeigen indelingen en de Pfile-indeling.
- [Inhoud bijhouden](tracking-content.md): dit onderwerp bevat algemene richtlijnen voor de implementatie van het bijhouden van inhoud die is beveiligd met RMS SDK 2.1.
- [Werken met versleuteling](working-with-encryption.md): dit onderwerp bevat informatie over onze versleutelingspakketten en enkele codefragmenten als voorbeeld van hoe u deze kunt gebruiken.

 

## Verwante onderwerpen ##
* [Overzicht](ad-rms-overview.md)
* [Gebruik](how-to-use-msipc.md)
 

 


<!--HONumber=Apr16_HO4-->


