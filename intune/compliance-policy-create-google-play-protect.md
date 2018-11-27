---
title: Naleving Google Play Protect voor Microsoft Intune inschakelen
titleSuffix: ''
description: Meer informatie over het maken van nalevingsbeleid voor Android-apparaten om Google Play Protect in te schakelen.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: E9810BEB-000A-4DFB-B5C7-A22A92082B22
ms.reviewer: muhosabe
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: e8c3c0d511439d6b18c7f04e5a493e2851d7997f
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/20/2018
ms.locfileid: "52179443"
---
# <a name="how-to-create-a-device-compliance-policy-to-enable-google-play-protect"></a>Meer informatie over het maken van een nalevingsbeleid voor apparaten om Google Play Protect in te schakelen

U kunt een nieuw nalevingsbeleid maken voor het Android-platform om te controleren op naleving van Google Play Protect (GPP).

Het nalevingsbeleid dat deze instellingen vereist kan vervolgens worden gericht op een groep Android-gebruikers of -apparaten. Als deze instellingen niet voor een apparaat zijn ingeschakeld, voldoet dit niet aan het nalevingsbeleid.

## <a name="create-a-compliance-policy"></a>Een nalevingsbeleid maken

1. Meld u aan bij de [Azure-portal](https://portal.azure.com).
2. Kies **Alle services** > **Intune**. Intune bevindt zich in de sectie **Controle en beheer**.
2. Kies **Apparaatnaleving** in de groep **Beheren**. 
3. Kies **Beleid** en vervolgens **Beleid maken**.
4. Geef een **Naam** en **Beschrijving** op voor het beleid.
5. Selecteer **Android** bij Platform.
6. Kies **Instellingen** > **Apparaatstatus**.
7. Configureer de instellingen voor **Google Play Protect**.
8. Wanneer u de instellingen voor Google Play Protect hebt ingesteld, geeft u vervolgens de instellingen voor **Systeembeveiliging** en **Apparaateigenschappen** op. Kies **OK** als u klaar bent.

## <a name="configure-the-google-play-protect-settings"></a>De instellingen voor Google Play Protect configureren

 - **Google Play Services is geconfigureerd**  
   Hiermee kunt u vereisen dat de app Google Play Services is geïnstalleerd en ingeschakeld. Google Play Services maakt beveiligingsupdates mogelijk en vormt een basisafhankelijkheid voor veel beveiligingsfuncties op door Google gecertificeerde apparaten.
 - **Bijgewerkte beveiligingsprovider**  
   Hiermee kunt u vereisen dat het apparaat tegen bekende beveiligingsproblemen wordt beschermd door een bijgewerkte beveiligingsprovider.
 - **Bedreigingsscan voor apps**  
   Hiermee kunt u vereisen dat de Android-functie **Apps controleren** is ingeschakeld.
    > [!Note]  
    > Deze functie is op oudere Android-platforms een nalevingsinstelling. Intune kan alleen controleren of deze instelling is ingeschakeld op het apparaatniveau. Op apparaten met een Android-werkprofiel is deze instelling te vinden als een configureerbare beleidsinstelling. Hiermee kunnen beheerders de instelling voor een apparaat inschakelen.

    Als uw bedrijf Android-werkprofielen gebruikt, kunt u **Bedreigingsscan voor apps** inschakelen voor uw geregistreerde apparaten. Hiermee kunt u een apparaatprofiel instellen en de systeembeveiligingsinstelling verplicht stellen. Zie [Apparaatbeperkingsinstellingen voor Android-werkprofielen in Microsoft Intune](device-restrictions-android-for-work.md) voor meer informatie.

 - **SafetyNet-attestation voor apparaat**  
   Hiermee kunt u instellen aan welk integriteitsniveau voor SafetyNet-attestation het apparaat moet voldoen. Deze niveaus zijn onder andere **Niet geconfigureerd**, **Eenvoudige integriteitscontrole** en **Eenvoudige integriteitscontrole & gecertificeerde apparaten**.




## <a name="next-steps"></a>Volgende stappen

Ga naar [Aan de slag met Intune-apparaatnalevingsbeleid](device-compliance-get-started.md) voor meer informatie over Intune-beleidsregels voor apparaatnaleving.