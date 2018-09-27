---
title: Problemen met beleid oplossen in Microsoft Intune - Azure | Microsoft Docs
description: Veelvoorkomende problemen en oplossingen bij het gebruik van beleid in Microsoft Intune
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 06/14/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 99fb6db6-21c5-46cd-980d-50f063ab8ab8
ROBOTS: ''
ms.reviewer: tscott
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 1d656dcc8c3abcf3a4b0a9c6aacbc42eb896289f
ms.sourcegitcommit: 7c70c3e0fcae7c4fa8c9e108aafb1cebb366332d
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/07/2018
ms.locfileid: "44096492"
---
# <a name="troubleshoot-policies-in-intune"></a>Beleidsproblemen oplossen in Intune

Als u problemen hebt met het implementeren en beheren van Intune-beleid, begint u hier. In dit artikel worden enkele veelvoorkomende problemen en mogelijke oplossingen voor die problemen beschreven.

## <a name="general-issues"></a>Algemene problemen

### <a name="was-a-deployed-policy-applied-to-the-device"></a>Is er een geïmplementeerd beleid toegepast op het apparaat?
**Probleem:** u weet niet zeker of een beleid correct is toegepast.

Al het beleid voor een apparaat wordt weergegeven onder Intune > **Apparaten** > **Alle apparaten** > Selecteer het apparaat > **Apparaatconfiguratie**. Elk beleid heeft een **Status**. De status is wat wordt toegepast wanneer alle beleidsregels die betrekking hebben op het apparaat, inclusief de beperkingen en vereisten van de hardware en het besturingssysteem, als een geheel worden beschouwd. Mogelijke statussen zijn:

- **Conform**: het apparaat heeft het beleid ontvangen en rapporteert aan de service dat het voldoet aan de instelling.

- **Niet van toepassing**: de beleidsinstelling is niet van toepassing. E-mailinstellingen voor iOS-apparaten zijn bijvoorbeeld niet van toepassing op een Android-apparaat.

- **In behandeling**: het beleid is naar het apparaat verzonden, maar de status is door het apparaat nog niet gerapporteerd aan de service. Zo moet de gebruiker in geval van versleuteling voor Android versleuteling inschakelen, waardoor de actie mogelijk in behandeling is.

> [!NOTE]
> Wanneer er twee sets beleidsregels met verschillende beperkingsniveaus zijn die op hetzelfde apparaat of dezelfde gebruiker van toepassing zijn, wordt het meest beperkende beleid toegepast.

## <a name="issues-with-enrolled-devices"></a>Problemen met geregistreerde apparaten

### <a name="alert-saving-of-access-rules-to-exchange-has-failed"></a>Waarschuwing: het opslaan van de toegangsregels in Exchange is mislukt
**Probleem**: u ontvangt in de beheerconsole de waarschuwing **Het opslaan van de toegangsregels in Exchange is mislukt**  .

Als u beleid hebt gemaakt in de werkruimte Beleid voor Exchange On-Premises van de beheerconsole, maar O365 gebruikt, worden de geconfigureerde beleidsinstellingen niet door Intune afgedwongen. Noteer de beleidsbron die in de waarschuwing wordt vermeld.  Verwijder de verouderde regels in de werkruimte Beleid voor Exchange On-Premises. De verouderde regels zijn algemene Exchange-regels in Intune voor Exchange On-Premises en zijn niet relevant voor O365. Maak vervolgens een nieuw beleid voor O365.

### <a name="cannot-change-security-policy-for-various-enrolled-devices"></a>Het beveiligingsbeleid voor verschillende MDM-apparaten kan niet worden gewijzigd
Bij Windows Phone-apparaten wordt niet toegestaan dat de beveiligingsbeleidsregels die via MDM of EAS zijn ingesteld, worden teruggebracht naar een lager niveau wanneer u die eenmaal hebt ingesteld. U stelt bijvoorbeeld een **minimumaantal tekens voor het wachtwoord** in op 8 en wilt dit vervolgens terugbrengen tot 4. Het meer beperkende beleid is al toegepast op het apparaat.

Afhankelijk van het apparaatplatform moet u mogelijk het beveiligingsbeleid opnieuw instellen als u de beveiliging naar beneden toe wilt bijstellen.

Veeg bijvoorbeeld in Windows op het bureaublad vanaf rechts over het scherm om de balk **Charms** te openen. Kies **Instellingen** > **Configuratiescherm** en selecteer **Gebruikersaccounts**. Selecteer aan de linkerkant de koppeling **Beveiligingsbeleid opnieuw instellen** en kies **Beleid opnieuw instellen**.

Andere MDM-apparaten, bijvoorbeeld met Android, Windows Phone 8.1 en hoger of iOS, moeten mogelijk buiten gebruik worden gesteld en weer opnieuw bij de service worden ingeschreven voordat u een minder beperkend beleid kunt toepassen.

## <a name="issues-with-pcs-that-run-the-intune-software-client"></a>Problemen met pc's waarop de Intune-software-client wordt uitgevoerd

Van toepassing op de klassieke portal.

### <a name="microsoft-intune-policy-related-errors-in-policyplatformlog"></a>Aan Microsoft Intune-beleid gerelateerde fouten in policyplatform.log
Bij Windows-pc's die worden beheerd met de Intune-softwareclient kunnen beleidsfouten in het bestand policyplatform.log het gevolg zijn van niet-standaardinstellingen in Windows Gebruikersaccountbeheer (UAC) op het apparaat. Bepaalde niet-standaard-UAC-instellingen kunnen invloed hebben op Microsoft Intune-clientinstallaties en de beleidsuitvoering.

#### <a name="resolve-uac-issues"></a>UAC-problemen oplossen

1. Stel de computer buiten gebruik. Zie [Apparaten verwijderen](devices-wipe.md).

2. Wacht twintig minuten tot de clientsoftware is verwijderd.

    > [!NOTE]
    > Probeer niet om de client te verwijderen vanuit Programma's en onderdelen.

3. Typ **UAC** in het startmenu om de instellingen voor Gebruikersaccountbeheer te openen.

4. Verplaats de schuifregelaar voor meldingen naar de standaardinstelling.

### <a name="error-cannot-obtain-the-value-from-the-computer-0x80041013"></a>Fout: kan de waarde niet ophalen van de computer, 0x80041013
Dit gebeurt als de tijd op het lokale systeem met meer dan vijf minuten afwijkt. Als de tijd op de lokale computer afwijkt, mislukken beveiligde transacties omdat de tijdstempels ongeldig zijn.

U lost dit probleem op door de lokale systeemtijd zo gelijk mogelijk in te stellen op de internettijd of op de tijd die is ingesteld op de domeincontrollers in het netwerk.

### <a name="next-steps"></a>Volgende stappen
Als deze informatie over probleemoplossing u niet heeft geholpen, kunt u contact opnemen met Microsoft Ondersteuning zoals is beschreven in [Ondersteuning voor Microsoft Intune krijgen](get-support.md).
