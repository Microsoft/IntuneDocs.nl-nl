---
title: Apparaatprofielen toewijzen in Microsoft Intune - Azure | Microsoft Docs
description: Gebruik Azure Portal om apparaatprofielen en beleidsregels aan gebruikers en apparaten toe te wijzen. Informatie over het uitsluiten van groepen uit een profieltoewijzing in Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/08/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: f6f5414d-0e41-42fc-b6cf-e7ad76e1e06d
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0c950efdd95fd8d856ec677385712a022dead870
ms.sourcegitcommit: 02803863eba37ecf3d8823a7f1cd7c4f8e3bb42c
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/09/2019
ms.locfileid: "59570504"
---
# <a name="assign-user-and-device-profiles-in-microsoft-intune"></a>Gebruikers- en apparaatprofielen toewijzen in Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

U maakt een profiel en dit omvat alle instellingen die u hebt ingevoerd. De volgende stap is het implementeren of toewijzen van het profiel aan uw gebruikers- of apparaatgroepen in Azure AD (Active Directory). Wanneer het is toegewezen, ontvangen de gebruikers en apparaten uw profiel, en worden de ingevoerde instellingen toegewezen.

In dit artikel ziet u hoe u een profiel kunt toewijzen, en krijgt u informatie over het gebruik van bereiktags in uw profielen.

## <a name="assign-a-device-profile"></a>Een apparaatprofiel toewijzen

1. Selecteer in [Azure Portal](https://portal.azure.com) de optie **Alle services** > filter op **Intune** > selecteer **Intune**.
2. Selecteer **Apparaatconfiguratie** > **Profielen**. Alle profielen worden vermeld.
3. Selecteer het profiel dat u wilt toewijzen > **Toewijzingen**.
4. Geef aan of u groepen wilt **Opnemen** of **Uitsluiten** en selecteer vervolgens uw groepen. Wanneer u uw groepen hebt geselecteerd, kiest u een Azure AD-groep. Houd **Ctrl** ingedrukt om meerdere groepen te selecteren, en selecteer uw groepen.

    ![Schermopname van opties waarmee u groepen kunt opnemen in of uitsluiten van een profieltoewijzing](./media/group-include-exclude.png)

5. U moet vervolgens de wijzigingen **Opslaan**.

### <a name="evaluate-how-many-users-are-targeted"></a>Evalueren op hoeveel gebruikers een beleid is gericht

Als u het profiel toewijst, kunt u ook **Evalueren** hoeveel gebruikers moeten worden beïnvloed. Met deze functie worden gebruikers berekend, geen apparaten.

1. Selecteer in Intune **Apparaatconfiguratie** > **Profielen**.
2. Selecteer een profiel > **Toewijzingen** > **Evalueren**. In een bericht wordt weergegeven op hoeveel gebruikers dit profiel is gericht.

Als de knop **Evalueren** is uitgeschakeld, controleert u of het profiel is toegewezen aan een of meer groepen.


## <a name="use-scope-tags"></a>Bereiktags gebruiken

Wanneer u een profiel maakt of bijwerkt, kunt u ook bereiktags toevoegen aan het profiel.

Met **bereiktags** kunt u eenvoudig beleid toewijzen aan en filteren voor specifieke groepen, zoals Human Resources of Alle NL-AMST-werknemers. [RBAC en bereiktags gebruiken voor gedistribueerde IT](scope-tags.md) heeft meer informatie.

## <a name="exclude-groups-from-a-profile-assignment"></a>Groepen uitsluiten van een profieltoewijzing

Intune-profielen voor apparaatconfiguratie bieden de mogelijkheid om groepen uit te sluiten van beleidstoewijzing. U kunt bijvoorbeeld een apparaatprofiel toewijzen aan de groep **Alle zakelijke gebruikers**, maar de leden van de groep **Senior Management** uitsluiten.

Als u groepen, alleen gebruikers- of alleen apparaatgroepen (en geen combinatie van groepen), uitsluit van een toewijzing, wordt er in Intune niet gekeken naar de relatie tussen gebruikers en apparaten. Als u gebruikersgroepen opneemt en tegelijkertijd apparaatgroepen uitsluit, krijgt u mogelijk niet de verwachte resultaten. Als u gemengde groepen gebruikt, of als er sprake is van andere conflicten, heeft opnemen prioriteit over uitsluiten.

Stel dat u een apparaatprofiel wilt toewijzen aan alle apparaten in uw organisatie, met uitzondering van kioskapparaten. U moet dan de groep **Alle gebruikers** opnemen, maar de groep **Alle apparaten** uitsluiten. In dit geval krijgen alle gebruikers en hun apparaten het beleid, zelfs als het apparaat van de gebruiker zich in de groep **Alle apparaten** bevindt.

Bij uitsluiting wordt er alleen gekeken naar de directe leden van de groep. Apparaten die zijn gekoppeld aan een gebruiker, worden niet opgenomen. Het apparaat wordt echter niet toegepast op apparaten zonder gebruiker. Dit gebeurt, omdat deze apparaten geen relatie hebben met de groep **Alle gebruikers**.

Als u **Alle apparaten** opneemt, maar **Alle gebruikers** uitsluit, ontvangen alle apparaten het beleid. De bedoeling is hier om dit beleid niet toe te wijzen aan apparaten waaraan een gebruiker is gekoppeld. Hierbij worden echter de apparaten niet uitgesloten, omdat bij uitsluiten alleen directe groepsleden worden vergeleken.

## <a name="next-steps"></a>Volgende stappen

Zie [apparaatprofielen bewaken](device-profile-monitor.md) voor richtlijnen voor het bewaken van uw profielen en de apparaten waarop deze profielen worden uitgevoerd.