---
# vereiste metagegevens

titel: Instructies: werken met versleutelingsinstellingen | Beschrijving Azure RMS: dit onderwerp bevat informatie over onze versleutelingspakketten trefwoorden: auteur: bruceperlerms manager: mbaldwin ms.date: 28-04-2016 ms.topic: artikel ms.prod: azure ms.service: rights-management ms.technology: techgroep-id ms.assetid: B1D2C227-F43D-4B18-9956-767B35145792
# optionele metagegevens

#ROBOTS:
doelgroep: ontwikkelaar
#ms.devlang:
ms.reviewer: shubhamp ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Instructies: werken met versleutelingsinstellingen

Dit onderwerp oriënteert u op onze versleutelingspakketten en toont een aantal codefragmenten en hoe u deze kunt gebruiken.

## Ondersteuning voor AES-256, de nieuwe standaard

Er is geen aanvullende code vereist om op *AES 256* gebaseerde versleuteling te gebruiken, omdat dit de nieuwe standaard is, aangenomen dat u gebruikmaakt van de RMS SDK 2.1-update van maart 2015 of hoger. We raden u ten zeerste aan om uw toepassingen bij te werken met deze release vanwege de aanvullende beveiligingsvoordelen van *AES 256*.

> [!IMPORTANT]
> Ondersteuning voor het gebruik van met *AES 256* beveiligde bestanden is er al sinds de [release van oktober 2014](release-notes-rtm.md). Als u andere toepassingen uitvoert met een versie van de SDK van vóór oktober 2014, wordt uw toepassing met deze update verbroken. Controleer of klanten van de toepassingen die u maakt, gebruikmaken van de bijgewerkte SDK of bereid zijn direct een update uit te voeren naar de meest recente versie van uw toepassing.

 
## Ondersteuning voor API-versleuteling

Vanaf de [update van maart 2015](release-notes-rtm.md) hebben we de volgende drie vlaggen opgenomen in onze API en de bijbehorende versleutelingspakketten:

-   IPC\_ENCRYPTION\_PACKAGE\_AES256\_CBC4K
-   IPC\_ENCRYPTION\_PACKAGE \_AES128\_CBC4K
-   IPC\_ENCRYPTION\_PACKAGE \_AES128\_ECB (ook wel ‘afgeschafte algoritmen’ genoemd)

De markeringen in het versleutelingspakket (zie [**Preferred encryption**](/rights-management/sdk/2.1/api/win/constants#msipc_preferred_encryption)(Versleuteling van voorkeur)) kunnen worden gebruikt in combinatie met onze nieuwe licentie-eigenschapsmarkering **IPC\_LI\_PREFERRED\_ENCRYPTION\_PACKAGE**.

Hieronder vindt u enkele eenvoudige codefragmenten die u laten zien hoe u de nieuwe licentie-eigenschap gebruikt.

## Afgeschafte algoritmen

De markering **IPC\_LI\_DEPRECATED\_ENCRYPTION\_ALGORITHMS** wordt niet meer weergegeven in de API. Dit betekent dat toekomstige toepassingen niet langer worden gecompileerd als ze verwijzen naar deze vlag. Toepassingen die al zijn gemaakt, blijven werken omdat de vlag in de API-code afzonderlijk wordt verwerkt.

U kunt de vlag voor oudere, afgeschafte versleutelingsalgoritmen nog steeds gebruiken door een vlag te wijzigen. Zie de volgende codefragmenten als voorbeeld.

## Bestanden beveiligen met AES 256 CBC4K

Er zijn geen wijzigingen in de code nodig: *AES 256* CBC4K is de standaardinstelling.

    C++

    hr = IpcCreateLicenseFromTemplateID(pcTil-&gt;aTi[0].wszID,
                                    0,
                                    NULL,
                                    &amp;pLicenseHandle);


## Bestanden beveiligen met AES-128 CBC4K

    C++

    hr = IpcCreateLicenseFromTemplateID(pcTil-&gt;aTi[0].wszID,
                                    0,
                                    NULL,
                                    &amp;pLicenseHandle);

    DWORD dwEncryptionMode = IPC_ENCRYPTION_PACKAGE_AES128_CBC4K;

    hr = IpcSetLicenseProperty(pLicenseHandle,
                           false,
                           IPC_LI_PREFERRED_ENCRYPTION_PACKAGE,
                           &amp;dwEncryptionMode);


## Bestanden beveiligen met AES-128 ECB (afgeschafte algoritmen)

Dit voorbeeld toont ook de nieuwe manier voor het ondersteunen van *afgeschafte algoritmen*.

    C++
    
    hr = IpcCreateLicenseFromTemplateID(pcTil-&gt;aTi[0].wszID,
                                    0,
                                    NULL,
                                    &amp;pLicenseHandle);

    DWORD dwEncryptionMode = IPC_ENCRYPTION_PACKAGE_AES128_ECB;

    hr = IpcSetLicenseProperty(pLicenseHandle,
                           false,
                           IPC_LI_PREFERRED_ENCRYPTION_PACKAGE,
                           &amp;dwEncryptionMode);

 

 


<!--HONumber=Jun16_HO2-->


