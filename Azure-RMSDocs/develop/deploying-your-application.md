---
# required metadata

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
# optional metadata

#ROBOTS:
audience: developer
#ms.devlang:
ms.reviewer: shubhamp
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Uw toepassing implementeren


Dit onderwerp bevat informatie over de implementatieopties voor uw toepassing met rechten.

> [!IMPORTANT]
> Het wordt aanbevolen de Rights Management Services SDK 2.1-toepassing eerst te testen met de RMS-preproductieomgeving op een RMS-Server. Als u wilt dat uw klant de mogelijkheid heeft om uw toepassing te gebruiken met de Azure RMS-service, moet u tests met die omgeving uitvoeren. Zie voor meer informatie [Ervoor zorgen dat uw servicetoepassing werkt met RMS in de cloud](how-to-use-file-api-with-aadrm-cloud.md)

 

## Installatieopties voor Active Directory Rights Management Services-Client 2.1

Als u uw manifestbestand met een productiecertificaat maakt, is de toepassing gereed om te worden geïmplementeerd. Aangezien u de RMS SDK 2.1 hebt gebruikt, moet u Active Directory Rights Management Services Client 2.1 implementeren op de computer van de eindgebruiker.

### AD RMS Client 2.1

AD RMS-Client 2.1 is software die is ontworpen voor uw clientcomputers om toegang tot en gebruik van informatie te beschermen die wordt gebruikt in toepassingen met RMS, ongeacht of deze zijn geïnstalleerd bij uw bedrijf of in een Microsoft-datacentrum.

AD RMS-Client 2.1 is geen onderdeel van Windows. AD RMS Client 2.1 wordt geleverd als optionele download en kan (na bevestiging en acceptatie van de gebruiksrechtovereenkomst) vrij worden gedistribueerd met uw software van derden om clients toegang te geven tot inhoud die met rechten is beschermd door gebruik en implementatie van AD RMS-servers in uw omgeving.

> [!IMPORTANT]
> AD RMS-Client 2.1 is architectuurspecifiek en moet overeenkomen met de architectuur van het beoogde besturingssysteem.


## Installatieopties voor AD RMS-Client 2.1

-   **De AD RMS-client 2.1 herdistribueren**

    De aanbevolen aanpak is het RMS-Client-installatiepakket te bundelen met uw toepassing of oplossing met behulp van de installatietechnologie van uw voorkeur. De RMS-client kan vrijelijk opnieuw worden gedistribueerd en gebundeld met andere programma’s en IT-oplossingen.

    U kunt de AD RMS-Client 2.1 interactief installeren door het AD RMS-Client 2.1-installatieprogramma te starten of u kunt het op de achtergrond installeren. De integratiestappen zijn:

    -   RMS-Client 2.1-installatieprogramma downloaden
    -   Het uitgevoerde AD RMS-Client 2.1-installatieprogramma integreren met het installatieprogramma van uw toepassing

    Twee goede voorbeelden van integratie van AD RMS-Client 2.1 met uw toepassing zijn het RMS SDK 2.1-installatiepakket en het pakket Right Protected Folder Explorer. Probeer deze zelf te installeren om inzicht te krijgen in de aanpak.

-   **Ervoor zorgen dat AD RMS-Client 2.1 een vereiste is voor het installeren van uw toepassing**

    In dit geval maakt u een vereiste waarbij de installatie van de toepassing mislukt als de AD RMS-Client 2.1 niet aanwezig is op de computer van de eindgebruiker.

    Als de client niet aanwezig is, geeft u een foutbericht weer waarin gebruikers worden geïnformeerd waar ze AD RMS-Client 2.1 kunnen downloaden.

    Als de client aanwezig is, gaat u verder met de installatie van de toepassing.

## Azure Rights Management Services inschakelen voor uw toepassing

> [!NOTE]
> Als u hebt gemigreerd naar het nieuwe ADAL-model voor verificatie, hoeft u SIA niet te installeren. Zie voor meer informatie ADAL-verificatie voor uw RMS-toepassing.

- **Uw toepassing certificeren voor Windows 10**: als u uw programma bijwerkt zodat dit ADAL-verificatie gebruikt in plaats van de Microsoft Online-aanmeldhulp, kunnen u en uw klanten het volgende:
  - Meervoudige verificatie gebruiken
  - De RMS 2.1-client installeren zonder dat hiervoor beheerdersrechten voor de computer zijn vereist
 
  De eindgebruiker kan pas profiteren van Azure Rights Management Services als u de *Online Services-aanmeldhulp* implementeert. Als ontwikkelaar van de toepassing weet u niet of de eindgebruiker RMS (op locatie) of Azure Rights Management Services (cloudservice) gebruikt.

> [!IMPORTANT]
> Wanneer u de RMS SDK 2.1-clienttoepassing uitvoert met Azure RMS, moet u een Azure RMS-tenant aanvragen. Verzend een e-mail naar <rmcstbeta@microsoft.com> met uw tenantaanvraag.

-   Download de [Microsoft Online Services-aanmeldhulp](http://www.microsoft.com/en-us/download/details.aspx?id=28177) vanuit het Microsoft Downloadcentrum.
-   Zorg ervoor dat uw implementatie van een toepassing met rechten een controle vereist voor de selectie van deze service.
-   Voor uw eigen tests en voor het gebruik van de online service door uw eindgebruikers raadpleegt u het TechNet-onderwerp [Rights Management configureren](https://TechNet.Microsoft.Com/en-us/library/jj585002.aspx).

Voor meer informatie over het configureren van uw toepassing zodat deze werkt met RMS voor Azure Rights Management Services, raadpleegt u [Ervoor zorgen dat uw servicetoepassing werkt met RMS in de cloud](how-to-use-file-api-with-aadrm-cloud.md).

## Verwante onderwerpen

* [Gebruik](how-to-use-msipc.md)
* [Microsoft Online Services-aanmeldhulp](http://www.microsoft.com/en-us/download/details.aspx?id=28177)
* [Rights Management configureren](https://TechNet.Microsoft.Com/en-us/library/jj585002.aspx)
* [Ervoor zorgen dat uw toepassing werkt met RMS in de cloud](how-to-use-file-api-with-aadrm-cloud.md)
 

 





<!--HONumber=Apr16_HO4-->


