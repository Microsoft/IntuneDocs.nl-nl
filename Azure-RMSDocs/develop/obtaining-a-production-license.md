---
# required metadata

title: Een productielicentie verkrijgen | Azure RMS
description: Als u een toepassing wilt vrijgeven die is ontwikkeld met de RMS SDK 2.1, moet u beschikken over een productlicentieovereenkomst.
keywords:
author: bruceperlerms
manager: mbaldwin
ms.date: 04/28/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: 6749817E-FF34-4384-BF63-39AEA5C372CA
# optional metadata

#ROBOTS:
audience: developer
#ms.devlang:
ms.reviewer: shubhamp
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Een productielicentie verkrijgen

Voordat u een toepassing kunt vrijgeven die is ontwikkeld met behulp van de Rights Management Services SDK 2.1, moet u een productielicentieovereenkomst aanvragen om een productiecertificaat te verkrijgen.

> [!IMPORTANT]
> Als u de clienttoepassing gaat uitvoeren met Azure RMS, moet u een Azure RMS-tenant aanvragen. Verzend een e-mail naar <rmcstbeta@microsoft.com> met uw tenantaanvraag.

Zie [Uw servicetoepassing inschakelen voor cloudgebaseerde RMS](how-to-use-file-api-with-aadrm-cloud.md) voor meer informatie over het uitvoeren van toepassingen met Azure RMS.


Het productiecertificaat en het preproductiecertificeringsplatform hebben een vergelijkbare functie, maar zijn bedoeld voor gebruik in andere omgevingen. Beide omvatten een certificaatketen met een Microsoft-certificeringsinstantiecertificaat (CA) in de vertrouwensbasis, maar het preproductiecertificaat wordt alleen gebruikt bij het ontwikkelen van een RMS-toepassing. Het productiecertificaat wordt gebruikt in omgevingen voor na de introductie. U gebruikt het productiecertificaat en de daaraan gekoppelde persoonlijke sleutel om een manifest te maken en te ondertekenen dat de bestanden identificeert die kunnen of moeten worden geladen in de procesruimte van uw toepassing en de bestanden die niet moeten worden geladen.

Zie voor meer informatie over sleutels [Een toepassing met rechtenbescherming testen](running-your-first-application.md).

U kunt het certificaat verkrijgen door u aan te melden voor een productielicentieovereenkomst.

## Een productielicentieovereenkomst aanvragen

-   Verstuur een e-mail naar [RMLA@microsoft.com](mailto:rmla@microsoft.com) en vermeld daarin de volgende informatie:

    -   Volledige bedrijfsnaam

    -   Fysiek bedrijfsadres (inclusief stad, staat/provincie, land of regio en postcode)
    -   Postadres van het bedrijf (inclusief stad, staat/provincie, land of regio en postcode)
    -   Telefoon- en faxnummer van het bedrijf
    -   URL van het bedrijf
    -   Land of regio waarin het hoofdkantoor is gevestigd
    -   Toepassings- of productnaam
    -   Voor- en achternaam van de aanvrager
    -   Titel of functie van de aanvrager
    -   E-mailadres van de aanvrager

    Hoewel er niet per se een e-mailadres hoeft te worden opgegeven, wordt er doorgaans per e-mail gecommuniceerd over het aanvraagproces. U kunt een gratis e-mailaccount aanmaken via Microsoft Outlook.com. Als u geen account hebt en er geen wilt maken, kunt u schriftelijk een aanvraag indienen. Stuur uw aanvraag naar het volgende adres:

    `Active Directory Rights Management License Agreements (ADRMLA)`

    `Microsoft Corporation`

    `One Microsoft Way`

    `Redmond, WA 98052-6399`

    Wanneer u een overeenkomst aanvraagt, doet u het volgende:

    -   Dien de informatie in het Engels in die in de overeenkomst moet worden verwerkt.
    -   Stuur alle aangevraagde informatie op. Als er informatie ontbreekt of als de informatie onvolledig is, kan dat het aanvraagproces vertragen.

    Het Active Directory Rights Management Licensing Agreement-team (ADRMLA) reageert binnen drie werkdagen op uw e-mailaanvraag. Het duurt langer als u de aanvraag per post verstuurt. De reactie omvat het licentieovereenkomstformulier en verdere instructies. Lees en onderteken alle pagina’s van de overeenkomst en stuur deze dan terug naar het ADRMLA-team. Wijzig de lettertypen niet en geef de alinea’s van de licentieovereenkomst geen andere indeling.

    Volg de instructies op die u van het ADRMLA-team ontvangt. De instructies bevatten de lijst met digitale gegevens die nodig zijn om uw certificaataanvraag te voltooien. Als u de stapsgewijze instructies opvolgt, beperkt dat de wachttijd.

    Het ADRMLA-team stuurt u het productiecertificaat op zodra het is gemaakt. Het certificaat wordt gemaakt op basis van de licentieovereenkomst en digitale gegevens die u aanlevert (waaronder een openbare sleutel). Het kan tot 15 werkdagen duren voor het ADRMLA-team u het certificaat per e-mail opstuurt. Dit duurt langer als de communicatie via reguliere post verloopt.

## Verwante onderwerpen

* [Gebruik](how-to-use-msipc.md)
* [Een toepassing met rechten testen](running-your-first-application.md)
 

 





<!--HONumber=Apr16_HO4-->


