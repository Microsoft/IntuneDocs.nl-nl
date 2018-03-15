---
title: Apparaatprofielen toewijzen in Microsoft Intune - Azure | Microsoft Docs
description: Azure Portal gebruiken om apparaatprofielen en beleidsregels toe te wijzen aan gebruikers en apparaten, en groepen uitsluiten voor de toewijzing van profielen in Microsoft Intune
keywords: 
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/01/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f6f5414d-0e41-42fc-b6cf-e7ad76e1e06d
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 512b9a0506241f87b5e0c19cf19cd6fe629fb291
ms.sourcegitcommit: 7e5c4d43cbd757342cb731bf691ef3891b0792b5
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/05/2018
---
# <a name="assign-user-and-device-profiles-in-microsoft-intune"></a>Gebruikers- en apparaatprofielen toewijzen in Microsoft Intune 

Wanneer u een profiel hebt gemaakt, kunt u het profiel toewijzen aan Azure Active Directory-groepen.

## <a name="assign-a-device-profile"></a>Een apparaatprofiel toewijzen

1. In [Azure Portal](https://portal.azure.com) selecteert u **Alle services** en zoekt u naar **Microsoft Intune**.
2. In **Microsoft Intune** selecteert u **Apparaatconfiguratie** en vervolgens **Profielen**. 
3. In de lijst met profielen selecteert u het profiel dat u wilt toewijzen en selecteer vervolgens **Toewijzingen**.
4. Kies ervoor om groepen **op te nemen** of **uit te sluiten**. Klik vervolgens op **Groepen selecteren**:  

    ![Groepen opnemen in of uitsluiten van een profieltoewijzing](./media/group-include-exclude.png)

5. Wanneer u uw groepen hebt geselecteerd, kiest u een Azure Active Directory-groep. U kunt **Ctrl** ingedrukt houden om meerdere groepen te selecteren.
6. Wanneer u klaar bent, klikt u op **Opslaan** om de wijzigingen op te slaan.

## <a name="exclude-groups-from-a-profile-assignment"></a>Groepen uitsluiten van een profieltoewijzing

Intune-profielen voor apparaatconfiguratie bieden de mogelijkheid om groepen uit te sluiten van beleidstoewijzing. U kunt bijvoorbeeld een apparaatprofiel toewijzen aan de groep **Alle zakelijke gebruikers**, maar leden van de groep **Senior Management** uitsluiten van deze groep.

Als u groepen van een toewijzing uitsluit, u alleen gebruikers uitsluit of u alleen apparaatgroepen uitsluit (geen combinatie van groepen), wordt in Intune geen rekening gehouden met gebruiker-apparaatrelaties. Als u gebruikersgroepen opneemt en tegelijkertijd apparaatgroepen uitsluit, behaalt u waarschijnlijk niet de verwachte resultaten. In situaties waarin gemengde groepen worden gebruikt, of waar sprake is van andere conflicten, heeft opnemen prioriteit over uitsluiten.

Stel dat u een apparaatprofiel wilt toewijzen aan alle apparaten in uw organisatie, met uitzondering van kioskapparaten. U moet dan de groep **Alle gebruikers** opnemen, maar de groep **Alle apparaten** uitsluiten.

In dit geval krijgen alle gebruikers en hun apparaten het beleid, zelfs als het apparaat van de gebruiker deel uitmaakt van de groep **Alle apparaten**. 

Bij uitsluiting wordt alleen gekeken naar de directe leden van de groepen en worden geen apparaten opgenomen die aan een gebruiker zijn gekoppeld. Het apparaat wordt echter niet toegepast op apparaten zonder gebruiker. Dit is het geval omdat die apparaten geen relatie hebben met de groep **Alle gebruikers**. 

Als u **Alle apparaten** opneemt, maar **Alle gebruikers** uitsluit, ontvangen alle apparaten het beleid. De bedoeling is hier om dit beleid niet toe te wijzen aan apparaten waaraan een gebruiker is gekoppeld. Hierbij worden echter de apparaten niet uitgesloten, omdat bij uitsluiten alleen directe groepsleden worden vergeleken. 

>[!TIP]
>Uitsluitingen zijn niet beschikbaar voor nalevingsbeleid of app-toewijzing. Als u leden wilt uitsluiten van een toewijzing, kunt u de toewijzingen **Beschikbaar** en **Niet van toepassing** gebruiken. Stel dat u een app toewijst aan **Alle zakelijke gebruikers** met de reden **Beschikbaar**, en aan **Senior Management** met de reden **Niet van toepassing**. De app wordt dan toegewezen aan alle gebruikers *behalve* gebruikers in de groep **Senior Management**. Als u de app toewijst aan **Alle zakelijke gebruikers** met de reden **Vereist**, worden de gebruikers in de groep **Senior Management** ook ingesloten.
    
## <a name="next-steps"></a>Volgende stappen
Zie [Apparaatprofielen bewaken](device-profile-monitor.md) voor informatie over het bewaken van apparaatprofieltoewijzingen.