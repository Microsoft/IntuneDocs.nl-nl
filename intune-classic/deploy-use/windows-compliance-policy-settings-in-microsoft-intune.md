---
title: Instellingen voor nalevingsbeleid voor Windows-apparaten
description: Dit onderwerp bevat informatie over de regels en instellingen die u kunt configureren voor een nalevingsbeleid voor Windows-apparaten.
keywords: ''
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/15/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f996842c-e9a4-4819-acb4-ee66e8fb35b8
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 6a54943873a6af158badb92cef4610e54fc8889b
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2018
---
# <a name="compliance-policy-settings-for-windows-devices-in-microsoft-intune"></a>Instellingen voor nalevingsbeleid voor Windows-apparaten in Microsoft Intune

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

De beleidsinstellingen die in dit onderwerp worden beschreven, zijn van toepassing op apparaten waarop het Windows-besturingssysteem wordt uitgevoerd. In de volgende secties worden de ondersteunde versies van Windows beschreven.

Als u op zoek bent naar informatie over andere platforms, selecteert u een van de volgende opties:
> [!div class="op_single_selector"]
> - [Instellingen voor nalevingsbeleid voor iOS-apparaten](ios-compliance-policy-settings-in-microsoft-intune.md)
> - [Instellingen voor nalevingsbeleid voor Android-apparaten](android-compliance-policy-settings-in-microsoft-intune.md)
> - [Instellingen voor nalevingsbeleid voor Android for Work](afw-compliance-policy-settings-in-microsoft-intune.md)

## <a name="compliance-policy-settings-for-windows-phone-devices"></a>Instellingen voor nalevingsbeleid voor Windows Phone-apparaten
De instellingen in deze sectie worden ondersteund op Windows Phone 8.1 en hoger.

### <a name="system-security-settings"></a>Systeembeveiligingsinstellingen
#### <a name="password"></a>Wachtwoord
- **Een wachtwoord vereisen voor het ontgrendelen van mobiele apparaten:** stel deze optie in op **Ja** als u de gebruiker wilt verplichten een wachtwoord in te voeren om toegang te krijgen tot hun apparaat.

- **Eenvoudige wachtwoorden toestaan:** stel deze optie in op **Ja** zodat de gebruiker een eenvoudig wachtwoord kan maken, zoals **1234** of **1111**.

-  **Minimale wachtwoordlengte**: hiermee geeft u het minimale aantal cijfers of tekens aan waaruit het wachtwoord van de gebruiker moet bestaan.
- **Vereist wachtwoordtype**: geef aan of de gebruiker een **alfanumeriek** of een **numeriek** wachtwoord moet maken.

  Bij Windows-apparaten die met een Microsoft-account toegankelijk zijn, kan het nalevingsbeleid geen goede controle uitvoeren als de minimale wachtwoordlengte langer is dan acht tekens of als het minimale aantal tekensets meer is dan twee.

- **Minimum aantal tekensets:** als **Vereist wachtwoordtype** is ingesteld op **Alfanumeriek**, wordt met deze instelling het minimum aantal tekensets opgegeven waaruit het wachtwoord moet bestaan. De vier tekensets zijn:
  -   Kleine letters
  -   Hoofdletters
  -   Symbolen
  -   Getallen

  Als u hiervoor een hogere waarde instelt, moet de gebruiker een wachtwoord maken dat complexer is. Bij Windows-apparaten die met een Microsoft-account toegankelijk zijn, kan het nalevingsbeleid geen goede controle uitvoeren als de minimale wachtwoordlengte langer is dan acht tekens of als het minimale aantal tekensets meer is dan twee.

- **Minuten inactief voordat wachtwoord is vereist:** deze instelling geeft aan na hoeveel niet-actieve tijd gebruikers hun wachtwoord opnieuw moeten invoeren.

- **Wachtwoord verloopt (in dagen):** selecteer het aantal dagen waarna het wachtwoord van gebruikers verloopt en ze een nieuw wachtwoord moeten maken.

- **Wachtwoordgeschiedenis onthouden**: gebruik deze instelling in combinatie met **Wachtwoorden niet opnieuw gebruiken** om te voorkomen dat gebruikers eerder gebruikte wachtwoorden opnieuw gebruiken.

- **Wachtwoorden niet opnieuw gebruiken:** als **Wachtwoordgeschiedenis onthouden** is geselecteerd, geeft u het aantal eerder gebruikte wachtwoorden op dat niet opnieuw kan worden gebruikt.
- **Wachtwoord vereisen wanneer het apparaat wordt geactiveerd vanuit een niet-actieve status:** gebruik deze instelling samen met de instelling **Minuten van inactiviteit voordat wachtwoord vereist is**. De gebruiker wordt gevraagd een wachtwoord op te geven om toegang te krijgen tot een apparaat dat inactief is geweest gedurende de tijd die is opgegeven bij de instelling **Minuten van inactiviteit voordat wachtwoord vereist is**.

  > [!NOTE]
  > Deze instelling geldt alleen voor Windows 10 Mobile-apparaten.

#### <a name="encryption"></a>Versleuteling
- **Versleuteling vereisen op een mobiel apparaat:** stel deze optie in op **Ja** als u wilt dat apparaten moeten worden versleuteld om verbinding te maken met resources.

### <a name="device-health-settings"></a>Instellingen voor de status van het apparaat
- **Vereisen dat apparaten worden gerapporteerd als goed:** u kunt een regel instellen om te vereisen dat **Windows 10 Mobile**-apparaten als goed moeten worden gerapporteerd bij nieuw of bestaand nalevingsbeleid.  Als deze instelling is ingeschakeld, worden Windows 10-apparaten via de Health Attestation-service (HAS) beoordeeld op de volgende gegevenspunten:
  -  **BitLocker is ingeschakeld:** wanneer BitLocker is ingeschakeld, kan het apparaat gegevens die zijn opgeslagen op de schijf beschermen tegen onbevoegde toegang wanneer het systeem naar de sluimerstand overschakelt of wordt uitgeschakeld. Windows BitLocker-stationsversleuteling versleutelt alle gegevens die zijn opgeslagen op het volume met het Windows-besturingssysteem. BitLocker gebruikt de TPM om het Windows-besturingssysteem en de gebruikersgegevens te beveiligen. Met BitLocker kan worden voorkomen dat met een computer kan worden geknoeid, zelfs als deze zonder toezicht is, kwijtgeraakt is of gestolen is. Als de computer is uitgerust met een compatibele TPM, gebruikt BitLocker de TPM om de versleutelingssleutels te vergrendelen waarmee de gegevens worden beschermd. Als gevolg hiervan zijn de sleutels niet toegankelijk totdat de TPM de status van de computer heeft gecontroleerd.
  -  **Code-integriteit is ingeschakeld:** code-integriteit is een functie die voortdurend de integriteit valideert van een stuurprogramma- of systeembestand wanneer dat bestand in het geheugen wordt geladen. Via deze functie wordt gedetecteerd of een niet-ondertekend stuurprogramma- of systeembestand in de kernel is geladen. Ook wordt gedetecteerd of een systeembestand is gewijzigd door schadelijke software die wordt uitgevoerd door een gebruikersaccount met beheerdersbevoegdheden.
  - **Beveiligd opstarten is ingeschakeld:** als beveiligd opstarten is ingeschakeld, wordt het systeem gedwongen om in een vertrouwde fabrieksstatus op te starten. Als beveiligd opstarten is ingeschakeld, moeten de belangrijkste onderdelen van de computer de juiste cryptografische handtekeningen hebben die worden vertrouwd door de organisatie die het apparaat heeft gemaakt. De UEFI-firmware verifieert dit voordat de computer kan worden opgestart. Als er bestanden zijn gemanipuleerd, waardoor de handtekening ongeldig is geworden, kan het systeem niet worden opgestart.

  > [!IMPORTANT]
  > Windows-apparaten bieden geen ondersteuning voor **Early Launch Anti-Malware** (ELAM)-software van derden als onderdeel van de apparaatstatusverklaring.

  Zie [Health Attestation CSP](https://msdn.microsoft.com/library/dn934876.aspx) voor meer informatie over de werking van de HAS-service.
  ###  <a name="device-property-settings"></a>Instellingen voor apparaateigenschappen
- **Minimale versie van het besturingssysteem die is vereist**: wanneer een apparaat niet voldoet aan de minimumvereisten met betrekking tot de versie van het besturingssysteem, wordt het apparaat gerapporteerd als niet-compatibel.
    Er wordt een koppeling met informatie over het uitvoeren van een upgrade weergegeven. Gebruikers kunnen dan kiezen om een upgrade van hun apparaat uit te voeren, waarna ze toegang tot bedrijfsbronnen krijgen.

- **Maximale versie van het besturingssysteem die is toegestaan**: wanneer een apparaat een versie van het besturingssysteem gebruikt die hoger is dan de versie die in de regel is opgegeven, wordt de toegang tot bedrijfsresources geblokkeerd en wordt de gebruiker gevraagd contact op te nemen met de IT-beheerder. Tot er een wijziging is doorgevoerd in de regel die de versie van het besturingssysteem toestaat, kan dit apparaat niet worden gebruikt om toegang tot bedrijfsbronnen te krijgen.


## <a name="compliance-policy-settings-for-windows-pcs"></a>Instellingen voor nalevingsbeleid voor Windows-pc’s
De instellingen in deze sectie worden ondersteund op Windows-pc’s.
### <a name="system-security-settings"></a>Instellingen voor systeembeveiliging
#### <a name="password"></a>Wachtwoord
- **Minimale wachtwoordlengte:** wordt ondersteund op Windows 8.1.

  Hiermee geeft u het minimale aantal cijfers of tekens op waaruit het wachtwoord van de gebruiker moet bestaan.

  Voor apparaten die zijn beveiligd met een Microsoft-account, kunnen met het nalevingsbeleid geen goede controles worden uitgevoerd als **Minimale wachtwoordlengte** meer dan acht tekens is of als **Minimum aantal tekensets** meer dan twee tekens is.

- **Vereist wachtwoordtype:** wordt ondersteund op Windows RT, Windows RT 8.1 en Windows 8.1.

  Geef aan of de gebruiker een **alfanumeriek** of een **numeriek** wachtwoord moet maken.

- **Minimum aantal tekensets:** wordt ondersteund op Windows RT, Windows RT 8.1 en Windows 8.1.

  Als **Vereist wachtwoordtype** is ingesteld op **Alfanumeriek**, wordt hier het minimale aantal tekensets opgegeven waaruit het wachtwoord moet bestaan. De vier tekensets zijn:
  -   Kleine letters
  -   Hoofdletters
  -   Symbolen
  -   Getallen     

  Als u hiervoor een hogere waarde instelt, moet de gebruiker een wachtwoord maken dat complexer is. Voor apparaten die zijn beveiligd met een Microsoft-account, kunnen met het nalevingsbeleid geen goede controles worden uitgevoerd als **Minimale wachtwoordlengte** meer dan acht tekens is of als **Minimum aantal tekensets** meer dan twee tekens is.

- **Minuten van inactiviteit voordat wachtwoord vereist is:** wordt ondersteund op Windows RT, Windows RT 8.1 en Windows 8.1.

  Hiermee geeft u aan na hoeveel niet-actieve tijd gebruikers hun wachtwoord opnieuw moeten invoeren.

- **Wachtwoord verloopt (dagen):** wordt ondersteund op Windows RT, Windows RT 8.1 en Windows 8.1.

  Selecteer het aantal dagen waarna het wachtwoord van gebruikers verloopt en ze een nieuw wachtwoord moeten maken.

- **Wachtwoordgeschiedenis onthouden:** wordt ondersteund op Windows RT, Windows RT 8.1 en Windows 8.1.

  Gebruik deze instelling in combinatie met **Wachtwoorden niet opnieuw gebruiken** om te voorkomen dat gebruikers eerder gebruikte wachtwoorden opnieuw gebruiken.

- **Wachtwoorden niet opnieuw gebruiken:** wordt ondersteund op Windows RT, Windows RT 8.1 en Windows 8.1.

  Als **Wachtwoordgeschiedenis onthouden:** is geselecteerd, geeft u aan hoeveel eerder gebruikte wachtwoorden er niet opnieuw kunnen worden gebruikt.

### <a name="device-health-settings"></a>Instellingen voor de status van het apparaat
- **Vereisen dat apparaten worden gerapporteerd als goed:** wordt ondersteund op Windows 10-apparaten.
U kunt een regel instellen die vereist dat Windows 10-apparaten in nieuw of bestaand nalevingsbeleid als goed moeten worden gerapporteerd. Als deze instelling is ingeschakeld, worden Windows 10-apparaten via de Health Attestation-service (HAS) beoordeeld op de volgende gegevenspunten:
  -  **BitLocker is ingeschakeld:** wanneer BitLocker is ingeschakeld, kan het apparaat gegevens die zijn opgeslagen op de schijf beschermen tegen onbevoegde toegang wanneer het systeem naar de sluimerstand overschakelt of wordt uitgeschakeld. Windows BitLocker-stationsversleuteling versleutelt alle gegevens die zijn opgeslagen op het volume met het Windows-besturingssysteem. BitLocker gebruikt de TPM om het Windows-besturingssysteem en de gebruikersgegevens te beveiligen. Met BitLocker kan worden voorkomen dat met een computer kan worden geknoeid, zelfs als deze zonder toezicht is, kwijtgeraakt is of gestolen is. Als de computer is uitgerust met een compatibele TPM, gebruikt BitLocker de TPM om de versleutelingssleutels te vergrendelen waarmee de gegevens worden beschermd. Als gevolg hiervan zijn de sleutels niet toegankelijk totdat de TPM de status van de computer heeft gecontroleerd.
  -  **Code-integriteit is ingeschakeld:** code-integriteit is een functie die voortdurend de integriteit valideert van een stuurprogramma- of systeembestand wanneer dat bestand in het geheugen wordt geladen. Via deze functie wordt gedetecteerd of een niet-ondertekend stuurprogramma- of systeembestand in de kernel is geladen. Ook wordt gedetecteerd of een systeembestand is gewijzigd door schadelijke software die wordt uitgevoerd door een gebruikersaccount met beheerdersbevoegdheden.
  - **Beveiligd opstarten is ingeschakeld:** als beveiligd opstarten is ingeschakeld, wordt het systeem gedwongen om in een vertrouwde fabrieksstatus op te starten. Als beveiligd opstarten is ingeschakeld, moeten de belangrijkste onderdelen van de computer de juiste cryptografische handtekeningen hebben die worden vertrouwd door de organisatie die het apparaat heeft gemaakt. De UEFI-firmware verifieert dit voordat de computer kan worden opgestart. Als er bestanden zijn gemanipuleerd, waardoor de handtekening ongeldig is geworden, kan het systeem niet worden opgestart.
  - **Early Launch Antimalware is ingeschakeld:** Early Launch Anti-Malware (ELAM) biedt de computers in uw netwerk bescherming wanneer ze worden opgestart en wanneer stuurprogramma’s van derden worden geïnitialiseerd.

  Zie [Health Attestation CSP](https://msdn.microsoft.com/library/dn934876.aspx) voor meer informatie over de werking van de HAS-service.

### <a name="device-property-settings"></a>Instellingen voor apparaateigenschappen
- **Minimale versie van het besturingssysteem die is vereist:** wordt ondersteund op Windows 8.1 en Windows 10.

  Geef hier het nummer van de major.minor.build op. Het versienummer moet overeenkomen met de versie die wordt geretourneerd door de opdracht **winver**.

  Wanneer een apparaat een eerdere versie heeft dan de opgegeven versie van het besturingssysteem, wordt de versie als niet-compatibel gerapporteerd. Er wordt een koppeling met informatie over het uitvoeren van een upgrade weergegeven. Gebruikers kunnen dan kiezen om een upgrade van hun apparaat uit te voeren, waarna ze toegang tot bedrijfsbronnen krijgen.

- **Maximale versie van het besturingssysteem die is toegestaan**: ondersteund op Windows 8.1 en Windows 10.

  Wanneer een apparaat een versie van het besturingssysteem gebruikt dat hoger is dan wat in de regel is bepaald, wordt de toegang tot bedrijfsbronnen geblokkeerd en wordt de gebruiker gevraagd contact op te nemen met zijn IT-beheerder. Tot er een wijziging is doorgevoerd in de regel die de versie van het besturingssysteem toestaat, kan dit apparaat niet worden gebruikt om toegang tot bedrijfsbronnen te krijgen.

Als u de versie van het besturingssysteem wilt vinden die u voor de instellingen **Minimale versie van het besturingssysteem die is vereist** en **Maximale versie van het besturingssysteem die is toegestaan** wilt gebruiken, voert u via de opdrachtregel de opdracht **winver** uit. De opdracht **winver** retourneert de gemelde versie van het besturingssysteem.

- Windows 8.1-pc's retourneren versie **6.3**. Als de besturingssysteemversieregel is ingesteld op Windows 8.1 voor Windows, wordt het apparaat als in strijd met het nalevingsbeleid gerapporteerd, zelfs als het apparaat Windows 8.1 heeft.

- Voor Windows 10-computers moet de versie worden ingesteld op **10.0**, gevolgd door het build-nummer van het besturingssysteem dat wordt geretourneerd door de opdracht **winver**. Dit nummer ziet er bijvoorbeeld zo uit: 10.0.10586.
  > ![Build-versie van het besturingssysteem gemarkeerd in het dialoogvenster Info](./media/ca_win10-os-version.png)
