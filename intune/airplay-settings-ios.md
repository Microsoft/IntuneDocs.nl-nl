---
title: Intune AirPlay-instellingen voor iOS-apparaten
titleSuffix: Intune Azure preview
description: In dit onderwerp leest u hoe u met Intune automatisch iOS-apparaten kunt verbinden met AirPlay- compatibele apparaten.
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 712a79fb-14ef-4f6b-aba5-1dfca900afd2
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: ad2f20603261ec0eac4156facd3fd23b2982f517
ms.contentlocale: nl-nl
ms.lasthandoff: 05/23/2017


---

# <a name="intune-airplay-settings-for-ios-devices"></a>Intune AirPlay-instellingen voor iOS-apparaten

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Gebruik deze instellingen om iOS-apparaten die u beheert te verbinden met AirPlay-compatibele apparaten (zoals Apple tv’s) in uw netwerk.
Met deze functie kunt u het volgende doen:

- **Een apparaat- en een wachtwoordenlijst configureren**: Apparaten inrichten met de naam en het wachtwoord van AirPlay-apparaten zodat deze automatisch verbinding maken wanneer deze binnen het bereik zijn. Als u een wachtwoord opgeeft, hoeven eindgebruikers dit niet op te geven wanneer ze verbinding maken.
- **Toegestane bestemmingen configureren**: Een lijst met AirPlay-apparaten configureren (op apparaat-id). Eindgebruikers kunnen alleen de vermelde apparaten zien en hiermee verbinding maken (alleen voor apparaten onder supervisie).

## <a name="get-started"></a>Aan de slag

1. Kies op de blade **Apparaatfuncties** het item **AirPlay**.
2. Kies op de blade **AirPlay** een of beide van de volgende acties:

## <a name="configure-a-device-and-password-list"></a>Een apparaat- en een wachtwoordenlijst configureren

1. Voer op de blade **Wachtwoorden** de **Apparaatnaam** en het **Wachtwoord** in van een Airplay-apparaat, bijvoorbeeld **Contoso Apple TV**.
2. Na het invoeren van de apparaatdetails klikt u op **Toevoegen**. Het apparaat wordt weergegeven in de lijst **Apparaatnaam**.
3. Ga door naar het toevoegen van apparaten. Als u klaar bent, kiest u **OK**.


## <a name="configure-allowed-destinations"></a>Toegestane bestemmingen configureren

1. Voer op de blade *Toegestane doelen (alleen onder supervisie)* de **Apparaat-ID** van een Airplay-apparaat in, bijvoorbeeld 52:46:CD:51:83:4 C.
2. Na het invoeren van de apparaat-ID klikt u op **Toevoegen**. De id wordt weergegeven in de lijst **Apparaat-id**.
3. Ga door naar het toevoegen van apparaten. Als u klaar bent, kiest u **OK**.

U kunt apparaten, wachtwoorden en toegestane bestemmingen ook importeren uit een bestand met door komma's gescheiden waarden (csv).



