---
title: Wijzigingenlogboek Intune-datawarehouse | Microsoft Docs
description: Een lijst met wijzigingen in de API van Intune-datawarehouse.
keywords: Intune-datawarehouse
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 02/23/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: E85DBB2D-67BB-4E10-82D6-E43046B9C43C
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 67eedf528763ae302e3850710b3fab026e15f813
ms.sourcegitcommit: 80a2eefc1896a42cc2bc16be23093d1abf58b088
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/27/2018
---
# <a name="change-log-for-the-intune-data-warehouse-api"></a>Wijzigingenlogboek voor de API van Intune-datawarehouse

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Houd updates voor Intune-datawarehouse bij.

## <a name="1801"></a>1801
_Uitgebracht in januari 2018_

### <a name="intune-data-warehouse-application-only-authentication----1867540---"></a>Intune-datawarehouse-verificatie enkel voor toepassing <!-- 1867540 -->

U kunt een toepassing instellen met behulp van Azure Active Directory (Azure AD) en verifiëren bij Intune Datawarehouse. Zie voor meer informatie [Intune-datawarehouse-verificatie enkel voor toepassing](data-warehouse-app-only-auth.md).

### <a name="azure-ad-and-intune-credential-requirements----2077525---"></a>Azure AD- en Intune-referentievereisten <!-- 2077525 -->

- Intune-licenties hoeven niet meer te worden toegewezen aan de gebruiker bij het openen van het Intune-datawarehouse (met inbegrip van de API).
- De Intune-rolnaam is veranderd van **Rapporten** in **Intune-datawarehouse**. 

    Zie [Azure AD en Intune-referentievereisten](reports-api-url.md#azure-ad-and-intune-credential-requirements) voor meer informatie.

### <a name="odata-query-options----2077711---"></a>OData-queryopties <!-- 2077711 -->

U kunt <code>$select</code> gebruiken als OData-queryparameter. De huidige versie ondersteunt de volgende OData-queryparameters: <code>$filter</code>, <code>$orderby</code>, <code>$select</code>, <code>$skip</code> en <code>$top</code>. Zie [OData-queryopties](reports-api-url.md#odata-query-options) voor meer informatie.

### <a name="new-entities-in-the-in-data-warehouse-data-model----2077804---"></a>Nieuwe entiteiten in het datawarehouse-gegevensmodel <!-- 2077804 -->

 - De entiteit [**MobileAppDeviceuserInstallStatus**](reports-ref-application.md#mobileappdeviceuserinstallstatus) is toegevoegd. De **MobileAppDeviceUserInstallStatus** toont de installatiestatus van een mobiele app voor een bepaald apparaat en een bepaalde gebruiker.
 - De entiteit [**MobileAppInstallState**](reports-ref-application.md#mobileappinstallstate) is toegevoegd. De entiteit **MobileAppInstallState** vertegenwoordigt de installatiestatus van een mobiele toepassing nadat deze is toegewezen aan een groep apparaten, gebruikers of beide. 

## <a name="1710"></a>1710
_Uitgebracht: november 2017_

### <a name="a-new-entity-collection-named-current-user-is-limited-to-currently-active-user-data----1544273---"></a>De nieuwe entiteitverzameling Huidige gebruiker is beperkt tot gegevens van actieve gebruikers <!-- 1544273 -->

De entiteitverzameling **Gebruiker** bevat alle Azure Active Directory-gebruikers (Azure AD) met toegewezen licenties in uw onderneming. Deze records bevatten gebruikersstatussen gedurende de periode van gegevensverzameling, ook als de gebruiker is verwijderd. Een gebruiker kan bijvoorbeeld worden toegevoegd aan Intune en vervolgens ergens gedurende de afgelopen maand zijn verwijderd. Ook al is deze gebruiker niet aanwezig op het moment dat het rapport wordt gegenereerd, toch zijn de gebruiker en de status aanwezig in de gegevens. U kunt een rapport maken dat de duur van de historische aanwezigheid van de gebruiker in uw gegevens weergeeft.

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
