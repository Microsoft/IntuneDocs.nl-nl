---
title: Certificatenprofiel maken in Microsoft Intune - Azure | Microsoft Docs
description: Voor uw apparaten voegt u een certificaatprofiel toe, of maakt u een profiel, door de certificaatomgeving SCEP of PKCS te configureren, het openbare certificaat te exporteren, het profiel te maken in de Azure Portal en vervolgens SCEP of PKCS toe te wijzen aan de certificaatprofielen in Microsoft Intune in de Azure Portal
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 09/03/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 5eccfa11-52ab-49eb-afef-a185b4dccde1
ms.reviewer: lacranda
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4d9554893a8317b014007bd7089ed62f222975c8
ms.sourcegitcommit: 7269abaefb2857bc8b343896bb2138bdb01bf8dc
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/03/2019
ms.locfileid: "70214324"
---
# <a name="use-certificates-for-authentication-in-microsoft-intune"></a>Certificaten voor verificatie gebruiken in Microsoft Intune  

Gebruik certificaten in Intune om uw gebruikers te verifiëren voor toepassingen en bedrijfsresources via een VPN-, Wi-Fi- of e-mailprofiel. Wanneer u certificaten gebruikt om deze verbindingen te verifiëren, hoeven uw eindgebruikers geen gebruikersnamen en wachtwoorden in te voeren, waardoor ze naadloos toegang kunnen krijgen. Certificaten worden ook gebruikt voor het ondertekenen en versleutelen van e-mail met behulp van S/MIME.

Intune ondersteunt de volgende certificaattypen:  

- Simple Certificate Enrollment Protocol (SCEP)  
- PKCS #12 (of PFX)  
- Geïmporteerd PKCS-certificaat

Als u deze certificaten wilt implementeren, moet u certificaatprofielen maken en deze toewijzen aan apparaten.  

Elk afzonderlijk certificaatprofiel dat u maakt, ondersteunt één platform. Als u bijvoorbeeld PKCS-certificaten gebruikt, moet u een PKCS-certificaatprofiel voor Android en een afzonderlijk PKCS-certificaatprofiel voor iOS maken. Als u ook SCEP-certificaten voor deze twee platforms gebruikt, moet u een SCEP-certificaatprofiel voor Android en een ander SCEP-certificaatprofiel voor iOS maken.  

**Algemene overwegingen**:  
- Als u geen certificeringsinstantie (CA) voor ondernemingen hebt, moet u er een maken of er een van [een van onze ondersteunde partners](certificate-authority-add-scep-overview.md#third-party-certification-authority-partners) gebruiken.
- Als u SCEP-certificaatprofielen gebruikt met behulp van Microsoft Active Directory Certificate Services, moet u een NDES-server (Registratieservice voor netwerkapparaten) configureren.
- Als u SCEP met een van onze certificeringsinstantiepartners gebruikt, moet u [deze integreren met Intune](certificate-authority-add-scep-overview.md#set-up-third-party-ca-integration).
- Voor zowel SCEP- als PKCS-certificaatprofielen moet u de Microsoft Intune Certificate Connector downloaden, installeren en configureren. 
- Voor geïmporteerde PCKS-certificaten moet u de PFX-certificaatconnector voor Microsoft Intune downloaden, installeren en configureren.
- Voor geïmporteerde PKCS-certificaten moet u certificaten van uw certificeringsinstantie exporteren en deze importeren in Microsoft Intune. Zie [het PowerShell-project PFXImport](https://github.com/Microsoft/Intune-Resource-Access/tree/develop/src/PFXImportPowershell)
- Als u wilt dat een apparaat geïmporteerde SCEP-, PCKS- of PKCS-certificaatprofielen gebruikt, moet dat apparaat uw basiscertificeringsinstantie vertrouwen. U gebruikt een *vertrouwd certificaatprofiel* om uw vertrouwde basis-CA-certificaat te implementeren op apparaten.  

## <a name="supported-platforms-and-certificate-profiles"></a>Ondersteunde platforms en certificaatprofielen  
| Platform              | Vertrouwd certificaatprofiel | PKCS-certificaatprofiel | SCEP-certificaatprofiel | Geïmporteerd PKCS-certificaatprofiel  |
|--|--|--|--|---|
| Android-apparaatbeheerder | ![Ondersteund](./media/certificates-configure/green-check.png) | ![Ondersteund](./media/certificates-configure/green-check.png) | ![Ondersteund](./media/certificates-configure/green-check.png)|  ![Ondersteund](./media/certificates-configure/green-check.png) |
| Android Enterprise <br> - Eigenaar van het apparaat   | ![Ondersteund](./media/certificates-configure/green-check.png) |   |  |   |
| Android Enterprise <br> - Werkprofiel    | ![Ondersteund](./media/certificates-configure/green-check.png) | ![Ondersteund](./media/certificates-configure/green-check.png) | ![Ondersteund](./media/certificates-configure/green-check.png) | ![Ondersteund](./media/certificates-configure/green-check.png) |
| iOS                   | ![Ondersteund](./media/certificates-configure/green-check.png) | ![Ondersteund](./media/certificates-configure/green-check.png) | ![Ondersteund](./media/certificates-configure/green-check.png) | ![Ondersteund](./media/certificates-configure/green-check.png) |
| macOS                 | ![Ondersteund](./media/certificates-configure/green-check.png) |   |![Ondersteund](./media/certificates-configure/green-check.png)|![Ondersteund](./media/certificates-configure/green-check.png)|
| Windows Phone 8.1     |![Ondersteund](./media/certificates-configure/green-check.png)  |  | ![Ondersteund](./media/certificates-configure/green-check.png)| ![Ondersteund](./media/certificates-configure/green-check.png) |
| Windows 8.1 en hoger |![Ondersteund](./media/certificates-configure/green-check.png)  |  |![Ondersteund](./media/certificates-configure/green-check.png) |   |
| Windows 10 en hoger  | ![Ondersteund](./media/certificates-configure/green-check.png) | ![Ondersteund](./media/certificates-configure/green-check.png) | ![Ondersteund](./media/certificates-configure/green-check.png) | ![Ondersteund](./media/certificates-configure/green-check.png) |

## <a name="export-the-trusted-root-ca-certificate"></a>Het vertrouwde basis-CA-certificaat exporteren  
Als u geïmporteerde PKCS-, SCEP- en PKCS-certificaten wilt gebruiken, moeten apparaten uw basiscertificeringsinstantie vertrouwen. U kunt deze vertrouwensrelatie tot stand brengen door het certificaat van de vertrouwde basiscertificeringsinstantie (basis-CA), evenals tussenliggende certificaten of certificaten van verlenende certificeringsinstanties, te exporteren als een openbaar certificaat (.cer). U kunt deze certificaten ophalen bij de verlenende CA of vanaf elk apparaat dat uw verlenende CA vertrouwt.  

Raadpleeg de documentatie van uw certificeringsinstantie om het certificaat te exporteren. U moet het openbare certificaat exporteren als een CER-bestand.  Exporteer niet de persoonlijke sleutel (een PFX-bestand).  

U gebruikt dit CER-bestand wanneer u [vertrouwde certificaatprofielen](#create-trusted-certificate-profiles) maakt om dat certificaat op uw apparaten te implementeren.  

## <a name="create-trusted-certificate-profiles"></a>profielen voor vertrouwde certificaten maken  
U moet een vertrouwd certificaatprofiel maken voordat u een SCEP-, PKCS- of geïmporteerd PKCS-certificaatprofiel kunt maken. Zorg er bij het implementeren van een vertrouwd certificaatprofiel voor dat elk apparaat de geldigheid van uw certificeringsinstantie herkent. SCEP-certificaat profielen verwijzen rechtstreeks naar een vertrouwd certificaatprofiel. PKCS-certificaatprofielen verwijzen niet rechtstreeks naar het vertrouwde certificaatprofiel, maar wel naar de server die als host fungeert voor uw CA. Geïmporteerde PKCS-certificaatprofielen verwijzen niet rechtstreeks naar het vertrouwde certificaatprofiel, maar kunnen er wel gebruik van maken op het apparaat. Het implementeren van een vertrouwd certificaatprofiel op apparaten zorgt ervoor dat deze vertrouwensrelatie tot stand wordt gebracht. Wanneer een apparaat de basis-CA niet vertrouwt, mislukt het SCEP- of PKCS-certificaatprofielbeleid.  

Maak een afzonderlijk vertrouwd certificaatprofiel voor elk apparaatplatform dat u wilt ondersteunen, net zoals u dat voor SCEP-, PCKS- en geïmporteerde PKCS-certificaatprofielen gaat doen.  


### <a name="to-create-a-trusted-certificate-profile"></a>Een profiel voor een vertrouwd certificaat maken  

1. Meld u aan bij de [Intune-portal](https://aka.ms/intuneportal).  
2. Selecteer **Apparaatconfiguratie** > **Beheren** > **Profielen** > **Profiel maken**.  
3. Voer een **Naam en beschrijving** in voor het vertrouwde certificaatprofiel.  
4. Selecteer in de vervolgkeuzelijst **Platform** het apparaatplatform voor dit vertrouwde certificaat.  
5. Kies in de vervolgkeuzelijst **Profieltype** de optie **Vertrouwd certificaat**.  
6. Blader naar het CER-bestand met het vertrouwde basis-CA-certificaat dat u hebt geëxporteerd voor gebruik bij dit certificaatprofiel en selecteer vervolgens **OK**.  
7. Voor Windows 8.1- en Windows 10-apparaten selecteert u het **doelarchief** voor het vertrouwde certificaat vanuit:  
   - **Certificaatarchief van de computer – basis**
   - **Certificaatarchief van de computer – tijdelijk**
   - **Certificaatarchief van de gebruiker – tijdelijk**
8. Als u klaar bent, kiest u **OK**, gaat u terug naar het deelvenster **Profiel maken** en kiest u **Maken**.
Het profiel wordt weergegeven in de lijst met profielen in het weergavevenster *Apparaatconfiguratie – Profielen* met het profieltype **Vertrouwd certificaat**.  Zorg ervoor dat u dit profiel toewijst aan apparaten die gebruik gaan maken van SCEP- of PCKS-certificaten. Zie [Apparaatprofielen toewijzen](device-profile-assign.md) om dit profiel toe te wijzen aan groepen.

> [!NOTE]  
> Op Android-apparaten wordt mogelijk een bericht weergegeven dat een derde partij een vertrouwd certificaat heeft geïnstalleerd.  

## <a name="additional-resources"></a>Aanvullende bronnen  
- [Apparaatprofielen toewijzen](device-profile-assign.md)  
- [S/MIME gebruiken om e-mailberichten te ondertekenen en te versleutelen](certificates-s-mime-encryption-sign.md)  
- [Een externe certificeringsinstantie gebruiken](certificate-authority-add-scep-overview.md)  

## <a name="next-steps"></a>Volgende stappen  
Nadat u een vertrouwd certificaatprofiel hebt gemaakt en toegewezen, maakt u SCEP-, PKCS- of geïmporteerde PKCS-certificaatprofielen voor elk platform dat u wilt gebruiken. Raadpleeg de volgende artikelen om verder te gaan:  
- [Infrastructuur configureren om SCEP-certificaten te ondersteunen in Intune](certificates-scep-configure.md)  
- [PKCS-certificaten configureren en beheren met Intune](certficates-pfx-configure.md)  
- [Een geïmporteerd PKCS-certificaatprofiel maken](certficates-pfx-configure.md#create-a-pkcs-imported-certificate-profile)  

