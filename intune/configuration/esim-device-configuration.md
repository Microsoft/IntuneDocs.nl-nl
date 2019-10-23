---
title: eSIM-gegevensverbindingen inschakelen in Microsoft Intune - Azure | Microsoft Docs
description: Voeg eSIM toe of maak er gebruik van om toegang tot internet en gegevens te verkrijgen met verschillende data-abonnementen. In Intune kunt u activeringscodes toevoegen of importeren en deze daarna toewijzen via een configuratieprofiel. U kunt hier ook de eSIM-profielen controleren en de status van apparaten met eSIM controleren.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 7/31/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 84103c6264431773ab5928f1da22c37a80cc9036
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/16/2019
ms.locfileid: "72492706"
---
# <a name="configure-esim-cellular-profiles-in-intune---public-preview"></a>Mobiele eSIM-profielen configureren in Intune - Openbare preview

Een eSIM is een ingesloten SIM-chip. U kunt hiermee verbinding maken met internet via een mobiele dataverbinding op een met eSIM compatibel apparaat, zoals de [Surface LTE Pro](https://www.microsoft.com/surface/business/surface-pro). Met een eSIM hebt u geen SIM-kaart van uw mobiele provider meer nodig. Als wereldreiziger hoeft u dan alleen nog maar te schakelen tussen mobiele providers en gegevensabonnementen om altijd online te blijven.

Dit is handig als u bijvoorbeeld een data-abonnement hebt voor het werk en u bij een andere provider bent aangesloten voor persoonlijk gebruik. Als u onderweg bent, kunt u gebruikmaken van internet door in die regio te zoeken naar providers met beschikbare data-abonnementen.

U kunt in Intune eenmalig te gebruiken activeringscodes importeren die door uw provider zijn aangeleverd. Als u in de eSIM-module data-abonnementen wilt configureren, implementeert u de activeringscodes op uw met eSIM compatibele apparaten. Wanneer via Intune een activeringscode is geïnstalleerd, maakt de eSIM-hardwaremodule gebruik van de gegevens die zijn gekoppeld aan de activeringscode om contact op te nemen met de provider. Wanneer dit is gebeurd, wordt het eSIM-profiel naar het apparaat gedownload en geconfigureerd voor mobiele activering.

Als u met Intune een eSIM wilt implementeren op uw apparaten, hebt u het volgende nodig:

- **Apparaten met eSIM-mogelijkheden**, zoals de Surface LTE: Zie [of uw apparaat ondersteuning biedt voor eSIM](https://support.microsoft.com/help/4020763/windows-10-use-esim-for-cellular-data). U kunt ook een lijst bekijken van [enkele apparaten waarvan bekend is dat ze met eSIM compatibel zijn](#esim-capable-devices) (in dit artikel).
- **Pc’s met Windows 10 Fall Creators Update** (1709 of hoger) die zijn geregistreerd en waarvoor MDM van Intune wordt gebruikt
- **Activeringscodes** aangeleverd door uw provider. De eenmalig te gebruiken activeringscodes worden aan Intune toegevoegd en geïmplementeerd op uw met eSIM compatibele apparaten. Neem contact op met uw provider om eSIM-activeringscodes te verkrijgen.

## <a name="deploy-esim-to-devices---overview"></a>eSIM implementeren op apparaten - Overzicht

Als u eSIM wilt implementeren op apparaten, moet een beheerder de volgende taken uitvoeren:

1. Activeringscodes importeren die zijn aangeleverd door uw provider
2. Een Azure Active Directory-apparaatgroep (Azure AD) maken die uw eSIM-apparaten omvat
3. De Azure AD-groep toewijzen aan uw groep geïmporteerde abonnementen
4. De implementatie controleren

Dit artikel bevat informatie over deze stappen.

## <a name="esim-capable-devices"></a>Voor eSIM geschikte apparaten

De volgende apparaten zijn geschikt voor eSIM en zijn momenteel verkrijgbaar. Controleer ook of [uw apparaat ondersteuning biedt voor eSIM](https://support.microsoft.com/help/4020763/windows-10-use-esim-for-cellular-data).

- Acer Swift 7
- Asus NovoGo TP370QL
- Asus TP401
- Asus Transformer Mini T103
- HP Elitebook G5
- HP Envy x2
- HP Probook G5
- Lenovo Miix 630
- Lenovo T480
- Samsung Galaxy Book
- Surface Pro LTE
- HP Spectre Folio 13
- Lenovo Yoga C630

## <a name="step-1-add-cellular-activation-codes"></a>Stap 1: Activeringscodes voor mobiele apparaten toevoegen

De activeringscodes voor mobiele apparaten worden door uw provider aangeleverd in een CSV-bestand. Wanneer u over het bestand beschikt, voegt u het als volgt toe aan Intune:

1. Meld u aan bij [Azure Portal](https://portal.azure.com/).
2. Selecteer **Alle services**, filter op **Intune** en selecteer **Microsoft Intune**.
3. Selecteer **Apparaatconfiguratie** > **Mobiele eSIM-profielen** > **Toevoegen**.
4. Selecteer het CSV-bestand dat uw activeringscodes bevat.
5. Selecteer **OK** om uw wijzigingen op te slaan.

### <a name="csv-file-requirements"></a>Vereisten voor het CSV-bestand

Als u met een CSV-bestand met activeringscodes werkt, controleert u of uw provider zich aan de volgende vereisten heeft gehouden:

- Het bestand moet de CSV-indeling hebben (bestandsnaam.csv).
- Het bestand moet op een specifieke manier zijn ingedeeld. Als dit niet het geval is, mislukt het importeren. Intune controleert het bestand tijdens het importeren. Het importeren mislukt als er fouten worden gevonden.
- Activeringscodes worden één keer gebruikt. Het is niet raadzaam om activeringscodes te importeren die u al eerder hebt geïmporteerd; dit kan tot problemen leiden wanneer u importeert op hetzelfde of op een ander apparaat.
- Elk bestand moet specifiek voor één provider zijn. Alle activeringscodes moeten daarnaast voor hetzelfde abonnement gelden. Intune verdeelt de activeringscodes willekeurig onder de doelapparaten. Het is niet mogelijk aan te geven welk apparaat een bepaalde activeringscode zal ontvangen.
- Er kunnen met één CSV-bestand maximaal 1000 activeringscodes worden geïmporteerd.

### <a name="csv-file-example"></a>Voorbeeld van een CSV-bestand

1. De eerste rij en eerste cel van het CSV-bestand bevat de URL van de eSIM-activeringsservice van de provider. Deze heet SM-DP+ (Subscription Manager Data Preparation-server). De URL moet een Fully Qualified Domain Name (FQDN) zijn zonder komma's.
2. De tweede en daarop volgende rijen bevatten unieke, eenmalig te gebruiken activeringscodes met twee waarden:

    1. De eerste kolom bevat de unieke ICCID (de id van de SIM-chip)
    2. Tweede kolom bevat de overeenkomst-id's, door komma's gescheiden (geen komma aan het einde). Zie het volgende voorbeeld:

        ![CSV-voorbeeldbestand met activeringscodes van een provider](./media/esim-device-configuration/url-activation-code-examples.png)

3. De naam van het CSV-bestand wordt de naam van de mobiele-abonnementsgroep in Azure Portal. In de voorgaande afbeelding is de bestandsnaam `UnlimitedDataSkynet.csv`. In Intune heet de abonnementsgroep dus `UnlimitedDataSkynet.csv`:

    ![De mobiele-abonnementsgroep krijgt de naam van het CSV-voorbeeldbestand met activeringscodes](./media/esim-device-configuration/subscription-pool-name-csv-file.png)

## <a name="step-2-create-an-azure-ad-device-group"></a>Stap 2: Een Azure AD-apparaatgroep maken

Maak een apparaatgroep die de voor eSIM geschikte apparaten bevat. In [Groepen toevoegen](../fundamentals/groups-add.md) staat hoe u dit doet.

> [!NOTE]
> - eSIM wordt gebruikt voor bepaalde apparaten en niet voor bepaalde personen.
> - Het wordt aanbevolen om een statische Azure AD-apparaatgroep te maken met daarin uw eSIM-apparaten. Als u een groep gebruikt, weet u zeker dat u zich alleen op eSIM-apparaten richt.

## <a name="step-3-assign-esim-activation-codes-to-devices"></a>Stap 3: eSIM-activeringscodes toewijzen aan apparaten

Wijs het profiel toe aan de Azure AD-groep die uw eSIM-apparaten bevat.

1. Selecteer in [Azure Portal](https://portal.azure.com/) **Alle services**, filter op **Intune** en selecteer **Microsoft Intune**.
2. Selecteer **Apparaatconfiguratie** > **Mobiele eSIM-profielen** > **Profielen**.
3. In de lijst met profielen selecteert u de mobiele eSIM-abonnementsgroep die u wilt toewijzen en selecteert u vervolgens **Toewijzingen**.
4. Geef aan of u groepen wilt **opnemen** of **uitsluiten** en selecteer vervolgens de gewenste groepen.

    ![Een apparaatgroep opnemen voor het toewijzen van het profiel](./media/esim-device-configuration/include-exclude-groups.png)

5. Wanneer u uw groepen hebt geselecteerd, kiest u een Azure AD-groep. Als u meerdere groepen wilt selecteren, houdt u de toets **Ctrl** ingedrukt en klikt u op de groepen.
6. Wanneer u klaar bent, klikt u op **Opslaan** om de wijzigingen op te slaan.

eSIM-activeringscodes worden één keer gebruikt. Wanneer Intune een activeringscode heeft geïnstalleerd op een apparaat neemt de eSIM-module contact op met de provider om het mobiele profiel te downloaden. Hiermee wordt de registratie van het apparaat bij het netwerk van de provider voltooid.

## <a name="step-4-monitor-deployment"></a>Stap 4: Implementatie controleren

### <a name="review-the-deployment-status"></a>De implementatiestatus controleren

Wanneer u het profiel hebt toegewezen, kunt u de implementatiestatus van een abonnementsgroep controleren.

1. Meld u aan bij [Azure Portal](https://portal.azure.com/).
2. Selecteer **Alle services**, filter op **Intune** en selecteer **Microsoft Intune**.
3. Selecteer **Apparaatconfiguratie** > **Mobiele eSIM-profielen**. Al uw bestaande mobiele eSIM-abonnementsgroepen worden weergegeven.
4. Selecteer een abonnement en bekijk de **implementatiestatus**.

### <a name="check-the-profile-status"></a>De profielstatus controleren
Nadat u een apparaatprofiel hebt gemaakt, biedt Intune grafieken. In deze grafieken wordt de status van een profiel weergegeven, zoals of het is toegewezen aan apparaten en of op het apparaat een conflict bestaat.

1. Selecteer **Apparaatconfiguratie** > **Mobiele eSIM-profielen** > selecteer een bestaand abonnement.
2. Op het tabblad **Overzicht** ziet u in de bovenste grafiek hoeveel apparaten er zijn toegewezen aan een specifieke geïmplementeerde mobiele eSIM-abonnementsgroep.

    De grafiek geeft ook voor andere platforms het aantal apparaten weer dat is toegewezen aan hetzelfde apparaatprofiel.

    Intune toont de leverings- en installatiestatus van de activeringscode die u voor apparaten wilt gebruiken.

    - **Apparaat niet gesynchroniseerd**: Het doelapparaat heeft nog geen contact opgenomen met Intune sinds het maken van het eSIM-implementatiebeleid
    - **Activering in behandeling**: Een tijdelijke status wanneer Intune bezig is met het installeren van de activeringscode op het apparaat
    - **Actief**: Het installeren van de activeringscode is voltooid
    - **Activering mislukt**: Het installeren van de activeringscode is mislukt. Zie de handleiding voor probleemoplossing.

#### <a name="view-the-detailed-device-status"></a>De gedetailleerde apparaatstatus weergeven

U kunt een gedetailleerde lijst met de apparaten uit Apparaatstatus controleren en bekijken.**

1. Selecteer **Apparaatconfiguratie** > **Mobiele eSIM-profielen** > selecteer een bestaand abonnement.
2. Selecteer **Apparaatstatus**. Intune bevat aanvullende informatie over het apparaat:

    - **Apparaatnaam**: De naam van het doelapparaat
    - **Gebruiker**: De gebruiker van het geregistreerde apparaat
    - **ICCID**: De unieke code die door de provider wordt geleverd. Deze maakt deel uit van de activeringscode die op het apparaat wordt geïnstalleerd
    - **Activeringsstatus**: De Intune-leverings- en installatiestatus van de activeringscode op het apparaat
    - **Mobiele status**: De status die is opgegeven door de mobiele provider. Neem contact op met de provider om mogelijke problemen op te lossen.
    - **Laatste check-in**: De datum waarop het apparaat het laatst met Intune heeft gecommuniceerd

### <a name="monitor-esim-profile-details-on-the-actual-device"></a>De eSIM-profielgegevens op het apparaat zelf controleren

1. Ga op uw apparaat naar **Instellingen** > **Netwerk en internet**.
2. Selecteer **Mobiel** > **eSIM-profielen beheren**
3. De eSIM-profielen worden weergegeven:

    ![De eSIM-profielen bekijken in uw apparaatinstellingen](./media/esim-device-configuration/device-settings-cellular-profiles.png)

## <a name="remove-the-esim-profile-from-device"></a>Het eSIM-profiel van het apparaat verwijderen

Als u het apparaat uit de Azure AD-groep verwijdert, wordt het eSIM-profiel ook verwijderd. Doe het volgende:

1. Controleer of u de Azure AD-groep van de eSIM-apparaten gebruikt.
2. Ga naar de Azure AD-groep en verwijder het apparaat uit de groep.
3. Wanneer het verwijderde apparaat contact opneemt met Intune, wordt het bijgewerkte beleid gecontroleerd en het eSIM-profiel verwijderd.

Het eSIM-profiel wordt ook verwijderd wanneer het apparaat [buiten gebruik wordt gesteld](../remote-actions/devices-wipe.md#retire) door de gebruiker of de registratie van het apparaat ongedaan wordt gemaakt, of wanneer de [externe actie apparaat opnieuw instellen](../remote-actions/devices-wipe.md#wipe) wordt uitgevoerd op het apparaat.

> [!NOTE]
> Als het profiel is verwijderd, worden er mogelijk nog steeds kosten in rekening gebracht. Neem contact op met uw provider om de factureringsstatus van uw apparaat op te vragen.

## <a name="best-practices--troubleshooting"></a>Best practices en probleemoplossing

- Zorg ervoor dat uw CSV-bestand correct is ingedeeld. Controleer of het bestand dubbele codes bevat, meerdere providers bevat en verschillende data-abonnementen bevat. Deze mogen niet aanwezig zijn. Elk bestand moet dienen voor één provider en één mobiel data-abonnement.
- Maak een statische Azure AD-groep die alleen de eSIM-doelapparaten bevat.
- Als er een probleem is met de implementatiestatus, controleert u de volgende zaken:
  - **Onjuiste bestandsindeling**: Zie **Stap 1: Activeringscodes voor mobiele apparaten toevoegen** (in dit artikel) over het indelen van het bestand.
  - **Fout bij mobiele activering, neem contact op met de mobiele provider**: De activeringscode wordt mogelijk niet geactiveerd binnen hun netwerk. Het kan ook zijn dat het downloaden van het profiel én de mobiele activering zijn mislukt.

## <a name="next-steps"></a>Volgende stappen
[Apparaatprofielen configureren](../device-profiles.md)
