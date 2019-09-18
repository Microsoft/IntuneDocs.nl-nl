---
title: Toegewezen Android Enterprise-apparaten of volledig beheerde apparaten inschrijven in Intune
titleSuffix: Microsoft Intune
description: Informatie over het inschrijven van toegewezen of volledig beheerde Android Enterprise-apparaten in Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 1/15/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: chmaguir
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 99ccc8c61aa781bdcb6ac79c76202253597b8ef6
ms.sourcegitcommit: 74911a263944f2dbd9b754415ccda6c68dae0759
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/17/2019
ms.locfileid: "71070997"
---
# <a name="enroll-your-android-enterprise-dedicated-devices-or-fully-managed-devices-preview"></a>Uw toegewezen of volledig beheerde Android Enterprise-apparaten inschrijven (preview-versie)

Nadat u uw [toegewezen Android Enterprise-apparaten](android-kiosk-enroll.md) of [volledig beheerde Android Enterprise-apparaten](android-fully-managed-enroll.md) in Intune hebt ingesteld, kunt u de apparaten inschrijven. De manier waarop u uw Android Enterprise-apparaten inschrijft, is afhankelijk van het besturingssysteem.

| Inschrijvingsmethode | Minimumversie van het Android-besturingssysteem voor toegewezen en volledig beheerde apparaten |
| ----- | ----- |
| Near Field Communication | 5.1 |
| Tokenvermelding | 6.0 |
| QR-code | 7.0 |
| Zero Touch  | 8.0\* |

\* Van deelnemende fabrikanten.

## <a name="enroll-by-using-near-field-communication-nfc"></a>Registreren met Near Field Communication

Apparaten die ondersteuning bieden voor NFC, kunnen worden ingericht door een speciaal opgemaakte NFC-tag te maken. U kunt uw eigen app of een hulpprogramma voor het maken van NFC-tags gebruiken. Zie [NFC-based Android Enterprise device enrollment with Microsoft Intune](https://blogs.technet.microsoft.com/cbernier/2018/10/15/nfc-based-android-enterprise-device-enrollment-with-microsoft-intune/) (Op NFC gebaseerde inschrijving van Android Enterprise-apparaten met Microsoft Intune) en [Google's Android Management API documentation](https://developers.google.com/android/management/provision-device#nfc_method) (Android Management API-documentatie van Google) voor meer informatie.

## <a name="enroll-by-using-a-token"></a>Registreren met een token

Op apparaten met Android 6 en hoger kunt u het token gebruiken om het apparaat te registreren. Bij Android 6.1 en latere versies kan ook gebruik worden gemaakt van de QR-code, in combinatie met de inschrijvingsmethode **afw#setup**.

1. Schakel uw gewiste apparaat in.
2. Selecteer uw taal in het scherm **Welkom**.
3. Maak verbinding met uw **Wi-Fi** en kies vervolgens **VOLGENDE**.
4. Accepteer de Google-voorwaarden en kies **VOLGENDE**.
5. Voer in plaats van een Gmail-account in het aanmeldscherm van Google **afw #setup** in en kies **VOLGENDE**.
6. Kies **INSTALLEREN** voor de app **Beleid voor Android-apparaat**.
7. Ga door met de installatie van dit beleid.  Op sommige apparaten moet u mogelijk aanvullende voorwaarden accepteren.
8. Sta in het scherm **Dit apparaat registreren** toe dat uw apparaat de QR-code mag scannen of stel in dat u het token handmatig invoert.
9. Volg de aanwijzingen op het scherm om de inschrijving te voltooien.

## <a name="enroll-by-using-a-qr-code"></a>Registreren met een QR-code

Op apparaten met Android 7 en hoger kunt u de QR-code scannen van het inschrijvingsprofiel om het apparaat in te schrijven.

> [!Note]
> Inzoomen op de browser kan ertoe leiden dat apparaten geen QR-code kunnen scannen. Dit probleem wordt opgelost door de zoomfactor van de browser te vergroten.

1. Tik meerdere keren op het eerste scherm dat u ziet nadat het apparaat is gewist om een QR te starten die op het Android-apparaat wordt gelezen.
2. Voor apparaten met Android 7 en 8 wordt u gevraagd om een QR-lezer te installeren. Op Android-apparaten 9 of hoger is al een QR-lezer geïnstalleerd.
3. Gebruik de QR-lezer om de QR-code van het inschrijvingsprofiel te scannen en volg de aanwijzingen op het scherm om het apparaat in te schrijven.

## <a name="enroll-by-using-google-zero-touch"></a>Registreren met Zero Touch van Google

Voor het gebruik van het Google Zero Touch-systeem moet het apparaat hiervoor ondersteuning bieden en kunnen worden gekoppeld aan een leverancier die deel uitmaakt van de service.  Zie [de programmawebsite van Zero Touch van Google](https://www.android.com/enterprise/management/zero-touch/) voor meer informatie.

1. Maak een nieuwe configuratie in de Zero Touch-console.
2. Kies **Microsoft Intune** in de vervolgkeuzelijst EMM DPC.
3. Kopieer en plak de volgende JSON in het veld DPC-extra's in de Google Zero Touch-console. Vervang de tekenreeks *YourEnrollmentToken* door het inschrijvingstoken dat u hebt gemaakt als onderdeel van het inschrijvingsprofiel. Zet het inschrijvingstoken tussen dubbele aanhalingstekens.

    ```json
    {
        "android.app.extra.PROVISIONING_DEVICE_ADMIN_COMPONENT_NAME": "com.google.android.apps.work.clouddpc/.receivers.CloudDeviceAdminReceiver",

        "android.app.extra.PROVISIONING_DEVICE_ADMIN_SIGNATURE_CHECKSUM": "I5YvS0O5hXY46mb01BlRjq4oJJGs2kuUcHvVkAPEXlg",

        "android.app.extra.PROVISIONING_DEVICE_ADMIN_PACKAGE_DOWNLOAD_LOCATION": "https://play.google.com/managed/downloadManagingApp?identifier=setup",

        "android.app.extra.PROVISIONING_ADMIN_EXTRAS_BUNDLE": {
            "com.google.android.apps.work.clouddpc.EXTRA_ENROLLMENT_TOKEN": "YourEnrollmentToken"
        }
    }
    ```

4. Kies **Toepassen**.


## <a name="next-steps"></a>Volgende stappen
- [Android-apps implementeren](apps-deploy.md)
- [Configuratiebeleid voor Android toevoegen](device-profiles.md)

