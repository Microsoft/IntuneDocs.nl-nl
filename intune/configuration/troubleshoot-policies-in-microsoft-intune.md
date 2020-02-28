---
title: Problemen met beleid oplossen in Microsoft Intune - Azure | Microsoft Docs
description: Lees hoe u de ingebouwde functie voor probleemoplossing gebruikt en lees over algemene problemen en de oplossingen daarvan wanneer u nalevingsbeleid en configuratieprofielen in Microsoft Intune gebruikt
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/18/2020
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 99fb6db6-21c5-46cd-980d-50f063ab8ab8
ROBOTS: ''
ms.reviewer: tscott
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9acb934cdf67aae9c18091a0340f27de635b5399
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/20/2020
ms.locfileid: "77511014"
---
# <a name="troubleshoot-policies-and-profiles-and-in-intune"></a>Beleidsregels en profielen voor het oplossen van problemen in Intune

Microsoft Intune bevat een aantal ingebouwde functies voor probleemoplossing. Gebruik deze functies voor het oplossen van problemen met nalevingsbeleidsregels en configuratieprofielen in uw omgeving.

In dit artikel staan een aantal oplossingstechnieken en er worden problemen beschreven die u mogelijk ervaart.

## <a name="check-tenant-status"></a>Tenantstatus controleren

Controleer de [tenantstatus](../fundamentals/tenant-status.md) en controleer of het abonnement actief is. U kunt ook details weergeven voor actieve incidenten en adviezen die van invloed kunnen zijn op de implementatie van uw beleid of profiel.

## <a name="use-built-in-troubleshooting"></a>Ingebouwde probleemoplossing gebruiken

1. Selecteer in het [beheercentrum van Microsoft Eindpuntbeheer](https://go.microsoft.com/fwlink/?linkid=2109431) de optie **Probleemoplossing en ondersteuning**:

    ![Ga in Intune naar Help en Ondersteuning en selecteer Problemen oplossen](./media/troubleshoot-policies-in-microsoft-intune/help-and-support-troubleshoot.png)

2. Kies **Gebruiker selecteren** > selecteer de gebruiker die het probleem ervaart > **Selecteren**.
3. Controleer of er naast zowel **Intune-licentie** als **Accountstatus** een groen vinkje staat:

    ![Selecteer in Intune de gebruiker en controleer of er naast Accountstatus en Intune-licentie een groen vinkje staat voor de status](./media/troubleshoot-policies-in-microsoft-intune/account-status-intune-license-show-green.png)

    **Nuttige koppelingen**:

    - [Licenties toewijzen zodat gebruikers apparaten kunnen registreren](../fundamentals/licenses-assign.md)
    - [Gebruikers toevoegen aan Intune](../fundamentals/users-add.md)

4. Zoek onder **Apparaten** het apparaat waarop het probleem zich voordoet. Controleer de verschillende kolommen:

    - **Beheerd**: Wanneer een apparaat nalevings- of configuratiebeleidsregels moet ontvangen, moet voor deze eigenschap **MDM** of **EAS/MDM** worden weergegeven.

        - Als **Beheerd** niet is ingesteld op **MDM** of **EAS/MDM**, is het apparaat niet geregistreerd. Een apparaat ontvangt pas nalevings- of configuratiebeleidsregels als het is geregistreerd.

        - Voor beveiligingsbeleid voor apps (mobiel toepassingsbeheer) hoeven apparaten niet te zijn geregistreerd. Zie [App-beveiligingsbeleid maken en toewijzen](../apps/app-protection-policies.md) voor meer informatie.

    - **Het type Azure AD-join**: Moet worden ingesteld op **Werkplek** of **AzureAD**.
 
        - Als deze kolom op **Niet geregistreerd** is ingesteld, is er mogelijk een probleem met de registratie. Doorgaans kunt u dit probleem oplossen door de registratie van het apparaat ongedaan te maken en het apparaat vervolgens opnieuw te registreren.

    - **Compatibel met Intune**: Moet **Ja** zijn. Als **Nee** wordt weergegeven, is er mogelijk een probleem met nalevingsbeleidsregels of maakt het apparaat geen verbinding met de Intune-service. Het apparaat is bijvoorbeeld uitgeschakeld of er is geen netwerkverbinding. Uiteindelijk wordt het apparaat niet-compatibel, mogelijk na 30 dagen.

        Zie [Aan de slag met apparaatnalevingsbeleid in Intune](../protect/device-compliance-get-started.md) voor meer informatie.

    - **Compatibel met Azure AD**: Moet **Ja** zijn. Als **Nee** wordt weergegeven, is er mogelijk een probleem met nalevingsbeleidsregels of maakt het apparaat geen verbinding met de Intune-service. Het apparaat is bijvoorbeeld uitgeschakeld of er is geen netwerkverbinding. Uiteindelijk wordt het apparaat niet-compatibel, mogelijk na 30 dagen.

        Zie [Aan de slag met apparaatnalevingsbeleid in Intune](../protect/device-compliance-get-started.md) voor meer informatie.

    - **Laatste check-in**: Moet een recente tijd en datum zijn. Standaard worden Intune-apparaten elke 8 uur ingecheckt.

        - Als de **Laatste incheckdatum** meer dan 24 uur geleden is, is er mogelijk een probleem met het apparaat. Een apparaat dat niet kan worden ingecheckt, kan geen beleidsregels uit Intune ontvangen.

        - U kunt inchecken als volgt afdwingen:
            - Android-apparaten: open de Bedrijfsportal-app > **Apparaten** > Kies het apparaat in de lijst > **Apparaatinstellingen controleren**.
            - iOS-/iPadOS-apparaten: open de Bedrijfsportal-app > **Apparaten** > Kies het apparaat in de lijst > **Instellingen controleren**.

        - Windows-apparaten: open **Instellingen** > **Accounts** > **Toegang tot werk of school**> Selecteer het account of de MDM-registratie > **Informatie** > **Synchroniseren**.

    - Selecteer het apparaat voor beleidsspecifieke informatie.

        Bij **Apparaatcompliantie** ziet u de status van de nalevingsbeleidsregels die aan het apparaat zijn toegewezen.

        **Apparaatconfiguratie** toont de status van de configuratiebeleidsregels die aan het apparaat zijn toegewezen.

        Als de verwachte beleidsregels niet onder **Apparaatcompliantie** of **Apparaatconfiguratie** worden weergegeven, dan zijn de beleidsregels niet goed gericht. Open het beleid en wijs het beleid aan deze gebruiker of dit apparaat toe.

        **Beleidsstatussen**:

        - **Niet van toepassing**: Dit beleid wordt niet ondersteund op dit platform. iOS-/iPadOS-beleid werkt bijvoorbeeld niet op Android. Samsung KNOX-beleid werkt niet op Windows-apparaten.
        - **Conflict**: Het apparaat heeft een bestaande instelling die niet door Intune kan worden overschreven. Of u hebt twee beleidsregels geïmplementeerd met dezelfde instelling, maar verschillende waarden.
        - **In behandeling**: Het apparaat is niet ingecheckt bij Intune om het beleid op te halen. Of het apparaat heeft het beleid wel ontvangen, maar de status is niet naar Intune gerapporteerd.
        - **Fouten**: Zoek fouten en mogelijke oplossingen op bij [Problemen met toegang tot bedrijfsresources oplossen](../fundamentals/troubleshoot-company-resource-access-problems.md).

        **Nuttige koppelingen**: 

        - [Nalevingsbeleid voor apparaten implementeren](../protect/device-compliance-get-started.md#ways-to-deploy-device-compliance-policies)
        - [Nalevingsbeleid voor apparaten controleren](../protect/compliance-policy-monitor.md)

## <a name="youre-unsure-if-a-profile-is-correctly-applied"></a>U weet niet zeker of een profiel op de juiste manier is toegepast

1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecteer **Apparaten** > **Alle apparaten** > selecteer het apparaat > **Apparaatconfiguratie**. 

    Bij elk apparaat worden de bijbehorende profielen vermeld. Elk profiel heeft een **status**. De status is van toepassing wanneer alle toegewezen profielen, inclusief hardware- en besturingssysteembeperkingen en -vereisten, als geheel worden overwogen. Mogelijke statussen zijn:

    - **Voldoet**: Het apparaat heeft het profiel ontvangen en meldt aan Intune dat de instelling wordt nageleefd.

    - **Niet van toepassing**: De profielinstelling is niet van toepassing. E-mailinstellingen voor iOS-/iPadOS-apparaten zijn bijvoorbeeld niet van toepassing op een Android-apparaat.

    - **In behandeling**: Het profiel wordt naar het apparaat verzonden, maar de status is nog niet naar Intune gerapporteerd. Zo moet de gebruiker in geval van versleuteling voor Android versleuteling inschakelen, waardoor de actie mogelijk in behandeling is.

**Nuttige koppeling**: [Configuratieprofielen voor apparaten bewaken](../configuration/device-profile-monitor.md)

> [!NOTE]
> Wanneer er twee sets beleidsregels met verschillende beperkingsniveaus zijn die op hetzelfde apparaat of dezelfde gebruiker van toepassing zijn, wordt het meest beperkende beleid toegepast.

## <a name="policy-troubleshooting-resources"></a>Problemen met beleidsresources polossen

- [Problemen oplossen met iOS-/iPadOS- of Android-beleid dat niet van toepassing is op apparaten](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-tip-Troubleshooting-iOS-or-Android-policies-not-applying/ba-p/280154) (opent een andere website van Microsoft)
- [Problemen oplossen met Intune-beleidsfouten in Windows 10](https://blogs.technet.microsoft.com/configmgrdogs/2018/08/09/troubleshooting-windows-10-intune-policy-failures/) (opent een blog)
- [Problemen oplossen met aangepaste CSP-instellingen voor Windows 10](https://support.microsoft.com/en-us/help/4055338/troubleshoot-csp-setting-windows-10-computer-intune) (opent een andere website van Microsoft)
- [Groepsbeleid in Windows 10 versus MDM-beleid in Intune](https://blogs.technet.microsoft.com/cbernier/2018/04/02/windows-10-group-policy-vs-intune-mdm-policy-who-wins/) (opent een andere website van Microsoft)

## <a name="alert-saving-of-access-rules-to-exchange-has-failed"></a>Waarschuwing: Opslaan van toegangsregels in Exchange is mislukt

**Probleem**: U ontvangt in de beheerconsole de waarschuwing **Het opslaan van de toegangsregels in Exchange is mislukt**.

Als u beleid hebt gemaakt in de werkruimte Beleid voor Exchange On-Premises (beheerconsole), maar Office 365 gebruikt, worden de geconfigureerde beleidsinstellingen niet door Intune afgedwongen. Noteer de beleidsbron die in de waarschuwing wordt vermeld. Verwijder de verouderde regels in de werkruimte Beleid voor Exchange On-Premises. De verouderde regels zijn algemene Exchange-regels in Intune voor Exchange On-Premises en zijn niet relevant voor Office 365. Maak vervolgens een nieuw beleid voor Office 365.

[Problemen met de Intune on-premises Exchange-connector oplossen](../protect/troubleshoot-exchange-connector.md) is wellicht een goede bron.

## <a name="cant-change-security-policies-for-enrolled-devices"></a>Kan beveiligingsbeleid voor geregistreerde apparaten niet wijzigen

Bij Windows Phone-apparaten wordt niet toegestaan dat de beveiligingsbeleidsregels die via MDM of EAS zijn ingesteld, worden teruggebracht naar een lager niveau wanneer u die eenmaal hebt ingesteld. U stelt bijvoorbeeld het **minimumaantal tekens voor het wachtwoord** in op 8 en wilt dit vervolgens terugbrengen tot 4. Het meer beperkende beleid wordt op het apparaat toegepast.

Op Windows 10-apparaten wordt beveiligingsbeleid mogelijk niet verwijderd wanneer u de toewijzing ervan opheft (de implementatie stopt). Mogelijk moet u het beleid toegewezen laten en vervolgens de beveiligingsinstellingen weer instellen op de standaardwaarden.

Afhankelijk van het apparaatplatform moet u mogelijk het beveiligingsbeleid opnieuw instellen als u de beveiliging naar beneden toe wilt bijstellen.

Veeg bijvoorbeeld in Windows 8.1 op het bureaublad vanaf rechts over het scherm om de balk **Charms** te openen. Kies **Instellingen** > **Configuratiescherm** > **Gebruikersaccounts**. Selecteer aan de linkerkant de koppeling **Beveiligingsbeleid opnieuw instellen** en kies **Beleid opnieuw instellen**.

Andere platformen, zoals Android, iOS/iPadOS en Windows Phone 8.1, moeten mogelijk buiten gebruik worden gesteld en weer opnieuw worden geregistreerd voordat u een minder beperkend beleid kunt toepassen.

Mogelijk is [Problemen met apparaatregistratie oplossen](../enrollment/troubleshoot-device-enrollment-in-intune.md) een goede bron.

## <a name="pcs-using-the-intune-software-client---classic-portal"></a>Pc’s die de Intune-softwareclient gebruiken - klassieke portal

> [!NOTE]
> Deze sectie is van toepassing op de klassieke portal. 

### <a name="microsoft-intune-policy-related-errors-in-policyplatformlog"></a>Aan Microsoft Intune-beleid gerelateerde fouten in policyplatform.log

Bij Windows-pc's die worden beheerd met de Intune-softwareclient kunnen beleidsfouten in het bestand `policyplatform.log` het gevolg zijn van niet-standaardinstellingen in Windows Gebruikersaccountbeheer (UAC) op het apparaat. Bepaalde niet-standaard-UAC-instellingen kunnen invloed hebben op Microsoft Intune-clientinstallaties en de beleidsuitvoering.

#### <a name="resolve-uac-issues"></a>UAC-problemen oplossen

1. Stel de computer buiten gebruik. Zie [Apparaten verwijderen](../remote-actions/devices-wipe.md).

2. Wacht twintig minuten tot de clientsoftware is verwijderd.

    > [!NOTE]
    > Probeer niet om de client te verwijderen vanuit Programma's en onderdelen.

3. Typ **UAC** in het startmenu om de instellingen voor Gebruikersaccountbeheer te openen.

4. Verplaats de schuifregelaar voor meldingen naar de standaardinstelling.

### <a name="error-cannot-obtain-the-value-from-the-computer-0x80041013"></a>Fout: Kan de waarde niet ophalen van de computer, 0x80041013

Dit gebeurt als de tijd op het lokale systeem met meer dan vijf minuten afwijkt. Als de tijd op de lokale computer afwijkt, mislukken beveiligde transacties omdat de tijdstempels ongeldig zijn.

Stel de lokale systeemtijd zo dicht mogelijk bij de internettijd in om dit probleem op te lossen. Of stel de lokale systeemtijd in op de tijd van de domeincontrollers in het netwerk.

## <a name="next-steps"></a>Volgende stappen

[Veelvoorkomende problemen met en oplossingen voor e-mailprofielen](../configuration/troubleshoot-email-profiles-in-microsoft-intune.md)

Krijg [ondersteuning van Microsoft](../fundamentals/get-support.md) of gebruik de [communityforums](https://social.technet.microsoft.com/Forums/en-US/home?category=microsoftintune).
