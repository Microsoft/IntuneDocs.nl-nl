---
title: De instantie voor het beheer van mobiele apparaten instellen
titlesuffix: Microsoft Intune
description: Stel de instantie in voor het beheer van mobiele apparaten in Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/30/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 8deff871-5dff-4767-9484-647428998d82
ms.reviewer: damionw
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: a783b784f63453ba706e69bbb5078b0c3cda37d8
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/07/2019
ms.locfileid: "55834514"
---
# <a name="set-the-mobile-device-management-authority"></a>De instantie voor het beheer van mobiele apparaten instellen

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Met de instantie voor het beheer van mobiele apparaten (MDM) wordt bepaald hoe u uw apparaten beheert. Als IT-beheerder moet u een MDM-instantie instellen voordat gebruikers apparaten voor beheer kunnen inschrijven.

Mogelijke configuraties zijn:

- **Intune Standalone**: cloudbeheer dat u configureert met behulp van de Azure Portal. Bevat de volledige reeks mogelijkheden van Intune. [De MDM-instantie instellen in de Intune-beheerconsole](#set-mdm-authority-to-intune).

- **Intune Hybrid**: integratie van de Intune-cloudoplossing met System Center Configuration Manager. U kunt Intune configureren met behulp van de Configuration Manager-console. [De MDM-instantie instellen in Configuratiebeheer](https://docs.microsoft.com/sccm/mdm/deploy-use/configure-intune-subscription). 

    > [!Important]
    >Het onboarden van nieuwe klanten van hybride MDM wordt uitgeschakeld in een volgende versie. Zie de blogpost [Overstappen van hybride Mobile Device Management naar Intune op Azure](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Move-from-Hybrid-Mobile-Device-Management-to-Intune-on-Azure/ba-p/280150) voor meer informatie.

- **Mobile Device Management voor Office 365**: integratie van Office 365 met de Intune-cloudoplossing. U kunt Intune configureren vanuit het Office 365-beheercentrum. Bevat een subset van de mogelijkheden die beschikbaar zijn met Intune Standalone. Stel de MDM-instantie in Office 365-beheercentrum in.

> [!IMPORTANT]
> In Configuration Manager versie 1610 of hoger en Microsoft Intune versie 1705 kunt u de MDM-instantie wijzigen zonder dat u contact hoeft op te nemen met Microsoft Ondersteuning en zonder dat u de inschrijving van bestaande beheerde apparaten ongedaan hoeft te maken om ze vervolgens opnieuw in te schrijven. Zie [Voorbereiden op het wijzigen van de MDM-instantie naar Configuration Manager](mdm-authority-set.md#prepare-to-change-the-mdm-authority-to-configuration-manager) voor meer informatie.

## <a name="set-mdm-authority-to-intune"></a>MDM-instantie instellen op Intune

Als u de MDM-instantie nog niet hebt ingesteld, volgt u de onderstaande stappen. Zie de sectie [MDM-instantie wijzigen](#prepare-to-change-the-mdm-authority-to-configuration-manager) hierna als u van MDM-instantie wilt wijzigen.

1. Meld u aan bij de [Azure-portal](https://portal.azure.com).
2. Kies **Alle services** > **Intune**. Intune bevindt zich in de sectie **Controle en beheer**.
3. Selecteer de oranje banner om de instelling **Instantie voor beheer van mobiele apparaten** te openen. De oranje banner wordt alleen weergegeven als u de MDM-instantie nog niet hebt ingesteld.
4. Kies onder **Instantie voor beheer van mobiele apparaten** uw MDM-instantie uit de volgende opties:
   - **MDM-instantie voor Intune**
   - **MDM-instantie voor Configuration Manager**
   - **Geen**

   ![Schermafbeelding van het scherm De instantie voor het beheer van mobiele apparaten instellen op Intune](media/set-mdm-auth.png)

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
Nadat u overschakelt naar de nieuwe MDM-instantie, duurt het waarschijnlijk enige tijd (maximaal acht uur) voordat het apparaat wordt ingecheckt en synchroniseert met de service. U moet instellingen in de nieuwe MDM-instantie (hybride) configureren om ervoor te zorgen dat geregistreerde apparaten na de wijziging nog steeds worden beheerd en beschermd. 
- Apparaten moeten na de wijziging verbinding maken met de service, zodat de instellingen van de nieuwe MDM-instantie (zelfstandige versie van Intune) de huidige instellingen op het apparaat vervangen.
- Na het wijzigen van de MDM-instantie blijven sommige basisinstellingen (zoals profielen) van de vorige MDM-instantie (zelfstandige versie van Intune) maximaal zeven dagen aanwezig op het apparaat, of totdat het apparaat de eerste keer verbinding maakt met de service. Het is aan te raden om de apps en instellingen (beleid, profielen, apps enzovoort) zo snel mogelijk te configureren in de nieuwe MDM-instantie (hybride) en de instellingen te implementeren naar de gebruikersgroepen met gebruikers met bestaande geregistreerde apparaten. Zodra een apparaat verbinding maakt met de service na de wijziging van MDM-instantie, ontvangt het de nieuwe instellingen van de nieuwe MDM-instantie om te voorkomen dat het apparaat enige tijd onbeheerd en onbeschermd is.
- Wanneer dezelfde apparaatcategorieën bestaan in Intune en Configuration Manager, worden apparaatcategorietoewijzingen voor apparaten niet overgedragen nadat u naar de nieuwe MDM-instantie bent overgeschakeld. Als u apparaatcategorieën wilt blijven gebruiken, moet u gemigreerde apparaten handmatig toevoegen aan de juiste verzamelingen nadat de MDM-instantie is gewijzigd en de apparaten worden weergegeven in de Configuration Manager-console.
- Apparaten waaraan geen gebruikers zijn gekoppeld (zoals wanneer u werkt met het iOS Device Enrollment Program of scenario’s voor bulkinschrijving) worden niet gemigreerd naar de nieuwe MDM-instantie. Voor die apparaten moet u contact opnemen met ondersteuning voor hulp bij het overbrengen naar de nieuwe MDM-instantie.

## <a name="prepare-to-change-the-mdm-authority-to-configuration-manager"></a>Voorbereiden op het wijzigen van de MDM-instantie naar Configuration Manager

Lees de volgende informatie ter voorbereiding op het wijzigen van de MDM-instantie:
- De optie voor het wijzigen van de MDM-instantie is alleen beschikbaar in Configuration Manager versie 1610 of hoger.
- Na het overschakelen naar de nieuwe MDM-instantie kan het tot acht uur duren voordat een apparaat verbinding maakt met de service.
- Maak een Configuration Manager-gebruikersverzameling met alle gebruikers die momenteel worden beheerd door de zelfstandige versie van Intune. Deze verzameling gebruikt u bij het instellen van het Intune-abonnement in de Configuration Manager-console. Met deze verzameling zorgt u ervoor dat er een Configuration Manager-licentie is toegewezen aan de gebruikers en hun apparaten en ze beheerd kunnen worden in de hybride omgeving na de wijziging van de MDM-instantie.
- Zorg dat de gebruikersverzameling ook de IT-beheerder omvat.  
- Voor de wijziging wordt de MDM-instantie weergegeven als **Ingesteld op Microsoft Intune** (zelfstandige versie) in de Intune-beheerconsole.
- Voorafgaand aan de wijziging van MDM-instantie moet de MDM-instantie worden weergegeven als **Ingesteld op Microsoft Intune** (zelfstandige tenant) in de Microsoft Intune-beheerconsole.
    > [!NOTE]    
    > Als de MDM-instantie wordt weergegeven als **Beheerd door Intune en Office 365** worden uw door Office 365 beheerde MDM-apparaten niet meer beheerd wanneer u de MDM-instantie wijzigt in **Configuration Manager** (hybride). We adviseren om die gebruikers te voorzien van een licentie voor Intune of Enterprise Mobility Suite voordat u de MDM-instantie wijzigt.   

- Verwijder in de [Microsoft Intune-beheerconsole](http://manage.microsoft.com) de rol Apparaatinschrijvingsmanager. Zie [Een apparaatinschrijvingsmanager uit Intune verwijderen](device-enrollment-manager-enroll.md#remove-device-enrollment-manager-permissions) voor meer informatie.
- Schakel eventuele groepstoewijzingen die zijn geconfigureerd uit. Zie [Apparaten categoriseren met apparaatgroeptoewijzing in Microsoft Intune](device-group-mapping.md) voor meer informatie.
- De eindgebruikers mogen niets merken van de wijziging van MDM-instantie. Mogelijk wilt u de wijziging echter bekendmaken aan gebruikers, om ervoor te zorgen dan hun apparaten zijn ingeschakeld en dat die kort na de wijziging verbinding maken met de service. Hiermee zorgt u ervoor dat zoveel mogelijk apparaten zo snel mogelijk verbinding maken met en registeren bij de service via de nieuwe instantie.
- Als u de zelfstandige versie van Intune gebruikt om iOS-apparaten te beheren voorafgaand aan de wijziging van MDM-instantie, moet u ervoor zorgen dat hetzelfde Apple Push Notification Service-certificaat (APNs) dat werd gebruikt in Intune wordt vernieuwd en gebruikt om de tenant opnieuw in te stellen in Configuration Manager (hybride).    

    > [!IMPORTANT]  
    > Als er een ander APNs-certificaat wordt gebruikt voor hybride, worden ALLE eerder ingeschreven iOS-apparaten uitgeschreven en moet u het gehele inschrijvingsproces opnieuw doorlopen. Zorg dat u precies weet welk APNs-certificaat is gebruikt voor het beheren van iOS-apparaten in Intune voordat u de MDM-instantie wijzigt. Zoek de vermelding van dat certificaat in de Apple Push Certificates Portal (https://identity.apple.com)), zorg dat u weet wie de gebruiker is van wie de Apple ID is gebruikt om het oorspronkelijke APNs-certificaat te maken, en zorg dat die gebruiker beschikbaar is om hetzelfde APNs-certificaat te vernieuwen als onderdeel van de wijziging naar de nieuwe MDM-instantie.

## <a name="change-the-mdm-authority-to-configuration-manager"></a>De MDM-instantie wijzigen naar Configuration Manager

1. Ga in de Configuration Manager-console naar **Beheer** &gt; **Overzicht** &gt; **Cloudservices** &gt; **Microsoft Intune-abonnement** en selecteer de optie om een Intune-abonnement toe te voegen.
2. Meld u aan bij de Intune-tenant die u oorspronkelijk hebt gebruikt bij het instellen van de MDM-instantie in Intune en klik op **Volgende**.
3. Selecteer **Mijn MDM-instantie wijzigen naar Configuration Manager** en klik op **Volgende**.
4. Selecteer de gebruikersverzameling die alle gebruikers bevat die ook worden beheerd door de nieuwe hybride MDM-instantie.
5. Klik op **Volgende** en voltooi de wizard. De MDM-instantie is nu gewijzigd naar **Configuration Manager**.
6. Meld u aan bij de [Microsoft Intune-beheerconsole](http://manage.microsoft.com) met dezelfde Intune-tenant om te controleren of de MDM-instantie is gewijzigd in **Ingesteld op Configuration Manager**.
7. Nadat de MDM-instantie is gewijzigd naar Configuration Manager, kunt u [iOS-inschrijving](https://docs.microsoft.com/sccm/mdm/deploy-use/enroll-hybrid-ios-mac) en [Android-inschrijving](https://docs.microsoft.com/sccm/mdm/deploy-use/enroll-hybrid-android) instellen.
8. Configureer en implementeer de nieuwe instellingen en apps van de nieuwe MDM-instantie (hybride) in de Configuration Manager-console.

De volgende keer dat apparaten verbinding maken met de service, worden ze gesynchroniseerd en ontvangen ze de nieuwe instellingen van de nieuwe MDM-instantie.

## <a name="change-mdm-authority-to-office-365"></a>MDM-instantie wijzigen in Office 365

Als u Office 365 MDM wilt activeren naast uw bestaande Intune Service, gaat u naar [https://protection.office.com](https://protection.office.com), kiest u **Preventie van gegevensverlies** > **Beveiligingsbeleid voor apparaten** > **Lijst met beheerde apparaten weergeven** > **aan de slag**.

Zie [Mobile Device Management (MDM) instellen in Office 365](https://support.office.com/en-us/article/Set-up-Mobile-Device-Management-MDM-in-Office-365-dd892318-bc44-4eb1-af00-9db5430be3cd) voor meer informatie.

Als u wilt dat de eindgebruikers alleen worden beheerd door Office 365 MDM, verwijdert u alle toegewezen Intune- en/of EMS-licenties na het activeren van Office 365 MDM.

## <a name="mobile-device-cleanup-after-mdm-certificate-expiration"></a>Mobiele apparaten opschonen na de verloopdatum van het MDM-certificaat

Het MDM-certificaat wordt automatisch vernieuwd wanneer mobiele apparaten communiceren met de Intune-service. Als mobiele apparaten worden gewist of een bepaalde tijd niet kunnen communiceren met de Intune-service, wordt het MDM-certificaat niet vernieuwd. Het apparaat wordt 180 dagen nadat het MDM-certificaat is verlopen verwijderd uit de Azure Portal.

## <a name="remove-mdm-authority"></a>MDM-instantie verwijderen

De MDM-instantie kan niet weer worden gewijzigd in Onbekend. De MDM-instantie wordt gebruikt door Microsoft-servers om te bepalen aan welke portal ingeschreven apparaten rapporteren (ConfigMGR, Azure Intune, Office 365 MDM).

## <a name="what-to-expect-after-changing-the-mdm-authority"></a>Wat u kunt verwachten na het wijzigen van de MDM-instantie

- Wanneer via de Intune-service wordt gedetecteerd dat de MDM-instantie van een tenant is gewijzigd, wordt er een verzoek verzonden naar alle geregistreerde apparaten om in te checken bij en te synchroniseren met de service (deze melding staat los van het gebruikelijke geplande inchecken). Dus nadat de MDM-instantie voor de tenant is gewijzigd van de zelfstandige versie van Intune in hybride, maken alle ingeschakelde apparaten die online zijn, verbinding met de service, ontvangen deze de nieuwe MDM-instantie en worden deze voortaan beheerd door hybride. Het beheer en de beveiliging van deze apparaten worden niet onderbroken.
- Zelfs voor ingeschakelde apparaten die online zijn tijdens (of kort na) de wijziging van MDM-instantie is er een vertraging van maximaal acht uur (afhankelijk van de timing van het gebruikelijke geplande inchecken) voordat apparaten zijn geregistreerd bij de service met de nieuwe MDM-instantie.    

  > [!IMPORTANT]    
  > Gedurende de periode tussen het wijzigen van de MDM-instantie en het uploaden van het vernieuwde APNs-certificaat naar de nieuwe instantie, mislukt het inschrijven van nieuwe apparaten en inchecken van iOS-apparaten. Daarom is het belangrijk dat u het APNs-certificaat zo snel mogelijk vernieuwt en uploadt naar de nieuwe instantie na het wijzigen van de MDM-instantie.

- Gebruikers kunnen snel overschakelen naar de nieuwe MDM-instantie door handmatig in te checken bij de service met hun apparaat. Gebruikers kunnen deze wijziging gemakkelijk doorvoeren door de bedrijfsportal-app te openen en een compatibiliteitscontrole te starten.
- Als u wilt controleren of alles goed werkt nadat apparaten zijn ingecheckt en gesynchroniseerd met de service na het wijzigen van de MDM-instantie, zoekt u de apparaten in de Configuration Manager-console. De apparaten die voorheen werden beheerd door Intune, worden nu weergegeven als beheerde apparaten in de Configuration Manager-console.    
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

-  Nadat u de MDM-instantie wijzigt, voert u de volgende stappen uit om te controleren of nieuwe apparaten correct worden ingeschreven bij de nieuwe instantie:   
    - Een nieuw apparaat inschrijven
    - Controleer of het nieuw ingeschreven apparaat wordt weergegeven in de Configuration Manager-console.
    - Voer een actie uit op het apparaat vanaf de beheerconsole, zoals vergrendelen op afstand. Als dit lukt, wordt het apparaat beheerd door de nieuwe MDM-instantie.
- Als er problemen optreden met specifieke apparaten, kunt u ze uitschrijven en weer inschrijven om ze verbinding te laten maken met de nieuwe instantie en zo snel mogelijk weer te kunnen beheren.

## <a name="next-steps"></a>Volgende stappen

Wanneer de MDM-instantie is ingesteld, kunt u beginnen met het [inschrijven van apparaten](device-enrollment.md).
