---
title: Beveiligingsbasislijninstellingen van Intune voor Microsoft Defender Advanced Threat Protection
titleSuffix: Microsoft Intune
description: Beveiligingsbasislijninstellingen die door Intune worden ondersteund voor het beheren van Microsoft Defender Advanced Threat Protection
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/25/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: ''
ms.reviewer: shpate
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: aa3cb3481de6e1fdc3790b7330ac521772e252be
ms.sourcegitcommit: 5932da3ed8f52c7b0f0d71c1801f81c85952cf0c
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 10/25/2019
ms.locfileid: "72923409"
---
# <a name="microsoft-defender-advanced-threat-protection-baseline-settings-for-intune"></a>Microsoft Defender Advanced Threat Protection-basislijninstellingen voor Intune

Bekijk de basislijninstellingen voor Microsoft Defender Advanced Threat Protection (voorheen Windows Defender Advanced Threat Protection) die worden ondersteund door Microsoft Intune. De standaardinstellingen van de basislijn Advanced Threat Protection (ATP) vertegenwoordigen de aanbevolen configuratie voor ATP en komen mogelijk niet overeen met de standaardinstellingen voor andere beveiligingsbasislijnen.  

De basislijn Microsoft Defender Advanced Threat Protection is beschikbaar als uw omgeving voldoet aan de vereisten voor het gebruik van [Microsoft Defender Advanced Threat Protection](advanced-threat-protection.md#prerequisites). 

Deze basis lijn is geoptimaliseerd voor fysieke apparaten en wordt momenteel niet aanbevolen voor gebruik op virtuele machines (Vm's) of VDI-eind punten. Bepaalde basislijninstellingen kunnen invloed hebben op externe interactieve sessies in gevirtualiseerde omgevingen. Voor meer informatie ziet u [Increase compliance to the Microsoft Defender ATP security baseline](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-machines-security-baseline) (Naleving met de Microsoft Defender ATP-beveiligingsbasislijn vergroten) in de Windows-documentatie.

## <a name="application-guard"></a>Application Guard  
Zie [WindowsDefenderApplicationGuard CSP](https://docs.microsoft.com/windows/client-management/mdm/windowsdefenderapplicationguard-csp) in de Windows-documentatie voor meer informatie.  

Wanneer u Microsoft Edge gebruikt, beschermt Microsoft Defender Application Guard uw omgeving tegen sites die niet worden vertrouwd door uw organisatie. Als gebruikers sites bezoeken die niet worden vermeld in uw geïsoleerde netwerkgrens, worden deze sites geopend in een virtuele browsersessie in Hyper-V. Vertrouwde sites worden gedefinieerd door een netwerkgrens.  

- **Application Guard** - *Settings/AllowWindowsDefenderApplicationGuard*  
  Selecteer *Ja* om deze functie aan te zetten. Hiermee worden niet-vertrouwde sites in een gevirtualiseerde Hyper-V-browsercontainer geopend. Als de functie op *Niet geconfigureerd* wordt ingesteld, wordt elke site (vertrouwd en niet-vertrouwd) op het apparaat geopend, en niet in een gevirtualiseerde container.  

  **Standaardinstelling**: Ja
 
  - **Externe inhoud op bedrijfssites** - *Settings/BlockNonEnterpriseContent*  
    Selecteer *Ja*, zodat inhoud van niet-goedgekeurde websites niet kan worden geladen. Als de functie op *Niet geconfigureerd* wordt ingesteld, kunnen niet-bedrijfssites op het apparaat worden geopend. 
 
    **Standaardinstelling**: Ja

  - **Klembordgedrag** - *Settings/ClipboardSettings*  
    Kies welke kopieer- en plakbewerkingen zijn toegestaan tussen de lokale pc en de virtuele browser van Application Guard.  Opties zijn onder andere:
    - Niet geconfigureerd  
    - Kopiëren en plakken tussen de PC en de browser blok keren... Er kunnen geen gegevens tussen de pc en de virtuele browser worden overgedragen.  
    - Kopiëren en plakken van browser naar PC toestaan: gegevens kunnen niet worden overgedragen van de PC naar de virtuele browser.
    - Kopiëren en plakken van PC naar browser toestaan: gegevens kunnen niet worden overgedragen van de virtuele browser naar de host-PC.
    - Kopiëren en plakken tussen de PC en de browser toestaan: er bestaat geen blok voor inhoud.  

    **Standaard**: kopiëren en plakken tussen de PC en de browser blok keren  

- **Windows-beleid voor netwerkisolatie – domeinnamen van bedrijfsnetwerk**  
  Zie [Beleids-CSP - NetworkIsolation](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-networkisolation) in de Windows-documentatie voor meer informatie.
  
  Geef een lijst met bedrijfsresources zoals domeinen, IP-adresbereiken en netwerkgrenzen op die worden gehost in de cloud die Application Guard als bedrijfssites behandelt.  

  **Standaardinstelling**: securitycenter.windows.com

## <a name="application-reputation"></a>Toepassingsreputatie  

Zie [Beleids-CSP - SmartScreen](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-smartscreen) in de Windows-documentatie voor meer informatie.

- **Uitvoering van niet-geverifieerde bestanden blokkeren**  
    Verhinderen dat een gebruiker niet-geverifieerde bestanden uitvoert. Met de instelling *Niet geconfigureerd* kunnen werknemers SmartScreen-waarschuwingen negeren en schadelijke bestanden uitvoeren. Met de instelling *Ja* kunnen werknemers SmartScreen-waarschuwingen niet negeren en geen schadelijke bestanden uitvoeren.  
  
    **Standaardinstelling**: Ja

- **SmartScreen vereisen voor apps en bestanden**  
  Kies de instelling *Ja* om SmartScreen voor Windows in te schakelen.  

  **Standaardinstelling**: Ja

## <a name="attack-surface-reduction"></a>Kwetsbaarheid voor aanvallen verminderen  

- **Onderliggend procestype voor starten van Office-apps**  
  [Regel voor het verminderen van de kwetsbaarheid voor aanvallen](/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction#attack-surface-reduction-rules): als de regel is ingesteld op *Blokkeren*, kunnen Office-apps geen onderliggende processen maken. Office-apps zijn onder meer Word, Excel, PowerPoint, OneNote en Access. Het maken van een onderliggend proces is typisch malwaregedrag, met name voor op macro's gebaseerde aanvallen die Office-apps proberen te gebruiken om schadelijke uitvoerbare bestanden te starten of te downloaden.  

  **Standaardinstelling**: Blokkeren

- **Uitvoeringstype van de payload die is gedownload met een script**  
  [Defender/PUAProtection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-puaprotection): geef een detectieniveau op voor mogelijk ongewenste toepassingen die proberen te downloaden of te installeren.  

  **Standaardinstelling**: Blokkeren 

- **Type referentiediefstal voorkomen**  
  Stel in op *Inschakelen* om [afgeleide domeinreferenties te beveiligen met Credential Guard](https://docs.microsoft.com/windows/security/identity-protection/credential-guard/credential-guard). Windows Defender Credential Guard maakt gebruik van op virtualisatie gebaseerde beveiliging om geheime gegevens te isoleren. Zo hebt u er alleen met bevoegde systeemsoftware toegang toe. Niet-geautoriseerde toegang tot deze geheime gegevens kan leiden tot pogingen tot diefstal, zoals een Pass-the-Hash- of Pass-the-Ticket-aanval. Met Windows Defender Credential Guard worden deze aanvallen voorkomen, doordat NTLM-wachtwoord-hashes, Kerberos Ticket Granting Tickets en referenties die door toepassingen zijn opgeslagen als domeinreferenties worden beschermd.  

  **Standaardinstelling**: Inschakelen

- **Uitvoer e-mailinhoud**  
  [Regel voor het verminderen van de kwetsbaarheid voor aanvallen](/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction#attack-surface-reduction-rules): wanneer deze regel is ingesteld op *Blokkeren*, voorkomt deze at de volgende bestandstypen worden uitgevoerd of gestart vanuit een e-mailbericht dat wordt weergegeven in Microsoft Outlook of webmail (zoals Gmail.com of Outlook.com):  

  - Uitvoerbare bestanden (zoals .exe, .dll of .scr)  
  - Scriptbestanden (zoals een .ps-bestand van PowerShell-PS, .vbs-bestand van VisualBasic of .js-bestand van JavaScript)  
  - Script-archiefbestanden  

  **Standaardinstelling**: Blokkeren

- **Adobe Reader starten in een onderliggend proces**  
  [Regel voor het verminderen van de kwetsbaarheid voor aanvallen](/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction#attack-surface-reduction-rules): u kunt deze regel *inschakelen* om te voorkomen dat Adobe Reader een onderliggend proces kan maken. Via social engineering of aanvallen kan malware aanvullende payloads downloaden en starten en uit Adobe Reader breken.  

  **Standaardinstelling**: Inschakelen

- **Macrocode verborgen in scripts**  
  [Regel voor het verminderen van de kwetsbaarheid voor aanvallen](/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction#attack-surface-reduction-rules): malware en andere bedreigingen kunnen proberen hun schadelijke code te verbergen in sommige scriptbestanden. Met deze regel wordt voorkomen dat scripts die verborgen lijken te zijn, worden uitgevoerd.  
    
  **Standaardinstelling**: Blokkeren

- **Niet-vertrouwd USB-proces**  
  [Regel voor het verminderen van de kwetsbaarheid voor aanvallen](/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction#attack-surface-reduction-rules): als u de instelling *Blokkeren* kiest, kunnen niet-ondertekende of niet-vertrouwde uitvoerbare bestanden op verwisselbare USB-stations en SD-kaarten niet worden uitgevoerd.

  Uitvoerbare bestanden zijn onder meer:
  - Uitvoerbare bestanden (zoals .exe, .dll of .scr)
  - Scriptbestanden (zoals een .ps-bestand van PowerShell-PS, .vbs-bestand van VisualBasic of .js-bestand van JavaScript)  

  **Standaardinstelling**: Blokkeren

- **Office-apps: invoering voor andere processen**  
  [Regel voor het verminderen van de kwetsbaarheid voor aanvallen](/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction#attack-surface-reduction-rules): als u de instelling *Blokkeren* kiest, kunnen Office-apps zoals Word, Excel, PowerPoint en OneNote geen code in andere processen invoegen. Het invoegen van code wordt doorgaans gebruikt door malware om schadelijke code uit te voeren in een poging om de activiteit te verbergen voor antivirusengines.  

  **Standaardinstelling**: Blokkeren

- **Office-macrocode staat Win32-imports toe**  
  [Regel voor het verminderen van de kwetsbaarheid voor aanvallen](/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction#attack-surface-reduction-rules): als u de instelling *Blokkeren* kiest, probeert deze regel Office-bestanden met macrocode die Win32-DLL's kan importeren te blokkeren. Office-bestanden omvatten Word, Excel, PowerPoint en OneNote. Malware kan macrocode in Office-bestanden gebruiken om Win32-DLL's te importeren en laden, die vervolgens worden gebruikt om API-aanroepen uit te voeren voor verdere infectie in het hele systeem.  

  **Standaardinstelling**: Blokkeren

- **Office-communicatieapps worden gestart in een onderliggend proces**  
  [Regel voor het verminderen van de kwetsbaarheid voor aanvallen](/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction#attack-surface-reduction-rules): als u de instelling *Inschakelen* kiest, voorkomt deze regel dat Outlook onderliggende processen maakt. Door het maken van onderliggende processen te blokkeren, beschermt deze regel tegen social engineering-aanvallen en voorkomt deze dat kwaadaardige code misbruik van een beveiligingsprobleem in Outlook kan maken.  

  **Standaardinstelling**: Inschakelen

- **Office-apps: uitvoerbare inhoud maken of lanceren**  
  [Regel voor het verminderen van de kwetsbaarheid voor aanvallen](/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction#attack-surface-reduction-rules): als u de instelling *Blokkeren* kiest, kunnen Office-apps geen uitvoerbare inhoud maken. Office-apps zijn onder meer Word, Excel, PowerPoint, OneNote en Access.  

  Deze regel is gericht op typisch gedrag van verdachte en schadelijke invoegtoepassingen en scripts (extensies) die uitvoerbare bestanden maken of openen. Dit is een typische malwaretechniek. Extensies kunnen niet worden gebruikt door Office-apps. Meestal gebruiken deze extensies Windows Scripting Host (WSH-bestanden) om scripts uit te voeren die bepaalde taken automatiseren of door gebruikers gemaakte extra functies leveren.

  **Standaardinstelling**: Blokkeren

## <a name="bitlocker"></a>BitLocker  

Zie [BitLocker Group Policy settings](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-group-policy-settings) (Instellingen voor BitLocker-groepsbeleid) in de Windows-documentatie voor meer informatie.  

- **Apparaten versleutelen**  
  Selecteer *Ja* om apparaatversleuteling van BitLocker in te schakelen. Afhankelijk van de hardware en versie van Windows op het apparaat, kunnen gebruikers worden gevraagd om te bevestigen dat er geen versleuteling van derden op het apparaat staat. Als Windows-versleuteling wordt ingeschakeld terwijl er versleuteling van derden actief is, wordt het apparaat instabiel.  

   **Standaardinstelling**: Ja

- **Bitlocker-beleid voor losse stations**  
  De waarden voor dit beleid bepalen de coderingssterkte die door BitLocker wordt gebruikt voor de versleuteling van verwisselbare stations. Ondernemingen kunnen het versleutelingsniveau bepalen voor extra beveiliging (AES-256 is sterker dan AES-128). Als u *Ja* selecteert om deze instelling in te schakelen, kunt u afzonderlijke versleutelingsalgoritmen en belangrijke coderingssterkten configureren voor vaste gegevensstations, besturingssysteemstations en verwisselbare gegevensstations. Voor vaste stations en besturingssysteemstations wordt het gebruik van het XTS-AES-algoritme aanbevolen. Gebruik 128-bits AES-CBC of 256-bits AES-CBC voor losse stations als het station in andere apparaten wordt gebruikt waarop geen Windows 10, versie 1511 of later wordt uitgevoerd. Het wijzigen van de versleutelingsmethode heeft geen invloed als het station al is versleuteld of als de versleuteling nog wordt uitgevoerd. In deze gevallen wordt deze beleidsinstelling genegeerd. 

  Voor het BitLocker-beleid voor verwisselbare stations moet u de volgende instellingen configureren:

  - **Versleuteling vereisen voor schrijftoegang**  
    **Standaardinstelling**: Ja

  - **Versleutelingsmethode**  
    **Standaardinstelling**: AES 128-bits CBC

- **Opslag kaart versleutelen (alleen mobiel)** Als u *Ja* selecteert, wordt de opslag kaart van het mobiele apparaat versleuteld.  

   **Standaardinstelling**: Ja

- **Bitlocker-beleid voor vaste stations**  
  De waarden voor dit beleid bepalen de coderingssterkte die door BitLocker wordt gebruikt voor de versleuteling van vaste stations. Ondernemingen kunnen het versleutelingsniveau bepalen voor extra beveiliging (AES-256 is sterker dan AES-128). Als u deze instelling inschakelt, kunt u afzonderlijke versleutelingsalgoritmen en belangrijke coderingssterkten configureren voor vaste gegevensstations, besturingssysteemstations en losse gegevensstations. Voor vaste stations en besturingssysteemstations wordt het gebruik van het XTS-AES-algoritme aanbevolen. Gebruik 128-bits AES-CBC of 256-bits AES-CBC voor losse stations als het station in andere apparaten wordt gebruikt waarop geen Windows 10, versie 1511 of later wordt uitgevoerd. Het wijzigen van de versleutelingsmethode heeft geen invloed als het station al is versleuteld of als de versleuteling nog wordt uitgevoerd. In deze gevallen wordt deze beleidsinstelling genegeerd.

  Voor het BitLocker-beleid voor vaste stations moet u de volgende instellingen configureren:

  - **Versleuteling vereisen voor schrijftoegang**  
    **Standaardinstelling**: Ja

  - **Versleutelingsmethode**  
    **Standaardinstelling**: AES 128-bits XTS

- **Bitlocker-beleid voor systeemstations**  
  De waarden voor dit beleid bepalen de coderingssterkte die door BitLocker wordt gebruikt voor de versleuteling van het systeemstation. Ondernemingen kunnen het versleutelingsniveau bepalen voor extra beveiliging (AES-256 is sterker dan AES-128). Als u deze instelling inschakelt, kunt u afzonderlijke versleutelingsalgoritmen en belangrijke coderingssterkten configureren voor vaste gegevensstations, besturingssysteemstations en losse gegevensstations. Voor vaste stations en besturingssysteemstations wordt het gebruik van het XTS-AES-algoritme aanbevolen. Gebruik 128-bits AES-CBC of 256-bits AES-CBC voor losse stations als het station in andere apparaten wordt gebruikt waarop geen Windows 10, versie 1511 of later wordt uitgevoerd. Het wijzigen van de versleutelingsmethode heeft geen invloed als het station al is versleuteld of als de versleuteling nog wordt uitgevoerd. In deze gevallen wordt deze beleidsinstelling genegeerd.  

  Voor het BitLocker-beleid voor het systeemstation moet u de volgende instellingen configureren:  

  - **Versleutelingsmethode**  
    **Standaardinstelling**: AES 128-bits XTS

## <a name="device-control"></a>Apparaatbeheer  

- **Verwisselbare stations scannen tijdens een volledige scan**  
  [Defender/AllowFullScanRemovableDriveScanning](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowfullscanremovabledrivescanning): als u de instelling *Ja* kiest, scant Defender tijdens een volledige scan naar schadelijke en ongewenste software op verwisselbare stations, zoals flashstations. Defender Antivirus scant alle bestanden op USB-apparaten voordat ze kunnen worden uitgevoerd.

  Gerelateerde instelling in deze lijst: *Defender/AllowFullScanOnMappedNetworkDrives*  

  **Standaardinstelling**: Ja

- **Opsomming van externe apparaten die niet compatibel zijn met DMA-beveiliging van kernel**  
   Zie *DmaGuard/DeviceEnumerationPolicy* in [Beleids-CSP - DmaGuard](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-dmaguard#dmaguard-deviceenumerationpolicy)

  Dit beleid biedt extra beveiliging tegen externe DMA-compatibele apparaten. Het geeft u meer controle over de opsomming van externe DMA-compatibele apparaten die niet compatibel zijn met apparaatgeheugenisolatie en sandbox van DMA.

  Dit beleid wordt alleen uitgevoerd als DMA-beveiliging van kernel wordt ondersteund en ingeschakeld door de systeemfirmware. DMA-beveiliging van kernel is een platformfunctie die niet kan worden beheerd door beleid of door de gebruiker van een apparaat. De functie moet door het systeem worden ondersteund ten tijde van de productie. 

  Voer MSINFO32.exe uit op het systeem en bekijk het veld *DMA-beveiliging van kernel* op de overzichtspagina om te controleren of het systeem DMA-beveiliging van kernel ondersteunt.  

  Opties zijn onder andere: 
  - *Standaardwaarde voor apparaat*: na aanmelden of ontgrendelen van het scherm mogen apparaten met stuurprogramma's die geschikt zijn voor opnieuw toewijzen met DMA op elk gewenst moment inventariseren. Apparaten met stuurprogramma's die niet geschikt zijn voor opnieuw toewijzen met DMA worden pas geïnventariseerd nadat de gebruiker het scherm ontgrendelt
  - *Alles toestaan*: alle externe DMA-compatibele PCIe-apparaten kunnen op elk gewenst moment worden geïnventariseerd
  - *Alles blokkeren*: apparaten met stuurprogramma's die geschikt zijn voor opnieuw toewijzen met DMA mogen op elk gewenst moment inventariseren. Apparaten met stuurprogramma's die niet geschikt zijn voor opnieuw toewijzen met DMA mogen nooit starten of DMA uitvoeren.

  **Standaardinstelling**: standaardinstelling van apparaat

- **Installatie van hardwareapparaten op basis van apparaat-id's**  
  [DeviceInstallation/PreventInstallationOfMatchingDeviceIDs](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deviceinstallation#deviceinstallation-preventinstallationofmatchingdeviceids): met dit beleid kunt u een lijst opgeven met Plug en Play-hardware-id's en compatibele id's voor apparaten die niet mogen worden geïnstalleerd in Windows. Deze beleidsinstelling heeft een hogere prioriteit dan welke andere beleidsinstelling dan ook waarmee Windows wordt toegestaan een apparaat te installeren. Als u deze beleidsinstelling inschakelt (instelling *Installatie van hardwareapparaten blokkeren*), kunnen apparaten waarvan de hardware-id of compatibele id die in de door u gemaakte lijst staan, niet worden geïnstalleerd in Windows. Als u deze beleidsinstelling inschakelt op een externe desktopserver, heeft dit beleid invloed op de omleiding van de opgegeven apparaten van een externe desktopclient naar de externe desktopserver. Als u deze beleidsinstelling uitschakelt of niet configureert (instelling *Installatie van hardwareapparaten toestaan*), kunnen apparaten worden geïnstalleerd of bijgewerkt, voor zover dat door andere beleidsinstellingen is toegestaan of verboden.  

  **Standaardinstelling**: installatie van hardwareapparaten blokkeren  

  Wanneer *installatie van hardwareapparaten blokkeren* wordt geselecteerd, zijn de volgende instellingen beschikbaar.
  - **Overeenkomende hardwareapparaten verwijderen**  
    Deze instelling is alleen beschikbaar als *Installatie hardwareapparaten op apparaat-id* is ingesteld op *Installatie van hardwareapparaten blokkeren*.  

    **Standaardinstelling**: Ja

  - **Hardwareapparaat-id's die zijn geblokkeerd**  
    Deze instelling is alleen beschikbaar als *Installatie hardwareapparaten op apparaat-id* is ingesteld op *Installatie van hardwareapparaten blokkeren*. Als u deze instelling wilt configureren, vouwt u de optie uit, selecteert u **+ Toevoegen** en geeft u vervolgens de hardwareapparaat-id op die u wilt blokkeren.  

    **Standaard**: PCI\CC_0C0A

- **Direct Memory Access blokkeren**  
  [DataProtection/AllowDirectMemoryAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-dataprotection#dataprotection-allowdirectmemoryaccess): met deze beleidsinstelling kunt u Direct Memory Access (DMA) blokkeren voor alle hot-pluggable PCI-downstream-poorten op een apparaat totdat een gebruiker zich bij Windows aanmeldt. Zodra een gebruiker zich heeft aangemeld, somt Windows de PCI-apparaten op die met de PCI-poorten van de host zijn verbonden. Steeds wanneer de gebruiker het apparaat vergrendelt, wordt DMA geblokkeerd op hot-pluggable PCI-poorten zonder onderliggende apparaten totdat de gebruiker zich opnieuw aanmeldt. Apparaten die al waren geïnventariseerd toen het apparaat was ontgrendeld, blijven werken totdat ze worden losgekoppeld. 

  Deze beleidsinstelling wordt uitsluitend afgedwongen wanneer BitLocker of apparaatversleuteling is ingeschakeld.  

  **Standaardinstelling**: Ja


- **Installatie van hardwareapparaten op basis van installatieklassen**  
  [DeviceInstallation/AllowInstallationOfMatchingDeviceSetupClasses](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deviceinstallation#deviceinstallation-allowinstallationofmatchingdevicesetupclasses): met deze beleidsinstelling kunt u een lijst opgeven met GUID's (Globally Unique Identifiers) voor de installatieklasse van apparaten voor apparaatstuurprogramma's die niet mogen worden geïnstalleerd in Windows. Deze beleidsinstelling heeft een hogere prioriteit dan welke andere beleidsinstelling dan ook waarmee Windows wordt toegestaan een apparaat te installeren. Als u deze beleidsinstelling inschakelt (instelling *Installatie van hardwareapparaten blokkeren*), mogen apparaatstuurprogramma's waarvan de GUID's voor de installatieklasse van apparaten niet in de door u gemaakte lijst staan, niet worden geïnstalleerd of bijgewerkt in Windows. Als u deze beleidsinstelling inschakelt op een externe desktopserver, heeft deze invloed op de omleiding van de opgegeven apparaten van een externe desktopclient naar de externe desktopserver. Als u deze beleidsinstelling uitschakelt of niet configureert (instelling *Installatie van hardwareapparaten toestaan*), kan Windows apparaten installeren en bijwerken, voor zover dat door andere beleidsinstellingen is toegestaan of verboden.  

  **Standaardinstelling**: installatie van hardwareapparaten blokkeren

  Wanneer *installatie van hardwareapparaten blokkeren* wordt geselecteerd, zijn de volgende instellingen beschikbaar.  

  - **Overeenkomende hardwareapparaten verwijderen**  
    Deze instelling is alleen beschikbaar wanneer *Installatie hardwareapparaten op installatieklasse* is ingesteld op *Installatie van hardwareapparaten blokkeren*.  
 
    **Standaardinstelling**: Ja  

  - **Hardwareapparaat-id's die zijn geblokkeerd**  
    Deze instelling is alleen beschikbaar wanneer Installatie hardwareapparaten op installatieklasse is ingesteld op Installatie van hardwareapparaten blokkeren. Als u deze instelling wilt configureren, vouwt u de optie uit, selecteert u **+ Toevoegen** en geeft u vervolgens de hardwareapparaat-id op die u wilt blokkeren.  
 
    **Standaard**: {d48179be-EC20-11D1-b6b8-00c04fa372a7}

## <a name="endpoint-detection-and-response"></a>Eindpuntdetectie en -respons  
Zie [WindowsAdvancedThreatProtection CSP](https://docs.microsoft.com/windows/client-management/mdm/windowsadvancedthreatprotection-csp) in de Windows-documentatie voor meer informatie.  

- **Frequentie van telemetrierapporten versnellen** - *Configuration/TelemetryReportingFrequency*

  De frequentie van telemetrierapporten van Microsoft Defender Advanced Threat Protection versnellen.  

  **Standaardinstelling**: Ja

- **Voorbeelddeling voor alle bestanden** - *Configuration/SampleSharing* 

  Hiermee wordt de configuratieparameter van de voorbeelddeling van Microsoft Defender Advanced Threat Protection geretourneerd of ingesteld.  

  **Standaardinstelling**: Ja

## <a name="exploit-protection"></a>Exploit Protection  

- **XML Exploit Guard-beveiliging**  
  Zie [Import, export, and deploy exploit protection configurations](/windows/security/threat-protection/microsoft-defender-atp/import-export-exploit-protection-emet-xml) (Exploit Protection-configuraties importeren, exporteren en implementeren) in de Windows-documentatie voor meer informatie.  

  Hiermee kan de IT-beheerder een configuratie pushen die de gewenste systeem- en toepassingbeperkingsopties voor alle apparaten in de organisatie aangeeft. De configuratie wordt vertegenwoordigd door een XML. 

  Exploit Protection helpt apparaten te beschermen tegen malware die exploits gebruikt om zichzelf te verspreiden en andere apparaten te infecteren. U gebruikt de Windows-beveiligingsapp of PowerShell om een set beperkingen te maken (dit wordt een configuratie genoemd). U kunt deze configuratie vervolgens als XML-bestand exporteren en delen met meerdere apparaten in uw netwerk, zodat ze allemaal dezelfde set beperkingsinstellingen hebben.
 
  U kunt ook een bestaand XML-bestand met een EMET-configuratie naar een XML-bestand voor exploitbeveiligingsconfiguratie converteren en importeren.

- **Exploit Protection overschrijven blokkeren**  
  [WindowsDefenderSecurityCenter/DisallowExploitProtectionOverride](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-windowsdefendersecuritycenter#windowsdefendersecuritycenter-disallowexploitprotectionoverride): kies de instelling *Ja* als u wilt voorkomen dat gebruikers wijzigingen kunnen aanbrengen in de Exploit Protection-instellingen in het Windows Defender Security Center. Als u deze instelling niet configureert of uitschakelt, kunnen lokale gebruikers wijzigingen aanbrengen in de Exploit Protection-instellingen.  
  **Standaardinstelling**: Ja  

## <a name="microsoft-defender-antivirus"></a>Micro soft Defender anti virus  

Zie [Beleids-CSP - Defender](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender) in de Windows-documentatie voor meer informatie.

- **Scripts scannen die in webbrowsers van Microsoft worden geladen**  
  [Defender/AllowScriptScanning](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowscriptscanning): ingesteld op *Ja* om het scannen van scripts door Windows Defender toe te staan.  

  **Standaardinstelling**: Ja

- **Inkomende e-mailberichten scannen**  
  [Defender/AllowEmailScanning](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowemailscanning): ingesteld op *Ja* om het scannen van e-mails door Windows Defender toe te staan.  

  **Standaardinstelling**: Ja

- **Voorbeeld van een Defender-toestemming voor indiening**  
  [Defender/SubmitSamplesConsent](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-submitsamplesconsent): hiermee wordt het gebruikerstoestemmingsniveau in Windows Defender gecontroleerd om gegevens te verzenden. Als de vereiste toestemming al is verleend, worden de gegevens door Windows Defender ingediend. Als dit niet het geval is (en als de gebruiker heeft opgegeven dat deze vraag nooit mag worden gesteld), wordt de gebruikersinterface geopend om de gebruiker om toestemming te vragen (wanneer *Cloudbeveiliging* is ingesteld op *Ja*) voordat gegevens worden verzonden.  

  **Standaardinstelling**: veilige voorbeelden automatisch verzenden

- **Netwerkinspectiesysteem (NIS)**  
  [Defender/EnableNetworkProtection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-enablenetworkprotection): hiermee wordt schadelijk verkeer geblokkeerd dat wordt gedetecteerd door handtekeningen in het netwerkinspectiesysteem (NIS).  
 
  **Standaardinstelling**: Ja

- **Interval voor handtekeningupdates (in uren)**  
  [Defender/SignatureUpdateInterval](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-signatureupdateinterval): hiermee kunt u opgeven (in uren) hoe vaak het apparaat op nieuwe updates voor Defender-handtekeningen moet controleren.  
 
  **Standaardinstelling**: 4

- **Lage CPU-prioriteit voor geplande scans configureren**  
  [Defender/EnableLowCPUPriority](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-enablelowcpupriority): bij de instelling *Ja* wordt de CPU-prioriteit voor scans op laag ingesteld. Bij *Niet geconfigureerd* worden er geen wijzigingen aangebracht in de CPU-prioriteit voor geplande scans.  

    **Standaardinstelling**: Ja

- **Defender block on access protection**  
  [Defender/AllowOnAccessProtection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowonaccessprotection): bij de instelling *Ja* wordt Windows Defender On Access Protection ingeschakeld.  

  **Standaardinstelling**: Ja

- **Type systeemscan dat moet worden uitgevoerd**  
  [Defender/ScanParameter](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-scanparameter): type Defender-scan.  

  **Standaardinstelling**: Snelle scan

- **Alle downloads scannen**  
  [Defender/AllowIOAVProtection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowioavprotection): bij de instelling *Ja* scant Defender alle gedownloade bestanden en bijlagen.  

  **Standaardinstelling**: Ja

- **Het aantal dagen voordat in quarantaine geplaatste malware wordt verwijderd**  
  [Defender/DaysToRetainCleanedMalware](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-daystoretaincleanedmalware): hiermee kunt u het aantal dagen opgeven dat items in quarantaine moeten blijven op het systeem voordat ze automatisch worden verwijderd. Als de waarde op nul wordt ingesteld, worden items in quarantaine nooit automatisch verwijderd.  

  **Standaard**: 0

- **Geplande begintijd voor het scannen**  
  [Defender/ScheduleScanTime](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-schedulescantime): hiermee kunt u een tijdstip plannen waarop Defender apparaten moet scannen. 
  
  Gerelateerde opties vindt u in deze lijst: *Defender/ScheduleScanDay*   

  **Standaardinstelling**: 02.00

- **Cloudbeveiliging**  
  [Defender/AllowCloudProtection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowcloudprotection): bij de instelling *Ja* stuurt Windows Defender gegevens naar Microsoft over eventuele gevonden problemen. Microsoft analyseert die gegevens, verzamelt meer gegevens over problemen die u en andere klanten ondervinden en biedt verbeterde oplossingen.

  Wanneer dit beleid is ingesteld op *Ja*, kunt u *Voorbeeld van een Defender-toestemmingstype voor indiening* gebruiken om gebruikers controle over het verzenden van gegevens van hun apparaat te geven.  

  **Standaardinstelling**: Ja

- **Defender: mogelijk ongewenste app-actie**  
  [Defender/PUAProtection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-puaprotection): Windows Defender Antivirus kan *mogelijk ongewenste toepassingen* identificeren en voorkomen dat ze worden gedownload en geïnstalleerd op eindpunten in uw netwerk. 
 
  - Bij de instelling *Blokkeren* blokkeert Windows Defender mogelijk ongewenste toepassingen en worden ze weergegeven in de geschiedenis, samen met andere bedreigingen.
  - Bij de instelling *Controleren* detecteert Windows Defender mogelijk ongewenste toepassingen maar blokkeert ze niet. Informatie over de toepassingen waar Windows Defender actie tegen zou ondernomen, kan worden gevonden door te zoeken naar gebeurtenissen die zijn gemaakt door Windows Defender in Logboeken.  
  - Als *Standaardwaarde voor apparaat* is ingesteld, is de beveiliging tegen mogelijk ongewenste toepassingen uitgeschakeld.  
 
  **Standaardinstelling**: Blokkeren

- **Verlengde time-out van Windows Defender-cloud**  
  [Defender/CloudExtendedTimeout](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-cloudextendedtimeout): hiermee kunt u opgeven voor hoeveel extra tijd Windows Defender Antivirus een bestand maximaal moet blokkeren terwijl u op een resultaat van de cloud wacht. De basistijd dat Windows Defender wacht, is 10 seconden. Eventuele extra tijd die u hier opgeeft (tot 50 seconden) wordt aan die 10 seconden toegevoegd. In de meeste gevallen duurt de scan korter dan de maximuminstelling. Als u de tijd verlengt, kan de cloud verdachte bestanden grondig onderzoeken.  

  De waarde voor extra tijd is standaard 0 (uitgeschakeld). Het is raadzaam voor Intune om deze instelling in te schakelen en ten minste 20 aanvullende seconden op te geven.  
 
  **Standaard**: 0

- **Archiefbestanden scannen**  
  [Defender/AllowArchiveScanning](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowarchivescanning): bij de instelling *Ja* kan Windows Defender archiefbestanden scannen.  

  **Standaardinstelling**: Ja

- **Defender-systeemscan plannen**  
  [Defender/ScheduleScanDay](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-schedulescanday): hiermee kunt u plannen op welke dag Defender apparaten moet scannen. 
 
  Gerelateerde opties vindt u in deze lijst: *Defender/ScheduleScanTime*

  **Standaardinstelling**: Door de gebruiker gedefinieerd

- **Gedragscontrole**  
  [Defender/AllowBehaviorMonitoring](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowbehaviormonitoring): bij de instelling *Ja* wordt de functionaliteit van Windows Defender-gedragscontrole ingeschakeld. De sensoren voor Windows Defender-gedragscontrole, ingesloten in Windows 10, verzamelen en verwerken gedragssignalen van het besturingssysteem en verzenden deze sensorgegevens naar uw persoonlijke, geïsoleerde cloudinstantie van Microsoft Defender ATP.  

  **Standaardinstelling**: Ja

- **Bestanden scannen die zijn geopend vanuit mappen op het netwerk**  
  [Defender/AllowScanningNetworkFiles](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowscanningnetworkfiles): bij de instelling *Ja* kan Windows Defender bestanden op het netwerk scannen. Gebruikers kunnen geen gedetecteerde malware verwijderen van alleen-lezenbestanden.  

  **Standaardinstelling**: Ja

- **Defender op cloudblokniveau**  
  [Defender/CloudBlockLevel](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-cloudblocklevel): gebruik dit beleid om te bepalen hoe agressief Windows Defender Antivirus moet zijn bij het blokkeren en scannen van verdachte bestanden. Opties zijn onder andere:

  - Hoog: onbekende bestanden agressief blokkeren tijdens het optimaliseren van clientprestaties (grotere kans op valse positieven)
  - Hoge plus: onbekende bestanden agressief blokkeren en aanvullende beveiligingsmaatregelen toepassen (heeft mogelijk invloed op clientprestaties)
  - Zero tolerance: alle onbekende uitvoerbare bestanden blokkeren

  **Standaardinstelling**: niet geconfigureerd

- **Realtimecontrole**  
  [Defender/AllowRealtimeMonitoring](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowrealtimemonitoring): bij de instelling *Ja* wordt bewaking in realtime door Windows Defender toegestaan.  

  **Standaardinstelling**: Ja

- **Limiet voor het CPU-gebruik tijdens het scannen**  
  [Defender/AvgCPULoadFactor](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-avgcpuloadfactor): hiermee kunt u het maximale gemiddelde CPU-gebruikspercentage opgeven dat Windows Defender tijdens een scan kan gebruiken.  

  **Standaardinstelling**: 50

- **Toegewezen netwerkschijven scannen tijdens een volledige scan**  
  [Defender/AllowFullScanOnMappedNetworkDrives](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowfullscanonmappednetworkdrives): bij de instelling *Ja* kan Windows Defender bestanden op het netwerk scannen. Gebruikers kunnen geen gedetecteerde malware verwijderen van alleen-lezenbestanden.

  Gerelateerde instellingen vindt u in deze lijst: *Defender/AllowScanningNetworkFiles*

  **Standaardinstelling**: Ja

- **Toegang van eindgebruikers tot Defender blokkeren**  
  [Defender/AllowUserUIAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowuseruiaccess): bij de instelling *Ja* wordt voorkomen dat eindgebruikers toegang hebben tot de gebruikersinterface van Windows Defender op hun apparaat.  

  **Standaardinstelling**: Ja

- **Starttijd snelle scan**  
  [Defender/ScheduleQuickScanTime](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-schedulequickscantime): hiermee kunt u een tijdstip plannen waarop Defender een snelle scan moet uitvoeren.  

  **Standaardinstelling**: 02.00

## <a name="windows-defender-firewall"></a>Windows Defender Firewall
Raadpleeg [Firewall CSP](https://docs.microsoft.com/windows/client-management/mdm/firewall-csp) in de Windows-documentatie voor meer informatie.

- **Niet-actieve tijd voordat beveiligingskoppeling wordt verwijderd** - *MdmStore/Global/SaIdleTime*   
  Beveiligingskoppelingen worden verwijderd nadat gedurende het opgegeven aantal seconden geen netwerkverkeer wordt gedetecteerd.  
  **Standaardinstelling**: 300

- **File Transfer Protocol** - *MdmStore/Global/DisableStatefulFtp*   
  Hiermee wordt een stateful File Transfer Protocol (FTP) geblokkeerd.  
  **Standaardinstelling**: Ja

- **Pakketten in wachtrij plaatsen** - *MdmStore/Global/EnablePacketQueue*    
  Hiermee kunt u opgeven hoe schalen voor software aan de ontvangstzijde wordt ingeschakeld voor versleuteld ontvangen en ongecodeerd doorsturen in het scenario voor de IPsec-tunnelgateway. Hierdoor wordt gegarandeerd dat de pakketvolgorde behouden blijft.  
  **Standaardinstelling**: standaardinstelling van apparaat

- **Firewall-profieldomein** - *FirewallRules/FirewallRuleName/Profiles*  
  Hiermee geeft u de profielen op waartoe de regel behoort: Domein, Privé of Openbaar. Deze waarde vertegenwoordigt het profiel voor netwerken die zijn verbonden met domeinen.  

  Beschikbare instellingen:  
  - **Unicast-antwoorden voor multicast-broadcasts vereist**  
    **Standaardinstelling**: Ja

  - **Regels voor gemachtigde toepassingen van groepsbeleid samengevoegd**  
    **Standaardinstelling**: Ja

  - **Binnenkomende meldingen geblokkeerd**  
    **Standaardinstelling**: Ja

  - **Globale poortregels van groepsbeleid samengevoegd**  
    **Standaardinstelling**: Ja

  - **Verborgen modus geblokkeerd**  
    **Standaardinstelling**: Ja

  - **Firewall ingeschakeld**  
    **Standaardinstelling**: Toegestaan

  - **Beveiligingsregels voor verbindingen van groepsbeleid niet samengevoegd**  
    **Standaardinstelling**: Ja

  - **Beleidsregels van groepsbeleid niet samengevoegd**  
    **Standaardinstelling**: Ja

- **Firewall-profiel openbaar** - *FirewallRules/FirewallRuleName/Profiles*  
  Hiermee geeft u de profielen op waartoe de regel behoort: Domein, Privé of Openbaar. Deze waarde vertegenwoordigt het profiel voor openbare netwerken. Deze netwerken wordt als openbaar geclassificeerd door de beheerders in de serverhost. De classificatie vindt plaats de eerste keer dat de host verbinding maakt met het netwerk. Deze netwerken bevinden zich meestal op luchthavens, in cafés en in andere openbare ruimten waar de peers in het netwerk of de netwerkbeheerder niet worden vertrouwd.  

  Beschikbare instellingen:

  - **Geblokkeerde binnenkomende verbindingen**  
    **Standaardinstelling**: Ja 

  - **Unicast-antwoorden voor multicast-broadcasts vereist**  
    **Standaardinstelling**: Ja  

  - **Verborgen modus vereist**  
    **Standaardinstelling**: Ja 
 
  - **Uitgaande verbindingen vereist**  
    **Standaardinstelling**: Ja  

  - **Regels voor gemachtigde toepassingen van groepsbeleid samengevoegd**  
    **Standaardinstelling**: Ja  

  - **Binnenkomende meldingen geblokkeerd**  
    **Standaardinstelling**: Ja  

  - **Globale poortregels van groepsbeleid samengevoegd**  
    **Standaardinstelling**: Ja

  - **Verborgen modus geblokkeerd**  
    **Standaardinstelling**: Ja

  - **Firewall ingeschakeld**  
    **Standaardinstelling**: Toegestaan  

  - **Beveiligingsregels voor verbindingen van groepsbeleid niet samengevoegd**  
    **Standaardinstelling**: Ja  

  - **Inkomend verkeer vereist**  
    **Standaardinstelling**: Ja

  - **Beleidsregels van groepsbeleid niet samengevoegd**  
    **Standaardinstelling**: Ja  

- **Firewall-profiel privé** - *FirewallRules/FirewallRuleName/Profiles*  
  Hiermee geeft u de profielen op waartoe de regel behoort: Domein, Privé of Openbaar. Deze waarde vertegenwoordigt het profiel voor privénetwerken.  

  Beschikbare instellingen: 

  - **Geblokkeerde binnenkomende verbindingen**  
    **Standaardinstelling**: Ja

  - **Unicast-antwoorden voor multicast-broadcasts vereist**  
    **Standaardinstelling**: Ja

  - **Verborgen modus vereist**  
    **Standaardinstelling**: Ja

  - **Uitgaande verbindingen vereist**  
    **Standaardinstelling**: Ja

  - **Binnenkomende meldingen geblokkeerd**  
    **Standaardinstelling**: Ja

  - **Globale poortregels van groepsbeleid samengevoegd**  
    **Standaardinstelling**: Ja

  - **Verborgen modus geblokkeerd**  
    **Standaardinstelling**: Ja  

  - **Firewall ingeschakeld**  
    **Standaardinstelling**: Toegestaan

  - **Regels voor gemachtigde toepassingen van groepsbeleid niet samengevoegd**  
    **Standaardinstelling**: Ja

  - **Beveiligingsregels voor verbindingen van groepsbeleid niet samengevoegd**  
    **Standaardinstelling**: Ja

  - **Inkomend verkeer vereist**  
    **Standaardinstelling**: Ja

  - **Beleidsregels van groepsbeleid niet samengevoegd**  
    **Standaardinstelling**: Ja  

- **Firewall-coderingsmethode voor vooraf gedeelde sleutel**  
  **Standaardinstelling**: UTF8

- **Controle van certificaatintrekkingslijsten**  
  **Standaardinstelling**: standaardinstelling van apparaat

## <a name="web--network-protection"></a>Web- en netwerkbeveiliging  

- **Netwerkbeveiligingstype**  
  [Defender/EnableNetworkProtection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-enablenetworkprotection): met dit beleid kunt u netwerkbeveiliging in- of uitschakelen in Windows Defender Exploit Guard. Netwerkbeveiliging is een functie van Windows Defender Exploit Guard die voorkomt dat werknemers die apps gebruiken in contact komen met phishing-praktijken, sites die misbruik maken en schadelijke inhoud op internet. Dit omvat het voorkomen dat browsers van derden verbinding maken met gevaarlijke websites.  

  Wanneer de functie is ingesteld op *Inschakelen* of *Controlemodus*, kunnen gebruikers netwerkbeveiliging niet uitschakelen en kunt u Windows Defender Security Center gebruiken om informatie over verbindingspogingen weer te geven.  
 
  - Met *Inschakelen* wordt voorkomen dat gebruikers en apps verbinding kunnen maken met gevaarlijke domeinen.  
  - Met *Controlemodus* wordt niet voorkomen dat gebruikers en apps verbinding kunnen maken met gevaarlijke domeinen.  

  Met de instelling *Door de gebruiker gedefinieerd* wordt niet voorkomen dat gebruikers en apps verbinding kunnen maken met gevaarlijke domeinen en is er geen informatie over verbindingen beschikbaar in Windows Defender Security Center.  

  **Standaardinstelling**: Controlemodus

- **SmartScreen vereisen voor Microsoft Edge**  
  [Browser/AllowSmartScreen](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-allowsmartscreen): Microsoft Edge gebruikt standaard Windows Defender SmartScreen (ingeschakeld) om gebruikers tegen mogelijke oplichting door phishing en schadelijke software te beschermen. Dit beleid is standaard ingeschakeld (ingesteld op *Ja*). Wanneer het is ingeschakeld, wordt voorkomen dat gebruikers Windows Defender SmartScreen kunnen uitschakelen.  Wanneer het effectieve beleid voor een apparaat gelijk is aan Niet geconfigureerd, kunnen gebruikers Windows Defender SmartScreen uitschakelen, waardoor het apparaat niet meer beveiligd is.  

  **Standaardinstelling**: Ja
  
- **Toegang tot schadelijke sites blokkeren**  
  [Browser/PreventSmartScreenPromptOverride](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-preventsmartscreenpromptoverride): standaard hebben gebruikers in Microsoft Edge toestemming om de Windows Defender SmartScreen-waarschuwingen over mogelijke schadelijke websites te omzeilen (negeren), zodat de gebruikers de site kunnen blijven gebruiken. Als dit beleid is ingeschakeld (ingesteld op *Ja*) voorkomt Microsoft Edge dat gebruikers de waarschuwingen kunnen omzeilen, waardoor ze de website dus niet langer kunnen gebruiken.  

  **Standaardinstelling**: Ja

- **Downloaden van niet-geverifieerde bestanden blokkeren**  
  [Browser/PreventSmartScreenPromptOverrideForFiles](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-preventsmartscreenpromptoverrideforfiles): standaard hebben gebruikers in Microsoft Edge toestemming om de Windows Defender SmartScreen-waarschuwingen over mogelijk schadelijke bestanden te omzeilen (negeren), waardoor ze niet-geverifieerde bestanden kunnen blijven downloaden. Als dit beleid is ingeschakeld (ingesteld op *Ja*), kunnen gebruikers de waarschuwingen niet negeren en kunnen ze geen niet-geverifieerde bestanden downloaden.  

  **Standaardinstelling**: Ja

## <a name="windows-hello-for-business"></a>Windows Hello voor Bedrijven  

Raadpleeg [PassportForWork CSP](https://docs.microsoft.com/windows/client-management/mdm/passportforwork-csp) in de Windows-documentatie voor meer informatie.

- **Windows Hello voor Bedrijven configureren** - *TenantId/beleid/UsePassportForWork*    
  Windows Hello voor Bedrijven is een alternatieve aanmeldmethode voor Windows die wachtwoorden, smartcards en virtuele smartcards vervangt.  

  - Wanneer deze optie is ingesteld op *Ja*, schakelt u dit beleid in en wordt Windows hello voor bedrijven door het apparaat ingericht.  
  - Als deze optie is ingesteld op *niet geconfigureerd*, is de basis lijn niet van invloed op de beleids instelling van het apparaat. Dit betekent dat als Windows hello voor bedrijven is uitgeschakeld op een apparaat, het uitgeschakeld blijft. Als de functie is ingeschakeld, blijft deze ingeschakeld. 

  U kunt Windows hello voor bedrijven niet uitschakelen via deze basis lijn. U kunt Windows hello voor bedrijven uitschakelen wanneer u [Windows-inschrijving](windows-hello.md)configureert of als onderdeel van een configuratie profiel voor [identiteits beveiliging](identity-protection-configure.md).  

Windows Hello voor Bedrijven is een alternatieve aanmeldmethode voor Windows die wachtwoorden, smartcards en virtuele smartcards vervangt.  

  Als u deze beleidsinstelling inschakelt of niet configureert, richt het apparaat Windows Hello voor Bedrijven in. Als u deze beleidsinstelling uitschakelt, richt het apparaat voor geen enkele gebruiker Windows Hello voor Bedrijven in.

  Intune biedt geen ondersteuning voor het uitschakelen van Windows Hello. In plaats daarvan kunt u beleid configureren om Windows Hello voor Bedrijven in te schakelen (Ja) of Windows Hello niet rechtstreeks te configureren (Niet geconfigureerd). Als er geen beleid is geconfigureerd, kan een apparaat configuratie via een ander beleid ontvangen, dat deze functie kan in- of uitschakelen.  

  **Standaardinstelling**: Ja  

- **Kleine letters in pincode vereisen** - *TenantId/Policies/PINComplexity/LowercaseLetters*  
  **Standaardinstelling**: Toegestaan  

- **Speciale tekens in pincode vereisen** - *TenantId/Policies/PINComplexity/SpecialCharacters*  
  **Standaardinstelling**: Toegestaan  

- **Hoofdletters in pincode vereisen** - *TenantId/Policies/PINComplexity/UppercaseLetters*   
  **Standaardinstelling**: Toegestaan  

