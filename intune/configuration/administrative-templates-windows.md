---
title: Sjablonen voor Windows 10-apparaten gebruiken in Microsoft Intune - Azure | Microsoft Docs
description: Gebruik beheersjablonen in Microsoft Intune om groepen instellingen te maken voor Windows 10-apparaten. Gebruik deze instellingen in een apparaatconfiguratieprofiel om Office-programma's en Microsoft Edge te beheren, functies in Internet Explorer te beveiligen, toegang tot OneDrive te beheren, Extern bureaublad-functies te gebruiken, automatisch afspelen in te schakelen, instellingen voor energiebeheer in te stellen, afdrukken via HTTP te gebruiken, verschillende aanmeldingsopties te gebruiken en de grootte van het gebeurtenislogboek te beheren.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/04/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: ca087ec67542102a0cd3111d27a860500b23d3c4
ms.sourcegitcommit: 23e9c48348a6eba494d072a2665b7481e5b5c84e
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/26/2019
ms.locfileid: "74547977"
---
# <a name="use-windows-10-templates-to-configure-group-policy-settings-in-microsoft-intune"></a>Windows 10-sjablonen gebruiken voor het configureren van instellingen voor groepsbeleid in Microsoft Intune

Wanneer u apparaten in uw organisatie beheert, moet u groepen instellingen maken die van toepassing zijn op verschillende apparaatgroepen. Stel dat u beschikt over verschillende apparaatgroepen. Aan GroupA wilt u een specifieke set instellingen toewijzen. Aan GroupB wilt u een andere set instellingen toewijzen. U wilt ook een eenvoudig overzicht verkrijgen van de instellingen die u kunt configureren.

U kunt deze taak uitvoeren met **Beheersjablonen** in Microsoft Intune. De beheersjablonen bevatten honderden instellingen waarmee functies kunnen worden geconfigureerd voor Microsoft Edge (versie 77 en hoger), Internet Explorer, Microsoft Office-programma's, Extern bureaublad, OneDrive, wachtwoorden en pincodes, en nog veel meer. Met deze instellingen kunnen groepsbeheerders groepsbeleid beheren via de cloud.

De Windows-instellingen zijn vergelijkbaar met instellingen voor groepsbeleid (GPO) in Active Directory (AD). Deze instellingen zijn ingebouwd in Windows. Het zijn [door ADMX ondersteunde instellingen](https://docs.microsoft.com/windows/client-management/mdm/understanding-admx-backed-policies) die gebruikmaken van XML. De instellingen voor Office en Microsoft Edge worden door ADMX opgenomen en gebruiken ADMX-instellingen in [Office-bestanden met beheersjablonen](https://www.microsoft.com/download/details.aspx?id=49030) en [Microsoft Edge-bestanden met beheersjablonen](https://www.microsoftedgeinsider.com/enterprise). De Intune-sjablonen zijn echter 100% cloudgebaseerd. Ze bieden een eenvoudige en duidelijke manier om de instellingen te configureren en om de gewenste instellingen te zoeken.

**Beheersjablonen** zijn ingebouwd in Intune en hoeven niet te worden aangepast; dit geldt ook voor het gebruik van de OMA-URI. Gebruik deze sjablooninstellingen als basis voor het beheren van uw Windows 10-apparaten, als onderdeel van uw MDM-oplossing (Mobile Device Management).

In dit artikel vindt u de stappen voor het maken van een sjabloon voor Windows 10-apparaten. U leest hier ook meer over het filteren van de beschikbare instellingen in Intune. Wanneer u de sjabloon maakt, wordt er ook een apparaatconfiguratieprofiel gemaakt. U kunt dit profiel vervolgens toewijzen aan of implementeren op Windows 10-apparaten in uw organisatie.

## <a name="before-you-begin"></a>Voordat u begint

- Sommige van deze instellingen zijn beschikbaar vanaf Windows 10 versie 1703 (RS2). Sommige instellingen zijn niet in alle Windows-edities beschikbaar. Voor de beste ervaring wordt u aangeraden Windows 10 Enterprise versie 1903 (19H1) of nieuwer te gebruiken.

- De Windows-instellingen maken gebruik van [beleids-CSP's voor Windows](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider#policies-supported-by-group-policy-and-admx-backed-policies). De CSP's werken op verschillende edities van Windows zoals Home, Professional, Enterprise enzovoort. Ga naar [Beleids-CSP's voor Windows](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider#policies-supported-by-group-policy-and-admx-backed-policies) om te zien of een bepaalde CSP in een specifieke editie werkt.

## <a name="create-a-template"></a>Een sjabloon maken

1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecteer **Apparaten** > **Configuratieprofielen** > **Profiel maken**.
3. Voer de volgende eigenschappen in:

    - **Naam**: Voer een naam voor het profiel in.
    - **Beschrijving**: Voer een beschrijving in voor het profiel. Deze instelling is optioneel, maar wordt aanbevolen.
    - **Platform**: Kies **Windows 10 en hoger**.
    - **Profieltype**: Selecteer **Beheersjablonen**.

4. Selecteer **Maken**. Selecteer in het nieuwe venster de optie **Instellingen**. Alle instellingen worden vermeld. U kunt de pijlen Vorige/Volgende gebruiken om meer instellingen te bekijken:

    ![Een voorbeeldlijst met instellingen bekijken en de knoppen Vorige en Volgende gebruiken](./media/administrative-templates-windows/administrative-templates-sample-settings-list.png)

    > [!TIP]
    > De Windows-instellingen in Intune correleren met het pad naar het on-premises groepsbeleidsobject dat u ziet in Lokale groepsbeleidsobjecteditor (`gpedit`).

5. Selecteer **Alle producten** in de vervolgkeuzelijst. In de lijst kunt u de instellingen ook filteren om alleen **Windows-instellingen**, alleen **Office-instellingen** of alleen **Edge-instellingen (versie 77 of hoger)** weer te geven:

    ![De lijst filteren om alle Windows- of alle Office-instellingen weer te geven in beheersjablonen in Intune](./media/administrative-templates-windows/administrative-templates-choose-windows-office-all-products.png)

    > [!NOTE]
    > Instellingen voor Microsoft Edge zijn van toepassing op:
    >
    > - Microsoft Edge versie 77 en hoger. Raadpleeg [Apparaatbeperkingsinstellingen voor de Microsoft Edge-browser](device-restrictions-windows-10.md#microsoft-edge-browser) om versie 45 of eerder van Microsoft Edge te configureren.
    > - Windows 10 RS4 en nieuwer waarvoor [KB 4512509](https://support.microsoft.com/kb/4512509) is geïnstalleerd
    > - Windows 10 RS5 en nieuwer waarvoor [KB 4512534](https://support.microsoft.com/kb/4512534) is geïnstalleerd
    > - Windows 10 19H1 en nieuwer waarvoor [KB 4512941](https://support.microsoft.com/kb/4512941) is geïnstalleerd

6. Selecteer een willekeurige instelling. U kunt bijvoorbeeld filteren op **Office** en **Beperkt browsen activeren** selecteren. Er wordt een gedetailleerde beschrijving van de instelling weergegeven. Kies **Ingeschakeld**, **Uitgeschakeld** of laat de instellingen op **Niet geconfigureerd** staan (standaard). In de gedetailleerde beschrijving wordt ook uitgelegd wat er gebeurt wanneer u kiest voor **Ingeschakeld**, **Uitgeschakeld** of **Niet geconfigureerd**.
7. Selecteer **OK** om uw wijzigingen op te slaan.

Doorloop de lijst met instellingen verder en configureer de instellingen die u in uw omgeving wilt gebruiken. Enkele voorbeelden:

- Gebruik de instelling **VBA Macro Notification Settings** (Meldingsinstellingen voor VBA-macro's) om in te stellen hoe in verschillende Microsoft Office-programma's moet worden omgegaan met VBA-macro's, bijvoorbeeld in Word en Excel.
- Gebruik de instelling **Bestand downloaden toestaan** als u wilt toestaan of voorkomen dat er vanuit Internet Explorer wordt gedownload.
- Gebruik **Een wachtwoord vereisen wanneer de computer uit de slaapstand komt (netstroom)** om gebruikers te vragen om een wachtwoord in te voeren wanneer apparaten uit de slaapstand worden gehaald.
- Gebruik de instelling **ActiveX-besturingselementen zonder handtekening downloaden** om te voorkomen dat gebruikers niet-ondertekende ActiveX-besturingselementen downloaden via Internet Explorer.
- Gebruik de instelling **Systeemherstel uitschakelen** om te voorkomen dat gebruikers systeemherstel uitvoeren op het apparaat.
- Gebruik de instelling **Importeren van favorieten toestaan** om toe te staan of te blokkeren dat gebruikers favorieten van een andere browser kunnen importeren in Microsoft Edge.
- En nog veel meer...

## <a name="find-some-settings"></a>Enkele instellingen zoeken

In deze sjablonen zijn honderden verschillende instellingen beschikbaar. Gebruik de volgende ingebouwde functies om het eenvoudiger te maken om specifieke instellingen te zoeken:

- Selecteer in uw sjabloon de kolom **Instellingen**, **Status**, **Instellingstype** of **Pad** om de lijst te sorteren. Selecteer bijvoorbeeld de kolom **Pad** om alle instellingen in het pad `Microsoft Excel` te bekijken:

  ![Klik op Pad om alle instellingen weer te geven die in Intune op groepsbeleid of ADMX-pad in beheersjablonen zijn gegroepeerd](./media/administrative-templates-windows/path-filter-shows-excel-options.png)

- Gebruik in uw sjabloon het vak **Zoeken** om specifieke instellingen te zoeken. U kunt zoeken op instellingsnaam of -pad. Bijvoorbeeld zoeken naar `copy`. Alle instellingen met `copy` worden weergegeven:

  ![Zoeken naar 'copy' om alle Windows- en Office-instellingen in beheersjablonen in Intune weer te geven](./media/administrative-templates-windows/search-copy-settings.png) 

  Zoek in een ander voorbeeld naar `microsoft word`. U ziet alle instellingen die u voor het programma Microsoft Word kunt instellen. Zoek naar `explorer` om te bekijken welke Internet Explorer-instellingen u allemaal aan uw sjabloon kunt toevoegen.

## <a name="next-steps"></a>Volgende stappen

De sjabloon is gemaakt, maar er gebeurt nog niets. De volgende stap is [de sjabloon, ook wel een profiel genoemd, toewijzen](device-profile-assign.md) en [de status ervan bewaken](device-profile-monitor.md).

[Office 365 bijwerken met behulp van beheersjablonen](administrative-templates-update-office.md)
