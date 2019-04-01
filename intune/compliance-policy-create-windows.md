---
title: Naleving controleren op Windows-apparaten in Microsoft Intune - Azure | Microsoft Docs
description: Een nalevingsbeleid voor apparaten van Microsoft Intune configureren voor apparaten met Windows Phone 8.1, Windows 8.1 en hoger, en Windows 10 en hoger. Controleren op naleving van het minimale en maximale vereiste besturingssysteem, wachtwoordbeperkingen en lengte instellen, bitlocker vereisen, controleren op AV-oplossingen van externe partijen (derden), instellen van het aanvaardbare dreigingsniveau en encryptie op de opslag van gegevens, zoals Surface Hub en de Windows Holographic voor bedrijven.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/04/2019
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: e6e82e24f051e64d07487d915ac6fd0848727ecf
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/14/2019
ms.locfileid: "57566808"
---
# <a name="add-a-device-compliance-policy-for-windows-devices-in-intune"></a>Een apparaatnalevingsbeleid maken voor Windows-apparaten in Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Een Intune-beleid voor apparaatcompatibiliteit omvat de regels en instellingen waaraan apparaten moeten voldoen om als compatibel te worden beschouwd. Gebruik dit beleid met voorwaardelijke toegang om toegang tot resources in uw organisatie toe te staan of te blokkeren. U kunt ook apparaatrapporten krijgen en maatregelen nemen voor niet-naleving.

Zie [Aan de slag met apparaatnalevingsbeleid](device-compliance-get-started.md) voor meer informatie over nalevingsbeleid en eventuele vereisten.

In de volgende tabel wordt beschreven hoe niet-compatibele instellingen worden beheerd wanneer een nalevingsbeleid wordt gebruikt in combinatie met beleid voor voorwaardelijke toegang.

---------------------------

| **Beleidsinstelling** | **Windows 8.1 en hoger** | **Windows Phone 8.1 en hoger** |
|----| ----| --- |
| **Configuratie van pincode of wachtwoord** | Hersteld | Hersteld |   
| **Apparaatversleuteling** | Niet van toepassing | Hersteld |   
| **Opengebroken of geroot apparaat** | Niet van toepassing | Niet van toepassing |  
| **E-mailprofiel** | Niet van toepassing | Niet van toepassing |   
| **Minimale versie van het besturingssysteem** | In quarantaine | In quarantaine |   
| **Maximale versie van het besturingssysteem** | In quarantaine | In quarantaine |   
| **Windows Health Attestation** | In quarantaine: Windows 10 en Windows 10 Mobile|Niet van toepassing: Windows 8.1 |

-------------------------------

**Hersteld** = het besturingssysteem van het apparaat dwingt naleving af. (De gebruiker wordt bijvoorbeeld gedwongen een pincode in te stellen.)

**In quarantaine** = het besturingssysteem van het apparaat dwingt geen naleving af. (Bij Android-apparaten bijvoorbeeld wordt de gebruiker niet gedwongen het apparaat te versleutelen.) Als het apparaat niet compatibel is, worden de volgende acties uitgevoerd:

- Het apparaat wordt geblokkeerd als een beleid voor voorwaardelijke toegang van toepassing is voor de gebruiker.
- De bedrijfsportal stelt de gebruiker op de hoogte van eventuele nalevingsproblemen.

## <a name="create-a-device-compliance-policy"></a>Een nalevingsbeleid voor apparaten maken

[!INCLUDE [new-device-compliance-policy](./includes/new-device-compliance-policy.md)]
5. Voor **Platform**, selecteer **Windows Phone 8.1**, **Windows 8.1 en hoger**, of **Windows 10 en hoger**.
6. Kies **Instellingen configureren** om instellingen op te geven voor de **Apparaatstatus**, de **Apparaateigenschappen** en de **Systeembeveiliging**. Selecteer **OK** en **Maken** als u klaar bent.

<!--- 4. Choose **Actions for noncompliance** to say what actions should happen when a device is determined as noncompliant with this policy.
5. In the **Actions for noncompliance** pane, choose **Add** to create a new action.  The action parameters pane allows you to specify the action, email recipients that should receive the notification in addition to the user of the device, and the content of the notification that you want to send.
6. The message template option allows you to create several custom emails depending on when the action is set to take. For example, you can create a message for notifications that are sent for the first time and a different message for final warning before access is blocked. The custom messages that you create can be used for all your device compliance policy.
7. Specify the **Grace period** which determines when that action to take place.  For example, you may want to send a notification as soon as the device is evaluated as noncompliant, but allow some time before enforcing the conditional access policy to block access to company resources like SharePoint online.
8. Choose **Add** to finish creating the action.
9. You can create multiple actions and the sequence in which they should occur. Choose **Ok** when you are finished creating all the actions.--->

## <a name="windows-81-devices-policy-settings"></a>Beleidsinstellingen voor Windows 8.1-apparaten

Deze beleidsinstellingen zijn van toepassing op apparaten met de volgende platforms:

- Windows Phone 8.1
- Windows 8.1 en hoger

### <a name="device-properties"></a>Apparaateigenschappen

- **Minimale versie van het besturingssysteem die is vereist:** wanneer een apparaat niet voldoet aan de minimumvereisten met betrekking tot de versie van het besturingssysteem, wordt dit apparaat gerapporteerd als niet-conform. Er wordt een koppeling met informatie over het uitvoeren van een upgrade weergegeven. Gebruikers kunnen dan kiezen om een upgrade van hun apparaat uit te voeren, waarna ze toegang tot bedrijfsresources krijgen.
- **Maximale versie van het besturingssysteem die is toegestaan**: wanneer een apparaat een versie van het besturingssysteem gebruikt die hoger is dan de versie die in de regel is ingevoerd, wordt de toegang tot bedrijfsresources geblokkeerd. De gebruiker wordt gevraagd contact op te nemen met de IT-beheerder. Het apparaat heeft geen toegang tot organisatieresources totdat u de regel wijzigt zodat de versie van het besturingssysteem is toegestaan.

Windows 8.1-pc's retourneren versie **3**. Als de besturingssysteemversieregel is ingesteld op Windows 8.1 voor Windows, wordt het apparaat als in strijd met het nalevingsbeleid gerapporteerd, zelfs als het apparaat Windows 8.1 heeft.

### <a name="system-security"></a>Systeembeveiliging

#### <a name="password"></a>Wachtwoord

- **Een wachtwoord vereisen voor het ontgrendelen van mobiele apparaten**: **verplicht** gebruikers een wachtwoord in te voeren om toegang te krijgen tot hun apparaat.
- **Eenvoudige wachtwoorden**: stel deze optie in op **Blokkeren** zodat de gebruiker geen eenvoudig wachtwoord kan maken, zoals **1234** of **1111**. Stel deze optie in op **Niet geconfigureerd** om gebruikers toe te staan wachtwoorden als **1234** of **1111** te maken.
- **Minimale wachtwoordlengte**: voer het minimale aantal cijfers of tekens aan waaruit het wachtwoord moet bestaan.

  Voor apparaten waarop Windows wordt uitgevoerd en met een Microsoft-account toegankelijk zijn, kan het nalevingsbeleid niet correct evalueren:
  - Als de minimale wachtwoordlengte langer is dan acht tekens
  - Of als het minimale aantal tekensets meer is dan twee

- **Wachtwoordtype**: kies of een wachtwoord alleen **numerieke** tekens mag bevatten of uit een combinatie van cijfers en andere tekens moet bestaan (**alfanumeriek**).
  
  - **Aantal niet-alfanumerieke tekens in wachtwoord**: als **Vereist wachtwoordtype** is ingesteld op **Alfanumeriek**, wordt met deze instelling het minimale aantal tekensets opgegeven waaruit het wachtwoord moet bestaan. De vier tekensets zijn:
    - Kleine letters
    - Hoofdletters
    - Symbolen
    - Getallen

    Als u een hogere waarde instelt, moet de gebruiker een wachtwoord maken dat complexer is. Voor apparaten die toegankelijk zijn met een Microsoft-account, kan het nalevingsbeleid niet juist worden geëvalueerd:

    - Als de minimale wachtwoordlengte langer is dan acht tekens
    - Of als het minimale aantal tekensets meer is dan twee

- **Maximum aantal minuten van inactiviteit voordat wachtwoord is vereist**: geef aan na hoeveel niet-actieve tijd de gebruiker het wachtwoord opnieuw moet invoeren.
- **Wachtwoord verloopt (in dagen)**: selecteer het aantal dagen waarna het wachtwoord verloopt en gebruikers een nieuw wachtwoord moeten maken.
- **Aantal eerdere wachtwoorden dat niet opnieuw mag worden gebruikt**: voer het aantal eerder gebruikte wachtwoorden in dat niet opnieuw mag worden gebruikt.

#### <a name="encryption"></a>Versleuteling

- **Versleuteling vereisen op een mobiel apparaat**: **vereis** dat het apparaat versleuteld moet zijn om verbinding te maken met gegevensopslag-resources.

## <a name="windows-10-and-later-policy-settings"></a>Beleidsinstellingen Windows 10 en hoger

### <a name="device-health"></a>Device health

- **Vereis BitLocker**: als Bitlocker is ingeschakeld, kan het apparaat gegevens die op de schijf zijn opgeslagen, beveiligen tegen onbevoegde toegang wanneer het systeem wordt uitgeschakeld of overschakelt naar de slaapstand. Windows BitLocker-stationsversleuteling versleutelt alle gegevens die zijn opgeslagen op het volume met het Windows-besturingssysteem. BitLocker gebruikt de TPM om het Windows-besturingssysteem en de gebruikersgegevens te beveiligen. Het helpt ook om te bevestigen dat een computer niet is gemanipuleerd, zelfs als deze zonder toezicht, kwijtgeraakt of gestolen is. Als de computer is uitgerust met een compatibele TPM, gebruikt BitLocker de TPM om de versleutelingssleutels te vergrendelen die de gegevens beschermen. Als gevolg hiervan kunnen de sleutels niet worden gebruikt tot met de TPM de status van de computer is gecontroleerd.
- **Vereis dat Beveiligd opstarten is ingeschakeld op het apparaat**: als beveiligd opstarten is ingeschakeld, wordt het systeem gedwongen om in een vertrouwde fabrieksstatus op te starten. Als beveiligd opstarten is ingeschakeld, moeten de belangrijkste onderdelen van de computer de juiste cryptografische handtekeningen hebben die worden vertrouwd door de organisatie die het apparaat heeft gemaakt. De UEFI-firmware verifieert de digitale handtekening voordat de computer kan worden opgestart. Als de bestanden zijn gemanipuleerd, waardoor de bijbehorende handtekening is beschadigd, kan het systeem niet worden gestart.

  > [!NOTE]
  > De instelling **Vereisen dat beveiligd opstarten wordt ingeschakeld op het apparaat** wordt ondersteund op bepaalde TPM 1.2- en 2.0-apparaten. Voor apparaten die geen ondersteuning bieden voor TPM 2.0 of later, wordt de beleidsstatus in Intune weergegeven als **Niet-conform**. Zie voor meer informatie over de ondersteunde versies [Health Attestation van apparaten](https://docs.microsoft.com/windows/security/information-protection/tpm/trusted-platform-module-overview#device-health-attestation).

- **Vereis code-integriteit**: code-integriteit is een functie die voortdurend de integriteit valideert van een stuurprogramma- of systeembestand wanneer dat bestand in het geheugen wordt geladen. Via deze functie wordt gedetecteerd of een niet-ondertekend stuurprogramma of systeembestand in de kernel is geladen. Ook wordt gedetecteerd of een systeembestand is gewijzigd vanwege schadelijke software die is uitgevoerd via een gebruikersaccount met beheerdersbevoegdheden.

Zie [Health Attestation CSP](https://docs.microsoft.com/windows/client-management/mdm/healthattestation-csp) (CSP-statusverklaring) voor meer informatie over de werking van de HAS-service.

### <a name="device-properties"></a>Apparaateigenschappen

- **Minimale versie van het besturingssysteem**: voer de minimaal toegestane versie in de nummerindeling **major.minor.build.CU** in. Als u de juiste waarde wilt ophalen, opent u een opdrachtprompt en typt u `ver`. De opdracht `ver` retourneert de versie in de volgende indeling:

  `Microsoft Windows [Version 10.0.17134.1]`

  Wanneer een apparaat een eerdere versie heeft dan de ingevoerde versie van het besturingssysteem, wordt de versie als niet-compatibel gerapporteerd. Er wordt een koppeling met informatie over het uitvoeren van een upgrade weergegeven. De eindgebruiker kan kiezen om het apparaat bij te werken. Na het bijwerken zijn de bedrijfsresources toegankelijk.

- **Maximale versie van het besturingssysteem**: voer de maximaal toegestane versie in de nummerindeling **major.minor.build.versienummer** in. Als u de juiste waarde wilt ophalen, opent u een opdrachtprompt en typt u `ver`. De opdracht `ver` retourneert de versie in de volgende indeling:

  `Microsoft Windows [Version 10.0.17134.1]`

  Wanneer een apparaat een versie van het besturingssysteem gebruikt dat hoger is dan wat is ingevoerd in de regel, wordt de toegang tot bedrijfsbronnen geblokkeerd en wordt de gebruiker gevraagd contact op te nemen met de IT-beheerder. Tot er een wijziging is doorgevoerd in de regel om de versie van het besturingssysteem toe te staan, heeft dit apparaat geen toegang tot bedrijfsresources.

- **Minimale versie van het besturingssysteem dat vereist is voor mobiele apparaten**: voer de minimaal toegestane versie in de nummerindeling major.minor.build in.

  Wanneer een apparaat een eerdere versie heeft dan de ingevoerde versie van het besturingssysteem, wordt de versie als niet-compatibel gerapporteerd. Er wordt een koppeling met informatie over het uitvoeren van een upgrade weergegeven. De eindgebruiker kan kiezen om het apparaat bij te werken. Na het bijwerken zijn de bedrijfsresources toegankelijk.

- **Maximale versie van het besturingssysteem dat vereist is voor mobiele apparaten**: voer de maximaal toegestane versie in de nummerindeling major.minor.build in.

  Wanneer een apparaat een versie van het besturingssysteem gebruikt dat hoger is dan de ingevoerde versie, wordt de toegang tot bedrijfsbronnen geblokkeerd en wordt de gebruiker gevraagd contact op te nemen met de IT-beheerder. Tot er een wijziging is doorgevoerd in de regel om de versie van het besturingssysteem toe te staan, heeft dit apparaat geen toegang tot bedrijfsresources.

- **Geldig besturingssysteem-builds**: voer een bereik in voor de acceptabele versies van besturingssystemen, met inbegrip van een minimum en maximum. U kunt ook een bestandslijst met door komma's gescheiden waarden (CSV) met de toegestane versienummers van besturingssystemen **exporteren**.

### <a name="configuration-manager-compliance"></a>Configuration Manager-compatibiliteit

Geldt alleen voor gezamenlijk beheerde apparaten met Windows 10 en hoger. Apparaten met alleen Intune retourneren de status Niet beschikbaar.

- **Het nalevingsbeleid voor apparaten in System Center Configuration Manager vereist**: kies **vereisen** om af te dwingen van alle instellingen (configuratie-items) in System Center Configuration Manager aan het beleid voldoen. 

  U kunt bijvoorbeeld vereisen dat alle software-updates worden geïnstalleerd op apparaten. Deze vereiste heeft in Configuration Manager de status 'Geïnstalleerd'. Als programma's op het apparaat een onbekende status hebben, is het apparaat niet-compatibel in Intune.
  
  Wanneer de status **Niet geconfigureerd** is, wordt in Intune niet gezocht naar Configuration Manager-instellingen voor naleving.

### <a name="system-security-settings"></a>Systeembeveiligingsinstellingen

#### <a name="password"></a>Wachtwoord

- **Een wachtwoord vereisen voor het ontgrendelen van mobiele apparaten**: **verplicht** gebruikers een wachtwoord in te voeren om toegang te krijgen tot hun apparaat.
- **Eenvoudige wachtwoorden**: stel deze optie in op **Blokkeren** zodat de gebruiker geen eenvoudig wachtwoord kan maken, zoals **1234** of **1111**. Stel deze optie in op **Niet geconfigureerd** om gebruikers toe te staan wachtwoorden als **1234** of **1111** te maken.
- **Wachtwoordtype**: kies of een wachtwoord alleen **numerieke** tekens mag bevatten of uit een combinatie van cijfers en andere tekens moet bestaan (**alfanumeriek**).

  - **Aantal niet-alfanumerieke tekens in wachtwoord**: als **Vereist wachtwoordtype** is ingesteld op **Alfanumeriek**, wordt met deze instelling het minimale aantal tekensets opgegeven waaruit het wachtwoord moet bestaan. De vier tekensets zijn:
    - Kleine letters
    - Hoofdletters
    - Symbolen
    - Getallen

    Als u een hogere waarde instelt, moet de gebruiker een wachtwoord maken dat complexer is.

- **Minimale wachtwoordlengte**: voer het minimale aantal cijfers of tekens aan waaruit het wachtwoord moet bestaan.
- **Maximum aantal minuten van inactiviteit voordat wachtwoord is vereist**: geef aan na hoeveel niet-actieve tijd de gebruiker het wachtwoord opnieuw moet invoeren.
- **Wachtwoord verloopt (in dagen)**: selecteer het aantal dagen waarna het wachtwoord verloopt en gebruikers een nieuw wachtwoord moeten maken.
- **Aantal eerdere wachtwoorden dat niet opnieuw mag worden gebruikt**: voer het aantal eerder gebruikte wachtwoorden in dat niet opnieuw mag worden gebruikt.
- **Wachtwoord vereisen wanneer het apparaat wordt geactiveerd vanuit een niet-actieve status (Mobile en Holographic)**: afdwingen dat gebruikers het wachtwoord invoeren telkens wanneer het apparaat wordt geactiveerd vanuit een niet-actieve status.

#### <a name="encryption"></a>Versleuteling

- **Versleuteling van gegevensopslag op een apparaat**: kies **Vereisen** om gegevensopslag op uw apparaten te versleutelen.

  > [!NOTE]
  > Met de instelling **Versleuteling van gegevensopslag op een apparaat** wordt algemeen gecontroleerd of er op het apparaat wordt versleuteld. Voor betere versleutelingsinstelling kunt u overwegen om **BitLocker vereisen** te gebruiken. Hierbij wordt gebruikgemaakt van de Windows-apparaatstatusverklaring om de Bitlocker-status op TPM-niveau te valideren.

#### <a name="device-security"></a>Apparaatbeveiliging

- **Antivirus**: als deze optie is ingesteld op **Vereisen**, kunt u de naleving controleren met behulp van antivirusoplossingen die zijn geregistreerd bij [Azure Security Center](https://blogs.windows.com/windowsexperience/2017/01/23/introducing-windows-defender-security-center/), zoals Symantec en Windows Defender. Als dit **niet is geconfigureerd**, controleert Intune niet of er AV-oplossingen op het apparaat zijn geïnstalleerd.
- **Antispyware**: als deze optie is ingesteld op **Vereisen**, kunt u de naleving controleren met behulp van antivirusoplossingen die zijn geregistreerd bij [Azure Security Center](https://blogs.windows.com/windowsexperience/2017/01/23/introducing-windows-defender-security-center/) en Windows Defender. Als dit **niet is geconfigureerd**, controleert Intune niet of er antispywareoplossingen op het apparaat zijn geïnstalleerd.

### <a name="windows-defender-atp"></a>Windows Defender ATP

- **Vereisen dat het apparaat de machinerisicoscore niet overschrijdt**: gebruik deze instelling om de risicobeoordeling uit uw diensten voor verdediging tegen bedreigingen te gebruiken als voorwaarde voor naleving. Kies het maximaal toegestane bedreigingsniveau:
  - **Wissen**: deze optie is het veiligst, omdat het apparaat geen bedreigingen kan hebben. Als een van de bedreigingsniveaus voor het apparaat wordt gedetecteerd, wordt het apparaat geëvalueerd als niet-compatibel.
  - **Laag**: het apparaat wordt als compatibel geëvalueerd als er bedreigingen van een laag niveau aanwezig zijn. Als een hoger niveau wordt aangetroffen, krijgt het apparaat de status niet-compatibel.
  - **Gemiddeld**: het apparaat wordt als conform geëvalueerd als bestaande bedreigingen op het apparaat van laag of gemiddeld niveau zijn. Als bedreigingen met hoog niveau worden aangetroffen op het apparaat, wordt het apparaat als niet-compatibel beoordeeld.
  - **Hoog**: deze optie is het minst veilig, omdat alle bedreigingsniveaus zijn toegestaan. Deze optie kan handig zijn als u deze alleen gebruikt voor rapportagedoeleinden.
  
  Zie [Windows Defender ATP met voorwaardelijke toegang inschakelen](advanced-threat-protection.md) als u Windows Defender ATP (Advanced Threat Protection) wilt gebruiken tegen bedreigingen.

## <a name="windows-holographic-for-business"></a>Windows Holographic for Business

Windows Holographic for Business gebruikt het **Windows 10 en hoger**-platform. De volgende instelling wordt in Windows Holographic for Business ondersteund:

- **Systeembeveiliging** > **Versleuteling** > **Versleuteling van opslag van gegevens op apparaat**.

Zie [Verify device encryption](https://docs.microsoft.com/hololens/hololens-encryption#verify-device-encryption) (Apparaatversleuteling controleren) om apparaatversleuteling te controleren op de Microsoft HoloLens.

## <a name="surface-hub"></a>Surface Hub
Surface Hub gebruikt het **Windows 10 en hoger**-platform. Surface Hubs worden ondersteund voor naleving en voorwaardelijke toegang. Voor het inschakelen van deze functies op Surface Hubs raden we u aan [Automatische inschrijving van Windows 10 in te schakelen](windows-enroll.md) bij Intune (dit vereist ook Azure AD (Azure Active Directory)) en te streven naar Surface Hub-apparaten als apparaatgroepen. Surface Hubs moeten zijn gekoppeld aan Azure AD om naleving en voorwaardelijke toegang te laten werken.

Zie [inschrijving voor Windows-apparaten instellen](windows-enroll.md) voor hulp.

## <a name="assign-user-or-device-groups"></a>Groepen gebruikers of apparaten toewijzen

1. Kies een beleid dat u hebt geconfigureerd. Bestaande beleidsregels bevinden zich in **Apparaatcompatibiliteit** > **Beleid**.
2. Kies het beleid en kies **Toewijzingen**. U kunt Azure Active Directory-beveiligingsgroepen (AD) opnemen of uitsluiten.
3. Kies **Geselecteerde groepen** om uw Azure AD-beveiligingsgroepen te zien. Selecteer de gebruikersgroepen waarop u dit beleid wilt toepassen en kies **Opslaan** om het beleid te implementeren.

U hebt het beleid toegepast op gebruikers. De apparaten die worden gebruikt door de gebruikers op wie het beleid wordt toegepast, worden gecontroleerd om te zien of ze voldoen aan de vereisten.

## <a name="next-steps"></a>Volgende stappen
[E-mail automatiseren en acties voor niet-conforme apparaten toevoegen](actions-for-noncompliance.md)  
[Nalevingsbeleid voor Intune-apparaten controleren](compliance-policy-monitor.md)
