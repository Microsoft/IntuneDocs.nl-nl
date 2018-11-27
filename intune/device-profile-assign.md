---
title: Apparaatprofielen toewijzen in Microsoft Intune - Azure | Microsoft Docs
description: Gebruik Azure Portal om apparaatprofielen en beleidsregels aan gebruikers en apparaten toe te wijzen. Informatie over het uitsluiten van groepen uit een profieltoewijzing in Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/01/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f6f5414d-0e41-42fc-b6cf-e7ad76e1e06d
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 2cd71eabf3efeb6b3eaa897745ed0441c456cd60
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/20/2018
ms.locfileid: "52182292"
---
# <a name="assign-user-and-device-profiles-in-microsoft-intune"></a>Gebruikers- en apparaatprofielen toewijzen in Microsoft Intune

Wanneer u een profiel hebt gemaakt, kunt u het profiel toewijzen aan Azure AD-groepen (Azure Active Directory).

## <a name="assign-a-device-profile"></a>Een apparaatprofiel toewijzen

1. In [Azure Portal](https://portal.azure.com) selecteert u **Alle services** en zoekt u naar **Microsoft Intune**.
2. In **Microsoft Intune** selecteert u **Apparaatconfiguratie** en vervolgens **Profielen**.
3. In de lijst met profielen selecteert u het profiel dat u wilt toewijzen en selecteer vervolgens **Toewijzingen**.
4. Geef aan of u groepen wilt **opnemen** of **uitsluiten** en selecteer vervolgens de gewenste groepen.  

    ![Schermopname van opties waarmee u groepen kunt opnemen in of uitsluiten van een profieltoewijzing](./media/group-include-exclude.png)

5. Wanneer u uw groepen hebt geselecteerd, kiest u een Azure AD-groep. Houd **Ctrl** ingedrukt om meerdere groepen te selecteren.
6. Selecteer **Opslaan** wanneer u klaar bent.

## <a name="exclude-groups-from-a-profile-assignment"></a>Groepen uitsluiten van een profieltoewijzing

Intune-profielen voor apparaatconfiguratie bieden de mogelijkheid om groepen uit te sluiten van beleidstoewijzing. U kunt bijvoorbeeld een apparaatprofiel toewijzen aan de groep **Alle zakelijke gebruikers**, maar leden van de groep **Senior Management** uitsluiten van deze groep.

Als u groepen van een toewijzing uitsluit, u alleen gebruikers uitsluit of u alleen apparaatgroepen uitsluit (geen combinatie van groepen), wordt in Intune geen rekening gehouden met gebruiker-apparaatrelaties. Als u gebruikersgroepen opneemt en tegelijkertijd apparaatgroepen uitsluit, behaalt u waarschijnlijk niet de verwachte resultaten. In situaties waarin gemengde groepen worden gebruikt, of waar sprake is van andere conflicten, heeft opnemen prioriteit over uitsluiten.

Stel dat u een apparaatprofiel wilt toewijzen aan alle apparaten in uw organisatie, met uitzondering van kioskapparaten. U moet dan de groep **Alle gebruikers** opnemen, maar de groep **Alle apparaten** uitsluiten. In dit geval krijgen alle gebruikers en hun apparaten het beleid, zelfs als het apparaat van de gebruiker deel uitmaakt van de groep **Alle apparaten**.

Bij uitsluiting wordt alleen gekeken naar de directe leden van de groepen en worden geen apparaten opgenomen die aan een gebruiker zijn gekoppeld. Het apparaat wordt echter niet toegepast op apparaten zonder gebruiker. Dit is het geval omdat die apparaten geen relatie hebben met de groep **Alle gebruikers**.

Als u **Alle apparaten** opneemt, maar **Alle gebruikers** uitsluit, ontvangen alle apparaten het beleid. De bedoeling is hier om dit beleid niet toe te wijzen aan apparaten waaraan een gebruiker is gekoppeld. Hierbij worden echter de apparaten niet uitgesloten, omdat bij uitsluiten alleen directe groepsleden worden vergeleken.

## <a name="next-steps"></a>Volgende stappen
Zie [Apparaatprofielen bewaken](device-profile-monitor.md) voor informatie over het bewaken van apparaatprofieltoewijzingen.
