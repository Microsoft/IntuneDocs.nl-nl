---
title: Instellingen voor Endpoint Protection configureren in Microsoft Intune - Azure | Microsoft Docs
description: Instellingen voor Endpoint Protection in Microsoft Intune maken wanneer u een profiel voor een macOS- of Windows 10-apparaat maakt.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 09/19/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
mr.reviewer: karthib
ms.openlocfilehash: f8923f3c4e1610be2501dccbd3ac551b9c994c24
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/02/2019
ms.locfileid: "71721432"
---
# <a name="add-endpoint-protection-settings-in-intune"></a>Instellingen voor Endpoint Protection toevoegen in Intune  

Met Intune kunt u configuratieprofielen voor apparaten gebruiken voor het beheren van algemene beveiligingsfuncties voor eindpunten op apparaten, waaronder:  
- Firewall   
- BitLocker  
- Apps toestaan en blokkeren  
- Windows Defender en versleuteling  

U kunt bijvoorbeeld een Endpoint Protection-profiel maken waarmee macOS-gebruikers alleen apps uit de Mac App Store kunnen installeren. Of u kunt Windows SmartScreen inschakelen bij het uitvoeren van apps op Windows 10-apparaten.  

Lees voordat u een profiel maakt de volgende artikelen door, zodat u precies weet welke instellingen voor de bescherming van eindpunten Intune kan beheren voor elk ondersteund platform:  
   - [macOS-instellingen](endpoint-protection-macos.md)  
   - [Windows 10-instellingen](endpoint-protection-windows-10.md)  

## <a name="create-a-device-profile-containing-endpoint-protection-settings"></a>Een apparaatprofiel met instellingen voor Endpoint Protection maken  

1. Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).  
3. Selecteer **Apparaatconfiguratie** > **Profielen** > **Profiel maken**.  
4. Geef een **naam** en **beschrijving** op voor het Endpoint Protection-profiel.  
5. Selecteer in de vervolgkeuzelijst **Platform** het apparaatplatform waarop u de aangepaste instellingen wilt toepassen. Op dit moment kunt u een van de volgende platformen kiezen voor apparaatbeperkingsinstellingen:  
   - **macOS**  
   - **Windows 10 en hoger**  
6. Kies **Endpoint Protection** in de vervolgkeuzelijst **Profieltype**.  
7. Welke instellingen u kunt configureren, is afhankelijk van het platform dat u hebt gekozen. Zie:  
   - [macOS-instellingen](endpoint-protection-macos.md)  
   - [Windows 10-instellingen](endpoint-protection-windows-10.md)  

8. Nadat u de gewenste instellingen hebt geconfigureerd, selecteert u **Maken** op de pagina **Profiel maken**.  

   Het profiel wordt gemaakt en wordt weergegeven op de pagina met de profielenlijst. Zie [Apparaatprofielen toewijzen](../configuration/device-profile-assign.md) om dit profiel toe te wijzen aan groepen.  

## <a name="add-custom-firewall-rules-for-windows-10-devices"></a>Aangepaste firewallregels toevoegen voor Windows 10-apparaten  

Als u de Windows Defender Firewall configureert als onderdeel van een profiel met Endpoint Protection-regels voor Windows 10, kunt u aangepaste regels configureren voor firewalls. Met aangepaste regels kunt u de vooraf gedefinieerde set firewallregels die worden ondersteund voor Windows 10 uitbreiden.  

Als u van plan bent profielen met aangepaste firewallregels te gebruiken, moet u rekening houden met de volgende informatie; deze kan van invloed kan zijn op de manier waarop u firewallregels in uw profielen groepeert:  
- Elk profiel ondersteunt maximaal 150 firewallregels. Als u meer dan 150 regels gebruikt, maakt u extra profielen met elk een maximum van 150 regels.  
- Als één regel niet kan worden toegepast in een profiel, mislukt het uitvoeren van álle regels. Er wordt dan dus geen enkele regel toegepast op het apparaat.  
- Als een regel niet kan worden toegepast, wordt van alle regels in het profiel gerapporteerd dat ze zijn mislukt. Intune kan niet identificeren welke specifieke regel dan is mislukt.  

De firewallregels die door Intune kunnen worden beheerd, worden beschreven in de Windows [Firewall]( https://docs.microsoft.com/windows/client-management/mdm/firewall-csp)-configuratieprovider (CSP). Zie [Aangepaste firewallregels](endpoint-protection-windows-10.md#firewall-rules) voor een overzicht van de aangepaste-firewallinstellingen voor Windows 10-apparaten die door Intune worden ondersteund.  

### <a name="to-add-custom-firewall-rules-to-an-endpoint-protection-profile"></a>Aangepaste firewallregels toevoegen aan een Endpoint Protection-profiel  

1. Ga in Intune naar **Apparaatconfiguratie** > **Profielen** > **Profiel maken**.  

2. Bij *Platform* selecteert u **Windows 10 en hoger** en bij *Profieltype* selecteert u **Endpoint Protection**.  

3. Selecteer **Windows Defender Firewall** om de configuratiepagina te openen en selecteer bij *Firewallregels* de optie **Toevoegen** om de pagina **Regel maken** te openen.  

4. Geef instellingen voor de firewallregel op en selecteer **OK** om deze op te slaan. Zie [Aangepaste firewallregels](endpoint-protection-windows-10.md#firewall-rules)om de beschikbare opties voor aangepaste firewallregels te bekijken in de documentatie.  

5. Als u de regel hebt opgeslagen, wordt deze weergegeven op de pagina *Windows Defender Firewall*, in de lijst met regels.  

6. Als u een regel wilt wijzigen, selecteert u de regel in de lijst. De pagina **Regel bewerken** wordt dan geopend.  

7. Als u een regel uit een profiel wilt verwijderen, selecteert u het beletselteken **(...)** bij de regel. Selecteer vervolgens **Verwijderen**.  

8. Als u de volgorde wilt wijzigen waarin de regels worden weergegeven, selecteert u het pictogram *pijl-omhoog en pijl-omlaag* bovenaan de lijst met regels.  


## <a name="next-steps"></a>Volgende stappen  

Zie [Apparaatprofielen toewijzen](../configuration/device-profile-assign.md) om een profiel toe te wijzen aan groepen.  
