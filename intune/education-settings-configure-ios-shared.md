---
title: Intune-instellingen voor gedeelde apparaten voor de iOS-app Classroom
titlesuffix: Azure portal
description: Meer informatie over de Intune-instellingen die u kunt gebruiken voor het beheren van instellingen voor de app Classroom op iOS-apparaten.
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 06/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1381a5ce-c743-40e9-8a10-4c218085bb5f
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 860efd0fb312aab13e543b9a2b4114f408e7137e
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/09/2017
---
# <a name="how-to-configure-intune-education-settings-for-shared-ipad-devices"></a>Intune-onderwijsinstellingen configureren voor gedeelde iPads

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Intune ondersteunt de iOS-app Classroom, waarmee docenten het leren kunnen begeleiden en de apparaten van studenten in het leslokaal kunnen beheren. Naast de Classroom-app ondersteunt Apple de mogelijkheid om iPads van studenten zo te configureren dat één apparaat door meerdere studenten kan worden gedeeld. In dit document leest u hoe u dit doel kunt realiseren met Intune.
Zie [De Intune-instellingen voor de iOS-app Classroom configureren](education-settings-configure-ios.md) voor informatie over het configureren van toegewezen (1:1) iPads voor het gebruik van de Classroom-app.

## <a name="before-you-start"></a>Voordat u begint

Dit zijn de vereisten voor het gebruiken van de mogelijkheden van gedeelde iPads:

- [Apple School Manager](apple-school-manager-set-up-ios.md) en [School Data Sync (SDS)](https://support.office.com/article/Apple-School-Manager-integration-with-Intune-for-Education-and-School-Data-Sync-974bd1f9-2c7a-45cb-9447-b58166108617) configureren.
- Tijdens de configuratie van Apple School Manager [beheerde Apple ID's](http://help.apple.com/schoolmanager/#/tes78b477c81) instellen voor studenten. Zie [Beheerde Apple ID‘s in het onderwijs](https://support.apple.com/en-us/HT205918) voor meer informatie.
- Een inschrijvingsprofiel maken voor de serienummers van apparaten die zijn gesynchroniseerd uit Apple School Manager.

## <a name="step-1---import-your-school-data-into-azure-active-directory"></a>Stap 1: uw schoolgegevens importeren in Azure Active Directory

Gebruik Schoolgegevens synchroniseren (SDS) van Microsoft om schoolgegevens uit een bestaand Studentinformatiesysteem (SIS) te importeren in Azure Active Directory (Azure AD).
SDS synchroniseert informatie uit uw SIS en slaat deze op in Azure AD. Azure AD is een Microsoft-beheersysteem waarmee u gebruikers en apparaten kunt organiseren. U kunt deze gegevens vervolgens gebruiken voor het beheren van uw studenten en klassen. [Meer informatie over het implementeren van SDS](https://support.office.com/article/Overview-of-School-Data-Sync-and-Classroom-f3d1147b-4ade-4905-8518-508e729f2e91).

### <a name="how-to-import-data-using-sds"></a>Gegevens importeren met SDS

U kunt op een van de volgende manieren gegevens importeren in SDS:

- [CSV-bestanden](https://support.office.com/article/Follow-these-steps-71d5fe4a-aa51-4f35-9b53-348898a390a1): bestanden met door komma's gescheiden waarden (.csv) handmatig exporteren en compileren
- [PowerSchool API](https://support.office.com/article/Follow-these-steps-851b5edc-558f-43a9-9122-b2d63458cb8f): dit is een SIS-provider die vereenvoudigde synchronisatie met Azure AD biedt
- [Clever API](https://support.office.com/article/Follow-these-steps-f3d92fde-3ad0-48f3-80a1-1ad0ac4a3fae): een oplossing voor identiteitsbeheer die directe synchronisatie met Azure AD uitvoert
- [OneRoster](https://support.office.com/article/Follow-these-steps-f43cbb2a-b502-497d-a8b1-783dc05a57ab): een CSV-indeling die u kunt exporteren en converteren om te synchroniseren met Azure AD

### <a name="find-out-more"></a>Meer informatie

- [Meer informatie over het synchroniseren van de on-premises schoolgegevens naar Azure AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)
- [Meer informatie over Schoolgegevens synchroniseren van Microsoft](https://sds.microsoft.com/)
- [Meer informatie over licentieverlening in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal)


## <a name="step-2---create-and-assign-an-ios-education-profile-in-intune"></a>Stap 2: een iOS-opleidingsprofiel maken en toewijzen in Intune

### <a name="configure-general-settings"></a>Algemene instellingen configureren

1. Meld u aan bij Azure Portal.
2. Kies **Meer services** > **Overige** > **Intune**.
3. Kies **Apparaten configureren** op de blade **Intune**.
4. Kies **Beheren** > **Profielen** op de blade **Apparaatconfiguratie**.
5. Kies **Profiel maken** op de blade Profielen.
6. Voer op de blade **Profiel maken** een **Naam** en **Beschrijving** in voor het iOS-opleidingsprofiel.
7. Kies **iOS** in de vervolgkeuzelijst **Platform**.
8. Kies **Onderwijs** in de vervolgkeuzelijst **Profieltype**.
9. Kies **Instellingen** > **Configureren**.

Vervolgens hebt u certificaten nodig om een vertrouwensrelatie te maken tussen de iPads van de docent en studenten. Certificaten worden gebruikt voor het naadloos en op de achtergrond verifiëren van verbindingen tussen apparaten zonder gebruikersnamen en wachtwoorden in te voeren.

>[!Important]
>De docent- en studentencertificaten die u gebruikt, moeten zijn uitgegeven door verschillende certificeringsinstanties (CA's). U moet twee nieuwe onderliggende CA's maken die verbonden zijn met uw bestaande certificaatinfrastructuur: één voor docenten en één voor studenten.

iOS-onderwijsprofielen ondersteunen alleen PFX-certificaten. SCEP-certificaten worden niet ondersteund.

De certificaten die u maakt, moeten niet alleen ondersteuning bieden voor gebruikersverificatie maar ook voor serververificatie.

### <a name="configure-teacher-certificates"></a>Docentcertificaten configureren

Kies **Docentcertificaten** op de blade **Opleiding**.

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

1. Kies **Studentcertificaten** op de blade **Opleiding**.
2. Kies op de blade **Studentencertificaten** in de lijst **Type studentapparaatcertificaten** de waarde **Gedeelde iPad**.

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

1. Kies **OK** op de blade **Opleiding**.
2. Kies **Maken** op de blade **Profiel maken**.

Het profiel wordt gemaakt en wordt weergegeven op de blade met de profielenlijst.

## <a name="step-3---create-a-device-category"></a>Stap 3: een apparaatcategorie maken

1. Meld u aan bij Azure Portal.
2. Kies **Meer services** > **Overige** > **Intune**.
3. Kies **Apparaatinschrijving** op de blade **Intune**.
4. Kies **Apparaatcategorieën** op de blade **Apparaatinschrijving - Overzicht**.
5. Kies **Maken** op de blade **Apparaatinschrijving - Apparaatcategorieën**.
6. Voer op de blade **Apparaatcategorie maken** een **naam** en een **beschrijving** in voor de categorie.
7. Kies **Maken** op de blade **Apparaatcategorie maken**.

De apparaatcategorie wordt gemaakt op de blade **Apparaatinschrijving – Apparaatcategorieën**.

## <a name="step-4--create-a-dynamic-group"></a>Stap 4: een dynamische groep maken

1. Meld u aan bij Azure Portal.
2. Kies **Meer services** > **Overige** > **Intune**.
3. Kies **Groepen** op de blade **Intune**.
4. Kies **Nieuwe groep** op de blade **Gebruikers en groepen – Alle groepen**.
5. Geef op de blade **Groep** waarden op voor **Naam** en **Beschrijving** voor de groep.
6. Kies **Dynamische apparaat** in de vervolgkeuzelijst **Type lidmaatschap**.
7. Kies **Leden van dynamisch apparaat** om lidmaatschapsregels te maken.
8. Ga als volgt te werk op de blade **Dynamisch-lidmaatschapregels**:
1. Selecteer **deviceCategory** in de vervolgkeuzelijst **Locatie voor het toevoegen van apparaten**.
2. Kies **Is gelijk aan**.
3. Typ de apparaatcategorie die u hebt gemaakt in het lege tekstvak.
9. Kies **Query toevoegen** op de blade **Dynamisch-lidmaatschapregels**.
10. Kies **Maken** op de blade **Groep**.

De dynamische groep wordt gemaakt op de blade **Gebruikers en groepen – Alle groepen**.

## <a name="step-5--assign-a-device-to-a-category-carts"></a>Stap 5: een apparaat toewijzen aan een categorie (Winkelwagens)

1. Meld u aan bij Azure Portal.
2. Kies **Meer services** > **Overige** > **Intune**.
3. Kies **Apparaten** op de blade **Intune**.
4. Kies **Alle apparaten** op de blade **Apparaten**.
5. Kies een apparaat op de blade **Apparaten - Alle apparaten**.
6. Kies **Eigenschappen** op de blade van het apparaat.
7. Ga op de blade met eigenschappen van het apparaat naar het tekstvak **Apparaatcategorie** en voer de apparaatcategorie in.
8. Kies **Opslaan** op de blade van het apparaat.

Het apparaat is nu aan de apparaatcategorie gekoppeld. Herhaal dit proces voor alle apparaten die u wilt koppelen aan de apparaatcategorie die u hebt gemaakt.

## <a name="step-6--create-classroom-profiles"></a>Stap 6: klaslokaalprofielen maken

1. Meld u aan bij Azure Portal.
2. Kies **Meer services** > **Overige** > **Intune**.
3. Kies **Apparaten configureren** op de blade **Intune**.
4. Kies **Beheren** > **Winkelwagenprofielen** op de blade **Apparaatconfiguratie**.
5. Kies **Profiel maken** op de blade Profielen.
6. Voer op de blade **Koppeling maken** waarden in voor **Naam** en **Beschrijving**.
7. Kies **Klassen selecteren** > **Configureren** om groepen te koppelen aan het winkelwagenprofiel.
8. Kies de klassen waaraan u het winkelwagenprofiel wilt toewijzen en kies vervolgens **Selecteren**. 
9. Kies **Winkelwagens selecteren** > **Configureren** om groepen te koppelen aan het winkelwagenprofiel.
10. Kies de groepen waaraan u het winkelwagenprofiel wilt toewijzen en kies vervolgens **Selecteren**.
11. Kies **Opslaan** op de blade **Koppeling maken** om het winkelwagenprofiel op te slaan.

Het profiel wordt gemaakt en wordt weergegeven op de blade met de profielenlijst.

## <a name="step-7---assign-the-cart-profile-to-classes"></a>Stap 7: het winkelwagenprofiel toewijzen aan klassen

1. Meld u aan bij Azure Portal.
2. Kies **Meer services** > **Overige** > **Intune**.
3. Kies **Apparaten configureren** op de blade **Intune**.
4. Kies **Beheren** > **Toewijzingsstatus** op de blade **Apparaatconfiguratie**.
5. Selecteer op de blade **Toewijzingsstatus** het** **winkelwagenprofiel dat u hebt gemaakt.
6. Kies **Toewijzingen** op de blade **Winkelwagenprofiel** en kies vervolgens **Groepen selecteren die moeten worden opgenomen** onder **Opnemen**.
7. Selecteer de klassen waarop u het winkelwagenprofiel wilt toepassen (selecteer niet een groep) en kies vervolgens **Selecteren**. 
8. Als u klaar bent, kiest u **Opslaan**.

De toewijzing wordt afgerond en Intune implementeer het klaslokaalprofiel naar de betreffende apparaten op basis van de klaslokaaltoewijzing.

## <a name="next-steps"></a>Volgende stappen

Studenten kunnen nu onderling apparaten delen en studenten kunnen een iPad pakken in een klaslokaal, zich aanmelden met een pincode en dan inhoud zien die specifiek op die student is afgestemd. Ga naar de [website van Apple](https://www.apple.com/education/it/) voor meer informatie over gedeelde iPads.
