---
title: Inschrijvingsopties voor apparaten die worden beheerd door Microsoft Intune
titleSuffix: ''
description: Een lijst met inschrijvingsopties die beheerders voor apparaten kunnen instellen die worden beheerd door Microsoft Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 10/31/2017
ms.topic: get-started-article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: cf4ad6d4-423f-4826-ab8d-6eb7a7cfb559
ms.openlocfilehash: 67805253f432098736e0fb96776e8f7f0ff44cc3
ms.sourcegitcommit: 7e5c4d43cbd757342cb731bf691ef3891b0792b5
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/05/2018
ms.locfileid: "29748715"
---
# <a name="enrollment-options-for-devices-managed-by-intune"></a>Inschrijvingsopties voor apparaten die worden beheerd door Intune

Als Intune-beheerder kunt u de registratie van apparaten configureren om gebruikers te helpen en de mogelijkheden van Intune inschakelen.  Intune bevat de volgende registratieopties:

## <a name="terms-and-conditions"></a>Voorwaarden

U kunt vereisen dat gebruikers de algemene voorwaarden van uw bedrijf accepteren voordat ze de bedrijfsportal kunnen gebruiken om hun apparaten te registreren en toegang hebben tot resources als bedrijfsapps en e-mail. De configuratie van voorwaarden is optioneel. Meer informatie over[voorwaarden](terms-and-conditions-create.md).

## <a name="enrollment-restrictions"></a>Registratiebeperkingen

U kunt de registratie van apparaten op de volgende manieren beperken:
- Apparaatplatform
- Aantal apparaten per gebruiker
- Persoonlijke apparaten blokkeren

Meer informatie over [registratiebeperkingen](enrollment-restrictions-set.md).

## <a name="enable-apple-device-enrollment"></a>Apple-apparaatregistratie inschakelen

Een MDM-pushcertificaat is vereist voor iOS- en macOS-apparaatregistratie. Meer informatie over [MDM-pushcertificaten](apple-mdm-push-certificate-get.md).

## <a name="corporate-identifiers"></a>Zakelijke id’s

U kunt IMEI- (international mobile equipment identifier) en serienummers opgeven om apparaten in bedrijfseigendom te identificeren. Meer informatie over [zakelijke id's](corporate-identifiers-add.md).
## <a name="multi-factor-authentication"></a>Meervoudige verificatie

U kunt gebruikers verplichten om een extra verificatiemethode, zoals een telefoonnummer, pincode of biometrische gegevens, te gebruiken als ze een apparaat inschrijven. Meer informatie over [meervoudige verificatie](multi-factor-authentication.md).

## <a name="device-enrollment-manager"></a>Apparaatinschrijvingsmanager
U kunt gebruikers apparaatinschrijvingsmanagers (DEM – Device Enrollment Manager) maken.  DEM-gebruikers kunnen met één gebruikersaccount grote aantallen apparaten registreren. Met het account voor de apparaatinschrijvingsmanager (DEM-account) kunnen maximaal duizend apparaten worden geregistreerd. Meer informatie over [apparaatinschrijvingsmanagers](device-enrollment-manager-enroll.md).

## <a name="device-categories"></a>Apparaatcategorieën

Met apparaatcategorieën kunnen apparaten automatisch worden toegevoegd aan groepen op basis van categorieën die u definieert. Door apparaten in groepen in te delen kunt u deze apparaten eenvoudiger beheren. Meer informatie over [apparaatcategorieën](device-group-mapping.md).
