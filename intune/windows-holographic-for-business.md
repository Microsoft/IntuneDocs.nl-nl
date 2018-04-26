---
title: Windows Holographic-apparaten beheren met Microsoft Intune - Azure | Microsoft Docs
description: Met Microsoft Intune kunt u verschillende taken uitvoeren op apparaten met Windows Holographic for Business, zoals de bedrijfsportal configureren, een nalevingsbeleid maken, OMA-URI-instellingen wijzigen, apps implementeren, apparaten in groepen categoriseren, profielen maken, apparaten beperken, software-updates inschakelen, voorwaarden instellen, VPN- en Wi-Fi-instellingen configureren en Hello voor Bedrijven gebruiken.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 4/5/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 41c1ea3bf12b83a0f09c8535275ffb58e5f46931
ms.sourcegitcommit: b727b6bd6f138c5def7ac7bf1658068db30a0ec3
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/06/2018
---
# <a name="customize-devices-running-windows-holographic-with-intune"></a>Apparaten met Windows Holographic wijzigen met Microsoft Intune

Microsoft Intune biedt ondersteuning voor apparaten met  Windows Holographic for Business, zoals de [Microsoft HoloLens](https://docs.microsoft.com/en-us/hololens/).

Voor het beheer van apparaten met Windows Holographic met Microsoft Intune moet u een Edition Upgrade-profiel maken. Met dit upgradeprofiel werkt u de apparaten bij van Windows Holographic naar Windows Holographic for Business. Voor Microsoft HoloLens kunt u de Commercial Suite aanschaffen om de vereiste licentie voor de upgrade op te halen. Zie [Apparaten met Windows Holographic upgraden naar Windows Holographic for Business](holographic-upgrade.md) voor meer informatie.

Gebruik de taken in dit artikel om uw apparaten met Windows Holographic for Business te beheren en te wijzigen. U kunt bijvoorbeeld software-updates beheren en VPN-instellingen configureren.

## <a name="company-portal"></a>Bedrijfsportal
**[De bedrijfsportal-app configureren](company-portal-app.md)**

Intune bevat de bedrijfsportal, waar gebruikers toegang hebben tot bedrijfsgegevens, apparaten inschrijven, apps installeren, contact opnemen met uw IT-afdeling en meer. U kunt de bedrijfsportal-app aanpassen voor uw apparaten met Windows Holographic for Business.

## <a name="compliance-policy"></a>Nalevingsbeleid
**[Een nalevingsbeleid voor apparaten maken](compliance-policy-create-windows.md)**

Nalevingsbeleid zijn regels en instellingen waaraan apparaten moeten voldoen om compatibel te zijn. U kunt deze beleidsregels met voorwaardelijke toegang gebruiken om toegang tot bedrijfsresources te blokkeren voor apparaten die niet compatibel zijn. U kunt in Intune beleidsregels maken om toegang voor apparaten met Windows Holographic for Business toe te staan of te blokkeren. U kunt bijvoorbeeld een beleid maken waarvoor Bitlocker moet zijn ingeschakeld.

Zie ook **[Aan de slag met nalevingsbeleid](device-compliance-get-started.md)**.

## <a name="deploy-apps"></a>Apps implementeren
**[Apps toevoegen aan Intune](apps-add.md)**

Met Intune kunt u apps toevoegen aan uw apparaten met Windows Holographic for Business. Apps kunnen op verschillende manieren worden geïmplementeerd. Voorbeelden hiervan zijn:

- [Microsoft Store-apps toevoegen](store-apps-windows.md)
- [Apps toevoegen die u maakt](lob-apps-windows.md)
- [Apps aan groepen toewijzen](apps-deploy.md)

## <a name="device-categories-and-groups"></a>Apparaatcategorieën en -groepen
**[Apparaten categoriseren in groepen](device-group-mapping.md)**

Met Intune kunt u apparaatcategorieën maken om apparaten automatisch toe te voegen aan groepen op basis van categorieën die u instelt, zoals Verkoop, Boekhouding, Human Resources, enzovoort. Het idee is om het beheer van uw apparaten met Windows Holographic for Business te vereenvoudigen.

## <a name="device-configuration-profiles"></a>Apparaatconfiguratieprofielen 
**[Aan de slag met configuratieprofielen](device-profiles.md) en [uw eigen profiel maken](device-profile-create.md)**

Intune omvat instellingen en functies die u op verschillende apparaten binnen uw organisatie kunt in- of uitschakelen. Deze instellingen en functies worden beheerd met behulp van profielen. U kunt bijvoorbeeld een profiel maken waarmee Cortana wordt ingeschakeld, of een profiel dat Windows Defender Smart Screen gebruikt op uw apparaten met Windows Holographic for Business.

U kunt OMA-URI in uw profielen gebruiken om een aantal instellingen aan te passen, apparaatbeperkingen in te stellen en een virtueel particulier netwerk (VPN) en Wi-Fi te configureren.

#### <a name="custom-device-settingscustom-settings-windows-holographicmd"></a>[Aangepaste apparaatinstellingen](custom-settings-windows-holographic.md)

Als u instellingen voor OMA-URI (Open Mobile Alliance Uniform Resource Identifier) wilt configureren, kunt u een aangepast profiel maken in Intune. Met de OMA-URI-instellingen kunt u verschillende functies beheren op uw apparaten met Windows Holographic for Business, zoals VPN inschakelen of controleren op updates van Microsoft Update.

#### <a name="device-restrictionsdevice-restrictions-windows-holographicmd"></a>[Apparaatbeperkingen](device-restrictions-windows-holographic.md)

Met apparaatbeperkingen kunt u verschillende instellingen en functies op uw apparaten beheren, zoals een wachtwoord vereisen, apps installeren apps uit de [Microsoft Store](https://www.microsoft.com/store/apps/windows?icid=CNavAppsWindowsApps), Bluetooth inschakelen en meer. Deze beperkingen worden gemaakt in een Intune-profiel. Dit profiel kan worden toegepast op meerdere apparaten met Windows Holographic for Business.

#### <a name="configure-vpnvpn-settings-configuremd"></a>[VPN configureren](vpn-settings-configure.md)

Met virtuele particuliere netwerken (VPN's) geeft u uw gebruikers veilige externe toegang tot uw bedrijfsnetwerk. U kunt in Intune een VPN-profiel maken met specifieke instellingen voor uw apparaten met Windows Holographic for Business. U kunt bijvoorbeeld een VPN-profiel maken zodat alle apparaten met Windows Holographic for Business Citrix-VPN gebruiken als verbindingstype.

#### <a name="configure-wi-fiwi-fi-settings-configuremd"></a>[Wi-Fi configureren](wi-fi-settings-configure.md)

U kunt in Intune ook een Wi-Fi-profiel maken om draadloze netwerkinstellingen toe te wijzen aan apparaten met Windows Holographic for Business. Als u een Wi-Fi-profiel toewijst, krijgen uw eindgebruikers zonder netwerkconfiguratie toegang tot het bedrijfsnetwerk. U kunt bijvoorbeeld een Wi-Fi-netwerk uitsluitend voor apparaten met Windows Holographic for Business maken.

## <a name="software-updates"></a>Software-updates
**[Software-updates beheren](windows-update-for-business-configure.md)**

Intune heeft de functie update-ringen voor Windows 10-apparaten. Deze update-ringen bevatten een groep instellingen waarmee u bepaalt hoe updates worden geïnstalleerd. U kunt bijvoorbeeld een onderhoudsvenster maken om updates te installeren of instellen dat opnieuw moet worden opgestart nadat updates zijn geïnstalleerd. De update-ring kan worden toegepast op meerdere apparaten met Windows Holographic for Business.

## <a name="terms-and-conditions"></a>Voorwaarden
**[De voorwaarden voor gebruikerstoegang van uw bedrijf instellen](terms-and-conditions-create.md)**

Voordat gebruikers apparaten kunnen registreren en toegang hebben tot uw bedrijfsapps, waaronder e-mail, kunt u vereisen dat gebruikers de voorwaarden van uw bedrijf accepteren. U kunt in Intune definiëren hoe de voorwaarden worden weergegeven in de bedrijfsportal en deze voorwaarden ook toewijzen aan apparaten met Windows Holographic for Business.

## <a name="windows-hello-for-business"></a>Windows Hello voor Bedrijven
**[Windows Hello voor Bedrijven gebruiken](windows-hello.md)**

Hello voor Bedrijven biedt een alternatieve aanmeldingsmethode waarbij een Azure Active Directory-account wordt gebruikt om een wachtwoord, smartcard of virtuele smartcard te vervangen. Met Hello voor Bedrijven kunnen apparaten met Windows Holographic for Business zich aanmelden met een pincode met een door u ingestelde minimale lengte.
