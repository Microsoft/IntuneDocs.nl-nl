---
title: Apparaatprofielen toewijzen in Microsoft Intune - Azure | Microsoft Docs
description: Gebruik Azure Portal om apparaatprofielen en beleidsregels aan gebruikers en apparaten toe te wijzen. Informatie over het uitsluiten van groepen uit een profieltoewijzing in Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 09/17/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: f6f5414d-0e41-42fc-b6cf-e7ad76e1e06d
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: db1f0944a6725d1f361ea20c972d8ffa8f5d9035
ms.sourcegitcommit: a50a1ca123ecc2c5ac129f112f73838748f56476
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/10/2019
ms.locfileid: "72237217"
---
# <a name="assign-user-and-device-profiles-in-microsoft-intune"></a>Gebruikers- en apparaatprofielen toewijzen in Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

U maakt een profiel en dit omvat alle instellingen die u hebt ingevoerd. De volgende stap is het implementeren of toewijzen van het profiel aan uw gebruikers- of apparaatgroepen in Azure AD (Active Directory). Wanneer het is toegewezen, ontvangen de gebruikers en apparaten uw profiel, en worden de ingevoerde instellingen toegewezen.

In dit artikel ziet u hoe u een profiel kunt toewijzen, en krijgt u informatie over het gebruik van bereiktags in uw profielen.

> [!NOTE]  
> Wanneer beleid wordt verwijderd of niet meer is toegewezen aan een apparaat, behoudt de instelling mogelijk de bestaande waarde. De instelling wordt niet teruggezet naar een standaardwaarde. Als u de instelling wilt wijzigen in een andere waarde, maakt u nieuw beleid en wijst u dit toe.

## <a name="assign-a-device-profile"></a>Een apparaatprofiel toewijzen

1. Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Selecteer **Apparaatconfiguratie** > **Profielen**. Alle profielen worden vermeld.
3. Selecteer het profiel dat u wilt toewijzen > **Toewijzingen**.
4. Geef aan of u groepen wilt **Opnemen** of **Uitsluiten** en selecteer vervolgens uw groepen. Wanneer u uw groepen hebt geselecteerd, kiest u een Azure AD-groep. Houd **Ctrl** ingedrukt om meerdere groepen te selecteren, en selecteer uw groepen.

    ![Schermopname van opties waarmee u groepen kunt opnemen in of uitsluiten van een profieltoewijzing](./media/device-profile-assign/group-include-exclude.png)

5. U moet vervolgens de wijzigingen **Opslaan**.

### <a name="evaluate-how-many-users-are-targeted"></a>Evalueren op hoeveel gebruikers een beleid is gericht

Als u het profiel toewijst, kunt u ook **Evalueren** hoeveel gebruikers moeten worden beïnvloed. Met deze functie worden gebruikers berekend, geen apparaten.

1. Selecteer in Intune **Apparaatconfiguratie** > **Profielen**.
2. Selecteer een profiel > **Toewijzingen** > **Evalueren**. In een bericht wordt weergegeven op hoeveel gebruikers dit profiel is gericht.

Als de knop **Evalueren** is uitgeschakeld, controleert u of het profiel is toegewezen aan een of meer groepen.

## <a name="use-scope-tags-or-applicability-rules"></a>Bereiktags of toepasselijkheidsregels gebruiken

Wanneer u een profiel maakt of bijwerkt, kunt u ook bereiktags en toepasselijkheidsregels toevoegen aan het profiel.

Met **bereiktags** kunt u eenvoudig beleid toewijzen aan en filteren voor specifieke groepen, zoals Human Resources of Alle NL-AMST-werknemers. [RBAC en bereiktags gebruiken voor gedistribueerde IT](../fundamentals/scope-tags.md) heeft meer informatie.

U kunt op Windows 10-apparaten **toepasselijkheidsregels** toevoegen, zodat het profiel alleen van toepassing is op een specifieke versie van het besturingssysteem of een specifieke Windows-editie. [Toepasbaarheidsregels](device-profile-create.md#applicability-rules) bevat meer informatie.

## <a name="exclude-groups-from-a-profile-assignment"></a>Groepen uitsluiten van een profieltoewijzing

Intune-profielen voor apparaatconfiguratie bieden de mogelijkheid om groepen uit te sluiten van beleidstoewijzing.

In Intune wordt niet gekeken naar groepsrelaties tussen gebruiker en apparaat. Als u gebruikersgroepen opneemt en tegelijkertijd apparaatgroepen uitsluit, krijgt u mogelijk niet de verwachte resultaten. In de scenario’s voor gebruikersgroep-naar-gebruikersgroep en apparaatgroep-naar-apparaatgroep heeft uitsluiting prioriteit boven insluiting.

Bijvoorbeeld: u wijst een apparaatprofiel toe aan de gebruikersgroep **Alle zakelijke gebruikers**, maar sluit leden van de groep **Managementteam** uit. Aangezien beide groepen gebruikersgroepen zijn, worden alle leden van het **Managementteam** uitgesloten van het beleid, zelfs al zijn ze lid van de opgenomen groep **Alle zakelijke gebruikers**.

Insluiting heeft prioriteit boven uitsluiting wanneer u een gemengde groep gebruikt, zoals gebruikersgroep-naar-apparaatgroep, of apparaatgroep-naar-gebruikersgroep.

Stel dat u een apparaatprofiel wilt toewijzen aan alle gebruikers in uw organisatie, met uitzondering van kioskapparaten. U moet dan de groep **Alle gebruikers** opnemen, maar de groep **Alle apparaten** uitsluiten. In dit geval krijgen alle gebruikers en hun apparaten het beleid, zelfs als het apparaat van de gebruiker zich in de groep **Alle apparaten** bevindt.

Bij uitsluiting wordt er alleen gekeken naar de directe leden van de groep. Apparaten die zijn gekoppeld aan een gebruiker, worden niet opgenomen. Het beleid wordt echter niet toegepast op apparaten zonder gebruiker. Dit gedrag vindt plaats, omdat apparaten geen relatie hebben met de groep **Alle gebruikers**.

Als u **Alle apparaten** opneemt, maar **Alle gebruikers** uitsluit, ontvangen alle apparaten het beleid. De bedoeling is hier om dit beleid niet toe te wijzen aan apparaten waaraan een gebruiker is gekoppeld. Hierbij worden echter de apparaten niet uitgesloten, omdat bij uitsluiten alleen directe groepsleden worden vergeleken.

## <a name="next-steps"></a>Volgende stappen

Zie [apparaatprofielen bewaken](device-profile-monitor.md) voor richtlijnen voor het bewaken van uw profielen en de apparaten waarop deze profielen worden uitgevoerd.
