---
title: Endpoint Protection in Windows 10 toevoegen in Microsoft Intune - Azure | Microsoft Docs
description: Gebruik of configureer op Windows 10-apparaten instellingen voor eindpuntbescherming om functies van Windows Defender in te schakelen, zoals Application Guard, Firewall, SmartScreen, versleuteling en bitlocker, Exploit Guard, Application Control, Security Center en beveiliging van lokale apparaten in Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 06/25/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 3af7c91b-8292-4c7e-8d25-8834fcf3517a
ms.reviewer: ilwu
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1a7c7ebca1c6472b58021a57b1b4a59fc42966b0
ms.sourcegitcommit: d8edd1c3d24123762dd6d14776836df4ff2a31dd
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/13/2018
ms.locfileid: "51576950"
---
# <a name="endpoint-protection-settings-for-windows-10-and-later-in-intune"></a>Instellingen voor de beveiliging van eindpunten voor Windows 10 en hoger in Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Via het profiel voor eindpuntbeveiliging kunt u beveiligingsfuncties op Windows 10-apparaten beheren, zoals BitLocker en Windows Defender.

Gebruik de informatie in dit artikel om profielen voor eindpuntbeveiliging te maken. Zie [Apparaatbeperkingsinstellingen voor Windows 10](device-restrictions-windows-10.md#windows-defender-antivirus) als u Windows Defender Antivirus wilt configureren. 

## <a name="windows-defender-application-guard"></a>Windows Defender Application Guard

Wordt ondersteund op de volgende edities van Windows 10:

- Zakelijk 
- Professional

Wanneer u Microsoft Edge gebruikt, beschermt Windows Defender Application Guard uw omgeving tegen sites die niet worden vertrouwd door uw organisatie. Als gebruikers sites bezoeken die niet worden vermeld in uw geïsoleerde netwerkgrens, worden deze sites geopend in een virtuele browsersessie in Hyper-V. Vertrouwde sites worden gedefinieerd door een netwerkgrens, die in Apparaatconfiguratie kan worden geconfigureerd.

Application Guard is alleen beschikbaar voor apparaten met de 64 bitsversie van Windows 10. Met dit profiel wordt een Win32-onderdeel geïnstalleerd om Application Guard te activeren.

- **Application Guard**: **Inschakelen** om deze functie aan te zetten. Hiermee worden niet-goedgekeurde sites in een Hyper-V gevirtualiseerde browsercontainer geopend. **Niet geconfigureerd** (standaard): hiermee wordt een site (goedgekeurd en niet-goedgekeurd) geopend op het apparaat.
- **Klembordgedrag**: kies welke kopieer- en plakbewerkingen zijn toegestaan tussen de lokale pc en de virtuele browser van Application Guard.
- **Externe inhoud op Enterprise-sites**: inhoud van niet-goedgekeurde websites **Blokkeren** zodat deze niet wordt geladen. **Niet geconfigureerd** (standaard): hiermee kunnen niet-zakelijke sites op het apparaat worden geopend.
- **Afdrukken vanuit virtuele browser**: **Toestaan** dat PDF-, XPS- en lokale of netwerkprinters inhoud vanuit de virtuele browser kunnen afdrukken. **Niet geconfigureerd** (standaard): hiermee schakelt u alle afdrukfuncties uit.
- **Logboeken verzamelen**: **Toestaan** om logboeken te verzamelen voor gebeurtenissen die zich voordoen in een Application Guard-browsersessie. **Niet geconfigureerd** (standaard): verzamelt geen logboeken binnen de browsersessie.
- **Door de gebruiker gegenereerde browsergegevens behouden**: **Toestaan** dat gebruikersgegevens (zoals wachtwoorden, favorieten en cookies) worden opgeslagen die zijn gemaakt tijdens een virtuele browsersessie met Application Guard. **Niet geconfigureerd** (standaard): hiermee worden door de gebruiker gedownloade bestanden en gegevens genegeerd wanneer het apparaat opnieuw wordt opgestart of wanneer een gebruiker zich afmeldt.
- **Grafische versnelling**: **Inschakelen** om grafisch-intensieve websites en video’s sneller te laden door toegang te krijgen tot een virtuele grafische verwerkingseenheid. **Niet geconfigureerd** (standaard): hiermee wordt de CPU van het apparaat gebruikt voor grafische weergave; de virtuele grafische verwerkingseenheid wordt niet gebruikt.
- **Bestanden downloaden naar hostbestandssysteem**: **Inschakelen** zodat gebruikers bestanden downloaden van de gevirtualiseerde browser naar het hostbesturingssysteem. **Niet geconfigureerd** (standaard): hiermee houdt u de bestanden lokaal op het apparaat en downloadt u bestanden niet naar het hostbestandsysteem.

## <a name="windows-defender-firewall"></a>Windows Defender Firewall

Wordt ondersteund op de volgende edities van Windows 10:
- Home
- Professional
- Zakelijk
- Zakelijk
- Education
- Mobiel
- Mobile Enterprise

### <a name="global-settings"></a>Globale instellingen

Deze instellingen gelden voor alle netwerktypen.

- **File Transfer Protocol**: **Blokkeren** om stateful FTP uit te schakelen. Indien ingesteld op **Niet geconfigureerd** (standaard): hiermee past de firewall stateful FTP-filtering toe om secundaire verbindingen toe te staan.
- **Niet-actieve tijd voordat beveiligingskoppeling wordt verwijderd**: beveiligingskoppelingen worden verwijderd nadat gedurende *n* seconden geen netwerkverkeer wordt gedetecteerd. Voer een niet-actieve tijd in seconden in.
- **Vooraf gedeelde sleutels coderen**: **Inschakelen** om codering van vooraf gedeelde sleutels met UTF-8 te gebruiken. **Niet geconfigureerd** (standaard): hiermee maakt u gebruik van de waarde van het lokale archief.
- **IPsec-uitzonderingen**: configureer specifiek verkeer dat moet worden uitgesloten van IPsec, met inbegrip van:
  - **ICMP-type-codes voor IPv6 detecteren met neighbor**
  - **ICMP**
  - **ICMP-type-codes voor IPv6 detecteren met router**
  - **Zowel IPv4 als IPv6 DHCP-netwerkverkeer**
- **Controle van certificaatintrekkingslijsten**: bepaal hoe controle van certificaatintrekkingslijsten wordt afgedwongen, zoals **CRL-controle uitschakelen**, **CRL-verificatie mislukt alleen bij alleen ingetrokken certificaat** en **CRL-verificatie mislukt bij elke fout die wordt aangetroffen**.
- **Verificatieset opportunistisch afstemmen per sleutelmodule**: **Inschakelen** zodat sleutelmodules alleen de verificatiepakketten die ze niet ondersteunen, MOETEN negeren. Wanneer **Niet geconfigureerd** is ingesteld, MOETEN sleutelmodules de volledige verificatieset negeren als ze niet alle verificatiepakketten opgegeven in de set ondersteunen.
- **Pakketten in wachtrij plaatsen**: voer in hoe schalen voor software aan de ontvangstzijde worden ingeschakeld voor versleuteld ontvangen en ongecodeerd doorsturen in het scenario voor de IPsec-tunnelgateway. Deze instelling garandeert dat de pakketvolgorde behouden blijft.

### <a name="network-settings"></a>Netwerkinstellingen

Deze instellingen zijn van toepassing op specifieke netwerktypen, waaronder **Domeinnetwerk (werkplek)**, **Privénetwerk (detecteerbaar)** en **Openbaar netwerk (niet-detecteerbaar)**.

#### <a name="general-settings"></a>Algemene instellingen

- **Windows Defender Firewall**: **Inschakelen** om de firewall en geavanceerde beveiliging aan te zetten. **Niet geconfigureerd** (standaard): hiermee staat u al het netwerkverkeer toe, ongeacht andere beleidsinstellingen.
- **Verborgen modus**: met deze optie kunt u de firewall in de verborgen modus **Blokkeren**. Als u de verborgen modus blokkeert, blokkeert u ook **Uitsluiting van beveiligd IPsec-pakket**. Wanneer **Niet geconfigureerd** (standaard) is ingesteld, werkt de firewall in verborgen modus, waarmee reacties op probing-verzoeken worden verhinderd.
- **Afgeschermd**: met **Blokkeren** schakelt u deze functie uit. Met **Niet geconfigureerd** (standaard): schakelt u deze instelling in. Wanneer deze instelling en Windows Defender Firewall zijn ingeschakeld, wordt al het binnenkomende verkeer geblokkeerd, ongeacht andere beleidsinstellingen.
- **Unicast-antwoorden voor multicast-broadcasts**: indien ingesteld op **Blokkeren**, schakelt u met deze optie unicast-antwoorden voor multicast-broadcasts uit. Normaal gesproken wilt u geen unicast-antwoorden voor multicast-broadcasts ontvangen. Deze antwoorden kunnen wijzen op een DOS-aanval (denial of service) of een aanvaller die een computer wil binnendringen. Met **Niet geconfigureerd** (standaard) schakelt u deze instelling in.
- **Binnenkomende meldingen**: indien ingesteld op **Blokkeren**, worden meldingen aan gebruikers verborgen wanneer een toepassing wordt geblokkeerd voor het luisteren naar een poort. **Niet geconfigureerd** (standaard): hiermee wordt deze instelling ingeschakeld en kan mogelijk een melding weergeven aan gebruikers wanneer een app wordt geblokkeerd en niet op een poort mag luisteren.
- **Standaardactie voor binnenkomende verbindingen**: indien ingesteld op **Blokkeren**, wordt de standaardfirewallactie niet uitgevoerd op binnenkomende verbindingen. Als de waarde is ingesteld op **Niet geconfigureerd** (standaard), wordt de standaardfirewallactie uitgevoerd op binnenkomende verbindingen.

#### <a name="rule-merging"></a>Regel samenvoegen

- **Windows Defender Firewall-regels uit het lokale archief voor de gemachtigde toepassing**: **Inschakelen** om firewallregels toe te passen in het lokale archief om te worden herkend en afgedwongen. Wanneer **Niet geconfigureerd** (standaard) is ingesteld, worden de firewallregels van de gemachtigde toepassing in het lokale archief genegeerd en worden deze niet afgedwongen.
- **Algemene poortfirewallregels van Windows Defender uit het lokale archief**: **Inschakelen** om toe te passen dat algemene poortfirewallregels in het lokale archief worden herkend en afgedwongen. Wanneer **Niet geconfigureerd** (standaard) is ingesteld, worden de firewallregels van de globale poort in het lokale archief genegeerd en worden deze niet afgedwongen.
- **Windows Defender Firewall-regels uit het lokale archief**: **Inschakelen** om toe te passen dat algemene firewallregels in het lokale archief worden herkend en afgedwongen. Wanneer **Niet geconfigureerd** (standaard) is ingesteld, worden de firewallregels van het lokale archief genegeerd en worden deze niet afgedwongen.
- **IPsec-regels vanuit het lokale archief**: **Inschakelen** om beveiligingsregels voor verbindingen uit het lokale archief toe te passen, ongeacht het schema of de versies van de beveiligingsregels voor verbindingen. Wanneer **Niet geconfigureerd** (standaard) is ingesteld, worden de beveiligingsregels voor verbindingen vanuit het lokale archief genegeerd en niet afgedwongen, ongeacht de versie van het schema en de versie van de beveiligingsregel van de verbinding.

## <a name="windows-defender-smartscreen-settings"></a>Instellingen voor Windows Defender SmartScreen

Wordt ondersteund in de volgens edities van Windows 10 met Microsoft Edge geïnstalleerd:
- Home
- Professional
- Zakelijk
- Zakelijk
- Education
- Mobiel
- Mobile Enterprise

**Instellingen**:

- **SmartScreen voor apps en bestanden**: Windows SmartScreen **Inschakelen** voor het uitvoeren van bestanden en apps. SmartScreen is een antiphishing- en antimalwareonderdeel in de cloud. **Niet geconfigureerd** (standaard) schakelt SmartScreen uit.
- **Niet-geverifieerde bestandsuitvoering**: **blokkeer** eindgebruikers en sta niet toe dat ze bestanden uitvoeren die niet zijn geverifieerd door Windows SmartScreen. **Niet geconfigureerd** (standaard): hiermee wordt deze functie uitgeschakeld, waardoor eindgebruikers bestanden kunnen uitvoeren die nog niet zijn geverifieerd.

## <a name="windows-encryption"></a>Windows-versleuteling

### <a name="windows-settings"></a>Windows-instellingen

Wordt ondersteund op de volgende edities van Windows 10:

- Professional
- Zakelijk
- Zakelijk
- Education
- Mobiel
- Mobile Enterprise

**Instellingen**:

- **Apparaten versleutelen**: **vereis** van gebruikers dat ze apparaatversleuteling inschakelen. Afhankelijk van de Windows-editie en de systeemconfiguratie, kunnen gebruikers:  
  - Worden gevraagd te bevestigen dat versleuteling van een andere provider niet is ingeschakeld
  - Worden verplicht BitLocker-stationsversleuteling uit te schakelen en vervolgens weer in te schakelen
    
    Als Windows-versleuteling is ingeschakeld terwijl een andere versleutelingsmethode actief is, wordt het apparaat mogelijk instabiel. 
- **Opslagkaart versleutelen (alleen mobiel)**: **vereis** dat verwijderbare opslagkaarten die door het apparaat worden gebruikt, worden versleuteld. **Niet geconfigureerd** (standaard): hiermee is geen versleuteling van de opslagkaart vereist en wordt de gebruiker niet gevraagd deze in te schakelen. Deze instelling geldt alleen voor Windows 10 Mobile-apparaten.

### <a name="bitlocker-base-settings"></a>Basisinstellingen voor BitLocker

Wordt ondersteund op de volgende edities van Windows 10:

- Zakelijk
- Education
- Mobiel
- Mobile Enterprise

Basisinstellingen zijn universele BitLocker-instellingen voor alle soorten gegevensstations. Met deze instellingen wordt beheerd welke schijfversleutelingstaken of configuratieopties de eindgebruiker kan wijzigen op alle soorten gegevensstations.

- **Waarschuwing voor andere schijfversleuteling**: selecteer **Blokkeren** om de waarschuwingsmelding uit te schakelen als er een andere schijfversleutelingsservice op het apparaat is. **Niet geconfigureerd** (standaard): hiermee wordt toegestaan dat de waarschuwing wordt weergegeven.
- **Versleutelingsmethoden configureren**: u moet deze instelling **inschakelen** om versleutelingsalgoritmen te configureren voor het besturingssysteem, de gegevens en de verwisselbare stations. Wanneer **Niet geconfigureerd** (standaard) is ingesteld, gebruikt BitLocker XTS-AES-128-bits als de standaardmethode voor versleuteling, of wordt de versleutelingsmethode gebruikt die is opgegeven door een installatiescript.
  - **Versleuteling voor stations met besturingssysteem**: kies de versleutelingsmethode stations met een besturingssysteem. Het is raadzaam om het algoritme XTS AES te gebruiken.
  - **Versleuteling voor vaste gegevensschijven**: kies de versleutelingsmethode voor vaste (ingebouwde) schijven, ook wel 'harde schijven' genoemd. Het is raadzaam om het algoritme XTS AES te gebruiken.
  - **Versleuteling voor verwisselbare gegevensstations**: kies de versleutelingsmethode voor verwisselbare gegevensstations. Als het verwisselbare station wordt gebruikt met apparaten waarop Windows 10 niet wordt uitgevoerd, wordt aanbevolen het algoritme AES-CBC te gebruiken.

### <a name="bitlocker-os-drive-settings"></a>BitLocker-instellingen voor station met besturingssysteem
Wordt ondersteund op de volgende edities van Windows 10:

- Zakelijk
- Education
- Mobiel
- Mobile Enterprise

Deze instellingen zijn van toepassing zijn op gegevensstations van het besturingssysteem.

- **Extra authenticatie vereisen bij opstarten**: selecteer **Vereisen** om de authenticatievereisten voor het opstarten van de computer te configureren, zoals het gebruik van TPM (Trusted Platform Module). Selecteer **Niet geconfigureerd** (standaard) om alleen eenvoudige opties te configureren op apparaten met een TPM.
  - **BitLocker met niet-compatibele TPM-chip**: **blokkeer** (schakel uit) met BitLocker wanneer een apparaat niet beschikt over een compatibele TPM-chip. Wanneer **Niet geconfigureerd** is ingesteld, kunnen gebruikers BitLocker gebruiken zonder een compatibele TPM-chip. BitLocker vereist mogelijk een wachtwoord of een opstartsleutel.
  - **Compatibele TPM opstarten**: kies ervoor om de TPM-chip toe te staan, niet toe te staan of te vereisen.
  - **Compatibele TPM-opstartpincode**: kies ervoor om het gebruik van een opstartpincode met de TPM-chip toe te staan, niet toe te staan of te vereisen. Voor het inschakelen van een opstartpincode is interactie van de eindgebruiker vereist. 
  - **Compatibele TPM-opstartsleutel**: kies ervoor om het gebruik van een opstartsleutel met de TPM-chip toe te staan, niet toe te staan of te vereisen. Voor het inschakelen van een opstartsleutel is interactie van de eindgebruiker vereist. 
  - **Compatibele opstartsleutel en pincode voor TPM**: kies ervoor om het gebruik van een opstartsleutel en -pincode met de TPM-chip toe te staan, niet toe te staan of te vereisen. Voor het inschakelen van een opstartsleutel en een pincode is interactie van de eindgebruiker vereist.
- **Minimale lengte pincode**: u moet deze instelling **Inschakelen** om een minimale lengte te configureren voor de TPM-opstartpincode. Wanneer **Niet geconfigureerd** (standaard) is ingesteld, kunnen gebruikers een opstartpincode met een lengte tussen 6 en 20 cijfers configureren.
  - **Minimale aantal tekens**: geef het aantal tekens op dat is vereist voor de opstartpincode, tussen **4**-**20**.
- **Herstellen van besturingssysteemstation**: u moet deze instelling **Inschakelen** om te bepalen hoe met BitLocker beveiligde besturingssysteemstations worden hersteld als de vereiste opstartgegevens niet beschikbaar zijn. Wanneer **Niet geconfigureerd** (standaard) is ingesteld, worden de standaardherstelopties ondersteund voor BitLocker-herstel. Standaard is een DRA toegestaan, de opties voor herstel zijn opgegeven door de gebruiker, met inbegrip van het herstelwachtwoord en de herstelsleutel, en er wordt geen reservekopie van herstelinformatie gemaakt op AD DS.
  - **Agent voor gegevensherstel op basis van certificaten**: als de waarde is ingesteld op **Blokkeren**, kunt u de agent voor gegevensherstel niet gebruiken voor met BitLocker beveiligde OS-stations. Stel deze functie in op **Niet geconfigureerd** (standaard) om deze instelling te schakelen, zodat agenten voor gegevensherstel kunnen worden gebruikt met besturingssysteemstations die met BitLocker zijn beveiligd.
  - **Herstelwachtwoord maken door gebruiker**: kies of gebruikers verplicht of optioneel een herstelwachtwoord van 48 cijfers mogen genereren, of dat dit niet is toegestaan.
  - **Herstelsleutel maken door gebruiker**: kies of gebruikers verplicht of optioneel een herstelsleutel van 256 bits mogen genereren, of dat dit niet is toegestaan.
  - **Herstelopties in de BitLocker-installatiewizard**: stel deze optie in op **Blokkeren** zodat gebruikers de opties voor herstel niet kunnen weergeven en wijzigen. Wanneer **Niet geconfigureerd** (standaard) is ingesteld, kunnen gebruikers de opties voor herstel weergeven en wijzigen wanneer ze BitLocker inschakelen.
  - **BitLocker-herstelgegevens naar AD DS opslaan**: stel deze optie in op **Inschakelen** om de BitLocker-herstelgegevens op te slaan in Azure Active Directory (AAD). Wanneer **Niet geconfigureerd** (standaard) is ingesteld, worden de herstelgegevens niet opgeslagen in AAD.
  - **BitLocker-herstelgegevens opgeslagen naar AD DS**: hiermee bepaalt u welke delen van de BitLocker-herstelgegevens worden opgeslagen in Azure AD. U kunt kiezen uit:
    - **Back-up maken van herstelwachtwoorden en sleutelpakketten**
    - **Alleen een back-up maken van herstelwachtwoorden**
  - **Herstelgegevens opslaan in AD DS voordat BitLocker wordt ingeschakeld**: stel deze instelling in op **Vereisen** om te voorkomen dat gebruikers BitLocker inschakelen, tenzij de BitLocker-herstelgegevens met succes zijn opgeslagen in Active Directory. Wanneer **Niet geconfigureerd** (standaard) is ingesteld, kunnen gebruikers BitLocker inschakelen, zelfs als herstelgegevens niet met succes zijn opgeslagen in Azure Active Directory.
- **Preboot-herstelbericht en -URL**: stel deze instelling in op **Inschakelen** om het bericht en de URL te configureren die worden weergegeven op het preboot-scherm voor sleutelherstel. Met **Niet geconfigureerd** (standaard) schakelt u deze functie uit.
  - **Preboot-herstelbericht**: configureer hoe preboot-herstelbericht wordt weergegeven aan gebruikers. U kunt kiezen uit:
    - **Standaardherstelbericht en URL gebruiken**
    - **Leeg herstelbericht en -URL gebruiken**
    - **Aangepaste herstelbericht gebruiken**
    - **Aangepaste herstel-URL gebruiken**

### <a name="bitlocker-fixed-data-drive-settings"></a>BitLocker-instellingen voor vaste-gegevensstations

Wordt ondersteund op de volgende edities van Windows 10:

- Zakelijk
- Education
- Mobiel
- Mobile Enterprise

**Instellingen**:

- **Schrijftoegang naar vaste-gegevensstations niet door BitLocker beveiligd**: stel deze optie in op **Blokkeren** om alleen-lezentoegang te geven tot de gegevensschijven die niet met BitLocker zijn beveiligd. Wanneer **Niet geconfigureerd** (standaard) is ingesteld, is er lees- en schrijftoegang tot de schijven die niet met BitLocker zijn beveiligd.
- **Vast-stationherstel**: stel deze optie in op **Inschakelen** om te bepalen hoe met BitLocker beveiligde vaste schijven worden hersteld als de vereiste opstartgegevens niet beschikbaar zijn. Met **Niet geconfigureerd** (standaard) schakelt u deze functie uit.
  - **Agent voor gegevensherstel**: u kunt het gebruik van de agent voor gegevensherstel met door BitLocker beveiligde harde schijven met beleidseditor **Blokkeren**. Met **Niet geconfigureerd** (standaard) schakelt u het gebruik van agents voor gegevensherstel met BitLocker beveiligde vaste schijven in.
  - **Herstelwachtwoord maken door gebruiker**: hiermee configureert u of gebruikers verplicht of optioneel een herstelwachtwoord van 48 cijfers mogen genereren, of dat dit niet is toegestaan.  
  - **Herstelsleutel maken door gebruiker**: hiermee configureert u of gebruikers verplicht of optioneel een herstelsleutel van 256 bits mogen genereren, of dat dit niet is toegestaan.
  - **Herstelopties in de BitLocker-installatiewizard**: stel deze optie in op **Blokkeren** zodat gebruikers de opties voor herstel niet kunnen weergeven en wijzigen. Wanneer **Niet geconfigureerd** (standaard) is ingesteld, kunnen gebruikers de opties voor herstel weergeven en wijzigen wanneer ze BitLocker inschakelen.
  - **BitLocker-herstelgegevens naar AD DS opslaan**: stel deze optie in op **Inschakelen** om de opslag van BitLocker-herstelgegevens op te slaan in Active Directory. Wanneer **Niet geconfigureerd** (standaard) is ingesteld, worden de herstelgegevens niet opgeslagen in AAD.
  - **BitLocker-herstelgegevens naar AD DS**: hiermee bepaalt u welke onderdelen van BitLocker-herstelgegevens worden opgeslagen in Azure Active Directory. U kunt kiezen uit:
    - **Back-up maken van herstelwachtwoorden en sleutelpakketten**
    - **Alleen een back-up maken van herstelwachtwoorden**
  - **Herstelgegevens opslaan in AD DS voordat BitLocker wordt ingeschakeld**: stel deze instelling in op **Vereisen** om te voorkomen dat gebruikers BitLocker inschakelen, tenzij de BitLocker-herstelgegevens met succes zijn opgeslagen in Active Directory. Wanneer **Niet geconfigureerd** (standaard) is ingesteld, kunnen gebruikers BitLocker inschakelen, zelfs als herstelgegevens niet met succes zijn opgeslagen in Azure Active Directory.

### <a name="bitlocker-removable-data-drive-settings"></a>BitLocker-instellingen voor verwisselbare gegevensstations

Wordt ondersteund op de volgende edities van Windows 10:

- Zakelijk
- Education
- Mobiel
- Mobile Enterprise

**Instellingen**:

- **Schrijftoegang naar verwisselbare gegevensstations niet door BitLocker beveiligd**: stel deze optie in op **Blokkeren** om alleen-lezen toegang te geven tot de gegevensschijven die niet met BitLocker zijn beveiligd. Wanneer **Niet geconfigureerd** (standaard) is ingesteld, is er lees- en schrijftoegang tot de schijven die niet met BitLocker zijn beveiligd.
  - **Schrijftoegang voor apparaten die zijn geconfigureerd in een andere organisatie**: stel in op **Blokkeren** om schrijftoegang toe te staan tot apparaten die zijn geconfigureerd in een andere organisatie. Met **Niet geconfigureerd** (standaard) weigert u schrijftoegang.

## <a name="windows-defender-exploit-guard"></a>Windows Defender Exploit Guard

Wordt ondersteund op de volgende edities van Windows 10:

- Home
- Professional
- Zakelijk
- Zakelijk
- Education
- Mobiel
- Mobile Enterprise

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

Als u beveiliging tegen misbruik wilt inschakelen, maakt u een XML-bestand met de gewenste beperkingsinstellingen voor het systeem en de toepassing. Er zijn twee methoden:

 1. PowerShell: gebruik een of meer van de Get-ProcessMitigation, Set-ProcessMitigation en ConvertTo-ProcessMitigationPolicy PowerShell-cmdlets. Met de cdmlets worden beperkingsinstellingen geconfigureerd en wordt hiervan een XML-weergave geëxporteerd.

 2. Gebruikersinterface van het Windows Defender-beveiligingscentrum: klik in het Windows Defender-beveiligingscentrum op het besturingselement voor de app en browser en scrol naar beneden op het scherm om Beveiliging met Exploit Guard te zoeken. Gebruik eerst de tabbladen Systeeminstellingen en Programma-instellingen om de beperkingsinstellingen te configureren. Zoek vervolgens de koppeling Instellingen exporteren onderaan het scherm om een XML-weergave hiervan te exporteren.

Blokkeer **bewerking door gebruikers van de Exploit Protection-interface** door een XML-bestand te uploaden waarmee uw het geheugen, de controlestroom en de beleidsbeperkingen kunt configureren. De instellingen in het XML-bestand kunnen worden gebruikt om een toepassing te blokkeren tegen aanvallen. Met **Niet geconfigureerd** (standaard) distribueert u geen aangepaste configuratie. 

## <a name="windows-defender-application-control"></a>Windows Defender Application Control

Wordt ondersteund op de volgende edities van Windows 10:

**Mobile Device Management (MDM)**: 
- Professional
- Zakelijk
- Zakelijk
- Education
- Mobiel
- Mobile Enterprise

**Groepsbeleidsbeheer**: 
- Zakelijk

Gebruik **Integriteitsbeleidsregels van de stuurcode van de toepassing** om aanvullende apps te kiezen die worden gecontroleerd door of worden vertrouwd door Windows Defender Application Control. Windows-onderdelen en alle apps uit de Windows Store worden automatisch vertrouwd.

Toepassingen worden niet geblokkeerd wanneer ze in de modus **Alleen controle** worden uitgevoerd. De modus **Alleen controle** registreert alle gebeurtenissen in lokale clientlogboeken.

Als deze modus is ingeschakeld, kan toepassingsbeheer alleen worden uitgeschakeld door de modus te wijzigen van **Afdwingen** naar **Alleen controle**. Als u de modus wijzigt van **Afdwingen** in **Niet geconfigureerd**, wordt toepassingsbeheer op toegewezen apparaten nog steeds afgedwongen.

## <a name="windows-defender-credential-guard"></a>Windows Defender Credential Guard

Wordt ondersteund op de volgende edities van Windows 10:

- Zakelijk

Windows Defender Credential Guard beschermt tegen aanvallen waarbij referenties worden gestolen. Het isoleert geheimen zodat alleen bevoegde systeemsoftware er toegang toe heeft.

De instellingen voor **Credential Guard** omvatten:

- **Uitschakelen**: hiermee wordt Credential Guard extern uitgeschakeld als deze eerder is ingeschakeld met de optie **Ingeschakeld zonder UEFI-vergrendeling**.

- **Inschakelen met UEFI-vergrendeling**: met deze optie kan Credential Guard niet extern worden uitgeschakeld met een registersleutel of via Groepsbeleid.

    > [!NOTE]
    > Als u deze instelling gebruikt en Credential Guard later wilt uitschakelen, moet u het Groepsbeleid instellen op **Uitgeschakeld**. Ook moet u de UEFI-configuratiegegevens fysiek van elke computer wissen. Zolang de UEFI-configuratie behouden blijft, is Credential Guard ingeschakeld.

- **Uitgeschakeld zonder UEFI-vergrendeling**: met deze optie kan Credential Guard extern worden uitgeschakeld via Groepsbeleid. Op de apparaten die gebruikmaken van deze instelling moet Windows 10 versie 1511 en hoger worden uitgevoerd.

Wanneer u Credential Guard inschakelt, worden de volgende vereiste functies ook ingeschakeld:

- **Beveiliging op basis van virtualisatie**: wordt ingeschakeld tijdens de volgende keer opnieuw opstarten. Beveiliging op basis van virtualisatie maakt gebruik van de Windows-Hypervisor om ondersteuning te bieden voor beveiligingsservices.
- **Beveiligd opstarten met directe geheugentoegang**: hiermee schakelt u beveiliging op basis van virtualisatie met beveiligd opstarten en directe geheugentoegang (DMA) in. Voor DMA-beveiliging is hardwareondersteuning vereist en deze wordt alleen ingeschakeld op apparaten die juist zijn geconfigureerd.

## <a name="windows-defender-security-center"></a>Windows Defender Security Center

Wordt ondersteund op de volgende edities van Windows 10:

- Home
- Professional
- Zakelijk
- Zakelijk
- Education
- Mobiel
- Mobile Enterprise

Windows Defender Security Center werkt als een afzonderlijke app of een afzonderlijk proces van de afzonderlijke functies. Deze geeft meldingen weer via het onderhoudscentrum. Het fungeert als een collector of één afzonderlijke plaats om de status te zien en een configuratie van de functies uit te voeren. Meer informatie de documenten over [Windows Defender](https://docs.microsoft.com/windows/threat-protection/windows-defender-security-center/windows-defender-security-center).

#### <a name="windows-defender-security-center-app-and-notifications"></a>Windows Defender Security Center-app en meldingen

Blokkeer de toegang van eindgebruikers tot verschillende gebieden van de Windows Defender-beveiligingscentrum-app. Als u een sectie verbergt, worden ook gekoppelde meldingen geblokkeerd.

- **Virus- en bedreigingsbeveiliging**
- **Prestaties en status van apparaat**
- **Firewall- en netwerkbeveiliging**
- **App- en browserbeheer**
- **Gezinsopties**
- **Meldingen van de weergegeven gebieden van de app**: kies welke meldingen worden weergegeven voor eindgebruikers. Niet-kritieke meldingen zijn bijvoorbeeld samenvattingen van Windows Defender Antivirus-activiteiten en meldingen wanneer scans zijn voltooid. Alle andere meldingen worden beschouwd als kritiek.

#### <a name="it-contact-information"></a>IT-contactgegevens

Geef de IT-contactgegevens op die in de Windows Defender-beveiligingscentrum-app en in de app-meldingen moeten worden weergegeven. U kunt kiezen tussen **In app en in meldingen weergeven**, **Alleen in app weergeven**, **Alleen in meldingen weergeven** en **Niet weergeven**. Voer de **IT-organisatienaam** en ten minste één van de volgende contactopties in:

- **Telefoonnummer of Skype-ID van de IT-afdeling**
- **E-mailadres van de IT-afdeling**
- **URL van de IT-ondersteuningswebsite**

## <a name="local-device-security-options"></a>Beveiligingsopties van lokale apparaten

Wordt ondersteund op de volgende edities van Windows 10:
 
- Home
- Professional
- Zakelijk
- Zakelijk
- Education

Gebruik deze opties voor het configureren van de lokale beveiligingsinstellingen op Windows 10-apparaten.

### <a name="accounts"></a>Accounts

- **Nieuwe Microsoft-accounts toevoegen**: stel deze optie in op **Blokkeren** om te voorkomen dat gebruikers nieuwe Microsoft-accounts aan deze computer toevoegen. Wanneer **Niet geconfigureerd** (standaard) is ingesteld, kunnen gebruikers Microsoft-accounts gebruiken op het apparaat.
- **Extern aanmelden zonder wachtwoord**: stel deze optie in op **Inschakelen** om toe te staan dat lokale accounts met lege wachtwoorden kunnen aanmelden met behulp van het toetsenbord van het apparaat. Met **Niet geconfigureerd** (standaard) kunnen lokale accounts met lege wachtwoorden aanmelden vanaf andere locaties dan het fysieke apparaat.

#### <a name="admin"></a>Administrator

- **Lokaal beheerdersaccount**: stel deze optie in op **Ingeschakeld** om het lokale Administrator-account toe te staan. Stel deze optie in op **Niet geconfigureerd** (standaard) om het lokale Administrator-account uit te schakelen.
- **Naam van beheerdersaccount wijzigen**: definieer een andere accountnaam die moet worden gekoppeld aan de beveiligings-id (SID) van het beheerdersaccount.

#### <a name="guest"></a>Gast

- **Gastaccount**: stel deze optie in op **Ingeschakeld** om het lokale gastaccount toe te staan. Stel deze optie in op **Niet geconfigureerd** (standaard) om het lokale gastaccount uit te schakelen.
- **Naam van gastaccount wijzigen**: definieer een andere accountnaam die moet worden gekoppeld aan de beveiligings-id (SID) van het gastaccount.

### <a name="devices"></a>Apparaten

- **Apparaat ontkoppelen zonder aanmelding**: stel deze optie in op **Blokkeren** zodat gebruikers op de fysieke knop voor uitwerpen van een gedokt draagbaar apparaat kunnen drukken om het apparaat veilig te ontkoppelen. Indien deze optie is ingesteld op **Niet geconfigureerd** (standaard), moet de gebruiker zich aanmelden bij het apparaat en toestemming krijgen om het apparaat los te koppelen.
- **Stuurprogramma's voor gedeelde printers installeren**: indien deze optie is ingesteld op **Ingeschakeld** kan een gebruiker een printerstuurprogramma installeren als onderdeel van het maken van verbinding met een gedeelde printer. Wanneer **Niet geconfigureerd** (standaard) is ingesteld, kunnen alleen beheerders een printerstuurprogramma installeren als onderdeel van het maken van een verbinding met een gedeelde printer.
- **Cd-rom-toegang beperken tot lokale actieve gebruiker**: indien deze optie is **Ingeschakeld**, kan alleen de interactief aangemelde gebruiker de cd-rom-media gebruiken. Als dit beleid is ingeschakeld en niemand interactief is aangemeld, wordt de cd-rom geopend via het netwerk. Wanneer **Niet geconfigureerd** (standaard) is ingesteld, heeft iedereen toegang tot de cd-rom.
- **Verwisselbare media formatteren en uitwerpen**: definieer de personen voor wie het is toegestaan om verwisselbare NTFS-media te formatteren en uit te werpen:
  - **Niet geconfigureerd**
  - **Beheerders**
  - **Beheerders en hoofdgebruikers**
  - **Beheerders en interactieve gebruikers**

### <a name="interactive-logon"></a>Interactief aanmelden

- **Minuten van inactiviteit van vergrendelingsscherm totdat de schermbeveiliging wordt geactiveerd**: voer het maximale aantal minuten van inactiviteit in op het aanmeldingsscherm van het interactieve bureaublad totdat de schermbeveiliging actief wordt.
- **CTRL + ALT + DEL vereisen om aan te melden**: stel deze optie in op **Inschakelen** zodat gebruikers niet op CTRL+ALT+DEL hoeven te drukken om zich aan te melden. Stel deze optie in op **Niet geconfigureerd** (standaard) om van gebruikers te vereisen dat deze op CTRL+ALT+DEL drukken vóór aanmelding bij Windows.
- **Gedrag bij verwijderen van smartcard**: hiermee bepaalt u wat er gebeurt wanneer de smartcard van een aangemelde gebruiker uit de lezer van de smartcard wordt verwijderd. Uw opties zijn:

  - **Werkstation vergrendelen**: het werkstation wordt vergrendeld wanneer de smartcard wordt verwijderd. Met deze optie kunnen gebruikers het gebied verlaten, de smartcard meenemen en toch een beveiligde sessie behouden.
  - **Afmelden forceren**: de gebruiker wordt automatisch afgemeld wanneer de smartcard wordt verwijderd.
  - **Verbinding verbreken bij sessie met Extern bureaublad-services**: als de smartcard wordt verwijderd, wordt de sessie verbroken zonder de gebruiker af te melden. Met deze optie kan de gebruiker de smartcard plaatsen en de sessie later of op een andere met smartcardlezer uitgeruste computer hervatten zonder zich opnieuw te moeten melden. Als de sessie lokaal is, werkt dit beleid op dezelfde manier als Werkstation vergrendelen.

    [Lokaal beleid/Beveiligingsopties](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-localpoliciessecurityoptions#localpoliciessecurityoptions-interactivelogon-smartcardremovalbehavior) biedt meer details.

#### <a name="display"></a>Weergave

- **Gebruikersinformatie op vergrendelingsscherm**: configureer welke gebruikersinformatie wordt weergegeven wanneer de sessie is vergrendeld. Als deze optie niet is geconfigureerd, worden de weergavenaam van de gebruiker, het domein en de gebruikersnaam weergegeven.
  - **Niet geconfigureerd**
  - **Weergavenaam van gebruiker, domein en gebruikersnaam**
  - **Alleen weergavenaam gebruiker**
  - **Gebruikersinformatie niet weergeven**
- **Laatste aangemelde gebruiker verbergen**: met **Inschakelen** verbergt u de gebruikersnaam. Met **Niet geconfigureerd** (standaard) geeft u de gebruikersnaam weer.
- **Gebruikersnaam verbergen bij aanmelden**: als u **Inschakelen** selecteert, verbergt u de gebruikersnaam. Met **Niet geconfigureerd** (standaard) geeft u de gebruikersnaam weer.
- **Titel aanmeldingsbericht**: stel de berichttitel in voor gebruikers die zich aanmelden.
- **Tekst aanmeldingsbericht**: stel de berichttekst in voor gebruikers die zich aanmelden.

### <a name="network-access-and-security"></a>Netwerktoegang en -beveiliging

- **Anonieme toegang tot benoemde pipes en shares**: **Niet geconfigureerd** (standaard) beperkt anonieme toegang tot instellingen voor shares en named pipes. Van toepassing op de instellingen die anoniem kunnen worden gebruikt.
- **Anonieme inventarisatie van SAM-accounts**: anonieme gebruikers **toestaan** de SAM-accounts te inventariseren. Windows staat anonieme gebruikers toe de namen van domeinaccounts en netwerkshares te inventariseren.
- **Anonieme inventarisatie van SAM-accounts en -shares**: **Niet geconfigureerd** (standaard) betekent dat anonieme gebruikers de namen van domeinaccounts en netwerkshares kunnen inventariseren. Als u anonieme inventarisatie van SAM-accounts en -shares wilt verhinderen, stelt u deze in op **Blokkeren**.
- **Hashwaarde van LAN Manager opslaan bij wachtwoordwijziging**: kies bij de volgende wachtwoordwijziging **Toestaan** zodat de LAN Manager (LM) de hash-waarde voor het nieuwe wachtwoord kan opslaan. Als de waarde is ingesteld op **Niet geconfigureerd** (standaard), wordt de hash-waarde niet opgeslagen.
- **PKU2U-verificatieaanvragen**: **blokkeer** PKU2U-verificatieaanvragen aan het apparaat om online-identiteiten te gebruiken. **Niet geconfigureerd** (standaard) staat deze aanvragen toe.
- **Externe RPC-verbindingen met SAM beperken**: **toestaan** dat de standaardtekenreeks van Security Descriptor Definition Language gebruikers en groepen weigert om externe aanroepen naar de SAM uit te voeren. **Niet geconfigureerd** (standaard) de standaardtekenreeks van Security Descriptor Definition Language om gebruikers en groepen toe te staan om externe aanroepen naar de SAM uit te voeren.
  - **Beveiligingsdescriptor**

### <a name="recovery-console-and-shutdown"></a>Herstelconsole en afsluiten

- **Wisselbestand voor virtueel geheugen wissen bij het afsluiten**: stel in op **Inschakelen** om het wisselbestand voor het virtueel geheugen te wissen wanneer het apparaat wordt uitgeschakeld. Met **Niet geconfigureerd** wordt het virtueel geheugen niet gewist.
- **Afsluiten zonder aanmelden**: met **Blokkeren** verbergt u de afsluitoptie in het Windows-aanmeldingsscherm. Gebruikers moet zich aanmelden bij het apparaat en vervolgens afsluiten. Met **Niet geconfigureerd** (standaard) kunnen gebruikers het apparaat afsluiten vanaf het Windows-aanmeldingsscherm.

### <a name="user-account-control"></a>Gebruikersaccountbeheer

- **UIA-integriteit zonder veilige locatie**: indien ingesteld op **Inschakelen**, kunnen apps in een beveiligde locatie in het bestandssysteem alleen uitvoeren met UIA-integriteit. Met **Niet geconfigureerd** (standaard) kunnen apps worden uitgevoerd met UIAccess-integriteit, zelfs als de apps zich niet op een veilige locatie in het bestandssysteem bevinden.
- **Schrijffouten naar bestanden en registers virtualiseren naar locaties per gebruiker**: indien ingesteld op **Blokkeren**, worden schrijffouten in toepassingen tijdens runtime naar gedefinieerde locaties voor het bestandssysteem en register omgeleid. Wanneer **Niet geconfigureerd** (standaard) is ingesteld, treden er fouten op bij toepassingen die gegevens naar de beveiligde locaties schrijven.
- **Alleen bevoegdheden verhogen voor uitvoerbare bestanden die zijn ondertekend en gevalideerd**: stel in op **Ingeschakeld** om de validatie van het PKI-certificeringspad af te dwingen voor een bepaald uitvoerbaar bestand voordat dit mag worden uitgevoerd. Stel in op **Niet geconfigureerd** (standaard) om validatie van het PKI-certificeringspad niet af te dwingen voordat een uitvoerbaar bestand kan uitvoeren.

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
- **Leid vragen om benodigde bevoegdheden naar het interactieve bureaublad van de gebruiker**: als u deze optie instelt op **Inschakelen** worden alle vragen om bevoegdheden naar het bureaublad van de interactieve gebruiker geleid, in plaats van het beveiligde bureaublad. Er worden beleidsinstellingen voor gedrag voor beheerders en standaardgebruikers gebruikt. Met **Niet geconfigureerd** (standaard) dwingt u af dat alle aanvragen om uitbreiding van bevoegdheden naar het beveiligde bureaublad gaan, ongeacht eventuele beleidsinstellingen voor gedrag voor beheerders en standaardgebruikers.
- **Prompt met verhoogde bevoegdheden voor app-installaties**: indien ingesteld op **Blokkeren**, worden installatiepakketten voor toepassingen niet gedetecteerd of gevraagd om benodigde bevoegdheden. Wanneer **Niet geconfigureerd** (standaard) is ingesteld, wordt de gebruiker gevraagd om een gebruikersnaam en wachtwoord voor de beheerder wanneer het installatiepakket van een toepassing verhoogde bevoegdheden vereist.
- **Vragen om benodigde UIA-bevoegdheden zonder beveiligd bureaublad**: stel in op **Inschakelen** om UIAccess-apps toe te staan te vragen om benodigde bevoegdheden zonder het beveiligde bureaublad te gebruiken. Wanneer **Niet geconfigureerd** (standaard) is ingesteld, worden de vragen om de benodigde bevoegdheden naar een beveiligd bureaublad geleid.

#### <a name="admin-approval-mode-settings"></a>Instellingen voor de modus Door administrator goedkeuren

- **Modus Door administrator goedkeuren voor geïntegreerde beheerder**: indien de waarde **Ingeschakeld** is ingesteld, kan het ingebouwde Administrator-account de modus Door administrator goedkeuren gebruiken. Voor elke bewerking waarvoor uitbreiding van toegangsrechten is vereist, wordt de gebruiker gevraagd de bewerking goed te keuren. Met **Niet geconfigureerd** (standaard) voert u alle apps uit met volledige beheerdersbevoegdheden.
- **Alle beheerders uitvoeren in de modus Door administrator goedkeuren**: stel in op **Blokkeren** om de modus Door administrator goedkeuren en alle verwante UAC-beleidsinstellingen uit te schakelen. Met **Niet geconfigureerd** (standaard) wordt de modus Door administrator goedkeuren ingeschakeld.

### <a name="microsoft-network-client"></a>Microsoft Network Client

- **Clientcommunicatie digitaal ondertekenen (indien mogelijk)**: hiermee wordt bepaald of de SMB-client onderhandelt over SMB-pakketondertekening. Wanneer **Niet geconfigureerd** of ingeschakeld (standaard) is ingesteld, vraagt Microsoft Network Client de server om SMB-pakketondertekening uit te voeren bij het instellen van een sessie. Als pakketondertekening is ingeschakeld op de server, wordt over ondertekening van pakketten onderhandeld. Als deze optie is ingesteld op **Uitschakelen**, onderhandelt de SMB-client nooit over SMB-pakketondertekening.
- **Niet-versleuteld wachtwoord verzenden om verbinding te kunnen maken met niet-Microsoft SMB-servers**: indien ingesteld op **Inschakelen**, kan de SMB-redirector (Server Message Block) ongecodeerde wachtwoorden verzenden naar niet-Microsoft SMB-servers die geen ondersteuning voor wachtwoordversleuteling bieden tijdens verificatie. Wanneer **Niet geconfigureerd** (standaard) is ingesteld, worden de wachtwoorden versleuteld.

### <a name="microsoft-network-server"></a>Microsoft Network Server

- **Communicatie digitaal ondertekenen (bij akkoord van client)**: hiermee wordt bepaald of de SMB-server onderhandelt over SMB-pakketondertekening met clients die dit aanvragen. Indien ingesteld op **Inschakelen**, onderhandelt de Microsoft-netwerkserver over SMB-pakketondertekening zoals aangevraagd door de client. Ofwel, als pakketondertekening is ingeschakeld op de client, wordt over ondertekening van pakketten onderhandeld. Als deze instelling **niet geconfigureerd** of uitgeschakeld (standaardwaarde) is, onderhandelt de SMB-client nooit over SMB-pakketondertekening.
- **Communicatie digitaal ondertekenen (altijd)**: hiermee wordt bepaald of het ondertekenen van pakketten wordt vereist door de SMB-servercomponent. Als deze instelling is ingesteld op **Inschakelen**, communiceert de Microsoft-netwerkserver niet met een Microsoft-netwerkclient, tenzij die client akkoord gaat met het uitvoeren van SMB-pakketondertekening. Als deze instelling is ingesteld op **Niet geconfigureerd** of is uitgeschakeld (standaard), wordt over het ondertekenen van SMB-pakketten onderhandeld door de client en de server.

## <a name="next-steps"></a>Volgende stappen

Zie [Apparaatprofielen toewijzen](device-profile-assign.md) als u dit profiel wilt toewijzen aan groepen.
