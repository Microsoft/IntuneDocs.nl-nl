---
title: Versleutelingsrapporten en BitLocker-sleutels in Microsoft Intune
titleSuffix: Microsoft Intune
description: Bekijk een rapport over de versleutelingsstatus van uw apparaten en krijg toegang tot BitLocker-herstelsleutels via de Microsoft Intune-portal.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 06/21/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: shpate
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: b4c7e4b2d35eb2662ca74660e2133dcd2c89f0a1
ms.sourcegitcommit: 7c251948811b8b817e9fe590b77f23aed95b2d4e
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/15/2019
ms.locfileid: "67883370"
---
# <a name="monitor-bitlocker-and-device-encryption"></a>BitLocker en apparaatversleuteling bewaken  
Intune biedt een gecentraliseerde locatie om de versleutelingsstatus van uw Windows 10-apparaten te identificeren. Ook krijgt u belangrijke informatie voor BitLocker van uw apparaten van Azure Active Directory (Azure AD).  

- Het [versleutelingsrapport](#encryption-report) bevat meer informatie over de versleutelingsstatus en gereedheid van een apparaat. Aan de hand van de rapportdetails kunt u problemen identificeren die ervoor zorgen dat de apparaten die u wilt beveiligen niet goed kunnen worden versleuteld.  
- U kunt in de Intune-portal [BitLocker-details weergeven](#bitlocker-recovery-keys) zoals de sleutel-id en herstelsleutels voor uw apparaten.  

## <a name="encryption-report"></a>Versleutelingsrapport
U kunt met het versleutelingsrapport details weergeven over de versleutelingsstatus van uw Windows 10-apparaten.  

Voor het rapport meldt u zich aan bij [Intune](https://aka.ms/intuneportal). Ga naar **Apparaatconfiguratie** en selecteer vervolgens bij *Monitor* de optie **Versleutelingsrapport**.  

### <a name="prerequisites"></a>Vereisten:
Op een apparaat moet Windows-versie 1607 of hoger worden uitgevoerd om het apparaat in het versleutelingsrapport weer te geven.  

### <a name="report-details"></a>Rapportdetails
In het rapport staat de **apparaatnaam** voor uw Windows 10-apparaten en details over elk apparaat op hoog niveau, zoals:  
- **Besturingssysteemversie**: de versie van Windows.  
- **TPM-versie**: de versie van de TPM-chip (Trusted Platform Module) op het apparaat.  
- **Gereedheid voor versleuteling**: met deze functie controleert u of de apparaten gereed zijn om BitLocker-versleuteling te ondersteunen. Apparaten kunnen worden geïdentificeerd als:
  - **Gereed**: Het apparaat kan met behulp van MDM-beleid worden versleuteld. Hiervoor moet het apparaat over een TMP beschikken en aan de volgende Windows 10-versie en SKU-vereisten voldoen:
    - Versie 1703 of hoger, van Business/Enterprise/Education
    - versie 1809 of hoger, van Pro  
  
    Zie de [BitLocker CSP (configuratieserviceprovider)](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp) in de Windows-documentatie voor meer informatie.  

  - **Niet gereed**: Het apparaat beschikt niet over alle versleutelingsmogelijkheden, maar kan nog wel worden versleuteld. Het apparaat kan bijvoorbeeld handmatig door een gebruiker worden versleuteld of door een groepsbeleid dat zodanig kan worden ingesteld dat versleuteling mogelijk is zonder een TMP.
  - **Niet van toepassing**: Er is onvoldoende informatie beschikbaar om dit apparaat te classificeren.  

- **Versleutelingsstatus**: deze optie geeft aan of de besturingssysteemschijf is versleuteld. 


### <a name="device-encryption-status"></a>Status apparaatversleuteling
Wanneer u een apparaat selecteert, wordt in Intune het deelvenster **Status apparaatversleuteling** weergegeven.

In dit deelvenster worden de volgende details weergegeven:  
- **Apparaatnaam**: de naam van het apparaat dat wordt weergegeven.  
- **Gereedheid voor versleuteling**: met deze functie controleert u of de apparaten gereed zijn om BitLocker-versleuteling te ondersteunen. Ook als de gereedheid voor versleuteling van een apparaat *Niet gereed* is, kan de versleutelingsstatus van dit apparaat *Versleuteld* zijn, omdat er geen TPM is. (Zie Gereedheid voor versleuteling in het vorige gedeelte voor meer informatie.)
- **Versleutelingsstatus**: deze optie geeft aan of de besturingssysteemschijf is versleuteld. Het kan tot 24 uur duren voordat Intune de versleutelingsstatus van apparaten of een wijziging in deze status rapporteert.  
- **Profielen**: een lijst met de profielen voor *Apparaatconfiguratie* die op dit apparaat van toepassing zijn, inclusief de volgende profieltypen en instellingen:  
  - Profieltype = *Endpoint Protection*  
  - Instellingen > Windows-versleuteling > Apparaten versleutelen = *Vereist*  

  U kunt deze lijst gebruiken om afzonderlijke beleidsregels te zoeken om te beoordelen, wanneer in de samenvatting van de profielstatus problemen worden aangeduid.  

- **Samenvatting van de profielstatus**: een samenvatting van de profielen die op dit apparaat van toepassing zijn. De samenvatting staat voor de minst gunstige voorwaarde voor alle profielen die van toepassing zijn. Als één profiel bijvoorbeeld tot een Fout leidt, wordt *Fout* in de samenvatting van de profielstatus weergegeven.  
- **Statusdetails**: geavanceerde details over de versleutelingsstatus van het apparaat. 
  > [!NOTE]  
  > Intune toont alleen de *Statusdetails* voor apparaten waarop de *Windows 10-update van april 2019* of hoger wordt uitgevoerd.
  
  In dit veld staat informatie voor elke toepasselijke fout die kan worden gedetecteerd. Aan de hand van deze informatie kunt u achterhalen waarom een apparaat mogelijk niet gereed is voor versleuteling.  

  Hieronder volgt een aantal voorbeelden van de statusdetails die in een Intune-rapport kunnen staan:  

  - Volgens het BitLocker-beleid moeten gebruikers toestemming geven om de wizard BitLocker-stationsversleuteling te starten om het besturingssysteemvolume te versleutelen, maar de gebruiker heeft geen toestemming gegeven.  
  - De versleutelingsmethode van het besturingssysteemvolume komt niet overeen met het BitLocker-beleid.  
  - Volgens het BitLocker-beleid moet TPM-beveiliging worden gebruikt om het besturingssysteemvolume te beveiligen, maar er is geen TPM gebruikt.  
  - Volgens het BitLocker-beleid moet alleen TPM-beveiliging worden gebruikt om het besturingssysteemvolume te beveiligen, maar er is geen TPM-beveiliging gebruikt.  
  - Volgens het BitLocker-beleid moet TPM- en pincodebeveiliging worden gebruikt om het besturingssysteemvolume te beveiligen, maar er is geen TPM- en pincodebeveiliging gebruikt.  
  - Volgens het BitLocker-beleid moet TPM- en opstartsleutelbeveiliging worden gebruikt om het besturingssysteemvolume te beveiligen, maar er is geen TPM- en opstartsleutelbeveiliging gebruikt.  
  - Volgens het BitLocker-beleid moet TPM-, pincode- en opstartsleutelbeveiliging worden gebruikt om het besturingssysteemvolume te beveiligen, maar er is geen TPM-, pincode- en opstartsleutelbeveiliging gebruikt.  
  - Het besturingssysteemvolume is niet beveiligd.  
  - Back-up van herstelsleutel is mislukt.  
  - Een vaste schijf is niet beveiligd.  
  - De versleutelingsmethode van de vaste schijf komt niet overeen met het BitLocker-beleid.  
  - Als u schijven wilt versleutelen, moeten gebruikers zich volgens het BitLocker-beleid aanmelden als beheerder, of het AllowStandardUserEncryption-beleid moet zijn ingesteld op 1 als het apparaat met Azure AD wordt samengevoegd.  
  - Windows Recovery Environment (WinRE) is niet geconfigureerd.  
  - Er is geen TPM beschikbaar voor BitLocker. Dit komt omdat er geen TPM aanwezig is, er geen TPM in het register is of het besturingssysteem zich op een verwisselbaar station bevindt.  
  - De TPM is niet gereed voor BitLocker.  
  - Het netwerk is niet beschikbaar, maar wel vereist voor back-ups van herstelsleutels.  

## <a name="bitlocker-recovery-keys"></a>BitLocker-herstelsleutels
Intune biedt toegang tot de Azure AD-blade voor BitLocker, zodat u via de Intune-portal BitLocker-sleutel-id's en herstelsleutels voor uw Windows 10-apparaten kunt weergeven.  Een apparaat is alleen toegankelijk als de sleutels van dat apparaat naar Azure AD worden geborgd. 
1. Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973), ga naar **Apparaten** en selecteer onder *Beheren* de optie **Alle apparaten**.
2. Selecteer een apparaat in de lijst en selecteer vervolgens onder *Monitor* **Herstelsleutels**.  
  
Als er sleutels in Azure AD beschikbaar zijn, is de volgende informatie beschikbaar:
- BitLocker-sleutel-id
- BitLocker-herstelsleutel
- Type station  

Als er geen sleutels aanwezig zijn in Azure AD, wordt *Er is geen BitLocker-sleutel gevonden voor dit apparaat* weergegeven.  

De informatie voor BitLocker wordt verkregen met behulp van de [BitLocker-configuratieserviceprovider](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp) (CSP). BitLocker CSP wordt ondersteund op Windows 10-versie 1703 en hoger en voor Windows 10 Pro-versie 1809 en hoger. 

## <a name="next-steps"></a>Volgende stappen
Maak een beleid voor [apparaatcompliantie](compliance-policy-create-windows.md) voor Windows 10-apparaten om BitLocker en versleuteling te configureren.
