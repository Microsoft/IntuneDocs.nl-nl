---
title: Apparaatprofielen toewijzen in Intune
titleSuffix: Intune on Azure
description: Zodra u een Intune-apparaatprofiel hebt gemaakt, gebruikt u dit onderwerp voor informatie over hoe u dit profiel kunt toewijzen aan apparaten.
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 07/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f6f5414d-0e41-42fc-b6cf-e7ad76e1e06d
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: cf6bd6cb301491c031e382236eee509e17f08383
ms.sourcegitcommit: fd5b7aa26446d2fa92c21638cb29371e43fe169f
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/06/2017
---
# <a name="how-to-assign-microsoft-intune-device-profiles"></a>Microsoft Intune-apparaatprofielen toewijzen

## <a name="assign-a-device-profile"></a>Een apparaatprofiel toewijzen

1. Meld u aan bij Azure Portal.
2. Kies **Meer services** > **Bewaking en beheer** > **Intune**.
3. Kies op de blade **Intune** de optie **Apparaatconfiguratie**.
1. Kies **Beheren** > **Profielen** op de blade **Apparaatconfiguratie**.
2. Kies op de blade met de profielenlijst het profiel dat u wilt beheren en kies **Beheren** > **Toewijzingen** op de blade <*profielnaam*> **Rapporten**.
3. Kies op de volgende blade **Opnemen** (als u groepen wilt opnemen) of **Uitsluiten** (als u groepen wilt uitsluiten), en kies vervolgens **Groepen selecteren**.
![Groepen opnemen in en uitsluiten van een profieltoewijzing.](./media/group-include-exclude.png)
4. Kies op de blade **Groepen selecteren** de Azure AD-groepen die u wilt opnemen in of uitsluiten van de toewijzing. U kunt **Ctrl** ingedrukt houden om meerdere groepen te selecteren.
4. Kies wanneer u klaar bent **Selecteren** op de blade **Groepen selecteren**.



## <a name="how-to-exclude-groups-from-a-device-profile-assignment"></a>Groepen uitsluiten van een apparaatprofieltoewijzing

Intune-profielen voor apparaatconfiguratie bieden de mogelijkheid om groepen uit te sluiten van beleidstoewijzing. U kunt bijvoorbeeld een apparaatprofiel toewijzen aan de groep **Alle zakelijke gebruikers**, maar leden van de groep **Senior Management** uitsluiten van deze groep.

Wanneer u groepen uitsluit van een toewijzing, moet u alleen groepen gebruikers of alleen groepen apparaten uitsluiten, niet een combinatie van groepen. Intune houdt geen rekening gehouden met eventuele koppelingen van gebruikers aan apparaten bij het uitsluiten van groepen. Als u gebruikersgroepen opneemt en tegelijkertijd apparaatgroepen uitsluit, is het onwaarschijnlijk dat dit de gewenste resultaten oplevert. In situaties waarin gemengde groepen worden gebruikt, of waar sprake is van andere conflicten, heeft opnemen prioriteit over uitsluiten.

Stel dat u een apparaatprofiel wilt toewijzen aan alle apparaten in uw organisatie, met uitzondering van kioskapparaten. U moet dan de groep **Alle gebruikers** opnemen, maar de groep **Alle apparaten** uitsluiten.

In dit geval krijgen alle gebruikers en hun apparaten het beleid, zelfs als het apparaat van de gebruiker deel uitmaakt van de groep **Alle apparaten**. 

Bij uitsluiting worden alleen de directe leden van de groepen geëvalueerd en worden geen apparaten opgenomen die aan een gebruiker zijn gekoppeld. Apparaten zonder gebruiker krijgen het beleid echter niet omdat ze geen koppeling hebben met de groep **Alle gebruikers**. 

Als u **Alle apparaten** opneemt, maar **Alle gebruikers** uitsluit, ontvangen alle apparaten het beleid. De bedoeling is hier om dit beleid niet toe te wijzen aan apparaten waaraan een gebruiker is gekoppeld. Dit gebeurt echter niet omdat bij uitsluiten zoals gezegd alleen directe groepsleden worden vergeleken. 

>[!Tip]
>Uitsluitingen zijn momenteel niet beschikbaar voor nalevingsbeleid of app-toewijzing. Als u leden wilt uitsluiten van een toewijzing, kunt u de toewijzingsredenen Beschikbaar en Niet van toepassing gebruiken. Stel dat u een app toewijst aan **Alle zakelijke gebruikers** met de reden **Beschikbaar**, en aan **Senior Management** met de reden **Niet van toepassing**. De app wordt dan toegewezen aan alle gebruikers *behalve* gebruikers in de groep **Senior Management personeel**. Als u de app toewijst aan **Alle zakelijke gebruikers** met de reden **Vereist**, worden de gebruikers in de groep **Senior Management** niet uitgesloten.
 
    
## <a name="next-steps"></a>Volgende stappen
Zie [Apparaatprofielen controleren](device-profile-monitor.md) voor informatie over het controleren van apparaatprofieltoewijzingen.
