---
title: Aangepaste Intune-instellingen voor macOS-apparaten | Intune Azure Preview | Microsoft Docs
description: 'Intune Azure Preview: in dit onderwerp vindt u informatie over de instellingen die u kunt gebruiken in een aangepast macOS-profiel.'
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 68100ea5-7d9b-4c0b-8df7-b9a24b2442c8
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 5ab494a3dd1e1bdea9703ab314574b192c5208ee
ms.openlocfilehash: 113572430f0ef82c9a6fa533e3d6fc17b86119cb


---

# <a name="custom-settings-for-macos-devices-in-intune-azure-preview"></a>Aangepaste instellingen voor macOS-apparaten in Intune Azure Preview

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Gebruik het aangepaste macOS-profiel van Microsoft Intune om instellingen die u met het hulpprogramma [Apple Configurator](https://itunes.apple.com/app/apple-configurator-2/id1037126344?mt=12) hebt gemaakt, op macOS-apparaten te implementeren. Met dit hulpprogramma kunt u veel instellingen configureren die de werking van deze apparaten regelen, en deze instellingen exporteren naar een configuratieprofiel. U kunt dit configuratieprofiel vervolgens importeren naar een aangepast Intune macOS-profiel en de instellingen toewijzen aan gebruikers en apparaten in uw organisatie.

Op deze manier kunt u macOS-instellingen implementeren die niet met andere Intune-profieltypen kunnen worden geconfigureerd.


1. Volg de instructies in [Aangepaste apparaatinstellingen configureren in Microsoft Intune](how-to-configure-custom-settings.md) om aan de slag te gaan.
2. Geef de volgende informatie op de blade **Profiel maken** op:

- **Aangepaste configuratieprofielnaam**: geef een naam op voor het beleid, zoals het moet worden weergegeven op het apparaat en in de Intune-status.
- **Configuratieprofielbestand**: blader naar het configuratieprofiel dat u hebt gemaakt met Apple Configurator.
Controleer of de instellingen die u vanuit het hulpprogramma Apple Configurator exporteert, compatibel zijn met de macOS-versie op de apparaten waarop u het aangepaste macOS-beleid implementeert. Als u meer wilt weten over het oplossen van problemen bij incompatibele instellingen, zoekt u op de [Apple Developer](https://developer.apple.com/)-website naar **Configuration Profile Reference** (naslag voor configuratieprofielen) en **Mobile Device Management Protocol Reference** (naslag voor beheerprotocol voor mobiele apparaten).

Het bestand dat u hebt geïmporteerd, wordt weergegeven in het gebied **Bestandsinhoud** van de blade.



<!--HONumber=Feb17_HO1-->


