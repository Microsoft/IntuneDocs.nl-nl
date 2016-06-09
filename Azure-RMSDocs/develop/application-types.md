---
# required metadata

title: Toepassingstypen | Azure RMS
description: Dit onderwerp bevat informatie over toepassingen die u kunt maken als toepassingen met rechten.
keywords:
author: bruceperlerms
manager: mbaldwin
ms.date: 04/28/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: 97169FC3-1395-4433-A632-7B0F020FABFE
# optional metadata

#ROBOTS:
audience: developer
#ms.devlang:
ms.reviewer: shubhamp
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Toepassingstypen


Dit onderwerp bevat informatie over toepassingen die u kunt maken als toepassingen met rechten.

De volgende toepassingstypen worden momenteel ondersteund door de Rights Management Services SDK 2.1

## Eenvoudige toepassingen

Een eenvoudige toepassing is bijvoorbeeld een opdrachtregelprogramma voor het versleutelen van een opgegeven bestand. Zie [IPCHelloWorld - een voorbeeldtoepassing](how-to-build-your-first-application.md) voor een voorbeeld van een eenvoudige toepassing met rechten.

### Toepassingen met servermodus

*Servermodus* is bedoeld voor niet-interactieve toepassingen die inhoud met RMS-beveiliging gebruiken, beschermen of verwerken. Een voorbeeld hiervan is een toepassing voor *Preventie van gegevensverlies* die wordt uitgevoerd als een service op een bestandsserver en automatisch gevoelige documenten beveiligt. Zie de [IpcDlp-voorbeeld](https://Code.MSDN.Microsoft.Com/IpcDlp-Sample-Application-d30bb99d) voor een voorbeeld van dit toepassingstype.

Als uw toepassing de *servermodus* gebruikt, moet deze de RMS-server op de achtergrond verifiëren. In tegenstelling tot de *clientmodus* opent de RMS SDK 2.1 geen vraag om aanmeldingsgegevens wanneer verificatie op de achtergrond niet lukt. Ook bij uitvoering in de *servermodus* is er geen toepassingsmanifest nodig.

Zie [De API-beveiligingsmodus instellen](setting-the-api-security-mode-api-mode.md) voor meer informatie over het instellen van de API-beveiligingsmodus.

### Interactieve toepassingen

Met een interactieve toepassing kunnen gebruikers gegevens weergeven en bewerken via een grafische gebruikersinterface (GUI). De gegevens die in deze gebruikersinterface worden gepresenteerd, zijn vaak waardevol en mogen beslist niet worden gestolen of per ongeluk openbaar worden gemaakt. Ondersteuning voor gegevensbeveiliging leidt doorgaans tot verbetering van bestaande scenario's, maar dat is niet de primaire reden voor het ontwikkelen van de toepassing.

Met behulp van de RMS SDK 2.1 met interactieve toepassingen kunt u het volgende:

-   Ervoor zorgen dat uw gegevens altijd worden versleuteld.

-   Voorkomen dat gebruikers gegevens uitpakken naar een niet-beveiligde-indeling (bijvoorbeeld voorkomen dat het Klembord of kopiëren en plakken wordt gebruikt).

Microsoft Kladblok is een eenvoudige interactieve toepassing. Microsoft Office is een complexere interactieve toepassing.

Zie [Gebruiksbeperkingen begrijpen](understanding-usage-restrictions.md) voor meer informatie over het beveiligen van uw toepassing.

## Verwante onderwerpen

* [IpcDlp-voorbeeld](https://Code.MSDN.Microsoft.Com/IpcDlp-Sample-Application-d30bb99d)
* [IPCHelloWorld - een voorbeeldtoepassing](how-to-build-your-first-application.md)
* [De API-beveiligingsmodus instellen](setting-the-api-security-mode-api-mode.md)
* [Gebruiksbeperkingen begrijpen](understanding-usage-restrictions.md)


<!--HONumber=Jun16_HO2-->


