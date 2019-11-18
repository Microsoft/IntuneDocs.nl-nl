---
title: Apparaatprofielen toewijzen in Microsoft Intune - Azure | Microsoft Docs
description: Gebruik Azure Portal om apparaatprofielen en beleidsregels aan gebruikers en apparaten toe te wijzen. Informatie over het uitsluiten van groepen uit een profieltoewijzing in Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/05/2019
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
ms.openlocfilehash: 50b91251572e45669f197df7ac4e5ff94caf47a1
ms.sourcegitcommit: 1a7f04c80548e035be82308d2618492f6542d3c0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/07/2019
ms.locfileid: "73755332"
---
# <a name="assign-user-and-device-profiles-in-microsoft-intune"></a>Gebruikers- en apparaatprofielen toewijzen in Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

U maakt een profiel en dit omvat alle instellingen die u hebt ingevoerd. De volgende stap is het implementeren of toewijzen van het profiel aan uw gebruikers- of apparaatgroepen in Azure AD (Active Directory). Wanneer het is toegewezen, ontvangen de gebruikers en apparaten uw profiel, en worden de ingevoerde instellingen toegewezen.

In dit artikel ziet u hoe u een profiel kunt toewijzen, en krijgt u informatie over het gebruik van bereiktags in uw profielen.

> [!NOTE]  
> Wanneer beleid wordt verwijderd of niet meer is toegewezen aan een apparaat, behoudt de instelling mogelijk de bestaande waarde. De instelling wordt niet teruggezet naar een standaardwaarde. Als u de instelling wilt wijzigen in een andere waarde, maakt u nieuw beleid en wijst u dit toe.

## <a name="before-you-begin"></a>Voordat u begint

Zorg ervoor dat u de juiste rol hebt om beleid toe te wijzen. Zie [Op rollen gebaseerd toegangsbeheer (RBAC) met Microsoft Intune](../fundamentals/role-based-access-control.md) voor meer informatie.

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

Met **bereiktags** kunt u eenvoudig beleid toewijzen aan en filteren voor specifieke groepen, zoals Human Resources of Alle NL-AMST-werknemers. [RBAC en bereiktags gebruiken voor gedistribueerde IT](../fundamentals/scope-tags.md) heeft meer informatie.

U kunt op Windows 10-apparaten **toepasselijkheidsregels** toevoegen, zodat het profiel alleen van toepassing is op een specifieke versie van het besturingssysteem of een specifieke Windows-editie. [Toepasbaarheidsregels](device-profile-create.md#applicability-rules) bevat meer informatie.

## <a name="exclude-groups-from-a-profile-assignment"></a>Groepen uitsluiten van een profieltoewijzing

Intune-profielen voor apparaatconfiguratie bieden de mogelijkheid om groepen op te nemen en uit te sluiten van beleidstoewijzing.

De aanbevolen procedure is om beleid specifiek voor uw gebruikersgroepen te maken en toe te wijzen. En ook om verschillende beleidsregels specifiek voor uw apparaatgroepen te maken en toe te wijzen. Zie [Groepen toevoegen om gebruikers en apparaten te organiseren](../fundamentals/groups-add.md) voor meer informatie over groepen.

Wanneer u beleid toewijst, gebruikt u de volgende tabel bij het opnemen en uitsluiten van groepen. Als het selectievakje is ingeschakeld, wordt de toewijzing ondersteund:

![Met ondersteunde opties kunt u groepen opnemen of uitsluiten voor profieltoewijzing](./media/device-profile-assign/include-exclude-user-device-groups.png)

### <a name="what-you-should-know"></a>Wat u moet weten

- Uitsluiten heeft voorrang op opnemen in de volgende scenario's voor gelijke groepstypen:

  - Gebruikersgroepen opnemen en uitsluiten
  - Apparaatgroepen opnemen en uitsluiten

  Bijvoorbeeld: u wijst een apparaatprofiel toe aan de gebruikersgroep **Alle zakelijke gebruikers**, maar sluit leden van de groep **Managementteam** uit. Aangezien beide groepen gebruikersgroepen zijn, krijgen **Alle zakelijke gebruikers** behalve het **Managementteam** het beleid toegewezen.

- Intune beoordeelt groepsrelaties tussen gebruikers en apparaten niet. Als u beleid aan gemengde groepen toewijst, zijn de resultaten mogelijk niet wat u wilt of verwacht.

  U kunt bijvoorbeeld een apparaatprofiel toewijzen aan de gebruikersgroep **Alle gebruikers**, maar tegelijk een apparaatgroep **Alle persoonlijke apparaten** uitsluiten. Bij deze gemengde toewijzing van groepsbeleid krijgen **Alle gebruikers** het beleid toegewezen. De uitsluiting wordt dan niet toegepast.

  Dit betekent dat het niet raadzaam is om beleid aan gemengde groepen toe te wijzen.

## <a name="next-steps"></a>Volgende stappen

Zie [apparaatprofielen bewaken](device-profile-monitor.md) voor richtlijnen voor het bewaken van uw profielen en de apparaten waarop deze profielen worden uitgevoerd.
