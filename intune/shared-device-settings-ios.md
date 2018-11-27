---
title: Microsoft Intune-configuratie-instellingen voor gedeelde apparaten voor iOS
titlesuffix: ''
description: Lees welke Microsoft Intune-instellingen u kunt gebruiken voor het weergeven van informatie op het vergrendelingsscherm van een iOS-apparaat.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 3/5/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 638b4b3ebc83917faae0d34ec407b8ad47b4a4fb
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/20/2018
ms.locfileid: "52183380"
---
# <a name="shared-device-configuration-settings-to-display-messages-on-the-ios-device-lock-screen"></a>Configuratie-instellingen voor gedeelde apparaten voor het weergeven van berichten op het vergrendelingsscherm van een iOS-apparaat

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

In dit artikel leest u welke Microsoft Intune-instellingen u kunt gebruiken voor het weergeven van informatie op het vergrendelingsscherm van een iOS-apparaat.

Met de configuratie-instellingen voor gedeelde apparaten kunt u optionele tekst weergeven in het aanmeldingsvenster en op het vergrendelingsscherm. U kunt bijvoorbeeld een bericht weergeven met de tekst 'Indien gevonden, graag contact opnemen' en informatie over de assettag. 

>[!IMPORTANT]
> Deze mogelijkheid wordt ondersteund op apparaten die onder supervisie staan en waarop iOS 9.3 of hoger wordt uitgevoerd.

## <a name="create-shared-device-settings"></a>Instellingen voor gedeelde apparaten maken

1. Navigeer vanaf [Intune in Azure Portal](https://portal.azure.com) naar [ **Apparaatfuncties** in het apparaatconfiguratiegebied](device-features-configure.md). 
1. Kies in het deelvenster **Apparaatfuncties** de optie **Configuratie voor gedeelde apparaten (alleen onder supervisie)**.
2. Configureer de volgende instellingen in het deelvenster **Configuratie voor gedeelde apparaten (alleen onder supervisie)**:
    - **Informatie over de assettag**: voer informatie over de assettag van het apparaat in. Bijvoorbeeld: **Eigendom van Contoso Corp**. De informatie die u invoert, wordt toegepast op alle apparaten waaraan u dit profiel toewijst.
    - **Voetnoot voor het vergrendelingsscherm**: voer een opmerking in waarmee u het apparaat misschien kunt terugkrijgen als het verloren of gestolen is. Bijvoorbeeld: **Indien gevonden, bel dit nummer**.
3. Als u klaar bent, kiest u **OK** totdat u terugkeert naar het deelvenster **Profiel maken** en kiest u vervolgens **Maken**. 


## <a name="next-steps"></a>Volgende stappen

U kunt het apparaatprofiel nu toewijzen aan de gewenste groepen. Zie [Apparaatprofielen toewijzen](device-profile-assign.md) voor meer informatie.
