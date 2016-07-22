---
title: Apparaten buiten gebruik stellen | Microsoft Intune
description: 
keywords: 
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3dbec400-5d8a-47be-b892-7745811d9de2
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 779127bfd39145010f0d9b6609286aaf4dedfdc8
ms.openlocfilehash: c06f1fc1168b0dde515eaa82d15095ec4d73d1cf


---

# Apparaten buiten gebruik stellen vanuit Intune-beheer

Of apparaten nu in bedrijfseigendom zijn of persoonlijke apparaten zijn, er komt een moment waarop een beheerd apparaat buiten gebruik moet worden gesteld en niet meer vanuit Intune wordt beheerd. Een apparaat buiten gebruik stellen is een relatief eenvoudige taak; u kunt kiezen tussen selectief wissen of alles wissen.
## Gegevens en apps op apparaten wissen
Zowel het selectief wissen als het volledig wissen van een apparaat zorgt ervoor dat het apparaat uit Intune-beheer wordt verwijderd doordat hun beleid en de bedrijfsportal worden verwijderd. Dit houdt in dat het apparaat niet meer de referenties heeft die voor aanmelding bij bedrijfsbronnen nodig zijn, zoals Microsoft SharePoint, e-mail en Office 365.

[Selectief wissen](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md#selective-wipe) is de aanbevolen actie voor werknemers die hun eigen apparaten in Intune hebben ingeschreven, omdat dit geen invloed heeft op de persoonlijke gegevens op het apparaat. Alleen zakelijke gegevens worden verwijderd.

Voor apparaten die bedrijfseigendom zijn, kunt u ook voor [volledig wissen](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md#full-wipe) kiezen. Hiermee worden de fabrieksinstellingen van het apparaat teruggezet.

## Toegang tot het bedrijfsnetwerk intrekken
In het geval dat u een apparaat buiten gebruik stelt omdat een werknemer uw bedrijf verlaat en de werknemer heeft nagelaten de hardware (die bedrijfseigendom is) terug te brengen, kunt u het apparaat ook [Extern vergrendelen](use-remote-lock-and-passcode-reset-in-microsoft-intune.md). Zo voorkomt u dat bedrijfsgegevens en bedrijfshardware worden misbruikt. Mogelijk moet u het apparaat echter wel afschrijven.

U moet ook de licentie van het Intune-account van de werknemer intrekken. Hiermee maakt u de licentie vrij en kunt u deze toewijzen aan een nieuw gebruikersaccount.

## Hardware buiten gebruik stellen
Het kan ook zo zijn dat het apparaat het einde van de levensduur heeft bereikt. In dergelijke gevallen kunt u de [fabrieksinstellingen van het apparaat terugzetten](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md). Alle gegevens worden dan gewist en het apparaat wordt uit Intune verwijderd. Vervolgens kunt de hardware volgens het beleid van uw bedrijf afvoeren.

### Zie tevens
[Uw gegevens beschermen met volledig wissen of selectief wissen](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md)



<!--HONumber=Jun16_HO4-->


