---
title: Windows BIOS-functies met behulp van MDM-beleid in Microsoft Intune bijwerken - Azure | Microsoft Docs
description: Voeg een DFCI-profiel (Device Firmware Configuration Interface) toe voor het beheren van UEFI-instellingen, zoals de CPU, ingebouwde hardware en opstartopties op Windows 10-apparaten in Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/06/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1d07066bcd599dc0cdbaf8fcf90ac1ee76be45fa
ms.sourcegitcommit: e166b9746fcf0e710e93ad012d2f52e2d3ed2644
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/19/2019
ms.locfileid: "75206683"
---
# <a name="use-device-firmware-configuration-interface-profiles-on-windows-devices-in-microsoft-intune-public-preview"></a>Device Firmware Configuration Interface-profielen gebruiken op Windows-apparaten in Microsoft Intune (openbare preview)



Wanneer u Intune gebruikt om Autopilot-apparaten te beheren, kunt u met behulp van DFCI UEFI-instellingen (BIOS) beheren, nadat deze zijn opgegeven. Zie [Overzicht van DFCI](https://microsoft.github.io/mu/dyn/mu_plus/DfciPkg/Docs/Dfci_Feature/) voor een overzicht van voordelen, scenario's en vereisten.

Met DFCI [kunt u in Windows](https://docs.microsoft.com/windows/client-management/mdm/uefi-csp) beheeropdrachten van Intune naar UEFI (Unified Extensible Firmware Interface) doorgeven.

U kunt in Intune via deze functie BIOS-instellingen beheren. Normaal gesproken is de firmware toleranter voor kwaadaardige aanvallen. Hierdoor wordt het beheer van eindgebruikers over het BIOS beperkt, wat een voordeel is in verdachte omstandigheden.

U gebruikt bijvoorbeeld Windows 10-apparaten in een beveiligde omgeving, en u wilt de camera uitschakelen. U kunt de camera uitschakelen in de firmwarelaag, zodat het niet uitmaakt wat de eindgebruiker doet. Als u het besturingssysteem opnieuw installeert of als u de computer wist, wordt de camera niet weer ingeschakeld. In een ander voorbeeld kunt u de opstartopties vergrendelen om te voorkomen dat gebruikers een ander besturingssysteem of een oudere versie van Windows opstarten die niet over dezelfde beveiligingsfuncties beschikt.

Wanneer u een oudere versie van Windows opnieuw installeert, een afzonderlijk besturingssysteem installeert of de harde schijf formatteert, kunt u het DFCI-beheer niet overschrijven. Met deze functie wordt voorkomen dat malware communiceert met besturingssysteemprocessen, inclusief besturingssysteemprocessen met een verhoogde bevoegdheid. De vertrouwensketen van de DFCI maakt gebruik van openbare-sleutelcryptografie en is niet afhankelijk van lokale UEFI-wachtwoordbeveiliging (BIOS). Met deze beveiligingslaag worden voor lokale gebruikers de toegang geblokkeerd tot beheerde instellingen vanuit de UEFI-menu's (BIOS) van het apparaat.

Deze functie is van toepassing op:

- Windows 10 RS5 (1809) en hoger op ondersteunde UEFI

## <a name="before-you-begin"></a>Voordat u begint

- De fabrikant van het apparaat moet DFCI hebben toegevoegd aan hun UEFI-firmware in het productieproces of als firmware-update die u installeert. Werk samen met de leveranciers van uw apparaten om te bepalen [welke fabrikanten DFCI ondersteunen](https://microsoft.github.io/mu/dyn/mu_plus/DfciPkg/Docs/Scenarios/DfciScenarios/#oems-that-support-dfci), of welke firmwareversie nodig is voor het gebruik van DFCI.

- Het apparaat moet voor Windows Autopilot zijn geregistreerd door een [Microsoft Cloud Solution Provider-partner (CSP)](https://partner.microsoft.com/cloud-solution-provider) of rechtstreeks door de OEM zijn geregistreerd. 

  Apparaten die handmatig zijn geregistreerd voor Autopilot en bijvoorbeeld zijn [geïmporteerd uit een CSV-bestand](../enrollment/enrollment-autopilot.md#add-devices), mogen DFCI niet gebruiken. Voor DFCI-beheer is standaard een extern bewijsstuk vereist voor de commerciële aanschaf van het apparaat via een OEM of een Microsoft CSP-partnerregistratie voor Windows Autopilot.

  Zodra het apparaat is geregistreerd, wordt het serienummer in de lijst met Windows Autopilot-apparaten weergegeven.

  Zie [Windows-apparaten in Intune inschrijven met Windows Autopilot](../enrollment/enrollment-autopilot.md) voor meer informatie over Autopilot en de bijbehorende vereisten.

## <a name="create-your-azure-ad-security-groups"></a>Uw Azure AD-beveiligingsgroepen maken

Autopilot-implementatieprofielen worden toegewezen aan Azure AD-beveiligingsgroepen. Zorg ervoor dat u groepen maakt waarin uw door DFCI ondersteunde apparaten zijn opgenomen. Voor DFCI-apparaten kunnen de meeste organisaties apparaatgroepen maken, in plaats van gebruikersgroepen. Denk eens na over de volgende scenario's:

- HR (Human Resources) beschikt over verschillende Windows-apparaten. Uit veiligheidsoverwegingen wilt u niet dat iemand van deze groep de camera op de apparaten gebruikt. In dit scenario kunt u een HR-beveiligingsgebruikersgroep maken, zodat het beleid van toepassing is op gebruikers in de HR-groep, ongeacht het apparaattype.
- Op de productievloer hebt u 10 apparaten. U wilt voor alle apparaten voorkomen dat deze worden opgestart vanaf een USB-apparaat. In dit scenario kunt u een beveiligingsapparatengroep maken en deze 10 apparaten toevoegen aan de groep.

Zie [Groepen toevoegen om gebruikers en apparaten te organiseren](../fundamentals/groups-add.md) voor meer informatie over het maken van groepen in Intune.

## <a name="create-the-profiles"></a>De profielen maken

Als u DFCI wilt gebruiken, maakt u de volgende profielen en wijst u deze toe aan uw groep.

### <a name="create-an-autopilot-deployment-profile"></a>Een Autopilot-implementatieprofiel maken

Met dit profiel worden nieuwe apparaten ingesteld en vooraf geconfigureerd. In het [Autopilot-implementatieprofiel](../enrollment/enrollment-autopilot.md#create-an-autopilot-deployment-profile) worden de stappen vermeld voor het maken van het profiel.

### <a name="create-an-enrollment-state-page-profile"></a>Een profiel voor een registratiestatuspagina maken

Met dit profiel zorgt u ervoor dat apparaten worden gecontroleerd en ingeschakeld voor DFCI tijdens de installatie van Windows. Het is zeer aanbevelenswaardig om dit profiel te gebruiken om het gebruik van apparaten te blokkeren totdat alle apps en profielen zijn geïnstalleerd. In het [profiel voor een registratiestatuspagina](../enrollment/windows-enrollment-status.md) worden de stappen vermeld voor het maken van het profiel.

### <a name="create-the-dfci-profile"></a>Het DFCI-profiel maken

Dit profiel bevat de DFCI-instellingen die u configureert.

1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecteer **Apparaten** > **Configuratieprofielen** > **Profiel maken**.
3. Voer de volgende eigenschappen in:

    - **Naam**: Voer een beschrijvende naam in voor het profiel. Geef uw beleid een naam zodat u het later eenvoudig kunt identificeren. Een goede profielnaam is bijvoorbeeld **Windows: Configureer DFCI-instellingen op Windows-apparaten**.
    - **Beschrijving**: Voer een beschrijving in voor het profiel. Deze instelling is optioneel, maar wordt aanbevolen.
    - **Platform**: Kies **Windows 10 en hoger**.
    - **Profieltype**: Selecteer **Configuratie-interface voor apparaatfirmware**.

4. Configureer de gewenste instellingen:

    - **Lokale gebruiker kan UEFI-instellingen (BIOS) wijzigen**: Uw opties zijn:
      - **Uitsluitend niet-geconfigureerde instellingen**: De lokale gebruiker kan elke instelling wijzigen, *met uitzondering van* die instellingen die expliciet zijn ingesteld op **Inschakelen** of **Uitschakelen** door Intune.
      - **Geen**: De lokale gebruiker mag geen UEFI-instellingen (BIOS) wijzigen, inclusief instellingen die niet worden weergegeven in het DFCI-profiel.

    - **CPU- en IO-virtualisatie**: Uw opties zijn:
        - **Niet geconfigureerd**: Intune laat deze functie ongemoeid en laat instellingen ongewijzigd.
        - **Ingeschakeld**: Met het BIOS kan de CPU- en IO-virtualisatiefunctionaliteit van het platform worden gebruikt door het besturingssysteem. Hiermee worden de Windows-technologieën Beveiliging op basis van virtualisatie en Device Guard ingeschakeld.
        - **Uitschakelen**: Met het BIOS kan de CPU- en IO-virtualisatiefunctionaliteit van het platform worden uitgeschakeld, en wordt voorkomen dat deze worden gebruikt.
    - **Camera's**: Uw opties zijn:
        - **Niet geconfigureerd**: Intune laat deze functie ongemoeid en laat instellingen ongewijzigd.
        - **Ingeschakeld**: Alle ingebouwde camera's die rechtstreeks worden beheerd door UEFI (BIOS) zijn ingeschakeld. Randapparatuur, zoals USB-camera's, wordt niet beïnvloed.
        - **Uitgeschakeld**: Alle ingebouwde camera's die rechtstreeks worden beheerd door UEFI (BIOS) zijn uitgeschakeld. Randapparatuur, zoals USB-camera's, wordt niet beïnvloed.
    - **Microfoons en luidsprekers**:  Uw opties zijn:
        - **Niet geconfigureerd**: Intune laat deze functie ongemoeid en laat instellingen ongewijzigd.
        - **Ingeschakeld**: Alle ingebouwde microfoons die rechtstreeks worden beheerd door UEFI (BIOS) zijn ingeschakeld. Randapparatuur, zoals USB-apparaten, wordt niet beïnvloed.
        - **Uitgeschakeld**: Alle ingebouwde microfoons die rechtstreeks worden beheerd door UEFI (BIOS) zijn uitgeschakeld. Randapparatuur, zoals USB-apparaten, wordt niet beïnvloed.
    - **Radio's (Bluetooth, Wi-Fi, NFC, enzovoort)** : Uw opties zijn:
        - **Niet geconfigureerd**: Intune laat deze functie ongemoeid en laat instellingen ongewijzigd.
        - **Ingeschakeld**: Alle ingebouwde radio's die rechtstreeks worden beheerd door UEFI (BIOS) zijn ingeschakeld. Randapparatuur, zoals USB-apparaten, wordt niet beïnvloed.
        - **Uitgeschakeld**: Alle ingebouwde radio's die rechtstreeks worden beheerd door UEFI (BIOS) zijn uitgeschakeld. Randapparatuur, zoals USB-apparaten, wordt niet beïnvloed.

        > [!WARNING]
        > Als u de instelling **Radio's** uitschakelt, is voor het apparaat een bekabelde netwerkverbinding vereist. Anders kan het apparaat misschien niet worden beheerd.

    - **Opstarten vanaf externe media (USB, SD)** : Uw opties zijn:
        - **Niet geconfigureerd**: Intune laat deze functie ongemoeid en laat instellingen ongewijzigd.
        - **Ingeschakeld**: UEFI (BIOS) staat het opstarten van niet-vaste-schijfopslag toe.
        - **Uitgeschakeld**: UEFI (BIOS) staat het opstarten van niet-vaste-schijfopslag niet toe.
    - **Opstarten vanaf netwerkadapters**:  Uw opties zijn:
        - **Niet geconfigureerd**: Intune laat deze functie ongemoeid en laat instellingen ongewijzigd.
        - **Ingeschakeld**: UEFI (BIOS) staat het opstarten vanaf ingebouwde netwerkinterfaces toe.
        - **Uitgeschakeld**: UEFI (BIOS) staat het opstarten vanaf ingebouwde netwerkinterfaces niet toe.

5. Wanneer u klaar bent, selecteert u **OK** > **Maken** om uw wijzigingen op te slaan. Het profiel wordt gemaakt en weergegeven in de lijst.

## <a name="assign-the-profiles-and-reboot"></a>De profielen toewijzen en opnieuw opstarten

Nadat de profiel zijn gemaakt, zijn deze [klaar om te worden toegewezen](../configuration/device-profile-assign.md). Zorg ervoor dat u de profielen toewijst aan uw Azure AD-beveiligingsgroepen die uw DFCI-apparaten bevatten.

Wanneer Windows Autopilot op het apparaat wordt uitgevoerd, kan het door de DFCI geforceerd opnieuw worden opgestart op de inschrijvingsstatuspagina. Tijdens de eerste keer dat de computer opnieuw wordt opgestart, wordt de UEFI ingeschreven bij Intune. 

Als u wilt bevestigen dat het apparaat is ingeschreven, kunt u het apparaat opnieuw opstarten, maar dit is niet vereist. Gebruik vervolgens de instructies van de fabrikant van het apparaat om het UEFI-menu te openen en controleer of de UEFI nu wordt beheerd.

De volgende keer dat het apparaat wordt gesynchroniseerd met Intune, ontvangt Windows de DFCI-instellingen. Start het apparaat opnieuw. Deze derde keer opnieuw opstarten is vereist om de UEFI de DFCI-instellingen van Windows te laten ontvangen.

## <a name="update-existing-dfci-settings"></a>Bestaande DFCI-instellingen bijwerken

Het is mogelijk om bestaande DFCI-instellingen te wijzigen op apparaten die in gebruik zijn. Wijzig de instellingen in uw bestaande DFCI-profiel en sla uw wijzigingen op. Omdat het profiel al is toegewezen, worden de nieuwe DFCI-instellingen van kracht wanneer:

1. Het apparaat incheckt bij de Intune-service om op profielupdates te controleren. Check-ins op verschillende tijdstippen plaatsvinden. Zie [Wanneer apparaten een beleid, profiel of app-updates ophalen](../configuration/device-profile-troubleshoot.md#how-long-does-it-take-for-devices-to-get-a-policy-profile-or-app-after-they-are-assigned) voor meer informatie.

2. Als u de nieuwe instellingen wilt afdwingen, moet u het apparaat [extern](../remote-actions/device-restart.md) of lokaal opnieuw opstarten.

U kunt ook [apparaten signaleren om in te checken](../remote-actions/device-sync.md). [Signaleer het apparaat na een geslaagde synchronisatie](../remote-actions/device-restart.md) om opnieuw op te starten.

>[!NOTE]
> Als u het DFCI-profiel verwijdert of een apparaat verwijdert uit de groep die aan het profiel is toegewezen, worden hiermee geen DFCI-instellingen verwijderd, en evenmin worden de UEFI-menu's (BIOS) opnieuw ingeschakeld. Als u wilt stoppen met het gebruik van DFCI, werkt u uw bestaande DFCI-profiel bij. Zie [Buiten gebruik stellen van het apparaat](#retire) in dit artikel voor meer informatie over de stappen.

## <a name="reuse-retire-or-recover-the-device"></a>Het apparaat opnieuw gebruiken, buiten gebruik stellen of herstellen

### <a name="reuse"></a>Opnieuw gebruiken

Als u van plan bent Windows opnieuw in te stellen om het apparaat een ander doel te geven, [moet u het apparaat wissen](../remote-actions/devices-wipe.md). Verwijder **niet** de Autopilot-apparaatrecord.

Nadat u het apparaat hebt gewist, verplaatst u het apparaat naar de groep waaraan de nieuwe DFCI en Autopilot-profielen zijn toegewezen. Zorg ervoor dat u het apparaat opnieuw opstart om de installatie van Windows opnieuw uit te voeren.

### <a name="retire"></a>Buiten gebruik stellen

Wanneer u klaar bent om het apparaat buiten gebruik te stellen en het uit te sluiten van beheer, werkt u het DFCI-profiel bij naar de UEFI-instellingen die u in de afsluitstatus wilt hebben. Normaal gesproken wilt u dat alle instellingen zijn ingeschakeld. Bijvoorbeeld:

1. Open uw DFCI-profiel (**Apparaten** > **Configuratieprofielen**).
2. Wijzig de instelling **Lokale gebruiker toestaan om de instellingen van UEFI (BIOS) te wijzigen** in **Alleen niet geconfigureerde instellingen**.
3. Stel alle andere instellingen in op **Niet geconfigureerd**.
4. Sla uw wijzigingen op.

Met deze stappen worden de UEFI-menu's (BIOS) van het apparaat ontgrendeld. De waarden blijven hetzelfde als in het profiel (**Ingeschakeld** of **Uitgeschakeld**) en worden niet teruggezet naar de standaardwaarden van het besturingssysteem.

U bent nu klaar om het apparaat te wissen. Wanneer het apparaat is gewist, verwijdert u de Autopilot-record. Door de record te verwijderen, voorkomt u dat het apparaat automatisch opnieuw wordt geregistreerd wanneer het opnieuw wordt opgestart.

### <a name="recover"></a>Herstellen

Als u een apparaat wist en de Autopilot-record verwijdert voordat u de UEFI-menu's (BIOS) ontgrendelt, blijven de menu's vergrendeld. Intune kan geen profielupdates verzenden om deze te ontgrendelen.

Als u het apparaat wilt ontgrendelen, opent u het UEFI-menu (BIOS) en vernieuwt u het beheer vanuit het netwerk. Met herstellen worden de menu's ontgrendeld, maar blijven alle UEFI-instellingen (BIOS) ingesteld op de waarden in het vorige Intune DFCI-profiel.

## <a name="end-user-impact"></a>Impact van eindgebruiker

Wanneer het DFCI-beleid wordt toegepast, kunnen lokale gebruikers geen instellingen wijzigen die zijn geconfigureerd door DFCI, zelfs niet als het UEFI-menu (BIOS) is beveiligd met een wachtwoord. Afhankelijk van de instellingen die u configureert, kunnen eindgebruikers fouten ontvangen, zoals hardwareonderdelen die niet te vinden zijn of niet kunnen worden onderzocht. Zorg ervoor dat u eindgebruikers documentatie verstrekt met uitleg over de opties die u hebt uitgeschakeld.  

## <a name="next-steps"></a>Volgende stappen

Wanneer het profiel is toegewezen, [moet u de status ervan controleren](../device-profile-monitor.md).
