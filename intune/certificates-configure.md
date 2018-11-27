---
title: Certificatenprofiel maken in Microsoft Intune - Azure | Microsoft Docs
description: Voor uw apparaten voegt u een certificaatprofiel toe, of maakt u een profiel, door de certificaatomgeving SCEP of PKCS te configureren, het openbare certificaat te exporteren, het profiel te maken in de Azure Portal en vervolgens SCEP of PKCS toe te wijzen aan de certificaatprofielen in Microsoft Intune in de Azure Portal
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 07/23/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 5eccfa11-52ab-49eb-afef-a185b4dccde1
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 1a70e8a5e9ad973f5d2c94a146a9f263f461d0ab
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/20/2018
ms.locfileid: "52180558"
---
# <a name="configure-a-certificate-profile-for-your-devices-in-microsoft-intune"></a>Een certificaatprofiel configureren voor uw apparaten in Microsoft Intune

U verleent gebruikers toegang tot bedrijfsbronnen via VPN, Wi-Fi of e-mailprofielen. Met behulp van certificaten kunt u deze verbindingen verifiëren. Wanneer u certificaten gebruikt, hoeven eindgebruikers geen gebruikersnamen en wachtwoorden op te geven om de verbinding te verifiëren.

Met Intune kunt u deze certificaten toewijzen aan apparaten die u beheert. Intune ondersteunt het toewijzen en beheren van de volgende typen certificaten:

- Simple Certificate Enrollment Protocol (SCEP)
- PKCS #12 (of PFX)

Elk van deze typen certificaten heeft eigen voorwaarden en infrastructuurvereisten.

## <a name="overview"></a>Overzicht

1. Zorg ervoor dat de juiste certificaatinfrastructuur is ingesteld. U kunt [SCEP-certificaten](certificates-scep-configure.md) en [PKCS-certificaten](certficates-pfx-configure.md) gebruiken.

2. Installeer op elk apparaat een basiscertificaat (of het tussenliggende CA-certificaat), zodat het apparaat de geldigheid van uw certificeringsinstantie (CA) erkent. Hiervoor maakt u een **vertrouwd certificaatprofiel** en wijst u het profiel toe. Wanneer u dit profiel toewijst, zullen de apparaten die door Intune worden beheerd, het basiscertificaat aanvragen en ontvangen. U moet voor elk platform een afzonderlijk profiel maken. Vertrouwde certificaatprofielen zijn beschikbaar voor de volgende platformen:

    - iOS 8.0 en hoger
    - macOS 10.11 of hoger
    - Android 4.0 en hoger
    - Android-werkprofiel
    - Windows 8.1 en hoger
    - Windows Phone 8.1 en hoger
    - Windows 10 en hoger

3. Maak certificaatprofielen zodat apparaten een certificaat aanvragen ten behoeve van verificatie van toegang per e-mail, VPN en Wi-F. U kunt een **PKCS**- of **SCEP**-certificaatprofiel maken en toewijzen voor apparaten op de volgende platformen:

   - iOS 8.0 en hoger
   - Android 4.0 en hoger
   - Android-werkprofiel
   - Windows 10 (Desktop en Mobile) en hoger

   U kunt alleen een **SCEP-certificaatprofiel** gebruiken voor apparaten met de volgende platformen:

   - macOS 10.9 of hoger
   - Windows Phone 8.1 en hoger

U moet voor elk apparaatplatform een afzonderlijk profiel maken. Wanneer u het profiel maakt, koppelt u dit aan het vertrouwde basiscertificaatprofiel dat u al hebt gemaakt.

### <a name="further-considerations"></a>Verdere overwegingen

- Als u geen bedrijfscertificeringsinstantie hebt, moet u er een maken
- Als u SCEP-profielen gebruikt, moet u een NDES-server (Network Device Enrollment Service) configureren
- Bovendien moet u de Microsoft Intune-certificaatconnector downloaden en configureren, ongeacht of u SCEP-profielen of PKCS-profielen wilt gebruiken


## <a name="step-1-configure-your-certificate-infrastructure"></a>Stap 1: uw certificaatinfrastructuur configureren

Zie een van de volgende onderwerpen voor meer informatie over het configureren van de infrastructuur voor elk type certificaatprofiel:

- [SCEP-certificaten configureren en beheren met Intune](certificates-scep-configure.md)
- [PKCS-certificaten configureren en beheren met Intune](certficates-pfx-configure.md)


## <a name="step-2-export-your-trusted-root-ca-certificate"></a>Stap 2: uw vertrouwde basis-CA-certificaat exporteren

Exporteer het certificaat van vertrouwde basiscertificeringsinstanties (CA) als een openbaar certificaat (.cer) van de verlenende CA of van een apparaat dat uw verlenende CA vertrouwt. Exporteer de persoonlijke sleutel (.pfx) niet.

U importeert dit certificaat wanneer u een vertrouwd certificaatprofiel instelt.

## <a name="step-3-create-trusted-certificate-profiles"></a>Stap 3: vertrouwde certificaatprofielen maken
Maak een profiel voor een vertrouwd certificaat voordat u een SCEP- of PKCS-certificaatprofiel kunt maken. Voor elk apparaatplatform is een vertrouwd certificaatprofiel en een SCEP- of PKCS-profiel vereist. De stappen voor het maken van vertrouwde certificaten zijn voor elk apparaatplatform ongeveer gelijk.

1. Meld u aan bij [Azure Portal](https://portal.azure.com).
2. Selecteer **Alle services**, filter op **Intune** en selecteer **Microsoft Intune**.
3. Selecteer **Apparaatconfiguratie** > **Beheren** > **Profielen** > **Profiel maken**.
4. Voer een **naam** en een **beschrijving** in voor het vertrouwde certificaatprofiel.
5. Selecteer in de vervolgkeuzelijst **Platform** het apparaatplatform voor dit vertrouwde certificaat. Uw opties zijn:

    - **Android**
    - **Android Enterprise**
    - **iOS**
    - **macOS**
    - **Windows Phone 8.1**
    - **Windows 8.1 en hoger**
    - **Windows 10 en hoger**

6. Kies in de vervolgkeuzelijst **Profieltype** de optie **Vertrouwd certificaat**.
7. Blader naar het certificaat dat u in taak 1 hebt opgeslagen en selecteer vervolgens **OK**.
8. Voor Windows 8.1- en Windows 10-apparaten selecteert u het **doelarchief** voor het vertrouwde certificaat vanuit:

    - **Certificaatarchief van de computer – basis**
    - **Certificaatarchief van de computer – tijdelijk**
    - **Certificaatarchief van de gebruiker – tijdelijk**

9. Als u klaar bent, kiest u **OK**, gaat u terug naar het deelvenster **Profiel maken** en kiest u **Maken**.

Het profiel wordt gemaakt en wordt weergegeven in de lijst. Zie [Apparaatprofielen toewijzen](device-profile-assign.md) om dit profiel toe te wijzen aan groepen.

Android-apparaten geven mogelijk een bericht weer dat een derde partij een vertrouwd certificaat heeft geïnstalleerd.

## <a name="step-4-create-scep-or-pkcs-certificate-profiles"></a>Stap 4: SCEP- of PKCS-certificaatprofielen maken

Zie een van de volgende onderwerpen voor meer informatie over het configureren en toewijzen van elk type certificaatprofiel:

- [SCEP-certificaten configureren en beheren met Intune](certificates-scep-configure.md)
- [PKCS-certificaten configureren en beheren met Intune](certficates-pfx-configure.md)

Nadat u een vertrouwd certificaatprofiel hebt gemaakt, maakt u SCEP- of PKCS-certificaatprofielen voor elk platform dat u wilt gebruiken. Wanneer u een SCEP-certificaatprofiel maakt, geeft u een profiel voor een vertrouwd certificaat op voor datzelfde platform. Door deze stap worden de twee certificaatprofielen gekoppeld. U moet nog wel elk profiel afzonderlijk toewijzen.

## <a name="next-steps"></a>Volgende stappen
[Apparaatprofielen toewijzen](device-profile-assign.md)  
[S/MIME gebruiken om e-mailberichten te ondertekenen en te versleutelen](certificates-s-mime-encryption-sign.md)  
[Externe certificeringsinstantie gebruiken](certificate-authority-add-scep-overview.md)
