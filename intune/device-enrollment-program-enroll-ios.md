---
title: iOS-apparaten inschrijven - Device Enrollment Program
titleSuffix: Microsoft Intune
description: Meer informatie over het registreren van iOS-apparaten in bedrijfseigendom met het Device Enrollment Program (DEP).
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 05/04/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 7ddbf360-0c61-11e8-ba89-0ed5f89f718b
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: bfc42775424ac84737af6c713a04295e24859f79
ms.sourcegitcommit: a5bd08f2b6a0693fa62683aa2d3699041030269e
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/23/2018
ms.locfileid: "39203251"
---
# <a name="automatically-enroll-ios-devices-with-apples-device-enrollment-program"></a>iOS-apparaten automatisch inschrijven met het Device Enrollment Program van Apple

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Met de informatie in dit artikel kunt u iOS-apparaten inschrijven die zijn gekocht via het [Device Enrollment Program (DEP)](https://deploy.apple.com) van Apple. U kunt inschrijving met DEP voor grote aantallen apparaten inschakelen zonder dat u ze hoeft aan te raken. U kunt deze apparaten rechtstreeks naar de gebruikers verzenden, net als iPhones en iPads. Als de gebruiker het apparaat inschakelt, wordt Configuratieassistent uitgevoerd met vooraf gedefinieerde instellingen en het apparaat ingeschreven bij beheer.

Voor het inschakelen van DEP-inschrijving moet u zowel de Intune-portal als de Apple DEP-portal gebruiken. U hebt een lijst met serienummers of een aankoopordernummer nodig om apparaten voor beheer aan Intune toe te wijzen. U maakt DEP-inschrijvingsprofielen met instellingen die tijdens de inschrijving op de apparaten van toepassing zijn geweest.

Overigens werkt de DEP-registratie niet met de [apparaatinschrijvingsmanager](device-enrollment-manager-enroll.md).

## <a name="what-is-supervised-mode"></a>Wat is de supervisiemodus?
Apple heeft de supervisiemodus geïntroduceerd in iOS 5. Een iOS-apparaat in de supervisiemodus kan worden beheerd met meer besturingselementen. Hierdoor is het vooral handig voor apparaten van het bedrijf. Intune ondersteunt het configureren van apparaten voor de supervisiemodus als onderdeel van het Apple Device Enrollment Program (DEP). 

<!--
**Steps to enable enrollment programs from Apple**
1. [Get an Apple DEP token and assign devices](#get-the-apple-dep-token)
2. [Create an enrollment profile](#create-an-apple-enrollment-profile)
3. [Synchronize DEP-managed devices](#sync-managed-device)
4. [Assign DEP profile to devices](#assign-an-enrollment-profile-to-devices)
5. [Distribute devices to users](#end-user-experience-with-managed-devices)
-->
## <a name="prerequisites"></a>Vereisten
- Apparaten die zijn gekocht in het [Device Enrollment Program van Apple](http://deploy.apple.com)
- [MDM-instantie](mdm-authority-set.md)
- [Apple MDM-pushcertificaat](apple-mdm-push-certificate-get.md)

## <a name="get-an-apple-dep-token"></a>Een Apple DEP-token ophalen

Voordat u iOS-apparaten met DEP kunt inschrijven, moet u een DEP-tokenbestand (.p7m) van Apple ontvangen. Intune kan met deze token informatie synchroniseren over DEP-apparaten die in eigendom zijn van uw bedrijf. Ook kan Intune hiermee inschrijvingsprofielen naar Apple uploaden en apparaten toewijzen aan die profielen.

U gebruikt de Apple DEP-portal om een DEP-token te maken. U gebruikt de DEP-portal ook om apparaten aan Intune toe te wijzen voor beheer.

> [!NOTE]
> In Intune kan een verwijderd Apple DEP-token worden hersteld, als u de token van de klassieke Intune-portal verwijdert voordat u naar Azure migreert. U kunt het DEP-token opnieuw verwijderen uit Azure Portal verwijderen. U kunt het DEP-token opnieuw verwijderen uit Azure Portal verwijderen.

### <a name="step-1-download-the-intune-public-key-certificate-required-to-create-the-token"></a>Stap 1. Download het openbare-sleutelcertificaat van Intune dat is vereist om het token te maken.

1. Kies in [Intune in Azure Portal](https://aka.ms/intuneportal) **Apparaatinschrijving** > **Apple-inschrijving** > **Token voor het inschrijvingsprogramma** > **Toevoegen**.

    ![Een token voor het inschrijvingsprogramma ophalen.](./media/device-enrollment-program-enroll-ios/image01.png)

2. Geef Microsoft toestemming om gebruikers- en apparaatgegevens naar Apple te verzenden door **Ik ga akkoord** te selecteren.

   ![Schermopname van het deelvenster Token voor het inschrijvingsprogramma in de werkruimte Apple-certificaten voor het downloaden van de openbare sleutel.](./media/device-enrollment-program-enroll-ios-newui/add-enrollment-program-token-pane.png)

3. Kies **Uw openbare-sleutelcertificaat downloaden** en sla het bestand met de versleutelingssleutel (.pem) lokaal op. Het .pem-bestand wordt gebruikt om een vertrouwensrelatiecertificaat bij de portal Apple Device Enrollment Program aan te vragen.


### <a name="step-2-use-your-key-to-download-a-token-from-apple"></a>Stap 2. Gebruik uw sleutel om een token van Apple te downloaden.

1. Kies **Een token voor Apple Device Enrollment Program maken** om de Deployment Program-portal van Apple te openen en meld u aan met uw Apple-id. Deze Apple-id kunt u gebruiken om uw DEP-token te verlengen.
2.  Kies **Aan de slag** bij **Device Enrollment Program** in de [Deployment Programs-portal](https://deploy.apple.com) van Apple.

3. Kies **MDM-server toevoegen** op de pagina **Servers beheren**.
4. Voer de **MDM-servernaam** in en kies **Volgende**. De servernaam is voor eigen referentie en dient om de MDM-server te identificeren. Het is niet de naam of URL van de Microsoft Intune-server.

5. Het dialoogvenster **Voeg &lt;servernaam&gt;** wordt geopend, met de instructie dat u uw **openbare sleutel moet uploaden**. Kies **Bestand selecteren...** om het .pem-bestand te uploaden en kies **Volgende**.

6. Ga naar **Deployment Programs** &gt; **Device Enrollment Program** &gt; **Apparaten beheren**.
7. Geef onder **Kies apparaten op** aan hoe apparaten worden geïdentificeerd:
    - **Serienummer**
    - **Ordernummer**
    - **CSV-bestand uploaden**

   ![Schermopname van het opgeven van apparaten op serienummer, het kiezen van een actie zoals toewijzen aan server en de naam van de server selecteren.](./media/enrollment-program-token-specify-serial.png)

8. Voor **Kies actie** kiest u **Toewijzen aan server**, kiest u de &lt;Servernaam&gt; die is opgegeven voor Microsoft Intune en kiest u vervolgens **OK**. De opgegeven apparaten worden voor beheer toegewezen aan de Intune-server en er verschijnt een melding dat de **toewijzing is voltooid**.

   Ga in de Apple-portal **Deployment Programs** &gt; **Device Enrollment Program** &gt; **Toewijzingsgeschiedenis weergeven** om een lijst van apparaten en hun toewijzing aan de MDM-server te bekijken.

### <a name="step-3-save-the-apple-id-used-to-create-this-token"></a>Stap 3. Sla de Apple-id op die u hebt gebruikt om dit token te maken.

Voer in Intune in de Apple-portal de Apple-id in, zodat u deze altijd kunt terugvinden.

![Schermopname van het invoeren van de Apple ID die is gebruikt voor het maken van het token voor het inschrijvingsprogramma en het uploaden van het token.](./media/device-enrollment-program-enroll-ios/image03.png)

### <a name="step-4-upload-your-token"></a>Stap 4. Upload uw token.
Ga in het venster **Apple-token** naar het certificaatbestand (.pem), kies **Openen** en vervolgens **Maken**. Met het pushcertificaat kan Intune iOS-apparaten inschrijven en beheren door beleid naar geregistreerde mobiele apparaten te pushen. Intune wordt automatisch gesynchroniseerd met Apple om het account voor het inschrijvingsprogramma weer te geven.

## <a name="create-an-apple-enrollment-profile"></a>Een Apple-inschrijvingsprofiel maken

Na installatie van de token kunt u een inschrijvingsprofiel voor DEP-apparaten maken. Met een inschrijvingsprofiel voor apparaten worden de instellingen gedefinieerd die worden toegepast op een groep apparaten tijdens de inschrijving.

1. Kies in Intune in Azure Portal **Apparaatinschrijving** > **Apple-inschrijving** > **Token voor het inschrijvingsprogramma**.
2. Selecteer een token, kies **Profielen** en kies vervolgens **Profiel maken**.

    ![Maak een schermopname van het profiel.](./media/device-enrollment-program-enroll-ios/image04.png)

3. Voer in het venster **Profiel maken** een **naam** en een **beschrijving** voor het profiel in voor administratieve doeleinden. Gebruikers zien deze gegevens niet. U kunt dit veld **Naam** gebruiken om een dynamische groep te maken in Azure Active Directory. Gebruik de profielnaam om de parameter enrollmentProfileName te definiëren om apparaten aan dit inschrijvingsprofiel toe te wijzen. Meer informatie over [Azure Active Directory dynamic groups](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal#using-attributes-to-create-rules-for-device-objects) (dynamische Azure Active Directory-groepen).

    ![Naam en beschrijving van het profiel.](./media/device-enrollment-program-enroll-ios/image05.png)

4. Geef voor **Gebruikersaffiniteit** aan of andere apparaten met dit profiel met of zonder toegewezen gebruiker moeten worden ingeschreven.
    - **Inschrijven met gebruikersaffiniteit**: kies deze optie voor apparaten die eigendom zijn van gebruikers en die de bedrijfsportal willen gebruiken voor services zoals het installeren van apps. Met deze optie kunnen gebruikers hun apparaat verifiëren door de bedrijfsportal te gebruiken. Als u ADFS gebruikt, vereist gebruikersaffiniteit [WS-Trust 1.3 gebruikersnaam/gemengd eindpunt](https://technet.microsoft.com/library/adfs2-help-endpoints). [Meer informatie](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint).

    - **Inschrijven zonder gebruikersaffiniteit**: kies deze optie voor een apparaat dat niet aan één gebruiker is gelieerd. Gebruik dit voor apparaten waarmee taken worden uitgevoerd zonder toegang tot lokale gebruikersgegevens. Apps als de bedrijfsportal-app werken niet.

5. Als u kiest voor **Inschrijven met gebruikersaffiniteit**, hebt u de optie om gebruikers zich te laten verifiëren met de bedrijfsportal in plaats van de Apple-configuratieassistent.

    ![Verificatie met de bedrijfsportal.](./media/device-enrollment-program-enroll-ios/authenticatewithcompanyportal.png)

    > [!NOTE]
    > Meervoudige verificatie (MFA) werkt niet tijdens de DEP-inschrijving als u profieleigenschappen hebt die zijn ingesteld op **Inschrijven met gebruikersaffiniteit**. Na de inschrijving werkt MFA zoals verwacht op apparaten. Op apparaten wordt de gebruiker niet gevraagd het wachtwoord te wijzigen als ze zich de eerste keer aanmelden. Daarnaast wordt gebruikers met verlopen wachtwoorden niet gevraagd hun wachtwoord opnieuw in te stellen tijdens de inschrijving. Deze gebruikers moeten het wachtwoord vanaf een ander apparaat opnieuw instellen.

6. Kies **Instellingen voor apparaatbeheer** en selecteer of u wilt dat apparaten die dit profiel gebruiken, onder supervisie worden gesteld.

    ![Schermopname Instellingen voor apparaatbeheer.](./media/device-enrollment-program-enroll-ios/devicemanagementsettingsblade.png)

    Met apparaten **onder supervisie** krijgt u meer beheeropties en de activeringsvergrendeling is standaard uitgeschakeld. Microsoft raadt het gebruik van DEP aan als mechanisme voor het inschakelen van de supervisiemodus, met name voor organisaties die veel iOS-apparaten implementeren.

    Gebruikers worden op twee manieren gewaarschuwd dat hun apparaten onder supervisie staan:

   - Het vergrendelingsscherm meldt: Deze iPhone wordt beheerd door Contoso.
   - Het scherm **Instellingen** > **Algemeen** > **Over** meldt: Deze iPhone staat onder supervisie. Contoso kan uw internetverkeer bijhouden en de locatie van dit apparaat bepalen'.

     > [!NOTE]
     > Een apparaat dat is ingeschreven zonder supervisie, kan alleen opnieuw worden ingesteld met behulp van de Apple Configurator. Als u het apparaat op deze manier opnieuw wilt instellen, moet u een iOS-apparaat verbinden met een Mac via een USB-kabel. Meer informatie hierover vindt u in de [Apple Configurator-documentatie](http://help.apple.com/configurator/mac/2.3).

7. Kies of u vergrendelde inschrijving wilt voor apparaten die dit profiel gebruiken. **Vergrendelde inschrijving** schakelt de iOS-instellingen uit, waardoor het beheerprofiel kan worden verwijderd uit het menu **Instellingen**. Als het apparaat is ingeschreven, kunt u deze instelling niet wijzigen zonder het apparaat terug te zetten naar de fabrieksinstellingen. Bij dergelijke apparaten is het vereist dat de beheermodus **Onder supervisie** is ingesteld op *Ja*. 

8. Kies of u wilt dat apparaten die dit profiel gebruiken, kunnen **synchroniseren met computers**. Als u **Apple Configurator per certificaat toestaan** kiest, moet u een certificaat kiezen onder **Apple Configurator-certificaten**.

9. Als u in de vorige stap hebt gekozen voor **Apple Configurator per certificaat toestaan**, moet u een Apple Configurator-certificaat kiezen om te importeren.

10. Kies **OK**.

11. Kies **Instellingen voor Configuratieassistent** om de volgende profielinstellingen te configureren: ![Aanpassing van Configuratieassistent](./media/device-enrollment-program-enroll-ios/setupassistantcustom.png).


    |                 Instelling                  |                                                                                               Description                                                                                               |
    |------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    |     <strong>Naam afdeling</strong>     |                                                             Wordt weergegeven wanneer de gebruiker tijdens de activering op <strong>Over configuratie</strong> tikt.                                                              |
    |    <strong>Telefoonnummer van afdeling</strong>     |                                                          Wordt weergegeven wanneer de gebruiker tijdens de activering de knop <strong>Hulp nodig?</strong> klikt.                                                          |
    | <strong>Configuratieassistentopties</strong> |                                                     De volgende instellingen zijn optioneel en kunnen naderhand worden geconfigureerd in het iOS-menu <strong>Instellingen</strong>.                                                      |
    |        <strong>Wachtwoordcode</strong>         | Hiermee wordt tijdens de activering gevraagd om de wachtwoordcode. Vraag altijd om een wachtwoordcode tenzij het apparaat wordt beveiligd of de toegang tot het apparaat op een andere manier wordt beheerd (bijvoorbeeld de kioskmodus waarmee op het apparaat maar één app kan worden uitgevoerd). |
    |    <strong>Locatieservices</strong>    |                                                                 Als deze optie is ingeschakeld, wordt tijdens de activering door Configuratieassistent om de service gevraagd.                                                                  |
    |         <strong>Herstellen</strong>         |                                                                Als deze optie is ingeschakeld, wordt tijdens de activering door Configuratieassistent gevraagd om een iCloud-back-up.                                                                 |
    |   <strong>iCloud en Apple-id</strong>   |                         Als deze optie is ingeschakeld, wordt de gebruiker door de Configuratieassistent gevraagd om zich aan te melden met een Apple-id en kan op het scherm Apps en gegevens het apparaat worden hersteld vanuit de iCloud-back-up.                         |
    |  <strong>Voorwaarden</strong>   |                                                   Als deze optie is ingeschakeld, wordt tijdens de activering door Configuratieassistent gevraagd om de voorwaarden van Apple te accepteren.                                                   |
    |        <strong>Touch-id</strong>         |                                                                 Als deze optie is ingeschakeld, wordt tijdens de activering door Configuratieassistent om deze service gevraagd.                                                                 |
    |        <strong>Apple Pay</strong>        |                                                                 Als deze optie is ingeschakeld, wordt tijdens de activering door Configuratieassistent om deze service gevraagd.                                                                 |
    |          <strong>In- en uitzoomen</strong>           |                                                                 Als deze optie is ingeschakeld, wordt tijdens de activering door Configuratieassistent om deze service gevraagd.                                                                 |
    |          <strong>Siri</strong>           |                                                                 Als deze optie is ingeschakeld, wordt tijdens de activering door Configuratieassistent om deze service gevraagd.                                                                 |
    |     <strong>Diagnostische gegevens</strong>     |                                                                 Als deze optie is ingeschakeld, wordt tijdens de activering door Configuratieassistent om deze service gevraagd.                                                                 |


12. Kies **OK**.

13. Kies **Maken** om een profiel op te slaan.

## <a name="sync-managed-devices"></a>Beheerde apparaten synchroniseren
Nu Intune toestemming heeft om uw apparaten te beheren, kunt u Intune synchroniseren met Apple om uw beheerde apparaten weer te geven in Intune in Azure Portal.

1. Kies in Intune in Azure Portal **Apparaatinschrijving** > **Apple-inschrijving** > **Token voor het inschrijvingsprogramma** > kies een token uit de lijst > **Apparaten** > **Synchroniseren**. ![Schermopname van het geselecteerde knooppunt Apparaten voor het inschrijvingsprogramma en een pijl naar de koppeling Synchroniseren.](./media/device-enrollment-program-enroll-ios/image06.png)

   Om te voldoen aan de voorwaarden van Apple voor acceptabel verkeer van het inschrijvingsprogramma, worden door Intune de volgende beperkingen opgelegd:
   - Een volledige synchronisatie kan niet vaker dan eens in de zeven dagen worden uitgevoerd. Tijdens een volledige synchronisatie haalt Intune de volledige bijgewerkte lijst met serienummers op die is toegewezen aan de Apple MDM-server die is verbonden met Intune. Wanneer een apparaat uit het inschrijvingsprogramma wordt verwijderd uit de Intune-portal zonder dat het eerst is afgemeld bij de Apple MDM-server in de DEP-portal, wordt het apparaat pas opnieuw in Intune geïmporteerd wanneer de volledige synchronisatie wordt uitgevoerd.   
   - Er wordt automatisch elke 24 uur een synchronisatie uitgevoerd. U kunt ook synchroniseren door op de knop **Synchroniseren** te klikken (maximaal één keer per 15 minuten). Synchronisatieaanvragen krijgen 15 minuten de tijd om te worden uitgevoerd. De knop **Synchroniseren** blijft uitgeschakeld totdat de synchronisatie is voltooid. Met de synchronisatie wordt de huidige apparaatstatus vernieuwt en worden nieuwe apparaten die aan de Apple MDM-server zijn toegewezen, geïmporteerd.   


## <a name="assign-an-enrollment-profile-to-devices"></a>Een inschrijvingsprofiel toewijzen aan apparaten
U moet een profiel voor een inschrijvingsprogramma aan apparaten toewijzen voordat deze kunnen worden ingeschreven.

>[!NOTE]
>U kunt ook serienummers aan profielen toewijzen via de blade **Apple-serienummers**.

1. Kies in Intune in Azure Portal **Apparaatinschrijving** > **Apple-inschrijving** > **Token voor het inschrijvingsprogramma** > kies een token uit de lijst.
2. Kies **Apparaten** > kies apparaten uit de lijst > **Profiel toewijzen**.
3. Kies onder **Profiel toewijzen** een profiel voor de apparaten en kies vervolgens **Toewijzen**.

### <a name="assign-a-default-profile"></a>Een standaardprofiel toewijzen

U kunt een standaardprofiel kiezen dat wordt toegepast op apparaten die zich inschrijven met een specifiek token.

1. Kies in Intune in Azure Portal **Apparaatinschrijving** > **Apple-inschrijving** > **Token voor het inschrijvingsprogramma** > kies een token uit de lijst.
2. Kies **Standaardprofiel instellen**, kies een profiel in de vervolgkeuzelijst en kies vervolgens **Opslaan**. Dit profiel wordt toegepast op alle apparaten die zich met het token inschrijven.

## <a name="distribute-devices"></a>Apparaten distribueren
U hebt beheer en synchronisatie tussen Apple en Intune ingeschakeld, en een profiel toegewezen om uw DEP-apparaten te kunnen inschrijven. De apparaten kunnen nu worden uitgedeeld aan de gebruikers. Voor apparaten met gebruikersaffiniteit moet aan elke gebruiker een Intune-licentie worden toegewezen. Voor apparaten zonder gebruikersaffiniteit is een apparaatlicentie vereist. Een geactiveerd apparaat kan geen inschrijvingsprofiel toepassen, tenzij het apparaat is teruggezet naar de fabrieksinstellingen.

Zie [Schrijf uw iOS-apparaat in Intune in met het Device Enrollment Program](/intune-user-help/enroll-your-device-dep-ios).

## <a name="renew-a-dep-token"></a>Een DEP-token vernieuwen  
1. Ga naar deploy.apple.com.  
2. Kies onder **Manage Servers** de MDM-server die is gekoppeld aan het tokenbestand dat u wilt vernieuwen.
3. Kies **Generate New Token**.

    ![Schermopname van nieuw token genereren.](./media/device-enrollment-program-enroll-ios/generatenewtoken.png)

4. Kies **Your Server Token**.  
5. Kies in [Intune in Azure Portal](https://aka.ms/intuneportal), **Apparaatinschrijving** > **Apple-inschrijving** > **Tokens voor het inschrijvingsprogramma** > kies het token.
    ![Schermopname van tokens voor het inschrijvingsprogramma.](./media/device-enrollment-program-enroll-ios/enrollmentprogramtokens.png)

6. Kies **Token vernieuwen** en voer de Apple ID in die is gebruikt om het oorspronkelijke token te maken.  
    ![Schermopname van nieuw token genereren.](./media/device-enrollment-program-enroll-ios/renewtoken.png)

8. Upload het token dat u net hebt gedownload.  
9. Kies **Token vernieuwen**. U krijgt een bevestiging te zien dat het token is vernieuwd.   
    ![Schermopname van de bevestiging.](./media/device-enrollment-program-enroll-ios/confirmation.png)
