---
title: Tips voor het oplossen van problemen met BitLocker-beleid in Microsoft Intune
titleSuffix: Microsoft Intune
description: Hierin wordt beschreven hoe u BitLocker-versleuteling inschakelt op een apparaat met behulp van intune-beleid en hoe u kunt controleren of uw beleid op een apparaat is geïmplementeerd.
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/02/2019
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 744277b0e49a4e3ca8b0fa3bac43c666110bb8a3
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 12/05/2019
ms.locfileid: "74410348"
---
# <a name="troubleshoot-bitlocker-policies-in-microsoft-intune"></a>Problemen met BitLocker-beleid in Microsoft Intune oplossen

Dit artikel kan intune-beheerders helpen begrijpen hoe Windows 10-apparaten BitLocker configureren op basis van intune-beleid. Dit artikel bevat ook richt lijnen voor het oplossen van problemen met BitLocker-instellingen op apparaten die u beheert met intune.  

## <a name="understanding-bitlocker"></a>Informatie over BitLocker

BitLocker-stationsversleuteling is een service die wordt aangeboden door micro soft Windows-besturings systemen, waarmee gebruikers gegevens op hun harde schijven kunnen versleutelen. BitLocker ondersteunt versleuteling voor stations van het besturings systeem, verwissel bare media stations en harde schijven. BitLocker biedt ook ondersteuning voor het gebruik van 256-bits versleuteling voor betere beveiliging van gevoelige gegevens.  

Met Microsoft Intune hebt u de volgende methoden voor het beheren van BitLocker op Windows 10-apparaten:

- **Configuratie beleid voor apparaten** : bepaalde ingebouwde beleids opties zijn beschikbaar in intune wanneer u een configuratie profiel voor een apparaat maakt om Endpoint Protection te beheren. Als u deze opties wilt vinden, [maakt u een apparaatprofiel voor Endpoint Protection](endpoint-protection-configure.md#create-a-device-profile-containing-endpoint-protection-settings), selecteert u **Windows 10 en hoger** voor het *platform*en selecteert u vervolgens de **Windows-versleutelings** categorie voor *instellingen*. 

   U vindt hier meer informatie over de beschik bare opties en functies: [Windows-versleuteling](https://docs.microsoft.com/intune/endpoint-protection-windows-10#windows-encryption).

- **Beveiligings basislijnen** - [beveiligings basislijnen](security-baselines.md) zijn bekende groepen instellingen en standaard waarden die worden aanbevolen door het relevante beveiligings team om Windows-apparaten te beveiligen. Verschillende basislijn bronnen, zoals de *MDM-beveiligings basislijn* of de *micro soft Defender ATP-basis lijn* , kunnen dezelfde instellingen beheren als andere instellingen dan beide. Ze kunnen ook dezelfde instellingen beheren die u beheert met configuratie beleid voor apparaten. 

Naast intune is het mogelijk dat BitLocker-instellingen worden beheerd op een andere manier, zoals groepsbeleid, of hand matig worden ingesteld door een gebruiker van een apparaat.

Ongeacht hoe instellingen worden toegepast op een apparaat, BitLocker-beleid maakt gebruik van de [BitLocker CSP](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp) voor het configureren van versleuteling op het apparaat. De BitLocker CSP is ingebouwd in Windows en wanneer intune een BitLocker-beleid implementeert op een toegewezen apparaat, is het de BitLocker CSP op het apparaat dat de juiste waarden naar het Windows-REGI ster schrijft, zodat de instellingen van het beleid van kracht kunnen worden.

Raadpleeg de volgende bronnen voor meer informatie over BitLocker:

- [BitLocker](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview)
- [Veelgestelde vragen over BitLocker-overzicht en-vereisten](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview-and-requirements-faq)

Nu u een algemeen overzicht hebt van wat dit beleid doet en hoe ze werken, kijkt u hoe u kunt controleren of de BitLocker-instellingen zijn toegepast op een Windows-client.

## <a name="verify-the-source-of-bitlocker-settings"></a>De bron van BitLocker-instellingen controleren

Wanneer u een BitLocker-probleem op een Windows 10-apparaat onderzoekt, is het belang rijk om eerst te bepalen of het probleem betrekking heeft op intune of Windows. Nadat de mogelijke bron van de fout bekend is, kunt u zich op de juiste plek richten op de probleem oplossing en zo nodig ondersteuning verkrijgen van het juiste team.  

Bepaal als eerste stap of het intune-beleid is geïmplementeerd op het doel apparaat. In het volgende voor beeld hebt u een configuratie beleid voor apparaten waarmee de BitLocker-instellingen (Windows Encryption) worden geïmplementeerd, zoals wordt weer gegeven:

![Beleid voor Windows-versleutelings apparaatconfiguratie met de instellingen](./media/troubleshooting-bitlocker-policies/settings.png)

Hoe bevestigt u dat de instellingen zijn toegepast op het doel apparaat? Hier volgen enkele manieren waarop u dit kunt doen.

### <a name="device-configuration-policy-device-status"></a>Apparaatstatus van het configuratie beleid voor apparaten  

Wanneer u het configuratie beleid voor apparaten gebruikt om BitLocker te configureren, kunt u de status van het beleid in de intune-Portal controleren.

1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Selecteer **apparaten** > **configuratie profielen** en selecteer vervolgens het profiel dat BitLocker-instellingen bevat.

3. Nadat u het profiel dat u wilt weer geven hebt geselecteerd, selecteert u **Apparaatstatus**. Apparaten die aan het profiel zijn toegewezen, worden weer gegeven en de kolom *Apparaatstatus* geeft aan of het profiel door een apparaat is geïmplementeerd.

Houd er rekening mee dat er een vertraging kan optreden tussen een apparaat dat een BitLocker-beleid ontvangt en het station is volledig versleuteld.  

### <a name="use-control-panel-on-the-client"></a>Het configuratie scherm gebruiken op de client  

Op een apparaat waarop BitLocker is ingeschakeld en een station is versleuteld, kunt u de status van BitLocker bekijken via het configuratie scherm van apparaten. Open **configuratie scherm** op het apparaat > **systeem-en beveiligings** > **BitLocker-stationsversleuteling**. Bevestiging wordt weer gegeven zoals in de volgende afbeelding.  

![BitLocker is ingeschakeld in het configuratie scherm](./media/troubleshooting-bitlocker-policies/control-panel.png)

### <a name="use-a-command-prompt"></a>Een opdrachtprompt gebruiken  

Op een apparaat waarop BitLocker is ingeschakeld en een station is versleuteld, start u de opdracht prompt met beheerders referenties en voert u vervolgens `manage-bde -status`uit. De resultaten moeten eruitzien als in het volgende voor beeld:  
![resultaat van de opdracht status](./media/troubleshooting-bitlocker-policies/command.png)

In het voor beeld:

- **BitLocker-beveiliging** is **ingeschakeld**
- **Percentage versleuteld** is **100%**
- De **versleutelings methode** is **XTS-AES 256**

U kunt ook **sleutel beveiligingen** controleren door de volgende opdracht uit te voeren:

```cmd
Manage-bde -protectors -get c:
```

Of met PowerShell:

```powershell
Confirm-SecureBootUEFI
```

### <a name="review-the-devices-registry-key-configuration"></a>De configuratie van de register sleutel voor apparaten controleren

Nadat het BitLocker-beleid op een apparaat is geïmplementeerd, bekijkt u de volgende register sleutel op het apparaat, waar u de configuratie van BitLocker-instellingen kunt controleren: *HKEY_LOCAL_MACHINE \software\microsoft\policymanager\current\device\bitlocker*. Hier volgt een voorbeeld:

![BitLocker-register sleutel](./media/troubleshooting-bitlocker-policies/registry.png)

Deze waarden worden geconfigureerd door de BitLocker CSP. Controleer of de waarden van de sleutels overeenkomen met de instellingen die zijn opgegeven in de bron van uw intune-versleutelings beleid voor Windows. Zie [BitLocker CSP](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp)voor meer informatie over elk van deze instellingen.

> [!NOTE]
> De Windows Logboeken bevat ook diverse informatie met betrekking tot BitLocker. Er zijn hier te veel om weer te geven, maar door te zoeken naar de **BitLocker API** krijgt u veel nuttige informatie.

### <a name="check-the-mdm-diagnostics-report"></a>Het MDM-diagnose rapport controleren

Op een apparaat waarop BitLocker is ingeschakeld, kunt u een MDM-diagnose rapport genereren en weer geven vanaf het doel apparaat om te bevestigen dat het BitLocker-beleid aanwezig is. Als u de beleids instellingen in het rapport kunt zien, is het een andere indicatie dat het beleid is geïmplementeerd. In de video van *micro soft* wordt uitgelegd hoe u een MDM-diagnose rapport kunt vastleggen vanaf een Windows-apparaat.

> [!VIDEO https://www.youtube.com/embed/WKxlcjV4TNE]

Wanneer u het rapport met het MDM-diagnose programma analyseert, kan de inhoud op het eerste gezicht enigszins verwarrend zijn. Hieronder ziet u een voor beeld waarin wordt uitgelegd hoe u met de instellingen in een beleid kunt correleren wat er in het rapport gebeurt:

![Rapport voor het MDM-diagnose programma](./media/troubleshooting-bitlocker-policies/report.png)

In het resultaat van de uitvoer ziet u de waarden die overeenkomen met de waarden van uw BitLocker-beleid:

![Resultaat van uitvoer toont de waarden ](./media/troubleshooting-bitlocker-policies/output.png)

Uitvoer resultaten van MDM-diagnose:

```asciidoc
EncryptionMethodWithXtsOsDropDown: 7 (The value 7 refers to the 256 bit encryption)
EncryptionMethodWithXtsFdvDropDown: 6 (The value 6 refers to the 128 bit encryption)
EncryptionMethodWithXtsRdvDropDown: 6 (The value 6 refers to the 128 bit encryption)
```

U kunt naar de [BitLocker CSP-documentatie](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp) verwijzen om te zien wat elke waarde betekent. In dit voor beeld wordt een fragment gedeeld in de volgende afbeelding.

![Doel van waarden](./media/troubleshooting-bitlocker-policies/shared-example.png)

Op dezelfde manier kunt u alle waarden bekijken en controleren via de BitLocker CSP-koppeling.

> [!TIP]
> Het belangrijkste doel van het MDM-diagnose rapport is om Microsoft Ondersteuning te helpen bij het oplossen van problemen. Als u een ondersteunings aanvraag voor intune opent en het probleem betrekking heeft op Windows-clients, is het altijd een goed idee om dit rapport te verzamelen en op te halen in uw ondersteunings aanvraag.

## <a name="troubleshooting-bitlocker-policy"></a>Problemen met BitLocker-beleid oplossen

U hebt nu een goed idee hoe u kunt controleren of het BitLocker-beleid door intune is geïmplementeerd, waardoor de configuratie van BitLocker wordt doorgevoerd in de BitLocker CSP in WIndows.

**Het beleid is niet bereikbaar voor het apparaat** -wanneer uw intune-beleid niet aanwezig is in een capaciteit:

- **Is het apparaat goed ingeschreven bij Microsoft Intune?** Als dat niet het geval is, moet u eerst een adres kiezen voordat u alle specifieke informatie voor het beleid opvraagt. Meer informatie over het oplossen van problemen met Windows-inschrijving vindt u [hier](../enrollment/troubleshoot-windows-enrollment-errors.md).

- **Heeft het apparaat een actieve netwerkverbinding?** Als het apparaat zich in de vliegtuig modus bevindt of is uitgeschakeld, of als de gebruiker het apparaat op een locatie zonder service heeft, wordt het beleid niet bezorgd of toegepast totdat de netwerk verbinding is hersteld.

- **Is het BitLocker-beleid geïmplementeerd voor de juiste gebruiker of Apparaatgroep?** Controleer of de juiste gebruiker of apparaat lid is van de groepen die u doel.

Het **beleid is aanwezig, maar niet alle instellingen zijn geconfigureerd** . Wanneer uw intune-beleid het apparaat bereikt, maar niet alle configuraties zijn ingesteld:

- **Mislukt de implementatie van het volledige beleid of zijn er alleen bepaalde instellingen die niet van toepassing zijn?** Als u een scenario hebt gevonden waarin slechts enkele beleids instellingen niet van toepassing zijn, controleert u de volgende overwegingen:

  1. **Niet alle BitLocker-instellingen worden ondersteund op alle Windows-versies**.
     Het beleid wordt als één eenheid naar een apparaat verzonden, dus als sommige instellingen van toepassing zijn en andere niet, kunt u erop vertrouwen dat het beleid zelf wordt ontvangen. In dit scenario is het mogelijk dat de Windows-versie op het apparaat niet de problematische instellingen ondersteunt. Zie [BitLocker CSP](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp) in de Windows-documentatie voor meer informatie over de versie vereisten voor elke instelling.

  2. **BitLocker wordt niet op alle hardware ondersteund**.
     Zelfs als u de juiste versie van Windows hebt, is het mogelijk dat de onderliggende hardware niet voldoet aan de vereisten voor BitLocker-versleuteling. De [systeem vereisten voor BitLocker](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview#system-requirements) vindt u in de Windows-documentatie, maar de belangrijkste te controleren taken zijn dat het apparaat een compatibele TPM-chip heeft (1,2 of hoger) en een BIOS-of UEFI-firmware die compatibel is met Trusted Computing Group (TCG).

**Voorbeeldonderzoek**

- U implementeert een BitLocker-beleid op een Windows 10-apparaat en de instelling **apparaten versleutelen** toont de status **fout** in de portal.

- Zoals de naam suggereert, kan een beheerder vereisen dat versleuteling is ingeschakeld met behulp van *BitLocker > apparaatversleuteling*. Op basis van de tips voor probleem oplossing die eerder werden beschreven, controleert u eerst het MDM-rapport voor controle. In het rapport wordt bevestigd dat het juiste beleid op het apparaat is geïmplementeerd:

  ![Rapport bevestigt dat het juiste beleid is geïmplementeerd op het apparaat](./media/troubleshooting-bitlocker-policies/mdm-report.png)

- U controleert ook de geslaagde pogingen in het REGI ster:

  ![In de register waarde RequiredDeviceEncryption wordt 1 weer gegeven](./media/troubleshooting-bitlocker-policies/registry-confirm.png)

- Vervolgens controleert u de status van TPM met behulp van Power shell en vindt u dat TPM niet beschikbaar is op het apparaat:

  ![TPM-status gecontroleerd met behulp van Power shell](./media/troubleshooting-bitlocker-policies/tpm-command.png)

- Omdat BitLocker afhankelijk is van TPM, kunt u concluderen dat BitLocker niet mislukt vanwege een probleem met intune of het beleid, maar in plaats daarvan omdat het apparaat zelf geen TPM-chip heeft of als TPM niet is ingeschakeld in het BIOS.

  Als extra tip kunt u hetzelfde controleren in het Windows-Logboeken onder **toepassingen en services-logboek** > **Windows** > **BitLocker API**. In het gebeurtenis logboek van **BitLocker-API** vindt u een gebeurtenis-ID van 853, wat betekent dat TPM niet beschikbaar is:

  ![Gebeurtenis-id 853](./media/troubleshooting-bitlocker-policies/event-error.png)

  > [!NOTE]
  > U kunt ook de TPM-status controleren door **TPM. msc** op het apparaat uit te voeren.

## <a name="summary"></a>Samenvatting

Wanneer u problemen met BitLocker-beleid met intune oplost en kunt bevestigen dat beleid het beoogde apparaat bereikt, is het veilig om aan te nemen dat het probleem niet rechtstreeks verband houdt met intune. Het probleem is waarschijnlijk een probleem met het Windows-besturings systeem of de hardware. In dit geval gaat u naar andere gebieden, zoals de TPM-configuratie of UEFI en beveiligd opstarten.

## <a name="next-steps"></a>Volgende stappen  

Hieronder vindt u meer bronnen die u kunnen helpen bij het werken met BitLocker:

- [BitLocker-product documentatie](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview)
- [BitLocker-systeem vereisten](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview#system-requirements)
- [BitLocker: veelgestelde vragen](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-frequently-asked-questions)
- [BitLocker CSP-documentatie](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp)
- [Instellingen voor Windows-versleutelings beleid van intune](https://docs.microsoft.com/intune/endpoint-protection-windows-10#windows-encryption)
- [Hardwarematig onafhankelijke automatische BitLocker-versleuteling met AAD/MDM](https://blogs.technet.microsoft.com/home_is_where_i_lay_my_head/2017/06/07/hardware-independent-automatic-bitlocker-encryption-using-aadmdm/)
- [CSP-beleid voor BitLocker-versleuteling op automatische pilot-apparaten](https://techcommunity.microsoft.com/t5/Windows-10-security/CSP-policy-for-bitLocker-encryption-on-autopilot-devices/m-p/284537)
- [Instructies voor het maken en implementeren van BitLocker-beleid met intune](https://blogs.technet.microsoft.com/cbernier/2017/07/11/windows-10-intune-windows-bitlocker-management-yes/)