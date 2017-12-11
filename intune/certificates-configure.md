---
title: Certificaten configureren met Intune
titlesuffix: Azure portal
description: Meer informatie over het gebruik van Intune om certificaten te maken en toe te wijzen die u helpen Wi-Fi-, VPN- en andere verbindingen te beveiligen.
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 11/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5eccfa11-52ab-49eb-afef-a185b4dccde1
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e9e511cef22fdfc8e2975bd14f7b969067317a44
ms.sourcegitcommit: 2ad0d88d3ef5b81563c6a54eaf52f09e126abeaf
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/29/2017
---
# <a name="how-to-configure-certificates-in-microsoft-intune"></a>Certificaten configureren in Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Wanneer u gebruikers toegang verleent tot bedrijfsresources via een VPN-, Wi-Fi- of e-mailprofiel, kunt u deze verbindingen verifiëren door certificaten te gebruiken. Wanneer u certificaten gebruikt, hoeft u geen gebruikersnamen en wachtwoorden op te geven om verbindingen te verifiëren.

Met Intune kunt u deze certificaten toewijzen aan apparaten die u beheert. Intune ondersteunt het toewijzen en beheren van de volgende typen certificaten:

- Simple Certificate Enrollment Protocol (SCEP)
- PKCS #12 (of PFX)

Elk van deze typen certificaten heeft eigen voorwaarden en infrastructuurvereisten.

## <a name="general-workflow"></a>Algemene werkstroom

1. Zorg ervoor dat er aan de vereisten voor de certificaatinfrastructuur is voldaan. U kunt [SCEP-certificaten](certificates-scep-configure.md) en [PKCS-certificaten](certficates-pfx-configure.md) gebruiken.
2. Installeer op elk apparaat een basiscertificaat (of het tussenliggende CA-certificaat), zodat het apparaat de geldigheid van uw certificeringsinstantie (CA) erkent. Hiervoor maakt u een **vertrouwd certificaatprofiel** en wijst u het profiel toe. Wanneer u dit profiel toewijst, zullen de apparaten die u met Intune beheert, het basiscertificaat aanvragen en ontvangen. U moet voor elk platform een afzonderlijk profiel maken. Vertrouwde certificaatprofielen zijn beschikbaar voor de volgende platformen:
    - iOS 8.0 en hoger
    - macOS 10.9 of hoger
    - Android 4.0 en hoger
    - Android for Work
    - Windows 8.1 en hoger
    - Windows Phone 8.1 en hoger
    - Windows 10 en hoger
3. Maak certificaatprofielen zodat apparaten een certificaat aanvragen ten behoeve van verificatie van toegang per e-mail, VPN en Wi-F.

   U kunt een **PKCS**- of **SCEP**-certificaatprofiel maken en toewijzen voor apparaten op de volgende platformen:

   - iOS 8.0 en hoger
   - Android 4.0 en hoger
   - Android for Work
   - Windows 10 (Desktop en Mobile) en hoger

   U kunt alleen een **SCEP-certificaatprofiel** gebruiken voor apparaten met de volgende platformen:

   - macOS 10.9 of hoger
   - Windows Phone 8.1 en hoger

U moet voor elk apparaatplatform een afzonderlijk profiel maken. Wanneer u het profiel maakt, koppelt u dit aan het vertrouwde basiscertificaatprofiel dat u al hebt gemaakt.

### <a name="further-considerations"></a>Verdere overwegingen

- Als u geen bedrijfscertificeringsinstantie hebt, moet u er een maken.
- U moet ook een NDES-server (Network Device Enrollment Service) configureren als u SCEP-profielen gebruikt.
- Bovendien moet u de Microsoft Intune-certificaatconnector downloaden en configureren, ongeacht of u SCEP-profielen of PKCS-profielen wilt gebruiken.


## <a name="step-1-configure-your-certificate-infrastructure"></a>Stap 1: uw certificaatinfrastructuur configureren

Zie een van de volgende onderwerpen voor meer informatie over het configureren van de infrastructuur voor elk type certificaatprofiel:

- [SCEP-certificaten configureren en beheren met Intune](certificates-scep-configure.md)
- [PKCS-certificaten configureren en beheren met Intune](certficates-pfx-configure.md)


## <a name="step-2-export-your-trusted-root-ca-certificate"></a>Stap 2: uw vertrouwde basis-CA-certificaat exporteren

Exporteer het certificaat van vertrouwde basiscertificeringsinstanties (CA) als een **.cer** -bestand van de verlenende CA of van een apparaat dat uw verlenende CA vertrouwt. Exporteer de persoonlijke sleutel niet.

U importeert dit certificaat wanneer u een vertrouwd certificaatprofiel instelt.

## <a name="step-3-create-trusted-certificate-profiles"></a>Stap 3: vertrouwde certificaatprofielen maken
U moet een profiel voor een vertrouwd certificaat maken voordat u een SCEP- of PKCS-certificaatprofiel kunt maken. U hebt een vertrouwd certificaatprofiel en een SCEP- of PKCS-profiel nodig voor elk apparaatplatform. De stroom voor het maken van vertrouwde certificaten is voor elk apparaatplatform ongeveer gelijk.

### <a name="to-create-a-trusted-certificate-profile"></a>Een profiel voor een vertrouwd certificaat maken

1. Meld u aan bij Azure Portal.
2. Kies **Meer services** > **Bewaking en beheer** > **Intune**.
3. Kies op de blade **Intune** de optie **Apparaatconfiguratie**.
2. Kies **Beheren** > **Profielen** op de blade **Apparaatconfiguratie**.
3. Kies **Profiel maken** op de blade Profielen.
4. Voer op de blade **Profiel maken** een **naam** en een **beschrijving** in voor het vertrouwde certificaatprofiel.
5. Selecteer in de vervolgkeuzelijst **Platform** het apparaatplatform voor dit vertrouwde certificaat. Op dit moment kunt u een van de volgende platformen kiezen voor certificaatinstellingen:
    - **Android**
    - **iOS**
    - **macOS**
    - **Windows Phone 8.1**
    - **Windows 8.1 en hoger**
    - **Windows 10 en hoger**
6. Kies in de vervolgkeuzelijst **Profieltype** de optie **Vertrouwd certificaat**.
7. Blader naar het certificaat dat u in taak 1 hebt opgeslagen, en klik vervolgens op **OK**.
8. Voor Windows 8.1- en Windows 10-apparaten selecteert u het **doelarchief** voor het vertrouwde certificaat vanuit:
    - **Certificaatarchief van de computer – basis**
    - **Certificaatarchief van de computer – tijdelijk**
    - **Certificaatarchief van de gebruiker – tijdelijk**
8. Als u klaar bent, kiest u **OK**, gaat u terug naar de blade **Profiel maken** en kiest u **Maken**.

Het profiel wordt gemaakt en wordt weergegeven op de blade met de profielenlijst.

Zie [How to assign device profiles](device-profile-assign.md) (Apparaatprofielen toewijzen) als u wilt doorgaan en dit profiel wilt toewijzen aan groepen.


> [!Note]
> Android-apparaten geven een melding weer dat een derde partij een vertrouwd certificaat heeft geïnstalleerd.

## <a name="step-4-create-scep-or-pkcs-certificate-profiles"></a>Stap 4: SCEP- of PKCS-certificaatprofielen maken

Zie een van de volgende onderwerpen voor meer informatie over het configureren en toewijzen van elk type certificaatprofiel:

- [SCEP-certificaten configureren en beheren met Intune](certificates-scep-configure.md)
- [PKCS-certificaten configureren en beheren met Intune](certficates-pfx-configure.md)

Nadat u een vertrouwd certificaatprofiel hebt gemaakt, maakt u SCEP- of PKCS-certificaatprofielen voor elk platform dat u wilt gebruiken. Wanneer u een SCEP-certificaatprofiel maakt, moet u een profiel voor een vertrouwd certificaat voor datzelfde platform opgeven. Hierdoor worden de twee certificaatprofielen gekoppeld. U moet nog wel elk profiel afzonderlijk toewijzen.


## <a name="next-steps"></a>Volgende stappen
Zie [Apparaatprofielen toewijzen](device-profile-assign.md) voor algemene informatie over het toewijzen van apparaatprofielen.
