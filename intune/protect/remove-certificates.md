---
title: SCEP- of PKCS-certificaten verwijderen in Microsoft Intune - Azure | Microsoft Docs
titleSuffix: ''
description: Beheerders kunnen certificaten uit Microsoft Intune verwijderen door apparaten te wissen of buiten gebruik te stellen. Er zijn enkele situaties waarin de certificaten automatisch worden verwijderd, zoals bij het uitschrijven van een apparaat of het verwijderen van een nalevingsbeleid. Er zijn enkele situaties waarin certificaten automatisch op het apparaat blijven gehandhaafd, wanneer bijvoorbeeld de Intune-licentie verloren gaat of wordt verwijderd. Bekijk de verschillende manieren voor Android-, Android Enterprise-, iOS/iPadOS-, macOS- en Windows-apparaten.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 11/21/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.reviewer: lacranda
ms.openlocfilehash: a77780c05b0f637a4ee5100f8c7a1a729c3ec674
ms.sourcegitcommit: 47c9af81c385c7e893fe5a85eb79cf08e69e6831
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/25/2020
ms.locfileid: "77576259"
---
# <a name="remove-scep-and-pkcs-certificates-in-microsoft-intune"></a>SCEP- en PKCS-certificaten verwijderen in Microsoft Intune

In Microsoft Intune kunt u SCEP-certificaatprofielen (Simple Certificate Enrollment Protocol) en PKCS-certificaatprofielen (Public Key Cryptography Standards) gebruiken om certificaten aan apparaten toe te voegen.

Deze certificaten kunnen worden verwijderd wanneer u het apparaat [wist](../remote-actions/devices-wipe.md#wipe) of [buiten gebruik stelt](../remote-actions/devices-wipe.md#retire). Er zijn ook scenario's waarin certificaten automatisch worden verwijderd en scenario's waarin certificaten op het apparaat blijven gehandhaafd. In dit artikel worden enkele veelvoorkomende situaties en de gevolgen voor PKCS- en SCEP-certificaten beschreven.

> [!NOTE]
> Als u certificaten wilt verwijderen en intrekken voor een gebruiker die uit on-premises Active Directory (AD) of Azure Active Directory (Azure AD) wordt verwijderd, moet u de stappen in de goede volgorde uitvoeren:
>
> 1. Wis het apparaat van de gebruiker of stel dit buiten gebruik.
> 2. Verwijder de gebruiker uit de on-premises Active Directory of Azure AD.

## <a name="manually-deleted-certificates"></a>Handmatig certificaten verwijderen

Handmatige verwijdering van een certificaat is een scenario dat van toepassing is op platformen en certificaten die zijn ingericht door SCEP- of PKCS-certificaatprofielen. Een gebruiker kan bijvoorbeeld een certificaat van een apparaat verwijderen wanneer het apparaat doel blijft van een certificaatbeleid.

Als het certificaat in dit scenario wordt verwijderd, is het apparaat de volgende keer dat het bij Intune incheckt niet compatibel, omdat het verwachte certificaat ontbreekt. Intune geeft vervolgens een nieuw certificaat uit om het apparaat weer compatibel te maken. Er is geen verdere actie nodig om het apparaat te herstellen.

## <a name="windows-devices"></a>Windows-apparaten

### <a name="scep-certificates"></a>SCEP-certificaten

Een SCEP-certificaat wordt ingetrokken *en* verwijderd wanneer:

- Een eindgebruiker zich uitschrijft.
- Een beheerder de actie [Wissen](../remote-actions/devices-wipe.md#wipe) uitvoert.
- Een beheerder de actie [Buiten gebruik stellen](../remote-actions/devices-wipe.md#retire) uitvoert.
- Het apparaat wordt verwijderd uit een Azure AD-groep.
- Een certificaatprofiel wordt verwijderd uit de groepstoewijzing.

Een SCEP-certificaat wordt ingetrokken wanneer:

- Een beheerder wijzigingen aanbrengt in het SCEP-profiel of dit bijwerkt.

Een basiscertificaat wordt verwijderd wanneer:

- Een eindgebruiker zich uitschrijft.
- Een beheerder de actie [Wissen](../remote-actions/devices-wipe.md#wipe) uitvoert.
- Een beheerder de actie [Buiten gebruik stellen](../remote-actions/devices-wipe.md#retire) uitvoert.

SCEP-certificaten *blijven gehandhaafd* op het apparaat (certificaten worden niet ingetrokken of verwijderd) wanneer:

- Een gebruiker de Intune-licentie verliest.
- Een beheerder de Intune-licentie intrekt.
- Een beheerder de gebruiker of groep uit Azure AD verwijdert.

### <a name="pkcs-certificates"></a>PKCS-certificaten

Een PKCS-certificaat wordt ingetrokken *en* verwijderd wanneer:

- Een eindgebruiker zich uitschrijft.
- Een beheerder de actie [Wissen](../remote-actions/devices-wipe.md#wipe) uitvoert.
- Een beheerder de actie [Buiten gebruik stellen](../remote-actions/devices-wipe.md#retire) uitvoert.

Een basiscertificaat wordt verwijderd wanneer:

- Een eindgebruiker zich uitschrijft.
- Een beheerder de actie [Wissen](../remote-actions/devices-wipe.md#wipe) uitvoert.
- Een beheerder de actie [Buiten gebruik stellen](../remote-actions/devices-wipe.md#retire) uitvoert.

PKCS-certificaten *blijven gehandhaafd* op het apparaat (certificaten worden niet ingetrokken of verwijderd) wanneer:

- Een gebruiker de Intune-licentie verliest.
- Een beheerder de Intune-licentie intrekt.
- Een beheerder de gebruiker of groep uit Azure AD verwijdert.
- Een beheerder wijzigingen aanbrengt in het PKCS-profiel of dit bijwerkt.
- Een certificaatprofiel wordt verwijderd uit de groepstoewijzing.


## <a name="ios-devices"></a>iOS-apparaten

### <a name="scep-certificates"></a>SCEP-certificaten

Een SCEP-certificaat wordt ingetrokken *en* verwijderd wanneer:

- Een eindgebruiker zich uitschrijft.
- Een beheerder de actie [Wissen](../remote-actions/devices-wipe.md#wipe) uitvoert.
- Een beheerder de actie [Buiten gebruik stellen](../remote-actions/devices-wipe.md#retire) uitvoert.
- Het apparaat wordt verwijderd uit de Azure AD-groep.
- Een certificaatprofiel wordt verwijderd uit de groepstoewijzing.

Een SCEP-certificaat wordt ingetrokken wanneer:

- Een beheerder wijzigingen aanbrengt in het SCEP-profiel of dit bijwerkt.

Een basiscertificaat wordt verwijderd wanneer:

- Een eindgebruiker zich uitschrijft.
- Een beheerder de actie [Wissen](../remote-actions/devices-wipe.md#wipe) uitvoert.
- Een beheerder de actie [Buiten gebruik stellen](../remote-actions/devices-wipe.md#retire) uitvoert.

SCEP-certificaten *blijven gehandhaafd* op het apparaat (certificaten worden niet ingetrokken of verwijderd) wanneer:

- Een gebruiker de Intune-licentie verliest.
- Een beheerder de Intune-licentie intrekt.
- Een beheerder de gebruiker of groep uit Azure AD verwijdert.

### <a name="pkcs-certificates"></a>PKCS-certificaten

Een PKCS-certificaat wordt ingetrokken *en* verwijderd wanneer:

- Een eindgebruiker zich uitschrijft.
- Een beheerder de actie [Wissen](../remote-actions/devices-wipe.md#wipe) uitvoert.
- Een beheerder de actie [Buiten gebruik stellen](../remote-actions/devices-wipe.md#retire) uitvoert.

Een PKCS-certificaat wordt verwijderd wanneer:

- Een certificaatprofiel wordt verwijderd uit de groepstoewijzing.

Een basiscertificaat wordt verwijderd wanneer:

- Een eindgebruiker zich uitschrijft.
- Een beheerder de actie [Wissen](../remote-actions/devices-wipe.md#wipe) uitvoert.
- Een beheerder de actie [Buiten gebruik stellen](../remote-actions/devices-wipe.md#retire) uitvoert.

PKCS-certificaten *blijven gehandhaafd* op het apparaat (certificaten worden niet ingetrokken of verwijderd) wanneer:

- Een gebruiker de Intune-licentie verliest.
- Een beheerder de Intune-licentie intrekt.
- Een beheerder de gebruiker of groep uit Azure AD verwijdert.
- Een beheerder wijzigingen aanbrengt in het PKCS-profiel of dit bijwerkt.

## <a name="android-knox-devices"></a>Android KNOX-apparaten

### <a name="scep-certificates"></a>SCEP-certificaten

Een SCEP-certificaat wordt ingetrokken *en* verwijderd wanneer:

- Een eindgebruiker zich uitschrijft.
- Een beheerder de actie [Wissen](../remote-actions/devices-wipe.md#wipe) uitvoert.

Een SCEP-certificaat wordt ingetrokken wanneer:

- Een beheerder de actie [Buiten gebruik stellen](../remote-actions/devices-wipe.md#retire) uitvoert.
- Het apparaat wordt verwijderd uit een Azure AD-groep.
- Een certificaatprofiel wordt verwijderd uit de groepstoewijzing.
- Een beheerder de gebruiker of groep uit Azure AD verwijdert.
- Een beheerder wijzigingen aanbrengt in het SCEP-profiel of dit bijwerkt.

Een basiscertificaat wordt verwijderd wanneer:

- Een eindgebruiker zich uitschrijft.
- Een beheerder de actie [Wissen](../remote-actions/devices-wipe.md#wipe) uitvoert.
- Een beheerder de actie [Buiten gebruik stellen](../remote-actions/devices-wipe.md#retire) uitvoert.

SCEP-certificaten *blijven gehandhaafd* op het apparaat (certificaten worden niet ingetrokken of verwijderd) wanneer:

- Een gebruiker de Intune-licentie verliest.
- Een beheerder de Intune-licentie intrekt.
- Een beheerder de gebruiker of groep uit Azure AD verwijdert.

### <a name="pkcs-certificates"></a>PKCS-certificaten

Een PKCS-certificaat wordt ingetrokken *en* verwijderd wanneer:

- Een eindgebruiker zich uitschrijft.
- Een beheerder de actie [Wissen](../remote-actions/devices-wipe.md#wipe) uitvoert.
- Een beheerder de actie [Buiten gebruik stellen](../remote-actions/devices-wipe.md#retire) uitvoert.

Een basiscertificaat wordt verwijderd wanneer:

- Een eindgebruiker zich uitschrijft.
- Een beheerder de actie [Wissen](../remote-actions/devices-wipe.md#wipe) uitvoert.
- Een beheerder de actie [Buiten gebruik stellen](../remote-actions/devices-wipe.md#retire) uitvoert.

PKCS-certificaten *blijven gehandhaafd* op het apparaat (certificaten worden niet ingetrokken of verwijderd) wanneer:
- Een gebruiker de Intune-licentie verliest.

- Een beheerder de Intune-licentie intrekt.
- Een beheerder de gebruiker of groep uit Azure AD verwijdert.
- Een beheerder wijzigingen aanbrengt in het PKCS-profiel of dit bijwerkt.
- Een certificaatprofiel wordt verwijderd uit de groepstoewijzing.


> [!NOTE]
> Android for Work-apparaten worden niet gevalideerd voor de bovenstaande scenario's.
> Op verouderde Android-apparaten (alle niet-Samsung-apparaten zonder werkprofiel) kunnen certificaten niet worden verwijderd.

## <a name="macos-certificates"></a>macOS-certificaten

### <a name="scep-certificates"></a>SCEP-certificaten

Een SCEP-certificaat wordt ingetrokken *en* verwijderd wanneer:

- Een eindgebruiker zich uitschrijft.
- Een beheerder de actie [Buiten gebruik stellen](../remote-actions/devices-wipe.md#retire) uitvoert.
- Het apparaat wordt verwijderd uit een Azure AD-groep.
- Een certificaatprofiel wordt verwijderd uit de groepstoewijzing.

Een SCEP-certificaat wordt ingetrokken wanneer:

- Een beheerder wijzigingen aanbrengt in het SCEP-profiel of dit bijwerkt.

SCEP-certificaten *blijven gehandhaafd* op het apparaat (certificaten worden niet ingetrokken of verwijderd) wanneer:

- Een gebruiker de Intune-licentie verliest.
- Een beheerder de Intune-licentie intrekt.
- Een beheerder de gebruiker of groep uit Azure AD verwijdert.

> [!NOTE]
> Het terugzetten van de fabrieksinstellingen op macOS-apparaten door middel van [wissen](../remote-actions/devices-wipe.md#wipe) wordt niet ondersteund.

### <a name="pkcs-certificates"></a>PKCS-certificaten

PKCS-certificaten worden niet ondersteund in macOS.

## <a name="next-steps"></a>Volgende stappen

[Certificaten gebruiken voor verificatie](certificates-configure.md)