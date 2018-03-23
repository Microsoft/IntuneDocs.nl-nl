---
title: Intune-instellingen voor gedeelde apparaten voor de iOS-app Classroom
titleSuffix: Microsoft Intune
description: Meer informatie over de Intune-instellingen die u kunt gebruiken voor het beheren van instellingen voor de app Classroom op iOS-apparaten.
keywords: ''
author: barlanmsft
ms.author: barlan
manager: dougeby
ms.date: 02/23/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 1381a5ce-c743-40e9-8a10-4c218085bb5f
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 4924d01c6f5d423b7c553d11eea065534179fe5f
ms.sourcegitcommit: 54fc806036f84a8667cf8f74086358bccd30aa7d
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/20/2018
---
# <a name="how-to-configure-intune-education-settings-for-shared-ipad-devices"></a>Intune-onderwijsinstellingen configureren voor gedeelde iPads

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Intune ondersteunt de iOS-app Classroom, waarmee docenten het leren kunnen begeleiden en de apparaten van studenten in het leslokaal kunnen beheren. Naast de Classroom-app ondersteunt Apple de mogelijkheid om iPads van studenten zo te configureren dat één apparaat door meerdere studenten kan worden gedeeld. In dit document leest u hoe u dit doel kunt realiseren met Intune.

Zie [De Intune-instellingen voor de iOS-app Classroom configureren](education-settings-configure-ios.md) voor informatie over het configureren van toegewezen (1:1) iPads voor het gebruik van de Classroom-app.

## <a name="before-you-start"></a>Voordat u begint

Dit zijn de vereisten voor het gebruiken van de mogelijkheden van gedeelde iPads:

- [Apple School Manager](apple-school-manager-set-up-ios.md) en [School Data Sync (SDS)](https://support.office.com/article/Apple-School-Manager-integration-with-Intune-for-Education-and-School-Data-Sync-974bd1f9-2c7a-45cb-9447-b58166108617) configureren.
- Tijdens de configuratie van Apple School Manager [beheerde Apple ID's](http://help.apple.com/schoolmanager/#/tes78b477c81) instellen voor studenten. Zie [Beheerde Apple ID‘s in het onderwijs](https://support.apple.com/HT205918) voor meer informatie.
- Een inschrijvingsprofiel maken voor de serienummers van apparaten die zijn gesynchroniseerd uit Apple School Manager.

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

1. Meld u aan bij de [Azure-portal](https://portal.azure.com).
2. Kies **Alle services** > **Intune**. Intune bevindt zich in de sectie **Controle en beheer**.
3. Kies in het deelvenster **Intune** de optie **Apparaatconfiguratie**.
2. Kies in het deelvenster **Apparaatconfiguratie** onder de sectie **Beheren** de optie **Profielen**.
5. Kies **Profiel maken** in het deelvenster Profielen.
6. Voer in het deelvenster **Profiel maken** een **Naam** en **Beschrijving** in voor het iOS-opleidingsprofiel.
7. Kies **iOS** in de vervolgkeuzelijst **Platform**.
8. Kies **Onderwijs** in de vervolgkeuzelijst **Profieltype**.
9. Kies **Instellingen** > **Configureren**.

Vervolgens hebt u certificaten nodig om een vertrouwensrelatie te maken tussen de iPads van de docent en studenten. Certificaten worden gebruikt voor het naadloos en op de achtergrond verifiëren van verbindingen tussen apparaten zonder gebruikersnamen en wachtwoorden in te voeren.

>[!Important]
>De docent- en studentencertificaten die u gebruikt, moeten zijn uitgegeven door verschillende certificeringsinstanties (CA's). U moet twee nieuwe onderliggende CA's maken die verbonden zijn met uw bestaande certificaatinfrastructuur: één voor docenten en één voor studenten.

iOS-onderwijsprofielen ondersteunen alleen PFX-certificaten. SCEP-certificaten worden niet ondersteund.

De certificaten die u maakt, moeten niet alleen ondersteuning bieden voor gebruikersverificatie maar ook voor serververificatie.

### <a name="configure-teacher-certificates"></a>Docentcertificaten configureren

Kies **Docentcertificaten** in het deelvenster **Opleiding**.

#### <a name="configure-teacher-root-certificate"></a>Het basiscertificaat voor de docent configureren

Kies onder **Basiscertificaat voor docent** de bladerknop om het basiscertificaat voor de docent te selecteren met de extensie .cer (gecodeerd met DER of Base64), of .P7B (met of zonder volledige keten).

#### <a name="configure-teacher-pkcs12-certificate"></a>PKCS#12-certificaat voor docent configureren

Configureer onder **PKCS #12-certificaat voor docent** de volgende waarden:

- **Indeling van de onderwerpnaam**: Intune zet vóór de algemene naam van het certificaat automatisch **leader** (leider) in het geval van het docentcertificaat en **member** (lid) in het geval van een studentencertificaat.
- **Certificeringsinstantie**: een certificeringsinstantie (CA) voor ondernemingen die wordt uitgevoerd op een Enterprise-editie van Windows Server 2008 R2 of hoger. Een zelfstandige CA wordt niet ondersteund.
- **Naam van certificeringsinstantie**: voer de naam van uw certificeringsinstantie in.
- **Certificaatsjabloonnaam**: voer de naam in van een certificaatsjabloon die is toegevoegd aan een verlenende CA.
- **Drempelwaarde voor verlenging (%)**: geef het percentage van de levensduur van het certificaat op dat resteert voordat het apparaat verlenging van het certificaat aanvraagt.
- **Geldigheidsduur van certificaat**: geef de hoeveelheid resterende tijd op totdat het certificaat verloopt. U kunt een waarde opgeven die lager is dan de geldigheidsperiode in het opgegeven certificaatsjabloon, maar niet hoger. Als de geldigheidsperiode van het certificaat in het certificaatsjabloon bijvoorbeeld twee jaar is, kunt u wel één jaar, maar niet vijf jaar opgeven. De waarde moet ook lager zijn dan de resterende geldigheidsperiode van het certificaat van de verlenende CA.

Wanneer u de docentcertificaten hebt geconfigureerd, kiest u **OK**.

### <a name="configure-student-certificates"></a>Studentencertificaten configureren

1. Kies **Studentencertificaten** in het deelvenster **Opleiding**.
2. Kies in het deelvenster **Studentencertificaten** in de lijst **Type studentapparaatcertificaten** de waarde **Gedeelde iPad**.

#### <a name="configure-student-root-certificate"></a>Het basiscertificaat voor studenten configureren

Kies onder **Basiscertificaat van het apparaat** de bladerknop om het basiscertificaat voor het apparaat te selecteren met de extensie .cer (gecodeerd met DER of Base64), of .P7B (met of zonder volledige keten).

#### <a name="configure-device-pkcs12-certificate"></a>Het PKCS#12-certificaat voor apparaten configureren

Configureer onder **PKCS#12-certificaat voor student** de volgende waarden:

- **Indeling van de onderwerpnaam**: Intune zet vóór de algemene naam van het certificaat automatisch 'leader' (leider) in het geval van het docentcertificaat en 'member' (lid) in het geval van een apparaatcertificaat.
- **Certificeringsinstantie**: een certificeringsinstantie (CA) voor ondernemingen die wordt uitgevoerd op een Enterprise-editie van Windows Server 2008 R2 of hoger. Een zelfstandige CA wordt niet ondersteund.
- **Naam van certificeringsinstantie**: voer de naam van uw certificeringsinstantie in.
- **Certificaatsjabloonnaam**: voer de naam in van een certificaatsjabloon die is toegevoegd aan een verlenende CA.
- **Drempelwaarde voor verlenging (%)**: geef het percentage van de levensduur van het certificaat op dat resteert voordat het apparaat verlenging van het certificaat aanvraagt.
- **Geldigheidsduur van certificaat**: geef de hoeveelheid resterende tijd op totdat het certificaat verloopt. U kunt een waarde opgeven die lager is dan de geldigheidsperiode in het opgegeven certificaatsjabloon, maar niet hoger. Als de geldigheidsperiode van het certificaat in het certificaatsjabloon bijvoorbeeld twee jaar is, kunt u wel één jaar, maar niet vijf jaar opgeven. De waarde moet ook lager zijn dan de resterende geldigheidsperiode van het certificaat van de verlenende CA.

Wanneer u de certificaten hebt geconfigureerd, kiest u **OK**.

### <a name="complete-certificate-setup"></a>Certificaatconfiguratie voltooien

1. Kies **OK** in het deelvenster **Opleiding**.
2. Kies **Maken** in het deelvenster **Profiel maken**.

Het profiel wordt gemaakt en wordt weergegeven in het deelvenster met de profielenlijst.

## <a name="step-3---create-a-device-category"></a>Stap 3: een apparaatcategorie maken

1. Meld u aan bij de [Azure-portal](https://portal.azure.com).
2. Kies **Alle services** > **Intune**. Intune bevindt zich in de sectie **Controle en beheer**.
3. Kies **Apparaatinschrijving** in het deelvenster **Intune**.
4. Kies **Apparaatcategorieën - Overzicht** in het deelvenster **Apparaatinschrijving**.
5. Kies **Maken** in het deelvenster **Apparaatinschrijving - Apparaatcategorieën**.
6. Voer in het deelvenster **Apparaatcategorie maken** een **naam** en een **beschrijving** in voor de categorie.
7. Kies **Maken** in het deelvenster **Apparaatcategorie maken**.

De apparaatcategorie wordt gemaakt in het deelvenster **Apparaatinschrijving – Apparaatcategorieën**.

## <a name="step-4--create-a-dynamic-group"></a>Stap 4: een dynamische groep maken

1. Meld u aan bij de [Azure-portal](https://portal.azure.com).
2. Kies **Alle services** > **Intune**. Intune bevindt zich in de sectie **Controle en beheer**.
3. Kies **Groepen** in het deelvenster **Intune**.
4. Kies **Nieuwe groep** in het deelvenster **Gebruikers en groepen – Alle groepen**.
5. Kies in het deelvenster **Groep** een **Type groep** en voer een **naam** en **beschrijving** voor de groep in.
6. Kies **Dynamisch apparaat** in de vervolgkeuzelijst **Type lidmaatschap**.
7. Kies **Leden van dynamisch apparaat** om lidmaatschapsregels te maken.
8. Ga als volgt te werk in het deelvenster **Dynamisch-lidmaatschapregels**:
1. Selecteer **deviceCategory** in de vervolgkeuzelijst **Locatie voor het toevoegen van apparaten**.
2. Kies **Is gelijk aan**.
3. Typ de apparaatcategorie die u hebt gemaakt in het lege tekstvak.
9. Kies **Query toevoegen** in het deelvenster **Dynamisch-lidmaatschapregels**.
10. Kies **Maken** in het deelvenster **Groep**.

De dynamische groep wordt gemaakt in het deelvenster **Gebruikers en groepen – Alle groepen**.

## <a name="step-5--assign-a-device-to-a-category-carts"></a>Stap 5: een apparaat toewijzen aan een categorie (Winkelwagens)

1. Meld u aan bij de [Azure-portal](https://portal.azure.com).
2. Kies **Alle services** > **Intune**. Intune bevindt zich in de sectie **Controle en beheer**.
3. Kies **Apparaten** in het deelvenster **Intune**.
4. Kies **Alle apparaten** in het deelvenster **Apparaten**.
5. Kies een apparaat in het deelvenster **Apparaten - Alle apparaten**.
6. Kies **Eigenschappen** in het deelvenster van het apparaat.
7. Ga in het deelvenster met eigenschappen van het apparaat naar het tekstvak **Apparaatcategorie** en voer de apparaatcategorie in.
8. Kies **Opslaan** in het deelvenster van het apparaat.

Het apparaat is nu aan de apparaatcategorie gekoppeld. Herhaal dit proces voor alle apparaten die u wilt koppelen aan de apparaatcategorie die u hebt gemaakt.

## <a name="step-6--create-classroom-profiles"></a>Stap 6: klaslokaalprofielen maken

1. Meld u aan bij de [Azure-portal](https://portal.azure.com).
2. Kies **Alle services** > **Intune**. Intune bevindt zich in de sectie **Controle en beheer**.
3. Kies in het deelvenster **Intune** de optie **Apparaatconfiguratie**.
4. Kies **Beheren** > **Winkelwagenprofielen** in het deelvenster **Apparaatconfiguratie**.
5. Kies **Profiel maken** in het deelvenster Profielen.
6. Voer in het deelvenster **Koppeling maken** waarden in voor **Naam** en **Beschrijving**.
7. Kies **Klassen selecteren** > **Configureren** om groepen te koppelen aan het winkelwagenprofiel.
8. Kies de klassen waaraan u het winkelwagenprofiel wilt toewijzen en kies vervolgens **Selecteren**. 
9. Kies **Winkelwagens selecteren** > **Configureren** om groepen te koppelen aan het winkelwagenprofiel.
10. Kies de groepen waaraan u het winkelwagenprofiel wilt toewijzen en kies vervolgens **Selecteren**.
11. Kies **Opslaan** in het deelvenster **Koppeling maken** om het winkelwagenprofiel op te slaan.

Het profiel wordt gemaakt en wordt weergegeven in het deelvenster met de profielenlijst.

## <a name="step-7---assign-the-cart-profile-to-classes"></a>Stap 7: het winkelwagenprofiel toewijzen aan klassen

1. Meld u aan bij de [Azure-portal](https://portal.azure.com).
2. Kies **Alle services** > **Intune**. Intune bevindt zich in de sectie **Controle en beheer**.
3. Kies in het deelvenster **Intune** de optie **Apparaatconfiguratie**.
4. Kies **Beheren** > **Toewijzingsstatus** in het deelvenster **Apparaatconfiguratie**.
5. Selecteer in het deelvenster **Toewijzingsstatus** het **winkelwagenprofiel** dat u hebt gemaakt.
6. Kies **Toewijzingen** in het deelvenster **Winkelwagenprofiel** en kies vervolgens **Groepen selecteren die moeten worden opgenomen** onder **Opnemen**.
7. Selecteer de klassen waarop u het winkelwagenprofiel wilt toepassen (selecteer niet een groep) en kies vervolgens **Selecteren**. 
8. Als u klaar bent, kiest u **Opslaan**.

De toewijzing wordt afgerond en Intune implementeer het klaslokaalprofiel naar de betreffende apparaten op basis van de klaslokaaltoewijzing.

## <a name="next-steps"></a>Volgende stappen

Studenten kunnen nu onderling apparaten delen en studenten kunnen een iPad pakken in een klaslokaal, zich aanmelden met een pincode en dan inhoud zien die specifiek op die student is afgestemd. Ga naar de [website van Apple](https://www.apple.com/education/it/) voor meer informatie over gedeelde iPads.
