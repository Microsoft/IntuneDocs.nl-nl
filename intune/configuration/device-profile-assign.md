---
title: Apparaatprofielen toewijzen in Microsoft Intune - Azure | Microsoft Docs
description: Gebruik Azure Portal om apparaatprofielen en beleidsregels aan gebruikers en apparaten toe te wijzen. Informatie over het uitsluiten van groepen uit een profieltoewijzing in Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/05/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: high
ms.technology: ''
ms.assetid: f6f5414d-0e41-42fc-b6cf-e7ad76e1e06d
ms.reviewer: altsou
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 651b02dc276ca2aa2003955e6aa7b0dfa6724a40
ms.sourcegitcommit: 66e284fe092e19c1da72b4b770e45bf25ac7910c
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/05/2019
ms.locfileid: "74860312"
---
# <a name="assign-user-and-device-profiles-in-microsoft-intune"></a>Gebruikers- en apparaatprofielen toewijzen in Microsoft Intune

U maakt een profiel en dit omvat alle instellingen die u hebt ingevoerd. De volgende stap is het implementeren of toewijzen van het profiel aan uw gebruikers- of apparaatgroepen in Azure AD (Active Directory). Wanneer het is toegewezen, ontvangen de gebruikers en apparaten uw profiel, en worden de ingevoerde instellingen toegewezen.

In dit artikel ziet u hoe u een profiel kunt toewijzen, en krijgt u informatie over het gebruik van bereiktags in uw profielen.

> [!NOTE]  
> Wanneer een profiel wordt verwijderd of niet meer is toegewezen aan een apparaat, behoudt de instelling mogelijk de bestaande waarde. De instelling wordt niet teruggezet naar een standaardwaarde. Als u de instelling wilt wijzigen in een andere waarde, maakt u een nieuw profiel en wijst u dit toe.

## <a name="before-you-begin"></a>Voordat u begint

Zorg ervoor dat u de juiste rol hebt om profielen toe te wijzen. Zie [Op rollen gebaseerd toegangsbeheer (RBAC) met Microsoft Intune](../fundamentals/role-based-access-control.md) voor meer informatie.

## <a name="assign-a-device-profile"></a>Een apparaatprofiel toewijzen

1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecteer **Apparaten** > **Configuratieprofielen**. Alle profielen worden vermeld.
3. Selecteer het profiel dat u wilt toewijzen > **Toewijzingen**.
4. Geef aan of u groepen wilt **Opnemen** of **Uitsluiten** en selecteer vervolgens uw groepen. Wanneer u uw groepen hebt geselecteerd, kiest u een Azure AD-groep. Houd **Ctrl** ingedrukt om meerdere groepen te selecteren, en selecteer uw groepen.

    ![Schermopname van opties waarmee u groepen kunt opnemen in of uitsluiten van een profieltoewijzing](./media/device-profile-assign/group-include-exclude.png)

5. U moet vervolgens de wijzigingen **Opslaan**.

### <a name="evaluate-how-many-users-are-targeted"></a>Evalueren op hoeveel gebruikers een beleid is gericht

Als u het profiel toewijst, kunt u ook **Evalueren** hoeveel gebruikers moeten worden beïnvloed. Met deze functie worden gebruikers berekend, geen apparaten.

1. Selecteer in het beheercentrum **Apparaten** > **Configuratieprofielen**.
2. Selecteer een profiel > **Toewijzingen** > **Evalueren**. In een bericht wordt weergegeven op hoeveel gebruikers dit profiel is gericht.

Als de knop **Evalueren** is uitgeschakeld, controleert u of het profiel is toegewezen aan een of meer groepen.

## <a name="use-scope-tags-or-applicability-rules"></a>Bereiktags of toepasselijkheidsregels gebruiken

Wanneer u een profiel maakt of bijwerkt, kunt u ook bereiktags en toepasselijkheidsregels toevoegen aan het profiel.

**Bereiktags** zijn een uitstekende manier om profielen te filteren op specifieke groepen, zoals `US-NC IT Team` of `JohnGlenn_ITDepartment`. [RBAC en bereiktags gebruiken voor gedistribueerde IT](../fundamentals/scope-tags.md) heeft meer informatie.

U kunt op Windows 10-apparaten **toepasselijkheidsregels** toevoegen, zodat het profiel alleen van toepassing is op een specifieke versie van het besturingssysteem of een specifieke Windows-editie. [Toepasbaarheidsregels](device-profile-create.md#applicability-rules) bevat meer informatie.

## <a name="user-groups-vs-device-groups"></a>Gebruikersgroepen versus apparaatgroepen

Veel gebruikers vragen wanneer ze gebruikersgroepen moeten gebruiken en wanneer ze apparaatgroepen moeten gebruiken. Het antwoord is afhankelijk van uw doel. Hier volgen enkele richtlijnen die u op weg helpen.

### <a name="device-groups"></a>Device groups

Als u instellingen wilt toepassen op een apparaat, ongeacht wie zich heeft aangemeld, moet u de profielen aan een apparaatgroep toewijzen. Instellingen die worden toegepast op apparaatgroepen blijven voor het apparaat gelden, en niet voor de gebruiker.

Bijvoorbeeld:

- Apparaatgroepen zijn handig voor het beheren van apparaten die geen toegewezen gebruiker hebben. Als u bijvoorbeeld apparaten hebt waarmee tickets worden afgedrukt, voorraad wordt gescand, die door ploegmedewerkers worden gedeeld, aan een specifiek magazijn zijn toegewezen enzovoort. Plaats deze apparaten in een apparaatgroep en wijs uw profielen toe aan deze apparaatgroep.

- U maakt een [DFCI-Intune-profiel (Device Firmware Configuration Interface)](device-firmware-configuration-interface-windows.md) waarmee de instellingen in het BIOS worden bijgewerkt. U kunt dit profiel bijvoorbeeld configureren om de camera van het apparaat uit te schakelen, of ter vergrendeling van de opstartopties om te voorkomen dat gebruikers een ander besturingssysteem opstarten. Dit profiel is een goed scenario om aan een apparaatgroep toe te wijzen.

- Op een aantal specifieke Windows-apparaten wilt u altijd bepaalde instellingen voor Microsoft Edge kunnen beheren, ongeacht wie het apparaat gebruikt. U wilt bijvoorbeeld alle downloads blokkeren, alle cookies beperken tot de huidige browsersessie en de browsegeschiedenis verwijderen. Voor dit scenario plaatst u deze specifieke Windows-apparaten in een apparaatgroep. Maak vervolgens een [beheersjabloon in Intune](administrative-templates-windows.md), voeg deze apparaatinstellingen toe en wijs dit profiel vervolgens toe aan de apparaatgroep.

Gebruik apparaatgroepen dus wanneer u niet weet wie zich op het apparaat heeft aangemeld of dat er überhaupt iemand is aangemeld. U wilt dat uw instellingen zich altijd op het apparaat bevinden.

### <a name="user-groups"></a>Gebruikersgroepen

Profielinstellingen die worden toegepast op gebruikersgroepen, gaan altijd mee met de gebruiker, en met de gebruiker als deze op een van zijn vele apparaten is aangemeld. Het is normaal dat gebruikers veel apparaten hebben, zoals een Surface Pro voor op het werk en een persoonlijk iOS-apparaat. En het is normaal dat een persoon vanaf deze apparaten toegang heeft tot e-mail en andere bronnen van de organisatie.

Bijvoorbeeld:

- U wilt een helpdeskpictogram voor alle gebruikers op al hun apparaten plaatsen. In dit scenario plaatst u deze gebruikers in een gebruikersgroep en wijst u het profiel van het helpdeskpictogram toe aan deze gebruikersgroep.
- Een gebruiker ontvangt een nieuw apparaat dat eigendom is van de organisatie. De gebruiker meldt zich aan bij het apparaat met zijn domeinaccount. Het apparaat wordt automatisch geregistreerd bij Azure AD en automatisch beheerd door Intune. Dit profiel is een goed scenario om aan een gebruikersgroep toe te wijzen.
- Wanneer een gebruiker zich aanmeldt bij een apparaat, wilt u dat u de functies in apps kunt beheren, zoals OneDrive of Office. In dit scenario wijst u de profielinstellingen voor OneDrive of Office toe aan een gebruikersgroep.

  U wilt bijvoorbeeld dat niet-vertrouwde ActiveX-besturingselementen in uw Office-apps worden geblokkeerd. U kunt een [beheersjabloon in Intune](administrative-templates-windows.md) maken, deze instelling toevoegen en dit profiel vervolgens aan een gebruikersgroep toevoegen.

Gebruik gebruikersgroepen dus wanneer u wilt dat uw instellingen en regels altijd met de gebruiker meegaan, ongeacht welk apparaat deze gebruikt.

## <a name="exclude-groups-from-a-profile-assignment"></a>Groepen uitsluiten van een profieltoewijzing

Intune-profielen voor apparaatconfiguratie bieden de mogelijkheid om groepen op te nemen en uit te sluiten van profieltoewijzing.

Het is best practice om profielen specifiek voor uw gebruikersgroepen te maken en toe te wijzen. En ook om verschillende profielen specifiek voor uw apparaatgroepen te maken en toe te wijzen. Zie [Groepen toevoegen om gebruikers en apparaten te organiseren](../fundamentals/groups-add.md) voor meer informatie over groepen.

Wanneer u profielen toewijst, gebruikt u de volgende tabel bij het opnemen en uitsluiten van groepen. Als het selectievakje is ingeschakeld, wordt de toewijzing ondersteund:

![Met ondersteunde opties kunt u groepen opnemen of uitsluiten voor profieltoewijzing](./media/device-profile-assign/include-exclude-user-device-groups.png)

### <a name="what-you-should-know"></a>Wat u moet weten

- Uitsluiten heeft voorrang op opnemen in de volgende scenario's voor gelijke groepstypen:

  - Gebruikersgroepen opnemen en uitsluiten
  - Apparaatgroepen opnemen en uitsluiten

  Bijvoorbeeld: u wijst een apparaatprofiel toe aan de gebruikersgroep **Alle zakelijke gebruikers**, maar sluit leden van de groep **Managementteam** uit. Aangezien beide groepen gebruikersgroepen zijn, krijgen **Alle zakelijke gebruikers** behalve het **Managementteam** het profiel toegewezen.

- Intune beoordeelt groepsrelaties tussen gebruikers en apparaten niet. Als u profielen aan gemengde groepen toewijst, zijn de resultaten mogelijk niet wat u wilt of verwacht.

  U kunt bijvoorbeeld een apparaatprofiel toewijzen aan de gebruikersgroep **Alle gebruikers**, maar tegelijk een apparaatgroep **Alle persoonlijke apparaten** uitsluiten. Bij deze gemengde toewijzing van een groepsprofiel krijgen **Alle gebruikers** het profiel toegewezen. De uitsluiting wordt dan niet toegepast.

  Dit betekent dat het niet raadzaam is om profielen aan gemengde groepen toe te wijzen.

## <a name="next-steps"></a>Volgende stappen

Zie [apparaatprofielen bewaken](device-profile-monitor.md) voor richtlijnen voor het bewaken van uw profielen en de apparaten waarop deze profielen worden uitgevoerd.
