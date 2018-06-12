---
title: Endpoint Protection in Windows 10 toevoegen in Microsoft Intune - Azure | Microsoft Docs
description: Gebruik of configureer op Windows 10-apparaten instellingen voor eindpuntbescherming om functies van Windows Defender in te schakelen, zoals Application Guard, Firewall, SmartScreen, versleuteling en bitlocker, Exploit Guard, Application Control, Security Center en beveiliging van lokale apparaten in Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 05/21/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 3af7c91b-8292-4c7e-8d25-8834fcf3517a
ms.reviewer: ilwu
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0831f374b9c6da417d8159dce1b58e40f0d3643c
ms.sourcegitcommit: 97b9f966f23895495b4c8a685f1397b78cc01d57
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2018
ms.locfileid: "34744938"
---
# <a name="endpoint-protection-settings-for-windows-10-and-later-in-intune"></a>Instellingen voor de beveiliging van eindpunten voor Windows 10 en hoger in Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Via het profiel voor eindpuntbeveiliging kunt u beveiligingsfuncties op Windows 10-apparaten beheren, zoals BitLocker en Windows Defender.

Gebruik de informatie in dit artikel om profielen voor eindpuntbeveiliging te maken. Zie [Apparaatbeperkingsinstellingen voor Windows 10](device-restrictions-windows-10.md#windows-defender-antivirus) als u Windows Defender Antivirus wilt configureren. 

> [!NOTE]
> Deze instellingen worden niet ondersteund in de edities Home en Professional van Windows 10.

## <a name="windows-defender-application-guard"></a>Windows Defender Application Guard

Wanneer u Microsoft Edge gebruikt, beschermt Windows Defender Application Guard uw omgeving tegen sites die nog niet als vertrouwd zijn gedefinieerd door uw organisatie. Als gebruikers sites bezoeken die niet worden vermeld in uw geïsoleerde netwerkgrens, worden deze sites geopend in een virtuele browsersessie in Hyper-V. Vertrouwde sites worden gedefinieerd door een netwerkgrens, die in Apparaatconfiguratie kan worden geconfigureerd. 

Application Guard is alleen beschikbaar voor apparaten met de 64 bitsversie van Windows 10. Met dit profiel wordt een Win32-onderdeel geïnstalleerd om Application Guard te activeren.

- **Application Guard**: open niet-goedgekeurde sites in een Hyper-V gevirtualiseerde browsercontainer.
- **Klembordgedrag**: kies welke kopieer- en plakbewerkingen zijn toegestaan tussen de lokale pc en de virtuele browser van Application Guard.
- **Externe inhoud op Enterprise-sites**: voorkom dat inhoud van niet-goedgekeurde websites wordt geladen.
- **Afdrukken vanuit virtuele browser**: sta toe dat PDF-, XPS- en lokale of netwerkprinters inhoud vanuit de virtuele browser kunnen afdrukken.
- **Logboeken verzamelen**: verzamel logboeken voor gebeurtenissen die zich voordoen in een Application Guard-browsersessie.
- **Door de gebruiker gegenereerde browsergegevens behouden**: sla gebruikersgegevens (zoals wachtwoorden, favorieten en cookies) op die zijn gemaakt tijdens een virtuele browsersessie met Application Guard.
- **Grafische versnelling**: laad grafisch-intensieve websites sneller wanneer u binnen een virtuele browsersessie met Application Guard werkt. Websites worden sneller geladen doordat de toegang tot een virtuele afbeeldingenverwerkingseenheid is ingeschakeld.
- **Bestanden downloaden naar hostbestandssysteem**: toestaan dat gebruikers bestanden downloaden van de gevirtualiseerde browser naar het hostbesturingssysteem.

## <a name="windows-defender-firewall"></a>Windows Defender Firewall

### <a name="global-settings"></a>Globale instellingen

Deze instellingen gelden voor alle netwerktypen.

- **File Transfer Protocol**: blokkeer stateful FTP.
- **Niet-actieve tijd voordat beveiligingskoppeling wordt verwijderd**: beveiligingskoppelingen worden verwijderd nadat gedurende *n* seconden geen netwerkverkeer wordt gedetecteerd.
- **Vooraf-gedeelde sleutels coderen**: codeer vooraf-gedeelde sleutels met UTF-8.
- **IPsec-uitzonderingen**: hiermee configureert u specifiek verkeer om te worden vrijgesteld voor het uitvoeren van IPsec, waaronder **ICMP-type-codes voor IPv6 detecteren met Neighbor**, **ICMP**, **ICMP-type-codes voor IPv6 detecteren met Router** en  **DHCP-netwerkverkeer via IPv4 en IPv6**.
- **Controle van certificaatintrekkingslijsten**: stel een waarde in voor het afdwingen van controle van certificaatintrekkingslijsten, zoals **CRL-controle uitschakelen**, **CRL-verificatie mislukt alleen bij alleen ingetrokken certificaat** en **CRL-verificatie mislukt bij elke fout die wordt aangetroffen**.
- **Verificatieset opportunistisch afstemmen per sleutelmodule**: stel sleutelmodules in om de volledige verificatieset te negeren als de modules geen ondersteuning bieden voor alle verificatiepakketten in de betreffende set.
- **Pakketten in wachtrij plaatsen**: voer in hoe schalen voor software aan de ontvangstzijde worden ingeschakeld voor versleuteld ontvangen en ongecodeerd doorsturen in het scenario voor de IPsec-tunnelgateway. Deze instelling garandeert dat de pakketvolgorde behouden blijft.

### <a name="network-settings"></a>Netwerkinstellingen

Deze instellingen zijn van toepassing op specifieke netwerktypen, waaronder **Domeinnetwerk (werkplek)**, **Privénetwerk (detecteerbaar)** en **Openbaar netwerk (niet-detecteerbaar)**.

#### <a name="general-settings"></a>Algemene instellingen

- **Windows Defender Firewall**: schakel deze instelling in om netwerkverkeer te blokkeren.
- **Verborgen modus**: blokkeer de firewall in de verborgen modus. Als u de verborgen modus blokkeert, blokkeert u ook **Uitsluiting van beveiligd IPsec-pakket**.
- **Afgeschermd**: als deze instelling is ingeschakeld, blokkeert de firewallinstelling al het binnenkomende verkeer.
- **Unicast-antwoorden voor multicast-broadcasts**: blokkeer unicast-antwoorden voor multicast-broadcasts. Normaal gesproken wilt u geen unicast-antwoorden voor multicast-broadcasts ontvangen. Deze antwoorden kunnen wijzen op een DOS-aanval (denial of service) of een aanvaller die een computer wil binnendringen.
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

De volgende twee instellingen gelden voor alle versies van Windows 10:

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
  - **Compatibele TPM opstarten**: kies ervoor om de TPM-chip toe te staan, niet toe te staan of te vereisen.
  - **Compatibele TPM-opstartpincode**: kies ervoor om het gebruik van een opstartpincode met de TPM-chip toe te staan, niet toe te staan of te vereisen.
  - **Compatibele TPM-opstartsleutel**: kies ervoor om het gebruik van een opstartsleutel met de TPM-chip toe te staan, niet toe te staan of te vereisen.
  - **Compatibele opstartsleutel en pincode voor TPM**: kies ervoor om het gebruik van een opstartsleutel en -pincode met de TPM-chip toe te staan, niet toe te staan of te vereisen.
- **Minimale lengte pincode**: schakel deze instelling in om een minimale lengte te configureren voor de TPM-opstartpincode.
  - **Minimale aantal tekens**: geef het aantal tekens op dat is vereist voor de opstartpincode, tussen **4**-**20**.
- **Herstellen van besturingssysteemstation**: schakel deze instelling in om te bepalen hoe met BitLocker beveiligde besturingssysteemstations worden hersteld als de vereiste opstartgegevens niet beschikbaar zijn.
  - **Agent voor gegevensherstel op basis van een certificaat**: schakel deze instelling in als agenten voor gegevensherstel mogen worden gebruikt met besturingssysteemstations die met BitLocker zijn beveiligd.
  - **Herstelwachtwoord maken door gebruiker**: kies of gebruikers verplicht of optioneel een herstelwachtwoord van 48 cijfers mogen genereren, of dat dit niet is toegestaan.
  - **Herstelsleutel maken door gebruiker**: kies of gebruikers verplicht of optioneel een herstelsleutel van 256 bits mogen genereren, of dat dit niet is toegestaan.
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

- **Referentiediefstal in het Windows-subsysteem voor de lokale beveiligingsautoriteit markeren**

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
- **Het maken van processen met PSExec- en WMI-opdrachten**
- **Niet-vertrouwde en niet-ondertekende processen die worden uitgevoerd via USB**
- **Uitvoerbare bestanden die niet voldoen aan een bepaalde gangbaarheid, ouderdom of aan criteria voor vertrouwde lijsten blokkeren**

#### <a name="rules-to-prevent-email-threats"></a>Regels om te e-mailbedreigingen te voorkomen

Blokkeer de volgende acties om e-mailbedreigingen te voorkomen:

- **Uitvoering van uitvoerbare inhoud (exe-, dll-, ps-, js-, vbs-bestanden enzovoort) die is verwijderd uit e-mail (webmail/e-mailclient) (geen uitzonderingen)**

#### <a name="rules-to-protect-against-ransomware"></a>Regels voor bescherming tegen ransomware
- **Geavanceerde ransomwarebeveiliging**

> [!TIP]
> [Oppervlakteaanvallen verminderen met Windows Defender Exploit Guard](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard) biedt meer informatie over deze regels.

#### <a name="attack-surface-reduction-exceptions"></a>Regels voor het verminderen van kwetsbaarheid voor aanvallen

- **Bestanden en mappen die moeten worden uitgesloten van regels voor het verminderen van kwetsbaarheid voor aanvallen**: importeer of voeg een lijst met locaties toe die moet worden uitgesloten van de geconfigureerde regels.

### <a name="controlled-folder-access"></a>Gecontroleerde mappentoegang

Hiermee kunt u waardevolle gegevens beter beveiligen tegen schadelijke apps en bedreigingen zoals ransomware.

- **Mapbeveiliging**: beveilig bestanden en mappen tegen ongewenste wijzigingen door schadelijke apps. U kunt een **lijst met apps importeren die toegang hebben tot beveiligde mappen** of deze handmatig toevoegen. U kunt ook een **lijst met andere mappen uploaden die moeten worden beveiligd** of deze handmatig toevoegen.

### <a name="network-filtering"></a>Netwerk filteren

Uitgaande verbindingen naar IP-adressen/domeinen met een slechte reputatie blokkeren voor elke app.

### <a name="exploit-protection"></a>Exploit Protection

Blokkeer **bewerking door gebruikers van de Exploit Protection-interface** door een XML-bestand te uploaden waarmee uw het geheugen, de controlestroom en de beleidsbeperkingen kunt configureren. De instellingen in het XML-bestand kunnen worden gebruikt om een toepassing te blokkeren tegen aanvallen.

Als u beveiliging tegen misbruik wilt inschakelen, maakt u een XML-bestand met de gewenste beperkingsinstellingen voor het systeem en de toepassing. U kunt dit op een van de volgende twee manieren doen:

 1. PowerShell: gebruik een of meer van de Get-ProcessMitigation, Set-ProcessMitigation en ConvertTo-ProcessMitigationPolicy PowerShell-cmdlets. Met de cdmlets worden beperkingsinstellingen geconfigureerd en wordt hiervan een XML-weergave geëxporteerd.

 2. Gebruikersinterface van het Windows Defender-beveiligingscentrum: klik in het Windows Defender-beveiligingscentrum op het besturingselement voor de app en browser en scrol naar beneden op het scherm om Beveiliging met Exploit Guard te zoeken. Gebruik eerst de tabbladen Systeeminstellingen en Programma-instellingen om de beperkingsinstellingen te configureren. Zoek vervolgens de koppeling Instellingen exporteren onderaan het scherm om een XML-weergave hiervan te exporteren.

## <a name="windows-defender-application-control"></a>Windows Defender Application Control

Gebruik **Integriteitsbeleidsregels van de stuurcode van de toepassing** om aanvullende apps te kiezen die moeten worden gecontroleerd door of kunnen worden vertrouwd door Windows Defender Application Control. Windows-onderdelen en alle apps uit Windows Store worden automatisch vertrouwd.

Toepassingen worden niet geblokkeerd wanneer ze in de modus **Alleen controle** worden uitgevoerd. De modus **Alleen controle** registreert alle gebeurtenissen in lokale clientlogboeken.

Als deze modus is ingeschakeld, kan toepassingsbeheer alleen worden uitgeschakeld door de modus te wijzigen van **Afdwingen** naar **Alleen controle**. Als u de modus wijzigt van **Afdwingen** in **Niet geconfigureerd**, wordt toepassingsbeheer op toegewezen apparaten nog steeds afgedwongen.

## <a name="windows-defender-credential-guard"></a>Windows Defender Credential Guard
Windows Defender Credential Guard beschermt tegen aanvallen waarbij referenties worden gestolen. Het isoleert geheimen zodat alleen bevoegde systeemsoftware er toegang toe heeft.

De instellingen voor **Credential Guard** omvatten:

- **Uitgeschakeld**: hiermee wordt Credential Guard extern uitgeschakeld als deze eerder is ingeschakeld met de optie **Ingeschakeld zonder UEFI-vergrendeling**.
- **Ingeschakeld met UEFI-vergrendeling**: met deze optie kan Credential Guard niet extern worden uitgeschakeld behulp van een registersleutel of via Groepsbeleid.

    > [!NOTE]
    > Als u deze instelling gebruikt en Credential Guard later wilt uitschakelen, moet u het Groepsbeleid instellen op **Uitgeschakeld**. Ook moet u de UEFI-configuratiegegevens fysiek van elke computer wissen. Zolang de UEFI-configuratie behouden blijft, is Credential Guard ingeschakeld.

- **Uitgeschakeld zonder UEFI-vergrendeling**: met deze optie kan Credential Guard extern worden uitgeschakeld via Groepsbeleid. Op de apparaten die gebruikmaken van deze instelling moet Windows 10 versie 1511 en hoger worden uitgevoerd.

Wanneer u Credential Guard inschakelt, worden de volgende vereiste functies ook ingeschakeld:

- **Beveiliging op basis van virtualisatie**: wordt ingeschakeld tijdens de volgende keer opnieuw opstarten. Beveiliging op basis van virtualisatie maakt gebruik van de Windows-Hypervisor om ondersteuning te bieden voor beveiligingsservices.
- **Beveiligd opstarten met directe geheugentoegang**: hiermee schakelt u beveiliging op basis van virtualisatie met beveiligd opstarten en directe geheugentoegang (DMA) in. Voor DMA-beveiliging is hardwareondersteuning vereist en deze wordt alleen ingeschakeld op apparaten die juist zijn geconfigureerd.

## <a name="windows-defender-security-center"></a>Windows Defender Security Center

De Windows Defender Security Center-app werkt als een afzonderlijke app of een afzonderlijk proces van de afzonderlijke functies. Deze geeft meldingen weer via het onderhoudscentrum. Het fungeert als een collector of één afzonderlijke plaats om de status te zien en een configuratie van de functies uit te voeren. Meer informatie de documenten over [Windows Defender](https://docs.microsoft.com/windows/threat-protection/windows-defender-security-center/windows-defender-security-center).

#### <a name="windows-defender-security-center-app-and-notifications"></a>Windows Defender Security Center-app en meldingen

Blokkeer de toegang van eindgebruikers tot verschillende gebieden van de Windows Defender-beveiligingscentrum-app. Als u een sectie verbergt, worden ook verwante meldingen geblokkeerd.

- **Virus- en bedreigingsbeveiliging**
- **Prestaties en status van apparaat**
- **Firewall- en netwerkbeveiliging**
- **App- en browserbeheer**
- **Gezinsopties**
- **Meldingen van de weergegeven gebieden van de app**: kies welke meldingen worden weergegeven voor eindgebruikers. Niet-kritieke meldingen zijn bijvoorbeeld samenvattingen van Windows Defender Antivirus-activiteiten en meldingen wanneer scans zijn voltooid. Alle andere meldingen worden beschouwd als kritiek.

#### <a name="it-contact-information"></a>IT-contactgegevens

Geef de IT-contactgegevens op die in de Windows Defender-beveiligingscentrum-app en in de app-meldingen moeten worden weergegeven. U kunt kiezen tussen **In app en in meldingen weergeven**, **Alleen in app weergeven**, **Alleen in meldingen weergeven** en **Niet weergeven**. U moet de **IT-organisatienaam** en ten minste één van de volgende contactopties invoeren:

- **Telefoonnummer of Skype-ID van de IT-afdeling**
- **E-mailadres van de IT-afdeling**
- **URL van de IT-ondersteuningswebsite**

## <a name="local-device-security-options"></a>Beveiligingsopties van lokale apparaten

Gebruik deze opties voor het configureren van de lokale beveiligingsinstellingen op Windows 10-apparaten.

### <a name="accounts"></a>Accounts

- **Nieuwe Microsoft-accounts toevoegen**: voorkom dat gebruikers nieuwe Microsoft-accounts aan deze computer toevoegen.
- **Extern aanmelden zonder wachtwoord**: toestaan dat lokale accounts zonder wachtwoord zich aanmelden vanaf een andere locatie dan het fysieke apparaat.

#### <a name="admin"></a>Administrator

- **Lokale beheerdersaccount**: bepaal of het lokale beheerdersaccount is ingeschakeld of uitgeschakeld.
- **Naam van beheerdersaccount wijzigen**: definieer een andere accountnaam die moet worden gekoppeld aan de beveiligings-id (SID) van het beheerdersaccount.

#### <a name="guest"></a>Gast

- **Gastaccount**: bepaal of het gastaccount is ingeschakeld of uitgeschakeld.
- **Naam van gastaccount wijzigen**: definieer een andere accountnaam die moet worden gekoppeld aan de beveiligings-id (SID) van het gastaccount.

### <a name="devices"></a>Apparaten

- **Apparaat ontkoppelen zonder aanmelding**: voorkom dat een draagbare computer wordt ontkoppeld zonder zich te hoeven aanmelden.
- **Stuurprogramma's voor gedeelde printers installeren**: beperk het installeren van printerstuurprogramma's als onderdeel van het maken van verbinding met een gedeelde printer tot alleen beheerders.
- **Cd-rom-toegang beperken tot lokale actieve gebruiker**: als u deze instelling inschakelt, heeft alleen de interactief aangemelde gebruiker toegang tot cd-rom-media
- **Verwisselbare media formatteren en uitwerpen**: definieer de personen voor wie het is toegestaan om verwisselbare NTFS-media te formatteren en uit te werpen:
  - **Niet geconfigureerd**
  - **Beheerders en hoofdgebruikers**
  - **Beheerders en interactieve gebruikers**

### <a name="interactive-logon"></a>Interactief aanmelden

- **Minuten van inactiviteit van vergrendelingsscherm totdat de schermbeveiliging wordt geactiveerd**: definieer het maximale aantal minuten van inactiviteit op het aanmeldingsscherm van het interactieve bureaublad totdat de schermbeveiliging actief wordt.
- **Indrukken van CTRL+ALT+DEL vereisen voor aanmelden**: vereis dat CTRL + ALT + DEL worden ingedrukt voordat een gebruiker zich kan aanmelden.
- **Gedrag bij verwijderen van smartcard**: hiermee bepaalt u wat er gebeurt wanneer de smartcard van een aangemelde gebruiker uit de lezer van de smartcard wordt verwijderd. Uw opties zijn:

  - **Werkstation vergrendelen**: het werkstation wordt vergrendeld wanneer de smartcard wordt verwijderd. Met deze optie kunnen gebruikers het gebied verlaten, de smartcard meenemen en toch een beveiligde sessie behouden.
  - **Afmelden forceren**: de gebruiker wordt automatisch afgemeld wanneer de smartcard wordt verwijderd.
  - **Verbinding verbreken bij sessie met Extern bureaublad-services**: als de smartcard wordt verwijderd, wordt de sessie verbroken zonder de gebruiker af te melden. Met deze optie kan de gebruiker de smartcard plaatsen en de sessie later of op een andere met smartcardlezer uitgeruste computer hervatten zonder zich opnieuw te moeten melden. Als de sessie lokaal is, werkt dit beleid op dezelfde manier als Werkstation vergrendelen.

    [Lokaal beleid/Beveiligingsopties](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-localpoliciessecurityoptions#localpoliciessecurityoptions-interactivelogon-smartcardremovalbehavior) biedt meer details.

#### <a name="display"></a>Weergave

- **Gebruikersinformatie op vergrendelingsscherm**: configureer welke gebruikersinformatie wordt weergegeven wanneer de sessie is vergrendeld. Als deze optie niet is geconfigureerd, worden de weergavenaam van de gebruiker, het domein en de gebruikersnaam weergegeven.
  - **Niet geconfigureerd**: weergavenaam van gebruiker, domein en gebruikersnaam
  - **Weergavenaam van gebruiker, domein en gebruikersnaam**
  - **Alleen weergavenaam gebruiker**
  - **Gebruikersinformatie niet weergeven**
- **Laatst aangemelde gebruiker verbergen**: de gebruikersnaam van de laatste persoon die zich heeft aangemeld op dit apparaat wordt niet weergegeven.
- **Gebruikersnaam verbergen bij aanmelden**: de gebruikersnaam van de persoon die zich op dit apparaat heeft aangemeld, wordt niet weergeven nadat de referenties zijn ingevoerd en voordat het bureaublad van het apparaat wordt weergegeven.
- **Titel aanmeldingsbericht**: stel de berichttitel in voor gebruikers die zich willen aanmelden.
- **Tekst aanmeldingsbericht**: stel de berichttekst in voor gebruikers die zich willen aanmelden.

### <a name="network-access-and-security"></a>Netwerktoegang en -beveiliging

- **Anonieme toegang tot benoemde pipes en shares**: **Niet geconfigureerd** (standaard) beperkt anonieme toegang tot instellingen voor shares en named pipes. Van toepassing op de instellingen die anoniem kunnen worden gebruikt.
- **Anonieme inventarisatie van SAM-accounts**: anonieme gebruikers **toestaan** de SAM-accounts te inventariseren. Windows staat anonieme gebruikers toe de namen van domeinaccounts en netwerkshares te inventariseren.
- **Anonieme inventarisatie van SAM-accounts en -shares**: **Niet geconfigureerd** (standaard) betekent dat anonieme gebruikers de namen van domeinaccounts en netwerkshares kunnen inventariseren. Als u anonieme inventarisatie van SAM-accounts en -shares wilt verhinderen, stelt u deze in op **Blokkeren**.
- **Hashwaarde van LAN Manager opslaan bij wachtwoordwijziging**: kies bij de volgende wachtwoordwijziging **Toestaan** zodat de LAN Manager (LM) de hash-waarde voor het nieuwe wachtwoord kan opslaan. Als de waarde is ingesteld op **Niet geconfigureerd** (standaard), wordt de hash-waarde niet opgeslagen.
- **PKU2U-verificatieaanvragen**: **blokkeer** PKU2U-verificatieaanvragen aan het apparaat om online-identiteiten te gebruiken. **Niet geconfigureerd** (standaard) staat deze aanvragen toe.
- **Externe RPC-verbindingen met SAM beperken**: **toestaan** dat de standaardtekenreeks van Security Descriptor Definition Language gebruikers en groepen weigert om externe aanroepen naar de SAM uit te voeren. **Niet geconfigureerd** (standaard) de standaardtekenreeks van Security Descriptor Definition Language om gebruikers en groepen toe te staan om externe aanroepen naar de SAM uit te voeren.
  - **Beveiligingsdescriptor**

### <a name="recovery-console-and-shutdown"></a>Herstelconsole en afsluiten

- **Wisselbestand voor virtueel geheugen wissen bij het afsluiten**: wis het wisselbestand voor het virtueel geheugen wanneer het apparaat wordt uitgeschakeld.
- **Afsluiten zonder aanmelding**: blokkeer de optie voor het afsluiten van de computer vanuit het Windows-aanmeldingsscherm. In dit geval moeten gebruikers zich eerst aanmelden bij de computer voordat ze het systeem kunnen afsluiten.

### <a name="user-account-control"></a>Gebruikersaccountbeheer

- **UIA-integriteit zonder veilige locatie**: bied de mogelijkheid apps vanaf niet-beveiligde locaties in het bestandssysteem uit te voeren met een UIA-integriteitsniveau.
- **Schrijffouten in bestanden en register in locaties per gebruiker virtualiseren**: bepaal of schrijffouten van een app worden omgeleid naar gedefinieerde register- en bestandssysteemlocaties. Of zorg ervoor dat de app niet meer kan worden uitgevoerd.
- **Alleen bevoegdheden verhogen voor uitvoerbare bestanden die zijn ondertekend en gevalideerd**: dwing PKI certificeringspadvalidatie af voor een bepaald uitvoerbaar bestand voordat dit mag worden uitgevoerd.

#### <a name="uia-elevation-prompt-behavior-settings"></a>Instellingen voor gedrag bij vragen om UIA-uitbreiding

- **Vragen om benodigde bevoegdheden voor beheerders**: definieer het gedrag voor het vragen om benodigde bevoegdheden voor beheerders in modus Door administrator goedkeuren:
  - **Verhogen zonder te vragen**
  - **Vragen om referenties op het beveiligde bureaublad**
  - **Vragen om toestemming op het beveiligde bureaublad**
  - **Vragen om referenties**
  - **Vragen om toestemming**
  - **Niet geconfigureerd**: Vragen om toestemming voor niet-Windows binaire bestanden
- **Vragen om benodigde bevoegdheden voor standaardgebruikers**: definieer het gedrag voor het vragen om benodigde bevoegdheden voor standaardgebruikers:
  - **Vragen voor benodigde bevoegdheden automatisch weigeren**
  - **Vragen om referenties op het beveiligde bureaublad**
  - **Niet geconfigureerd**: Vragen om referenties
- **Leid vragen om benodigde bevoegdheden naar het interactieve bureaublad van de gebruiker**: laat alle vragen om bevoegdheden naar het bureaublad van de interactieve gebruiker gaan in plaats van het beveiligde bureaublad. Er worden beleidsinstellingen voor vragen voor beheerders en standaardgebruikers gebruikt.
- **Vragen om verhoogde bevoegdheden bij installatie van apps**: bij app-installaties die verhoogde bevoegdheden nodig hebben, wordt gevraagd om beheerdersreferenties.
- **Vragen om benodigde UIA-bevoegdheden zonder beveiligd bureaublad**: sta UIAccess-apps toe te vragen om benodigde bevoegdheden zonder het beveiligde bureaublad te gebruiken.

#### <a name="admin-approval-mode-settings"></a>Instellingen voor de modus Door administrator goedkeuren

- **De modus Door administrator goedkeuren voor geïntegreerde beheerder**: definieer of het ingebouwde beheerdersaccount de modus Door administrator goedkeuren gebruikt of dat alle apps met volledige beheerdersbevoegdheden worden uitgevoerd.
- **Alle beheerders uitvoeren in de modus Door administrator goedkeuren**: definieer of de modus Door administrator goedkeuren en alle UAC-beleidsinstellingen zijn ingeschakeld.

### <a name="microsoft-network-client"></a>Microsoft Network Client

- **Clientcommunicatie digitaal ondertekenen (indien mogelijk)**: hiermee wordt bepaald of de SMB-client probeert te onderhandelen over SMB-pakketondertekening. Indien ingeschakeld (Niet geconfigureerd), vraagt Microsoft Network Client de server om SMB-pakketondertekening uit te voeren bij het instellen van een sessie. Als pakketondertekening is ingeschakeld op de server, wordt over ondertekening van pakketten onderhandeld. Als dit beleid is uitgeschakeld, onderhandelt de SMB-client nooit over SMB-pakketondertekening.
- **Niet-versleuteld wachtwoord verzenden om verbinding te kunnen maken met niet-Microsoft SMB-servers**: indien ingeschakeld, mag de SMB-redirector (Server Message Block) ongecodeerde wachtwoorden verzenden naar niet-Microsoft SMB-servers die geen ondersteuning voor wachtwoordversleuteling bieden tijdens verificatie.

### <a name="microsoft-network-server"></a>Microsoft Network Server

- **Communicatie digitaal ondertekenen (bij akkoord van client)**: hiermee wordt bepaald of de SMB-server onderhandelt over SMB-pakketondertekening met clients die dit aanvragen. Indien ingeschakeld, onderhandelt de Microsoft-netwerkserver over SMB-pakketondertekening zoals aangevraagd door de client. Ofwel, als pakketondertekening is ingeschakeld op de client, wordt over ondertekening van pakketten onderhandeld. Als deze instelling **niet geconfigureerd** of uitgeschakeld (standaardwaarde) is, onderhandelt de SMB-client nooit over SMB-pakketondertekening.
- **Communicatie digitaal ondertekenen (altijd)**: hiermee wordt bepaald of het ondertekenen van pakketten wordt vereist door de SMB-servercomponent. Als deze instelling is ingeschakeld, communiceert de Microsoft-netwerkserver niet met een Microsoft-netwerkclient, tenzij die client akkoord gaat met het uitvoeren van SMB-pakketondertekening. Als deze instelling **niet geconfigureerd** of uitgeschakeld (standaardwaarde) is, wordt over het ondertekenen van SMB-pakketten onderhandeld door de client en de server.

## <a name="next-steps"></a>Volgende stappen

Zie [Apparaatprofielen toewijzen](device-profile-assign.md) als u dit profiel wilt toewijzen aan groepen.