---
title: Gegevens selectief wissen met toegangsacties voor het app-beveiligingsbeleid
titleSuffix: Microsoft Intune
description: Meer informatie over het selectief wissen van gegevens met toegangsacties voor het app-beveiligingsbeleid in Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 07/03/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f5ca557e-a8e1-4720-b06e-837c4f0bc3ca
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 2cfd426a0ae7165a7aae60a90d104852fd834db6
ms.sourcegitcommit: 98b444468df3fb2a6e8977ce5eb9d238610d4398
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/07/2018
ms.locfileid: "37909113"
---
# <a name="selectively-wipe-data-using-app-protection-policy-access-actions-in-intune"></a>Gegevens selectief wissen met toegangsacties voor het app-beveiligingsbeleid in Intune

Met behulp van het app-beveiligingsbeleid in Intune kunt u instellingen configureren om te voorkomen dat eindgebruikers toegang hebben tot een zakelijke app of zakelijk account. Deze instellingen zijn gericht op verplaatsing van gegevens en toegangsvereisten die door uw organisatie zijn ingesteld voor zaken als opengebroken apparaten en minimale besturingssysteemversies.
 
U kunt er expliciet voor kiezen om de zakelijke gegevens van uw bedrijf te wissen van het apparaat van de eindgebruiker als een actie die moet worden uitgevoerd voor niet-naleving door deze instellingen te gebruiken. Voor sommige instellingen kunt u meerdere acties configureren, zoals de toegang blokkeren en gegevens wissen op basis van verschillende opgegeven waarden.

## <a name="create-an-app-protection-policy-using-access-actions"></a>Een app-beveiligingsbeleid maken met behulp van toegangsacties

1. Meld u aan bij [Azure Portal](https://portal.azure.com).
2. Selecteer **Alle services** > **Intune**.  
    Intune bevindt zich in de sectie **Controle en beheer**.
3. Selecteer in het deelvenster **Intune** **Mobiele apps** > **App-beveiligingsbeleid**.
4. Klik op **Een beleid toevoegen** (u kunt ook een bestaand beleid bewerken). 
5. Klik op **Vereiste instellingen configureren** om de lijst met instellingen weer te geven die voor het beleid kunnen worden geconfigureerd. 
6. Schuif omlaag in het deelvenster **Instellingen** naar de sectie met de titel **Toegangsacties** met een bewerkbare tabel.

    ![Schermafbeelding van de toegangsacties voor app-beveiliging in Intune](./media/apps-selective-wipe-access-actions01.png)

7. Selecteer een **instelling** en voer de **waarde** in waaraan gebruikers moeten voldoen om zich aan te melden bij uw bedrijfsapp. 
8. Selecteer de **actie** die u wilt uitvoeren als gebruikers niet voldoen aan uw vereisten. In sommige gevallen kunnen meerdere acties worden geconfigureerd voor één instelling. Zie [App-beveiligingsbeleid maken en toewijzen](app-protection-policies.md) voor meer informatie.

>[!NOTE]
> Als u de instelling voor **apparaatmodellen** wilt gebruiken, voert u een lijst met door puntkomma's gescheiden waarden in met modelaanduidingen. 

## <a name="policy-settings"></a>Beleidsinstellingen 

De tabel met instellingen voor het app-beveiligingsbeleid bevat kolommen voor **Instelling**, **Waarde** en **Actie**.

Voor iOS kunt u acties configureren voor de volgende instellingen met behulp van de vervolgkeuzelijst **Instelling**:
-  Maximum aantal pincodepogingen
-  Offline respijtperiode
-  Apparaten die zijn opengebroken of geroot
-  Minimale versie van het besturingssysteem
-  Minimale versie van de app
-  Minimale SDK-versie
-  Apparaatmodel(len)

Voor Android kunt u acties configureren voor de volgende instellingen met behulp van de vervolgkeuzelijst **Instelling**:
-  Maximum aantal pincodepogingen
-  Offline respijtperiode
-  Apparaten die zijn opengebroken of geroot
-  Minimale versie van het besturingssysteem
-  Minimale versie van de app
-  Minimale patchversie
-  Apparaatfabrikant(en)

Standaard worden de rijen in de tabel gevuld als instellingen die zijn geconfigureerd voor **Offline respijtperiode** en **Maximum aantal pincodepogingen** als de instelling **Pincode is vereist voor toegang** is ingesteld op **Ja**.
 
Als u een instelling wilt configureren, selecteert u een instelling in de vervolgkeuzelijst onder de kolom **Instelling**. Nadat een instelling is geselecteerd, wordt het bewerkbare tekstvak ingeschakeld onder de kolom **Waarde** in dezelfde rij als is vereist dat de waarde wordt ingesteld. Ook de vervolgkeuzelijst onder de kolom **Actie** wordt ingeschakeld met de reeks voorwaardelijke startacties die van toepassing zijn op de instelling. 

De volgende lijst bevat de algemene lijst met acties:
-  **Toegang blokkeren**: de toegang tot de bedrijfsapp wordt geblokkeerd voor de eindgebruiker.
-  **Gegevens wissen**: de bedrijfsgegevens worden van het apparaat van de eindgebruiker gewist.
-  **Waarschuwen**: de eindgebruiker ziet een dialoogvenster als een waarschuwingsbericht.

### <a name="additional-settings-and-actions"></a>Extra instellingen en acties 

In sommige gevallen, zoals voor de instelling **Minimale versie van het besturingssysteem**, kunt u de instelling zo configureren dat alle toepasselijke acties worden uitgevoerd op basis van verschillende versienummers. 

![Schermafbeelding van de toegangsacties voor app-beveiliging in Intune - Minimale versie van het besturingssysteem](./media/apps-selective-wipe-access-actions05.png)

Wanneer een instelling volledig is geconfigureerd, wordt de rij weergegeven in de alleen-lezenweergave en kan de rij op elk moment worden bewerkt. Bovendien is er voor de rij een vervolgkeuzelijst beschikbaar in de kolom **Instelling**. Instellingen die al zijn geconfigureerd en waarvoor meerdere acties niet zijn toegestaan, kunnen niet worden geselecteerd in de vervolgkeuzelijst.

## <a name="next-steps"></a>Volgende stappen

Ga voor meer informatie over het app-beveiligingsbeleid in Intune naar:
- [App-beveiligingsbeleid maken en toewijzen](app-protection-policies.md)
- [Beveiligingsbeleidsinstellingen voor iOS-apps](app-protection-policy-settings-ios.md)
- [Instellingen voor beveiligingsbeleid voor apps voor Android in Microsoft Intune](app-protection-policy-settings-android.md) 


