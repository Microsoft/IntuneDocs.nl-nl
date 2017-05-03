---
title: Intune-configuratie-instellingen voor gedeelde apparaten voor iOS
titleSuffix: Intune Azure preview
description: 'Intune Azure Preview: informatie over de Intune-instellingen die u kunt gebruiken voor het weergeven van informatie op het vergrendelingsscherm van een iOS-apparaat.'
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 4/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f122e4ee-90e7-4b42-b801-8c1c7c0a5bf7
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: e5dd7cb5b320df7f443b52a1b502027fa3c4acaf
ms.openlocfilehash: 2bc107054f438d5ed72de87dec85900f871c0acc
ms.lasthandoff: 04/19/2017


---

# <a name="shared-device-configuration-settings-to-display-messages-on-the-ios-device-lock-screen"></a>Configuratie-instellingen voor gedeelde apparaten voor het weergeven van berichten in het vergrendelingsscherm van een iOS-apparaat

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Met de configuratie-instellingen voor gedeelde apparaten kunt u optionele tekst laten weergeven in het aanmeldingsvenster en vergrendelingsscherm (bijvoorbeeld een bericht 'If Lost, Return to' (Indien verloren, retourneren naar) en Informatie over de assettag). 

>[!IMPORTANT]
> Deze mogelijkheid wordt ondersteund op apparaten die onder supervisie staan en waarop iOS 9.3 of hoger wordt uitgevoerd.

1. Kies op de blade **Apparaatfuncties** de optie **
Configuratie voor gedeelde apparaten (alleen onder supervisie)**.
2. Configureer op de blade **
Configuratie voor gedeelde apparaten (alleen onder supervisie)** het volgende:
    - **Informatie over de assettag**: voer informatie over de assettag van het apparaat in. Bijvoorbeeld: **Eigendom van Contoso Corp**. De informatie die u invoert, wordt toegepast op alle apparaten waaraan u dit profiel toewijst.
    - **Voetnoot voor het vergrendelingsscherm**: voer een opmerking in waarmee u het apparaat kunt terugkrijgen als het verloren of gestolen is. Bijvoorbeeld: **Als gevonden, bel dan nummer**.
3. Als u klaar bent, kiest u **OK** totdat u terugkeert naar de blade **Profiel maken** en kiest u vervolgens **Maken**. 

