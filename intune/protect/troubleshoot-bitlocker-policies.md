---
title: Tips voor het oplossen van problemen met BitLocker-beleid in Microsoft Intune
titleSuffix: Microsoft Intune
description: Hierin wordt beschreven hoe u BitLocker-versleuteling inschakelt op een apparaat met behulp van Intune-beleid en hoe u kunt controleren of uw beleid is geïmplementeerd op een apparaat.
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 01/29/2020
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
ms.openlocfilehash: f3b32268d0b04dee84a737b9a1c768bc4fab7202
ms.sourcegitcommit: 3964e6697b4d43e2c69a15e97c8d16f8c838645b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/21/2020
ms.locfileid: "77556496"
---
# <a name="troubleshoot-bitlocker-policies-in-microsoft-intune"></a>Problemen met BitLocker-beleid in Microsoft Intune oplossen

Dit artikel biedt Intune-beheerders inzicht in hoe BitLocker wordt geconfigureerd op Windows 10-apparaten op basis van Intune-beleid. Dit artikel bevat ook richtlijnen voor het oplossen van problemen met BitLocker-instellingen op apparaten die u beheert met Intune.  

## <a name="understanding-bitlocker"></a>Informatie over BitLocker

BitLocker-stationsversleuteling is een service die wordt aangeboden in Microsoft Windows-besturingssystemen waarmee gebruikers gegevens op hun harde schijven kunnen versleutelen. BitLocker ondersteunt versleuteling voor besturingssysteemstations, verwisselbare mediastations en vaste gegevensstations. BitLocker biedt ook ondersteuning voor het gebruik van 256 bitsversleuteling voor betere beveiliging van gevoelige gegevens.  

Met Microsoft Intune beschikt u over de volgende methoden om BitLocker te beheren op Windows 10-apparaten:

- **Beleidsregels voor apparaatconfiruatie**: bepaalde ingebouwde beleidsopties zijn beschikbaar in Intune wanneer u een apparaatconfiguratieprofiel maakt om Endpoint Protection te beheren. U kunt deze opties vinden door [een apparaatprofiel voor Endpoint Protection](endpoint-protection-configure.md#create-a-device-profile-containing-endpoint-protection-settings) te maken, **Windows 10 en later** te selecteren bij *Platform* en vervolgens de categorie **Windows-versleuteling** te selecteren bij *Instellingen*. 

   Zie dit artikel voor de beschikbare opties en functies: [Windows-versleuteling](https://docs.microsoft.com/intune/endpoint-protection-windows-10#windows-encryption).

- **Beveiligingsbasislijnen** - [Beveiligingsbasislijnen](security-baselines.md) zijn bekende groepen instellingen en standaardwaarden die door het relevante beveiligingsteam worden aanbevolen om Windows-apparaten te beveiligen. Met verschillende basislijnbronnen, zoals de *MDM-beveiligingsbasislijn* of de *Microsoft Defender ATP-basislijn*, kunt u dezelfde of andere instellingen beheren. U kunt er ook dezelfde instellingen mee beheren als met apparaatconfiguratiebeleid. 

Naast Intune wordt, voor hardware die compatibel is met Modern Standby-en HSTI, BitLocker-apparaatversleuteling automatisch ingeschakeld wanneer de gebruiker een apparaat aan Azure AD koppelt. Azure AD biedt een portal waar ook een back-up van de herstelsleutels wordt gemaakt, zodat gebruikers zo nodig hun eigen herstelsleutel voor selfservice kunnen ophalen.

BitLocker-instellingen kunnen ook op andere manieren worden beheerd, zoals met groepsbeleid, of handmatig worden ingesteld door een apparaatgebruiker.

Ongeacht hoe instellingen worden toegepast op een apparaat, BitLocker-beleid maakt gebruik van de [BitLocker CSP](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp) om versleuteling op het apparaat te configureren. De BitLocker CSP is ingebouwd in Windows. Wanneer via Intune een BitLocker-beleidsregel wordt geïmplementeerd op een toegewezen apparaat, worden de juiste waarden door de BitLocker CSP op het apparaat in het Windows-register geschreven zodat de beleidsinstellingen van kracht kunnen worden.

Raadpleeg de volgende resources voor meer informatie over BitLocker:

- [BitLocker](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview)
- [Overzicht van BitLocker en veelgestelde vragen over vereisten](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview-and-requirements-faq)

Nu u basisinzicht hebt in de functie en werking van deze beleidsregels gaan we kijken hoe u kunt controleren of de BitLocker-instellingen zijn toegepast op een Windows-client.

## <a name="verify-the-source-of-bitlocker-settings"></a>De bron van BitLocker-instellingen controleren

Wanneer u een BitLocker-probleem op een Windows 10-apparaat onderzoekt, is het belangrijk om eerst te bepalen of het probleem betrekking heeft op Intune of Windows. Als de mogelijke bron van de fout bekend is, kunt u uw inspanningen om het probleem op te lossen richten op het juiste gebied en zo nodig ondersteuning verkrijgen van het juiste team.  

Bepaal als eerste stap of het Intune-beleid is geïmplementeerd op het doelapparaat. In het volgende voorbeeld hebt u apparaatconfiguratiebeleid waarmee de instellingen van Windows-versleuteling (BitLocker) worden geïmplementeerd, zoals hier wordt weergegeven:

![Apparaatconfiguratiebeleid voor Windows-versleuteling met de instellingen](./media/troubleshooting-bitlocker-policies/settings.png)

Hoe controleert u of de instellingen zijn toegepast op het doelapparaat? Hier volgen enkele manieren waarop u dit kunt doen.

### <a name="device-configuration-policy-device-status"></a>Apparaatstatus van het apparaatconfiguratiebeleid  

Wanneer u het apparaatconfiguratiebeleid gebruikt om BitLocker te configureren, kunt u de status van het beleid controleren in de Intune-portal.

1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Selecteer **Apparaten** > **Configuratieprofielen** en selecteer vervolgens het profiel dat BitLocker-instellingen bevat.

3. Na selectie van het profiel dat u wilt weergeven selecteert u **Apparaatstatus**. Apparaten die aan het profiel zijn toegewezen, worden weergegeven en de kolom *Apparaatstatus* geeft aan of het profiel is geïmplementeerd op een apparaat.

Houd er rekening mee dat er een vertraging kan optreden tussen het moment waarop een apparaat BitLocker-beleid ontvangt en waarop het station volledig is versleuteld.  

### <a name="use-control-panel-on-the-client"></a>Het configuratiescherm op de client gebruiken  

Op een apparaat waarop BitLocker is ingeschakeld en een station is versleuteld, kunt u de BitLocker-status bekijken via het Configuratiescherm van apparaten. Open op het apparaat **Configuratiescherm** > **Systeem en beveiliging** > **BitLocker-stationsversleuteling**. Er wordt een bevestiging weergegeven, zoals te zien is in de volgende afbeelding.  

![BitLocker is ingeschakeld in het Configuratiescherm](./media/troubleshooting-bitlocker-policies/control-panel.png)

### <a name="use-a-command-prompt"></a>Een opdrachtprompt gebruiken  

Op een apparaat waarop BitLocker is ingeschakeld en een station is versleuteld, start u de opdrachtprompt met beheerdersreferenties en voert u vervolgens `manage-bde -status` uit. De resultaten moeten eruitzien zoals in het volgende voorbeeld:  
![Een resultaat van de statusopdracht](./media/troubleshooting-bitlocker-policies/command.png)

In het voorbeeld:

- **BitLocker-beveiliging** is **Ingeschakeld**
- **Percentage versleuteld** is **100%**
- De **Versleutelingsmethode** is **XTS-AES 256**

U kunt ook **Sleutelbeveiligingen** controleren door de volgende opdracht uit te voeren:

```cmd
Manage-bde -protectors -get c:
```

Of met PowerShell:

```powershell
Confirm-SecureBootUEFI
```

### <a name="review-the-devices-registry-key-configuration"></a>De configuratie van de registersleutel voor apparaten controleren

Nadat BitLocker-beleid op een apparaat is geïmplementeerd, bekijkt u de volgende registersleutel op het apparaat, waar u de configuratie van BitLocker-instellingen kunt controleren:  *HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\PolicyManager\current\device\BitLocker*. Hier volgt een voorbeeld:

![BitLocker-registersleutel](./media/troubleshooting-bitlocker-policies/registry.png)

Deze waarden worden geconfigureerd door de BitLocker CSP. Controleer of de waarden van de sleutels overeenkomen met de instellingen die zijn opgegeven in de bron van uw Intune-versleutelingsbeleid voor Windows. Zie [BitLocker CSP](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp)voor meer informatie over elk van deze instellingen.

> [!NOTE]
> De Logboeken van Windows bevatten ook diverse informatie met betrekking tot BitLocker. Er is te veel om hier weer te geven, maar als u zoekt naar **BitLocker API** krijgt u veel nuttige informatie.

### <a name="check-the-mdm-diagnostics-report"></a>Het MDM-diagnoserapport controleren

Op een apparaat waarop BitLocker is ingeschakeld, kunt u een MDM-diagnoserapport genereren en bekijken vanaf het doelapparaat om te controleren of het BitLocker-beleid aanwezig is. Als u de beleidsinstellingen in het rapport kunt zien, is dat nog een indicatie dat het beleid is geïmplementeerd. In de video *Microsoft helpt* wordt uitgelegd hoe u een MDM-diagnoserapport kunt vastleggen vanaf een Windows-apparaat.

> [!VIDEO https://www.youtube.com/embed/WKxlcjV4TNE]

Wanneer u het MDM-diagnoserapport analyseert, kan de inhoud aanvankelijk een beetje verwarrend lijken. Hieronder ziet u een voorbeeld waarin wordt uitgelegd hoe de rapportinhoud zich verhoudt tot de beleidsinstellingen:

![Voorbeeld van een MDM-diagnoserapport](./media/troubleshooting-bitlocker-policies/report.png)

In de uitvoerresultaten ziet u de waarden die overeenkomen met de waarden van uw BitLocker-beleid:

![De waarden in het uitvoerresultaat ](./media/troubleshooting-bitlocker-policies/output.png)

Uitvoerresultaten van MDM-diagnose:

```asciidoc
EncryptionMethodWithXtsOsDropDown: 7 (The value 7 refers to the 256 bit encryption)
EncryptionMethodWithXtsFdvDropDown: 6 (The value 6 refers to the 128 bit encryption)
EncryptionMethodWithXtsRdvDropDown: 6 (The value 6 refers to the 128 bit encryption)
```

U kunt de [BitLocker CSP-documentatie](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp) raadplegen om te zien wat elke waarde betekent. Voor dit voorbeeld wordt een fragment gedeeld in de volgende afbeelding.

![Doelen van waarden](./media/troubleshooting-bitlocker-policies/shared-example.png)

Op dezelfde manier kunt u alle waarden bekijken en deze controleren via de BitLocker CSP-koppeling.

> [!TIP]
> Het belangrijkste doel van het MDM-diagnoserapport is om Microsoft Ondersteuning te helpen bij het oplossen van problemen. Als u een ondersteuningsaanvraag voor Intune opent en het probleem betrekking heeft op Windows-clients, is het altijd verstandig om dit rapport te verzamelen en op te nemen in uw ondersteuningsaanvraag.

## <a name="troubleshooting-bitlocker-policy"></a>Problemen met BitLocker-beleid oplossen

Nu weet u hoe u kunt controleren of het BitLocker-beleid via Intune is geïmplementeerd, waarna BitLocker wordt geconfigureerd in de BitLocker CSP in Windows.

**Het beleid bereikt het apparaat niet**: wanneer uw Intune-beleid niet aanwezig is in een capaciteit:

- **Is het apparaat goed ingeschreven bij Microsoft Intune?** Als dat niet het geval is, moet u dat probleem eerst oplossen voordat u specifieke fouten met het beleid oplost. Meer informatie over het oplossen van problemen met Windows-inschrijving vindt u [hier](../enrollment/troubleshoot-windows-enrollment-errors.md).

- **Heeft het apparaat een actieve netwerkverbinding?** Als het apparaat zich in de vliegtuigmodus bevindt of is uitgeschakeld, of als het apparaat zich op een locatie zonder service bevindt, wordt het beleid pas geleverd of toegepast als de netwerkverbinding is hersteld.

- **Is het BitLocker-beleid geïmplementeerd voor de juiste gebruikers- of apparaatgroep?** Controleer of de juiste gebruiker of het juiste apparaat lid is van de groepen waarop u zicht richt.

**Het beleid is aanwezig, maar niet alle instellingen zijn geconfigureerd**: wanneer uw Intune-beleid het apparaat heeft bereikt, maar niet alle configuraties zijn ingesteld:

- **Mislukt de implementatie van het volledige beleid of zijn alleen bepaalde instellingen niet toegepast?** In een scenario waarin slechts enkele beleidsinstellingen niet zijn toegepast, controleert u de volgende mogelijkheden:

  1. **Niet alle BitLocker-instellingen worden ondersteund in alle Windows-versies**.
     Het beleid wordt als één eenheid naar een apparaat verzonden. Als sommige instellingen dus wel van toepassing zijn en andere niet, kunt u erop vertrouwen dat het beleid zelf is ontvangen. In dit scenario is het mogelijk dat de Windows-versie op het apparaat de problematische instellingen niet ondersteunt. Zie [BitLocker CSP](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp) in de Windows-documentatie voor meer informatie over de versievereisten voor elke instelling.

  2. **BitLocker wordt niet op alle hardware ondersteund**.
     Ook als u de juiste versie van Windows hebt, is het mogelijk dat de onderliggende apparaathardware niet voldoet aan de vereisten voor BitLocker-versleuteling. De [systeemvereisten voor BitLocker](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview#system-requirements) vindt u in de Windows-documentatie, maar het belangrijkste is om te controleren of het apparaat een compatibele TPM-chip heeft (1.2 of later) en TCB-compatibele (Trusted Computing Group) BIOS- of UEFI-firmware.
     
**BitLocker-versleuteling wordt niet op de achtergrond uitgevoerd**: u hebt een Endpoint Protection-beleid geconfigureerd waarbij de instelling voor een waarschuwing voor andere schijfversleuteling is ingesteld op blokkeren en de wizard voor versleuteling nog steeds wordt weergegeven:

- **Controleren of de Windows-versie ondersteuning biedt voor stille versleuteling** Hiervoor is versie 1803 of hoger vereist. Als de gebruiker geen beheerder op het apparaat is, is versie 1809 of hoger vereist. In versie 1809 is ook ondersteuning toegevoegd voor apparaten waarop Modern Standby niet wordt ondersteund

**Het door BitLocker versleutelde apparaat wordt weergegeven als zijnde niet compatibel met Intune-nalevingsbeleid**: dit probleem treedt op als BitLocker-versleuteling niet is voltooid. BitLocker-versleuteling is afhankelijk van factoren zoals de schijfgrootte, het aantal bestanden en BitLocker-instellingen, en kan veel tijd in beslag nemen. Nadat de versleuteling is voltooid, wordt het apparaat weergegeven als zijnde compatibel. Apparaten kunnen ook tijdelijk niet-compatibel worden direct na een recente installatie van Windows-updates.

**Apparaten worden versleuteld met een 128-bits algoritme terwijl het beleid is ingesteld op 256-bits**: in Windows 10 wordt een station standaard versleuteld met XTS-AES 128-bits versleuteling. Zie deze handleiding voor het [instellen van 256-bits versleuteling voor BitLocker tijdens Autopilot](https://techcommunity.microsoft.com/t5/intune-customer-success/setting-256-bit-encryption-for-bitlocker-during-autopilot-with/ba-p/323791#) (Engelstalig).


**Voorbeeldonderzoek**

- U implementeert BitLocker-beleid op een Windows 10-apparaat en de instelling **Apparaten versleutelen** heeft de status **Fout** in de portal.

- Zoals de naam al aangeeft, kan een beheerder met deze instelling vereisen dat versleuteling is ingeschakeld met behulp van *BitLocker > Apparaatversleuteling*. Controleer met behulp van de bovengenoemde tips voor probleemoplossing eerst het MDM-diagnoserapport. Het rapport bevestigt dat het juiste beleid op het apparaat is geïmplementeerd:

  ![Het rapport bevestigt dat het juiste beleid op het apparaat is geïmplementeerd](./media/troubleshooting-bitlocker-policies/mdm-report.png)

- Controleer de status ook in het register:

  ![De registerwaarde RequiredDeviceEncryption geeft 1 aan](./media/troubleshooting-bitlocker-policies/registry-confirm.png)

- Controleer vervolgens de status van TPM met behulp van PowerShell en ontdek dat TPM niet beschikbaar is op het apparaat:

  ![Gecontroleerde TPM-status met behulp van PowerShell](./media/troubleshooting-bitlocker-policies/tpm-command.png)

- Omdat BitLocker afhankelijk is van TPM, kunt u concluderen dat BitLocker niet mislukt vanwege een probleem met Intune of het beleid, maar omdat het apparaat zelf geen TPM-chip heeft of omdat TPM is uitgeschakeld in het BIOS.

  Als extra tip kunt u hetzelfde controleren in de Logboeken van Windows onder **Logboek van toepassingen en services** > **Microsoft** > **Windows** > **BitLocker API**. In het gebeurtenislogboek van **BitLocker-API** vindt u een gebeurtenis-id 853, wat betekent dat TPM niet beschikbaar is:

  ![Gebeurtenis-id 853](./media/troubleshooting-bitlocker-policies/event-error.png)

  > [!NOTE]
  > U kunt de TPM-status ook controleren door **tpm.msc** op het apparaat uit te voeren.

## <a name="summary"></a>Samenvatting

Wanneer u problemen met BitLocker-beleid met Intune oplost en kunt bevestigen dat beleid het beoogde apparaat heeft bereikt, kunt u veilig aannemen dat het probleem niet rechtstreeks verband houdt met Intune. De kans is groter dat het gaat om een probleem met het Windows-besturingssysteem of de hardware. In dat geval zoekt u in andere gebieden, zoals de TPM-configuratie of UEFI en beveiligd opstarten.

## <a name="next-steps"></a>Volgende stappen  

Hieronder volgen nog meer resources die u kunnen helpen als u met BitLocker werkt:

- [BitLocker-productdocumentatie](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview)
- [BitLocker-systeemvereisten](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview#system-requirements)
- [BitLocker: veelgestelde vragen](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-frequently-asked-questions)
- [BitLocker CSP-documentatie](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp)
- [Instellingen voor Intune-versleutelingsbeleid voor Windows](https://docs.microsoft.com/intune/endpoint-protection-windows-10#windows-encryption)
- [Hardwareonafhankelijke automatische BitLocker-versleuteling met behulp van AAD/MDM](https://blogs.technet.microsoft.com/home_is_where_i_lay_my_head/2017/06/07/hardware-independent-automatic-bitlocker-encryption-using-aadmdm/)
- [CSP-beleid voor BitLocker-versleuteling op Autopilot-apparaten](https://techcommunity.microsoft.com/t5/Windows-10-security/CSP-policy-for-bitLocker-encryption-on-autopilot-devices/m-p/284537)
- [Stapsgewijze instructies voor het maken en implementeren van BitLocker-beleid met Intune](https://blogs.technet.microsoft.com/cbernier/2017/07/11/windows-10-intune-windows-bitlocker-management-yes/)
