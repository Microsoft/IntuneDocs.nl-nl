---
# required metadata

title: De toepassing ondertekenen voor productie | Azure RMS
description: Dit onderwerp bevat de stappen voor het ondertekenen van de toepassing voor de productiemodus.
keywords:
author: bruceperlerms
manager: mbaldwin
ms.date: 04/28/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: 09BA148C-7D1E-43C8-92EA-24BBB6EFDB19
# optional metadata

#ROBOTS:
audience: developer
#ms.devlang:
ms.reviewer: shubhamp
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# De toepassing ondertekenen voor productie

Dit onderwerp bevat de stappen voor het ondertekenen van de toepassing voor de productiemodus.

## Uw toepassing met rechtenbescherming ondertekenen

Bij deze stappen wordt ervan uitgegaan dat u uw toepassing al hebt ondertekend voor een preproductiehiërarchie. Doorloop het proces dat is beschreven in [Uw toepassing met rechtenbescherming testen](running-your-first-application.md), als u dit nog niet hebt gedaan.

Zodra u het productiecertificaat van Microsoft hebt ontvangen, hebt u de volgende bestanden:

-   YourPrivateKey.dat
-   YourPublicKey.dat
-   ProductionCertificate.xml

Plaats deze in dezelfde map als *GenManifest.exe* en het binaire bestand (.exe) van de toepassing.

-   Met onderstaande procedure doorloopt u de stappen voor het maken van een nieuw MCF-bestand met productiecertificaat:

    -   Maak een nieuwe map en plaats de bestanden in die nieuwe map. Gebruik Kladblok (Notepad.exe) om een MCF-bestand voor uw toepassing te maken. Het bestand moet de volgende inhoud hebben.

        ``` syntax
        AUTO-GUID
        .\\YourPrivateKey.dat
        modulelist
        req     .\\<yourappname>.exe
        POLICYLIST
        INCLUSION
        PUBLICKEY .\\YourPublicKey.dat
        EXCLUSION
        ```

    -   Voer de volgende opdracht uit om uw toepassing te ondertekenen:

        **genmanifest.exe -chain ProductionCertificate.xml** *Appnaam***.mcf** *Appnaam***.exe.man**

        Als Genmanifest gelukt is, ziet u alleen de volgende tekst:

        Als Genmanifest is mislukt, wordt een foutbericht weergegeven.

    -   Uw *Appnaam*. exe.man moet altijd in dezelfde map als *Appnaam*.exe worden geplaatst.

## Verwante onderwerpen

* [Gebruik](how-to-use-msipc.md)
* [Uw toepassing met rechtenbescherming testen](running-your-first-application.md)
 

 





<!--HONumber=Apr16_HO4-->


