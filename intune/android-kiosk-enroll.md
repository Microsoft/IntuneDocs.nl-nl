---
title: Kioskapparaten voor Android Enterprise in Intune registreren
titlesuffix: Microsoft Intune
description: Meer informatie over het registreren van kioskapparaten voor Android Enterprise in Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 6/21/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 515853864236638bc2732f6539d087bd125e3c56
ms.sourcegitcommit: 4d314df59747800169090b3a870ffbacfab1f5ed
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/30/2018
ms.locfileid: "43313458"
---
# <a name="set-up-enrollment-of-android-enterprise-kiosk-devices"></a>Inschrijving van kioskapparaten voor Android Enterprise instellen

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Android ondersteunt kioskapparaten waarvoor de COSU-oplossing (Corporate-Owned, Single-Use) is ingesteld. Dergelijke apparaten worden voor een bepaald doel gebruikt, zoals digitale ondertekening, het afdrukken van tickets of voorraadbeheer. Beheerders vergrendelen het gebruik van een apparaat voor een beperkt aantal apps en webkoppelingen. Ook wordt voorkomen dat gebruikers andere apps kunnen toevoegen of andere acties op het apparaat kunnen uitvoeren.

Intune helpt u met de implementatie van apps en instellingen op Android-kioskapparaten. Zie [Android Enterprise-vereisten](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012) voor specifieke informatie over Android Enterprise.

Apparaten die u op deze manier beheert, zijn geregistreerd in Intune zonder een gebruikersaccount en zijn niet gekoppeld aan een eindgebruiker. Ze zijn niet bedoeld voor apps voor persoonlijk gebruik of voor apps met een sterke vereiste voor gebruikersspecifieke accountgegevens, zoals Outlook of Gmail.

## <a name="device-requirements"></a>Vereisten voor apparaten

Apparaten moeten voldoen aan de volgende vereisten om te worden beheerd als een kioskapparaat voor Android Enterprise:

- Android-besturingssysteemversie 5.1 en hoger.
- Op de apparaten moet een verdeling van Android worden uitgevoerd die connectiviteit met GMS (Google Mobile Services) heeft. Op de apparaten moet GMS beschikbaar zijn en de apparaten moeten in staat zijn om verbinding te maken met GMS.

## <a name="set-up-android-kiosk-management"></a>Android-kioskbeheer instellen

Volg deze stappen om Android-kioskbeheer in te stellen:

1. U moet de [MDM-instantie instellen op **Microsoft Intune**](mdm-authority-set.md) als voorbereiding op het beheer van mobiele apparaten. U stelt de instantie slechts één keer in, wanneer u Intune voor het eerst instelt voor het beheer van mobiele apparaten.
2. [Verbind uw Intune-tenantaccount met uw Android Enterprise-account](connect-intune-android-enterprise.md).
3. [Maak een inschrijvingsprofielprofiel](#create-an-enrollment-profile).
4. [Maak een apparaatgroep](#create-a-device-group).
5. [Schrijf de kioskapparaten in](#enroll-the-kiosk-devices).

### <a name="create-an-enrollment-profile"></a>Inschrijvingsprofielen maken

U moet een inschrijvingsprofiel maken, zodat u uw kioskapparaten kunt registreren. Bij het maken van het profiel ontvangt u een inschrijvingstoken (willekeurige tekenreeks) en een QR-code. Afhankelijk van het Android-besturingssysteem en de versie van het apparaat kunt u het token of de QR-code gebruiken om [het kioskapparaat te registreren](#enroll-the-kiosk-devices).

1. Ga naar de [Intune-portal](https://portal.azure.com) en kies **Apparaatinschrijving** > **Android-inschrijving** > **Kiosk- en taakapparaatinschrijvingen**.
2. Kies **Maken** en vul de vereiste velden in.
    - **Naam**: typ een naam die u gebruikt wanneer u het profiel toewijst aan de dynamische apparaatgroep.
    - **Vervaldatum van token**: de datum waarop het token verloopt. Google dwingt een maximum van 90 dagen af.
3. Kies **Maken** om het profiel op te slaan.

### <a name="create-a-device-group"></a>Een apparaatgroep maken

U kunt apps en beleidsregels zenden naar toegewezen of dynamische apparaatgroepen. U kunt dynamische AAD-apparaatgroepen configureren om apparaten die zijn geregistreerd met een bepaald inschrijvingsprofiel automatisch te vullen door deze stappen te volgen:

1. Ga naar de [Intune-portal](https://portal.azure.com) en kies **Groepen** > **Alle groepen** > **Nieuwe groep**.
2. Vul in de blade **Groep** de vereiste velden als volgt in:
    - **Groepstype**: Beveiliging
    - **Groepsnaam**: typ een intuïtieve naam (bijvoorbeeld Factory 1-apparaten)
    - **Type lidmaatschap**: Dynamisch apparaat
3. Kies **Dynamische query toevoegen**.
4. Vul in de blade **Dynamisch-lidmaatschapregels** de velden als volgt in:
    - **Regel voor dynamisch lidmaatschap toevoegen**: Eenvoudige regel
    - **Locatie voor het toevoegen van apparaten**: enrollmentProfileName
    - Kies in het middelste vak **Overeenkomst**.
    - Voer in het laatste veld de naam in van het inschrijvingsprofiel dat u eerder hebt gemaakt.
5. Kies **Query toevoegen** > **Maken**.

### <a name="replace-or-remove-tokens"></a>Tokens vervangen of verwijderen

U kunt tokens en QR-codes vervangen of verwijderen.

- **Token vervangen**: met Token vervangen kunt u een nieuw token of nieuwe QR-code genereren wanneer voor een van beide de vervaldatum nadert.
- **Token intrekken**: u kunt het token of de QR-code direct laten verlopen. Vanaf dat moment is het token of de QR-code niet meer bruikbaar. U kunt deze optie bijvoorbeeld gebruiken als u:
    - het token of de QR-code per ongeluk hebt gedeeld met een onbevoegde partij
    - alle inschrijvingen hebt voltooid en het token of de QR-code niet meer nodig hebt

Het vervangen of intrekken van een token of QR-code heeft geen effect op apparaten die al zijn geregistreerd.

1. Ga naar de [Intune-portal](https://portal.azure.com) en kies **Apparaatinschrijving** > **Android-inschrijving** > **Kiosk- en taakapparaatinschrijvingen**.
2. Kies het profiel waarmee u wilt werken.
3. Kies **Token**.
4. Kies **Token vervangen** als u het token wilt vervangen.
5. Kies **Token intrekken** als u het token wilt intrekken.

## <a name="enroll-the-kiosk-devices"></a>De kioskapparaten registreren

Nadat u het inschrijvingsprofiel en de dynamische apparaatgroep hebt gemaakt, kunt u uw kioskapparaten registreren. De manier waarop u uw Android-apparaten registreert, is afhankelijk van het besturingssysteem.

| Inschrijvingsmethode | Minimale ondersteunde versie van het Android-besturingssysteem |
| ----- | ----- |
| Near Field Communication | 5.1 |
| Tokenvermelding | 6.0 |
| QR-code | 7.0 |
| Zero Touch | 8.0, van de deelnemende fabrikanten |

### <a name="enroll-by-using-near-field-communication-nfc"></a>Registreren met Near Field Communication

Apparaten met Android 5.1 en hoger die ondersteuning bieden voor NFC, kunnen worden ingericht door een speciaal opgemaakte NFC-tag te maken. U kunt uw eigen app of een hulpprogramma voor het maken van NFC-tags gebruiken. Zie de [Google's Android Management API documentation](https://developers.google.com/android/management/provision-device#nfc_method) (Android Management API-documentatie van Google) voor meer informatie.

### <a name="enroll-by-using-a-token"></a>Registreren met een token

Op apparaten met Android 6 en hoger kunt u het token gebruiken om het apparaat te registreren. Android 6.1 en latere versies kunnen ook gebruikmaken van de QR-code scannen bij het gebruik van de **aft#setup**-inschrijvingsmethode.

1. Schakel uw gewiste apparaat in.
2. Selecteer uw taal in het scherm **Welkom**.
3. Maak verbinding met uw **Wi-Fi** en kies vervolgens **VOLGENDE**.
4. Accepteer de Google-voorwaarden en kies **VOLGENDE**.
5. Voer in plaats van een Gmail-account in het aanmeldscherm van Google **afw #setup** in en kies **VOLGENDE**.
6. Kies **INSTALLEREN** voor de app **Beleid voor Android-apparaat**.
7. Ga door met de installatie van dit beleid.  Op sommige apparaten moet u mogelijk aanvullende voorwaarden accepteren. 
8. Sta in het scherm **Dit apparaat registreren** toe dat uw apparaat de QR-code mag scannen of stel in dat u het token handmatig invoert.
9. Volg de aanwijzingen op het scherm om de inschrijving te voltooien. 

### <a name="enroll-by-using-a-qr-code"></a>Registreren met een QR-code

Op apparaten met Android 7 en hoger kunt u de QR-code scannen van het inschrijvingsprofiel om het apparaat in te schrijven.

> [!Note]
> Inzoomen op de browser kan ertoe leiden dat apparaten geen QR-code kunnen scannen. Dit probleem wordt opgelost door de zoomfactor van de browser te vergroten.

1. Tik meerdere keren op het eerste scherm dat u ziet nadat het apparaat is gewist om een QR te starten die op het Android-apparaat wordt gelezen.
2. Voor apparaten met Android 7 en 8 wordt u gevraagd om een QR-lezer te installeren. Op Android-apparaten 9 of hoger is al een QR-lezer geïnstalleerd.
3. Gebruik de QR-lezer om de QR-code van het inschrijvingsprofiel te scannen en volg de aanwijzingen op het scherm om het apparaat in te schrijven.

### <a name="enroll-by-using-google-zero-touch"></a>Registreren met Zero Touch van Google

Voor het gebruik van het Google Zero Touch-systeem moet het apparaat hiervoor ondersteuning bieden en kunnen worden gekoppeld aan een leverancier die deel uitmaakt van de service.  Zie [de programmawebsite van Zero Touch van Google](https://www.android.com/enterprise/management/zero-touch/) voor meer informatie. 


1. Maak een nieuwe configuratie in de Zero Touch-console.
2. Kies **Microsoft Intune** in de vervolgkeuzelijst EMM DPC.
3. Kopieer en plak de volgende JSON in het veld DPC-extra's in de Google Zero Touch-console. Vervang de tekenreeks *YourEnrollmentToken* door het inschrijvingstoken dat u hebt gemaakt als onderdeel van het inschrijvingsprofiel. Zet het inschrijvingstoken tussen dubbele aanhalingstekens.

```
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

## <a name="managing-apps-on-android-kiosk-devices"></a>Apps beheren op Android-kioskapparaten

U kunt op Android-kioskapparaten alleen apps installeren waarvoor het toewijzingstype [is ingesteld op Vereist](apps-deploy.md#to-assign-an-app). De apps worden geïnstalleerd vanuit de beheerde Google Play Store op dezelfde manier als op apparaten met een Android-werkprofiel.

Apps worden automatisch bijgewerkt op beheerde apparaten zodra de app-ontwikkelaar een update op Google Play publiceert.

Als u een app van Android-kioskapparaten wilt verwijderen, kunt u het volgende doen:
-   Verwijder de vereiste app-implementatie.
-   Maak een verwijderimplementatie voor de app.


## <a name="next-steps"></a>Volgende stappen
- [Android-kiosk-apps implementeren](apps-deploy.md)
- [Configuratiebeleid voor Android-kiosk toevoegen](device-profiles.md)
