---
title: Sjablonen voor Windows 10-apparaten gebruiken in Microsoft Intune - Azure | Microsoft Docs
description: Gebruik beheersjablonen in Microsoft Intune om groepen instellingen te maken voor Windows 10-apparaten. Gebruik deze instellingen in een apparaatconfiguratieprofiel om Office-programma's te beheren, functies in Internet Explorer te beveiligen, toegang tot OneDrive te beheren, Extern bureaublad-functies te gebruiken, automatisch afspelen in te schakelen, instellingen voor energiebeheer in te stellen, afdrukken via HTTP te gebruiken, verschillende opties voor aanmelden te gebruiken en de grootte van het gebeurtenislogboek te beheren.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/27/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9309b110d37795f840e10f22b71b06507aea4c62
ms.sourcegitcommit: 78ae22b1a7cb221648fc7346db751269d9c898b1
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/29/2019
ms.locfileid: "66373728"
---
# <a name="use-windows-10-templates-to-configure-group-policy-settings-in-microsoft-intune"></a>Windows 10-sjablonen gebruiken voor het configureren van instellingen voor groepsbeleid in Microsoft Intune

Wanneer u apparaten in uw organisatie beheert, moet u een groep instellingen maken die wordt toegepast op verschillende apparaatgroepen. Stel dat u beschikt over verschillende apparaatgroepen. Aan GroupA wilt u een specifieke set instellingen toewijzen. Aan GroupB wilt u een andere set instellingen toewijzen. U wilt ook een eenvoudig overzicht verkrijgen van de instellingen die u kunt configureren.

U kunt deze taak uitvoeren met **Beheersjablonen** in Microsoft Intune. De beheersjablonen bevatten honderden instellingen waarmee functies kunnen worden geconfigureerd voor Internet Explorer, Microsoft Office-programma's, Extern bureaublad, toegang tot OneDrive, het gebruik van een afbeeldingswachtwoord of een pincode voor aanmelding en nog veel meer. Deze sjablonen zijn vergelijkbaar met instellingen voor groepsbeleid (GPO) in Active Directory (AD) en zijn [door ADMX ondersteunde instellingen](https://docs.microsoft.com/windows/client-management/mdm/understanding-admx-backed-policies) (hiermee opent u een andere Docs-site) waarbij gebruik wordt gemaakt van XML. De sjablonen in Intune zijn echter 100% cloudgebaseerd. De instellingen in deze sjablonen kunnen eenvoudiger worden geconfigureerd en het is eenvoudiger om de gewenste instellingen te zoeken.

**Beheersjablonen** zijn ingebouwd in Intune en hoeven niet te worden aangepast; dit geldt ook voor het gebruik van de OMA-URI. Gebruik deze sjablooninstellingen als basis voor het beheren van uw Windows 10-apparaten, als onderdeel van uw MDM-oplossing (Mobile Device Management).

In dit artikel staan de stappen voor het maken van een sjabloon voor Windows 10-apparaten. U leest hier ook meer over het filteren van de beschikbare instellingen in Microsoft Intune. Wanneer u de sjabloon maakt, wordt er ook een apparaatconfiguratieprofiel gemaakt. U kunt dit profiel vervolgens toewijzen aan of implementeren op Windows 10-apparaten in uw organisatie.

## <a name="create-a-template"></a>Een sjabloon maken

1. Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Selecteer **Apparaatconfiguratie** > **Profielen** > **Profiel maken**.
3. Voer de volgende eigenschappen in:

    - **Naam**: Voer een naam voor het profiel in.
    - **Beschrijving**: Voer een beschrijving in voor het profiel. Deze instelling is optioneel, maar wordt aanbevolen.
    - **Platform**: Kies **Windows 10 en hoger**.
    - **Profieltype**: Selecteer **Beheersjablonen (preview)** .

4. Selecteer **Maken**. Selecteer in het nieuwe venster de optie **Instellingen**. Alle instellingen worden vermeld. U kunt de pijlen Vorige/Volgende gebruiken om meer instellingen te bekijken:

    ![Een voorbeeldlijst met instellingen bekijken en de knoppen Vorige en Volgende gebruiken](./media/administrative-templates-windows/sample-settings-list-next-page.png)

5. Selecteer een willekeurige instelling. Selecteer bijvoorbeeld **Bestand downloaden toestaan**. Er wordt een gedetailleerde beschrijving van de instelling weergegeven. Kies ervoor om de instelling **in** of **uit** te schakelen, of om de instelling **niet te configureren** (standaard). In de gedetailleerde beschrijving wordt ook uitgelegd wat er gebeurt wanneer u een instelling **inschakelt**, **uitschakelt** of **niet configureert**.
6. Selecteer **OK** om uw wijzigingen op te slaan.

Doorloop de lijst met instellingen verder en configureer de instellingen die u in uw omgeving wilt gebruiken. Enkele voorbeelden:

- Gebruik de instelling **VBA Macro Notification Settings** (Meldingsinstellingen voor VBA-macro's) om in te stellen hoe in verschillende Microsoft Office-programma's moet worden omgegaan met VBA-macro's, bijvoorbeeld in Word en Excel.
- Gebruik de instelling **Bestand downloaden toestaan** als u wilt toestaan of voorkomen dat er vanuit Internet Explorer wordt gedownload.
- Gebruik de instelling **Require a password when a computer wakes (plugged in)** (Wachtwoord vereisten wanneer een computer uit de slaapstand wordt gehaald (aangesloten)) om gebruikers te vragen om een wachtwoord in te voeren wanneer apparaten uit de slaapstand worden gehaald.
- Gebruik de instelling **ActiveX-besturingselementen zonder handtekening downloaden** om te voorkomen dat gebruikers niet-ondertekende ActiveX-besturingselementen downloaden via Internet Explorer.
- Gebruik de instelling **Systeemherstel uitschakelen** om te voorkomen dat gebruikers systeemherstel uitvoeren op het apparaat.
- En nog veel meer...

## <a name="find-some-settings"></a>Enkele instellingen zoeken

In deze sjablonen zijn honderden verschillende instellingen beschikbaar. Gebruik de volgende ingebouwde functies om het eenvoudiger te maken om specifieke instellingen te zoeken:

- Selecteer in uw sjabloon de kolom **Instellingen**, **Status** of **Pad** om de lijst te sorteren. Selecteer bijvoorbeeld de kolom **Pad** om alle instellingen in het pad `Microsoft Excel` te bekijken:

  ![Klik op Pad om op alfabetische volgorde te sorteren](./media/administrative-templates-windows/path-filter-shows-excel-options.png)

- Gebruik in uw sjabloon het vak **Zoeken** om specifieke instellingen te zoeken. Bijvoorbeeld zoeken naar `copy`. Alle instellingen met `copy` worden weergegeven:

  ![Klik op Pad om op alfabetische volgorde te sorteren](./media/administrative-templates-windows/search-copy-settings.png)

  Zoek in een ander voorbeeld naar `microsoft word`. U ziet alle instellingen die u voor het programma Microsoft Word kunt instellen. Zoek naar `explorer` om te bekijken welke Internet Explorer-instellingen u allemaal aan uw sjabloon kunt toevoegen.

Voor deze functie worden [Beleids-CSP’s voor Windows](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider#admx-backed-policies) gebruikt (er wordt een andere Docs-site geopend). De CSP's werken op verschillende edities van Windows zoals Home, Professional, Enterprise enzovoort. Ga naar [Beleids-CSP's voor Windows](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider#admx-backed-policies) om te zien of een bepaalde CSP op een specifieke editie werkt (er wordt een andere Docs-site geopend).

## <a name="next-steps"></a>Volgende stappen

De sjabloon is gemaakt, maar er gebeurt nog niets. De volgende stap is [de sjabloon, ook wel een profiel genoemd, toewijzen](device-profile-assign.md) en [de status ervan bewaken](device-profile-monitor.md).
