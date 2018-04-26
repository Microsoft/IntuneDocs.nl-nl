---
title: Bekende problemen in Microsoft Intune - Azure | Microsoft Docs
description: Meer informatie over bekende problemen in Microsoft Intune.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 03/27/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f33a6645-a57e-4424-a1e9-0ce932ea83c5
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d0a8a189e708ed140c3cda987a20cebb562fdb34
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2018
---
# <a name="known-issues-in-microsoft-intune"></a>Bekende problemen in Microsoft Intune


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Gebruik dit artikel als u meer informatie wilt over bekende problemen in Microsoft Intune.

Als u een bug wilt melden die hier niet wordt weergegeven, kunt u een [ondersteuningsaanvraag openen](get-support.md).

Als u een suggestie wilt doen voor een nieuwe functie in Intune, kunt u een rapport indienen op de site [Uservoice](https://microsoftintune.uservoice.com/forums/291681-ideas/category/189016-azure-admin-console).

## <a name="migration"></a>Migratie

### <a name="intune-legacy-pc-client-features-are-only-available-in-the-silverlight-console"></a>Verouderde Intune PC Client-functies zijn alleen beschikbaar in de Silverlight-console

De mogelijkheid voor het beheren van Windows 10 in Intune op Azure Portal is beschikbaar via Windows MDM-inschrijving. Zie voor meer informatie [Console voor Intune in Azure en verouderde Intune PC Client](https://docs.microsoft.com/intune-classic/deploy-use/intune-on-azure).

### <a name="groups-created-by-intune-during-migration-might-affect-functionality-of-other-microsoft-products"></a>Groepen die tijdens de migratie door Intune zijn gemaakt, hebben mogelijk invloed op de functionaliteit van andere Microsoft-producten

Wanneer u van de Intune-portal naar Azure Portal migreert, ziet u mogelijk een nieuwe groep met de naam **Alle gebruikers - b0b08746-4dbe-4a37-9adf-9e7652c0b421**. Deze groep bevat alle gebruikers in uw Azure Active Directory, niet alleen gebruikers met een Intune-licentie. Dit gebruik kan problemen veroorzaken met andere Microsoft-producten, als u verwacht dat sommige bestaande of nieuwe gebruikers van geen enkele groep lid zijn.

### <a name="status-blades-for-migrated-policies-do-not-work"></a>Statusblades voor gemigreerde beleidsregels werken niet

U kunt geen statusinformatie weergeven voor beleidsregels die zijn gemigreerd vanuit de klassieke Azure-portal naar Azure Portal. U kunt rapporten voor dit beleid echter blijven bekijken in de klassieke portal. Als u statusinformatie voor gemigreerde configuratiebeleid wilt weergeven, maakt u ze opnieuw in Azure Portal.

## <a name="apps"></a>Apps

### <a name="ios-volume-purchased-apps-only-available-in-default-intune-tenant-language"></a>iOS-apps die zijn gekocht via het volume-aankoopprogramma, zijn alleen beschikbaar in de standaardtaal van de Intune-tenant
iOS-apps die zijn gekocht via het volume-aankoopprogramma, worden alleen in de taal van uw Intune-account weergegeven en kunnen alleen voor die taal worden toegewezen. Intune synchroniseert alleen apps met dezelfde iTunes-landinstelling als het account van de Intune-tenant. Als u bijvoorbeeld een app koopt die alleen beschikbaar is in de Amerikaanse store, maar u een Duits Intune-account hebt, wordt die app niet weergegeven in Intune.

### <a name="multiple-copies-of-the-same-ios-volume-purchase-program-are-uploaded"></a>Meerdere exemplaren van hetzelfde iOS-volume-aankoopprogramma worden geüpload
Klik niet meerdere keren op de knop **Uploaden** voor hetzelfde VPP-token. Hierdoor worden namelijk dubbele VPP-tokens geüpload en worden apps meerdere keren voor hetzelfde VPP-token gesynchroniseerd.


<!-- ## Groups -->

## <a name="device-configuration"></a>Apparaatconfiguratie

### <a name="you-cannot-save-a-windows-information-protection-policy-for-some-devices"></a>U kunt een Windows Information Protection-beleid voor bepaalde apparaten niet opslaan

Voor apparaten die niet zijn ingeschreven bij Intune, kunt u alleen een primair domein opgeven in het veld **Zakelijk identificeren** in de instellingen voor een Windows Information Protection-beleid.
Als u aanvullende domeinen toevoegt (met **Geavanceerde instellingen** > **Netwerkperimeter** > **Een beveiligd domein toevoegen**), kunt u het beleid niet opslaan. Het weergegeven foutbericht wordt binnenkort aangepast met nauwkeurigere informatie.

### <a name="cisco-anyconnect-vpn-client-support"></a>Ondersteuning voor Cisco AnyConnect VPN-client
De nieuwste versie van de Cisco AnyConnect VPN-client (4.0.07072) is momenteel niet compatibel met Intune. In een toekomstige update van Intune wordt compatibiliteit met deze versie van de VPN-client toegevoegd. Tot dat moment is het raadzaam om uw Cisco AnyConnect VPN-client niet bij te werken en de bestaande versie te blijven gebruiken.


### <a name="using-the-numeric-password-type-with-macos-sierra-devices"></a>Numerieke wachtwoordtypen gebruiken met macOS Sierra-apparaten

Als u momenteel het **Vereiste wachtwoordtype** **Numeriek** selecteert in een apparaatbeperkingsprofiel voor macOS Sierra-apparaten, wordt dit afgedwongen als **Alfanumeriek**. Als u een numeriek wachtwoord wilt gebruiken met deze apparaten, moet u deze instelling niet configureren.
Dit probleem wordt mogelijk opgelost in een toekomstige versie van macOS.

Zie [macOS-apparaatbeperkingsinstellingen in Microsoft Intune](device-restrictions-macos.md) voor meer informatie over deze instellingen.

## <a name="compliance"></a>Naleving

### <a name="compliance-policies-from-intune-do-not-show-up-in-new-console"></a>Nalevingsbeleid uit Intune wordt niet weergegeven in de nieuwe console

Nalevingsbeleidsregels die u hebt gemaakt in de klassieke portal, worden wel gemigreerd maar worden niet weergegeven in Azure Portal vanwege de ontwerpwijzigingen in Azure Portal. Nalevingsbeleid dat u in de klassieke Intune-portal hebt gemaakt, wordt nog steeds afgedwongen, maar u moet dit beleid in de klassieke portal weergeven en bewerken.

Bovendien is nieuw nalevingsbeleid dat u in Azure Portal maakt, niet zichtbaar in de klassieke portal.

Zie [Wat is apparaatcompatibiliteit](device-compliance.md) voor meer informatie.

<!-- ## Enrollment -->


## <a name="data-protection"></a>Gegevensbescherming

### <a name="ios-app-protection-policies"></a>Beleidsregels voor beveiliging van iOS-apps

U kunt [beleidsregels voor de beveiliging van iOS-apps](app-protection-policy-settings-ios.md) definiëren, die beschikbaar zijn voor gebruikers met apparaten die worden beheerd via beheer van mobiele apps (MAM) zonder inschrijving. Vanwege een tijdelijke fout kunt u deze beleidsregels alleen definiëren voor iOS-versienummers met één decimale punt en niet voor versienummers met meerdere decimale punten. In plaats van dat u iOS 10.3.1 als minimumversie instelt, stelt u de beleidsregels in voor iOS 10.3. Deze fout wordt in een toekomstige update van de iOS-SDK opgelost.


## <a name="administration-and-accounts"></a>Beheer en accounts

Globale beheerders (ook wel tenantbeheerders genoemd) kunnen de reguliere beheertaken voortzetten zonder afzonderlijke Intune- of Enterprise Mobility Suite-licentie (ESM). Als ze echter de service willen gebruiken, bijvoorbeeld om hun eigen apparaat of een bedrijfsapparaat in te schrijven of om de Intune-bedrijfsportal te gebruiken, moeten ze beschikken over een Intune- of EMS-licentie.

<!-- ## Additional items -->
