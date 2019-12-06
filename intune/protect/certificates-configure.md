---
title: Certificatenprofiel maken in Microsoft Intune - Azure | Microsoft Docs
description: Meer informatie het gebruik van SCEP-certificaatprofielen (Simple Certificate Enrollment Protocol) of PKCS-certificaatprofielen (Public Key Cryptography Standards) en certificaatprofielen met Microsoft Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 11/22/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 5eccfa11-52ab-49eb-afef-a185b4dccde1
ms.reviewer: lacranda
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 5092fa37f0bf6bd1320fa06fa58ac5e36f55aa3c
ms.sourcegitcommit: a7b479c84b3af5b85528db676594bdb3a1ff6ec6
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/22/2019
ms.locfileid: "74410189"
---
# <a name="use-certificates-for-authentication-in-microsoft-intune"></a>Certificaten voor verificatie gebruiken in Microsoft Intune

Gebruik certificaten in Intune om uw gebruikers te verifiëren voor toepassingen en bedrijfsresources via een VPN-, Wi-Fi- of e-mailprofiel. Wanneer u certificaten gebruikt om deze verbindingen te verifiëren, hoeven uw eindgebruikers geen gebruikersnamen en wachtwoorden in te voeren, waardoor ze naadloos toegang kunnen krijgen. Certificaten worden ook gebruikt voor het ondertekenen en versleutelen van e-mail met behulp van S/MIME.

## <a name="intune-supported-certificates-and-usage"></a>Door Intune ondersteunde certificaten en ondersteund gebruik

| Type              | Verificatie | S/MIME-ondertekening | S/MIME-versleuteling  |
|--|--|--|--|
| Geïmporteerd PKCS-certificaat (Public Key Cryptography Standards) |  | ![Ondersteund](./media/certificates-configure/green-check.png) | ![Ondersteund](./media/certificates-configure/green-check.png)|
| PKCS #12 (of PFX)    | ![Ondersteund](./media/certificates-configure/green-check.png) | ![Ondersteund](./media/certificates-configure/green-check.png) |  |
| Simple Certificate Enrollment Protocol (SCEP)  | ![Ondersteund](./media/certificates-configure/green-check.png) | ![Ondersteund](./media/certificates-configure/green-check.png) | |

Als u deze certificaten wilt implementeren, moet u certificaatprofielen maken en deze toewijzen aan apparaten.

Elk afzonderlijk certificaatprofiel dat u maakt, ondersteunt één platform. Als u bijvoorbeeld PKCS-certificaten gebruikt, moet u een PKCS-certificaatprofiel voor Android en een afzonderlijk PKCS-certificaatprofiel voor iOS maken. Als u ook SCEP-certificaten voor deze twee platforms gebruikt, moet u een SCEP-certificaatprofiel voor Android en een ander SCEP-certificaatprofiel voor iOS maken.

### <a name="general-considerations-when-you-use-a-microsoft-certification-authority"></a>Algemene overwegingen als u een Microsoft-certificeringsinstantie gebruikt

Als u een Microsoft-certificeringsinstantie gebruikt (CA):

- Als u SCEP-certificaatprofielen wilt gebruiken, moet u [een NDES-server (Network Device Enrollment Service) instellen](certificates-scep-configure.md#set-up-ndes) voor gebruik met Intune.
- Als u de volgende certificaatprofieltypen wilt gebruiken, moet u de [Microsoft Intune Certificate Connector installeren](certificates-scep-configure.md#install-the-intune-certificate-connector):
  - SCEP-certificaatprofiel
  - PKCS-certificaatprofiel

- Geïmporteerde PKCS-certificaten gebruiken:
  - [Installeer de PFX-certificaatconnector voor Microsoft Intune](certificates-imported-pfx-configure.md#download-install-and-configure-the-pfx-certificate-connector-for-microsoft-intune).
  - Exporteer certificaten van de certificeringsinstantie en importeer deze vervolgens in Microsoft Intune. Zie [het PowerShell-project PFXImport](https://github.com/Microsoft/Intune-Resource-Access/tree/develop/src/PFXImportPowershell).

- Certificaten implementeren met behulp van de volgende mechanismen:
  - [Vertrouwde certificaatprofielen](certificates-configure.md#create-trusted-certificate-profiles) om van het vertrouwde basis-CA-certificaat vanuit uw basis-CA of tussenliggende (verlenende) CA naar apparaten te implementeren
  - SCEP-certificaatprofielen
  - PKCS-certificaatprofielen
  - Geïmporteerde PKCS-certificaatprofielen

### <a name="general-considerations-when-you-use-a-third-party-certification-authority"></a>Algemene overwegingen als u een externe certificeringsinstantie gebruikt

Als u een externe (niet-Microsoft) certificeringsinstantie (CA) gebruikt:

- SCEP-certificaatprofielen gebruiken:
  - Stel integratie met een externe certificeringsinstantie in van [een van onze ondersteunde partners](certificate-authority-add-scep-overview.md#third-party-certification-authority-partners). Dit instellen omvat het volgen van de instructies van de externe certificeringsinstantie waardoor de integratie van hun CA met Intune wordt voltooid.
  - [Maak een toepassing in Azure AD](certificate-authority-add-scep-overview.md#set-up-third-party-ca-integration) die de rechten voor Intune delegeert zodat de validatie van de SCEP-certificaatverificatievraag kan worden uitgevoerd.

- Voor geïmporteerde PKCS-certificaten moet u de [PFX-certificaatconnector voor Microsoft Intune installeren](certificates-imported-pfx-configure.md#download-install-and-configure-the-pfx-certificate-connector-for-microsoft-intune).

- Certificaten implementeren met behulp van de volgende mechanismen:
  - [Vertrouwde certificaatprofielen](certificates-configure.md#create-trusted-certificate-profiles) om van het vertrouwde basis-CA-certificaat vanuit uw basis-CA of tussenliggende (verlenende) CA naar apparaten te implementeren
  - SCEP-certificaatprofielen
  - PKCS-certificaatprofielen *(alleen ondersteund voor het [Digicert PKI-platform](certificates-digicert-configure.md))*
  - Geïmporteerde PKCS-certificaatprofielen

## <a name="supported-platforms-and-certificate-profiles"></a>Ondersteunde platforms en certificaatprofielen

| Platform              | Vertrouwd certificaatprofiel | PKCS-certificaatprofiel | SCEP-certificaatprofiel | Geïmporteerd PKCS-certificaatprofiel  |
|--|--|--|--|---|
| Android-apparaatbeheerder | ![Ondersteund](./media/certificates-configure/green-check.png) | ![Ondersteund](./media/certificates-configure/green-check.png) | ![Ondersteund](./media/certificates-configure/green-check.png)|  ![Ondersteund](./media/certificates-configure/green-check.png) |
| Android Enterprise <br> - Volledig beheerd (apparaateigenaar)   | ![Ondersteund](./media/certificates-configure/green-check.png) |   | ![Ondersteund](./media/certificates-configure/green-check.png) |   |
| Android Enterprise <br> - Toegewezen (apparaateigenaar)   | ![Ondersteund](./media/certificates-configure/green-check.png)  |   | ![Ondersteund](./media/certificates-configure/green-check.png)  |   |
| Android Enterprise <br> - Werkprofiel    | ![Ondersteund](./media/certificates-configure/green-check.png) | ![Ondersteund](./media/certificates-configure/green-check.png) | ![Ondersteund](./media/certificates-configure/green-check.png) | ![Ondersteund](./media/certificates-configure/green-check.png) |
| iOS                   | ![Ondersteund](./media/certificates-configure/green-check.png) | ![Ondersteund](./media/certificates-configure/green-check.png) | ![Ondersteund](./media/certificates-configure/green-check.png) | ![Ondersteund](./media/certificates-configure/green-check.png) |
| macOS                 | ![Ondersteund](./media/certificates-configure/green-check.png) |  ![Ondersteund](./media/certificates-configure/green-check.png) |![Ondersteund](./media/certificates-configure/green-check.png)|![Ondersteund](./media/certificates-configure/green-check.png)|
| Windows Phone 8.1     |![Ondersteund](./media/certificates-configure/green-check.png)  |  | ![Ondersteund](./media/certificates-configure/green-check.png)| ![Ondersteund](./media/certificates-configure/green-check.png) |
| Windows 8.1 en hoger |![Ondersteund](./media/certificates-configure/green-check.png)  |  |![Ondersteund](./media/certificates-configure/green-check.png) |   |
| Windows 10 en hoger  | ![Ondersteund](./media/certificates-configure/green-check.png) | ![Ondersteund](./media/certificates-configure/green-check.png) | ![Ondersteund](./media/certificates-configure/green-check.png) | ![Ondersteund](./media/certificates-configure/green-check.png) |

## <a name="export-the-trusted-root-ca-certificate"></a>Het vertrouwde basis-CA-certificaat exporteren

Als u geïmporteerde PKCS-, SCEP- en PKCS-certificaten wilt gebruiken, moeten apparaten uw basiscertificeringsinstantie vertrouwen. Als u vertrouwen tot stand wilt brengen, exporteert u het certificaat van de vertrouwde basis-CA, evenals tussenliggende certificaten of certificaten van verlenende certificeringsinstanties, als een openbaar certificaat (.cer). U kunt deze certificaten ophalen bij de verlenende CA of vanaf elk apparaat dat uw verlenende CA vertrouwt.

Raadpleeg de documentatie van uw certificeringsinstantie om het certificaat te exporteren. U moet het openbare certificaat exporteren als een CER-bestand.  Exporteer niet de persoonlijke sleutel (een PFX-bestand).

U gebruikt dit CER-bestand wanneer u [vertrouwde certificaatprofielen](#create-trusted-certificate-profiles) maakt om dat certificaat op uw apparaten te implementeren.

## <a name="create-trusted-certificate-profiles"></a>profielen voor vertrouwde certificaten maken

U moet een vertrouwd certificaatprofiel maken voordat u een SCEP-, PKCS- of geïmporteerd PKCS-certificaatprofiel kunt maken. Zorg er bij het implementeren van een vertrouwd certificaatprofiel voor dat elk apparaat de geldigheid van uw certificeringsinstantie herkent. SCEP-certificaat profielen verwijzen rechtstreeks naar een vertrouwd certificaatprofiel. PKCS-certificaatprofielen verwijzen niet rechtstreeks naar het vertrouwde certificaatprofiel, maar wel naar de server die als host fungeert voor uw CA. Geïmporteerde PKCS-certificaatprofielen verwijzen niet rechtstreeks naar het vertrouwde certificaatprofiel, maar kunnen er wel gebruik van maken op het apparaat. Het implementeren van een vertrouwd certificaatprofiel op apparaten zorgt ervoor dat deze vertrouwensrelatie tot stand wordt gebracht. Wanneer een apparaat de basis-CA niet vertrouwt, mislukt het SCEP- of PKCS-certificaatprofielbeleid.

Maak een afzonderlijk vertrouwd certificaatprofiel voor elk apparaatplatform dat u wilt ondersteunen, net zoals u dat voor SCEP-, PKCS- en geïmporteerde PKCS-certificaatprofielen gaat doen.

### <a name="to-create-a-trusted-certificate-profile"></a>Een profiel voor een vertrouwd certificaat maken

1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Selecteer **Apparaten** > **Configuratieprofielen** > **Profiel maken**.

   ![Ga naar Intune en maak een nieuw profiel voor een vertrouwd certificaat](./media/certficates-pfx-configure/certificates-pfx-configure-profile-new.png)

3. Voer de volgende eigenschappen in:

   - **Naam** voor het profiel
   - Een **beschrijving** instellen (optioneel)
   - **Platform** waarvoor het profiel moet worden geïmplementeerd
   - Stel **Profieltype** in op **Vertrouwd certificaat**

4. Selecteer **Instellingen** en blader naar het CER-bestand met het vertrouwde basis-CA-certificaat dat u hebt geëxporteerd voor gebruik bij dit certificaatprofiel en selecteer vervolgens **OK**.

5. Voor Windows 8.1- en Windows 10-apparaten selecteert u het **doelarchief** voor het vertrouwde certificaat vanuit:

   - **Certificaatarchief van de computer – basis**
   - **Certificaatarchief van de computer – tijdelijk**
   - **Certificaatarchief van de gebruiker – tijdelijk**

6. Als u klaar bent, kiest u **OK**, gaat u terug naar het deelvenster **Profiel maken** en kiest u **Maken**.

Het profiel wordt weergegeven in de lijst met profielen in het venster *Apparaten - Configuratieprofielen* met het profieltype **Vertrouwd certificaat**. Zorg ervoor dat u dit profiel toewijst aan apparaten die gebruik gaan maken van SCEP- of PKCS-certificaten. Zie [Apparaatprofielen toewijzen](../configuration/device-profile-assign.md) om dit profiel toe te wijzen aan groepen.

> [!NOTE]
> Op Android-apparaten wordt mogelijk een bericht weergegeven dat een derde partij een vertrouwd certificaat heeft geïnstalleerd.

## <a name="additional-resources"></a>Extra resources

- [Apparaatprofielen toewijzen](../configuration/device-profile-assign.md)  
- [S/MIME gebruiken om e-mailberichten te ondertekenen en te versleutelen](certificates-s-mime-encryption-sign.md)  
- [Een externe certificeringsinstantie gebruiken](certificate-authority-add-scep-overview.md)  

## <a name="next-steps"></a>Volgende stappen

Maak SCEP-, PKCS- of geïmporteerde PKCS-certificaatprofielen voor elk platform dat u wilt gebruiken. Raadpleeg de volgende artikelen om verder te gaan:

- [Infrastructuur configureren om SCEP-certificaten te ondersteunen in Intune](certificates-scep-configure.md)  
- [PKCS-certificaten configureren en beheren met Intune](certficates-pfx-configure.md)  
- [Een geïmporteerd PKCS-certificaatprofiel maken](certificates-imported-pfx-configure.md#create-a-pkcs-imported-certificate-profile)
