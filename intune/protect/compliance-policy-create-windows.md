---
title: Nalevingsinstellingen voor Windows 10 in Microsoft Intune - Azure | Microsoft Docs
description: Bekijk een overzicht van alle instellingen die u kunt gebruiken bij het instellen van naleving voor uw Windows 10-, Windows Holographic- en Surface Hub-apparaten in Microsoft Intune. Controleer de naleving van de minimum- en maximumversie van het besturingssysteem, stel wachtwoordbeperkingen en -lengte in, controleer op antivirusoplossingen van partners, schakel versleuteling voor de gegevensopslag in en meer.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/10/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 2e427fe0889dcfb51ba5be322ed4db566cc29e9d
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 10/16/2019
ms.locfileid: "72502463"
---
# <a name="windows-10-and-later-settings-to-mark-devices-as-compliant-or-not-compliant-using-intune"></a>Instellingen in Windows 10 en later om te markeren of apparaten wel of niet conform zijn met behulp van Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Dit artikel bevat een overzicht en beschrijving van de verschillende nalevingsinstellingen die u kunt configureren op apparaten met Windows 10 of later in Intune. Gebruik deze instellingen als onderdeel van uw MDM-oplossing (Mobile Device Management) om BitLocker te vereisen, een minimum- en maximumversie van het besturingssysteem in te stellen, een risiconiveau in te stellen met behulp van Microsoft Defender Advanced Threat Protection (ATP), en meer.

Deze functie is van toepassing op:

- Windows 10 en hoger
- Windows Holographic for Business
- Surface Hub

Gebruik deze nalevingsinstellingen als Intune-beheerder om de resources van uw organisatie beter te beschermen. Zie [Aan de slag met apparaatnalevingsbeleid](device-compliance-get-started.md) voor meer informatie over nalevingsbeleid en wat dit doet.

## <a name="before-you-begin"></a>Voordat u begint

[Een nalevingsbeleid maken](create-compliance-policy.md#create-the-policy). Voor **Platform** selecteert u **Windows 10 en hoger**.

## <a name="device-health"></a>Device health

- **BitLocker vereisen**: Als **Vereisen** is ingesteld, kan het apparaat gegevens die op de schijf zijn opgeslagen, beveiligen tegen onbevoegde toegang wanneer het systeem is uitgeschakeld of zich in de slaapstand bevindt. Windows BitLocker-stationsversleuteling versleutelt alle gegevens die zijn opgeslagen op het volume met het Windows-besturingssysteem. BitLocker gebruikt de TPM om het Windows-besturingssysteem en de gebruikersgegevens te beveiligen. Het helpt ook om te bevestigen dat een computer niet is gemanipuleerd, zelfs als deze zonder toezicht, kwijtgeraakt of gestolen is. Als de computer is uitgerust met een compatibele TPM, gebruikt BitLocker de TPM om de versleutelingssleutels te vergrendelen die de gegevens beschermen. Als gevolg hiervan kunnen de sleutels niet worden gebruikt tot met de TPM de status van de computer is gecontroleerd.

  Als **Niet geconfigureerd** (standaard) is ingesteld, wordt deze instelling niet beoordeeld op naleving of niet-naleving.

- **Vereisen dat Beveiligd opstarten is ingeschakeld op het apparaat**: Als **Vereisen** is ingesteld, wordt het systeem gedwongen om in een vertrouwde fabrieksstatus op te starten. Indien ingeschakeld, moeten de belangrijkste onderdelen van de computer de juiste cryptografische handtekeningen hebben die worden vertrouwd door de organisatie die het apparaat heeft gemaakt. De UEFI-firmware verifieert de digitale handtekening voordat de computer kan worden opgestart. Als de bestanden zijn gemanipuleerd, waardoor de bijbehorende handtekening is beschadigd, kan het systeem niet worden gestart.

  Als **Niet geconfigureerd** (standaard) is ingesteld, wordt deze instelling niet beoordeeld op naleving of niet-naleving.

  > [!NOTE]
  > De instelling **Vereisen dat beveiligd opstarten wordt ingeschakeld op het apparaat** wordt ondersteund op bepaalde TPM 1.2- en 2.0-apparaten. Voor apparaten die geen ondersteuning bieden voor TPM 2.0 of later, wordt de beleidsstatus in Intune weergegeven als **Niet-conform**. Zie [Apparaatstatusverklaring](https://docs.microsoft.com/windows/security/information-protection/tpm/trusted-platform-module-overview#device-health-attestation) voor meer informatie over ondersteunde versies.

- **Vereis code-integriteit**: code-integriteit is een functie die voortdurend de integriteit valideert van een stuurprogramma- of systeembestand wanneer dat bestand in het geheugen wordt geladen. Als **Vereisen** is ingesteld, wordt via deze functie gedetecteerd of een niet-ondertekend stuurprogramma of systeembestand in de kernel is geladen. Ook wordt gedetecteerd of een systeembestand is gewijzigd door middel van schadelijke software die is uitgevoerd via een gebruikersaccount met beheerdersbevoegdheden.

  Als **Niet geconfigureerd** (standaard) is ingesteld, wordt deze instelling niet beoordeeld op naleving of niet-naleving.

Meer resources:

- [Health Attestation CSP](https://docs.microsoft.com/windows/client-management/mdm/healthattestation-csp) (CSP-statusverklaring) biedt meer informatie over de werking van de HAS-service.
- [Ondersteuningstip: Apparaatstatusverklaring gebruiken als onderdeel van uw Intune-nalevingsbeleid](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-Tip-Using-Device-Health-Attestation-Settings-as-Part-of/ba-p/282643)

## <a name="device-properties"></a>Apparaateigenschappen

- **Minimale versie van het besturingssysteem**: voer de minimaal toegestane versie in de nummerindeling **major.minor.build.CU** in. Als u de juiste waarde wilt ophalen, opent u een opdrachtprompt en typt u `ver`. De opdracht `ver` retourneert de versie in de volgende indeling:

  `Microsoft Windows [Version 10.0.17134.1]`

  Wanneer een apparaat een eerdere versie heeft dan de ingevoerde versie van het besturingssysteem, wordt de versie als niet-compatibel gerapporteerd. Er wordt een koppeling met informatie over het uitvoeren van een upgrade weergegeven. De eindgebruiker kan kiezen om het apparaat bij te werken. Na het bijwerken zijn de bedrijfsresources toegankelijk.

- **Maximale versie van het besturingssysteem**: voer de maximaal toegestane versie in de nummerindeling **major.minor.build.versienummer** in. Als u de juiste waarde wilt ophalen, opent u een opdrachtprompt en typt u `ver`. De opdracht `ver` retourneert de versie in de volgende indeling:

  `Microsoft Windows [Version 10.0.17134.1]`

  Wanneer een apparaat een versie van het besturingssysteem gebruikt die hoger is dan de versie die is ingevoerd, wordt de toegang tot organisatieresources geblokkeerd. De eindgebruiker wordt gevraagd contact op te nemen met de IT-beheerder. Op dit apparaat kan geen toegang worden verkregen tot organisatieresources zolang de regel niet zodanig is gewijzigd dat de versie van het besturingssysteem is toegestaan.

- **Minimale versie van het besturingssysteem dat vereist is voor mobiele apparaten**: voer de minimaal toegestane versie in de nummerindeling major.minor.build in.

  Wanneer een apparaat een eerdere versie heeft dan de ingevoerde versie van het besturingssysteem, wordt de versie als niet-compatibel gerapporteerd. Er wordt een koppeling met informatie over het uitvoeren van een upgrade weergegeven. De eindgebruiker kan kiezen om het apparaat bij te werken. Na het bijwerken zijn de bedrijfsresources toegankelijk.

- **Maximale versie van het besturingssysteem dat vereist is voor mobiele apparaten**: voer de maximaal toegestane versie in de nummerindeling major.minor.build in.

  Wanneer een apparaat een versie van het besturingssysteem gebruikt die hoger is dan de versie die is ingevoerd, wordt de toegang tot organisatieresources geblokkeerd. De eindgebruiker wordt gevraagd contact op te nemen met de IT-beheerder. Op dit apparaat kan geen toegang worden verkregen tot organisatieresources zolang de regel niet zodanig is gewijzigd dat de versie van het besturingssysteem is toegestaan.

- **Geldig besturingssysteem-builds**: voer een bereik in voor de acceptabele versies van besturingssystemen, met inbegrip van een minimum en maximum. U kunt ook een bestandslijst met door komma's gescheiden waarden (CSV) met de toegestane versienummers van besturingssystemen **exporteren**.

## <a name="configuration-manager-compliance"></a>Configuration Manager-compatibiliteit

Geldt alleen voor gezamenlijk beheerde apparaten met Windows 10 en hoger. Apparaten met alleen Intune retourneren de status Niet beschikbaar.

- **Apparaatnaleving vereisen van System Center Configuration Manager**: Kies **Vereisen** om af te dwingen dat alle instellingen (configuratie-items) in System Center Configuration Manager conform het beleid moeten zijn. 

  U kunt bijvoorbeeld vereisen dat alle software-updates worden geïnstalleerd op apparaten. Deze vereiste heeft in Configuration Manager de status 'Geïnstalleerd'. Als programma's op het apparaat een onbekende status hebben, is het apparaat niet-compatibel in Intune.
  
  Wanneer de status **Niet geconfigureerd** is, wordt in Intune niet gezocht naar Configuration Manager-instellingen voor naleving.

## <a name="system-security"></a>Systeembeveiliging

### <a name="password"></a>Wachtwoord

- **Een wachtwoord vereisen voor het ontgrendelen van mobiele apparaten**: **verplicht** gebruikers een wachtwoord in te voeren om toegang te krijgen tot hun apparaat. Wanneer deze **niet is geconfigureerd**, wordt het apparaat niet door intune geëvalueerd voor wachtwoord instellingen voor naleving.
- **Eenvoudige wachtwoorden**: stel deze optie in op **Blokkeren** zodat de gebruiker geen eenvoudig wachtwoord kan maken, zoals **1234** of **1111**. Stel deze optie in op **Niet geconfigureerd** om gebruikers toe te staan wachtwoorden als **1234** of **1111** te maken.
- **Wachtwoordtype**: kies het type wachtwoord of pincode vereist. Uw opties zijn:

  - **Standaard waarde voor apparaat**: wacht woord, numerieke pincode of alfanumerieke pincode vereisen
  - **Numeriek**: wacht woord of numerieke pincode vereisen
  - **Alfanumeriek**: een wacht woord of alfanumerieke pincode vereisen. Kies ook de **complexiteit van het wacht woord**: 
    
    - **Cijfers en kleine letters vereisen**
    - **Cijfers, kleine letters en hoofd letters vereisen**
    - **Cijfers, kleine letters, hoofdletters en speciale tekens vereisen**

    > [!TIP]
    > Het alfanumerieke wachtwoord beleid kan ingewikkeld zijn. Wij raden beheerders aan om de Csp's te lezen voor meer informatie:
    >
    > - [DeviceLock/AlphanumericDevicePasswordRequired CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-devicelock#devicelock-alphanumericdevicepasswordrequired)
    > - [DeviceLock/MinDevicePasswordComplexCharacters CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-devicelock#devicelock-mindevicepasswordcomplexcharacters)

- **Minimale wachtwoordlengte**: voer het minimale aantal cijfers of tekens aan waaruit het wachtwoord moet bestaan.
- **Maximum aantal minuten van inactiviteit voordat wachtwoord is vereist**: geef aan na hoeveel niet-actieve tijd de gebruiker het wachtwoord opnieuw moet invoeren.
- **Wachtwoordverlooptijd (dagen)** : voer het aantal dagen in (van 1 tot 730) waarna het wachtwoord verloopt en gebruikers een nieuw wachtwoord moeten maken.
- **Aantal eerdere wachtwoorden dat niet opnieuw mag worden gebruikt**: voer het aantal eerder gebruikte wachtwoorden in dat niet opnieuw mag worden gebruikt.
- **Wachtwoord vereisen wanneer het apparaat wordt geactiveerd vanuit een niet-actieve status (Mobile en Holographic)** : afdwingen dat gebruikers het wachtwoord invoeren telkens wanneer het apparaat wordt geactiveerd vanuit een niet-actieve status.

  > [!IMPORTANT]
  > Als de wachtwoordvereiste op een Windows-bureaublad wordt gewijzigd, heeft dit een invloed op gebruikers de volgende keer dat ze zich aanmelden, omdat het apparaat op dat moment van niet-actief naar actief gaat. Gebruikers met wachtwoorden die aan de vereisten voldoen, worden nog steeds gevraagd hun wachtwoord te wijzigen.

### <a name="encryption"></a>Versleuteling

- **Versleuteling van gegevensopslag op een apparaat**: kies **Vereisen** om gegevensopslag op uw apparaten te versleutelen.

  > [!NOTE]
  > Met de instelling **Versleuteling van gegevensopslag op een apparaat** wordt algemeen gecontroleerd of er op het apparaat wordt versleuteld. Voor betere versleutelingsinstelling kunt u overwegen om **BitLocker vereisen** te gebruiken. Hierbij wordt gebruikgemaakt van de Windows-apparaatstatusverklaring om de Bitlocker-status op TPM-niveau te valideren.

### <a name="device-security"></a>Apparaatbeveiliging

- **Firewall**: Stel deze optie in op **vereist** om de micro soft Defender firewall in te scha kelen en te voor komen dat gebruikers deze uitschakelen. **Niet geconfigureerd** (standaard) heeft geen invloed op de micro soft Defender firewall en de bestaande instellingen worden niet gewijzigd.

  [CSP van Firewall](https://docs.microsoft.com/windows/client-management/mdm/firewall-csp)

  > [!NOTE]
  > Als het apparaat direct wordt gesynchroniseerd nadat het systeem opnieuw is opgestart of als het activeren vanuit de slaap stand direct wordt gesynchroniseerd, wordt deze instelling mogelijk gerapporteerd als **fout**. Dit scenario heeft mogelijk geen invloed op de algehele status van de apparaatcompatibiliteit. Als u de nalevings status opnieuw wilt evalueren, [synchroniseert u het apparaat](https://docs.microsoft.com/intune-user-help/sync-your-device-manually-windows)hand matig.

- **Trusted Platform Module (TPM)** : als u deze instelling instelt op **vereist**, controleert intune de versie op naleving. Het apparaat is compatibel als de versie van de TPM-chip groter is dan 0 (nul). Het apparaat is niet compatibel als er geen TPM-versie op het apparaat is. Wanneer dit **niet is geconfigureerd**, controleert intune het apparaat niet op een TPM-chip versie.

  [DeviceStatus CSP-DeviceStatus/TPM/SpecificationVersion-knoop punt](https://docs.microsoft.com/windows/client-management/mdm/devicestatus-csp)
  
- **Antivirus**: als deze optie is ingesteld op **Vereisen**, kunt u de naleving controleren met behulp van antivirusoplossingen die zijn geregistreerd bij [Azure Security Center](https://blogs.windows.com/windowsexperience/2017/01/23/introducing-windows-defender-security-center/), zoals Symantec en Microsoft Defender. Als dit **niet is geconfigureerd**, controleert Intune niet of er AV-oplossingen op het apparaat zijn geïnstalleerd.
- **Antispyware**: als deze optie is ingesteld op **Vereisen**, kunt u de naleving controleren met behulp van antispyware-oplossingen die zijn geregistreerd bij [Azure Security Center](https://blogs.windows.com/windowsexperience/2017/01/23/introducing-windows-defender-security-center/), zoals Symantec en Microsoft Defender. Als dit **niet is geconfigureerd**, controleert Intune niet of er antispywareoplossingen op het apparaat zijn geïnstalleerd.

### <a name="defender"></a>Defender

- **Micro soft Defender antimalware**: Stel in dat de micro soft Defender anti-malware-service **moet worden ingeschakeld** en voor komen dat gebruikers deze uitschakelen. **Niet geconfigureerd** (standaard) heeft geen invloed op de service of de bestaande instellingen wijzigen.
- **Minimale versie van micro soft Defender antimalware**: Voer de mini maal toegestane versie van de micro soft Defender anti-malware-service in. Voer bijvoorbeeld `4.11.0.0` in. Als dit veld leeg blijft, kan elke versie van de micro soft Defender anti-malware-service worden gebruikt.
- **Micro soft Defender antimalware Security Intelligence up-to-date**: Hiermee beheert u de Windows-beveiligings virus-en bedreigings beveiligings updates op de apparaten. **Vereisen dat** de beveiligings informatie van micro soft Defender up-to-date is. **Niet geconfigureerd** (standaard) dwingt geen vereisten af.

  [Beveiligings updates voor micro soft Defender anti virus en andere micro soft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates) bevat meer informatie over de beveiligings informatie.

- **Real-time beveiliging**: **Hiermee** schakelt u de real-time beveiliging in, die scant op malware, spyware en andere ongewenste software. **Niet geconfigureerd** (standaard) heeft geen invloed op deze functie en de bestaande instellingen worden niet gewijzigd.

  [Defender/AllowRealtimeMonitoring CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowrealtimemonitoring)

## <a name="microsoft-defender-atp"></a>Microsoft Defender ATP

- **Vereisen dat het apparaat de machinerisicoscore niet overschrijdt**: gebruik deze instelling om de risicobeoordeling uit uw diensten voor verdediging tegen bedreigingen te gebruiken als voorwaarde voor naleving. Kies het maximaal toegestane bedreigingsniveau:

  - **Wissen**: deze optie is het veiligst, omdat het apparaat geen bedreigingen kan hebben. Als een van de bedreigingsniveaus voor het apparaat wordt gedetecteerd, wordt het apparaat geëvalueerd als niet-conform.
  - **Laag**: het apparaat wordt als compatibel geëvalueerd als er bedreigingen van een laag niveau aanwezig zijn. Als een hoger niveau wordt aangetroffen, krijgt het apparaat de status niet-compatibel.
  - **Gemiddeld**: het apparaat wordt als conform geëvalueerd als bestaande bedreigingen op het apparaat van laag of gemiddeld niveau zijn. Als bedreigingen met hoog niveau worden aangetroffen op het apparaat, wordt het apparaat als niet-conform beoordeeld.
  - **Hoog**: deze optie is het minst veilig, omdat alle bedreigingsniveaus zijn toegestaan. Deze optie kan handig zijn als u deze alleen gebruikt voor rapportagedoeleinden.
  
  Zie [Microsoft Defender ATP met voorwaardelijke toegang inschakelen](advanced-threat-protection.md) als u Microsoft Defender ATP (Advanced Threat Protection) wilt gebruiken tegen bedreigingen.

Selecteer **OK** > **Maken** om uw wijzigingen op te slaan.

## <a name="windows-holographic-for-business"></a>Windows Holographic for Business

Windows Holographic for Business gebruikt het **Windows 10 en hoger**-platform. De volgende instelling wordt in Windows Holographic for Business ondersteund:

- **Systeembeveiliging** > **Versleuteling** > **Versleuteling van opslag van gegevens op apparaat**.

Zie [Verify device encryption](https://docs.microsoft.com/hololens/hololens-encryption#verify-device-encryption) (Apparaatversleuteling controleren) om apparaatversleuteling te controleren op de Microsoft HoloLens.

## <a name="surface-hub"></a>Surface Hub

Surface Hub gebruikt het **Windows 10 en hoger**-platform. Surface Hubs worden ondersteund voor naleving en voorwaardelijke toegang. Voor het inschakelen van deze functies in Surface Hubs raden we u aan [Automatische inschrijving van Windows 10 in te schakelen](../enrollment/windows-enroll.md) in Intune (hiervoor is Microsoft Azure Active Directory (Azure AD) vereist) en te streven naar Surface Hub-apparaten als apparaatgroepen. Surface Hubs moeten zijn gekoppeld aan Azure AD om naleving en voorwaardelijke toegang te laten werken.

Zie [inschrijving voor Windows-apparaten instellen](../enrollment/windows-enroll.md) voor hulp.

## <a name="next-steps"></a>Volgende stappen

- [Voeg acties voor niet-conforme apparaten toe](actions-for-noncompliance.md) en [gebruik bereiktags om beleidsregels te filteren](../fundamentals/scope-tags.md).
- [Controleer uw nalevingsbeleid](compliance-policy-monitor.md).
- Zie de [Instellingen voor nalevingsbeleid voor Windows 8.1-apparaten](compliance-policy-create-windows-8-1.md).
