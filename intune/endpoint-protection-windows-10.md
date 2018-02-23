---
title: Instellingen voor Intune Endpoint Protection voor Windows 10
titlesuffix: Azure portal
description: Lees hier alles over de Intune-instellingen die u kunt gebruiken voor het beheren van instellingen voor eindpuntbeveiliging op Windows 10-apparaten, zoals BitLocker.
keywords: 
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 01/16/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3af7c91b-8292-4c7e-8d25-8834fcf3517a
ms.reviewer: ilwu
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 35c33fb189187a678efa04d10706fe752d683e17
ms.sourcegitcommit: 6d69403266dbcb31c879432719798935c94917fa
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/19/2018
---
# <a name="endpoint-protection-settings-for-windows-10-and-later-in-microsoft-intune"></a>Instellingen voor de beveiliging van eindpunten voor Windows 10 en hoger in Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Via het profiel voor eindpuntbeveiliging kunt u beveiligingsfuncties op Windows 10-apparaten beheren, zoals BitLocker en Windows Defender.

Gebruik de informatie in dit onderwerp om profielen voor eindpuntbeveiliging te maken.

> [!Note]
> Deze instellingen worden niet ondersteund in de edities Home en Professional van Windows 10.

## <a name="create-an-endpoint-protection-profile"></a>Een profiel voor eindpuntbeveiliging maken

1. Meld u aan bij Azure-portal.
2. Kies **Meer services** > **Bewaking en beheer** > **Intune**.
3. Kies op de blade **Intune** de optie **Apparaatconfiguratie**.
2. Kies **Beheren** > **Profielen** op de blade **Apparaatconfiguratie**.
3. Kies **Profiel maken** op de blade Profielen.
4. Voer op de blade **Profiel maken** een **naam** en **beschrijving** in voor het profiel voor de apparaatfuncties.
5. Selecteer in de vervolgkeuzelijst **Platform** de optie **Windows 10 en hoger**.
6. Kies **Endpoint Protection** in de vervolgkeuzelijst **Profieltype**.
7. Configureer de gewenste instellingen. Gebruik de informatie in dit onderwerp om te begrijpen wat elke instelling doet. Als u klaar bent, kiest u **OK**.
8. Ga terug naar de blade **Profiel maken** en kies **Maken**.

Het profiel wordt gemaakt en wordt weergegeven op de blade met de profielenlijst.

## <a name="windows-defender-application-guard"></a>Windows Defender Application Guard

Application Guard is alleen beschikbaar voor apparaten met de 64 bitsversie van Windows 10. Met dit profiel wordt een Win32-onderdeel geïnstalleerd om Application Guard te activeren.

- **Application Guard**: open niet-goedgekeurde sites in een Hyper-V gevirtualiseerde browsercontainer.
- **Klembordgedrag**: kies welke kopieer- en plakbewerkingen zijn toegestaan tussen de lokale pc en de virtuele browser van Application Guard.
- **Externe inhoud op Enterprise-sites**: voorkom dat inhoud van niet-goedgekeurde websites wordt geladen.
- **Afdrukken vanuit virtuele browser**: sta toe dat PDF-, XPS- en lokale of netwerkprinters inhoud vanuit de virtuele browser kunnen afdrukken.
- **Logoeken verzamelen**: verzamel logboeken voor gebeurtenissen die zich voordoen in een Application Guard-browsersessie.
- **Door de gebruiker gegenereerde browsergegevens behouden**: sta toe dat gebruikersgegevens (zoals wachtwoorden, favorieten en cookies) worden opgeslagen die zijn gemaakt tijdens een virtuele browsersessie met Application Guard.


## <a name="windows-defender-firewall"></a>Windows Defender Firewall

### <a name="global-settings"></a>Globale instellingen

Deze instellingen gelden voor alle netwerktypen.

- **File Transfer Protocol**: blokkeer stateful FTP.
- **Niet-actieve tijd voordat beveiligingskoppeling wordt verwijderd**: beveiligingskoppelingen worden verwijderd nadat gedurende *n* seconden geen netwerkverkeer wordt gedetecteerd.
- **Vooraf-gedeelde sleutels coderen**: codeer vooraf-gedeelde sleutels met UTF-8.
- **IPsec-uitzonderingen**: hiermee configureert u specifiek verkeer om te worden vrijgesteld voor het uitvoeren van IPsec, waaronder **ICMP-type-codes voor IPv6 detecteren met Neighbor**, **ICMP**, **ICMP-type-codes voor IPv6 detecteren met Router** en  **DHCP-netwerkverkeer via IPv4 en IPv6**.
- **Controle van certificaatintrekkingslijsten**: stel een waarde in voor het afdwingen van controle van certificaatintrekkingslijsten, zoals **CRL-controle uitschakelen**, **CRL-verificatie mislukt alleen bij alleen ingetrokken certificaat** en **CRL-verificatie mislukt bij elke fout die wordt aangetroffen**.
- **Verificatieset opportunistisch afstemmen per sleutelmodule**: stel sleutelmodules in om de volledige verificatieset te negeren als de modules geen ondersteuning bieden voor alle verificatiepakketten in de betreffende set.
- **Pakketten in wachtrij plaatsen**: Geef op hoe schalen voor software aan de ontvangstzijde wordt ingeschakeld voor versleuteld ontvangen en ongecodeerd doorsturen in het scenario voor de IPsec-tunnelgateway. Hierdoor wordt gegarandeerd dat de pakketvolgorde behouden blijft.

### <a name="network-settings"></a>Netwerkinstellingen

Deze instellingen zijn van toepassing op specifieke netwerktypen, waaronder **Domeinnetwerk (werkplek)**, **Privénetwerk (detecteerbaar)** en **Openbaar netwerk (niet-detecteerbaar)**.

#### <a name="general-settings"></a>Algemene instellingen

- **Windows Defender Firewall**: schakel deze instelling in om netwerkverkeer te blokkeren.
- **Verborgen modus**: blokkeer de firewall in de verborgen modus. Als u de firewall blokkeert, blokkeert u ook **Uitsluiting van beveiligd IPsec-pakket**.
- **Afgeschermd**: als deze instelling is ingeschakeld, blokkeert de firewallinstelling al het binnenkomende verkeer.
- **Unicast-antwoorden voor multicast-broadcasts**: Blokkeer unicast-antwoorden voor multicast-broadcasts. Doorgaans wilt u geen unicast-antwoorden voor multicast- of broadcastberichten ontvangen. Dergelijke antwoorden kunnen namelijk duiden op een DoS-aanval (Denial of Service) of op een aanvaller die een bekende livecomputer wilt testen.
- **Binnenkomende meldingen**: blokkeer meldingen zodat deze niet aan gebruikers worden weergegeven wanneer een toepassing wordt geblokkeerd voor het luisteren naar een poort.
- **De standaardactie voor binnenkomende verbindingen**: blokkeer de standaardactie die door firewalls wordt uitgevoerd op binnenkomende verbindingen.

#### <a name="rule-merging"></a>Regel samenvoegen

- **Windows Defender Firewall-regels uit het lokale archief voor de gemachtigde toepassing**: stel in dat gemachtigde firewallregels in het lokale archief worden herkend en afgedwongen.
- **Algemene poortfirewallregels van Windows Defender uit het lokale archief**: stel in dat algemene poortfirewallregels in het lokale archief worden herkend en afgedwongen.
- **Windows Defender Firewall-regels uit het lokale archief**: stel in dat algemene firewallregels in het lokale archief worden herkend en afgedwongen.
- **IPsec-regels vanuit het lokale archief**: pas beveiligingsregels voor verbindingen uit het lokale archief toe, ongeacht het schema of de versies van de beveiligingsregels voor verbindingen.

## <a name="windows-defender-smartscreen-settings"></a>Instellingen voor Windows Defender SmartScreen

- **SmartScreen voor apps en bestanden**: schakel Windows SmartScreen in voor het uitvoeren van bestanden en apps.
- **Niet-geverifieerde uitvoering van bestanden**: voorkom dat de eindgebruiker bestanden kan uitvoeren die niet zijn geverifieerd door Windows SmartScreen.

## <a name="windows-encryption"></a>Windows-versleuteling

### <a name="windows-settings"></a>Windows-instellingen

Deze instellingen gelden voor alle versies van Windows 10.

- **Apparaten versleutelen**: als deze instelling is ingeschakeld, krijgen gebruikers opdracht om apparaatversleuteling in te schakelen. Bovendien moeten ze bevestigen dat er geen versleuteling van een andere provider is ingeschakeld. Als Windows-versleuteling is ingeschakeld terwijl een andere versleutelingsmethode actief is, wordt het apparaat mogelijk instabiel.
- **Opslagkaart versleutelen**: schakel deze instelling in om verwijderbare opslagkaarten te versleutelen die door het apparaat worden gebruikt.


### <a name="bitlocker-base-settings"></a>Basisinstellingen voor BitLocker

Basisinstellingen zijn universele BitLocker-instellingen voor alle soorten gegevensstations. Met de instellingen voor het BitLocker-groepsbeleid wordt beheerd welke schijfversleutelingstaken of configuratieopties de eindgebruiker kan wijzigen op alle soorten gegevensstations.

- **Waarschuwing voor andere schijfversleuteling**: schakel de waarschuwing uit voor andere schijfversleuteling op computers van eindgebruikers.
- **Versleutelingsmethoden configureren**: schakel deze instelling in om versleutelingsalgoritmen te configureren voor het besturingssysteem, gegevens en verwisselbare stations.
    - **Versleuteling voor stations met besturingssysteem**: kies de versleutelingsmethode stations met een besturingssysteem. Het is raadzaam om het algoritme XTS AES te gebruiken.
    - **Versleuteling voor vaste gegevensschijven**: kies de versleutelingsmethode voor vaste (ingebouwde) schijven, ook wel 'harde schijven' genoemd. Het is raadzaam om het algoritme XTS AES te gebruiken.
    - **Versleuteling voor verwisselbare gegevensstations**: kies de versleutelingsmethode voor verwisselbare gegevensstations. Als het verwisselbare station wordt gebruikt met apparaten waarop Windows 10 niet wordt uitgevoerd, raden we aan om het algoritme AES-CBC te gebruiken.

### <a name="bitlocker-os-drive-settings"></a>BitLocker-instellingen voor station met besturingssysteem

Deze instellingen zijn van toepassing zijn op gegevensstations van het besturingssysteem.

- **Extra authenticatie vereisen bij opstarten**: hiermee configureert u authenticatievereisten voor het opstarten van de computer, zoals het gebruik van TPM (Trusted Platform Module).
    - **BitLocker met niet-compatibele TPM-chip**
    - **Compatibele TPM opstarten**: hiermee configureert u of de TPM-chip is toegestaan, niet is toegestaan of is vereist.
    - **Compatibele TPM-opstartpincode**: hiermee configureert u of het gebruik van een TPM-opstartpincode met de TPM-chip is toegestaan, niet is toegestaan of is vereist.
    - **Compatibele TPM-opstartsleutel**: hiermee configureert u of het gebruik van een TPM-opstartsleutel met de TPM-chip is toegestaan, niet is toegestaan of is vereist.
    - **Compatibele opstartsleutel en pincode voor TPM**: hiermee configureert u of het gebruik van een opstartsleutel en pincode voor TPM met de TPM-chip is toegestaan, niet is toegestaan of is vereist.
- **Minimale lengte pincode**: schakel deze instelling in om een minimale lengte te configureren voor de TPM-opstartpincode.
    - **Minimum aantal tekens**: geef het aantal tekens op dat is vereist voor de opstartpincode, tussen **4**-**20**.
- **Herstellen van OS-station**: schakel deze instelling in om te bepalen hoe met BitLocker beveiligde besturingssysteemstations worden hersteld als de vereiste opstartgegevens niet beschikbaar zijn.
    - **Agent voor gegevensherstel op basis van een certificaat**: schakel deze instelling in als agenten voor gegevensherstel mogen worden gebruikt met besturingssysteemstations die met BitLocker zijn beveiligd.
    - **Herstelwachtwoord maken door gebruiker**: hiermee configureert u of gebruikers verplicht of optioneel een herstelwachtwoord van 48 cijfers mogen genereren, of dat dit niet is toegestaan.
    - **Herstelsleutel maken door gebruiker**: hiermee configureert u of gebruikers verplicht of optioneel een herstelsleutel van 256 bits mogen genereren, of dat dit niet is toegestaan.
    - **Herstelopties in de BitLocker-installatiewizard**: schakel deze instelling in om te voorkomen dat gebruikers herstelopties zien of deze kunnen wijzigen wanneer ze BitLocker inschakelen.
    - **BitLocker-herstelgegevens naar AD DS opslaan**: hiermee schakelt u de opslag van BitLocker-herstelgegevens in Active Directory in.
    - **BitLocker-herstelgegevens opgeslagen naar AD DS**: hiermee bepaalt u welke onderdelen van BitLocker-herstelgegevens worden opgeslagen in Active Directory. U kunt kiezen uit:
        - **Back-up maken van herstelwachtwoorden en sleutelpakketten**
        - **Alleen een back-up maken van herstelwachtwoorden**
    - **Herstelgegevens opslaan in AD DS voordat BitLocker wordt ingeschakeld**: schakel deze instelling in om te voorkomen dat gebruikers BitLocker inschakelen, tenzij het apparaat lid is van een domein en BitLocker-herstelgegevens met succes zijn opgeslagen in Active Directory.
- **Preboot-herstelbericht en -URL**: schakel deze instelling in om het bericht en de URL te configureren die worden weergegeven op het preboot-scherm voor sleutelherstel.
    - **Preboot-herstelbericht**: configureer hoe preboot-herstelbericht wordt weergegeven aan gebruikers. U kunt kiezen uit:
        - **Standaardherstelbericht en URL gebruiken**
        - **Leeg herstelbericht en -URL gebruiken**
        - **Aangepaste herstelbericht gebruiken**
        - **Aangepaste herstel-URL gebruiken**


### <a name="bitlocker-fixed-data-drive-settings"></a>BitLocker-instellingen voor vaste-gegevensstations

- **Toegang voor schrijven naar vaste-gegevensstations wanneer deze niet door BitLocker zijn beveiligd**: als deze instelling is ingeschakeld, moet BitLocker-beveiliging zijn ingeschakeld voor alle vaste of ingebouwde gegevensstations om gegevens te kunnen wegschrijven naar die stations.
- **Vast-stationherstel**: schakel deze instelling in om te bepalen hoe met BitLocker beveiligde vaste schijven worden hersteld als de vereiste opstartgegevens niet beschikbaar zijn.
    - **Agent voor gegevensherstel**: schakel deze instelling in als agenten voor gegevensherstel mogen worden gebruikt met vaste schijven die met BitLocker zijn beveiligd.
    - **Herstelwachtwoord maken door gebruiker**: hiermee configureert u of gebruikers verplicht of optioneel een herstelwachtwoord van 48 cijfers mogen genereren, of dat dit niet is toegestaan.  
    - **Herstelsleutel maken door gebruiker**: hiermee configureert u of gebruikers verplicht of optioneel een herstelsleutel van 256 bits mogen genereren, of dat dit niet is toegestaan.
    - **Herstelopties in de BitLocker-installatiewizard**: schakel deze instelling in om te voorkomen dat gebruikers herstelopties zien of deze kunnen wijzigen wanneer ze BitLocker inschakelen.
    - **BitLocker-herstelgegevens naar AD DS opslaan**: hiermee schakelt u de opslag van BitLocker-herstelgegevens in Active Directory in.
    - **BitLocker-herstelgegevens naar AD DS**: hiermee bepaalt u welke onderdelen van BitLocker-herstelgegevens worden opgeslagen in Active Directory. U kunt kiezen uit:
        - **Back-up maken van herstelwachtwoorden en sleutelpakketten**
        - **Alleen een back-up maken van herstelwachtwoorden**
    - **Herstelgegevens opslaan in AD DS voordat BitLocker wordt ingeschakeld**: schakel deze instelling in om te voorkomen dat gebruikers BitLocker inschakelen, tenzij het apparaat lid is van een domein en BitLocker-herstelgegevens met succes zijn opgeslagen in Active Directory.

### <a name="bitlocker-removable-data-drive-settings"></a>BitLocker-instellingen voor verwisselbare gegevensstations

- **Schrijftoegang voor een verwisselbaar gegevensstation dat niet door BitLocker is beveiligd**: geef op of BitLocker-versleuteling is vereist voor verwijderbare opslagstations.
  - **Schrijftoegang voor apparaten die in een andere organisatie zijn geconfigureerd**: geef op of gegevens mogen worden weggeschreven naar verwisselbare gegevensstations die deel uitmaken van een andere organisatie.

## <a name="windows-defender-exploit-guard"></a>Windows Defender Exploit Guard

Gebruik [Windows Defender Exploit Guard](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/windows-defender-exploit-guard) om de kwetsbaarheid voor aanvallen te beheren en te verminderen van apps die door uw medewerkers worden gebruikt.

### <a name="attack-surface-reduction"></a>Kwetsbaarheid voor aanvallen verminderen

Help [acties en apps te voorkomen](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard) die meestal worden gebruikt door malware om computers te infecteren.

#### <a name="rules-to-prevent-office-macro-threats"></a>Regels voor het voorkomen van bedreigingen voor Office-macro's

Blokkeer de volgende acties voor Office-apps:

- **Office-apps injecteren in andere processen (geen uitzonderingen)**
- **Uitvoerbare inhoud maken met Office-apps/-macro's**
- **Onderliggende processen starten met Office-apps**
- **Win32-importbewerkingen uit macrocode van Office**

#### <a name="rules-to-prevent-script-threats"></a>Regels om scriptbedreigingen te voorkomen

Blokkeer de volgende acties om scriptbedreigingen te voorkomen:

- **Verborgen js-/vbs-/ps-/macrocode**
- **Van internet gedownloade payloads uitvoeren met js-/vbs-bestanden (geen uitzonderingen)**

#### <a name="rules-to-prevent-email-threats"></a>Regels om te e-mailbedreigingen te voorkomen

Blokkeer de volgende acties om e-mailbedreigingen te voorkomen:

- **Uitvoering van uitvoerbare inhoud (exe-, dll-, ps-, js-, vbs-bestanden enzovoort) die is verwijderd uit e-mail (webmail/e-mailclient) (geen uitzonderingen)**

#### <a name="attack-surface-reduction-exceptions"></a>Regels voor het verminderen van kwetsbaarheid voor aanvallen

- **Bestanden en mappen die moeten worden uitgesloten van regels voor het verminderen van kwetsbaarheid voor aanvallen**: importeer of voeg een lijst met locaties toe die moet worden uitgesloten van de geconfigureerde regels.

### <a name="controlled-folder-access"></a>Gecontroleerde mappentoegang

Hiermee kunt u waardevolle gegevens beter beveiligen tegen schadelijke apps en bedreigingen zoals ransomware.

- **Mapbeveiliging**: beveilig bestanden en mappen tegen ongewenste wijzigingen door schadelijke apps. U kunt een **lijst met apps importeren die toegang hebben tot beveiligde mappen** of deze handmatig toevoegen. U kunt ook een **lijst met andere mappen uploaden die moeten worden beveiligd** of deze handmatig toevoegen.

### <a name="network-filtering"></a>Netwerk filteren

Uitgaande verbindingen naar IP-adressen/domeinen met een slechte reputatie blokkeren voor elke app.

### <a name="exploit-protection"></a>Exploit Protection

Blokkeer **bewerking door gebruikers van de Exploit Protection-interface** door een XML-bestand te uploaden waarmee uw het geheugen, de controlestroom en de beleidsbeperkingen kunt configureren waarmee wordt een toepassing wordt geblokkeerd voor aanvallen.

Als u beveiliging tegen misbruik wilt inschakelen, maakt u een XML-bestand met de gewenste beperkingsinstellingen voor het systeem en de toepassing. U kunt dit op een van de volgende twee manieren doen:

 1. PowerShell: gebruik een of meer van de Get-ProcessMitigation, Set-ProcessMitigation en ConvertTo-ProcessMitigationPolicy PowerShell-cmdlets om de beperkingsinstellingen te configureren en een XML-weergave hiervan te exporteren.

 2. Gebruikersinterface van het Windows Defender-beveiligingscentrum: klik in het Windows Defender-beveiligingscentrum op het besturingselement voor de app en browser en scrol naar beneden op het scherm om Beveiliging met Exploit Guard te zoeken. Gebruik eerst de tabbladen Systeeminstellingen en Programma-instellingen om de beperkingsinstellingen te configureren. Zoek vervolgens de koppeling Instellingen exporteren onderaan het scherm om een XML-weergave hiervan te exporteren.

## <a name="windows-defender-application-control"></a>Windows Defender Application Control

Gebruik **Integriteitsbeleidsregels van de stuurcode van de toepassing** om aanvullende apps te kiezen die moeten worden gecontroleerd door of kunnen worden vertrouwd door Windows Defender Application Control. Windows-onderdelen en alle apps uit Windows Store worden automatisch vertrouwd.

Toepassingen worden niet geblokkeerd wanneer ze in de modus **Alleen controle** worden uitgevoerd. De modus **Alleen controle** registreert alle gebeurtenissen in lokale clientlogboeken.

Als deze modus is ingeschakeld, kan toepassingsbeheer alleen worden uitgeschakeld door de modus te wijzigen van **Afdwingen** naar **Alleen controle**. Als u de modus wijzigt van **Afdwingen** in **Niet geconfigureerd**, wordt toepassingsbeheer op toegewezen apparaten nog steeds afgedwongen.

## <a name="windows-defender-security-center"></a>Windows Defender Security Center

De Windows Defender Security Center-app werkt als een afzonderlijke app of een afzonderlijk proces van de afzonderlijke functies en geeft meldingen weer via het onderhoudscentrum. Het fungeert als een collector of één afzonderlijke plaats om de status te zien en een configuratie van de functies uit te voeren. Meer informatie de documenten over [Windows Defender](https://docs.microsoft.com/windows/threat-protection/windows-defender-security-center/windows-defender-security-center).

#### <a name="windows-defender-security-center-app-and-notifications"></a>Windows Defender Security Center-app en meldingen

Blokkeer de toegang van eindgebruikers tot verschillende gebieden van de Windows Defender-beveiligingscentrum-app. Als u een sectie verbergt, worden ook verwante meldingen geblokkeerd.

- **Virus- en bedreigingsbeveiliging**
- **Prestaties en status van apparaat**
- **Firewall- en netwerkbeveiliging**
- **App- en browserbeheer**
- **Gezinsopties**
- **Meldingen van de weergegeven gebieden van de app**: kies welke meldingen worden weergegeven voor eindgebruikers. Niet-kritieke meldingen zijn bijvoorbeeld samenvattingen van Windows Defender Antivirus-activiteiten en meldingen wanneer scans zijn voltooid. Alle andere meldingen worden beschouwd als kritiek.

#### <a name="it-contact-information"></a>IT-contactgegevens

Geef de IT-contactgegevens op die in de Windows Defender-beveiligingscentrum-app en in de app-meldingen moeten worden weergegeven. U kunt kiezen tussen **In app en in meldingen weergeven**, **Alleen in app weergeven**, **Alleen in meldingen weergeven** en **Niet weergeven**. U moet de **IT-organisatienaam** en ten minste één van de volgende contactopties opgeven:

- **Telefoonnummer of Skype-ID van de IT-afdeling**
- **E-mailadres van de IT-afdeling**
- **URL van de IT-ondersteuningswebsite**

## <a name="next-steps"></a>Volgende stappen

Zie [How to assign device profiles](device-profile-assign.md) (Apparaatprofielen toewijzen) als u wilt doorgaan en dit profiel wilt toewijzen aan groepen.
