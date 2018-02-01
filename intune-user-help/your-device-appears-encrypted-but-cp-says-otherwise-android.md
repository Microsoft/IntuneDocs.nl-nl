---
title: Uw Android-apparaat lijkt versleuteld te zijn | Microsoft Docs
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: dougeby
ms.date: 11/14/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ba593c08-1a78-4013-8525-b45a948772ec
searchScope:
- User help
ROBOTS: 
ms.reviewer: arnab
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: ab67a6f2fd1f861ba197464a9e369ca0b54e6b5d
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/25/2018
---
# <a name="your-android-device-seems-to-be-encrypted-but-company-portal-says-otherwise"></a>Uw Android-apparaat lijkt versleuteld te zijn, maar de Bedrijfsportal geeft anders aan

Wanneer u een apparaat versleutelt, versleutelt u de informatie erop op met behulp van een geheime sleutel die alleen bij u bekend is. Dit voorkomt dat onbevoegden er toegang toe hebben. Bij veel organisaties moeten gebruikers hun Android-apparaten versleutelen voordat ze toegang krijgen tot bedrijfsbestanden, -e-mail of -gegevens.

## <a name="common-issues"></a>Veelvoorkomende problemen

Voor nieuwere versies van Android, met name vanaf v7.0, is een opstartwachtwoordcode vereist om ervoor te zorgen dat uw apparaat volledig wordt versleuteld. Fabrikanten van verschillende apparaten hebben verschillende beschrijvingen en locaties voor de opstartwachtwoordcode. In de meeste gevallen heet deze instelling Beveiligd opstarten. 

## <a name="solutions"></a>Oplossingen

### <a name="add-a-startup-pin"></a>Een opstartpincode toevoegen

Voor bepaalde Android-apparaten moet u een opstartpincode instellen om ervoor te zorgen dat uw apparaat beveiligd is. Er zijn veel Android-versies van veel verschillende fabrikanten. U kunt dit probleem oplossen door in uw instellingen-app de locatie te zoeken waar u deze optie kunt inschakelen. Op de Samsung Galaxy S7 schakelt u Beveiligd opstarten bijvoorbeeld in bij **Instellingen** > **Vergrendelscherm en beveiliging** > **Beveiligd opstarten**.  

### <a name="encrypt-the-entire-device"></a>Versleutel het hele apparaat

Op sommige apparaten kunt u kiezen of u het hele apparaat of alleen de gebruikte ruimte wilt versleutelen. Kies de optie om het hele apparaat te versleutelen in plaats van 'Alleen gebruikte ruimte'. Als u alleen de gebruikte ruimte al hebt versleuteld:

1. [Verwijder dit apparaat uit de bedrijfsportal](unenroll-your-device-from-intune-android.md)
2. Ontsleutel de gebruikte ruimte
3. Versleutel het hele apparaat
4. Schrijf het apparaat opnieuw in

### <a name="downgrade-your-version-of-android"></a>Uw versie van Android downgraden

Als uw apparaat u de optie biedt naar Android 6.0+ te downgraden, kies daar dan voor. Er is een risico van gegevensverlies als u uw apparaat probeert te downgraden. Anders is het raadzaam dat u contact opneemt met het ondersteuningsteam van uw bedrijf om dit probleem op te lossen. U kunt de contactgegevens voor het ondersteuningsteam van uw bedrijf vinden op de [Bedrijfsportalwebsite](https://portal.manage.microsoft.com#HelpDeskDialog).

## <a name="specific-manufacturer-issues"></a>Fabrikant-specifieke problemen

Sommige Android-apparaten met versie 7.0+ versleutelen gegevens op een manier die inconsistent is met bepaalde Android-platformstandaarden. Deze apparaten lijkt versleuteld, zelfs wanneer ze gloednieuw zijn. Intune erkent dat de versleutelingsmethoden van deze apparaten een risico zijn voor de informatie op het apparaat. Dit risico komt voornamelijk voort uit kwaadwillende gebruikers die fysieke toegang tot het apparaat hebben.

> [!Note]
> Microsoft werkt samen met fabrikanten aan het oplossen van problemen die worden gevonden tijdens het testen of die gebruikers rapporteren. Dit artikel wordt bijgewerkt wanneer nieuwe informatie beschikbaar is. 

## <a name="known-devices"></a>Bekende apparaten

### <a name="known-devices-that-can-be-updated-to-fix-this-issue"></a>Bekende apparaten die kunnen worden bijgewerkt om dit probleem op te lossen

Als u een van de volgende apparaten hebt, kan dit probleem optreden als u uw apparaat niet hebt bijgewerkt naar de meest recente versie van Android. U kunt de updates voor deze apparaten installeren bij **Instellingen** > **Bijwerken**. 

- [Huawei Honor 8](http://consumer.huawei.com/en/support/mobile-phones/honor8_en-sup.htm)
- [Huawei P9](http://consumer.huawei.com/en/phones/p9/)

### <a name="known-devices-that-currently-cannot-be-updated-to-fix-this-issue"></a>Bekende apparaten die momenteel niet kunnen worden bijgewerkt om dit probleem op te lossen

U kunt dit probleem niet oplossen voor de volgende apparaten. U moet wellicht een ander apparaat gebruiken voor toegang tot bedrijfsresources. 

- [Huawei Mate 8](https://consumer.huawei.com/en/mobile-phones/mate8/index.htm)
- [OPPO-apparaten](http://www.oppo.com/en/smartphones)
- [Vivo-apparaten](https://www.vivo.co.in)
- [Xiaomi Mi-smartphones](https://xiaomi-mi.com/mi-smartphones/)
