---
title: iOS-apparaten inschrijven met het programma voor apparaatinschrijving
titlesuffix: Microsoft Intune
description: Meer informatie over het inschrijven van iOS-apparaten in bedrijfseigendom met het Device Enrollment Program (DEP) van Apple.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/08/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 7981a9c0-168e-4c54-9afd-ac51e895042c
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 05b03502a27c244dd665363741f70a695f8e945b
ms.sourcegitcommit: a22309174e617e59ab0cdd0a55abde38711a5f35
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2018
---
# <a name="automatically-enroll-ios-devices-by-using-apples-device-enrollment-program"></a>iOS-apparaten automatisch inschrijven met het Device Enrollment Program van Apple

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

> [!NOTE]
> ### <a name="temporary-user-interface-differences"></a>Tijdelijke verschillen in de gebruikersinterface
>
>De gebruikersinterfaces voor de functies die op deze pagina worden beschreven, worden op dit moment bijgewerkt. Deze updates moeten tegen het einde van april in alle gebruikersaccounts zijn geïmplementeerd.
>
>Als uw pagina **Apparaatinschrijving** niet op de onderstaande afbeelding lijkt, is uw account nog niet bijgewerkt naar de nieuwe gebruikersinterface en kunt u deze Help-pagina gebruiken.
>
>![Oude Intune-gebruikersinterface](./media/appleenroll-oldui.png)
>
>Als uw pagina **Apparaatinschrijving** op de onderstaande afbeelding lijkt, beschikt u over de bijgewerkte gebruikersinterfaces.  Ga dan naar [deze Help-pagina](device-enrollment-program-enroll-ios-newui.md).
>
>![Nieuwe Intune-gebruikersinterface](./media/appleenroll-newui.png)

Met de informatie in dit onderwerp kunt u iOS-apparaten inschrijven die zijn gekocht via het [Device Enrollment Program (DEP)](https://deploy.apple.com) van Apple. U kunt inschrijving met DEP voor grote aantallen apparaten inschakelen zonder dat u ze hoeft aan te raken. U kunt deze apparaten rechtstreeks naar de gebruikers verzenden, net als iPhones en iPads. Als de gebruiker het apparaat inschakelt, wordt Configuratieassistent uitgevoerd met vooraf gedefinieerde instellingen en het apparaat ingeschreven bij beheer.

Voor het inschakelen van DEP-inschrijving moet u zowel de Intune-portal als de Apple DEP-portal gebruiken. U hebt een lijst met serienummers of een aankoopordernummer nodig om apparaten voor beheer aan Intune toe te wijzen. U maakt DEP-inschrijvingsprofielen met instellingen die tijdens de inschrijving op de apparaten van toepassing zijn geweest.

DEP-inschrijving werkt niet met de [apparaatinschrijvingsmanager](device-enrollment-manager-enroll.md). Daarnaast biedt MacOS op dit moment geen ondersteuning voor DEP.

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

> [!NOTE]
> Multi-Factor Authentication (MFA) werkt niet tijdens instellen DEP-inschrijving voor gebruikersaffiniteit. Na de inschrijving werkt MFA zoals verwacht op apparaten. Op apparaten wordt de gebruiker niet gevraagd het wachtwoord te wijzigen als ze zich de eerste keer aanmelden. Daarnaast wordt gebruikers met verlopen wachtwoorden niet gevraagd hun wachtwoord opnieuw in te stellen tijdens de inschrijving. Deze gebruikers moeten het wachtwoord vanaf een ander apparaat opnieuw instellen.

## <a name="get-the-apple-dep-token"></a>Het Apple DEP-token ophalen

Voordat u iOS-apparaten met DEP kunt inschrijven, moet u een DEP-tokenbestand (.p7m) van Apple ontvangen. Intune kan met deze token informatie synchroniseren over DEP-apparaten die in eigendom zijn van uw bedrijf. Ook kan Intune hiermee inschrijvingsprofielen naar Apple uploaden en apparaten toewijzen aan die profielen.

U gebruikt de Apple DEP-portal om een DEP-token te maken. U gebruikt de DEP-portal ook om apparaten aan Intune toe te wijzen voor beheer.

> [!NOTE]
> In Intune kan een verwijderd Apple DEP-token worden hersteld, als u de token van de klassieke Intune-portal verwijdert voordat u naar Azure migreert. U kunt het DEP-token opnieuw verwijderen uit Azure Portal verwijderen. U kunt het DEP-token opnieuw verwijderen uit Azure Portal verwijderen.

**Stap 1. Download een openbare-sleutelcertificaat van Intune dat is vereist voor het maken van een Apple DEP-token.**<br>

1. Kies in [Intune in Azure Portal](https://aka.ms/intuneportal) achtereenvolgens **Apparaatinschrijving** > **Apple-inschrijving** > **Token voor het inschrijvingsprogramma**.

  ![Het deelvenster Token voor het inschrijvingsprogramma in de werkruimte Apple-certificaten](./media/enrollment-program-token-add.png)

2. Kies **Uw openbare-sleutelcertificaat downloaden** en sla het bestand met de versleutelingssleutel (.pem) lokaal op. Het .pem-bestand wordt gebruikt om een vertrouwensrelatiecertificaat bij de portal Apple Device Enrollment Program aan te vragen.

  ![Het deelvenster Token voor het inschrijvingsprogramma in de werkruimte Apple-certificaten voor het downloaden van de openbare sleutel](./media/enrollment-program-token-download.png)

**Stap 2. Maak en download een Apple DEP-token.**<br>
1. Kies **Een token via Apple Device Enrollment Program maken** om de Deployment Program-portal van Apple te openen en meld u aan met uw Apple-id. Deze Apple-id kunt u gebruiken om uw DEP-token te verlengen.
2.  Kies **Aan de slag** bij **Device Enrollment Program** in de [Deployment Programs-portal](https://deploy.apple.com) van Apple.

3. Kies **MDM-server toevoegen** op de pagina **Servers beheren**.
4. Voer de **MDM-servernaam** in en kies **Volgende**. De servernaam is voor eigen referentie en dient om de MDM-server te identificeren. Het is niet de naam of URL van de Microsoft Intune-server.

   ![Een MDM-servernaam voor DEP toevoegen en klikken op Volgende](./media/enrollment-program-token-add-server.png)

5. Het dialoogvenster **Voeg &lt;servernaam&gt;** wordt geopend, met de instructie dat u uw **openbare sleutel moet uploaden**. Kies **Bestand selecteren...** om het .pem-bestand te uploaden en kies **Volgende**.  

6. Ga naar **Deployment Programs** &gt; **Device Enrollment Program** &gt; **Apparaten beheren**.
7. Geef onder **Kies apparaten op** aan hoe apparaten worden geïdentificeerd:
    - **Serienummer**
    - **Ordernummer**
    - **CSV-bestand uploaden**

   ![Het opgeven van apparaten kiezen op serienummer, het instellen van een actie kiezen zoals toewijzen aan server en de naam van de server selecteren](./media/enrollment-program-token-specify-serial.png)

8. Voor **Kies actie** kiest u **Toewijzen aan server**, kiest u de &lt;Servernaam&gt; die is opgegeven voor Microsoft Intune en kiest u vervolgens **OK**. De opgegeven apparaten worden voor beheer toegewezen aan de Intune-server en er verschijnt een melding dat de **toewijzing is voltooid**.

   Ga in de Apple-portal **Deployment Programs** &gt; **Device Enrollment Program** &gt; **Toewijzingsgeschiedenis weergeven** om een lijst van apparaten en hun toewijzing aan de MDM-server te bekijken.

**Stap 3. Voer de Apple ID in die u hebt gebruikt om het token voor het inschrijvingsprogramma te maken.**<br>Voer in Intune in de Apple-portal de Apple-id in, zodat u deze altijd kunt terugvinden.

![De Apple-id invoeren die is gebruikt voor het maken van het token voor het inschrijvingsprogramma en het uploaden van het token](./media/enrollment-program-token-apple-id.png)

**Stap 4. Blader naar het token voor het inschrijvingsprogramma om dit te uploaden.**<br>
Ga naar het certificaatbestand (.pem), kies **Openen** en kies vervolgens **Uploaden**. Met het pushcertificaat kan Intune iOS-apparaten inschrijven en beheren door beleid naar geregistreerde mobiele apparaten te pushen. Intune wordt automatisch gesynchroniseerd met Apple om het account voor het inschrijvingsprogramma weer te geven.

## <a name="create-an-apple-enrollment-profile"></a>Een Apple-inschrijvingsprofiel maken

Na installatie van de token kunt u een inschrijvingsprofiel voor DEP-apparaten maken. Met een inschrijvingsprofiel voor apparaten worden de instellingen gedefinieerd die worden toegepast op een groep apparaten tijdens de inschrijving.

1. Kies in [Intune in Azure Portal](https://aka.ms/intuneportal) achtereenvolgens **Apparaatinschrijving** > **Apple-inschrijving**.
2. Kies onder **Inschrijvingsprogramma van Apple** de opties **Profielen voor het inschrijvingsprogramma** > **Maken**.
3. Voer bij **Inschrijvingsprofiel maken** een **naam** en een **beschrijving** voor het profiel in voor administratieve doeleinden. Gebruikers zien deze gegevens niet. U kunt dit veld **Naam** gebruiken om een dynamische groep te maken in Azure Active Directory. Gebruik de profielnaam om de parameter enrollmentProfileName te definiëren om apparaten aan dit inschrijvingsprofiel toe te wijzen. Meer informatie over [Azure Active Directory dynamic groups](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal#using-attributes-to-create-rules-for-device-objects) (dynamische Azure Active Directory-groepen).

  Geef voor **Gebruikersaffiniteit** aan of u andere apparaten met dit profiel wilt inschrijven met of zonder toegewezen gebruiker.

 - **Inschrijven met gebruikersaffiniteit**: kies deze optie voor apparaten die eigendom zijn van gebruikers en waarvoor de bedrijfsportal moet worden gebruikt voor services als het installeren van apps. Gebruikersaffiniteit vereist [WS-Trust 1.3 gebruikersnaam/gemengd eindpunt](https://technet.microsoft.com/library/adfs2-help-endpoints). [Meer informatie](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint).

 - **Inschrijven zonder gebruikersaffiniteit**: kies deze optie voor een apparaat dat niet aan één gebruiker is gelieerd. Gebruikt voor apparaten waarmee taken worden uitgevoerd zonder toegang tot lokale gebruikersgegevens. Apps als de bedrijfsportal-app werken niet.

4. Kies **Instellingen voor apparaatbeheer** om de volgende profielinstellingen te configureren:

  ![De beheermodus kiezen](./media/enrollment-program-profile-mode.png)
  - **Onder supervisie**: een beheermodus waarmee standaard meer beheeropties worden ingeschakeld en de activeringsvergrendeling wordt uitgeschakeld. Als u het selectievakje leeg laat, hebt u beperkte beheermogelijkheden. Microsoft raadt het gebruik van DEP aan als mechanisme voor het inschakelen van de supervisiemodus, met name voor organisaties die veel iOS-apparaten implementeren.

 > [!NOTE]
 > Een apparaat kan niet worden geconfigureerd voor de supervisiemodus met behulp van Intune nadat een apparaat is geregistreerd. Na de registratie kan de supervisiemodus alleen worden ingeschakeld door een iOS-apparaat op een Mac aan te sluiten met een USB-kabel en Apple Configurator te gebruiken. Hierdoor wordt het apparaat opnieuw ingesteld en geconfigureerd in de supervisiemodus. Meer informatie hierover vindt u in de [Apple Configurator-documentatie](http://help.apple.com/configurator/mac/2.3). Bij een apparaat onder supervisie ziet u 'Deze iPhone wordt beheerd door Contoso'. op het vergrendelingsscherm en 'Deze iPhone is onder supervisie. Contoso kan uw internetverkeer bijhouden en de locatie van dit apparaat bepalen'. in **Instellingen** > **Algemeen** > **Info**.

  - **Vergrendelde registratie** (hiervoor is Onder supervisie als beheermodus vereist): hiermee worden de iOS-instellingen uitgeschakeld waarmee het beheerprofiel kan worden verwijderd. Als u dit selectievakje leeg laat, kan het beheerprofiel uit het menu Instellingen worden verwijderd. Als het apparaat is ingeschreven, kunt u deze instelling niet wijzigen zonder het apparaat terug te zetten naar de fabrieksinstellingen.

  - **Gedeelde iPad ingeschakeld**: het Device Enrollment Program van Apple ondersteunt het gebruik van gedeelde iPad niet.

  - **Koppelen toestaan**: hiermee wordt aangegeven of iOS-apparaten kunnen worden gesynchroniseerd met computers. Als u **Apple Configurator per certificaat toestaan** kiest, moet u een certificaat kiezen onder **Apple Configurator-certificaten**.

  - **Apple Configurator-certificaten**: als u **Apple Configurator per certificaat toestaan** onder **Koppelen toestaan** hebt gekozen, kiest u het Apple Configurator-certificaat dat u wilt importeren.

  Kies **Opslaan**.

5. Kies **Instellingen voor Configuratieassistent** om de volgende profielinstellingen te configureren:

  ![Instellingen configureren kiezen met de beschikbare instellingen voor een nieuw profiel voor het inschrijvingsprogramma](./media/enrollment-program-profile-settings.png)
  - **Naam van afdeling**: wordt weergegeven wanneer gebruikers tijdens de activering op **Over configuratie** tikken.

  - **Telefoonnummer van afdeling**: wordt weergegeven wanneer de gebruiker tijdens de activering de knop **Hulp nodig?** klikt.
    - **Configuratieassistentopties**: deze instellingen zijn optioneel en kunnen naderhand worden geconfigureerd in het iOS-menu **Instellingen**.
        - **Wachtwoordcode**
        - **Locatieservices**
        - **Herstellen**
        - **Apple-id**
        - **Voorwaarden**
        - **Touch-id**
        - **Apple Pay**
        - **In- en uitzoomen**
        - **Siri**
        - **Diagnostische gegevens**

    Kies **Opslaan**.

9. Kies **Maken** op de blade **Inschrijvingsprofiel maken** om de profielinstellingen op te slaan. Het inschrijvingsprofiel wordt weergegeven in de lijst met inschrijvingsprofielen voor Apple Enrollment Program.

## <a name="sync-managed-devices"></a>Beheerde apparaten synchroniseren
Nu Intune toestemming heeft om uw apparaten te beheren, kunt u Intune synchroniseren met Apple om uw beheerde apparaten weer te geven in Intune in Azure Portal.

1. Kies in [Intune in Azure Portal](https://aka.ms/intuneportal) achtereenvolgens **Apparaatinschrijving** > **Apple-inschrijving** > **Apparaten voor het inschrijvingsprogramma** > **Synchroniseren**. Op de voortgangsbalk wordt aangegeven hoe lang u moet wachten voordat u opnieuw synchronisatie kunt aanvragen.

  ![Het geselecteerde knooppunt Apparaten voor het inschrijvingsprogramma en de koppeling Synchroniseren die wordt gekozen](./media/enrollment-program-device-sync.png)

2. Kies **Synchronisatie aanvragen** op de blade **Synchroniseren**. Op de voortgangsbalk wordt aangegeven hoe lang u moet wachten voordat u opnieuw synchronisatie kunt aanvragen.

   ![De blade Synchroniseren met de koppeling Synchronisatie aanvragen die is geselecteerd](./media/enrollment-program-device-request-sync.png)

   Om te voldoen aan de voorwaarden van Apple voor acceptabel verkeer van het inschrijvingsprogramma, worden door Intune de volgende beperkingen opgelegd:
     -  Een volledige synchronisatie kan niet vaker dan eens in de zeven dagen worden uitgevoerd. Tijdens volledige synchronisatie wordt elk Apple-serienummer vernieuwd dat aan Intune is toegewezen. Als een volledige synchronisatie wordt uitgevoerd binnen zeven dagen na de vorige volledige synchronisatie, vernieuwt Intune alleen serienummers die nog niet aanwezig zijn in Intune.
     -  Een synchronisatieaanvraag krijgt 15 minuten de tijd om te worden uitgevoerd. Gedurende deze tijd of totdat de aanvraag is geslaagd, is de knop **Synchronisatie** uitgeschakeld.
     - Intune synchroniseert elke 24 uur nieuwe en verwijderde apparaten met Apple.

3. Kies in de werkruimte Apparaten voor het inschrijvingsprogramma **Vernieuwen** om uw apparaten weer te geven.

## <a name="assign-an-enrollment-profile-to-devices"></a>Een inschrijvingsprofiel toewijzen aan apparaten
U moet een profiel voor een inschrijvingsprogramma aan apparaten toewijzen voordat deze kunnen worden ingeschreven.

>[!NOTE]
>U kunt ook serienummers aan profielen toewijzen via de blade **Apple-serienummers**.

1. Kies in [Intune in Azure Portal](https://aka.ms/intuneportal) achtereenvolgens **Apparaatinschrijving** > **Apple-inschrijving** en kies vervolgens **Profielen voor het inschrijvingsprogramma**.
2. Kies in de lijst **Profielen voor het inschrijvingsprogramma** het profiel dat u wilt toewijzen aan apparaten en kies vervolgens **Apparaten toewijzen**.

 ![Apparaattoewijzingen met Toewijzen geselecteerd](./media/enrollment-program-device-assign.png)

3. Kies **Toewijzen** en kies vervolgens de apparaten die u aan dit profiel wilt toewijzen. U kunt filteren om beschikbare apparaten weer te geven:
  - **niet-toegewezen**
  - **alle**
  - **&lt;profielnaam&gt;**
4. Kies de apparaten die u wilt toewijzen. Met het selectievakje boven de kolom selecteert u tot 1000 apparaten in de lijst. Klik vervolgens op **Toewijzen**. Als u meer dan 1000 apparaten wilt registreren, herhaalt u de stappen voor toewijzing totdat aan alle apparaten een inschrijvingsprofiel is toegewezen.

  ![De knop Toewijzen voor het toewijzen van een profiel voor het inschrijvingsprogramma in Intune](media/dep-profile-assignment.png)

## <a name="distribute-devices"></a>Apparaten distribueren
U hebt beheer en synchronisatie tussen Apple en Intune ingeschakeld, en een profiel toegewezen om uw DEP-apparaten te kunnen inschrijven. De apparaten kunnen nu worden uitgedeeld aan de gebruikers. Voor apparaten met gebruikersaffiniteit moet aan elke gebruiker een Intune-licentie worden toegewezen. Voor apparaten zonder gebruikersaffiniteit is een apparaatlicentie vereist. Een geactiveerd apparaat kan geen inschrijvingsprofiel toepassen, tenzij het apparaat is teruggezet naar de fabrieksinstellingen.

Zie [Schrijf uw iOS-apparaat in Intune in met het Device Enrollment Program](/intune-user-help/enroll-your-device-dep-ios).
