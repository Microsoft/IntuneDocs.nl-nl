---
title: Uw Android-apparaat lijkt versleuteld te zijn | Microsoft Docs
description: De versleutelings status in Bedrijfsportal en Microsoft Intune app omzetten
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 08/14/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.subservice: end-user
ms.technology: ''
ms.assetid: ba593c08-1a78-4013-8525-b45a948772ec
searchScope:
- User help
ROBOTS: ''
ms.reviewer: arnab
ms.suite: ems
ms.custom: intune-enduser
ms.collection: ''
ms.openlocfilehash: 442f44ac22587925c8a775d51a7e88e5e72473b3
ms.sourcegitcommit: caee3c3fa77586314aa8040b0caf32a0527b669e
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 01/10/2020
ms.locfileid: "75857164"
---
# <a name="device-encrypted-but-apps-say-otherwise"></a>Apparaat is versleuteld, maar apps zeggen anders

Als Bedrijfsportal of de Microsoft Intune-app zegt dat uw apparaat niet is versleuteld, maar u zeker weet dat dit het geval is, probeert u de stappen in dit artikel uit te voeren.  

## <a name="add-a-startup-pin"></a>Een opstartpincode toevoegen

Voor bepaalde Android-apparaten moet u een opstartpincode instellen om ervoor te zorgen dat uw apparaat beveiligd is. De locatie van deze instelling vindt u in de app **instellingen** van uw apparaat. De naam en locatie van de instelling kunnen verschillen. Op de Samsung Galaxy-S7 wordt de instelling bijvoorbeeld aangeduid als **beveiligd opstarten**. Als u dit wilt inschakelen en een wachtwoord code wilt maken, gaat u naar **instellingen** > **scherm vergren delen en beveiliging** > **beveiligd opstarten**.  

## <a name="encrypt-the-entire-device"></a>Versleutel het hele apparaat

Deze sectie is alleen van toepassing op de app Bedrijfsportal. Op sommige apparaten kunt u kiezen of u het hele apparaat of alleen de gebruikte ruimte wilt versleutelen. Kies de optie voor het versleutelen van het hele apparaat. Als u ervoor hebt gekozen alleen de gebruikte ruimte te versleutelen:

1. [Verwijder dit apparaat uit de bedrijfsportal](unenroll-your-device-from-intune-android.md).
2. Ontsleutel de gebruikte ruimte.  
3. Versleutel het hele apparaat.  
4. Schrijf het apparaat opnieuw in.  

## <a name="downgrade-your-version-of-android"></a>Uw versie van Android downgraden

Deze sectie is alleen van toepassing op de app Bedrijfsportal. Als uw apparaat u de optie biedt naar Android 6.0 en later te downgraden, kies daar dan voor. Er is een risico van gegevensverlies als u uw apparaat probeert te downgraden. Anders is het raadzaam dat u contact opneemt met het ondersteuningsteam van uw bedrijf om dit probleem op te lossen. Haal contactgegevens voor uw bedrijfsondersteuning op bij de [Bedrijfsportalwebsite](https://go.microsoft.com/fwlink/?linkid=2010980).  

## <a name="specific-manufacturer-issues"></a>Fabrikant-specifieke problemen

Sommige Android-apparaten met versie 7.0 en later versleutelen gegevens op een manier die inconsistent is met bepaalde Android-platformstandaarden. Met deze versleutelings methoden wordt een risico op de apparaatgegevens gelegd. Als gevolg hiervan worden deze apparaten niet ondersteund.

Zie het artikel [ondersteunde besturings systemen en browsers in intune](https://docs.microsoft.com/intune/fundamentals/supported-devices-browsers#supported-samsung-knox-standard-devices)voor een niet-limitatieve lijst van ondersteunde Android-apparaten. Als uw apparaat niet wordt weer gegeven, raadpleegt u de fabrikant van het apparaat of neemt u contact op met de ondersteunings medewerker.

> [!Note]
> Microsoft werkt samen met fabrikanten aan het oplossen van problemen die worden gevonden tijdens het testen of die gebruikers rapporteren. Dit artikel wordt bijgewerkt wanneer nieuwe informatie beschikbaar is.

## <a name="update-devices"></a>Apparaten bijwerken

Als u uw apparaat niet hebt bijgewerkt naar de meest recente versie van Android, gaat u naar de **instellingen** -app van uw apparaat en selecteert u **bijwerken**.  

## <a name="next-steps"></a>Volgende stappen

Nog hulp nodig? Neem contact op met het ondersteuningsteam van het bedrijf (zie de [bedrijfsportalwebsite](https://go.microsoft.com/fwlink/?linkid=2010980) voor contactgegevens) of stuur een e-mail naar het <a href="mailto:wintunedroidfbk@microsoft.com?subject=I'm having trouble with enrolling my Android device&body=Describe the issue you're experiencing here.">Microsoft Android-team</a>.  
