---
title: Intune-filterinstellingen voor webinhoud op iOS-apparaten
titleSuffix: Intune on Azure
description: Meer informatie over welke instellingen u gebruikt om toegang tot websites toe te staan of te blokkeren vanaf iOS-apparaten.
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 7/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 16aa0f3c-8977-4495-9fbe-ca30ad278c9e
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1fb2ce8ed9db6ff808cac2ee8ff46ee865dbdf35
ms.sourcegitcommit: c9b3a95bf529b6cb2a2bdacbc49127dfa0c233e5
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/05/2017
---
# <a name="web-content-filter-settings-for-ios-devices"></a>Filterinstellingen voor webinhoud op iOS-apparaten

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Gebruik deze instellingen voor het configureren van URL's die eindgebruikers van webbrowsers op iOS-apparaten wel of niet kunnen bezoeken. U kunt dit op twee manieren doen:

- **URL's configureren**: gebruik het ingebouwde webfilter van Apple dat zoekt naar ongepaste termen, zoals grof of seksueel getint taalgebruik. Met deze functie wordt elke webpagina geëvalueerd tijdens het laden en wordt ongeschikte inhoud herkend en geblokkeerd. U kunt ook URL's configureren die niet worden gecontroleerd door het filter of URL's die worden geblokkeerd, ongeacht de filterinstellingen.

- **Alleen specifieke websites** (alleen voor Safari): Deze URL's worden toegevoegd aan de bladwijzers van de Safari-browser. De gebruiker mag **alleen** deze sites bezoeken. Andere sites zijn niet toegankelijk. Gebruik deze optie alleen als u de exacte lijst van URL's weet die gebruikers mogen bezoeken.
Als u geen URL's opgeeft, kunnen eindgebruikers geen websites openen, met uitzondering van microsoft.com microsoft.net en apple.com.



## <a name="get-started"></a>Aan de slag

1. Kies op de blade Apparaatfuncties de optie **Filter voor webinhoud (alleen onder supervisie)**.
2. Kies op de blade **Filter voor webinhoud** het **Filtertype** dat u wilt configureren uit het volgende:
    - **Niet geconfigureerd**: er wordt geen filtering uitgevoerd.
    - **URL's configureren**
    - **Alleen specifieke websites**
3. Afhankelijk van het type filter dat u gebruikt, voert u vervolgens een van de onderstaande procedure uit:


## <a name="configure-urls"></a>URL's configureren

1. Kies op de blade **Filter voor webinhoud** een van de volgende instellingen, indien nodig:
    - **Toegestane URL's**: Voer op de blade **Toegestane URL's** de URL's in die u wilt toestaan (het webfilter van Apple wordt genegeerd). Kies Enter na elke ingevoerde URL.
    - **Geblokkeerde URL's**: Voer op de blade **Geblokkeerde URL's** de URL's in die u wilt blokkeren (ongeacht het webfilter van Apple). Kies Enter na elke ingevoerde URL.
2. Klik op **OK**als u klaar bent.


## <a name="specific-websites-only"></a>Alleen specifieke websites

1. Configureer op de blade **Filter voor webinhoud** de volgende instellingen voor elke website die u wilt toestaan:
    - **URL**: voer de URL in van de website die u wilt toestaan, bijvoorbeeld **http://www.contoso.com**.
    - **Pad naar bladwijzer**: voer het pad in naar de locatie waar u de bladwijzer wilt opslaan, bijvoorbeeld **Contoso/Business-Apps**. Als u geen pad toevoegt, wordt de bladwijzer toegevoegd aan de standaardmap voor bladwijzers op het apparaat.
    - **Titel**: geef een beschrijvende titel voor de bladwijzer op.
2. Klik op **Toevoegen** nadat u de gegevens voor elke website hebt ingevoerd.
3. Klik op **OK**als u klaar bent.

>[!IMPORTANT] 
> De volgende URL's zijn automatisch toegestaan in Intune.
> - www.microsoft.com
> - www.microsoft.net
> - www.apple.com

## <a name="finish-up"></a>Voltooien

Kies **OK** totdat u terugkeert naar de blade **Profiel maken** en kies vervolgens **Maken**.

## <a name="next-steps"></a>Volgende stappen

U kunt het apparaatprofiel nu toewijzen aan de gewenste groepen. Zie [Apparaatprofielen toewijzen](device-profile-assign.md) voor meer informatie.
