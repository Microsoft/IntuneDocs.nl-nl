---
title: Windows Information Protection configureren - Intune
titleSuffix: Azure portal
description: In dit onderwerp vindt u meer informatie over de Intune-instellingen die u kunt gebruiken om Windows-gegevensbescherming te beheren."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 1/18/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 96af3413d559b57dafe166797816f886e79c22b0
ms.sourcegitcommit: 1a390b47b91e743fb0fe82e88be93a8d837e8b6a
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-configure-windows-information-protection-in-microsoft-intune"></a>Windows Information Protection configureren in Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Met de toename van het aantal apparaten in de onderneming dat eigendom is van werknemers, is er ook een groter risico op datalekken via apps en services die zich buiten de invloed van de onderneming bevinden, zoals e-mail, sociale media en de openbare cloud. Bijvoorbeeld wanneer een medewerker de nieuwste technische afbeeldingen via een persoonlijke e-mailaccount verstuurt, productinformatie kopieert en in een tweet plakt, of een conceptversie van een verkooprapport opslaat in de openbare cloud.

**Windows-gegevensbeveiliging** helpt bij de bescherming tegen deze potentiële gegevenslekken zonder dat de gebruikerservaring van werknemers hierdoor wordt beïnvloed. Het helpt tevens zakelijke apps en gegevens te beschermen tegen onbedoelde gegevenslekken op apparaten die eigendom zijn van de onderneming en persoonlijke apparaten die werknemers meenemen naar het werk, zonder dat hiervoor wijzigingen nodig zijn aan uw omgeving of andere apps.

Dit Intune-beleid beheert de lijst met apps die zijn beveiligd door Windows Information Protection, de bedrijfsnetwerklocaties, het beveiligingsniveau en de versleutelingsinstellingen.

>[!NOTE]
> Als u de bedrijfsportal-app voor Windows 10 met Windows Information Protection wilt gebruiken, moet u de bedrijfsportal-app toevoegen in de modus Windows Information Protection van **Uitgesloten**. 

### <a name="next-steps"></a>Volgende stappen
Zie voor meer informatie:
-  [Uw ondernemingsgegevens beveiligen met Windows Information Protection](https://technet.microsoft.com/itpro/windows/keep-secure/protect-enterprise-data-using-wip).
- [Een WIP-beleid (Windows Information Protection) maken met de klassieke console voor Microsoft Intune](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/create-wip-policy-using-intune)
- [Een WIP-beleid (Windows Information Protection) maken met MDM via Azure Portal voor Microsoft Intune](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/create-wip-policy-using-intune-azure)
- [Een WIP-beleid (Windows Information Protection) maken met MAM via Azure Portal voor Microsoft Intune](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/create-wip-policy-using-mam-intune-azure)
