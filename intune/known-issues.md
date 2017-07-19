---
title: Bekende problemen in Microsoft Intune op Azure
titleSuffix: Intune on Azure
description: Meer informatie over bekende problemen in Intune"
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 06/27/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f33a6645-a57e-4424-a1e9-0ce932ea83c5
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 4fda224613d8b69be82ef7f9681ba9165be33e52
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/01/2017
---
# <a name="known-issues-in-microsoft-intune"></a>Bekende problemen in Microsoft Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]


Gebruik dit onderwerp als u meer informatie wilt over bekende problemen in Microsoft Intune.

Als u een fout wilt melden die bug hier niet wordt weergegeven, kunt u een [ondersteuningsaanvraag openen](get-support.md).

Als u een suggestie wilt doen voor een nieuwe functie in Intune, kunt u een rapport op de site [Uservoice](https://microsoftintune.uservoice.com/forums/291681-ideas/category/189016-azure-admin-console) indienen.

## <a name="migration"></a>Migratie

### <a name="groups-created-by-intune-during-migration-might-affect-functionality-of-other-microsoft-products"></a>Groepen die tijdens de migratie door Intune zijn gemaakt, hebben mogelijk invloed op de functionaliteit van andere Microsoft-producten

Wanneer u van de klassieke Intune-portal naar Azure migreert, ziet u mogelijk een nieuwe groep met de naam **Alle gebruikers - b0b08746-4dbe-4a37-9adf-9e7652c0b421**. Deze groep bevat alle gebruikers in uw Azure Active Directory, niet alleen gebruikers met een Intune-licentie. Dit gebruik kan problemen veroorzaken met andere Microsoft-producten, als u verwacht dat sommige bestaande of nieuwe gebruikers van geen enkele groep lid zijn.

### <a name="secondary-migration-required-for-select-capabilities"></a>Secundaire migratie vereist is voor bepaalde mogelijkheden

Intune-accounts die voor januari 2017 zijn gemaakt, moeten worden gemigreerd voordat deze mogelijkheden kunnen worden gebruikt in de Azure portal:

- Inschrijvingsprofiel voor bedrijfsapparaten
- Apple Device Enrollment Program
- Vooraf geregistreerde bedrijfsapparaten op groep voor iOS-serienummer
- Apparaatinschrijvingsmanagers
- Apple Volume Purchase Program

Deze mogelijkheden kunnen niet worden beheerd in de klassieke Silverlight- en de Azure-console. Daarom zal de migratie:
- Ze in de klassieke console uitschakelen
- Ze in de Azure-console inschakelen.  

Als u deze Intune-mogelijkheden nu in Azure Portal beheert, moet u rekening houden met de volgende punten:

#### <a name="removes-default-corporate-device-enrollment-profiles-in-apple-dep"></a>De standaardprofielen voor de registratie van bedrijfsapparaten in Apple DEP worden verwijderd
Azure Portal biedt geen ondersteuning voor een standaardprofiel voor de registratie van bedrijfsapparaten voor Apple DEP-apparaten (Device Enrollment Program). Deze functionaliteit, die beschikbaar is in de klassieke Silverlight Intune-console, wordt stopgezet om onbedoelde profieltoewijzing te voorkomen. Als de DEP-serienummers in Azure Portal worden gesynchroniseerd, wordt er geen inschrijvingsprofiel voor bedrijfsapparaten toegewezen. Een inschrijvingsprofiel moet worden toegewezen voordat het apparaat wordt gebruikt.

#### <a name="apple-dep-token-restored-with-migration"></a>Apple DEP-token hersteld met migratie

Als u een token van Apple Device Enrollment Program hebt verwijderd in de klassieke Intune-portal (Silverlight) en geen nieuw token uploadt naar Azure Portal, wordt het oorspronkelijke token tijdens de migratie hersteld in Azure Portal. Als u dit token wilt verwijderen en DEP-inschrijving wilt voorkomen, verwijdert u het token uit Azure Portal.

### <a name="status-blades-for-migrated-policies-do-not-work"></a>Statusblades voor gemigreerde beleidsregels werken niet

U kunt geen statusinformatie weergeven voor beleidsregels die zijn gemigreerd vanuit de klassieke portal naar Azure Portal. U kunt rapporten voor dit beleid echter blijven bekijken in de klassieke portal.
Als u statusinformatie voor gemigreerde configuratiebeleid wilt weergeven, maakt u ze opnieuw in Azure Portal.

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

Nalevingsbeleidsregels die u hebt gemaakt in de klassieke portal, worden wel gemigreerd maar worden niet weergegeven in Azure Portal vanwege de ontwerpwijzigingen in Azure Portal. Nalevingsbeleid dat u in de klassieke Intune-portal hebt gemaakt, wordt nog steeds afgedwongen, maar u moet dit beleid in de klassieke Intune-portal weergeven en bewerken.
Bovendien is nieuw nalevingsbeleid dat u in Azure Portal maakt, niet zichtbaar in de klassieke Intune-portal.

Zie [Wat is apparaatcompatibiliteit](device-compliance.md) voor meer informatie.

<!-- ## Enrollment -->


<!-- ## Data protection -->


## <a name="administration-and-accounts"></a>Beheer en accounts

Globale beheerders (ook wel tenantbeheerders genoemd) kunnen de reguliere beheertaken voortzetten zonder afzonderlijke Intune- of Enterprise Mobility Suite-licentie (ESM). Als ze echter de service willen gebruiken, bijvoorbeeld om hun eigen apparaat of een bedrijfsapparaat in te schrijven of om de Intune-bedrijfsportal te gebruiken, moeten ze beschikken over een Intune- of EMS-licentie.

<!-- ## Additional items -->












 
