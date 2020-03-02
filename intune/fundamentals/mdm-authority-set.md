---
title: De instantie voor het beheer van mobiele apparaten instellen
titleSuffix: Microsoft Intune
description: Stel de instantie in voor het beheer van mobiele apparaten in Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 08/16/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.assetid: 8deff871-5dff-4767-9484-647428998d82
ms.reviewer: damionw
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: b611b2307b7b4f7e789e7db9d070e4b6b3f1350c
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/20/2020
ms.locfileid: "77514486"
---
# <a name="set-the-mobile-device-management-authority"></a>De instantie voor het beheer van mobiele apparaten instellen

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Met de instantie voor het beheer van mobiele apparaten (MDM) wordt bepaald hoe u uw apparaten beheert. Als IT-beheerder moet u een MDM-instantie instellen voordat gebruikers apparaten voor beheer kunnen inschrijven.

Mogelijke configuraties zijn:

- **Intune Standalone**: cloudbeheer dat u configureert met behulp van de Azure Portal. Bevat de volledige reeks mogelijkheden van Intune. [De MDM-instantie instellen in de Intune-beheerconsole](#set-mdm-authority-to-intune).

- **Co-beheer voor Intune**: integratie van de Intune-cloudoplossing met Configuration Manager voor Windows 10-apparaten. U kunt Intune configureren met behulp van de Configuration Manager-console. [Configureer de automatische inschrijving van apparaten in Intune](https://docs.microsoft.com/configmgr/comanage/tutorial-co-manage-clients#configure-auto-enrollment-of-devices-to-intune). 

- **Mobile Device Management voor Office 365**: integratie van Office 365 met de Intune-cloudoplossing. U kunt Intune configureren vanuit het Microsoft 365-beheercentrum. Bevat een subset van de mogelijkheden die beschikbaar zijn met Intune Standalone. Stel de MDM-instantie in het Microsoft 365-beheercentrum in.

- **Combinatie met Office 365 MDM**: u kunt MDM voor Office 365 gelijktijdig met Intune activeren en gebruiken in uw tenant. U kunt per gebruiker de beheerinstantie instellen op Intune of MDM voor Office 365 om te bepalen welke service wordt gebruikt voor het beheren van de mobiele apparaten van die gebruiker. De beheerinstantie van de gebruiker wordt gedefinieerd op basis van de licentie die aan de gebruiker is toegewezen. Zie het blogbericht [Microsoft Intune Co-existence with MDM for Office 365](https://blogs.technet.microsoft.com/configmgrdogs/2016/01/04/microsoft-intune-co-existence-with-mdm-for-office-365) voor meer informatie

## <a name="set-mdm-authority-to-intune"></a>MDM-instantie instellen op Intune

Als u de MDM-instantie nog niet hebt ingesteld, volgt u de onderstaande stappen.

1. Selecteer in [het beheercentrum Eindpuntbeheer van Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431) de oranje banner om de instelling **Instantie voor beheer van mobiele apparaten** te openen. De oranje banner wordt alleen weergegeven als u de MDM-instantie nog niet hebt ingesteld.
2. Kies onder **Instantie voor beheer van mobiele apparaten** uw MDM-instantie uit de volgende opties:
   - **MDM-instantie voor Intune**
   - **Geen**

   ![Schermafbeelding van het scherm De instantie voor het beheer van mobiele apparaten instellen op Intune](./media/mdm-authority-set/set-mdm-auth.png)

   Er verschijnt een bericht met de melding dat u uw MDM-instantie hebt ingesteld op Intune.

### <a name="workflow-of-intune-administration-ui"></a>Werkstroom van de Intune-beheergebruikersinterface
Als Android- of Apple-apparaatbeheer is ingeschakeld, worden met Intune apparaat- en gebruikersgegevens verzonden, zodat deze kunnen worden geïntegreerd in de externe services voor het beheren van apparaten.

Scenario's waarin toestemming moet worden gegeven om gegevens te delen, zijn:
- Wanneer u Android-werkprofielen inschakelt.
- Wanneer u Apple MDM-pushcertificaten inschakelt en uploadt,
- Wanneer u een van de Apple-services zoals Device Enrollment Program, School Manager of Volume Purchasing Program inschakelt.

Hoe dan ook, blijft de toestemming beperkt tot het uitvoeren van een service voor het beheer van mobiele apparaten. Zoals wanneer een IT-beheerder Google- of Apple-apparaten heeft geautoriseerd om zich te registreren. Documentatie over welke informatie wordt gedeeld wanneer de nieuwe werkstromen live gaan, is beschikbaar op de volgende locaties:
- [Gegevens die Intune naar Google verzendt](https://aka.ms/Data-intune-sends-to-google)
- [Gegevens die Intune naar Apple verzendt](https://aka.ms/data-intune-sends-to-apple)

## <a name="key-considerations"></a>Belangrijke overwegingen
Nadat u overschakelt naar de nieuwe MDM-instantie, duurt het waarschijnlijk enige tijd (maximaal acht uur) voordat het apparaat wordt ingecheckt en synchroniseert met de service. U moet instellingen in de nieuwe MDM-instantie configureren om ervoor te zorgen dat geregistreerde apparaten na de wijziging nog steeds worden beheerd en beschermd. 
- Apparaten moeten na de wijziging verbinding maken met de service, zodat de instellingen van de nieuwe MDM-instantie (zelfstandige versie van Intune) de huidige instellingen op het apparaat vervangen.
- Na het wijzigen van de MDM-instantie blijven sommige basisinstellingen (zoals profielen) van de vorige MDM-instantie maximaal zeven dagen aanwezig op het apparaat, of totdat het apparaat de eerste keer verbinding maakt met de service. Het is aan te raden om de apps en instellingen (beleid, profielen, apps enzovoort) zo snel mogelijk te configureren in de nieuwe MDM-instantie en de instellingen te implementeren naar de gebruikersgroepen met gebruikers met bestaande geregistreerde apparaten. Zodra een apparaat verbinding maakt met de service na de wijziging van MDM-instantie, ontvangt het de nieuwe instellingen van de nieuwe MDM-instantie om te voorkomen dat het apparaat enige tijd onbeheerd en onbeschermd is.
- Apparaten waaraan geen gebruikers zijn gekoppeld (zoals wanneer u werkt met het iOS/iPadOS Device Enrollment Program of scenario’s voor bulkinschrijving) worden niet gemigreerd naar de nieuwe MDM-instantie. Voor die apparaten moet u contact opnemen met ondersteuning voor hulp bij het overbrengen naar de nieuwe MDM-instantie.

## <a name="change-mdm-authority-to-office-365"></a>MDM-instantie wijzigen in Office 365

Als u Office 365 MDM wilt activeren (of MDM wilt activeren naast uw bestaande Intune-service), gaat u naar [https://protection.office.com](https://protection.office.com), kiest u **Preventie van gegevensverlies** > **Beveiligingsbeleid voor apparaten** > **Lijst met beheerde apparaten weergeven** > **Aan de slag**.

Zie [Mobile Device Management (MDM) instellen in Office 365](https://support.office.com/en-us/article/Set-up-Mobile-Device-Management-MDM-in-Office-365-dd892318-bc44-4eb1-af00-9db5430be3cd) voor meer informatie.

Als u wilt dat de eindgebruikers alleen worden beheerd door Office 365 MDM, verwijdert u alle toegewezen Intune- en/of EMS-licenties na het activeren van Office 365 MDM.

## <a name="mobile-device-cleanup-after-mdm-certificate-expiration"></a>Mobiele apparaten opschonen na de verloopdatum van het MDM-certificaat

Het MDM-certificaat wordt automatisch vernieuwd wanneer mobiele apparaten communiceren met de Intune-service. Als mobiele apparaten worden gewist of een bepaalde tijd niet kunnen communiceren met de Intune-service, wordt het MDM-certificaat niet vernieuwd. Het apparaat wordt 180 dagen nadat het MDM-certificaat is verlopen verwijderd uit de Azure Portal.

## <a name="remove-mdm-authority"></a>MDM-instantie verwijderen

De MDM-instantie kan niet weer worden gewijzigd in Onbekend. De MDM-instantie wordt gebruikt door de service om te bepalen aan welke portal ingeschreven apparaten rapporteren (Microsoft Intune of Office 365 MDM).

## <a name="what-to-expect-after-changing-the-mdm-authority"></a>Wat u kunt verwachten na het wijzigen van de MDM-instantie

- Wanneer via de Intune-service wordt gedetecteerd dat de MDM-instantie van een tenant is gewijzigd, wordt er een verzoek verzonden naar alle geregistreerde apparaten om in te checken bij en te synchroniseren met de service (deze melding staat los van het gebruikelijke geplande inchecken). Dus nadat de MDM-instantie voor de tenant is gewijzigd van de zelfstandige versie van Intune, maken alle ingeschakelde apparaten die online zijn, verbinding met de service, ontvangen deze de nieuwe MDM-instantie en worden deze voortaan beheerd door de nieuwe MDM-instantie. Het beheer en de beveiliging van deze apparaten worden niet onderbroken.
- Zelfs voor ingeschakelde apparaten die online zijn tijdens (of kort na) de wijziging van MDM-instantie is er een vertraging van maximaal acht uur (afhankelijk van de timing van het gebruikelijke geplande inchecken) voordat apparaten zijn geregistreerd bij de service met de nieuwe MDM-instantie.    

  > [!IMPORTANT]    
  > Gedurende de periode tussen het wijzigen van de MDM-instantie en het uploaden van het vernieuwde APNs-certificaat naar de nieuwe instantie, mislukt het inschrijven van nieuwe apparaten en inchecken van iOS-/iPadOS-apparaten. Daarom is het belangrijk dat u het APNs-certificaat zo snel mogelijk vernieuwt en uploadt naar de nieuwe instantie na het wijzigen van de MDM-instantie.

- Gebruikers kunnen snel overschakelen naar de nieuwe MDM-instantie door handmatig in te checken bij de service met hun apparaat. Gebruikers kunnen deze wijziging gemakkelijk doorvoeren door de bedrijfsportal-app te openen en een compatibiliteitscontrole te starten.
- Als u wilt controleren of alles goed werkt nadat apparaten zijn ingecheckt en gesynchroniseerd met de service na het wijzigen van de MDM-instantie, zoekt u de apparaten in de nieuwe MDM-instantie.
- Er ontstaat een tijdelijke situatie als een apparaat offline is tijdens de wijziging van MDM-instantie en pas later incheckt bij de service. Om ervoor te zorgen dat het apparaat beveiligd is en blijft functioneren tijdens deze periode, blijven de volgende profielen maximaal zeven dagen beschikbaar op het apparaat (of tot het moment waarop het apparaat verbinding maakt met de nieuwe MDM-instantie en nieuwe instellingen ontvangt die de oude overschrijven):
  - E-mailprofiel
  - VPN-profiel
  - Certificaatprofiel
  - Wi-Fi-profiel
  - Configuratieprofielen
- Nadat de MDM-instantie is gewijzigd, kan het tot een week duren voordat de nalevingsgegevens in de Microsoft Intune-beheerconsole correct worden weergegeven. De nalevingsstatus in Azure Active Directory en op het apparaat is echter wel correct, zodat het apparaat nog steeds is beveiligd.
- Zorg dat de nieuwe instellingen, die de bestaande instellingen moeten overschrijven, dezelfde naam hebben als de vorige instellingen om er zeker van te zijn dat ze worden overschreven. Anders blijven er mogelijk achterhaalde profielen en beleidsregels achter op het apparaat.    

  > [!TIP]    
  > De beste methode is om alle beheerinstellingen en -configuraties en alle implementaties zo snel mogelijk te maken nadat de wijziging van MDM-instantie is voltooid. Dit zorgt ervoor dat apparaten beveiligd zijn en actief worden beheerd in de tussenperiode.

- Nadat u de MDM-instantie wijzigt, voert u de volgende stappen uit om te controleren of nieuwe apparaten correct worden ingeschreven bij de nieuwe instantie:   
  - Een nieuw apparaat inschrijven
  - Controleer of het nieuw ingeschreven apparaat wordt weergegeven in de nieuwe MDM-instantie.
  - Voer een actie uit op het apparaat vanaf de beheerconsole, zoals vergrendelen op afstand. Als dit lukt, wordt het apparaat beheerd door de nieuwe MDM-instantie.
- Als er problemen optreden met specifieke apparaten, kunt u ze uitschrijven en weer inschrijven om ze verbinding te laten maken met de nieuwe instantie en zo snel mogelijk weer te kunnen beheren.

## <a name="next-steps"></a>Volgende stappen

Wanneer de MDM-instantie is ingesteld, kunt u beginnen met het [inschrijven van apparaten](../enrollment/device-enrollment.md).
