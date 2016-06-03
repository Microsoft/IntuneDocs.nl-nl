---
# required metadata

title: Certificaatketens begrijpen | Azure RMS
description: Een toepassing met rechten vereist een openbaar sleutelpaar en een certificaatketen die terug leidt naar een Microsoft-certificaat als vertrouwensbasis.
keywords:
author: bruceperlerms
manager: mbaldwin
ms.date: 04/28/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: 6AEA2162-82BF-4867-9285-111CD3FCD2F6
# optional metadata

#ROBOTS:
audience: developer
#ms.devlang:
ms.reviewer: shubhamp
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Certificaatketens begrijpen

Het ontwikkelen van een toepassing met rechten vereist een openbaar sleutelpaar en een certificaatketen die terug leidt naar een Microsoft-certificaat als vertrouwensbasis.

## Certificaattypen

Elke licentie die en elk certificaat dat in een omgeving met Rights Management Services (RMS) wordt gebruikt, bestaat uit een keten van certificaten die terug kunnen worden geleid naar een certificaat van een Microsoft-certificeringsinstantie (CA). Microsoft biedt twee ketens waarin een licentie of een certificaat kan worden genest: een preproductiecertificaatketen en een productieketen. Wij raden aan de preproductiehiërarchie te gebruiken bij het ontwikkelen van een toepassing, zodat u kunt werken zonder een *productielicentieovereenkomst* met Microsoft te hoeven ondertekenen. Houd er rekening mee dat ook de RMS-server voor de preproductieomgeving moet worden geconfigureerd.

Voordat u uw toepassing vrijgeeft, moet u overschakelen naar een productieketen. Beveiliging van inhoud met een preproductiecertificaat is minder veilig dan beveiliging met een productiecertificaat.

De openbare en persoonlijke sleutels en het preproductiecertificaat zijn in de SDK opgenomen in de volgende bestanden in de map `%MsipcSDKDir%\Bin`.

- **ISVTier5AppSigningPrivKey.dat** bevat de persoonlijke sleutel voor het ondertekenen van een manifest voor gebruik tijdens het ontwikkelen van een toepassing.
- **ISVTier5AppSigningPubKey.dat** bevat de openbare sleutel die is ondertekend in de hiërarchie van het preproductiecertificaat.
- **ISVTier5AppSignSDK_Client.xml** bevat het preproductiecertificaat voor het genereren van een manifest voor gebruik tijdens het ontwikkelen van een toepassing.

 

U gebruikt het certificaat en de persoonlijke sleutel om een manifest te maken en te ondertekenen dat de bestanden identificeert die kunnen of moeten worden geladen in de procesruimte van uw toepassing, evenals bestanden die niet moeten worden geladen. Het manifest wordt vervolgens geladen door het platform.

Of u tijdens het ontwikkelen van een toepassing een preproductiecertificaat hebt gebruikt of niet, in beide gevallen geldt: wanneer u klaar bent voor het vrijgeven van de toepassing, moet u een nieuw sleutelpaar genereren, een productiecertificaat van Microsoft verkrijgen en de nieuwe persoonlijke sleutel en het nieuwe certificaat gebruiken om een toepassingsmanifest te maken en te ondertekenen.

Zie [Overschakelen op de productieomgeving](switching-to-the-production-environment.md) voor meer informatie over het werken met certificaatketens en het ondertekenen van toepassingen.

## Verwante onderwerpen

* [Concepten voor ontwikkelaars](ad-rms-concepts-nav.md)
* [Overschakelen op de productieomgeving](switching-to-the-production-environment.md)
 

 


<!--HONumber=May16_HO2-->


