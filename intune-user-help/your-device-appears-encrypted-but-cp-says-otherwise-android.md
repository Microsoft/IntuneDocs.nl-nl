---
title: Uw Android-apparaat lijkt versleuteld te zijn
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 05/25/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ba593c08-1a78-4013-8525-b45a948772ec
searchScope: User help
ROBOTS: 
ms.reviewer: arnab
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 269ad7968242f8f5ce7095c9c73347987675e846
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/01/2017
---
# <a name="your-android-device-seems-to-be-encrypted-but-company-portal-says-otherwise"></a>Uw Android-apparaat lijkt versleuteld te zijn, maar de Bedrijfsportal geeft anders aan

Wanneer u een apparaat versleutelt, versleutelt u de informatie erop op met behulp van een geheime sleutel die alleen bij u bekend is. Zo wordt voorkomen dat onbevoegden er toegang toe hebben. Als eerste stap om uw informatie te beveiligen, vereist uw organisatie dat u uw Android-apparaat versleutelt voordat u toegang krijgt tot bedrijfsbestanden, e-mail of gegevens.

## <a name="common-issues"></a>Veelvoorkomende problemen

Voor nieuwere versies van Android, met name vanaf v7.0, is een opstartwachtwoordcode vereist om ervoor te zorgen dat uw apparaat volledig wordt versleuteld. Fabrikanten van verschillende apparaten hebben verschillende beschrijvingen en locaties voor de opstartwachtwoordcode. In de meeste gevallen heet dit Beveiligd opstarten. 

## <a name="solutions"></a>Oplossingen

### <a name="add-a-startup-pin"></a>Een opstartpincode toevoegen

Voor bepaalde Android-apparaten moet u een opstartpincode instellen om ervoor te zorgen dat uw apparaat beveiligd is. Er zijn veel Android-versies van veel verschillende fabrikanten. U kunt dit probleem oplossen door in uw instellingen-app de locatie te zoeken waar u deze optie kunt inschakelen. Op de Samsung Galaxy S7 schakelt u Beveiligd opstarten bijvoorbeeld in bij **Instellingen** > **Vergrendelscherm en beveiliging** > **Beveiligd opstarten**.  

### <a name="downgrade-your-version-of-android"></a>Uw versie van Android downgraden
Als uw apparaat u de optie biedt naar Android 6.0+ te downgraden, kies daar dan voor. Er is een risico van gegevensverlies als u uw apparaat probeert te downgraden. Anders is het raadzaam dat u contact opneemt met uw IT-beheerder om dit probleem op te lossen. U kunt de contactgegevens voor uw IT-beheerder vinden op de [Bedrijfsportalwebsite ](http://portal.manage.microsoft.com).

## <a name="specific-manufacturer-issues"></a>Fabrikant-specifieke problemen

Sommige Android-apparaten met versie 7.0+ versleutelen gegevens op een manier die inconsistent is met bepaalde Android-platformstandaarden. Deze apparaten lijken vanuit de fabriek al gecodeerd te zijn, maar Intune ziet de gebruikte methoden als een risico dat de gegevens van het apparaat onbeschermd zijn tegen kwaadwillende gebruikers die fysieke toegang tot het apparaat hebben.

> [!Note]
> Microsoft werkt samen met fabrikanten aan het oplossen van problemen die worden gevonden tijdens het testen of die gebruikers rapporteren. Dit artikel wordt bijgewerkt wanneer nieuwe informatie beschikbaar is. 

## <a name="known-devices"></a>Bekende apparaten

### <a name="known-devices-that-can-be-updated-to-fix-this-issue"></a>Bekende apparaten die kunnen worden bijgewerkt om dit probleem op te lossen

Als u een van de volgende apparaten hebt, kan dit probleem optreden als u uw apparaat niet hebt bijgewerkt naar de meest recente versie van Android. U kunt de updates voor deze apparaten installeren bij **Instellingen** > **Bijwerken**. 

- [Huawei Honor 8](http://consumer.huawei.com/en/support/mobile-phones/honor8_en-sup.htm)
- [Huawei P9](http://consumer.huawei.com/mobile-phones/p9/index.html)

### <a name="known-devices-that-currently-cannot-be-updated-to-fix-this-issue"></a>Bekende apparaten die momenteel niet kunnen worden bijgewerkt om dit probleem op te lossen

- [Huawei Mate 8](http://consumer.huawei.com/en/mobile-phones/mate8/index.htm)
- [Xiaomi Mi-smartphones](https://xiaomi-mi.com/mi-smartphones/)
