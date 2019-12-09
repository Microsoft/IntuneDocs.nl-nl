---
title: Inschrijving met het programma Apple School Manager voor iOS-apparaten
titleSuffix: Microsoft Intune
description: Meer informatie over het instellen van inschrijving met het Apple School Manager Program voor zakelijke iOS-apparaten met Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 12/06/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: enrollment
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 4c35a23e-0c61-11e8-ba89-0ed5f89f718b
ms.reviewer: tisilver
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1c574714b4bd4f748c2dbe898555de35b0e03190
ms.sourcegitcommit: f26039d674eb4d61ab68264dd1a10b2e5e1d842c
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/02/2019
ms.locfileid: "74691829"
---
# <a name="set-up-ios-device-enrollment-with-apple-school-manager"></a>Inschrijving van iOS-apparaten instellen met Apple School Manager

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Met Intune kunt u iOS-apparaten inschrijven die zijn aangeschaft via het programma [Apple School Manager](https://school.apple.com/). Als u Intune gebruikt in combinatie met Apple School Manager, kunt u een groot aantal iOS-apparaten registreren zonder ze ooit aan te raken. Wanneer een student of docent het apparaat inschakelt, wordt Configuratieassistent uitgevoerd met vooraf gedefinieerde instellingen en wordt het apparaat geregistreerd voor beheer.

Als u registratie via Apple School Manager wilt inschakelen, gebruikt u zowel de Intune- als Apple School Manager-portal. U hebt een lijst met serienummers of een aankoopordernummer nodig om apparaten voor beheer aan Intune toe te wijzen. U maakt DEP-inschrijvingsprofielen met instellingen die tijdens de inschrijving op de apparaten van toepassing zijn geweest.

Inschrijving voor Apple School Manager kan niet worden gebruikt met het [Device Enrollment Program van Apple](device-enrollment-program-enroll-ios.md) of de [apparaatinschrijvingsmanager](device-enrollment-manager-enroll.md).

**Vereisten**
- [Apple MDM-push certificaat (Mobile Device Management)](apple-mdm-push-certificate-get.md)
- [MDM-instantie](../fundamentals/mdm-authority-set.md)
- [Apple MDM-pushcertificaat](apple-mdm-push-certificate-get.md)
- Als u ADFS gebruikt, vereist gebruikersaffiniteit [WS-Trust 1.3 gebruikersnaam/gemengd eindpunt](https://technet.microsoft.com/library/adfs2-help-endpoints). [Meer informatie](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint).
- Apparaten die zijn gekocht via het programma [Apple School Management](http://school.apple.com)

## <a name="get-an-apple-token-and-assign-devices"></a>Een Apple-token ophalen en apparaten toewijzen

Voordat u iOS-bedrijfsapparaten met Apple School Manager kunt inschrijven, hebt u een token (.p7m) van Apple nodig. Intune kan met dit token informatie synchroniseren over apparaten die aan Apple School Manager deelnemen. Ook kan Intune hiermee inschrijvingsprofielen naar Apple uploaden en apparaten toewijzen aan die profielen. Als u zich in de Apple-portal bevindt, kunt u ook apparaatserienummers voor beheer toewijzen.

### <a name="step-1-download-the-intune-public-key-certificate-required-to-create-an-apple-token"></a>Stap 1. Het openbare-sleutelcertificaat van Intune downloaden dat is vereist voor het maken van een Apple-token

1. Kies in het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431) de opties **Apparaten** > **iOS** > **iOS-inschrijving** > **Tokens voor het inschrijvingsprogramma** > **Toevoegen**.

   ![Een token voor het inschrijvingsprogramma ophalen.](./media/device-enrollment-program-enroll-ios/image01.png)

2. Kies in de blade **Token voor het inschrijvingsprogramma** de optie **Uw openbare sleutel downloaden** om de versleutelingssleutel (.pem) lokaal op te slaan. Het .pem-bestand wordt gebruikt om een vertrouwensrelatiecertificaat bij de portal Apple School Manager aan te vragen.
     ![De blade Token voor het inschrijvingsprogramma.](./media/apple-school-manager-set-up-ios/image02.png)

### <a name="step-2-download-a-token-and-assign-devices"></a>Stap 2. Een token downloaden en apparaten toewijzen
1. Kies **Een token maken via Apple School Manager** en meld u met de Apple-id van uw bedrijf aan bij Apple School. U kunt dit Apple-id gebruiken om uw Apple School Manager-token te verlengen.
2. Ga in de [Apple School Manager-portal](https://school.apple.com) naar **MDM-servers** en kies vervolgens **MDM-server toevoegen** (rechtsboven).
3. Voer de **MDM-servernaam** in. De servernaam is voor eigen referentie en dient om de MDM-server te identificeren. Het is niet de naam of URL van de Microsoft Intune-server.
   ![Schermopname van de Apple School Manager-portal met de optie voor het serienummer geselecteerd](./media/apple-school-manager-set-up-ios/asm-server-assignment.png)

4. Kies in de Apple-portal de optie **Bestand uploaden...** , blader naar het PEM-bestand en selecteer **MDM-server opslaan** (rechtsonder).
5. Kies **Token ophalen** en download het servertokenbestand (.p7m) naar uw computer.
6. Ga naar **Toewijzingen van apparaten** en **Apparaat kiezen** door handmatige invoer van de **serienummers** of het **volgordenummer**, of selecteer **CSV-bestand uploaden**.
     ![Schermopname van de Apple School Manager-portal met de optie voor het serienummer geselecteerd](./media/apple-school-manager-set-up-ios/asm-device-assignment.png)
7. Kies de actie **Toewijzen aan server** en kies de **MDM-server** die u hebt gemaakt.
8. Geef uw apparaat aan onder **Apparaten kiezen** en geef de apparaatgegevens op.
9. Selecteer **Toewijzen aan server**, kies de &lt;Servernaam&gt; die is opgegeven voor Microsoft Intune en kies vervolgens **OK**.

### <a name="step-3-save-the-apple-id-used-to-create-this-token"></a>Stap 3. De Apple-id opslaan die u hebt gebruikt om dit token te maken

Geef in het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431) de Apple-id op voor toekomstige referentie.

![Schermopname van het invoeren van de Apple ID die is gebruikt voor het maken van het token voor het inschrijvingsprogramma en het uploaden van het token.](./media/apple-school-manager-set-up-ios/image03.png)

### <a name="step-4-upload-your-token"></a>Stap 4. Uw token uploaden
Ga in het venster **Apple-token** naar het certificaatbestand (.pem), kies **Openen** en vervolgens **Maken**. Met het pushcertificaat kan Intune iOS-apparaten inschrijven en beheren door beleid naar geregistreerde mobiele apparaten te pushen. Intune synchroniseert automatisch de Apple School Manager-apparaten van Apple.

## <a name="create-an-apple-enrollment-profile"></a>Een Apple-inschrijvingsprofiel maken
Na installatie van het token kunt u een inschrijvingsprofiel voor Apple School-apparaten maken. Met een inschrijvingsprofiel voor apparaten worden de instellingen gedefinieerd die worden toegepast op een groep apparaten tijdens de inschrijving.

1. Kies in het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431) de opties **Apparaten** > **iOS** > **iOS-inschrijving** > **Tokens voor het inschrijvingsprogramma**.
2. Selecteer een token, kies **Profielen** en kies vervolgens **Profiel maken**.

3. Voer in het venster **Profiel maken** een **naam** en een **beschrijving** voor het profiel in voor administratieve doeleinden. Gebruikers zien deze gegevens niet. U kunt dit veld **Naam** gebruiken om een dynamische groep te maken in Azure Active Directory. Gebruik de profielnaam om de parameter enrollmentProfileName te definiëren om apparaten aan dit inschrijvingsprofiel toe te wijzen. Meer informatie over [Azure Active Directory dynamic groups](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal#rules-for-devices) (dynamische Azure Active Directory-groepen).

    ![Naam en beschrijving van het profiel.](./media/apple-school-manager-set-up-ios/image05.png)

4. Geef voor **Gebruikersaffiniteit** aan of andere apparaten met dit profiel met of zonder toegewezen gebruiker moeten worden ingeschreven.
    - **Inschrijven met gebruikersaffiniteit**: kies deze optie voor apparaten die eigendom zijn van gebruikers en die de bedrijfsportal willen gebruiken voor services zoals het installeren van apps. Met deze optie kunnen gebruikers hun apparaat verifiëren door de bedrijfsportal te gebruiken. Als u ADFS gebruikt, vereist gebruikersaffiniteit [WS-Trust 1.3 gebruikersnaam/gemengd eindpunt](https://technet.microsoft.com/library/adfs2-help-endpoints). [Meer informatie](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint).   Voor de modus Gedeelde iPad in Apple School Manager moeten gebruikers worden ingeschreven zonder gebruikersaffiniteit.

    - **Inschrijven zonder gebruikersaffiniteit**: kies deze optie voor apparaten die niet aan één gebruiker zijn gelieerd, zoals een gedeeld apparaat. Gebruik deze optie voor apparaten waarmee taken worden uitgevoerd zonder toegang tot lokale gebruikersgegevens. Apps als de bedrijfsportal-app werken niet.

5. Als u kiest voor **Inschrijven met gebruikersaffiniteit**, kunt u gebruikers zich te laten verifiëren met de bedrijfsportal in plaats van de Apple-configuratieassistent.

    ![Verificatie met de bedrijfsportal.](./media/apple-school-manager-set-up-ios/authenticatewithcompanyportal.png)

    > [!NOTE]
    > Als u een van de volgende handelingen wilt uitvoeren, stelt u **Verifiëren met bedrijfsportal in plaats van Apple-configuratieassistent** in op **Ja**.
    >    - meervoudige verificatie gebruiken
    >    - gebruikers vragen het wachtwoord te wijzigen als ze zich de eerste keer aanmelden
    >    - gebruikers vragen om hun verlopen wachtwoorden tijdens het inschrijven te herstellen
    >
    > Deze worden niet ondersteund bij het verifiëren met Apple-configuratieassistent.

6. Kies **Instellingen voor apparaatbeheer** en geef aan of u wilt dat apparaten die dit profiel gebruiken, onder supervisie worden gesteld.
    Met apparaten **onder supervisie** krijgt u meer beheeropties en de activeringsvergrendeling is standaard uitgeschakeld. Microsoft raadt het gebruik van DEP aan als mechanisme voor het inschakelen van de supervisiemodus, met name voor organisaties die veel iOS-apparaten implementeren.

    Gebruikers worden op twee manieren gewaarschuwd dat hun apparaten onder supervisie staan:

   - Het vergrendelingsscherm meldt: 'Deze iPhone wordt beheerd door Contoso.'
   - Het scherm **Instellingen** > **Algemeen** > **Info** meldt: 'Deze iPhone is onder supervisie. Contoso kan uw internetverkeer bijhouden en de locatie van dit apparaat bepalen'.

     > [!NOTE]
     > Een apparaat dat is ingeschreven zonder supervisie, kan alleen opnieuw worden ingesteld met behulp van de Apple Configurator. Als u het apparaat op deze manier opnieuw wilt instellen, moet u een iOS-apparaat verbinden met een Mac via een USB-kabel. Meer informatie hierover vindt u in de [Apple Configurator-documentatie](http://help.apple.com/configurator/mac/2.3).

7. Kies of u vergrendelde inschrijving wilt voor apparaten die dit profiel gebruiken. **Vergrendelde inschrijving** schakelt de iOS-instellingen uit, waardoor het beheerprofiel kan worden verwijderd uit het menu **Instellingen**. Als het apparaat is ingeschreven, kunt u deze instelling niet wijzigen zonder het apparaat te wissen. Bij dergelijke apparaten is het vereist dat de beheermodus **Onder supervisie** is ingesteld op *Ja*. 

8. U kunt meerdere gebruikers zich met een beheerde Apple-id laten aanmelden bij ingeschreven iPads. Als u dit wilt toestaan, kiest u **Ja** onder **Gedeelde iPad** (deze optie vereist dat **Inschrijven zonder gebruikersaffiniteit** en **Onder supervisie** zijn ingesteld op **Ja**.) Beheerde Apple-id's worden gemaakt in de portal Apple School Manager. Lees meer over [Gedeelde iPad](../fundamentals/education-settings-configure-ios-shared.md) en [de vereisten van Apple voor gedeelde iPad's](https://help.apple.com/classroom/ipad/2.0/#/cad7e2e0cf56).

9. Kies of u wilt dat apparaten die dit profiel gebruiken, kunnen **synchroniseren met computers**. Als u **Apple Configurator per certificaat toestaan** kiest, moet u een certificaat kiezen onder **Apple Configurator-certificaten**.

10. Als u in de vorige stap hebt gekozen voor **Apple Configurator per certificaat toestaan**, moet u een Apple Configurator-certificaat kiezen om te importeren.

11. U kunt een naamgevingsindeling opgeven voor apparaten die automatisch wordt toegepast wanneer zij zich inschrijven. Selecteer hiervoor **Ja** onder **Sjabloon voor apparaatnamen toepassen**. Voer vervolgens in het tekstvak **Apparaatnaamsjabloon** het te gebruiken sjabloon in voor de naam die dit profiel gebruiken. U kunt een sjabloonindeling opgeven waarin het apparaattype en serienummer wordt opgenomen.

12. Kies **OK**.

13. Kies **Instellingen voor Configuratieassistent** om de volgende profielinstellingen te configureren: ![Aanpassing van Configuratieassistent](./media/apple-school-manager-set-up-ios/setupassistantcustom.png).


    |                 Instelling                  |                                                                                               Beschrijving                                                                                               |
    |------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    |     <strong>Naam afdeling</strong>     |                                                             Wordt weergegeven wanneer de gebruiker tijdens de activering op <strong>Over configuratie</strong> tikt.                                                              |
    |    <strong>Telefoonnummer van afdeling</strong>     |                                                          Wordt weergegeven wanneer de gebruiker tijdens de activering de knop <strong>Hulp nodig?</strong> klikt.                                                          |
    | <strong>Configuratieassistentopties</strong> |                                                     De volgende instellingen zijn optioneel en kunnen naderhand worden geconfigureerd in het iOS-menu <strong>Instellingen</strong>.                                                      |
    |        <strong>Wachtwoordcode</strong>         | Hiermee wordt tijdens de activering gevraagd om de wachtwoordcode. Vraag altijd om een wachtwoordcode voor onbeveiligde apparaten, tenzij toegang op een andere manier wordt beheerd (bijvoorbeeld een kioskmodus die het apparaat tot één app beperkt). |
    |    <strong>Locatieservices</strong>    |                                                                 Als deze optie is ingeschakeld, wordt tijdens de activering door Configuratieassistent om de service gevraagd.                                                                  |
    |         <strong>Herstellen</strong>         |                                                                Als deze optie is ingeschakeld, wordt tijdens de activering door Configuratieassistent gevraagd om een iCloud-back-up.                                                                 |
    |   <strong>iCloud en Apple-id</strong>   |                         Als deze optie is ingeschakeld, wordt de gebruiker door de Configuratieassistent gevraagd om zich aan te melden met een Apple-id en kan op het scherm Apps en gegevens het apparaat worden hersteld vanuit de iCloud-back-up.                         |
    |  <strong>Voorwaarden</strong>   |                                                   Als deze optie is ingeschakeld, wordt tijdens de activering door Configuratieassistent gevraagd om de voorwaarden van Apple te accepteren.                                                   |
    |        <strong>Touch-id</strong>         |                                                                 Als deze optie is ingeschakeld, wordt tijdens de activering door Configuratieassistent om deze service gevraagd.                                                                 |
    |        <strong>Apple Pay</strong>        |                                                                 Als deze optie is ingeschakeld, wordt tijdens de activering door Configuratieassistent om deze service gevraagd.                                                                 |
    |          <strong>In- en uitzoomen</strong>           |                                                                 Als deze optie is ingeschakeld, wordt tijdens de activering door Configuratieassistent om deze service gevraagd.                                                                 |
    |          <strong>Siri</strong>           |                                                                 Als deze optie is ingeschakeld, wordt tijdens de activering door Configuratieassistent om deze service gevraagd.                                                                 |
    |     <strong>Diagnostische gegevens</strong>     |                                                                 Als deze optie is ingeschakeld, wordt tijdens de activering door Configuratieassistent om deze service gevraagd.                                                                 |


14. Kies **OK**.

15. Kies **Maken** om een profiel op te slaan.

## <a name="connect-school-data-sync"></a>Verbinding maken met Schoolgegevens synchroniseren
(Optioneel) Apple School Manager ondersteunt het synchroniseren van gegevens van lesroosters met Azure Active Directory (AD) met behulp van Microsoft School Data Sync (SDS). U kunt slechts één token synchroniseren met SDS. Als u een ander token met School Data Sync hebt ingesteld, wordt SDS verwijderd van het token dat het eerder had. Het huidige token wordt vervangen door een nieuwe verbinding. Voltooi de volgende stappen voor het gebruik van SDS om schoolgegevens te synchroniseren.

1. Kies in het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431) de opties **Apparaten** > **iOS** > **iOS-inschrijving** > **Tokens voor het inschrijvingsprogramma**.
2. Selecteer een Apple School Manager-token en kies vervolgens **School Data Sync**.
3. Kies onder **School Data Sync** voor **Toestaan**. Met deze instelling kan Intune verbinding maken met SDS in Office 365.
4. Als u een verbinding tussen Apple School Manager en Azure AD wilt maken, kiest u **Microsoft School Data Sync instellen**. Meer informatie over [het instellen van Microsoft School Data Sync](https://support.office.com/article/Install-the-School-Data-Sync-Toolkit-8e27426c-8c46-416e-b0df-c29b5f3f62e1).
5. Klik op **Opslaan** > **OK**.

## <a name="sync-managed-devices"></a>Beheerde apparaten synchroniseren

Nu Intune toestemming heeft om uw Apple School Manager-apparaten te beheren, kunt u Intune synchroniseren met de Apple-service om uw beheerde apparaten weer te geven in Intune.

Kies in het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431) de opties **Apparaten** > **iOS** > **iOS-inschrijving** > **Tokens voor het inschrijvingsprogramma** > kies een token in de lijst > **Apparaten** > **Synchroniseren**. ![Schermafbeelding van het knooppunt Apparaten voor het inschrijvingsprogramma en de koppeling Synchronisatie.](./media/apple-school-manager-set-up-ios/image06.png)

Intune legt de volgende beperkingen op om aan de voorwaarden van Apple voor acceptabel verkeer van het inschrijvingsprogramma te voldoen:
- Een volledige synchronisatie kan niet vaker dan eens in de zeven dagen worden uitgevoerd. Tijdens volledige synchronisatie wordt elk Apple-serienummer vernieuwd dat aan Intune is toegewezen. Als een volledige synchronisatie wordt uitgevoerd binnen zeven dagen na de vorige volledige synchronisatie, vernieuwt Intune alleen serienummers die nog niet aanwezig zijn in Intune.
- Een synchronisatieaanvraag krijgt 15 minuten de tijd om te worden uitgevoerd. Gedurende deze tijd of totdat de aanvraag is geslaagd, is de knop **Synchronisatie** uitgeschakeld.
- Intune synchroniseert elke 24 uur nieuwe en verwijderde apparaten met Apple.

>[!NOTE]
>U kunt ook Apple School Manager-serienummers toewijzen aan profielen vanaf de blade **Apparaten voor het inschrijvingsprogramma**.

## <a name="assign-a-profile-to-devices"></a>Een profiel aan apparaten toewijzen
Apple School Manager-apparaten die worden beheerd door Intune, moeten een profiel voor het inschrijvingsprogramma toegewezen krijgen voordat ze worden ingeschreven.

1. Kies in het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431) de opties **Apparaten** > **iOS** > **iOS-inschrijving** > **Tokens voor het inschrijvingsprogramma** > kies een token in de lijst.
2. Kies **Apparaten** > kies apparaten uit de lijst > **Profiel toewijzen**.
3. Kies onder **Profiel toewijzen** een profiel voor de apparaten en kies vervolgens **Toewijzen**.

## <a name="distribute-devices-to-users"></a>Apparaten onder gebruikers distribueren

U hebt beheer en synchronisatie tussen Apple en Intune ingeschakeld en u hebt een profiel toegewezen om uw Apple School-apparaten te kunnen inschrijven. De apparaten kunnen nu worden uitgedeeld aan de gebruikers. Wanneer een iOS Apple School Manager-apparaat wordt ingeschakeld, wordt het door Intune ingeschreven voor beheer. Profielen kunnen niet worden toegepast op geactiveerde apparaten die momenteel in gebruik zijn totdat het apparaat wordt gewist.
