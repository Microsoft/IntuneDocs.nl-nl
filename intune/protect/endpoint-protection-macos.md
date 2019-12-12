---
title: Endpoint Protection in macOS toevoegen in Microsoft Intune - Azure | Microsoft Docs
description: Gebruik Gatekeeper op macOS-apparaten om te bepalen waar apps kunnen worden geïnstalleerd, inclusief de Mac App Store. Schakel met Microsoft Intune ook een firewall in of configureer een firewall die bepaalde apps toestaat, bepaalde apps blokkeert, de verborgen modus gebruikt en zelfs bepaalde typen binnenkomende verbindingen blokkeert.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/02/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 358a396e762f1f20051abadfc2f3df80f37ca8c8
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 12/05/2019
ms.locfileid: "72502296"
---
# <a name="macos-endpoint-protection-settings-in-intune"></a>Instellingen in Intune voor eindpuntbescherming in macOS  

In dit artikel komt u meer te weten over de eindpuntbeschermingsinstellingen die u kunt configureren voor apparaten waarop macOS wordt uitgevoerd. U kunt deze instellingen configureren met behulp van een configuratie profiel voor macOS-apparaten voor [Endpoint Protection](endpoint-protection-configure.md) in intune.  

## <a name="gatekeeper"></a>Gatekeeper  

- **Apps die vanaf deze locaties worden gedownload, toestaan**  
  Beperk de apps die een apparaat kan starten, afhankelijk van waar de apps zijn gedownload. Het doel hiervan is om de apparaten te beschermen tegen malware en alleen apps toe te staan van bronnen die u vertrouwt.  

  - **Niet geconfigureerd**  
  - **Mac App Store**  
  - **Mac App Store en geïdentificeerde ontwikkelaars**  
  - **Overal**  

  **Standaard**: niet geconfigureerd  

- **Gebruiker kan gate keeper overschrijven**  
  Hiermee voorkomt u dat gebruikers de Gatekeeper-instelling kunnen overschrijven en voorkomt u dat ze op Control kunnen klikken om een app te installeren. Wanneer dit is ingeschakeld, kunnen gebruikers op Control klikken om een app te installeren.  
 
  - **Niet geconfigureerd** : gebruikers kunnen Control-klikken om apps te installeren.  
  - **Blok keren** : hiermee voor komt u dat gebruikers met Control-Click apps kunnen installeren.  

  **Standaard**: niet geconfigureerd  

## <a name="firewall"></a>Firewall  

Gebruik de firewall om verbindingen per toepassing te beheren, in plaats van per poort. Met de instellingen per toepassing kunt u beter profiteren van de voordelen van firewallbeveiliging. Bovendien helpt het te voorkomen dat ongewenste apps gebruikmaken van netwerkpoorten die zijn geopend voor legitieme apps.  

**Algemeen**
- **Firewall**  
  Schakel de firewall in om te configureren hoe binnenkomende verbindingen in uw omgeving worden verwerkt.  
  - **Niet geconfigureerd**  
  - **Inschakelen**  

  **Standaard**: niet geconfigureerd  

- **Binnenkomende verbindingen**  
  Hiermee blokkeert u alle binnenkomende verbindingen, behalve de verbindingen die vereist zijn voor basisinternetservices, zoals DHCP, Bonjour en IPSec. Hiermee worden ook alle services voor delen (zoals delen van bestanden en delen van het scherm) geblokkeerd. Als u services voor delen gebruikt, moet u *Niet geconfigureerd* gebruiken.  
  - **Niet geconfigureerd**  
  - **Blokkeren**  

  **Standaard**: niet geconfigureerd  

**Binnenkomende verbindingen voor specifieke apps blokkeren of toestaan.**  

  - **Apps toegestaan**  
    Selecteer de apps die expliciet zijn toegestaan voor het ontvangen van binnenkomende verbindingen.  

  - **Geblokkeerde apps**  
    Selecteer de apps die binnenkomende verbindingen moeten blokkeren.  

  - **Verborgen modus**  
    Schakel deze optie in om te voorkomen dat de computer reageert op peilverzoeken. Het apparaat reageert nog wel op binnenkomende verzoeken voor toegestane apps. Onverwachte aanvragen, zoals ICMP (ping), worden genegeerd.  
    - **Niet geconfigureerd**  
    - **Inschakelen**  

    **Standaard**: niet geconfigureerd  

## <a name="filevault"></a>FileVault  
Zie [FDEFileVault](https://developer.apple.com/documentation/devicemanagement/fdefilevault) in de inhoud van Apple Developer voor meer informatie over de Apple FileVault-instellingen. 

> [!IMPORTANT]  
> Vanaf macOS 10,15 is door de FileVault-configuratie een door de gebruiker goedgekeurde MDM-inschrijving vereist. 

- **FileVault**  
  U kunt de volledige schijf versleuteling *inschakelen* met behulp van XTS-AES 128 met FileVault op apparaten waarop macOS 10,13 of hoger wordt uitgevoerd.  
  - **Niet geconfigureerd**  
  - **Inschakelen**  

  **Standaard**: niet geconfigureerd  

  - **Type herstel sleutel**  
    Sleutels voor herstel van *persoonlijke sleutels* worden gemaakt voor apparaten. Configureer de volgende instellingen voor de persoonlijke sleutel.  

    - **Locatie van persoonlijke herstel sleutel** : Geef een kort bericht voor de gebruiker op waarin wordt uitgelegd hoe en waar ze hun persoonlijke herstel sleutel kunnen ophalen. Deze tekst wordt ingevoegd in het bericht dat de gebruiker op het aanmeld scherm ziet wanneer u wordt gevraagd hun persoonlijke herstel sleutel in te voeren als een wacht woord is verg eten.  
      
    - **Draaiing van persoonlijke herstel sleutel** : Geef op hoe vaak de persoonlijke herstel sleutel voor een apparaat wordt gedraaid. U kunt de standaard instelling **niet geconfigureerd**of een waarde van **1** tot **12** maanden selecteren.  

  - **Prompt uitschakelen bij afmelden**  
    Voor komen dat de gebruiker wordt gevraagd om FileVault in te scha kelen wanneer deze zich afmeldt.  Wanneer u deze optie inschakelt, wordt de prompt bij het afmelden uitgeschakeld en wordt de gebruiker gevraagd om zich aan te melden.  
    - **Niet geconfigureerd**  
    - **Schakel** de prompt bij het afmelden uit.

    **Standaard**: niet geconfigureerd  

  - **Aantal keren dat mag worden omzeild**  
  Stel het aantal keren in dat een gebruiker prompts kan negeren om FileVault in te scha kelen voordat FileVault is vereist om zich aan te melden. 

    - **Niet geconfigureerd** : versleuteling op het apparaat is vereist voordat de volgende aanmelding is toegestaan.  
    - **1** tot **10** : Hiermee staat u een gebruiker toe de prompt te negeren van 1 tot 10 keer voordat versleuteling op het apparaat is vereist.  
    - **Geen limiet, altijd vragen** : de gebruiker wordt gevraagd om FileVault in te scha kelen, maar versleuteling is nooit vereist.  
 
    **Standaard**: is *afhankelijk* *van het uitschakelen van de instelling prompt bij afmelden* is ingesteld op **niet geconfigureerd**, wordt de standaard instelling **niet geconfigureerd**. Als de optie voor het *uitschakelen van de prompt bij afmelden* is ingesteld op **uitschakelen**, wordt standaard de instelling **1** gebruikt en is de waarde **niet geconfigureerd** .

Zie [FileVault Recovery Keys](encryption-monitor.md#filevault-recovery-keys)(Engelstalig) voor meer informatie over FileVault met intune.

