---
title: HYOK-beperkingen | Azure Rights Management
description: 
author: cabailey
manager: mbaldwin
ms.date: 08/11/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: 7667b5b0-c2e9-4fcf-970f-05577ba51126
translationtype: Human Translation
ms.sourcegitcommit: cfab76a97034b58eec8dfdbdc82cc1037a647d11
ms.openlocfilehash: 95f64c00c28fb52a0bd7d78a997705f7ed515557


---

# HYOK-vereisten (Hold Your Own Key) en -beperkingen voor AD RMS-beveiliging

>*Van toepassing op: Azure Information Protection preview*

**[ Deze informatie is voorlopig en kan worden gewijzigd. ]**

Wanneer u uw meest gevoelige documenten en e-mailberichten beveiligt, zult u dit meestal doen door Azure Rights Management-beveiliging toe te passen om van het volgende te profiteren:

- Er is geen serverinfrastructuur vereist, waardoor de oplossing sneller en goedkoper is te implementeren en te onderhouden dan een on-premises oplossing.

- Gemakkelijker delen met partners en gebruikers van andere organisaties met cloudverificatie.

- Nauwe integratie met Office 365-services, zoals zoeken, webviewers, gedraaide weergaven, anti-malware, eDiscovery en Delve.

- Documenttracking, intrekking en e-mailmelding voor gevoelige documenten die u hebt gedeeld.

Azure RMS beveiligt de documenten en e-mailberichten van uw organisatie met een persoonlijke sleutel voor de organisatie die wordt beheerd door Microsoft (de standaardinstelling) of door uzelf (het BYOK-scenario [Bring Your Own Key]). De informatie die u met Azure RMS beveiligt, wordt nooit naar de cloud verzonden; de beveiligde documenten en e-mailberichten worden niet opgeslagen in Azure tenzij u ze expliciet daar opslaat of een andere cloudservice gebruikt waarmee ze in Azure worden opgeslagen. Zie [Uw Azure Rights Management-tenantsleutel plannen en implementeren](../plan-design/plan-implement-tenant-key.md) voor meer informatie over de sleutelopties voor tenants. 

Enkele klanten willen echter misschien geselecteerde documenten en e-mailberichten beveiligen met een sleutel die on-premises wordt gehost. Dit kan bijvoorbeeld vereist zijn vanwege regelgeving of om compatibiliteitsredenen. 

Deze configuratie wordt wel HYOK (Hold Your Own Key) genoemd en wordt ondersteund door Azure Information Protection wanneer u een werkende AD RMS-implementatie (Active Directory Rights Management Services) hebt met de vereisten die in de volgende sectie worden beschreven. 

In dit HYOK-scenario worden de beleidsregels voor rechten en de persoonlijke sleutel van de organisatie waarmee deze beleidsregels worden beveiligd, on-premises beheerd en bewaard terwijl het Azure Information Protection-beleid voor het labelen en classificeren in Azure wordt beheerd en opgeslagen. Net als bij Azure RMS-beveiliging wordt de informatie die u beveiligt met AD RMS, nooit naar de cloud verzonden.

> [!NOTE]
> Gebruik deze configuratie alleen wanneer dit echt nodig is en alleen voor de documenten en e-mailberichten waarvoor dit vereist is. AD RMS-beveiliging biedt niet de genoemde voordelen van Azure RMS-beveiliging en het doel hiervan is "onzichtbaarheid van gegevens tegen elke prijs".

Gebruikers weten niet dat bij een label AD RMS-beveiliging in plaats van Azure RMS-beveiliging wordt gebruikt. Met het oog op de beperkingen van AD RMS-beveiliging is het belangrijk dat u gebruikers de benodigde informatie verstrekt voor het geval ze labels selecteren waarmee AD RMS-beveiliging wordt toegepast.

## Vereisten voor HYOK

Controleer of uw AD RMS-implementatie voldoet aan de volgende vereisten om AD RMS-beveiliging voor Azure Information Protection te bieden.

- AD RMS-configuratie:
    
    - Eén AD RMS-basiscluster.
    
    - [Cryptografische modus 2](https://technet.microsoft.com/library/hh867439.aspx).
    
    - Geconfigureerde rechtensjablonen.

- Adreslijstsynchronisatie is geconfigureerd tussen uw on-premises Active Directory en Azure Active Directory, en gebruikers van AD RMS-beveiliging zijn geconfigureerd voor eenmalige aanmelding.

- Als u documenten of e-mailberichten die worden beveiligd door AD RMS, deelt met anderen buiten uw organisatie: AD RMS is geconfigureerd voor expliciet gedefinieerde vertrouwensrelaties in een directe Point to Point-relatie met de andere organisaties met ofwel vertrouwde gebruikersdomeinen (TUD's) of federatieve vertrouwensrelaties die zijn gemaakt met AD FS (Active Directory Federation Services).

- Gebruikers hebben Office 2013 Pro Plus met Service Pack 1 of Office 2016 Pro Plus en de betreffende Office-versie wordt uitgevoerd onder Windows 7 Service Pack 1 of hoger. Houd er rekening mee dat Office 2010 en Office 2007 niet voor dit scenario worden ondersteund.

- De [Azure Information Protection-client](info-protect-client.md) is versie **1.0.233.0** of hoger.

> [!IMPORTANT]
> Om te voldoen aan de hoge zekerheid die dit scenario biedt, is het beter dat uw AD RMS-servers zich niet in uw perimeternetwerk bevinden en dat deze alleen worden gebruikt op goed beheerde computers (dus niet op mobiele apparaten of werkgroepcomputers).

Zie [Active Directory Rights Management Services](https://technet.microsoft.com/library/hh831364.aspx) in de Windows Server-bibliotheek voor implementatie-informatie en instructies voor AD RMS. 


## De informatie zoeken waarmee AD RMS-beveiliging met een Azure Information Protection-label wordt opgegeven

Wanneer u een label voor AD RMS-beveiliging configureert, moet u de sjabloon-GUID en licentieverlenings-URL van uw AD RMS-cluster opgeven. U kunt deze beide waarden via de Active Directory Rights Management Services-console zoeken:

- De sjabloon-GUID zoeken: vouw het cluster uit en klik op **Rechtenbeleidssjablonen**. Vervolgens kunt u bij de gegevens over **Gedistribueerde rechtenbeleidssjablonen** de GUID uit de gewenste sjabloon kopiëren. Bijvoorbeeld: 82bf3474-6efe-4fa1-8827-d1bd93339119

- De licentieverlenings-URL zoeken: klik op de clusternaam. Kopieer uit de gegevens bij **Clusterdetails** de waarde van **Licentieverlening** minus de tekenreeks **/_wmcs/licensing**. Bijvoorbeeld: https://rmscluster.contoso.com 
    
    Als u beschikt over een extranetlicentieverleningswaarde evenals een intranetlicentieverleningswaarde en deze verschillend zijn: geef de extranetwaarde alleen op als u beveiligde documenten en e-mailberichten deelt met partners die u hebt gedefinieerd met expliciete Point-to-Point-vertrouwensrelaties. Anders gebruikt u de intranetwaarde en zorgt u ervoor dat alle clientcomputers die AD RMS-beveiliging met Azure Information Protection gebruiken, verbinding maken met een intranetverbinding (bijvoorbeeld: externe computers gebruiken een VPN-verbinding).

## Volgende stappen

Zie de blogberichtaankondiging [Azure Information Protection with HYOK (Hold Your Own Key)](https://blogs.technet.microsoft.com/enterprisemobility/2016/08/10/azure-information-protection-with-hyok-hold-your-own-key/) (Azure Information Protection met HYOK (Hold Your Own Key)) voor meer informatie over deze preview-functie.

Zie [Een label configureren om Rights Management-beveiliging toe te passen](configure-policy-protection.md) voor informatie over het configureren van een label voor AD RMS-beveiliging. 



<!--HONumber=Aug16_HO2-->


