---
title: Windows Holographic-apparaten beheren met Microsoft Intune - Azure | Microsoft Docs
description: Met Microsoft Intune kunt u verschillende taken uitvoeren op apparaten met Windows Holographic for Business, zoals de bedrijfsportal configureren, een nalevingsbeleid maken, OMA-URI-instellingen wijzigen, apps implementeren, apparaten in groepen categoriseren, profielen maken, apparaten beperken, software-updates inschakelen, voorwaarden instellen, VPN- en Wi-Fi-instellingen configureren en Hello voor Bedrijven gebruiken.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 5/1/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 18f86580fc4c80fade7aeaa9678e9d8edac9a53e
ms.sourcegitcommit: b57be56524ddb5026fab94f7638dc516ed118325
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/03/2018
---
# <a name="customize-devices-running-windows-holographic-with-intune"></a>Apparaten met Windows Holographic wijzigen met Microsoft Intune

Microsoft Intune biedt ondersteuning voor apparaten met  Windows Holographic for Business, zoals de [Microsoft HoloLens](https://docs.microsoft.com/en-us/hololens/).

Voor het beheer van apparaten met Windows Holographic met Microsoft Intune moet u een Edition Upgrade-profiel maken. Met dit upgradeprofiel werkt u de apparaten bij van Windows Holographic naar Windows Holographic for Business. Voor Microsoft HoloLens kunt u de Commercial Suite aanschaffen om de vereiste licentie voor de upgrade op te halen. Zie [Apparaten met Windows Holographic upgraden naar Windows Holographic for Business](holographic-upgrade.md) voor meer informatie.

Gebruik de taken in dit artikel om uw apparaten met Windows Holographic for Business te beheren en te wijzigen. U kunt bijvoorbeeld software-updates beheren en VPN-instellingen configureren.

## <a name="azure-active-directory"></a>Azure Active Directory

Azure Active Directory (AD) is een geweldige resource voor het beheren en bedienen van uw apparaten waarop Windows Holographic voor Bedrijven wordt uitgevoerd. Met behulp van Intune en Azure AD kunt u: 

- **[Gekoppelde Azure Active Directory-apparaten instellen](https://docs.microsoft.com/azure/active-directory/device-management-azuread-joined-devices-setup)**: in Azure Active Directory (AD) kunt u uw Windows 10-apparaten voor zakelijk gebruik toevoegen, waaronder apparaten waarop Windows Holographic voor Bedrijven wordt uitgevoerd. Via deze functie kan Azure AD het apparaat beheren. Hiermee kunt u ervoor zorgen dat uw gebruikers toegang tot uw bedrijfsresources hebben vanaf apparaten die aan uw standaarden voor beveiliging en naleving voldoen.

  [Inleiding tot apparaatbeheer in Azure AD](https://docs.microsoft.com/azure/active-directory/device-management-introduction) biedt meer informatie.

- **[Bulkregistratie voor Windows-apparaten](windows-bulk-enroll.md)**: u kunt grote aantallen nieuwe Windows-apparaten toevoegen aan Azure Active Directory (AD) en Intune. Deze functie wordt bulkregistratie genoemd. Hiervoor worden inrichtingspakketten gebruikt. Deze pakketten koppelen de apparaten waarop Windows Holographic voor Bedrijven wordt uitgevoerd met uw Azure AD-tenant en registreren deze in Intune.

## <a name="company-portal"></a>Bedrijfsportal
**[De bedrijfsportal-app configureren](company-portal-app.md)**

Intune bevat de bedrijfsportal, waar gebruikers toegang hebben tot bedrijfsgegevens, apparaten inschrijven, apps installeren, contact opnemen met uw IT-afdeling en meer. U kunt de bedrijfsportal-app aanpassen voor uw apparaten met Windows Holographic for Business.

## <a name="compliance-policy"></a>Nalevingsbeleid
**[Een nalevingsbeleid voor apparaten maken](compliance-policy-create-windows.md)**

Nalevingsbeleid zijn regels en instellingen waaraan apparaten moeten voldoen om compatibel te zijn. U kunt deze beleidsregels met voorwaardelijke toegang gebruiken om toegang tot bedrijfsresources te blokkeren voor apparaten die niet compatibel zijn. U kunt in Intune beleidsregels maken om toegang voor apparaten met Windows Holographic for Business toe te staan of te blokkeren. U kunt bijvoorbeeld een beleid maken waarvoor Bitlocker moet zijn ingeschakeld.

Zie ook **[Aan de slag met nalevingsbeleid](device-compliance-get-started.md)**.

## <a name="deploy-and-manage-apps"></a>Apps implementeren en beheren
**[Apps toevoegen aan Intune](apps-add.md)**

Met Intune kunt u apps toevoegen aan uw apparaten met Windows Holographic for Business. Apps kunnen op verschillende manieren worden geïmplementeerd. Voorbeelden hiervan zijn:

- [Microsoft Store-apps toevoegen](store-apps-windows.md)
- [Apps toevoegen die u maakt](lob-apps-windows.md)
- [Apps aan groepen toewijzen](apps-deploy.md)

Microsoft Intune kan universele Windows-apps implementeren op Microsoft HoloLens-apparaten waarop Windows Holographic for Business wordt uitgevoerd. U kunt uw app-pakketten rechtstreeks uploaden in de Intune Azure Portal of implementeren vanuit de Microsoft Store voor Bedrijven. Zie de volgende onderwerpen voor meer informatie:
- Zie [Windows Line-Of-Business-apps toevoegen aan Microsoft Intune](lob-apps-windows.md) voor het implementeren van Line-of-Business-apps (LOB) met behulp van Intune Azure Portal.
- Zie [Apps die u hebt aangeschaft in Microsoft Store voor Bedrijven beheren met Microsoft Intune](windows-store-for-business.md) voor het implementeren van apps via de Microsoft Store voor Bedrijven. 
- Zie [Wat is appbeheer in Microsoft Intune?](app-management.md) voor meer informatie over het beheer van apps met Microsoft Intune.
- Zie [Apps met gemengde realiteit voor Microsoft HoloLens](https://www.microsoft.com/hololens/apps) voor meer informatie over het ontwikkelen van apps voor Microsoft HoloLens. 

> [!NOTE]
> HoloLens-apparaten met Windows 10 Holographic voor bedrijven 1607 ondersteunen geen apps met een online licentie uit de Microsoft Store voor Bedrijven. Zie [Apps installeren op HoloLens](https://docs.microsoft.com/en-us/hololens/hololens-install-apps) voor meer informatie.

## <a name="device-actions"></a>Apparaatacties
In Intune worden een aantal ingebouwde acties gebruikt waarmee IT-beheerders verschillende taken kunnen uitvoeren. Dit kan lokaal op het apparaat maar ook extern met behulp van Intune in Azure Portal. Gebruikers kunnen ook vanuit de Intune-bedrijfsportal op afstand een opdracht geven voor persoonlijke apparaten die bij Intune zijn ingeschreven.

De volgende acties kunnen worden gebruikt wanneer u apparaten gebruikt waarop Windows Holographic voor Bedrijven wordt uitgevoerd: 

- **[Fabrieksinstellingen terugzetten](devices-wipe.md#factory-reset)**: met de actie **Fabrieksinstellingen terugzetten** wordt het apparaat uit Intune verwijderd en worden de standaardfabrieksinstellingen van het apparaat hersteld. Gebruik deze actie voordat u het apparaat aan een nieuwe gebruiker geeft of wanneer het apparaat is verloren of gestolen.

- **[Bedrijfsgegevens verwijderen](devices-wipe.md#remove-company-data)**: met de actie **Bedrijfsgegevens verwijderen** wordt het apparaat uit Intune verwijderd en worden beheerde app-gegevens, instellingen en e-mailprofielen die door Intune zijn toegewezen, verwijderd. De persoonlijke gegevens van de gebruiker blijven op het apparaat.

- **[Apparaten synchroniseren naar de nieuwste beleidsregels en acties](device-sync.md)**: met de actie **Synchroniseren** dwingt u het apparaat direct in te checken bij Intune. Wanneer een apparaat wordt ingecheckt, worden direct eventuele openstaande acties of toegewezen beleidsregels ontvangen die eraan zijn toegewezen. Met deze functie kunt u toegewezen beleid controleren en in het geval van problemen direct aanpassen, zonder dat u hoeft te wachten op de volgende geplande check-in.

**[Wat is Microsoft Intune-apparaatbeheer?](device-management.md)** is een goede resource voor meer informatie over het beheer van apparaten via Azure Portal. 

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
