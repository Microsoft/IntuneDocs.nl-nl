---
title: SCEP- of PKCS-certificaten verwijderen in Microsoft Intune - Azure | Microsoft Docs
titleSuffix: ''
description: Beheerders kunnen certificaten uit Microsoft Intune verwijderen door apparaten te wissen of buiten gebruik te stellen. Er zijn enkele situaties waarin de certificaten automatisch worden verwijderd, zoals bij het uitschrijven van een apparaat of het verwijderen van een nalevingsbeleid. Er zijn enkele situaties waarin certificaten automatisch op het apparaat blijven gehandhaafd, wanneer bijvoorbeeld de Intune-licentie verloren gaat of wordt verwijderd. Bekijk de verschillende manieren voor Android-, Android Enterprise-, iOS-, macOS- en Windows-apparaten.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/23/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 06b568ee7cc2dc55a8d44cf04b96078b47d8c4b3
ms.sourcegitcommit: 77a1047f5d93c1924e5c9ea243454532881be031
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/28/2018
ms.locfileid: "52579163"
---
# <a name="remove-scep-and-pkcs-certificates-in-microsoft-intune"></a>SCEP- en PKCS-certificaten verwijderen in Microsoft Intune

U kunt in Microsoft Intune SCEP- en PKCS-certificaten toevoegen aan apparaten. Deze certificaten kunnen ook worden verwijderd wanneer u het apparaat [wist](devices-wipe.md#wipe) of [buiten gebruik stelt](devices-wipe.md#retire). Er zijn enkele andere situaties waarin certificaten automatisch worden verwijderd, en een aantal situaties waarin certificaten op het apparaat gehandhaafd blijven.

In dit artikel worden enkele veelvoorkomende situaties en de gevolgen voor PKCS- en SCEP-certificaten beschreven.

> [!NOTE]
> Als u certificaten wilt verwijderen en intrekken voor een gebruiker die uit Active Directory (AD) of Azure AD wordt verwijderd, moet u de stappen in de goede volgorde uitvoeren:
>
>    1. Het apparaat van de gebruiker wissen of buiten gebruik stellen
>    2. De gebruiker uit AD of Azure AD verwijderen

## <a name="windows-devices"></a>Windows-apparaten

#### <a name="scep-certificates"></a>SCEP-certificaten

- Een SCEP-certificaat wordt ingetrokken *en* verwijderd wanneer:

  - Een eindgebruiker wordt uitgeschreven
  - De beheerder een apparaat [wist](devices-wipe.md#wipe)
  - De beheerder een apparaat [buiten gebruik stelt](devices-wipe.md#retire)
  - Het apparaat wordt verwijderd uit de AD-groep (Azure Active Directory)
  - Certificaatprofiel wordt verwijderd uit de groepstoewijzing

- Een SCEP-certificaat wordt ingetrokken wanneer:
  - De beheerder wijzigingen aanbrengt in het SCEP-profiel of dit bijwerkt

- Een basiscertificaat wordt verwijderd wanneer:
  - Een eindgebruiker wordt uitgeschreven
  - De beheerder een apparaat [wist](devices-wipe.md#wipe)
  - De beheerder een apparaat [buiten gebruik stelt](devices-wipe.md#retire)

- SCEP-certificaten **blijven gehandhaafd** op het apparaat (certificaten worden niet ingetrokken of verwijderd) wanneer:
  - Een eindgebruiker de Intune-licentie verliest
  - De beheerder de Intune-licentie intrekt
  - De beheerder de gebruiker of groep uit Azure AD verwijdert

#### <a name="pkcs-certificates"></a>PKCS-certificaten

- Een PKCS-certificaat wordt ingetrokken *en* verwijderd wanneer:

  - Een eindgebruiker wordt uitgeschreven
  - De beheerder een apparaat [wist](devices-wipe.md#wipe)
  - De beheerder een apparaat [buiten gebruik stelt](devices-wipe.md#retire)

- Een basiscertificaat wordt verwijderd wanneer:
  - Een eindgebruiker wordt uitgeschreven
  - De beheerder een apparaat [wist](devices-wipe.md#wipe)
  - De beheerder een apparaat [buiten gebruik stelt](devices-wipe.md#retire)

- PKCS-certificaten **blijven gehandhaafd** op het apparaat (certificaten worden niet ingetrokken of verwijderd) wanneer:
  - Een eindgebruiker de Intune-licentie verliest
  - De beheerder de Intune-licentie intrekt
  - De beheerder de gebruiker of groep uit Azure AD verwijdert
  - De beheerder wijzigingen aanbrengt in het PKCS-profiel of dit bijwerkt
  - Certificaatprofiel wordt verwijderd uit de groepstoewijzing


## <a name="ios-devices"></a>iOS-apparaten

#### <a name="scep-certificates"></a>SCEP-certificaten

- Een SCEP-certificaat wordt ingetrokken *en* verwijderd wanneer:

  - Een eindgebruiker wordt uitgeschreven
  - De beheerder een apparaat [wist](devices-wipe.md#wipe)
  - De beheerder een apparaat [buiten gebruik stelt](devices-wipe.md#retire)
  - Het apparaat wordt verwijderd uit de AD-groep (Azure Active Directory)
  - Certificaatprofiel wordt verwijderd uit de groepstoewijzing

- Een SCEP-certificaat wordt ingetrokken wanneer:
  - De beheerder wijzigingen aanbrengt in het SCEP-profiel of dit bijwerkt

- Een basiscertificaat wordt verwijderd wanneer:
  - Een eindgebruiker wordt uitgeschreven
  - De beheerder een apparaat [wist](devices-wipe.md#wipe)
  - De beheerder een apparaat [buiten gebruik stelt](devices-wipe.md#retire)

- SCEP-certificaten **blijven gehandhaafd** op het apparaat (certificaten worden niet ingetrokken of verwijderd) wanneer:
  - Een eindgebruiker de Intune-licentie verliest
  - De beheerder de Intune-licentie intrekt
  - De beheerder de gebruiker of groep uit Azure AD verwijdert

#### <a name="pkcs-certificates"></a>PKCS-certificaten

- Een PKCS-certificaat wordt ingetrokken *en* verwijderd wanneer:

  - Een eindgebruiker wordt uitgeschreven
  - De beheerder een apparaat [wist](devices-wipe.md#wipe)
  - De beheerder een apparaat [buiten gebruik stelt](devices-wipe.md#retire)

- Een PKCS-certificaat wordt verwijderd wanneer:
  - Certificaatprofiel wordt verwijderd uit de groepstoewijzing
  
- Een basiscertificaat wordt verwijderd wanneer:
  - Een eindgebruiker wordt uitgeschreven
  - De beheerder een apparaat [wist](devices-wipe.md#wipe)
  - De beheerder een apparaat [buiten gebruik stelt](devices-wipe.md#retire)

- PKCS-certificaten **blijven gehandhaafd** op het apparaat (certificaten worden niet ingetrokken of verwijderd) wanneer:
  - Een eindgebruiker de Intune-licentie verliest
  - De beheerder de Intune-licentie intrekt
  - De beheerder de gebruiker of groep uit Azure AD verwijdert
  - De beheerder wijzigingen aanbrengt in het PKCS-profiel of dit bijwerkt

## <a name="android-knox-devices"></a>Android KNOX-apparaten

#### <a name="scep-certificates"></a>SCEP-certificaten

- Een SCEP-certificaat wordt ingetrokken *en* verwijderd wanneer:
  - Een eindgebruiker wordt uitgeschreven
  - De beheerder een apparaat [wist](devices-wipe.md#wipe)

- Een SCEP-certificaat wordt ingetrokken wanneer:
  - De beheerder een apparaat [buiten gebruik stelt](devices-wipe.md#retire)
  - Het apparaat wordt verwijderd uit de AD-groep (Azure Active Directory)
  - Certificaatprofiel wordt verwijderd uit de groepstoewijzing
  - De beheerder de gebruiker of groep uit Azure Active Directory (AD) verwijdert
  - De beheerder wijzigingen aanbrengt in het SCEP-profiel of dit bijwerkt

- Een basiscertificaat wordt verwijderd wanneer:
  - Een eindgebruiker wordt uitgeschreven
  - De beheerder een apparaat [wist](devices-wipe.md#wipe)
  - De beheerder een apparaat [buiten gebruik stelt](devices-wipe.md#retire)

- SCEP-certificaten **blijven gehandhaafd** op het apparaat (certificaten worden niet ingetrokken of verwijderd) wanneer:
  - Een eindgebruiker de Intune-licentie verliest
  - De beheerder de Intune-licentie intrekt
  - De beheerder de gebruiker of groep uit Azure AD verwijdert

#### <a name="pkcs-certificates"></a>PKCS-certificaten

- Een PKCS-certificaat wordt ingetrokken *en* verwijderd wanneer:

  - Een eindgebruiker wordt uitgeschreven
  - De beheerder een apparaat [wist](devices-wipe.md#wipe)
  - De beheerder een apparaat [buiten gebruik stelt](devices-wipe.md#retire)

- Een basiscertificaat wordt verwijderd wanneer:
  - Een eindgebruiker wordt uitgeschreven
  - De beheerder een apparaat [wist](devices-wipe.md#wipe)
  - De beheerder een apparaat [buiten gebruik stelt](devices-wipe.md#retire)

- PKCS-certificaten **blijven gehandhaafd** op het apparaat (certificaten worden niet ingetrokken of verwijderd) wanneer:
  - Een eindgebruiker de Intune-licentie verliest
  - De beheerder de Intune-licentie intrekt
  - De beheerder de gebruiker of groep uit Azure AD verwijdert
  - De beheerder wijzigingen aanbrengt in het PKCS-profiel of dit bijwerkt
  - Certificaatprofiel wordt verwijderd uit de groepstoewijzing
  
  
> [!NOTE]
> Android for work-apparaten zijn niet gevalideerd voor de bovenstaande scenario's. Verouderde Android-apparaten (alle niet-Samsung-apparaten zonder werkprofiel) zijn niet ingeschakeld voor het verwijderen van certificaten. 

## <a name="macos-certificates"></a>macOS-certificaten

#### <a name="scep-certificates"></a>SCEP-certificaten

- Een SCEP-certificaat wordt ingetrokken *en* verwijderd wanneer:
  - Een eindgebruiker wordt uitgeschreven
  - De beheerder een apparaat [buiten gebruik stelt](devices-wipe.md#retire)
  - Het apparaat wordt verwijderd uit de AD-groep (Azure Active Directory)
  - Certificaatprofiel wordt verwijderd uit de groepstoewijzing

- Een SCEP-certificaat wordt ingetrokken wanneer:
  - De beheerder wijzigingen aanbrengt in het SCEP-profiel of dit bijwerkt

- SCEP-certificaten **blijven gehandhaafd** op het apparaat (certificaten worden niet ingetrokken of verwijderd) wanneer:
  - Een eindgebruiker de Intune-licentie verliest
  - De beheerder de Intune-licentie intrekt
  - De beheerder de gebruiker of groep uit Azure AD verwijdert

> [!NOTE]
> Het terugzetten van de fabrieksinstellingen op macOS-apparaten door middel van [wissen](devices-wipe.md#wipe) wordt niet ondersteund.

#### <a name="pkcs-certificates"></a>PKCS-certificaten

PKCS-certificaten worden niet ondersteund op macOS.

