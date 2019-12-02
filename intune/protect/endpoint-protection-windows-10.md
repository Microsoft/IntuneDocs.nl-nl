---
title: Beveiligingsinstellingen voor Windows 10-apparaten in Microsoft Intune - Azure | Microsoft Docs
description: Op Windows 10-apparaten kunt u instellingen voor eindpuntbescherming gebruiken of configureren om functies van Microsoft Defender in te schakelen, zoals Application Guard, Firewall, SmartScreen, versleuteling en Bitlocker, Exploit Guard, Application Control, Security Center en beveiliging van lokale apparaten in Microsoft Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 11/13/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 3af7c91b-8292-4c7e-8d25-8834fcf3517a
ms.reviewer: karthig
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: e2909e7ad1ced9483a6cec58f1f3009f56946f5f
ms.sourcegitcommit: 78cebd3571fed72a3a99e9d33770ef3d932ae8ca
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 11/13/2019
ms.locfileid: "74058430"
---
# <a name="windows-10-and-later-settings-to-protect-devices-using-intune"></a>Instellingen voor Windows 10 (en hoger) om apparaten te beveiligen met Intune

Microsoft Intune bevat veel instellingen om uw apparaten te beveiligen. In dit artikel worden alle instellingen beschreven die u kunt inschakelen en configureren op apparaten met Windows 10 en hoger. Deze instellingen zijn gemaakt in een configuratieprofiel voor eindpuntbeveiliging in Intune om beveiligingsfuncties te beheren, zoals BitLocker en Microsoft Defender.  

Zie [Apparaatbeperkingsinstellingen voor Windows 10](../configuration/device-restrictions-windows-10.md#microsoft-defender-antivirus) als u Microsoft Defender Antivirus wilt configureren.  

## <a name="before-you-begin"></a>Voordat u begint  

[Maak een configuratieprofiel voor eindpuntbeveiliging op een apparaat](endpoint-protection-configure.md).  

Zie [Configuration service provider Reference](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference)(Engelstalig) voor meer informatie over Configuration service providers (csp's).  

## <a name="microsoft-defender-application-guard"></a>Microsoft Defender Application Guard  

Wanneer u Microsoft Edge gebruikt, beschermt Microsoft Defender Application Guard uw omgeving tegen sites die niet worden vertrouwd door uw organisatie. Als gebruikers sites bezoeken die niet worden vermeld in uw geïsoleerde netwerkgrens, worden deze sites geopend in een virtuele browsersessie in Hyper-V. Vertrouwde sites worden gedefinieerd door een netwerkgrens, die in Apparaatconfiguratie wordt geconfigureerd.  

Application Guard is alleen beschikbaar voor apparaten met de 64 bitsversie van Windows 10. Met dit profiel wordt een Win32-onderdeel geïnstalleerd om Application Guard te activeren.  

- **Application Guard**  
  **Standaard**: niet geconfigureerd  
   Application Guard CSP: [instellingen/AllowWindowsDefenderApplicationGuard](https://docs.microsoft.com/windows/client-management/mdm/windowsdefenderapplicationguard-csp#allowwindowsdefenderapplicationguard)  

  - **Ingeschakeld voor Edge**: hiermee wordt deze functie ingeschakeld en worden niet-vertrouwde sites geopend in een met Hyper-V gevirtualiseerde browsercontainer.  
  - **Niet geconfigureerd** : elke site (vertrouwd en niet-vertrouwd) kan op het apparaat worden geopend.  

- **Klembordgedrag**  
  **Standaard**: niet geconfigureerd  
   Application Guard CSP: [instellingen/ClipboardSettings](https://go.microsoft.com/fwlink/?linkid=872351)  

  Kies welke kopieer- en plakbewerkingen zijn toegestaan tussen de lokale pc en de virtuele browser van Application Guard.  
  - **Niet geconfigureerd**  
  - **Alleen kopiëren en plakken van de PC naar de browser toestaan**  
  - **Alleen kopiëren en plakken van de browser naar de PC toestaan**  
  - **Kopiëren en plakken tussen de PC en de browser toestaan**  
  - **Kopiëren en plakken tussen de PC en de browser blok keren**  

- **Klembord inhoud**  
  Deze instelling is alleen beschikbaar als het *Klembord gedrag* is ingesteld op een van de instellingen *toestaan* .  
  **Standaard**: niet geconfigureerd  
  Application Guard CSP: [instellingen/ClipboardFileType](https://docs.microsoft.com/windows/client-management/mdm/windowsdefenderapplicationguard-csp#clipboardfiletype)  

  De toegestane klembord inhoud selecteren.  
  - **Niet geconfigureerd**  
  - **Tekst**  
  - **Afbeeldingen**  
  - **Tekst en afbeeldingen**  

- **Externe inhoud op bedrijfssites**  
  **Standaard**: niet geconfigureerd  
  Application Guard CSP: [instellingen/BlockNonEnterpriseContent](https://go.microsoft.com/fwlink/?linkid=872352)  

  - **Blokkeren**: inhoud van niet-goedgekeurde websites blokkeren, zodat deze niet kan worden geladen.  
  - **Niet geconfigureerd**: niet-bedrijfssites kunnen op het apparaat worden geopend.  
 
- **Afdrukken vanuit virtuele browser**  
  **Standaard**: niet geconfigureerd  
  Application Guard CSP: [instellingen/PrintingSettings](https://go.microsoft.com/fwlink/?linkid=872354)  

  - **Toestaan** : Hiermee staat u het afdrukken van geselecteerde inhoud vanuit de virtuele browser toe.  
  - **Niet geconfigureerd** Alle afdruk functies uitschakelen.  

  Wanneer u afdrukken *toestaat* , kunt u de volgende instelling configureren:
  - **Afdruk type (n)** Selecteer een of meer van de volgende opties:  
    - PDF  
    - XPS  
    - Lokale printers
    - Netwerk printers  

- **Logboeken verzamelen**  
  **Standaard**: niet geconfigureerd  
  Application Guard CSP: [audit-AuditApplicationGuard](https://go.microsoft.com/fwlink/?linkid=872418)  

  - **Toestaan**: logboeken verzamelen voor gebeurtenissen die zich voordoen in een Application Guard-browsersessie.  
  - **Niet geconfigureerd**: geen logboeken verzamelen binnen de browsersessie.  

- **Door de gebruiker gegenereerde browsergegevens behouden**  
  **Standaard**: niet geconfigureerd  
  Application Guard CSP: [instellingen/AllowPersistence](https://go.microsoft.com/fwlink/?linkid=872419)  

  - **Toestaan**: gebruikersgegevens (zoals wachtwoorden, favorieten en cookies) opslaan die worden gemaakt tijdens een virtuele browsersessie met Application Guard.  
  - **Niet geconfigureerd**: door de gebruiker gedownloade bestanden en gegevens verwijderen wanneer het apparaat opnieuw wordt opgestart of wanneer een gebruiker zich afmeldt.  

- **Grafische versnelling**  
 **Standaard**: niet geconfigureerd  
  Application Guard CSP: [instellingen/AllowVirtualGPU](https://go.microsoft.com/fwlink/?linkid=872420)  
      
  - **Inschakelen**: grafisch-intensieve websites en video's worden sneller geladen door toegang tot een virtuele grafische verwerkingseenheid.  
  - **Niet geconfigureerd** De CPU van het apparaat gebruiken voor grafische elementen; Gebruik niet de virtuele grafische verwerkings eenheid.  

- **Bestanden downloaden naar hostbestandssysteem**  
  **Standaard**: niet geconfigureerd  
  Application Guard CSP: [instellingen/SaveFilesToHost](https://go.microsoft.com/fwlink/?linkid=872421)  

  - **Inschakelen**: gebruikers kunnen bestanden vanuit de gevirtualiseerde browser downloaden naar het hostbesturingssysteem.  
  - **Niet geconfigureerd**: hiermee houdt u de bestanden lokaal op het apparaat en downloadt u bestanden niet naar het hostbestandssysteem.  

## <a name="microsoft-defender-firewall"></a>Microsoft Defender firewall  
 
### <a name="global-settings"></a>Globale instellingen  

Deze instellingen gelden voor alle netwerktypen.  

- **File Transfer Protocol**  
  **Standaard**: niet geconfigureerd  
   Firewall CSP: [MdmStore/Global/DisableStatefulFtp](https://go.microsoft.com/fwlink/?linkid=872536)  

  - **Blokkeren**: stateful FTP uitschakelen.  
  - **Niet geconfigureerd**: de firewall past stateful FTP-filtering toe om secundaire verbindingen toe te staan.  

- **Niet-actieve tijd voordat beveiligingskoppeling wordt verwijderd**  
  **Standaard**: *niet geconfigureerd*  
   Firewall CSP: [MdmStore/Global/SaIdleTime](https://go.microsoft.com/fwlink/?linkid=872539)  

   Geef een niet-actieve tijd in seconden op waarna beveiligings koppelingen worden verwijderd.   

- **Vooraf gedeelde sleutels coderen**  
  **Standaard**: niet geconfigureerd  
   Firewall CSP: [MdmStore/Global/PresharedKeyEncoding](https://go.microsoft.com/fwlink/?linkid=872541)  

   - Vooraf geschuingetrokkene sleutels **inschakelen** met UTF-8.  
   - **Niet geconfigureerd** : versleutelen vooraf geschuinde sleutels met de waarde van het lokale archief.  

- **IPsec-uitzonderingen**  
  **Standaard**: *0 geselecteerd*  
   Firewall CSP: [MdmStore/Global/IPsecExempt](https://go.microsoft.com/fwlink/?linkid=872547)

   Selecteer een of meer van de volgende typen verkeer die van IPsec moeten worden uitgesloten:  
   - **ICMP-type-codes voor IPv6 detecteren met neighbor**  
   - **ICMP**  
   - **ICMP-type-codes voor IPv6 detecteren met router**  
   - **Zowel IPv4 als IPv6 DHCP-netwerkverkeer**  

- **Controle van certificaatintrekkingslijsten**  
  **Standaard**: niet geconfigureerd  
  Firewall CSP: [MdmStore/Global/CRLcheck](https://go.microsoft.com/fwlink/?linkid=872548)  

  Bepaal hoe het apparaat certificaatintrekkingslijsten controleert. Opties zijn onder andere:  
  - **CRL-verificatie uitschakelen**  
  - **Mislukte CRL-verificatie voor ingetrokken certificaat**  
  - **MISLUKTE CRL-verificatie bij een fout aangetroffen**.  
 

- **Verificatieset opportunistisch afstemmen per sleutelmodule**  
  **Standaard**: niet geconfigureerd  
  Firewall CSP: [MdmStore/Global/OpportunisticallyMatchAuthSetPerKM](https://go.microsoft.com/fwlink/?linkid=872550)  
  
  - **Inschakelen**: sleutelmodules moeten alleen de verificatiepakketten negeren die ze niet ondersteunen.  
  - **Niet geconfigureerd**: sleutelmodules moeten de volledige verificatieset negeren als ze niet alle verificatiepakketten ondersteunen die zijn opgegeven in de set.  


- **Pakketten in wachtrij plaatsen**  
  **Standaard**: niet geconfigureerd  
  Firewall CSP: [MdmStore/Global/EnablePacketQueue](https://go.microsoft.com/fwlink/?linkid=872551)  

  Geef aan hoe schalen voor software aan de ontvangstzijde wordt ingeschakeld voor versleuteld ontvangen en ongecodeerd doorsturen in het scenario met de IPsec-tunnelgateway. Deze instelling garandeert dat de pakketvolgorde behouden blijft. Opties zijn onder andere:  
  - **Niet geconfigureerd**  
  - **Alle pakket wachtrijen uitschakelen**  
  - **Alleen binnenkomende versleutelde pakketten in de wachtrij**  
  - **Pakketten in wachtrij plaatsen na ontsleutelen wordt alleen uitgevoerd voor door sturen**  
  - **Zowel binnenkomende als uitgaande pakketten configureren**  

### <a name="network-settings"></a>Netwerkinstellingen  

De volgende instellingen worden één keer vermeld in dit artikel, maar zijn allemaal van toepassing op de drie specifieke netwerk typen:  
- **Domein (werk plek) netwerk**  
- **Particulier netwerk (detecteerbaar)**  
- **Openbaar netwerk (niet-detecteerbaar)**  

#### <a name="general-settings"></a>Algemene instellingen  

- **Microsoft Defender firewall**  
  **Standaard**: niet geconfigureerd  
  Firewall CSP: [EnableFirewall](https://go.microsoft.com/fwlink/?linkid=872558)  
  
  - **Inschakelen**: de firewall en geavanceerde beveiliging inschakelen. 
  - **Niet geconfigureerd**: hiermee staat u al het netwerkverkeer toe, ongeacht andere beleidsinstellingen.  

- **Verborgen modus**  
  **Standaard**: niet geconfigureerd  
  Firewall CSP: [DisableStealthMode](https://go.microsoft.com/fwlink/?linkid=872559)  
  - **Niet geconfigureerd**  
  - **Block** -firewall is geblokkeerd voor het werken in de verborgen modus. Als u de verborgen modus blokkeert, blokkeert u ook **Uitsluiting van beveiligd IPsec-pakket**.  
  - **Toestaan** : de firewall werkt in de verborgen modus, waardoor er geen reacties op aanvragen kunnen worden uitgevoerd.  

- **Uitsluiting van beveiligd IPsec-pakket met verborgen modus**  
  **Standaard**: niet geconfigureerd  
  Firewall CSP: [DisableStealthModeIpsecSecuredPacketExemption](https://go.microsoft.com/fwlink/?linkid=872560)  

  Deze optie wordt genegeerd als de *verborgen modus* is ingesteld op *blok keren*.  

  - **Niet geconfigureerd**  
  - **Blok** -IPSec-beveiligde pakketten ontvangen geen uitzonde ringen.  
  - Uitzonde ringen **toestaan** . De verborgen computer modus mag niet verhinderen dat de hostcomputer reageert op ongevraagd netwerk verkeer dat wordt beveiligd door IPsec.  

- **Afgeschermd**  
  **Standaard**: niet geconfigureerd  
  Firewall CSP: [afgeschermd](https://go.microsoft.com/fwlink/?linkid=872561)  
    - **Niet geconfigureerd**  
    - **Blok keren** : wanneer de Microsoft Defender firewall is ingeschakeld en deze instelling is ingesteld op *blok keren*, wordt al het binnenkomende verkeer geblokkeerd, ongeacht andere beleids instellingen. 
    - **Toestaan** : wanneer deze optie is ingesteld op *toestaan*, wordt deze instelling uitgeschakeld en wordt binnenkomend verkeer toegestaan op basis van andere beleids instellingen.

- **Unicast-antwoorden voor multicast-broadcasts**  
  **Standaard**: niet geconfigureerd  
  Firewall CSP: [DisableUnicastResponsesToMulticastBroadcast](https://go.microsoft.com/fwlink/?linkid=872562)  
  
  Normaal gesproken wilt u geen unicast-antwoorden voor multicast-broadcasts ontvangen. Deze antwoorden kunnen wijzen op een DOS-aanval (denial of service) of een aanvaller die een computer wil binnendringen.  
  - **Niet geconfigureerd**  
  - **Blokkeren**:  unicast-antwoorden voor multicast-broadcasts uitschakelen.  
  - **Toestaan**: unicast-antwoorden voor multicast-broadcasts toestaan.  

- **Binnenkomende meldingen**  
  **Standaard**: niet geconfigureerd  
  Firewall CSP: [DisableInboundNotifications](https://go.microsoft.com/fwlink/?linkid=8725630)  

  - **Niet geconfigureerd**  
  - **Blok** : meldingen verbergen die moeten worden gebruikt wanneer een app niet luistert op een poort.  
  - **Toestaan**: hiermee wordt deze instelling ingeschakeld en wordt er mogelijk een melding weergeven aan gebruikers wanneer een app wordt geblokkeerd en niet op een poort mag luisteren.  

- **De standaardactie voor uitgaande verbindingen**  
  **Standaard**: niet geconfigureerd  
  Firewall CSP: [DefaultOutboundAction](https://aka.ms/intune-firewall-outboundaction)  
  
  De standaard actie firewall configureren die wordt uitgevoerd voor uitgaande verbindingen. Deze instelling wordt toegepast op Windows-versie 1809 en hoger.  

  - **Niet geconfigureerd**  
  - **Blok keren** : de standaard actie voor de firewall wordt niet uitgevoerd voor uitgaand verkeer tenzij expliciet wordt opgegeven dat deze niet moet worden geblokkeerd.  
  - **Toestaan** : standaard firewall acties worden uitgevoerd bij uitgaande verbindingen.  

- **De standaardactie voor binnenkomende verbindingen**  
  **Standaard**: niet geconfigureerd  
  Firewall CSP: [DefaultInboundAction](https://go.microsoft.com/fwlink/?linkid=872564)  
 
  - **Niet geconfigureerd**  
  - **Blokkeren**: de standaardfirewallactie wordt niet uitgevoerd op binnenkomende verbindingen.  
  - **Toestaan** : standaard firewall acties worden uitgevoerd op binnenkomende verbindingen.  

#### <a name="rule-merging"></a>Regel samenvoegen  

- **Defender Firewall-regels uit het lokale archief voor de gemachtigde toepassing**  
  **Standaard**: niet geconfigureerd  
  Firewall CSP: [AuthAppsAllowUserPrefMerge](https://go.microsoft.com/fwlink/?linkid=872565)  

  - **Niet geconfigureerd**  
  - **Blokkeren**: de firewallregels van de gemachtigde toepassing in het lokale archief worden genegeerd en worden niet afgedwongen.  
  - **Toestaan**: -
   kies **Inschakelen** om firewallregels in het lokale archief toe te passen zodat deze worden herkend en afgedwongen.  

- **Algemene poortfirewallregels van Microsoft Defender uit het lokale archief**  
  **Standaard**: niet geconfigureerd  
  Firewall CSP: [GlobalPortsAllowUserPrefMerge](https://go.microsoft.com/fwlink/?linkid=872566)  

  - **Niet geconfigureerd**  
  - **Blok** -de firewall regels voor globale poort in het lokale archief worden genegeerd en niet afgedwongen.  
  - **Inschakelen**: algemene poortfirewallregels in het lokale archief toepassen om te herkennen en af te dwingen.  

- **Firewallregels van Microsoft Defender uit het lokale archief**  
  **Standaard**: niet geconfigureerd  
  Firewall CSP: [AllowLocalPolicyMerge](https://go.microsoft.com/fwlink/?linkid=872567)  

  - **Niet geconfigureerd**  
  - **Blok** -firewall regels van het lokale archief worden genegeerd en niet afgedwongen.
  - **Inschakelen**: firewallregels in het lokale archief toepassen om te herkennen en af te dwingen.  

- **IPsec-regels vanuit het lokale archief**  
  **Standaard**: niet geconfigureerd  
  Firewall CSP: [AllowLocalIpsecPolicyMerge](https://go.microsoft.com/fwlink/?linkid=872568)  

  - **Niet geconfigureerd**  
  - **Blokkeren**: de beveiligingsregels voor verbindingen vanuit het lokale archief worden genegeerd en niet afgedwongen, ongeacht de versie van het schema en de versie van de beveiligingsregel van de verbinding.  
  - **Toestaan**: beveiligingsregels voor verbindingen toepassen vanuit het lokale archief, ongeacht het schema of de versies van de beveiligingsregels voor verbindingen.  

### <a name="firewall-rules"></a>Firewallregels  

U kunt een of meer aangepaste firewall regels **toevoegen** . Zie [aangepaste firewall regels toevoegen voor Windows 10-apparaten](endpoint-protection-configure.md#add-custom-firewall-rules-for-windows-10-devices)voor meer informatie.  

Aangepaste firewall regels ondersteunen de volgende opties:  

#### <a name="general-settings"></a>Algemene instellingen:  

- **Naam**  
  **Standaard**: *geen naam*  

  Geef een beschrijvende naam op voor de regel. Deze naam wordt weer gegeven in de lijst met regels die u helpen bij het identificeren ervan.  

- **Beschrijving**  
  **Standaard**: *geen beschrijving*  

  Geef een beschrijving van de regel op.  

- **Richting**   
  **Standaard**: niet geconfigureerd  
  Firewall CSP: [FirewallRules/*FirewallRuleName*/Direction](https://docs.microsoft.com/windows/client-management/mdm/firewall-csp#direction)  
  
  Geef op of deze regel van toepassing is op **Inkomend**of **uitgaand** verkeer. Als deze instelling is ingesteld op **niet geconfigureerd**, wordt de regel automatisch toegepast op uitgaand verkeer.  

- **Actie**  
  **Standaard**: niet geconfigureerd  
  Firewall CSP: [FirewallRules/*FirewallRuleName*/Action](https://docs.microsoft.com/windows/client-management/mdm/firewall-csp#action), en [FirewallRules/*FirewallRuleName*/action/type](https://docs.microsoft.com/windows/client-management/mdm/firewall-csp#type)  

  Selecteer uit **toestaan** of **blok keren**. Als deze instelling is ingesteld op **niet geconfigureerd**, wordt verkeer door de regel standaard toegestaan.  

- **Netwerktype**  
  **Standaard**: 0 geselecteerd  
  Firewall CSP: [FirewallRules/*FirewallRuleName*/Profiles](https://docs.microsoft.com/windows/client-management/mdm/firewall-csp#profiles)  

  Selecteer Maxi maal drie typen netwerk typen waarvan deze regel deel uitmaakt. Opties zijn onder meer **domein**, **privé**en **openbaar**.  Als er geen netwerk typen zijn geselecteerd, is de regel van toepassing op alle drie de netwerk typen.  

#### <a name="application-settings"></a>Toepassingsinstellingen  

- **Toepassing (en)**  
  **Standaard**: alle  

  Verbindingen voor een app of programma beheren. Selecteer een van de volgende opties en voltooi vervolgens de aanvullende configuratie:  
  - **Pakket familie naam** : Geef een familie naam van een pakket op. Gebruik de Power shell **-opdracht Get-AppxPackage**om de familie naam van het pakket te vinden.   
    Firewall CSP: [FirewallRules/*FirewallRuleName*/app/PackageFamilyName](https://docs.microsoft.com/windows/client-management/mdm/firewall-csp#packagefamilyname)  
 
  - **Bestandspad: u** moet een bestandspad opgeven naar een app op het client apparaat. Dit kan een absoluut pad zijn of een relatief pad. Bijvoorbeeld: C:\Windows\System\Notepad.exe of%WINDIR%\Notepad.exe.  
    Firewall CSP: [FirewallRules/*FirewallRuleName*/app/filepath](https://docs.microsoft.com/windows/client-management/mdm/firewall-csp#filepath)  

  - **Windows-service** : Geef de korte naam van de Windows-service op als deze een service is en niet een toepassing die verkeer verzendt of ontvangt. Gebruik de Power shell **-opdracht Get-service**om de korte naam van de service te vinden.  
    Firewall CSP: [FirewallRules/*FirewallRuleName*/app/ServiceName](https://docs.microsoft.com/windows/client-management/mdm/firewall-csp#servicename)  

  - **Alle**: *Er is geen aanvullende configuratie beschikbaar*.  

#### <a name="ip-address-settings"></a>IP-adres instellingen  

Geef de lokale en externe adressen op waarop deze regel van toepassing is.  

- **Lokale adressen**    
  **Standaard**: een adres  
  Firewall CSP: [FirewallRules/*FirewallRuleName*/LocalPortRanges](https://docs.microsoft.com/windows/client-management/mdm/firewall-csp#localportranges)  

  Selecteer **een adres** of **opgegeven adres**.  

  Wanneer u het *opgegeven adres*gebruikt, voegt u een of meer adressen toe als een door komma's gescheiden lijst met lokale adressen die worden gedekt door de regel. Geldige tokens zijn:  
  - Gebruik een asterisk "*" voor *elk* lokaal adres. Als u een asterisk gebruikt, moet dit het enige token zijn dat u gebruikt.  
  - Als u een subnet wilt opgeven, gebruikt u het subnetmasker of de notatie voor het netwerk voorvoegsel. Als geen subnetmasker of netwerk prefix wordt opgegeven, wordt het subnetmasker standaard ingesteld op 255.255.255.255.  
  - Een geldig IPv6-adres.  
  - Een IPv4-adres bereik met de indeling ' begin adres-eind adres ' zonder spaties.  
  - Een IPv6-adres bereik met de indeling ' begin adres-eind adres ' zonder spaties.  

- **Externe adressen**  
  **Standaard**: een adres  
  Firewall CSP: [FirewallRules/*FirewallRuleName*/RemoteAddressRanges](https://docs.microsoft.com/windows/client-management/mdm/firewall-csp#remoteaddressranges)  
 
  Selecteer **een adres** of **opgegeven adres**.  

  Wanneer u het *opgegeven adres*gebruikt, voegt u een of meer adressen toe als een door komma's gescheiden lijst met externe adressen die worden gedekt door de regel. Tokens zijn niet hoofdletter gevoelig. Geldige tokens zijn:  
  - Gebruik een asterisk "*" voor *elk* extern adres. Als u een asterisk gebruikt, moet dit het enige token zijn dat u gebruikt.  
  - "Defaultgateway"  
  - "DHCP"  
  - "DNS"  
  - "WINS"  
  - ' Intranet ' (ondersteund op Windows versie 1809 en hoger)  
  - "RmtIntranet" (ondersteund op Windows-versies 1809 en hoger)  
  - Internet (ondersteund op Windows-versies 1809 en hoger)  
  - "Ply2Renders" (ondersteund op Windows-versies 1809 en hoger)  
  - "LocalSubnet" duidt op een lokaal adres op het lokale subnet.  
  - Als u een subnet wilt opgeven, gebruikt u het subnetmasker of de notatie voor het netwerk voorvoegsel. Als geen subnetmasker of netwerk prefix wordt opgegeven, wordt het subnetmasker standaard ingesteld op 255.255.255.255.  
  - Een geldig IPv6-adres.  
  - Een IPv4-adres bereik met de indeling ' begin adres-eind adres ' zonder spaties.  
  - Een IPv6-adres bereik met de indeling ' begin adres-eind adres ' zonder spaties.  

#### <a name="port-and-protocol-settings"></a>Poort-en Protocol instellingen  
Geef de lokale en externe poorten op waarop deze regel van toepassing is.  

- **Protocol**  
  **Standaard**: alle  
  Firewall CSP: [FirewallRules/*FirewallRuleName*/protocol](https://docs.microsoft.com/windows/client-management/mdm/firewall-csp#protocol)  
  Selecteer een van de volgende opties en voltooi de vereiste configuraties:  
  - **Alle** : er is geen aanvullende configuratie beschikbaar.  
  - **TCP** : lokale en externe poorten configureren. Beide opties ondersteunen alle poorten of opgegeven poorten. Geef opgegeven poorten op met behulp van een door komma's gescheiden lijst.  
    - **Lokale poorten** -firewall-CSP: [FirewallRules/*FirewallRuleName*/LocalPortRanges](https://docs.microsoft.com/windows/client-management/mdm/firewall-csp#localportranges)  
    - **Externe poorten** -firewall-CSP: [FirewallRules/*FirewallRuleName*/RemotePortRanges](https://docs.microsoft.com/windows/client-management/mdm/firewall-csp#remoteportranges)  
  - **UDP** : lokale en externe poorten configureren. Beide opties ondersteunen alle poorten of opgegeven poorten. Geef opgegeven poorten op met behulp van een door komma's gescheiden lijst.  
    - **Lokale poorten** -firewall-CSP: [FirewallRules/*FirewallRuleName*/LocalPortRanges](https://docs.microsoft.com/windows/client-management/mdm/firewall-csp#localportranges)  
    - **Externe poorten** -firewall-CSP: [FirewallRules/*FirewallRuleName*/RemotePortRanges](https://docs.microsoft.com/windows/client-management/mdm/firewall-csp#remoteportranges)  
  - **Aangepast** : Geef een aangepast **protocol** nummer tussen 0 en 255 op.  

#### <a name="advanced-configuration"></a>Geavanceerde configuratie  
- **Interfacetypen**  
  **Standaard**: 0 geselecteerd  
  Firewall CSP: [FirewallRules/*FirewallRuleName*/InterfaceTypes](https://docs.microsoft.com/windows/client-management/mdm/firewall-csp#interfacetypes)  

  Maak een keuze uit de volgende opties:  
  - **Externe toegang**  
  - **Draadloos**  
  - **Lokaal netwerk**  

- **Alleen verbindingen van deze gebruikers toestaan**  
  **Standaard**: alle gebruikers *(standaard al gebruikt wanneer er geen lijst is opgegeven)*  
  Firewall CSP: [FirewallRules/*FirewallRuleName*/LocalUserAuthorizationList](https://aka.ms/intunefirewallauthorizedusers)  

  Geef een lijst met geautoriseerde lokale gebruikers op voor deze regel. Er kan geen lijst met gemachtigde gebruikers worden opgegeven als deze regel van toepassing is op een Windows-service.  


## <a name="microsoft-defender-smartscreen-settings"></a>Instellingen voor Microsoft Defender SmartScreen  
 
Microsoft Edge moet op het apparaat zijn geïnstalleerd.  

- **SmartScreen voor apps en bestanden**  
  **Standaard**: niet geconfigureerd  
   SmartScreen CSP: [SmartScreen-EnableSmartScreenInShell](https://go.microsoft.com/fwlink/?linkid=872784)  

  - **Niet geconfigureerd** : het gebruik van SmartScreen wordt uitgeschakeld.  
  - **Inschakelen**: Windows SmartScreen inschakelen voor het uitvoeren van bestanden en apps. SmartScreen is een antiphishing- en antimalwareonderdeel in de cloud.  

- **Niet-geverifieerde bestandsuitvoering**  
  **Standaard**: niet geconfigureerd  
   SmartScreen CSP: [SmartScreen-PreventOverrideForFilesInShell](https://go.microsoft.com/fwlink/?linkid=872783)

  - **Niet geconfigureerd**: hiermee wordt deze functie uitgeschakeld, waardoor eindgebruikers bestanden kunnen uitvoeren die niet zijn geverifieerd.  
  - **Blokkeren**: voorkomen dat eindgebruikers bestanden uitvoeren die niet zijn geverifieerd door Windows SmartScreen.  

## <a name="windows-encryption"></a>Windows-versleuteling  
 
### <a name="windows-settings"></a>Windows-instellingen  

- **Apparaten versleutelen**  
  **Standaard**: niet geconfigureerd  
  BitLocker CSP: [RequireDeviceEncryption](https://go.microsoft.com/fwlink/?linkid=872523)  

  - **Vereisen**: gebruikers vragen om apparaatversleuteling in te schakelen. Afhankelijk van de Windows-editie en de systeemconfiguratie, kunnen gebruikers:  
    - Worden gevraagd te bevestigen dat versleuteling van een andere provider niet is ingeschakeld.  
    - Worden verplicht BitLocker-stationsversleuteling uit te schakelen en vervolgens weer in te schakelen.  
  - **Niet geconfigureerd**  
  
  Als Windows-versleuteling is ingeschakeld terwijl een andere versleutelingsmethode actief is, wordt het apparaat mogelijk instabiel.  

- **Opslagkaart versleutelen (alleen mobiel)**  
  *Deze instelling geldt alleen voor Windows 10 Mobile.*  
  **Standaard**: niet geconfigureerd  
  BitLocker CSP: [RequireStorageCardEncryption](https://go.microsoft.com/fwlink/?linkid=872524)  

  - Selecteer **Vereisen** om ervoor te zorgen dat verwijderbare opslagkaarten die door het apparaat worden gebruikt, worden versleuteld.  
  - **Niet geconfigureerd**: geen versleuteling van de opslagkaart vereisen en de gebruiker niet vragen om dit in te schakelen.  

### <a name="bitlocker-base-settings"></a>Basisinstellingen voor BitLocker  

Basisinstellingen zijn universele BitLocker-instellingen voor alle soorten gegevensstations. Met deze instellingen wordt beheerd welke schijfversleutelingstaken of configuratieopties de eindgebruiker kan wijzigen op alle soorten gegevensstations.  

- **Waarschuwing voor andere schijfversleuteling**  
  **Standaard**: niet geconfigureerd  
  BitLocker CSP: [AllowWarningForOtherDiskEncryption](https://go.microsoft.com/fwlink/?linkid=872525)  

  - **Blokkeren**: de waarschuwing uitschakelen als op het apparaat een andere service voor schijfversleuteling actief is.  
  - **Niet geconfigureerd** : Hiermee staat u toe dat de waarschuwing voor andere schijf versleuteling wordt weer gegeven.  

  Wanneer deze optie is ingesteld op *blok keren*, kunt u de volgende instelling configureren:  

  - **Standaardgebruikers toestaan om versleuteling in te schakelen tijdens Azure AD Join**  
    *Deze instelling is alleen van toepassing op Azure Active Directory gekoppelde apparaten (Azure ADJ) en is afhankelijk van de vorige instelling `Warning for other disk encryption`.*  
    **Standaard**: niet geconfigureerd  
    BitLocker CSP: [AllowStandardUserEncryption](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp#allowstandarduserencryption)

     - **Toestaan** -standaard gebruikers (niet-beheerders) kunnen BitLocker-versleuteling inschakelen bij het aanmelden.  
     - **Niet geconfigureerd**: alleen beheerders kunnen BitLocker-versleuteling inschakelen op het apparaat.  

- **Versleutelingsmethoden configureren**  
  **Standaard**: niet geconfigureerd  
  BitLocker CSP: [EncryptionMethodByDriveType](https://go.microsoft.com/fwlink/?linkid=872526)  

  - **Inschakelen**: versleutelingsalgoritmen configureren voor het besturingssysteem, gegevens en verwisselbare stations.  
  - **Niet geconfigureerd**: BitLocker gebruikt XTS-AES-128-bits als de standaardmethode voor versleuteling, of de versleutelingsmethode die wordt opgegeven door een installatiescript.  

  Als de optie is ingesteld op *Inschakelen*, kunt u de volgende instellingen configureren:  

  - **Versleuteling voor stations met besturingssysteem**  
    **Standaard**: XTS-AES 128-bits  
   
    Kies de versleutelingsmethode voor stations met een besturingssysteem. Het is raadzaam om het algoritme XTS AES te gebruiken.  
    - **AES-CBC 128-bits**  
    - **AES-CBC 256-bits**  
    - **XTS-AES 128-bits**  
    - **XTS-AES 256-bits**  

  - **Versleuteling voor vaste gegevensschijven**  
    **Standaard**: AES-CBC 128-bits  
   
    Kies de versleutelingsmethode voor vaste (ingebouwde) schijven, ook wel 'harde schijven' genoemd. Het is raadzaam om het algoritme XTS AES te gebruiken.  
    - **AES-CBC 128-bits**  
    - **AES-CBC 256-bits**  
    - **XTS-AES 128-bits**  
    - **XTS-AES 256-bits**  

  - **Versleuteling voor verwisselbare gegevensstations**  
    **Standaard**: AES-CBC 128-bits  

    Kies de versleutelingsmethode voor verwisselbare gegevensstations. Als het verwisselbare station wordt gebruikt met apparaten waarop Windows 10 niet wordt uitgevoerd, wordt aanbevolen het algoritme AES-CBC te gebruiken.  
    - **AES-CBC 128-bits**  
    - **AES-CBC 256-bits**  
    - **XTS-AES 128-bits**  
    - **XTS-AES 256-bits**  

### <a name="bitlocker-os-drive-settings"></a>BitLocker-instellingen voor station met besturingssysteem  

Deze instellingen zijn van toepassing zijn op gegevensstations van het besturingssysteem.  

- **Aanvullende verificatie bij opstarten**  
  **Standaard**: niet geconfigureerd  
  BitLocker CSP: [SystemDrivesRequireStartupAuthentication](https://go.microsoft.com/fwlink/?linkid=872527)  

  - **Vereisen**: de verificatievereisten voor het opstarten van de computer configureren, waaronder het gebruik van TPM (Trusted Platform Module).  
  - **Niet geconfigureerd** : Configureer alleen basis opties op apparaten met een TPM.  

  Als de optie is ingesteld op *Vereisen*, kunt u de volgende instellingen configureren:  

  - **BitLocker met niet-compatibele TPM-chip**  
    **Standaard**: niet geconfigureerd  

    - **Blokkeren**: gebruik van BitLocker uitschakelen wanneer een apparaat niet beschikt over een compatibele TPM-chip.  
    - **Niet geconfigureerd**: gebruikers kunnen BitLocker gebruiken zonder een compatibele TPM-chip. BitLocker vereist mogelijk een wachtwoord of een opstartsleutel.  

  - **Compatibele TPM opstarten**  
    **Standaard**: TPM toestaan  

    Configureer of TPM is toegestaan, vereist of niet toegestaan.  

    - **TPM toestaan**  
    - **TPM niet toestaan**  
    - **TPM vereisen**  

  - **Compatibele TPM-opstartpincode**  
    **Standaard**: opstart pincode met TPM toestaan  

    Kies ervoor om het gebruik van een opstartpincode met de TPM-chip toe te staan, niet toe te staan of te vereisen. Voor het inschakelen van een opstartpincode is interactie van de eindgebruiker vereist.  

    - **Opstart pincode met TPM toestaan**  
    - **Opstart pincode met TPM niet toestaan**  
    - **Opstart pincode met TPM vereisen**

  - **Compatibele TPM-opstartsleutel**  
    **Standaard**: opstart sleutel met TPM toestaan  

    Kies ervoor om het gebruik van een opstartsleutel met de TPM-chip toe te staan, niet toe te staan of te vereisen. Voor het inschakelen van een opstartsleutel is interactie van de eindgebruiker vereist.  

    - **Opstart sleutel met TPM toestaan**  
    - **Opstart sleutel met TPM niet toestaan**  
    - **Opstart sleutel met TPM vereisen**  

  - **Compatibele opstartsleutel en pincode voor TPM**  
    **Standaard**: opstart sleutel en pincode met TPM toestaan  

    Kies ervoor om het gebruik van een opstartsleutel en -pincode met de TPM-chip toe te staan, niet toe te staan of te vereisen. Voor het inschakelen van een opstartsleutel en een pincode is interactie van de eindgebruiker vereist.  
    - **Opstart sleutel en pincode met TPM toestaan**  
    - **Opstart sleutel en pincode met TPM niet toestaan**  
    - **Opstart sleutel en pincode met TPM vereisen**   

- **Minimale lengte pincode**  
    **Standaard**: niet geconfigureerd  
    BitLocker CSP: [SystemDrivesMinimumPINLength](https://go.microsoft.com/fwlink/?linkid=872528)   

    - **Inschakelen** Configureer een minimale lengte voor de TPM-opstart pincode.  
    - **Niet geconfigureerd**: gebruikers kunnen een opstartpincode met een lengte tussen 6 en 20 cijfers configureren.  

  Als de optie is ingesteld op *Inschakelen*, kunt u de volgende instelling configureren:  

  - **Minimum aantal tekens**  
    **Standaard**: *niet geconfigureerde* BitLocker CSP: [SystemDrivesMinimumPINLength](https://go.microsoft.com/fwlink/?linkid=872528)  

    Geef het aantal tekens op dat is vereist voor de opstartpincode, tussen **4**-**20**.  

- **Herstellen van besturingssysteemstation**  
  **Standaard**: niet geconfigureerd   
  BitLocker CSP: [SystemDrivesRecoveryOptions](https://go.microsoft.com/fwlink/?linkid=872529)  

  - **Inschakelen**: bepalen hoe met BitLocker beveiligde besturingssysteemstations worden hersteld als de vereiste opstartgegevens niet beschikbaar zijn.  
  - **Niet geconfigureerd**: de standaardherstelopties worden ondersteund voor BitLocker-herstel. Standaard is een DRA toegestaan, de opties voor herstel zijn opgegeven door de gebruiker, met inbegrip van het herstelwachtwoord en de herstelsleutel, en er wordt geen reservekopie van herstelinformatie gemaakt op AD DS.  

  Als de optie is ingesteld op *Inschakelen*, kunt u de volgende instellingen configureren:  

  - **Agent voor gegevensherstel op basis van certificaten**  
    **Standaard**: niet geconfigureerd  
     
    - **Blok keren** : gebruik voor komen van gegevens herstel agent met met BitLocker beveiligde OS-stations.  
    - **Niet geconfigureerd** : Hiermee staat u toe dat agenten voor gegevens herstel worden gebruikt met met BitLocker beveiligde besturingssysteem stations.  

  - **Herstelwachtwoord maken door gebruiker**  
    **Standaard**: een herstel wachtwoord van 48 cijfers toestaan  

    Kies of gebruikers verplicht of optioneel een herstelwachtwoord van 48 cijfers mogen genereren, of dat dit niet is toegestaan.  
    - **Herstel wachtwoord van 48 cijfers toestaan**  
    - **Herstel wachtwoord van 48 cijfers niet toestaan**  
    - **Herstel wachtwoord van 48 cijfers vereisen**  

  - **Herstelsleutel maken door gebruiker**  
    **Standaard**: 256-bits herstel sleutel toestaan  

    Kies of gebruikers verplicht of optioneel een herstelsleutel van 256 bits mogen genereren, of dat dit niet is toegestaan.  
    - **256-bits herstel sleutel toestaan**  
    - **Geen 256-bits herstel sleutel toestaan**  
    - **Herstel sleutel van 256 bits vereisen**  

  - **Herstelopties in de BitLocker-installatiewizard**  
    **Standaard**: niet geconfigureerd  

    - **Blokkeren**: gebruikers zien de opties voor herstel niet en kunnen deze dus niet wijzigen. Wanneer ingesteld op 
    - **Niet geconfigureerd**: gebruikers kunnen de opties voor herstel zien en wijzigen wanneer ze BitLocker inschakelen. 
 
  - **BitLocker-herstel gegevens opslaan in Azure Active Directory**  
    **Standaard**: niet geconfigureerd  

    - **Inschakelen**: de BitLocker-herstelgegevens opslaan in Azure Active Directory (AAD).  
    - **Niet geconfigureerd** : BitLocker-herstel gegevens worden niet opgeslagen in Aad.  

  - **BitLocker-herstel gegevens opgeslagen in Azure Active Directory**  
    **Standaard**: back-up maken van herstelwachtwoorden en sleutelpakketten  

    Hiermee bepaalt u welke delen van de BitLocker-herstelgegevens worden opgeslagen in Azure AD. U kunt kiezen uit:  
    - **Back-up maken van herstelwachtwoorden en sleutelpakketten**  
    - **Alleen een back-up maken van herstelwachtwoorden**  

  - **Rotatie van op client gebaseerd herstel wachtwoord**  
    **Standaard**: sleutel rotatie ingeschakeld voor apparaten die lid zijn van Azure AD  
    BitLocker CSP: [ConfigureRecoveryPasswordRotation](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp)  
    
    Deze instelling initieert een door client aangedreven herstel wachtwoord rotatie na een herstel van een besturings systeem (hetzij met behulp van BOOTMGR of WinRE).  

    - Niet geconfigureerd  
    - Sleutel rotatie uitgeschakeld  
    - Sleutel rotatie ingeschakeld voor Azure AD-lid/ICES  
    - Sleutel rotatie ingeschakeld voor Azure AD en hybride apparaten  

  - **Herstel gegevens opslaan in Azure Active Directory voordat u BitLocker inschakelt**  
    **Standaard**: niet geconfigureerd  
 
     Voor komen dat gebruikers BitLocker inschakelen, tenzij de computer een back-up van de BitLocker-herstel gegevens heeft gemaakt Azure Active Directory.  

    - **Vereisen**: voorkomen dat gebruikers BitLocker inschakelen, tenzij de BitLocker-herstelgegevens zijn opgeslagen in Azure AD.  
    - **Niet geconfigureerd**: gebruikers kunnen BitLocker inschakelen, zelfs als herstelgegevens niet zijn opgeslagen in Azure AD.  

- **Preboot-herstelbericht en -URL**  
  **Standaard**: niet geconfigureerd  
  BitLocker CSP: [SystemDrivesRecoveryMessage](https://go.microsoft.com/fwlink/?linkid=872530)  

  - **Enable** : Configureer het bericht en de URL die worden weer gegeven op het scherm Pre-boot sleutel herstel.  
  - **Niet geconfigureerd**: deze functie uitschakelen.  
  
  Als de optie is ingesteld op *Inschakelen*, kunt u de volgende instelling configureren:  
  - **Preboot-herstelbericht**  
    **Standaard**: standaardherstelbericht en URL gebruiken   
 
    Configureer hoe het preboot-herstelbericht wordt weergegeven aan gebruikers. U kunt kiezen uit:  
    - **Standaardherstelbericht en URL gebruiken**  
    - **Leeg herstelbericht en -URL gebruiken**  
    - **Aangepaste herstelbericht gebruiken**  
    - **Aangepaste herstel-URL gebruiken**  

### <a name="bitlocker-fixed-data-drive-settings"></a>BitLocker-instellingen voor vaste-gegevensstations  

Deze instellingen zijn specifiek van toepassing op vaste-gegevens stations.  

- **Schrijftoegang naar vaste-gegevensstations niet door BitLocker beveiligd**  
  **Standaard**: niet geconfigureerd  
  BitLocker CSP: [FixedDrivesRequireEncryption](https://go.microsoft.com/fwlink/?linkid=872534)  

  - **Blokkeren**: alleen-lezentoegang geven aan gegevensstations die niet met BitLocker zijn beveiligd.  
  - **Niet geconfigureerd** : standaard lees-en schrijf toegang tot gegevens stations die niet zijn versleuteld.  

- **Vast-stationherstel**  
  **Standaard**: niet geconfigureerd  
  BitLocker CSP: [FixedDrivesRecoveryOptions](https://go.microsoft.com/fwlink/?linkid=872538)  

  - **Inschakelen**: bepalen hoe met BitLocker beveiligde vaste schijven worden hersteld als de vereiste opstartgegevens niet beschikbaar zijn.  
  - **Niet geconfigureerd**: deze functie uitschakelen.  

  Als de optie is ingesteld op *Inschakelen*, kunt u de volgende instellingen configureren:  

  - **Agent voor gegevensherstel**  
    **Standaard**: niet geconfigureerd  
 
    - **Blokkeren**: voorkomen dat de agent voor gegevensherstel wordt gebruikt met door BitLocker beveiligde vaste schijven met beleidseditor. 
    - **Niet geconfigureerd**: het gebruik van agents voor gegevensherstel met BitLocker beveiligde vaste schijven inschakelen.  

  - **Herstelwachtwoord maken door gebruiker**  
    **Standaard**: een herstel wachtwoord van 48 cijfers toestaan  

    Kies of gebruikers verplicht of optioneel een herstelwachtwoord van 48 cijfers mogen genereren, of dat dit niet is toegestaan.  
    - **Herstel wachtwoord van 48 cijfers toestaan**  
    - **Herstel wachtwoord van 48 cijfers niet toestaan**  
    - **Herstel wachtwoord van 48 cijfers vereisen**  

  - **Herstelsleutel maken door gebruiker**  
    **Standaard**: 256-bits herstel sleutel toestaan

    Kies of gebruikers verplicht of optioneel een herstelsleutel van 256 bits mogen genereren, of dat dit niet is toegestaan.
    - **256-bits herstel sleutel toestaan**  
    - **Geen 256-bits herstel sleutel toestaan**  
    - **Herstel sleutel van 256 bits vereisen**  

  - **Herstelopties in de BitLocker-installatiewizard**  
    **Standaard**: niet geconfigureerd  

    - **Blokkeren**: gebruikers zien de opties voor herstel niet en kunnen deze dus niet wijzigen. Wanneer ingesteld op 
    - **Niet geconfigureerd**: gebruikers kunnen de opties voor herstel zien en wijzigen wanneer ze BitLocker inschakelen.
 
  - **BitLocker-herstel gegevens opslaan in Azure Active Directory**  
    **Standaard**: niet geconfigureerd  

    - **Inschakelen**: de BitLocker-herstelgegevens opslaan in Azure Active Directory (AAD).  
    - **Niet geconfigureerd** : BitLocker-herstel gegevens worden niet opgeslagen in Aad.

  - **BitLocker-herstel gegevens opgeslagen in Azure Active Directory**  
    **Standaard**: back-up maken van herstelwachtwoorden en sleutelpakketten  

    Hiermee bepaalt u welke delen van de BitLocker-herstelgegevens worden opgeslagen in Azure AD. U kunt kiezen uit:  
    - **Back-up maken van herstelwachtwoorden en sleutelpakketten**  
    - **Alleen een back-up maken van herstelwachtwoorden**  

  - **Rotatie van op client gebaseerd herstel wachtwoord**  
    **Standaard**: sleutel rotatie ingeschakeld voor apparaten die lid zijn van Azure AD  
    BitLocker CSP: [ConfigureRecoveryPasswordRotation](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp)  
    
    Deze instelling initieert een door client aangedreven herstel wachtwoord rotatie na een herstel van een besturings systeem (hetzij met behulp van BOOTMGR of WinRE).  

    - Niet geconfigureerd  
    - Sleutel rotatie uitgeschakeld  
    - Sleutel rotatie ingeschakeld voor Azure AD-lid/ICES  
    - Sleutel rotatie ingeschakeld voor Azure AD en hybride apparaten  

  - **Herstel gegevens opslaan in Azure Active Directory voordat u BitLocker inschakelt**  
    **Standaard**: niet geconfigureerd  
 
    Voor komen dat gebruikers BitLocker inschakelen, tenzij de computer een back-up van de BitLocker-herstel gegevens heeft gemaakt Azure Active Directory.  

    - **Vereisen**: voorkomen dat gebruikers BitLocker inschakelen, tenzij de BitLocker-herstelgegevens zijn opgeslagen in Azure AD.  
    - **Niet geconfigureerd**: gebruikers kunnen BitLocker inschakelen, zelfs als herstelgegevens niet zijn opgeslagen in Azure AD.  

### <a name="bitlocker-removable-data-drive-settings"></a>BitLocker-instellingen voor verwisselbare gegevensstations  

Deze instellingen zijn specifiek van toepassing op Verwissel bare gegevens stations.  

- **Schrijftoegang voor een verwisselbaar gegevensstation dat niet door BitLocker is beveiligd**  
  **Standaard**: niet geconfigureerd  
  BitLocker CSP: [RemovableDrivesRequireEncryption](https://go.microsoft.com/fwlink/?linkid=872540)  

  - **Blokkeren**: alleen-lezentoegang geven aan gegevensstations die niet met BitLocker zijn beveiligd.  
  - **Niet geconfigureerd** : standaard lees-en schrijf toegang tot gegevens stations die niet zijn versleuteld.  

  Als de optie is ingesteld op *Inschakelen*, kunt u de volgende instelling configureren:  

  - **Schrijftoegang voor apparaten die zijn geconfigureerd in een andere organisatie**  
    **Standaard**: niet geconfigureerd  

    - **Blokkeren**: schrijftoegang blokkeren voor apparaten die zijn geconfigureerd in een andere organisatie.  
    - **Niet geconfigureerd** -schrijf toegang weigeren.  
 
## <a name="microsoft-defender-exploit-guard"></a>Microsoft Defender exploit Guard  

Gebruik [exploit Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/exploit-protection) om de kwets baarheid te beheren en te verminderen van de apps die door uw werk nemers worden gebruikt.  

### <a name="attack-surface-reduction"></a>Kwetsbaarheid voor aanvallen verminderen  

Regels voor het verminderen van kwets baarheid voor aanvallen helpen te voor komen dat malware wordt gebruikt om computers met schadelijke code te infecteren.  

#### <a name="attack-surface-reduction-rules"></a>Regels voor het verminderen van kwetsbaarheid voor aanvallen  

- **Referentiediefstal in het Windows-subsysteem voor de lokale beveiligingsautoriteit markeren**  
  **Standaard**: niet geconfigureerd  
  Regel: [Blokkeer referentiediefstal in het Windows-subsysteem voor de lokale beveiligingsautoriteit (lsass.exe)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction#block-credential-stealing-from-the-windows-local-security-authority-subsystem-lsassexe)

  Help acties en apps te voorkomen die meestal worden gebruikt door malware om computers te infecteren.  

  - **Niet geconfigureerd**  
  - **Inschakelen**: referentiediefstal in het Windows-subsysteem voor de lokale beveiligingsautoriteit (lsass.exe) markeren.  
  - **Alleen controle**  

- **Het maken van processen vanuit Adobe Reader (bèta)**  
  **Standaard**: niet geconfigureerd  
  Regel: voor [komen dat Adobe Reader een onderliggend proces maakt](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction#block-adobe-reader-from-creating-child-processes)  

  - **Niet geconfigureerd**  
  - **Schakel** onderliggende processen die zijn gemaakt vanuit Adobe Reader in.  
  - **Alleen controle**  

#### <a name="rules-to-prevent-office-macro-threats"></a>Regels voor het voorkomen van bedreigingen voor Office-macro's  

Blokkeer de volgende acties voor Office-apps:  

- **Office-apps injecteren in andere processen (geen uitzonderingen)**  
  **Standaard**: niet geconfigureerd  
  Regel: [Voorkomen dat Office-toepassingen code in andere processen injecteren](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction#block-office-applications-from-injecting-code-into-other-processes)  

  - **Niet geconfigureerd**  
  - **Blok** keren: de Office-apps mogen niet worden ingevoegd in andere processen.  
  - **Alleen controle**  

- **Uitvoerbare inhoud maken met Office-apps/-macro's**  
  **Standaard**: niet geconfigureerd  
  Regel: [Voorkomen dat Office-toepassingen uitvoerbare inhoud maken](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction#block-office-applications-from-creating-executable-content)  

  - **Niet geconfigureerd**  
  - **Blok** keren: blok keer Office-apps en macro's voor het maken van uitvoer bare inhoud.  
  - **Alleen controle**  

- **Onderliggende processen starten met Office-apps**  
  **Standaard**: niet geconfigureerd  
  Regel: [Voorkomen dat Office-toepassingen onderliggende processen maken](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction#block-all-office-applications-from-creating-child-processes)  

  - **Niet geconfigureerd**  
  - **Blok** keren: blok keer dat Office-apps onderliggende processen kunnen starten.  
  - **Alleen controle**  
  
- **Win32-importbewerkingen uit macrocode van Office**  
  **Standaard**: niet geconfigureerd  
  Regel: [Win32 API-aanroepen blokkeren vanuit Office-macro's](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction#block-win32-api-calls-from-office-macros)  

  - **Niet geconfigureerd**  
  - **Blok** keren: Win32-import bewerkingen uit macro code in Office.  
  - **Alleen controle**  
  
- **Het maken van processen van Office-communicatie producten**  
  **Standaard**: niet geconfigureerd  
  Regel: voor komen dat de [Office-communicatie toepassing onderliggende processen maakt](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction#block-office-communication-application-from-creating-child-processes)  

  - **Niet geconfigureerd**  
  - **Inschakelen** : het maken van een onderliggend proces vanuit Office Communications-apps blok keren.  
  - **Alleen controle**  

#### <a name="rules-to-prevent-script-threats"></a>Regels om scriptbedreigingen te voorkomen  

Blokkeer de volgende acties om scriptbedreigingen te voorkomen:  

- **Verborgen js-/vbs-/ps-/macrocode**  
  **Standaard**: niet geconfigureerd  
  Regel: [De uitvoering voorkomen van mogelijk betekenisloze scripts](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction#block-execution-of-potentially-obfuscated-scripts)    

  - **Niet geconfigureerd**  
  - **Blok** keren: wille keurige Codeer-js/vbs/PS/-macro codes blok keren.  
  - **Alleen controle**  

- **Van internet gedownloade payloads uitvoeren met js-/vbs-bestanden (geen uitzonderingen)**  
  **Standaard**: niet geconfigureerd  
  Regel: [Voorkomen dat JavaScript of VBScript gedownloade uitvoerbare inhoud start](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction#block-javascript-or-vbscript-from-launching-downloaded-executable-content)  

  - **Niet geconfigureerd**  
  - **Block** -Block js/vbs van het uitvoeren van Payload dat is gedownload van Internet.  
  - **Alleen controle**  

- **Het maken van processen met PSExec- en WMI-opdrachten**  
  **Standaard**: niet geconfigureerd  
  Regel: [Blokkeer het maken van processen die afkomstig zijn van PSExec- en WMI-opdrachten](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction#block-process-creations-originating-from-psexec-and-wmi-commands)  

  - **Niet geconfigureerd**  
  - **Blokkeren**: het maken van processen voorkomen die afkomstig zijn van PSExec- en WMI-opdrachten.  
  
  - **Alleen controle**  

- **Niet-vertrouwde en niet-ondertekende processen die worden uitgevoerd via USB**  
  **Standaard**: niet geconfigureerd  
  Regel: [Blokkeer niet-vertrouwde en niet-ondertekende processen die worden uitgevoerd vanaf een USB](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction#block-untrusted-and-unsigned-processes-that-run-from-usb)    

  - **Niet geconfigureerd**  
  - **Blokkeren**: voorkomen dat niet-vertrouwde en niet-ondertekende processen worden uitgevoerd vanaf een USB.  
  - **Alleen controle**  
  
- **Uitvoerbare bestanden die niet voldoen aan een bepaalde gangbaarheid, ouderdom of aan criteria voor vertrouwde lijsten blokkeren**  
  **Standaard**: niet geconfigureerd  
  Regel: [Voorkom dat uitvoerbare bestanden worden uitgevoerd tenzij deze voldoen aan een bepaalde gangbaarheid, ouderdom of criteria voor vertrouwde lijsten](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction#block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion)    

  - **Niet geconfigureerd**  
  - **Blokkeren**: voorkomen dat uitvoerbare bestanden worden uitgevoerd tenzij deze voldoen aan een bepaalde gangbaarheid, ouderdom of criteria voor vertrouwde lijsten.  
  - **Alleen controle**  

#### <a name="rules-to-prevent-email-threats"></a>Regels om te e-mailbedreigingen te voorkomen  

Blokkeer de volgende acties om e-mailbedreigingen te voorkomen:  

- **Uitvoering van uitvoerbare inhoud (exe-, dll-, ps-, js-, vbs-bestanden enzovoort) die is verwijderd uit e-mail (webmail/e-mailclient) (geen uitzonderingen)**  
  **Standaard**: niet geconfigureerd  
  Regel: [Uitvoerbare inhoud blokkeren van e-mailclient en webmail](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction#block-executable-content-from-email-client-and-webmail)  

  - **Niet geconfigureerd**  
  - **Blokkeren**: uitvoering voorkomen van uitvoerbare inhoud (exe-, dll-, ps-, js-, vbs-bestanden, enzovoort) die is verwijderd uit e-mail (webmail/e-mailclient).  
  - **Alleen controle**  

#### <a name="rules-to-protect-against-ransomware"></a>Regels voor bescherming tegen ransomware  

- **Geavanceerde ransomwarebeveiliging**  
  Standaard: niet geconfigureerd  
  Regel: [geavanceerde beveiliging gebruiken tegen Ransomware](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction#use-advanced-protection-against-ransomware)  

  - **Niet geconfigureerd**  
  - **Inschakelen**: agressieve ransomwarebeveiliging gebruiken.  
  - **Alleen controle**  

#### <a name="attack-surface-reduction-exceptions"></a>Regels voor het verminderen van kwetsbaarheid voor aanvallen

- **Bestanden en mappen die worden uitgesloten voor regels voor kwetsbaarheid voor aanvallen verminderen**  
  Defender CSP: [AttackSurfaceReductionOnlyExclusions](https://go.microsoft.com/fwlink/?linkid=872981)  

  - **Importeer** een CSV-bestand dat bestanden en mappen bevat die moeten worden uitgesloten van regels voor het verminderen van kwets baarheid voor aanvallen.  
  - Lokale bestanden of mappen hand matig **toevoegen** .  

> [!IMPORTANT]  
> Als u wilt toestaan dat LOB Win32-apps goed worden geïnstalleerd en uitgevoerd, moeten via de antimalware-instellingen worden ingesteld dat de volgende mappen niet worden gescand:  
> **Voor X64-clientcomputers**:  
> *C:\Program Files (x86)\Microsoft Intune Management Extension\Content*  
> *C:\windows\IMECache*  
>  
> **Voor X86-clientcomputers**:  
> *C:\Program Files\Microsoft Intune Management Extension\Content*  
> *C:\windows\IMECache*  

### <a name="controlled-folder-access"></a>Gecontroleerde mappentoegang  

Hiermee kunt u [waardevolle gegevens beter beveiligen](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/controlled-folders) tegen schadelijke apps en bedreigingen zoals ransomware.  

- **Mapbeveiliging**  
  **Standaard**: niet geconfigureerd  
  Defender CSP: [EnableControlledFolderAccess](https://go.microsoft.com/fwlink/?linkid=872614)  

  Beveilig bestanden en mappen tegen niet-geautoriseerde wijzigingen door niet-goedgekeurde apps.  

  - **Niet geconfigureerd**  
  - **Inschakelen**  
  - **Alleen controle**  
  - **Schijfwijziging blokkeren**  
  - **Schijfwijziging controleren**  

  Wanneer u een andere configuratie selecteert dan *niet geconfigureerd*, kunt u het volgende configureren:  
  - **Lijst met apps die toegang hebben tot beveiligde mappen**  
    Defender CSP: [ControlledFolderAccessAllowedApplications](https://go.microsoft.com/fwlink/?linkid=872616)  

    - **Importeer** een CSV-bestand dat een lijst met apps bevat.  
    - Apps hand matig aan deze lijst **toevoegen** .  

  - **Lijst met aanvullende mappen die moeten worden beveiligd**  
    Defender CSP: [ControlledFolderAccessProtectedFolders](https://go.microsoft.com/fwlink/?linkid=872617)  

    - Een CSV-bestand met een mappen lijst **importeren** .  
    - **Voeg** mappen hand matig toe aan deze lijst.  

### <a name="network-filtering"></a>Netwerk filteren  

Blok keer uitgaande verbindingen van elke app naar IP-adressen of domeinen met een lage reputatie. Netwerk filtering wordt ondersteund in de modus controleren en blok keren.  

- **Netwerkbeveiliging**  
  **Standaard**: niet geconfigureerd  
  Defender CSP: [EnableNetworkProtection](https://go.microsoft.com/fwlink/?linkid=872618)  

  Het doel van deze instelling is om eind gebruikers te beschermen tegen apps met toegang tot phishing-prak tijken, sites voor het hosten van aanvallen en schadelijke inhoud op internet. Ook wordt voor komen dat browsers van derden verbinding maken met gevaarlijke sites.  

  - **Niet geconfigureerd**: deze functie uitschakelen. Gebruikers en apps worden niet geblokkeerd voor het verbinden met gevaarlijke domeinen. Beheerders kunnen deze activiteit niet bekijken in het Microsoft Defender-beveiligingscentrum.  
  - **Schakel** netwerk beveiliging in en blok keer gebruikers en apps om verbinding te maken met gevaarlijke domeinen. Beheerders kunnen deze activiteit bekijken in het Microsoft Defender-beveiligingscentrum.  
  - **Alleen controle**:-gebruikers en apps worden niet geblokkeerd om verbinding te maken met gevaarlijke domeinen. Beheerders kunnen deze activiteit bekijken in het Microsoft Defender-beveiligingscentrum.  

### <a name="exploit-protection"></a>Exploit Protection  

- **XML uploaden**  
  **Standaard**: *niet geconfigureerd*  

  Als u exploit Protection wilt gebruiken om [apparaten te beschermen tegen aanvallen](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection), maakt u een XML-bestand met daarin de gewenste systeem-en toepassings beperkings instellingen. Er zijn twee methoden om het XML-bestand te maken:  

  - *PowerShell*: gebruik een of meer van de PowerShell-cmdlets *Get-ProcessMitigation*, *Set-ProcessMitigation* en *ConvertTo-ProcessMitigationPolicy*. Met de cdmlets worden beperkingsinstellingen geconfigureerd en wordt hiervan een XML-weergave geëxporteerd.  

  - *Gebruikersinterface van het Microsoft Defender-beveiligingscentrum*: klik in het Windows Defender-beveiligingscentrum op het besturingselement voor de app en browser en scrol naar beneden op het scherm om Beveiliging met Exploit Guard te zoeken. Gebruik eerst de tabbladen Systeeminstellingen en Programma-instellingen om de beperkingsinstellingen te configureren. Zoek vervolgens de koppeling Instellingen exporteren onderaan het scherm om een XML-weergave hiervan te exporteren.  

- **Gebruikers bewerking van de exploit Protection-interface**  
  **Standaard**: niet geconfigureerd  
  ExploitGuard CSP: [ExploitProtectionSettings](https://go.microsoft.com/fwlink/?linkid=872887)  


  - **Blok** -upload een XML-bestand waarmee u geheugen, controle stroom en beleids beperkingen kunt configureren. De instellingen in het XML-bestand kunnen worden gebruikt om een toepassing te blokkeren tegen aanvallen.  
  - **Niet geconfigureerd** : er wordt geen aangepaste configuratie gebruikt.  

## <a name="microsoft-defender-application-control"></a>Microsoft Defender-toepassingsbeheer  

Kies de extra apps die moeten worden gecontroleerd door of die kunnen worden vertrouwd om te worden uitgevoerd door Microsoft Defender Application Control. Windows-onderdelen en alle apps uit Windows Store worden automatisch vertrouwd.  


- **Beleid voor toepassings beheer code-integriteit**  
  **Standaard**: niet geconfigureerd  
   CSP: [APPLOCKER CSP](https://go.microsoft.com/fwlink/?linkid=874543)  

  - **Forceren** : Kies het beleid voor toepassings beheer code-integriteit voor de apparaten van uw gebruikers.  
  
    Als toepassingsbeheer is ingeschakeld op een apparaat, kunt u de functie alleen uitschakelen door de modus te wijzigen van *Afdwingen* in *Alleen controle*. Als u de modus wijzigt van *Afdwingen* in *Niet geconfigureerd*, wordt toepassingsbeheer op toegewezen apparaten nog steeds afgedwongen.  

  - **Niet geconfigureerd** : toepassings beheer is niet toegevoegd aan apparaten. Instellingen die eerder zijn toegevoegd, blijven echter worden afgedwongen op toegewezen apparaten. 
 
  - **Alleen controle** : toepassingen worden niet geblokkeerd. Alle gebeurtenissen worden geregistreerd in de logboeken van de lokale client.  

## <a name="microsoft-defender-credential-guard"></a>Microsoft Defender Credential Guard  

Microsoft Defender Credential Guard beschermt tegen aanvallen waarbij referenties worden gestolen. Het isoleert geheimen zodat alleen bevoegde systeemsoftware er toegang toe heeft.  

- **Credential Guard**  
  **Standaard**: Uitschakelen  
  [DeviceGuard CSP](https://go.microsoft.com/fwlink/?linkid=872424)  

  - **Uitschakelen**: Credential Guard op afstand uitschakelen als de functie eerder is ingeschakeld met de optie **Ingeschakeld zonder UEFI-vergrendeling**.  

  - **Inschakelen met UEFI-vergrendeling**: Credential Guard kan niet op afstand worden uitgeschakeld met een registersleutel of via Groepsbeleid.  

    > [!NOTE]
    > Als u deze instelling gebruikt en Credential Guard later wilt uitschakelen, moet u het Groepsbeleid instellen op **Uitgeschakeld**. Ook moet u de UEFI-configuratiegegevens fysiek van elke computer wissen. Zolang de UEFI-configuratie behouden blijft, is Credential Guard ingeschakeld.  

  - **Inschakelen zonder UEFI-vergrendeling**: instellen dat Credential Guard op afstand kan worden uitgeschakeld via Groepsbeleid. Op de apparaten die gebruikmaken van deze instelling moet Windows 10 versie 1511 en hoger worden uitgevoerd.  

  Wanneer u Credential Guard *inschakelt*, worden de volgende vereiste functies ook ingeschakeld:  
  
  - **Beveiliging op basis van virtualisatie** (VBS)  
    Wordt ingeschakeld wanneer de machine de volgende keer opnieuw wordt opgestart. Beveiliging op basis van virtualisatie maakt gebruik van de Windows-Hypervisor om ondersteuning te bieden voor beveiligingsservices.  
  - **Beveiligd opstarten met directe geheugentoegang**  
    Hiermee schakelt u beveiliging op basis van virtualisatie met beveiligd opstarten en directe geheugentoegang (DMA) in. Voor DMA-beveiliging is hardwareondersteuning vereist en deze wordt alleen ingeschakeld op apparaten die juist zijn geconfigureerd.  

## <a name="microsoft-defender-security-center"></a>Microsoft Defender-beveiligingscentrum  

Het Microsoft Defender-beveiligingscentrum werkt als een afzonderlijke app of een afzonderlijk proces van de afzonderlijke functies. Deze geeft meldingen weer via het onderhoudscentrum. Het fungeert als een collector of één afzonderlijke plaats om de status te zien en een configuratie van de functies uit te voeren. Meer informatie vindt u in de [Microsoft Defender](https://docs.microsoft.com/windows/threat-protection/windows-defender-security-center/windows-defender-security-center) docs.  

### <a name="microsoft-defender-security-center-app-and-notifications"></a>Microsoft Defender-beveiligingscentrum-app en meldingen  

Blokkeer de toegang van eindgebruikers tot verschillende gebieden van de Microsoft Defender-beveiligingscentrum-app. Als u een sectie verbergt, worden ook gekoppelde meldingen geblokkeerd.  

- **Virus- en bedreigingsbeveiliging**  
  **Standaard**: niet geconfigureerd  
  WindowsDefenderSecurityCenter CSP: [DisableVirusUI](https://go.microsoft.com/fwlink/?linkid=873662)  

  Configureren of eind gebruikers het gebied virus-en bedreigings beveiliging in Microsoft Defender Security Center kunnen bekijken. Door deze sectie te verbergen, worden ook alle meldingen met betrekking tot virus-en bedreigings beveiliging geblokkeerd.  

  - **Niet geconfigureerd**  
  - **Verbergen**  

- **Bescherming tegen Ransomware**  
  **Standaard**: niet geconfigureerd  
  WindowsDefenderSecurityCenter CSP: [HideRansomwareDataRecovery](https://go.microsoft.com/fwlink/?linkid=873664)  

  Configureren of eind gebruikers het gebied bescherming tegen Ransomware kunnen weer geven in Microsoft Defender Security Center. Door deze sectie te verbergen, worden ook alle meldingen die betrekking hebben op Ransomware-beveiliging geblokkeerd.  

  - **Niet geconfigureerd**  
  - **Verbergen**  

- **Account beveiliging**  
  **Standaard**: niet geconfigureerd  
  WindowsDefenderSecurityCenter CSP: [DisableAccountProtectionUI](https://go.microsoft.com/fwlink/?linkid=873666)  

  Configureren of eind gebruikers het gedeelte account beveiliging in de Microsoft Defender Security Center kunnen bekijken. Als u deze sectie verbergt, worden ook alle meldingen met betrekking tot account beveiliging geblokkeerd.  

  - **Niet geconfigureerd**  
  - **Verbergen**  

- **Firewall- en netwerkbeveiliging**  
  **Standaard**: niet geconfigureerd  
  WindowsDefenderSecurityCenter CSP: [DisableNetworkUI](https://go.microsoft.com/fwlink/?linkid=873668)  

  Configureren of eind gebruikers het gebied firewall en netwerk beveiliging kunnen weer geven in het Microsoft Defender-beveiligings centrum. Door deze sectie te verbergen, worden ook alle meldingen met betrekking tot Firewall-en netwerk beveiliging geblokkeerd.  

  - **Niet geconfigureerd**  
  - **Verbergen**  

- **App- en browserbeheer**  
  **Standaard**: niet geconfigureerd  
  WindowsDefenderSecurityCenter CSP: [DisableAppBrowserUI](https://go.microsoft.com/fwlink/?linkid=873669)  

  Configureren of eind gebruikers het besturings gebied app en browser kunnen weer geven in het Microsoft Defender-beveiligings centrum. Door deze sectie te verbergen, worden ook alle meldingen die betrekking hebben op app-en browser beheer geblokkeerd.  

  - **Niet geconfigureerd**  
  - **Verbergen**  

- **Hardware-beveiliging**  
  **Standaard**: niet geconfigureerd  
  WindowsDefenderSecurityCenter CSP: [DisableDeviceSecurityUI](https://go.microsoft.com/fwlink/?linkid=873670)  

  Configureren of eind gebruikers het gebied voor hardware-beveiliging in de Microsoft Defender Security Center kunnen bekijken. Door deze sectie te verbergen, worden ook alle meldingen die betrekking hebben op de beveiliging van hardware geblokkeerd.  

  - **Niet geconfigureerd**  
  - **Verbergen**  

- **Prestaties en status van apparaat**  
  **Standaard**: niet geconfigureerd  
  WindowsDefenderSecurityCenter CSP: [DisableHealthUI](https://go.microsoft.com/fwlink/?linkid=873671)  

  Configureren of eind gebruikers het gebied prestaties en status van het apparaat kunnen bekijken in het Microsoft Defender-beveiligings centrum. Als u deze sectie verbergt, worden ook alle meldingen die betrekking hebben op de prestaties en status van het apparaat geblokkeerd.  
  
  - **Niet geconfigureerd**  
  - **Verbergen**  

- **Gezinsopties**  
  **Standaard**: niet geconfigureerd  
  WindowsDefenderSecurityCenter CSP: [DisableFamilyUI](https://go.microsoft.com/fwlink/?linkid=873673)  

  Configureren of eind gebruikers het gebied met gezins opties kunnen weer geven in het Microsoft Defender-beveiligings centrum. Als u deze sectie verbergt, worden ook alle meldingen met betrekking tot gezins opties geblokkeerd.  
  
  - **Niet geconfigureerd**  
  - **Verbergen**  

- **Meldingen van de weergegeven gebieden van de app**  
  **Standaard**: niet geconfigureerd  
  WindowsDefenderSecurityCenter CSP: [DisableNotifications](https://go.microsoft.com/fwlink/?linkid=873675)  

  Kies welke meldingen worden weergegeven voor eindgebruikers. Niet-kritieke meldingen zijn bijvoorbeeld samenvattingen van Microsoft Defender Antivirus-activiteiten en meldingen wanneer scans zijn voltooid. Alle andere meldingen worden beschouwd als kritiek.  

  - **Niet geconfigureerd**  
  - **Niet-kritieke meldingen blok keren**  
  - **Alle meldingen blokkeren**  

- **Pictogram Windows-Security Center in het systeemvak**  
  **Standaard**: niet geconfigureerd  

  De weer gave van het besturings element voor het systeemvak configureren. De gebruiker moet zich afmelden en vervolgens aanmelden of de computer opnieuw opstarten om deze instelling van kracht te laten worden.  
  
  - **Niet geconfigureerd**  
  - **Verbergen**  

- **TPM-knop wissen**  
  **Standaard**: niet geconfigureerd  

  Configureer de weer gave van de knop TPM wissen.  
  
  - **Niet geconfigureerd**  
  - **Uitschakelen**  

- **Waarschuwing firmware-update TPM**  
  **Standaard**: niet geconfigureerd  
  
  Configureer de weer gave van firmware voor update-TPM wanneer een kwets bare firmware wordt gedetecteerd.  

  - **Niet geconfigureerd**  
  - **Verbergen**  

- **Bescherming tegen knoeien**  
  **Standaard**: niet geconfigureerd

  Ingrijpende beveiliging in-of uitschakelen op apparaten. Als u onrecht matige beveiliging wilt gebruiken, moet u [Microsoft Defender Advanced Threat Protection integreren met intune](advanced-threat-protection.md)en beschikken over [Enterprise Mobility + Security E5-licenties](../fundamentals/licenses.md).  
  - **Niet geconfigureerd** : er is geen wijziging aangebracht in Apparaatinstellingen.
  - Beveiliging op ingrijpen **is ingeschakeld en** beperkingen worden afgedwongen op apparaten.
  - **Uitgeschakeld** : beveiliging tegen knoei is uitgeschakeld en de beperkingen worden niet afgedwongen.

### <a name="it-contact-information"></a>IT-contactgegevens  

Geef de IT-contactgegevens op die in de Microsoft Defender-beveiligingscentrum-app en in de app-meldingen moeten worden weergegeven.  

U kunt kiezen tussen **In app en in meldingen weergeven**, **Alleen in app weergeven**, **Alleen in meldingen weergeven** en **Niet weergeven**. Voer de **IT-organisatienaam** en ten minste één van de volgende contactopties in:  


- **IT-contactgegevens**  
  **Standaard**: niet weer geven  
  WindowsDefenderSecurityCenter CSP: [EnableCustomizedToasts](https://go.microsoft.com/fwlink/?linkid=873676)  
  
  Hiermee configureert u hoe IT-contact gegevens worden weer gegeven voor eind gebruikers.  
  
  - **Weer geven in app en in meldingen**  
  - **Alleen weer geven in de app**  
  - **Alleen weer geven in meldingen**  
  - **Niet weer geven**  

  Wanneer is geconfigureerd om weer te geven, kunt u de volgende instellingen configureren:  

  - **Naam van IT-organisatie**  
    **Standaard**: *niet geconfigureerd*  
    WindowsDefenderSecurityCenter CSP: [bedrijf](https://go.microsoft.com/fwlink/?linkid=873677)  

  - **Telefoonnummer of Skype-ID van de IT-afdeling**  
    **Standaard**: *niet geconfigureerd*  
    WindowsDefenderSecurityCenter CSP: [telefoon nummer](https://go.microsoft.com/fwlink/?linkid=873678) 

  - **E-mailadres van de IT-afdeling**  
    **Standaard**: *niet geconfigureerd*  
    WindowsDefenderSecurityCenter CSP: [e-mail](https://go.microsoft.com/fwlink/?linkid=873679)  

  - **URL van de IT-ondersteuningswebsite**  
    **Standaard**: *niet geconfigureerd*  
    WindowsDefenderSecurityCenter CSP: [URL](https://go.microsoft.com/fwlink/?linkid=873680)  
 
## <a name="local-device-security-options"></a>Beveiligingsopties van lokale apparaten  

Gebruik deze opties voor het configureren van de lokale beveiligingsinstellingen op Windows 10-apparaten.  

### <a name="accounts"></a>Accounts  

- **Nieuwe Microsoft-accounts toevoegen**  
  **Standaard**: niet geconfigureerd  
  LocalPoliciesSecurityOptions CSP: [Accounts_BlockMicrosoftAccounts](https://go.microsoft.com/fwlink/?linkid=867916)  


  - **Blokkeren**: voorkomen dat gebruikers nieuwe Microsoft-accounts aan het apparaat toevoegen.  
  - **Niet geconfigureerd** : gebruikers kunnen Microsoft-accounts op het apparaat gebruiken.  

- **Extern aanmelden zonder wachtwoord**  
  **Standaard**: niet geconfigureerd  
  LocalPoliciesSecurityOptions CSP: [Accounts_LimitLocalAccountUseOfBlankPasswordsToConsoleLogonOnly](https://go.microsoft.com/fwlink/?linkid=867890)  


   - **Blokkeren**: lokale accounts met lege wachtwoorden alleen toestaan zich aan te melden met behulp van het toetsenbord van het apparaat.  
   - **Niet geconfigureerd**: lokale accounts met lege wachtwoorden kunnen zich aanmelden vanaf andere locaties dan het fysieke apparaat.  

#### <a name="admin"></a>Administrator  

- **Lokaal beheerdersaccount**  
  **Standaard**: niet geconfigureerd  
  LocalPoliciesSecurityOptions CSP: [Accounts_LimitLocalAccountUseOfBlankPasswordsToConsoleLogonOnly](https://go.microsoft.com/fwlink/?linkid=867850)  


  - **Blok keren** Voor komen dat een lokaal beheerders account wordt gebruikt.  
  - **Niet geconfigureerd**  

- **Naam van beheerdersaccount wijzigen**  
  **Standaard**: *niet geconfigureerd*  
  LocalPoliciesSecurityOptions CSP: [Accounts_RenameAdministratorAccount](https://go.microsoft.com/fwlink/?linkid=867917)  
 

  Definieer een andere accountnaam die moet worden gekoppeld aan de beveiligings-id (SID) van het beheerdersaccount.  

 #### <a name="guest"></a>Gast  

- **Gastaccount**  
  **Standaard**: niet geconfigureerd  
  LocalPoliciesSecurityOptions CSP: [LocalPoliciesSecurityOptions](https://go.microsoft.com/fwlink/?linkid=867853)  

  - **Blok keren** : het gebruik van een gast account voor komen.  
  - **Niet geconfigureerd**  

- **Naam van het gastaccount wijzigen**  
  **Standaard**: *niet geconfigureerd*  
  LocalPoliciesSecurityOptions CSP: [Accounts_RenameGuestAccount](https://go.microsoft.com/fwlink/?linkid=867918)  
  
  Definieer een andere accountnaam die moet worden gekoppeld aan de beveiligings-id (SID) van het gastaccount.  

### <a name="devices"></a>Apparaten  

- **Apparaat ontkoppelen zonder aanmelding**  
  **Standaard**: niet geconfigureerd  
  LocalPoliciesSecurityOptions CSP: [Devices_AllowUndockWithoutHavingToLogon](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-localpoliciessecurityoptions#localpoliciessecurityoptions-devices-allowundockwithouthavingtologon)  

  
  - **Blokkeren**: gebruikers kunnen op de fysieke knop voor het uitwerpen van een gedokt draagbaar apparaat drukken om het apparaat veilig te ontkoppelen.  
  - **Niet geconfigureerd** : een gebruiker moet zich aanmelden bij het apparaat en de machtiging ontvangen om het apparaat te ontkoppelen.  

- **Stuurprogramma's voor gedeelde printers installeren**  
  **Standaard**: niet geconfigureerd  
  LocalPoliciesSecurityOptions CSP: [Devices_PreventUsersFromInstallingPrinterDriversWhenConnectingToSharedPrinters](https://go.microsoft.com/fwlink/?linkid=867921)  


  - **Ingeschakeld**: elke gebruiker kan een printerstuurprogramma installeren als onderdeel van het maken van verbinding met een gedeelde printer.  
  - **Niet geconfigureerd**: alleen beheerders kunnen een printerstuurprogramma installeren als onderdeel van het maken van een verbinding met een gedeelde printer.  

- **Cd-rom-toegang beperken tot lokale actieve gebruiker**  
  **Standaard**: niet geconfigureerd  
  CSP: [Devices_RestrictCDROMAccessToLocallyLoggedOnUserOnly](https://go.microsoft.com/fwlink/?linkid=867922)  


  - **Ingeschakeld**: alleen de interactief aangemelde gebruiker kan de cd-rom-media gebruiken. Als dit beleid is ingeschakeld en niemand interactief is aangemeld, wordt de cd-rom geopend via het netwerk.  
  - **Niet geconfigureerd** : iedereen heeft toegang tot de cd-rom.  

- **Verwisselbare media formatteren en uitwerpen**  
  **Standaard**: beheerders  
  CSP: [Devices_AllowedToFormatAndEjectRemovableMedia](https://go.microsoft.com/fwlink/?linkid=867920)  
 

  Definieer de personen voor wie het is toegestaan om verwisselbare NTFS-media te formatteren en uit te werpen:  
  - **Niet geconfigureerd**  
  - **Beheerders**  
  - **Beheerders en hoofdgebruikers**  
  - **Beheerders en interactieve gebruikers**  

### <a name="interactive-logon"></a>Interactief aanmelden  

- **Minuten van inactiviteit van vergrendelingsscherm totdat de schermbeveiliging wordt geactiveerd**  
  **Standaard**: *niet geconfigureerd*  
  LocalPoliciesSecurityOptions CSP: [InteractiveLogon_MachineInactivityLimit](https://go.microsoft.com/fwlink/?linkid=867891)  


  Voer het maximale aantal minuten van inactiviteit in op het aanmeldingsscherm van het interactieve bureaublad totdat de schermbeveiliging actief wordt. (**0** - **99999**)  

- **CTRL+ALT+DEL vereisen om aan te melden**  
  **Standaard**: niet geconfigureerd  
  LocalPoliciesSecurityOptions CSP: [InteractiveLogon_DoNotRequireCTRLALTDEL](https://go.microsoft.com/fwlink/?linkid=867951)  


  - **Inschakelen**: gebruikers hoeven niet op CTRL+ALT+DEL te drukken om zich aan te melden.  
  - **Niet geconfigureerd**: vereisen dat gebruikers op CTRL+ALT+DEL drukken om zich aan te melden bij Windows.  

- **Gedrag bij verwijderen van smartcard**  
  **Standaardinstelling**: Werkstation vergrendelen   
  LocalPoliciesSecurityOptions CSP: [InteractiveLogon_SmartCardRemovalBehavior](https://go.microsoft.com/fwlink/?linkid=868437)  
    
  Hiermee bepaalt u wat er gebeurt wanneer de smartcard van een aangemelde gebruiker uit de lezer van de smartcard wordt verwijderd. Uw opties zijn:  

  - **Werkstation vergrendelen**: het werkstation wordt vergrendeld wanneer de smartcard wordt verwijderd. Met deze optie kunnen gebruikers het gebied verlaten, de smartcard meenemen en toch een beveiligde sessie behouden.  
  - **Geen actie**  
  - **Afmelden forceren**: de gebruiker wordt automatisch afgemeld wanneer de smartcard wordt verwijderd.  
  - **Verbinding verbreken bij sessie met Extern bureaublad-services**: als de smartcard wordt verwijderd, wordt de sessie verbroken zonder de gebruiker af te melden. Met deze optie kan de gebruiker de smartcard plaatsen en de sessie later of op een andere met smartcardlezer uitgeruste computer hervatten zonder zich opnieuw te moeten melden. Als de sessie lokaal is, werkt dit beleid op dezelfde manier als Werkstation vergrendelen.  

#### <a name="display"></a>Weergave  

- **Gebruikersinformatie op vergrendelingsscherm**  
  **Standaard**: niet geconfigureerd  
  LocalPoliciesSecurityOptions CSP: [InteractiveLogon_DisplayUserInformationWhenTheSessionIsLocked](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-localpoliciessecurityoptions#localpoliciessecurityoptions-interactivelogon-displayuserinformationwhenthesessionislocked)  

  Configureer welke gebruikersinformatie wordt weergegeven wanneer de sessie is vergrendeld. Als deze optie niet is geconfigureerd, worden de weergavenaam van de gebruiker, het domein en de gebruikersnaam weergegeven.  

  - **Niet geconfigureerd**  
  - **Weergavenaam van gebruiker, domein en gebruikersnaam**  
  - **Alleen weergavenaam gebruiker**  
  - **Gebruikersinformatie niet weergeven**  

- **Laatste aangemelde gebruiker verbergen**  
  **Standaard**: niet geconfigureerd  
  LocalPoliciesSecurityOptions CSP: [InteractiveLogon_DoNotDisplayLastSignedIn](https://go.microsoft.com/fwlink/?linkid=868437)  
  
  
  - **Schakel** de gebruikers naam in-verbergen.  
  - **Niet geconfigureerd** : de laatste gebruikers naam weer geven.  

- **Gebruikers naam verbergen bij aanmelding**
  **standaard**: niet geconfigureerd  
  LocalPoliciesSecurityOptions CSP: [InteractiveLogon_DoNotDisplayUsernameAtSignIn](https://go.microsoft.com/fwlink/?linkid=867959)  

  
  - **Schakel** de gebruikers naam in-verbergen.  
  - **Niet geconfigureerd** : de laatste gebruikers naam weer geven.  

- **Titel aanmeldingsbericht**  
  **Standaard**: *niet geconfigureerd*  
  LocalPoliciesSecurityOptions CSP: [InteractiveLogon_MessageTitleForUsersAttemptingToLogOn](https://go.microsoft.com/fwlink/?linkid=867964)  

  Stel de berichttitel in voor gebruikers die zich aanmelden.  

- **Tekst aanmeldingsbericht**  
  **Standaard**: *niet geconfigureerd*  
  LocalPoliciesSecurityOptions CSP: [InteractiveLogon_MessageTextForUsersAttemptingToLogOn](https://go.microsoft.com/fwlink/?linkid=867962)  

  Stel de berichttekst in voor gebruikers die zich aanmelden.  
  
### <a name="network-access-and-security"></a>Netwerktoegang en -beveiliging

- **Anonieme toegang tot named pipes en shares**  
  **Standaard**: niet geconfigureerd  
  LocalPoliciesSecurityOptions CSP: [NetworkAccess_RestrictAnonymousAccessToNamedPipesAndShares](https://go.microsoft.com/fwlink/?linkid=868432)  

  - **Niet geconfigureerd**: anonieme toegang beperken tot instellingen voor delen en named pipes. Van toepassing op de instellingen die anoniem kunnen worden gebruikt.  
  - **Blok keer** -Schakel dit beleid uit, zodat anonieme toegang beschikbaar wordt.  

- **Anonieme inventarisatie van SAM-accounts**  
  **Standaard**: niet geconfigureerd  
  LocalPoliciesSecurityOptions CSP: [NetworkAccess_DoNotAllowAnonymousEnumerationOfSAMAccounts](https://go.microsoft.com/fwlink/?linkid=868434)  
  
  - **Niet geconfigureerd** : anonieme gebruikers kunnen SAM-accounts opsommen.  
  - **Blokkeren**: anonieme inventarisatie van SAM-accounts voorkomen.  

- **Anonieme inventarisatie van SAM-accounts en -shares**  
  **Standaard**: niet geconfigureerd  
  LocalPoliciesSecurityOptions CSP: [NetworkAccess_DoNotAllowAnonymousEnumerationOfSamAccountsAndShares](https://go.microsoft.com/fwlink/?linkid=868435)  

  - **Niet geconfigureerd**: anonieme gebruikers kunnen de namen van domeinaccounts en netwerkshares inventariseren.  
  - **Blokkeren**: anonieme inventarisatie van SAM-accounts en -shares voorkomen. 

- **Hash-waarde van LAN Manager opslaan bij wachtwoordwijziging**  
  **Standaard**: niet geconfigureerd  
  LocalPoliciesSecurityOptions CSP: [NetworkSecurity_DoNotStoreLANManagerHashValueOnNextPasswordChange](https://go.microsoft.com/fwlink/?linkid=868431)  
   
  Bepaal of de hash-waarde voor wacht woorden de volgende keer dat het wacht woord wordt gewijzigd wordt opgeslagen. 
  - **Niet geconfigureerd** -de hash-waarde is niet opgeslagen  
  - **Blok** -de LAN Manager (LM) slaat de hash-waarde voor het nieuwe wacht woord op.  

- **PKU2U-verificatieaanvragen**  
  **Standaard**: niet geconfigureerd  
  LocalPoliciesSecurityOptions CSP: [NetworkSecurity_AllowPKU2UAuthenticationRequests](https://go.microsoft.com/fwlink/?linkid=867892)  

  - **Niet geconfigureerd**-PU2U-aanvragen toestaan.  
  - **Blok** keren: PKU2U authenticatie aanvragen naar het apparaat.  

- **Externe RPC-verbindingen met SAM beperken**  
  **Standaard**: niet geconfigureerd  
  LocalPoliciesSecurityOptions CSP: [NetworkAccess_RestrictClientsAllowedToMakeRemoteCallsToSAM](https://go.microsoft.com/fwlink/?linkid=867893)  
  
  - **Niet geconfigureerd** : gebruik de standaard security descriptor, zodat gebruikers en groepen externe RPC-aanroepen naar de SAM kunnen toestaan.
  - **Toestaan** : weiger gebruikers en groepen om externe RPC-aanroepen naar de SAM (Security Accounts Manager) te maken, waarmee gebruikers accounts en wacht woorden worden opgeslagen. Met **toestaan** kunt u ook de standaard SDDL-teken reeks (Security Descriptor Definition Language) wijzigen om gebruikers en groepen expliciet toe te staan of te weigeren om deze externe aanroepen te maken.  

    - **Beveiligingsdescriptor**  
      **Standaard**: *niet geconfigureerd*  
    
- **Minimale sessiebeveiliging voor op NTLM SSP-gebaseerde clients**  
  **Standaard**: geen  
  LocalPoliciesSecurityOptions CSP: [NetworkSecurity_MinimumSessionSecurityForNTLMSSPBasedClients](https://aka.ms/policy-csp-localpoliciessecurityoptions-networksecurity-minimumsessionsecurityforntlmsspbasedclients)  
  
  Via deze beveiligingsinstelling kan een server de onderhandeling van een 128-bits versleuteling en/of een NTLMv2-sessiebeveiliging vereisen.  

  - **Geen**  
  - **NTLMv2-sessiebeveiliging vereisen**  
  - **128-bits versleuteling vereisen**  
  - **NTLMv2 en 128-bits versleuteling**  
 
- **Minimale sessiebeveiliging voor op NTLM SSP-gebaseerde servers**  
  **Standaard**: geen  
  LocalPoliciesSecurityOptions CSP: [NetworkSecurity_MinimumSessionSecurityForNTLMSSPBasedServers](https://aka.ms/policy-csp-localpoliciessecurityoptions-networksecurity-minimumsessionsecurityforntlmsspbasedservers)  

  Met deze beveiligingsinstelling bepaalt u welk vraag/antwoord-verificatieprotocol wordt gebruikt voor netwerkaanmeldingen.  

  - **Geen**  
  - **NTLMv2-sessiebeveiliging vereisen**  
  - **128-bits versleuteling vereisen**  
  - **NTLMv2 en 128-bits versleuteling**  

- **LAN Manager-verificatie niveau**  
  **Standaard**: LM en NTLM  
  LocalPoliciesSecurityOptions CSP: [NetworkSecurity_LANManagerAuthenticationLevel](https://aka.ms/policy-csp-localpoliciessecurityoptions-lanmanagerauthenticationlevel)  


  - **LM en NTLM**  
  - **LM, NTLM en NTLMv2**  
  - **NTLM**  
  - **NTLMv2**  
  - **NTLMv2 en niet LM**  
  - **NTLMv2 en niet LM of NTLM**  
  
- **Onveilige gast aanmeldingen**  
  **Standaard**: niet geconfigureerd  
  LanmanWorkstation CSP: [lanmanworkstation](https://aka.ms/policy-csp-lanmanworkstation-enableinsecureguestlogons)  

  Als u deze instelling inschakelt, weigert de SMB-client onveilige gast aanmeldingen.  

  - **Niet geconfigureerd**  
  - **Blok keren** : de SMB-client weigert onveilige gast aanmeldingen.  

### <a name="recovery-console-and-shutdown"></a>Herstelconsole en afsluiten  

- **Wisselbestand voor virtueel geheugen wissen bij het afsluiten**  
  **Standaard**: niet geconfigureerd  
   LocalPoliciesSecurityOptions CSP: [Shutdown_ClearVirtualMemoryPageFile](https://go.microsoft.com/fwlink/?linkid=867914)  


  - **Inschakelen**: het wisselbestand voor virtueel geheugen wissen wanneer het apparaat wordt uitgeschakeld.  
  - **Niet geconfigureerd**: het virtuele geheugen niet wissen.  

- **Afsluiten zonder aanmelden**  
  **Standaard**: niet geconfigureerd  
  LocalPoliciesSecurityOptions CSP: [Shutdown_AllowSystemToBeShutDownWithoutHavingToLogOn](https://go.microsoft.com/fwlink/?linkid=867912)  

  
  - **Blokkeren**: de afsluitoptie in het Windows-aanmeldingsscherm verbergen. Gebruikers moet zich aanmelden bij het apparaat en vervolgens afsluiten.  
  - **Niet geconfigureerd**: gebruikers kunnen het apparaat afsluiten vanaf het Windows-aanmeldingsscherm.  

### <a name="user-account-control"></a>Gebruikersaccountbeheer  

- **UIA-integriteit zonder veilige locatie**  
  **Standaardinstelling**: niet geconfigureerd  
  LocalPoliciesSecurityOptions CSP: [UserAccountControl_OnlyElevateUIAccessApplicationsThatAreInstalledInSecureLocations](https://go.microsoft.com/fwlink/?linkid=867897)  
  
  - **Blok** -apps die zich op een veilige locatie in het bestands systeem bevinden, worden alleen uitgevoerd met de integriteit van UIAccess.  
  - **Niet geconfigureerd**: apps kunnen worden uitgevoerd met UIAccess-integriteit, zelfs als de apps zich niet op een veilige locatie in het bestandssysteem bevinden.  

- **Schrijffouten in bestanden en registers in locaties per gebruiker virtualiseren**  
  **Standaardinstelling**: niet geconfigureerd  
  LocalPoliciesSecurityOptions CSP: [UserAccountControl_VirtualizeFileAndRegistryWriteFailuresToPerUserLocations](https://go.microsoft.com/fwlink/?linkid=867900)  

  - **Ingeschakeld** : toepassingen die gegevens naar beveiligde locaties schrijven, mislukken.  
  - **Niet geconfigureerd**: schrijffouten in toepassingen worden tijdens runtime omgeleid naar gedefinieerde gebruikerslocaties voor het bestandssysteem en register.  

- **Alleen bevoegdheden verhogen voor uitvoerbare bestanden die zijn ondertekend en gevalideerd**  
  **Standaardinstelling**: niet geconfigureerd  
  LocalPoliciesSecurityOptions CSP: [UserAccountControl_OnlyElevateUIAccessApplicationsThatAreInstalledInSecureLocations](https://go.microsoft.com/fwlink/?linkid=867965)  

  - **Ingeschakeld**: de validatie van het PKI-certificeringspad afdwingen voor een uitvoerbaar bestand voordat dit mag worden uitgevoerd.  
  - **Niet geconfigureerd**: validatie van het PKI-certificeringspad niet afdwingen voordat een uitvoerbaar bestand kan worden uitgevoerd.  

#### <a name="uia-elevation-prompt-behavior"></a>Gedrag bij vragen om UIA-uitbreiding  

- **Vragen om benodigde bevoegdheden voor beheerders**  
  **Standaard**: vragen om toestemming voor niet-Windows binaire bestanden  
  LocalPoliciesSecurityOptions CSP: [UserAccountControl_BehaviorOfTheElevationPromptForAdministrators](https://go.microsoft.com/fwlink/?linkid=867895)  

  Definieer het gedrag voor het vragen om benodigde bevoegdheden voor beheerders in de modus Door administrator goedkeuren.  

  - **Niet geconfigureerd**  
  - **Verhogen zonder te vragen**  
  - **Vragen om referenties op het beveiligde bureaublad**  
  - **Vragen om referenties**  
  - **Vragen om toestemming**  
  - **Vragen om toestemming voor niet-Windows binaire bestanden**  


- **Vragen om benodigde bevoegdheden voor standaardgebruikers**  
  **Standaard**: vragen om referenties  
  LocalPoliciesSecurityOptions CSP: [UserAccountControl_BehaviorOfTheElevationPromptForStandardUsers](https://go.microsoft.com/fwlink/?linkid=867896)  

  Definieer het gedrag voor het vragen om benodigde bevoegdheden voor standaardgebruikers.  

  - **Niet geconfigureerd**  
  - **Vragen voor benodigde bevoegdheden automatisch weigeren**  
  - **Vragen om referenties op het beveiligde bureaublad**  
  - **Vragen om referenties**  

- **Leid vragen over benodigde bevoegdheden naar het interactieve bureaublad van de gebruiker**  
  **Standaardinstelling**: niet geconfigureerd  
  LocalPoliciesSecurityOptions CSP: [UserAccountControl_SwitchToTheSecureDesktopWhenPromptingForElevation](https://go.microsoft.com/fwlink/?linkid=867899)  


  - **Ingeschakeld** : alle uitbrei ding aanvragen om naar het bureau blad van de interactieve gebruiker te gaan, in plaats van het beveiligde bureau blad. Er worden beleidsinstellingen voor gedrag voor beheerders en standaardgebruikers gebruikt.  
  - **Niet geconfigureerd**: afdwingen dat alle aanvragen voor uitbreiding van bevoegdheden naar het beveiligde bureaublad gaan, ongeacht eventuele beleidsinstellingen voor gedrag voor beheerders en standaardgebruikers.

- **Prompt met verhoogde bevoegdheden voor app-installaties**  
  **Standaardinstelling**: niet geconfigureerd  
  LocalPoliciesSecurityOptions CSP: [UserAccountControl_DetectApplicationInstallationsAndPromptForElevation](https://go.microsoft.com/fwlink/?linkid=867901)  

   - **Ingeschakeld**: installatiepakketten voor toepassingen worden niet gedetecteerd en worden niet om benodigde bevoegdheden gevraagd.
   - **Niet geconfigureerd**: gebruikers worden gevraagd om een gebruikersnaam en wachtwoord van een beheerder wanneer het installatiepakket van een toepassing verhoogde bevoegdheden vereist.

- **Vragen om benodigde UIA-bevoegdheden zonder beveiligd bureaublad**  
  **Standaardinstelling**: niet geconfigureerd  
  LocalPoliciesSecurityOptions CSP: [UserAccountControl_AllowUIAccessApplicationsToPromptForElevation](https://go.microsoft.com/fwlink/?linkid=867894)  

- **Inschakelen**: UIAccess-apps toestemming geven om te vragen om benodigde bevoegdheden zonder het beveiligde bureaublad te gebruiken.  
- **Niet geconfigureerd** -vragen om benodigde bevoegdheden een beveiligd bureau blad gebruiken.  

#### <a name="admin-approval-mode"></a>Modus Door administrator goedkeuren  

- **Modus Door administrator goedkeuren voor geïntegreerde beheerder**  
  **Standaardinstelling**: niet geconfigureerd  
  LocalPoliciesSecurityOptions CSP: [UserAccountControl_UseAdminApprovalMode](https://go.microsoft.com/fwlink/?linkid=867902)  

  - **Ingeschakeld**: het ingebouwde Administrator-account kan de modus Door administrator goedkeuren gebruiken. Voor elke bewerking waarvoor uitbreiding van toegangsrechten is vereist, wordt de gebruiker gevraagd de bewerking goed te keuren.  
  - **Niet geconfigureerd**: alle apps worden met volledige beheerdersbevoegdheden uitgevoerd.  

- **Alle beheerders uitvoeren in de modus Door administrator goedkeuren**  
  **Standaardinstelling**: niet geconfigureerd  
  LocalPoliciesSecurityOptions CSP: [UserAccountControl_RunAllAdministratorsInAdminApprovalMode](https://go.microsoft.com/fwlink/?linkid=867898)  


  - **Ingeschakeld**: modus voor goed keuring van beheerder inschakelen.  
  - **Niet geconfigureerd**: de modus Door administrator goedkeuren en alle gerelateerde UAC-beleidsinstellingen uitschakelen.  

### <a name="microsoft-network-client"></a>Microsoft Network Client  

- **Clientcommunicatie digitaal ondertekenen (indien mogelijk)**  
  **Standaard**: niet geconfigureerd  
  LocalPoliciesSecurityOptions CSP: [MicrosoftNetworkClient_DigitallySignCommunicationsIfServerAgrees](https://go.microsoft.com/fwlink/?linkid=868423)  

  Hiermee wordt bepaald of de SMB-client onderhandelt over SMB-pakketondertekening.  
  - **Blok keren** : de SMB-client onderhandelt nooit SMB-pakket ondertekening.
  - **Niet geconfigureerd**: de Microsoft-netwerkclient vraagt de server om SMB-pakketondertekening uit te voeren bij het opzetten van een sessie. Als pakketondertekening is ingeschakeld op de server, wordt over ondertekening van pakketten onderhandeld.  

- **Niet-versleuteld wachtwoord verzenden om verbinding te kunnen maken met niet-Microsoft SMB-servers**  
  **Standaard**: niet geconfigureerd  
  LocalPoliciesSecurityOptions CSP: [MicrosoftNetworkClient_SendUnencryptedPasswordToThirdPartySMBServers](https://go.microsoft.com/fwlink/?linkid=868426)  


  - **Blokkeren**: de SMB-redirector (Server Message Block) kan ongecodeerde wachtwoorden verzenden naar niet-Microsoft SMB-servers die geen ondersteuning voor wachtwoordversleuteling bieden tijdens verificatie.  
  - **Niet geconfigureerd** : het verzenden van wacht woorden met lees bare tekst blok keren. De wacht woorden worden versleuteld.  

- **Communicatie digitaal ondertekenen (altijd)**  
  **Standaard**: niet geconfigureerd  
  LocalPoliciesSecurityOptions CSP: [MicrosoftNetworkClient_DigitallySignCommunicationsAlways](https://go.microsoft.com/fwlink/?linkid=868425)  


  - **Inschakelen**: de Microsoft-netwerkclient communiceert niet met een Microsoft-netwerkserver, tenzij die server akkoord gaat met SMB-pakketondertekening.  
  - **Niet geconfigureerd** : er wordt onderhandeld over het ondertekenen van SMB-pakketten tussen de client en de server.  

### <a name="microsoft-network-server"></a>Microsoft Network Server  
  
- **Communicatie digitaal ondertekenen (bij akkoord van client)**  
  **Standaard**: niet geconfigureerd  
  CSP: [MicrosoftNetworkServer_DigitallySignCommunicationsIfClientAgrees](https://go.microsoft.com/fwlink/?linkid=868429)  

  - **Inschakelen**: de Microsoft-netwerkserver onderhandelt over SMB-pakketondertekening zoals aangevraagd door de client. Ofwel, als pakketondertekening is ingeschakeld op de client, wordt over ondertekening van pakketten onderhandeld.  
  - **Niet geconfigureerd** : de SMB-client onderhandelt nooit SMB-pakket ondertekening.  

- **Communicatie digitaal ondertekenen (altijd)**  
  **Standaard**: niet geconfigureerd  
  CSP: [MicrosoftNetworkServer_DigitallySignCommunicationsAlways](https://go.microsoft.com/fwlink/?linkid=868428)  

  - **Inschakelen**: de Microsoft-netwerkserver communiceert niet met een Microsoft-netwerkclient, tenzij die client akkoord gaat met SMB-pakketondertekening.  
  - **Niet geconfigureerd** : er wordt onderhandeld over het ondertekenen van SMB-pakketten tussen de client en de server.  

## <a name="xbox-services"></a>Xbox-Services

- **Xbox game-taak opslaan**  
  **Standaard**: niet geconfigureerd  
  CSP: [TaskScheduler/EnableXboxGameSaveTask](https://go.microsoft.com/fwlink/?linkid=875480)  
   
  Met deze instelling wordt bepaald of de taak voor het opslaan van Xbox-games is ingeschakeld of uitgeschakeld.  
  - **Ingeschakeld**
  - **Niet geconfigureerd**

- **Xbox accessoire Management-service**  
  **Standaard**: hand matig  
  CSP: [SystemServices/ConfigureXboxAccessoryManagementServiceStartupMode](https://go.microsoft.com/fwlink/?linkid=875481)  

  Met deze instelling wordt het start type van de service voor het beheer van accessoires bepaald.  
  - **Handmatig**
  - **Automatisch**
  - **Uitgeschakeld**

- **Xbox Live auth Manager-service**  
  **Standaard**: hand matig  
  CSP: [SystemServices/ConfigureXboxLiveAuthManagerServiceStartupMode](https://go.microsoft.com/fwlink/?linkid=875482)  
 
  Met deze instelling wordt het start type van de service van de Live auth Manager bepaald.  
  - **Handmatig**
  - **Automatisch**
  - **Uitgeschakeld**
 
- **Xbox Live-spel service**  
  **Standaard**: hand matig  
  CSP: [SystemServices/ConfigureXboxLiveGameSaveServiceStartupMode](https://go.microsoft.com/fwlink/?linkid=875483)  

  Met deze instelling wordt het start type van de service voor het opslaan van de Live game bepaald.  
  - **Handmatig**
  - **Automatisch**
  - **Uitgeschakeld**

- **Xbox Live-netwerk service**  
  **Standaard**: hand matig  
  CSP: [SystemServices/ConfigureXboxLiveNetworkingServiceStartupMode](https://go.microsoft.com/fwlink/?linkid=875484)  

  Met deze instelling bepaalt u het start type van de netwerk service.  
  - **Handmatig**
  - **Automatisch**
  - **Uitgeschakeld**

## <a name="user-rights"></a>Gebruikers rechten

- **Toegang tot Referentiebeheer als vertrouwde aanvrager**  
  **Standaard**: niet geconfigureerd  
  CSP: [UserRights/AccessCredentialManagerAsTrustedCaller](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-userrights#userrights-accesscredentialmanagerastrustedcaller)

  Dit gebruikers recht wordt gebruikt door Credential Manager tijdens het maken van back-ups en herstel bewerkingen. De opgeslagen referenties van de gebruiker kunnen worden aangetast als deze bevoegdheid aan andere entiteiten wordt gegeven.
  - **Niet geconfigureerd**
  - **Toestaan**

- **Lokaal aanmelden toestaan**  
  **Standaard**: niet geconfigureerd  
  CSP: [UserRights/AllowLocalLogOn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-userrights#userrights-allowlocallogon)

  Met dit gebruikers recht bepaalt u welke gebruikers zich kunnen aanmelden bij de computer.
  - **Niet geconfigureerd**
  - **Toestaan**

- **Toegang vanaf het netwerk toestaan**  
  **Standaard**: niet geconfigureerd  
  CSP: [UserRights/AccessFromNetwork](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-userrights#userrights-accessfromnetwork)

  Met dit gebruikers recht bepaalt u welke gebruikers en groepen via het netwerk verbinding mogen maken met de computer.
  - **Niet geconfigureerd**
  - **Toestaan**

- **Functioneren als deel van het besturings systeem**  
  **Standaard**: niet geconfigureerd  
  CSP: [UserRights/ActAsPartOfTheOperatingSystem](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-userrights#userrights-actaspartoftheoperatingsystem)

  Functioneren als deel van het besturings systeem
  - **Niet geconfigureerd**
  - **Toestaan**  

- **Back-ups van bestanden en mappen maken**  
  **Standaard**: niet geconfigureerd  
  CSP: [UserRights/BackupFilesAndDirectories](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-userrights#userrights-backupfilesanddirectories)

  Met dit gebruikers recht bepaalt u welke gebruikers machtigingen voor bestanden, mappen, het REGI ster en andere permanente objecten kunnen omzeilen bij het maken van een back-up van bestanden en mappen.
  - **Niet geconfigureerd**
  - **Toestaan**

- **De systeemtijd wijzigen**  
  **Standaard**: niet geconfigureerd  
  CSP: [UserRights/ChangeSystemTime](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-userrights#userrights-changesystemtime)

  Dit gebruikers recht bepaalt welke gebruikers en groepen de tijd en de datum van de interne klok van de computer kunnen wijzigen.
  - **Niet geconfigureerd**
  - **Toestaan**

- **Globale objecten maken**  
  **Standaard**: niet geconfigureerd  
  CSP: [UserRights/CreateGlobalObjects](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-userrights#userrights-createglobalobjects)

  Met deze beveiligings instelling bepaalt u of gebruikers globale objecten kunnen maken die beschikbaar zijn voor alle sessies. Gebruikers die globale objecten kunnen maken, kunnen invloed hebben op processen die worden uitgevoerd onder andere gebruikers sessies, wat kan leiden tot een toepassings fout of beschadiging van gegevens.
  - **Niet geconfigureerd**
  - **Toestaan**

- **Wissel bestand maken**  
  **Standaard**: niet geconfigureerd  
  CSP: [UserRights/CreatePageFile](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-userrights#userrights-createpagefile)

  Dit gebruikers recht bepaalt welke gebruikers en groepen een interne API kunnen aanroepen om de grootte van een wissel bestand te maken en te wijzigen.
  - **Niet geconfigureerd**
  - **Toestaan**

- **Permanent gedeelde objecten maken**  
  **Standaard**: niet geconfigureerd  
  CSP: [UserRights/CreatePermanentSharedObjects](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-userrights#userrights-createpermanentsharedobjects)

  Met dit gebruikers recht bepaalt u welke accounts door processen kunnen worden gebruikt om een Directory-object te maken met behulp van object beheer.
  - **Niet geconfigureerd**
  - **Toestaan**

- **Symbolische koppelingen maken**  
  **Standaard**: niet geconfigureerd  
  CSP: [UserRights/CreateSymbolicLinks](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-userrights#userrights-createsymboliclinks)

  Dit gebruikers recht bepaalt of de gebruiker een symbolische koppeling kan maken van de computer waarop ze zijn aangemeld.
  - **Niet geconfigureerd**
  - **Toestaan**

- **Tokens maken**  
  **Standaard**: niet geconfigureerd  
  CSP: [UserRights/Okta](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-userrights#userrights-createtoken)

  Dit gebruikers recht bepaalt welke gebruikers/groepen kunnen worden gebruikt door processen om een token te maken dat vervolgens kan worden gebruikt om toegang te krijgen tot lokale resources wanneer het proces een interne API gebruikt om een toegangs token te maken.
  - **Niet geconfigureerd**
  - **Toestaan**

- **Fouten in programma's opsporen**  
  **Standaard**: niet geconfigureerd  
    CSP: [UserRights/DebugPrograms](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-userrights#userrights-debugprograms)

  Met dit gebruikers recht bepaalt u welke gebruikers een fout opsporingsprogramma aan een proces of aan de kernel kunnen koppelen.
  - **Niet geconfigureerd**
  - **Toestaan**

- **Toegang vanaf het netwerk weigeren**  
  **Standaard**: niet geconfigureerd  
  CSP: [UserRights/DenyAccessFromNetwork](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-userrights#userrights-denyaccessfromnetwork)

  Dit gebruikers recht bepaalt welke gebruikers geen toegang hebben tot een computer via het netwerk.
  - **Niet geconfigureerd**
  - **Toestaan**

- **Aanmelden als service weigeren**  
  **Standaard**: niet geconfigureerd  
  CSP: [UserRights/DenyLocalLogOn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-userrights#userrights-denylocallogon)

  Met deze beveiligings instelling bepaalt u welke service accounts een proces niet als een service kunnen registreren.
  - **Niet geconfigureerd**
  - **Toestaan**

- **Aanmelden weigeren via Extern bureaublad-Services**  
  **Standaard**: niet geconfigureerd  
  CSP: [UserRights/DenyRemoteDesktopServicesLogOn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-userrights#userrights-denyremotedesktopserviceslogon)

  Dit gebruikers recht bepaalt welke gebruikers en groepen zich niet mogen aanmelden als een Extern bureaublad-services-client.
  - **Niet geconfigureerd**
  - **Toestaan**

- **Delegering inschakelen**  
  **Standaard**: niet geconfigureerd  
  CSP: [UserRights/EnableDelegation](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-userrights#userrights-enabledelegation)

 Dit gebruikers recht bepaalt welke gebruikers de instelling vertrouwd voor delegeren kunnen instellen voor een gebruiker of computer object.
  - **Niet geconfigureerd**
  - **Toestaan**

- **Beveiligingscontroles genereren**  
  **Standaard**: niet geconfigureerd  
  CSP: [UserRights/GenerateSecurityAudits](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-userrights#userrights-generatesecurityaudits)

  Dit gebruikers recht bepaalt welke accounts kunnen worden gebruikt door een proces om vermeldingen toe te voegen aan het beveiligings logboek. Het beveiligings logboek wordt gebruikt voor het traceren van onbevoegde systeem toegang.
  - **Niet geconfigureerd**
  - **Toestaan**

- **Een client imiteren**  
  **Standaard**: niet geconfigureerd  
  CSP: [UserRights/ImpersonateClient](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-userrights#userrights-impersonateclient)

  Als u dit gebruikers recht aan een gebruiker toewijst, kunnen Program ma's die namens die gebruiker worden uitgevoerd, een client imiteren. Als u dit gebruikers recht vereist voor dit soort imitatie, voor komt u dat een niet-geautoriseerde gebruiker een client kan koppelen aan een service die ze hebben gemaakt en vervolgens die client imiteert, waardoor de machtigingen van de niet-geautoriseerde gebruiker kunnen worden verhoogd tot beheer-of systeem niveaus.
  - **Niet geconfigureerd**
  - **Toestaan**

- **Prioriteit verhogen voor planning**  
  **Standaard**: niet geconfigureerd  
  CSP: [UserRights/IncreaseSchedulingPriority](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-userrights#userrights-increaseschedulingpriority)

  Met dit gebruikers recht bepaalt u welke accounts een proces met schrijf toegang tot een ander proces kunnen gebruiken om de uitvoerings prioriteit die aan het andere proces is toegewezen, te verg Roten.
  - **Niet geconfigureerd**
  - **Toestaan**

- **Apparaatstuurprogramma's laden en verwijderen**  
  **Standaard**: niet geconfigureerd  
  CSP: [UserRights/LoadUnloadDeviceDrivers](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-userrights#userrights-loadunloaddevicedrivers)

  Met dit gebruikers recht bepaalt u welke gebruikers Stuur Programma's of andere code dynamisch kunnen laden en verwijderen in de kernelmodus.
  - **Niet geconfigureerd**
  - **Toestaan**

- **Pagina's in het geheugen vergrendelen**  
  **Standaard**: niet geconfigureerd  
  CSP: [UserRights/LockMemory](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-userrights#userrights-lockmemory)

  Dit gebruikers recht bepaalt welke accounts een proces kunnen gebruiken voor het opslaan van gegevens in het fysieke geheugen, waarmee wordt voor komen dat het systeem de gegevens naar het virtuele geheugen op schijf gepagineerd.
  - **Niet geconfigureerd**
  - **Toestaan**

- **Controle en beveiligingslogboek beheren**  
  **Standaard**: niet geconfigureerd  
  CSP: [UserRights/ManageAuditingAndSecurityLog](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-userrights#userrights-manageauditingandsecuritylog)

  Met dit gebruikers recht bepaalt u welke gebruikers controle opties voor object toegang kunnen opgeven voor afzonderlijke resources, zoals bestanden, Active Directory objecten en register sleutels.
  - **Niet geconfigureerd**
  - **Toestaan**

- **Onderhoudstaken op volume uitvoeren**  
  **Standaard**: niet geconfigureerd  
  CSP: [UserRights/ManageVolume](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-userrights#userrights-managevolume)

  Dit gebruikers recht bepaalt welke gebruikers en groepen onderhouds taken kunnen uitvoeren op een volume, zoals externe defragmentatie.
  - **Niet geconfigureerd**
  - **Toestaan**

- **Omgevingswaarden in firmware wijzigen**  
  **Standaard**: niet geconfigureerd  
  CSP: [UserRights/ModifyFirmwareEnvironment](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-userrights#userrights-modifyfirmwareenvironment)

  Dit gebruikers recht bepaalt wie firmware omgevings waarden kan wijzigen.
  - **Niet geconfigureerd**
  - **Toestaan**

- **Een objectlabel wijzigen**  
  **Standaard**: niet geconfigureerd  
  CSP: [UserRights/ModifyObjectLabel](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-userrights#userrights-modifyobjectlabel)

  Dit gebruikers recht bepaalt welke gebruikers accounts het integriteits label van objecten kunnen wijzigen, zoals bestanden, register sleutels of processen die eigendom zijn van andere gebruikers.
  - **Niet geconfigureerd**
  - **Toestaan**

- **Een enkel proces bekijken**  
  **Standaard**: niet geconfigureerd  
  CSP: [UserRights/ProfileSingleProcess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-userrights#userrights-profilesingleprocess)

  Met dit gebruikers recht bepaalt u welke gebruikers hulpprogram ma's voor prestatie controle kunnen gebruiken om de prestaties van systeem processen te controleren.
  - **Niet geconfigureerd**
  - **Toestaan**

- **Extern afsluiten**  
  **Standaard**: niet geconfigureerd  
  CSP: [UserRights/RemoteShutdown](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-userrights#userrights-remoteshutdown)

  Met dit gebruikers recht bepaalt u welke gebruikers een computer mogen afsluiten vanaf een externe locatie op het netwerk. Misbruik van dit gebruikers recht kan leiden tot een denial-of-service.
  - **Niet geconfigureerd**
  - **Toestaan**
  
- **Back-ups van bestanden en mappen terugzetten**  
  **Standaard**: niet geconfigureerd  
  CSP: [UserRights/RestoreFilesAndDirectories](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-userrights#userrights-restorefilesanddirectories)
  
  Dit gebruikers recht bepaalt welke gebruikers machtigingen voor bestanden, mappen, het REGI ster en andere permanente objecten kunnen overs Laan bij het terugzetten van back-ups van bestanden en mappen, en bepaalt welke gebruikers een geldige beveiligingsprincipal kunnen instellen als de eigenaar van een object.
  - **Niet geconfigureerd**
  - **Toestaan**
  
- **Eigenaar worden van bestanden of andere objecten**  
  **Standaard**: niet geconfigureerd  
  CSP: [UserRights/TakeOwnership](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-userrights#userrights-takeownership)

  Met dit gebruikers recht bepaalt u welke gebruikers eigenaar kunnen worden van elk Beveilig bare object in het systeem, met inbegrip van Active Directory objecten, bestanden en mappen, printers, register sleutels, processen en threads.
  - **Niet geconfigureerd**
  - **Toestaan**

## <a name="next-steps"></a>Volgende stappen

Het profiel is gemaakt, maar er gebeurt nog niets. Vervolgens moet u [het profiel toewijzen](../configuration/device-profile-assign.md) en [de status ervan controleren](../configuration/device-profile-monitor.md).  

Instellingen voor eindpuntbescherming configureren op [macOS](endpoint-protection-macos.md)-apparaten.  
