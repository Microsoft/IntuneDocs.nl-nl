---
title: Intune-instellingen voor de iOS-app Classroom
titleSuffix: Microsoft Intune
description: Meer informatie over de Intune-instellingen die u kunt gebruiken voor het beheren van instellingen voor de app Classroom op iOS-apparaten.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 11/14/2019
ms.topic: archived
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 1381a5ce-c743-40e9-8a10-4c218085bb5f
ms.reviewer: derriw
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6814b4d98b8512ce95119b05cc299964e486ac64
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 12/05/2019
ms.locfileid: "74784218"
---
# <a name="how-to-configure-intune-settings-for-the-ios-classroom-app"></a>De Intune-instellingen voor de iOS-app Classroom configureren

> [!NOTE]
> InTune biedt momenteel geen ondersteuning voor het configureren van de app class. Dit artikel is alleen van toepassing voor gebruikers met een iOS-onderwijsprofiel in Intune.  

## <a name="introduction"></a>Inleiding
[Classroom](https://itunes.apple.com/app/id1085319084) is een app waarmee docenten het leren kunnen begeleiden en op apparaten van studenten in het leslokaal kunnen beheren. Met de app kunnen leraren bijvoorbeeld:

- Apps op apparaten van studenten openen
- Het iPad-scherm vergrendelen en ontgrendelen
- Het iPad-scherm van een student weergeven
- iPads van studenten laten navigeren naar een bladwijzer of een hoofdstuk in een boek
- Het iPad-scherm van een student weergeven op een Apple-TV

Als u Classroom wilt instellen op uw apparaat, moet u een profiel voor een Intune iOS-onderwijsapparaat maken.

## <a name="before-you-start"></a>Voordat u begint

Let op het volgende voordat u begint met het configureren van deze instellingen:

- De iPads van zowel docenten als studenten moeten zijn geregistreerd bij Intune.
- Zorg ervoor dat u de app [Apple Classroom](https://itunes.apple.com/us/app/classroom/id1085319084?mt=8) hebt geïnstalleerd op het apparaat van de docent. U kunt de app handmatig installeren of [App-beheer van Intune](../apps/app-management.md) gebruiken.
- U moet certificaten configureren om verbindingen tussen de apparaten van de docent en studenten te verifiëren (zie stap 2, een iOS-opleidingsprofiel maken en toewijzen in Intune).
- iPads van de docent en studenten moeten verbonden zijn met hetzelfde Wi-Fi-netwerk en Bluetooth moet ingeschakeld zijn.
- De app Classroom draait op iPads met supervisie onder iOS 9.3 of hoger.
- In deze release biedt Intune ondersteuning voor het beheer van een 1-op-1-scenario waarbij elke student een eigen iPad heeft.


## <a name="step-1---import-your-school-data-into-azure-active-directory"></a>Stap 1: uw schoolgegevens importeren in Azure Active Directory

Gebruik Schoolgegevens synchroniseren (SDS) van Microsoft om schoolgegevens uit een bestaand Studentinformatiesysteem (SIS) te importeren in Azure Active Directory (Azure AD).
SDS synchroniseert informatie uit uw SIS en slaat deze op in Azure AD. Azure AD is een Microsoft-beheersysteem waarmee u gebruikers en apparaten kunt organiseren. U kunt deze gegevens vervolgens gebruiken voor het beheren van uw studenten en klassen. [Meer informatie over het implementeren van SDS](https://support.office.com/article/Overview-of-School-Data-Sync-and-Classroom-f3d1147b-4ade-4905-8518-508e729f2e91).

### <a name="how-to-import-data-using-sds"></a>Gegevens importeren met SDS

U kunt op een van de volgende manieren gegevens importeren in SDS:

- [CSV-bestanden](https://support.office.com/article/Follow-these-steps-71d5fe4a-aa51-4f35-9b53-348898a390a1): bestanden met door komma's gescheiden waarden (.csv) handmatig exporteren en compileren
- [PowerSchool API](https://support.office.com/article/Follow-these-steps-851b5edc-558f-43a9-9122-b2d63458cb8f): dit is een SIS-provider die vereenvoudigde synchronisatie met Azure AD biedt
- [OneRoster](https://support.office.com/article/Follow-these-steps-f43cbb2a-b502-497d-a8b1-783dc05a57ab): een CSV-indeling die u kunt exporteren en converteren om te synchroniseren met Azure AD

### <a name="find-out-more"></a>Meer informatie

- [Meer informatie over het synchroniseren van de on-premises schoolgegevens naar Azure AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)
- [Meer informatie over Schoolgegevens synchroniseren van Microsoft](https://sds.microsoft.com/)
- [Meer informatie over licentieverlening in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal)

## <a name="step-2---create-and-assign-an-ios-education-profile-in-intune"></a>Stap 2: een iOS-opleidingsprofiel maken en toewijzen in Intune

### <a name="configure-general-settings"></a>Algemene instellingen configureren

1. Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
3. Kies in het deelvenster **Intune** de optie **Apparaatconfiguratie**.
2. Kies in het deelvenster **Apparaatconfiguratie** onder de sectie **Beheren** de optie **Profielen**.
5. Kies **Profiel maken** in het deelvenster Profielen.
6. Voer in het deelvenster **Profiel maken** een **Naam** en **Beschrijving** in voor het iOS-opleidingsprofiel.
7. Kies **iOS** in de vervolgkeuzelijst **Platform**.
8. Kies **Onderwijs** in de vervolgkeuzelijst **Profieltype**.
9. Kies **Instellingen** > **Configureren**.


In de volgende sectie maakt u certificaten om een vertrouwensrelatie te maken tussen de iPads van de docent en studenten. Certificaten worden gebruikt voor het naadloos en op de achtergrond verifiëren van verbindingen tussen apparaten zonder gebruikersnamen en wachtwoorden in te voeren.

>[!IMPORTANT]
>De docent- en studentencertificaten die u gebruikt, moeten zijn uitgegeven door verschillende certificeringsinstanties (CA's). U moet twee nieuwe onderliggende CA's maken die verbonden zijn met uw bestaande certificaatinfrastructuur: één voor docenten en één voor studenten.

iOS-onderwijsprofielen ondersteunen alleen PFX-certificaten. SCEP-certificaten worden niet ondersteund.

De gemaakte certificaten moeten ondersteuning bieden voor gebruikersverificatie en serververificatie.

### <a name="configure-teacher-certificates"></a>Docentcertificaten configureren

Kies **Docentcertificaten** in het deelvenster **Opleiding**.

#### <a name="configure-teacher-root-certificate"></a>Het basiscertificaat voor de docent configureren

Kies onder **Basiscertificaat voor docent** de knop Bladeren. Selecteer het basiscertificaat met een van de volgende opties:
- .cer-extensie (DER of Base64-gecodeerd) 
- .P7b-extensie (met of zonder volledig keten)

#### <a name="configure-teacher-pkcs12-certificate"></a>PKCS#12-certificaat voor docent configureren

Configureer onder **PKCS #12-certificaat voor docent** de volgende waarden:

- **Indeling van onderwerpnaam**: Intune voorziet algemene namen automatisch van het voorvoegsel **leider** voor docentcertificaten. Algemene namen voor studentcertificaten hebben het voorvoegsel **lid**.
- **Certificeringsinstantie**: een certificeringsinstantie (CA) voor ondernemingen die wordt uitgevoerd op een Enterprise-editie van Windows Server 2008 R2 of hoger. Een zelfstandige CA wordt niet ondersteund. 
- **Naam van certificeringsinstantie**: voer de naam van uw certificeringsinstantie in.
- **Certificaatsjabloonnaam**: voer de naam in van een certificaatsjabloon die is toegevoegd aan een verlenende CA. 
- **Drempelwaarde voor verlenging (%)** : geef het percentage van de levensduur van het certificaat op dat resteert voordat het apparaat verlenging van het certificaat aanvraagt.
- **Geldigheidsduur van certificaat**: geef de hoeveelheid resterende tijd op totdat het certificaat verloopt.
U kunt een waarde opgeven die lager is dan de geldigheidsperiode in het opgegeven certificaatsjabloon, maar niet hoger. Als de geldigheidsperiode van het certificaat in het certificaatsjabloon bijvoorbeeld twee jaar is, kunt u wel één jaar, maar niet vijf jaar opgeven. De waarde moet ook lager zijn dan de resterende geldigheidsperiode van het certificaat van de verlenende CA.

Wanneer u de certificaten hebt geconfigureerd, kiest u **OK**.

### <a name="configure-student-certificates"></a>Studentencertificaten configureren

1. Kies **Studentencertificaten** in het deelvenster **Opleiding**.
2. Kies in het deelvenster **Studentencertificaten** in de lijst **Type studentapparaatcertificaten** de waarde **1:1**.

#### <a name="configure-student-root-certificate"></a>Het basiscertificaat voor studenten configureren

Kies onder **Basiscertificaat voor student** de knop Bladeren. Selecteer het basiscertificaat met een van de volgende opties:
- .cer-extensie (DER of Base64-gecodeerd) 
- .P7b-extensie (met of zonder volledig keten)

#### <a name="configure-student-pkcs12-certificate"></a>Het PKCS#12-certificaat voor studenten configureren

Configureer onder **PKCS#12-certificaat voor student** de volgende waarden:

- **Indeling van onderwerpnaam**: Intune voorziet algemene namen automatisch van het voorvoegsel **leider** voor docentcertificaten. Algemene namen voor studentcertificaten hebben het voorvoegsel **lid**.
- **Certificeringsinstantie**: een certificeringsinstantie (CA) voor ondernemingen die wordt uitgevoerd op een Enterprise-editie van Windows Server 2008 R2 of hoger. Een zelfstandige CA wordt niet ondersteund. 
- **Naam van certificeringsinstantie**: voer de naam van uw certificeringsinstantie in.
- **Certificaatsjabloonnaam**: voer de naam in van een certificaatsjabloon die is toegevoegd aan een verlenende CA. 
- **Drempelwaarde voor verlenging (%)** : geef het percentage van de levensduur van het certificaat op dat resteert voordat het apparaat verlenging van het certificaat aanvraagt.
- **Geldigheidsduur van certificaat**: geef de hoeveelheid resterende tijd op totdat het certificaat verloopt.
U kunt een waarde opgeven die lager is dan de geldigheidsperiode in het opgegeven certificaatsjabloon, maar niet hoger. Als de geldigheidsperiode van het certificaat in het certificaatsjabloon bijvoorbeeld twee jaar is, kunt u wel één jaar, maar niet vijf jaar opgeven. De waarde moet ook lager zijn dan de resterende geldigheidsperiode van het certificaat van de verlenende CA.

Wanneer u de certificaten hebt geconfigureerd, kiest u **OK**.

## <a name="finish-up"></a>Voltooien

1. Kies OK in het deelvenster **Opleiding**.
2. Kies **Maken** in het deelvenster **Profiel maken**.

Het profiel wordt gemaakt en wordt weergegeven in het deelvenster met de profielenlijst.

Wijs het profiel toe aan studentapparaten in de Classroom-groepen die zijn gemaakt toen u uw schoolgegevens synchroniseerde met Azure AD (Zie [Apparaatprofielen toewijzen](../configuration/device-profile-assign.md)).

## <a name="next-steps"></a>Volgende stappen

Als een docent nu de Classroom-app gebruikt, hebben ze de volledige controle over de apparaten van studenten.

Zie [Help bij Classroom](https://help.apple.com/classroom/ipad/2.0/) op de website van Apple voor meer informatie over de app Classroom.

Als u gedeelde iPads wilt configureren voor studenten, raadpleegt u [Intune-onderwijsinstellingen configureren voor gedeelde iPads](education-settings-configure-ios-shared.md).
