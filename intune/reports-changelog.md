---
title: Wijzigingenlogboek Intune-datawarehouse | Microsoft Docs
description: Een lijst met wijzigingen in de API van Intune-datawarehouse.
keywords: Intune-datawarehouse
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 11/14/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: E85DBB2D-67BB-4E10-82D6-E43046B9C43C
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 7269d0552a0c01e4702eaae861d6c24f3f4f6f02
ms.sourcegitcommit: d26930f45ba9e6292a49bcb08defb5b3f14b704b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/15/2017
---
# <a name="change-log-for-the-intune-data-warehouse-api"></a>Wijzigingenlogboek voor de API van Intune-datawarehouse

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Houd updates voor Intune-datawarehouse bij.

## <a name="1710"></a>1710
_Uitgebracht: november 2017_

### <a name="a-new-entity-collection-named-current-user-is-limited-to-currently-active-user-data----1544273---"></a>De nieuwe entiteitverzameling Huidige gebruiker is beperkt tot gegevens van actieve gebruikers <!-- 1544273 -->

De entiteitverzameling **Gebruikers** bevat gegevens van de afgelopen maand. Deze records bevatten gebruikersstatussen gedurende de periode van gegevensverzameling, ook als de gebruiker is verwijderd. Een gebruiker kan bijvoorbeeld worden toegevoegd aan Intune en vervolgens ergens gedurende de afgelopen maand zijn verwijderd. Ook al is deze gebruiker niet aanwezig op het moment dat het rapport wordt gegenereerd, toch zijn de gebruiker en de status aanwezig in de gegevens. U kunt een rapport maken dat de duur van de historische aanwezigheid van de gebruiker in uw gegevens weergeeft.

Daarentegen bevat de nieuwe entiteitverzameling **Huidige gebruiker** alleen gebruikers die niet zijn verwijderd. De entiteitverzameling **Huidige gebruiker** bevat alleen gebruikers die momenteel actief zijn. Zie [Naslaginformatie voor huidige gebruikersentiteit](reports-ref-current-user.md) voor informatie over de entiteitverzameling **Huidige gebruiker**.

## <a name="1709"></a>1709
_Uitgebracht: oktober 2017_

### <a name="user-device-association-entity-collection-added-to-intune-data-warehouse-data-model----1187917---"></a>Verzameling voor koppelingsentiteit voor gebruikersapparaten toegevoegd aan het Intune-datawarehouse-gegevensmodel <!-- 1187917 -->

U kunt rapporten en gegevensvisualisaties maken met behulp van de informatie over de gebruikersapparaatkoppelingen; deze koppelen verzamelingen over gebruikers en apparaten. Het gegevensmodel is toegankelijk via het Power BI-bestand (PBIX) dat wordt opgehaald op de datawarehouse-pagina in Intune, via het OData-eindpunt of door een aangepaste client te ontwikkelen. Zie de [Gebruikersapparaatkoppelingen](reports-ref-user-device.md) voor meer informatie.

### <a name="new-entities-in-the-in-data-warehouse-data-model----1479526--------"></a>Nieuwe entiteiten in het datawarehouse-gegevensmodel <!-- 1479526 --><!-- -->

 - De entiteit [ **UserDeviceAssociation**](reports-ref-user-device.md) is toegevoegd. **UserDeviceAssociation** bevat gebruikersapparaatkoppelingen in uw organisatie. U kunt rapporten en gegevensvisualisaties maken met behulp van de informatie over de gebruikersapparaatkoppelingen; deze koppelen verzamelingen over gebruikers en apparaten.  
 - De entiteit [ **IntuneManagementExtension**](reports-ref-intunemanagementextension.md) is toegevoegd. **IntuneManagementExtension** bevat entiteiten voor mobiele apparaten die informatie bijhouden, zoals de versie en de status van de installatie.

## <a name="next-steps"></a>Volgende stappen
 - Ontdek [wat er elke week nieuw is in Intune](whats-new.md). U vindt hier ook informatie over toekomstige wijzigingen, belangrijke kennisgevingen betreffende de service en informatie over oudere releases. 
 - Lees het [Microsoft Intune-blog](http://go.microsoft.com/fwlink/?LinkID=273882).