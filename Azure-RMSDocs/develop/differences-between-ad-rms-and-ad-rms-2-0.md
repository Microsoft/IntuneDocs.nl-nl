---
# required metadata

title: Waarom deze SDK beter is | Azure RMS
description: In dit onderwerp wordt beschreven waarom de RMS SDK 2.1 een aanzienlijke verbetering vormt ten opzichte van de oorspronkelijke Active Directory Rights Management Services SDK.
keywords:
author: bruceperlerms
manager: mbaldwin
ms.date: 04/28/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: 622D5C6E-07D5-4C71-A99D-9823C1FE6936
# optional metadata

#ROBOTS:
audience: developer
#ms.devlang:
ms.reviewer: shubhamp
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Waarom deze SDK beter is
In dit onderwerp wordt beschreven waarom de RMS SDK 2.1 een aanzienlijke verbetering vormt ten opzichte van de oorspronkelijke [Active Directory Rights Management Services SDK](https://msdn.microsoft.com/library/Cc530379) voor wat betreft de vereiste inspanningen voor ontwikkelaars bij het maken van een toepassing met rechtenbescherming.

**API-gebied**: het API-gebied is aanzienlijk verminderd via abstractie, zodat u zich niet langer bezig hoeft te houden met veel details van back-end-implementatie. Van een API-gebied met 84 functies bij de RMS SDK bevat de SDK RMS 2.1 nu nog maar 20 API-functies. De meeste toepassingen hoeven slechts een kleine subset van dit API-gebied te gebruiken.

**Opstarttijd**: met de RMS SDK 2.1 kunt u een stapsgewijze handleiding volgen om te identificeren welke bronnen van uw toepassing gevoelig zijn en hoe u deze kunt beveiligen. Bij gebruik van de RMS-SDK moest u gedetailleerde kennis hebben over certificaten, indelingen en topologieën, en complexe code schrijven voor multithreading.

**Ondersteuning van meerdere topologieën**: de RMS SDK 2.1 helpt u het herschrijven van code te minimaliseren; uw toepassing zou met alle topologieën moeten kunnen werken nu we de wijze waarop ontwikkelaars met topologieën omgaan, sterk hebben vereenvoudigd. Bij gebruik van de RMS-SDK moest u alle ondersteunde topologieën begrijpen en vervolgens voor elk hiervan specifieke code schrijven en testen.

**Toekomstbestendig**: de RMS SDK 2.1 helpt u het herschrijven van uw rechtenbeschermingscode te minimaliseren; uw toepassing zou in elke RMS-omgeving moeten werken en automatisch moeten profiteren van nieuwe functionaliteit wanneer er bijgewerkte RMS-kernfuncties worden uitgebracht. Bij gebruik van de AD RMS SDK moest u uw toepassing speciaal bijwerken om te kunnen profiteren van nieuwe functies.

**Belangrijke mededeling**  
Alle onderwerpen in de oorspronkelijke [Active Directory Rights Management Services SDK](https://msdn.microsoft.com/library/Cc530379) in de MSDN-bibliotheek beginnen nu met de volgende ondersteuningsverklaring:

Functionaliteit die gebruikmaakt van de AD RMS SDK en door de client beschikbaar wordt gesteld in Msdrm.dll, is beschikbaar voor gebruik in Windows Server 2008, Windows Vista, Windows Server 2008 R2, Windows 7, Windows Server 2012 en Windows 8. Dergelijke functionaliteit is in latere versies mogelijk gewijzigd of niet beschikbaar. Gebruik in plaats daarvan de [Active Directory Rights Management Services SDK 2.1](microsoft-information-protection-and-control-client-portal.md), die gebruikmaakt van functionaliteit die door de client beschikbaar wordt gesteld in *Msipc.dll*.

 

## Verwante onderwerpen ##
* [Overzicht](ad-rms-overview.md)
* [Active Directory Rights Management Services SDK](https://msdn.microsoft.com/library/Cc530379)
* [Rights Management Services SDK 2.1](microsoft-information-protection-and-control-client-portal.md)
 

 


<!--HONumber=Apr16_HO4-->


