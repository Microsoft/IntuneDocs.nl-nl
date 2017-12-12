---
title: Intune-configuratie-instellingen voor gedeelde apparaten voor iOS
titlesuffix: Azure portal
description: Lees welke Intune-instellingen u kunt gebruiken voor het weergeven van informatie op het vergrendelingsscherm van een iOS-apparaat.
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 07/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f122e4ee-90e7-4b42-b801-8c1c7c0a5bf7
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1f9256594493aeebda9ab65e3df269ea7acaca5b
ms.sourcegitcommit: 3b397b1dcb780e2f82a3d8fba693773f1a9fcde1
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/12/2017
---
# <a name="shared-device-configuration-settings-to-display-messages-on-the-ios-device-lock-screen"></a>Configuratie-instellingen voor gedeelde apparaten voor het weergeven van berichten op het vergrendelingsscherm van een iOS-apparaat

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Met de configuratie-instellingen voor gedeelde apparaten kunt u optionele tekst weergeven in het aanmeldingsvenster en op het vergrendelingsscherm. U kunt bijvoorbeeld een bericht weergeven met de tekst 'Indien gevonden, graag contact opnemen' en informatie over de assettag. 

>[!IMPORTANT]
> Deze mogelijkheid wordt ondersteund op apparaten die onder supervisie staan en waarop iOS 9.3 of hoger wordt uitgevoerd.

## <a name="create-shared-device-settings"></a>Instellingen voor gedeelde apparaten maken

1. Kies op de blade **Apparaatfuncties** de optie **Configuratie voor gedeelde apparaten (alleen onder supervisie)**.
2. Configureer de volgende instellingen op de blade **Configuratie voor gedeelde apparaten (alleen onder supervisie)**:
    - **Informatie over de assettag**: voer informatie over de assettag van het apparaat in. Bijvoorbeeld: **Eigendom van Contoso Corp**. De informatie die u invoert, wordt toegepast op alle apparaten waaraan u dit profiel toewijst.
    - **Voetnoot voor het vergrendelingsscherm**: voer een opmerking in waarmee u het apparaat misschien kunt terugkrijgen als het verloren of gestolen is. Bijvoorbeeld: **Indien gevonden, bel dit nummer**.
3. Als u klaar bent, kiest u **OK** totdat u terugkeert naar de blade **Profiel maken** en kiest u vervolgens **Maken**. 


## <a name="next-steps"></a>Volgende stappen

U kunt het apparaatprofiel nu toewijzen aan de gewenste groepen. Zie [Apparaatprofielen toewijzen](device-profile-assign.md) voor meer informatie.
