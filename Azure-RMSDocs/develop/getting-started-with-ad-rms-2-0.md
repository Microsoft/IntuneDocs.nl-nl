---
# required metadata

title: Aan de slag | Azure RMS
description: Het RMS SDK 2.1-platform stelt ontwikkelaars in staat om toepassingen te ontwikkelen die gebruikmaken van de RMS-beveiliging voor informatie.
keywords:
author: bruceperlerms
manager: mbaldwin
ms.date: 04/28/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: 728113C9-FCF9-4280-BE1D-6AF5C15E449E
# optional metadata

#ROBOTS:
audience: developer
#ms.devlang:
ms.reviewer: shubhamp
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---
# Aan de slag

Met het Rights Management Services SDK 2.1-platform kunnen ontwikkelaars toepassingen ontwikkelen die gebruikmaken van de RMS-informatiebeveiliging via een RMS-server of Azure RMS. Het platform werkt met complexe beveiligingsprocedures, zoals sleutelbeheer, versleuteling en ontsleuteling, en biedt een vereenvoudigde API voor het eenvoudig ontwikkelen van toepassingen.

## Aan de slag met de RMS SDK 2.1

Dit onderwerp bevat informatie over het instellen en uitvoeren van uw toepassing met rechten in een testomgeving. In de volgende onderwerpen vindt u informatie over het instellen van uw ontwikkelomgeving. U wordt aanbevolen dezelfde stappenvolgorde te gebruiken bij het uitvoeren van de taken.

## In deze secties

| Onderwerp | Beschrijving |
|-------|-------------|
| [Opmerkingen bij de release](release-notes-rtm.md) | Dit onderwerp bevat belangrijke informatie over deze en eerdere versies van de RMS SDK 2.1.|
| [De SDK installeren](install-the-rms-sdk.md) | Dit onderwerp bevat de stappen voor het installeren van de hulpprogramma's voor ontwikkelaars.|
| [Visual Studio configureren](how-to-configure-a-visual-studio-project-to-use-the-ad-rms-sdk-2-0.md) | Dit onderwerp bevat instructies over het configureren van een Visual Studio-project voor het gebruik van de RMS SDK 2.1.|
| [Uw toepassing ontwikkelen](developing-your-application.md) | Dit onderwerp bevat essentiële instructies voor de belangrijkste aspecten van een RMS-toepassing en kan fungeren als basis bij het ontwikkelen van uw eigen toepassing.|
| [Uw toepassing testen](running-your-first-application.md) |Dit onderwerp bevat instructies voor het instellen van uw toepassingstest.|
| [Implementeren in productieomgeving](deploying-your-application.md) |Dit onderwerp bevat informatie over de implementatieopties voor uw toepassing met rechten.|

Wanneer u aan de slag bent gegaan, is het een goed idee om enkele van onze andere [RMS-voorbeelden](samples.md) te bekijken. Bezoek vervolgens regelmatig onze [RMS Developer’s Corner](http://blogs.msdn.com/b/rms/) voor de meest recente informatie.


Gebruik de RMS SDK 2.1 aan de hand van de richtlijnen in de volgende onderwerpen:

-   [De SDK installeren](install-the-rms-sdk.md)
-   [Een toepassing met rechten testen](running-your-first-application.md)
-   [IPCHelloWorld - een voorbeeld van de toepassing](how-to-build-your-first-application.md)

### Waarom de RMS SDK 2.1 gebruiken voor het beveiligen van uw inhoud

Voor ontwikkelaars die RMS-ondersteuning willen toevoegen aan hun nieuwe en bestaande toepassingen, maakt de RMS SDK 2.1 de volgende zaken eenvoudiger:

-   Ontwikkeling van beheerbare, compatibele en robuuste RMS-toepassingen.
-   Permanente versleuteling van gebruikersgegevens. Gegevens blijven versleuteld, ongeacht de omgeving, het apparaat en het besturingssysteem.
-   Toepassing van een groot aantal gebruiksbeperkingen, zoals voorkomen dat er schermafbeeldingen worden gemaakt van uw vertrouwelijke gegevens.
-   Ondersteuning voor beveiligingsbeleid dat door het bedrijf wordt beheerd.
-   Ondersteuning voor nieuwe verificatiemechanismen en versleutelingsalgoritmen zodra deze beschikbaar komen.

De RMS SDK 2.1 ondersteunt een aantal belangrijke client- en serverplatforms. Ga voor meer informatie naar [Ondersteunde platforms](supported-platforms.md).

## Kernprincipes

**Eenvoud**: de feedback over en gebruikspatronen van de AD RMS SDK 1.0 zijn geanalyseerd. Deze gegevens zijn vervolgens gebruikt om de lastigste programmeringstaken te vereenvoudigen of automatiseren. RMS-toepassingen die zijn geschreven met behulp van de RMS SDK 2.1, bevatten doorgaans 5-10 keer minder RMS-coderegels dan RMS-toepassingen die met behulp van de AD RMS SDK 1.0 zijn geschreven.
**Eenmalig schrijven**: bij RMS SDK 2.1-toepassingen hoeft de code niet te worden gewijzigd en is het niet nodig om uw toepassing opnieuw te compileren als u de nieuwste RMS-functies wilt gebruiken. Nieuwe RMS-functies komen beschikbaar in uw bestaande toepassing zodra ze zijn toegevoegd aan de RMS-server.
**Consistentie**: dankzij de RMS SDK 2.1 is het eenvoudiger om toepassingen te schrijven die consistent voldoen aan verschillende RMS-configuraties. Hierdoor wordt ook de hoeveelheid RMS-gebruikersinterface die u als toepassingsontwikkelaar moet schrijven, aanzienlijk minder. De look wordt consistenter en gebruikers hoeven minder te worden geïnstrueerd.

## Verwante onderwerpen

* [AD RMS-voorbeelden](samples.md)
* [AD RMS Developer's Corner](http://blogs.msdn.com/b/rms/)
* [De SDK installeren](install-the-rms-sdk.md)
* [IPCHelloWorld - een voorbeeldtoepassing](how-to-build-your-first-application.md)
* [Overzicht](ad-rms-overview.md)
* [Ondersteunde platforms](supported-platforms.md)
 

 


<!--HONumber=Jun16_HO2-->


