---
title: Uw toepassing implementeren | Azure RMS
description: Dit onderwerp bevat informatie over de implementatieopties voor uw toepassing met rechten
keywords: 
author: bruceperlerms
manager: mbaldwin
ms.date: 04/28/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: 4B785564-6839-49ED-A243-E2A6DFF88B2E
audience: developer
ms.reviewer: shubhamp
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 982021a2e972023b04e6483348a7c27aa029e198
ms.openlocfilehash: 8308e2db84e13c6b8c85a1a3ae6c01fc0aabee75


---

# Implementeren in productieomgeving


Dit onderwerp bevat informatie over de implementatieopties voor uw toepassing met rechten.

## Een productielicentieovereenkomst aanvragen

 Voordat u een toepassing kunt vrijgeven die is ontwikkeld met behulp van de Rights Management Services SDK 2.1, moet u een productielicentieovereenkomst aanvragen om een productiecertificaat te verkrijgen.

> [!IMPORTANT]
> Als u de clienttoepassing gaat uitvoeren met Azure RMS, moet u uw eigen tenants maken. Zie [Azure RMS requirements: Cloud subscriptions that support Azure RMS](../get-started/requirements-subscriptions.md) (Azure RMS-vereisten: cloudabonnementen die ondersteuning bieden voor Azure RMS) voor meer informatie.
> Zie [Ervoor zorgen dat uw servicetoepassing werkt met RMS in de cloud](how-to-use-file-api-with-aadrm-cloud.md) voor meer informatie over het uitvoeren van toepassingen met Azure RMS.

U kunt het certificaat verkrijgen door u aan te melden voor een productielicentieovereenkomst.

Verstuur een e-mail naar [RMLA@microsoft.com](mailto:rmla@microsoft.com) en vermeld daarin de volgende informatie:

- Volledige bedrijfsnaam
- Fysiek bedrijfsadres (inclusief stad, staat/provincie, land of regio en postcode)
- Postadres van het bedrijf (inclusief stad, staat/provincie, land of regio en postcode)
- Telefoon- en faxnummer van het bedrijf
- URL van het bedrijf
- Land of regio waarin het hoofdkantoor is gevestigd
- Toepassings- of productnaam
- Voor- en achternaam van de aanvrager
- Titel of functie van de aanvrager
- E-mailadres van de aanvrager

Hoewel er niet per se een e-mailadres hoeft te worden opgegeven, wordt er doorgaans per e-mail gecommuniceerd over het aanvraagproces. U kunt een gratis e-mailaccount aanmaken via Microsoft Outlook.com. Als u geen account hebt en er geen wilt maken, kunt u schriftelijk een aanvraag indienen. Stuur uw aanvraag naar het volgende adres:

      Active Directory Rights Management License Agreements (ADRMLA)

      Microsoft Corporation

      One Microsoft Way

      Redmond, WA 98052-6399

Wanneer u een overeenkomst aanvraagt, doet u het volgende:
- Dien de informatie in het Engels in die in de overeenkomst moet worden verwerkt.
- Stuur alle aangevraagde informatie op. Als er informatie ontbreekt of als de informatie onvolledig is, kan dat het aanvraagproces vertragen.

Het Active Directory Rights Management Licensing Agreement-team (ADRMLA) reageert binnen drie werkdagen op uw e-mailaanvraag. Het duurt langer als u de aanvraag per post verstuurt. De reactie omvat het licentieovereenkomstformulier en verdere instructies. Lees en onderteken alle pagina’s van de overeenkomst en stuur deze dan terug naar het ADRMLA-team. Wijzig de lettertypen niet en geef de alinea’s van de licentieovereenkomst geen andere indeling.

Volg de instructies op die u van het ADRMLA-team ontvangt. De instructies bevatten de lijst met digitale gegevens die nodig zijn om uw certificaataanvraag te voltooien. Als u de stapsgewijze instructies opvolgt, beperkt dat de wachttijd.

Het ADRMLA-team stuurt u het productiecertificaat op zodra het is gemaakt. Het kan tot 15 werkdagen duren voor het ADRMLA-team u het certificaat per e-mail opstuurt. Dit duurt langer als de communicatie via reguliere post verloopt.


## Opties en vereisten voor de installatie van Rights Management Service-client 2.1

Aangezien u de RMS SDK 2.1 hebt gebruikt, moet u Active Directory Rights Management Services Client 2.1 implementeren op de computer van de eindgebruiker.

### RMS-client 2.1

De RMS-client 2.1 is software die is ontworpen voor uw clientcomputers om toegang tot en gebruik van informatie te beschermen die wordt gebruikt in toepassingen met RMS, ongeacht of deze zijn geïnstalleerd bij uw bedrijf of in een Microsoft-datacentrum.

De RMS-client 2.1 is geen onderdeel van Windows. RMS-client 2.1 wordt geleverd als optionele download en kan (na bevestiging en acceptatie van de gebruiksrechtovereenkomst) vrij worden gedistribueerd met uw software van derden om clients toegang te geven tot inhoud die met rechten is beschermd door gebruik en implementatie van RMS-servers in uw omgeving.


> [!IMPORTANT]
> AD RMS-Client 2.1 is architectuurspecifiek en moet overeenkomen met de architectuur van het beoogde besturingssysteem.


## Installatieopties voor RMS-client 2.1

-   **De RMS-client 2.1 opnieuw distribueren**

    De aanbevolen aanpak is het RMS-Client-installatiepakket te bundelen met uw toepassing of oplossing met behulp van de installatietechnologie van uw voorkeur. De RMS-client kan vrijelijk opnieuw worden gedistribueerd en gebundeld met andere programma’s en IT-oplossingen.

    U kunt de RMS-Client 2.1 interactief installeren door het installatieprogramma van RMS-client 2.1 te starten of u kunt het op de achtergrond installeren. De integratiestappen zijn:

    -   RMS-Client 2.1-installatieprogramma downloaden
    -   Het uitgevoerde installatieprogramma van RMS-client 2.1 integreren met het installatieprogramma van uw toepassing

    Twee goede voorbeelden van integratie van RMS-client 2.1 met uw toepassing zijn het RMS SDK 2.1-installatiepakket en het pakket Right Protected Folder Explorer. Probeer deze zelf te installeren om inzicht te krijgen in de aanpak.

-   **Zorgen dat RMS-Client 2.1 een vereiste is voor het installeren van uw toepassing**

    In dit geval maakt u een vereiste waarbij de installatie van de toepassing mislukt als RMS-client 2.1 niet aanwezig is op de computer van de eindgebruiker.

    Als de client niet aanwezig is, geeft u een foutbericht weer waarin gebruikers worden geïnformeerd waar ze RMS-client 2.1 kunnen downloaden

    Als de client aanwezig is, gaat u verder met de installatie van de toepassing.

## Azure Rights Management Services inschakelen voor uw toepassing

> [!NOTE]
> Als u hebt gemigreerd naar het nieuwe ADAL-model voor verificatie, hoeft u SIA niet te installeren. Zie voor meer informatie [ADAL-verificatie voor uw RMS-toepassing](adal-auth.md).
> U kunt ook **Uw toepassing certificeren voor Windows 10**. Als u uw toepassing bijwerkt zodat deze ADAL-verificatie gebruikt in plaats van de Microsoft Online-aanmeldhulp, kunnen u en uw klanten het volgende: Meervoudige verificatie gebruiken De RMS-client 2.1 installeren zonder dat er beheerdersrechten voor de machine vereist zijn


De eindgebruiker kan pas profiteren van Azure Rights Management Services als u de *Online Services-aanmeldhulp (SIA)* implementeert. Als ontwikkelaar van de toepassing weet u niet of de eindgebruiker RMS (op locatie) of Azure Rights Management Services (cloudservice) gebruikt.


> [!IMPORTANT]
> Als u de RMS SDK 2.1-clienttoepassing uitvoert met Azure RMS, moet u uw eigen tenants maken. Zie [Azure RMS requirements: Cloud subscriptions that support Azure RMS](../get-started/requirements-subscriptions.md) (Azure RMS-vereisten: cloudabonnementen die ondersteuning bieden voor Azure RMS) voor meer informatie.

-   Download de [Microsoft Online Services-aanmeldhulp](http://www.microsoft.com/en-us/download/details.aspx?id=28177) vanuit het Microsoft Downloadcentrum.
-   Zorg ervoor dat uw implementatie van een toepassing met rechten een controle vereist voor de selectie van deze service.
-   Voor uw eigen tests en voor het gebruik van de online service door uw eindgebruikers raadpleegt u het TechNet-onderwerp [Rights Management configureren](https://TechNet.Microsoft.Com/en-us/library/jj585002.aspx).

Voor meer informatie over het configureren van uw toepassing zodat deze werkt met RMS voor Azure Rights Management Services, raadpleegt u [Ervoor zorgen dat uw servicetoepassing werkt met RMS in de cloud](how-to-use-file-api-with-aadrm-cloud.md).

## Verwante onderwerpen

* [Microsoft Online Services-aanmeldhulp](http://www.microsoft.com/en-us/download/details.aspx?id=28177)
* [Rights Management configureren](https://TechNet.Microsoft.Com/en-us/library/jj585002.aspx)
* [Ervoor zorgen dat uw toepassing werkt met RMS in de cloud](how-to-use-file-api-with-aadrm-cloud.md)
 

 



<!--HONumber=Jul16_HO1-->


