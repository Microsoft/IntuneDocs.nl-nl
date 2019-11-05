---
title: Gegevens wissen met acties voor voorwaardelijke toegang in app-beveiligingsbeleid
titleSuffix: Microsoft Intune
description: Meer informatie over het selectief wissen van gegevens met acties voor voorwaardelijke toegang in het app-beveiligingsbeleid in Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/24/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: f5ca557e-a8e1-4720-b06e-837c4f0bc3ca
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 882c542d6a1d981b9924bb33eee40f03b41689f7
ms.sourcegitcommit: 4bf23327af734a9811d555fbd566c31239e2acd6
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/29/2019
ms.locfileid: "72999478"
---
# <a name="selectively-wipe-data-using-app-protection-policy-conditional-launch-actions-in-intune"></a>Selectief gegevens wissen met acties voor voorwaardelijke toegang in app-beveiligingsbeleid in Intune

Met behulp van het app-beveiligingsbeleid in Intune kunt u instellingen configureren om te voorkomen dat eindgebruikers toegang hebben tot een zakelijke app of zakelijk account. Deze instellingen zijn gericht op verplaatsing van gegevens en toegangsvereisten die door uw organisatie zijn ingesteld voor zaken als opengebroken apparaten en minimale besturingssysteemversies.
 
U kunt er expliciet voor kiezen om de zakelijke gegevens van uw bedrijf te wissen van het apparaat van de eindgebruiker als een actie die moet worden uitgevoerd voor niet-naleving door deze instellingen te gebruiken. Voor sommige instellingen kunt u meerdere acties configureren, zoals de toegang blokkeren en gegevens wissen op basis van verschillende opgegeven waarden.

## <a name="create-an-app-protection-policy-using-conditional-launch-actions"></a>Een app-beveiligingsbeleid maken met acties voor voorwaardelijke toegang

1. Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
3. Selecteer in het deelvenster **Intune** **Client-apps** > **App-beveiligingsbeleid**.
4. Klik op **Een beleid toevoegen** (u kunt ook een bestaand beleid bewerken). 
5. Klik op **Vereiste instellingen configureren** om de lijst met instellingen weer te geven die voor het beleid kunnen worden geconfigureerd. 
6. Schuif omlaag in het deelvenster Instellingen naar het gedeelte met de titel **Voorwaardelijk starten** met een bewerkbare tabel.

    ![Schermafbeelding van de toegangsacties voor app-beveiliging in Intune](./media/app-protection-policies-access-actions/apps-selective-wipe-access-actions01.png)

7. Selecteer een **instelling** en voer de **waarde** in waaraan gebruikers moeten voldoen om zich aan te melden bij uw bedrijfsapp. 
8. Selecteer de **actie** die u wilt uitvoeren als gebruikers niet voldoen aan uw vereisten. In sommige gevallen kunnen meerdere acties worden geconfigureerd voor één instelling. Zie [App-beveiligingsbeleid maken en toewijzen](app-protection-policies.md) voor meer informatie.

>[!NOTE]
> Als u de instelling voor **Apparaatmodel(len) of Apparaatfabrikant(en)** wilt gebruiken, voert u een lijst met door puntkomma's gescheiden waarden in met modelaanduidingen (iOS) of apparaatfabrikanten (Android). Vermijd spaties in lijsten met meerdere waarden. Deze waarden zijn niet hoofdlettergevoelig. 

## <a name="policy-settings"></a>Beleidsinstellingen 

De tabel met instellingen voor het app-beveiligingsbeleid bevat kolommen voor **Instelling**, **Waarde** en **Actie**.

### <a name="ios-policy-settings"></a>Beleidsinstellingen voor iOS
Voor iOS kunt u acties configureren voor de volgende instellingen met behulp van de vervolgkeuzelijst **Instelling**:
- Maximum aantal pincodepogingen
- Offline respijtperiode
- Apparaten die zijn opengebroken of geroot
- Minimale versie van het besturingssysteem
- Minimale versie van de app
- Minimale SDK-versie
- Apparaatmodel(len)
- Maximaal toegestaan bedreigingsniveau van apparaat

Als u de instelling voor **apparaatmodellen** wilt gebruiken, voert u een lijst met door puntkomma's gescheiden waarden in met iOS-modelaanduidingen. U vindt de iOS-modelaanduidingen onder de kolom Apparaattype in [Ondersteuningsdocumentatie voor HockeyApp](https://support.hockeyapp.net/kb/client-integration-ios-mac-os-x-tvos/ios-device-types).<br>
Voorbeeldinvoer: *iPhone5,2;iPhone5,3*

Op apparaten van eindgebruikers moet de Intune-client actie ondernemen op basis van tekenreeksen van het apparaatmodel die zijn opgegeven in Intune-beleid voor toepassingsbeveiliging. Het afstemmen is volledig afhankelijk van wat het apparaat rapporteert. U (de IT-beheerder) wordt aangeraden om ervoor te zorgen dat het beoogde gedrag optreedt door deze instelling in een kleine groep gebruikers te testen op basis van verschillende apparaatfabrikanten en -modellen. De standaardwaarde is **Niet geconfigureerd**.<br>
Stel een van de volgende acties in: 
- Opgegeven toestaan (blokkeren indien niet opgegeven)
- Opgegeven toestaan (wissen indien niet opgegeven)

**Wat gebeurt er als de IT-beheerder een andere lijst met iOS-modelaanduidingen opgeeft terwijl er al beleid van kracht is voor dezelfde apps en dezelfde Intune-gebruiker?**<br>
Als er zich conflicten voordoen tussen het ene app-beschermingsbeleid voor geconfigureerde waarden en het andere, gaat Intune doorgaans uit van de meest beperkende aanpak. Het resulterende beleid voor de betreffende app die door de betreffende Intune-gebruiker wordt geopend, bestaat dan uit de overlap van de vermelde iOS-modelaanduidingen in *Beleid A* en *Beleid B* voor dezelfde app-/gebruikercombinatie. *Beleid A* specificeert bijvoorbeeld 'iPhone5,2;iPhone5,3', terwijl *Beleid B* 'iPhone5,3' specificeert. Het resulterende beleid voor een Intune-gebruiker op wie zowel *Beleid A* als *Beleid B* is gericht, is dan 'iPhone5,3'. 

### <a name="android-policy-settings"></a>Beleidsinstellingen voor Android

Voor Android kunt u acties configureren voor de volgende instellingen met behulp van de vervolgkeuzelijst **Instelling**:
- Maximum aantal pincodepogingen
- Offline respijtperiode
- Apparaten die zijn opengebroken of geroot
- Minimale versie van het besturingssysteem
- Minimale versie van de app
- Minimale patchversie
- Apparaatfabrikant(en)
- SafetyNet-attestation voor apparaat
- Bedreigingsscan voor apps vereisen
- Minimale versie bedrijfsportal
- Maximaal toegestaan bedreigingsniveau van apparaat

Met behulp van **Minimale versie bedrijfsportal** kunt u een minimale versie van de bedrijfsportal opgeven die wordt afgedwongen op het apparaat van de eindgebruiker. Met deze instelling voor voorwaardelijk starten kunt u waarden instellen voor **Toegang blokkeren**, **Gegevens wissen** en **Waarschuwen** als mogelijke acties wanneer niet aan alle waarden wordt voldaan. De mogelijke notaties voor deze waarde volgen het patroon *[major].[minor]* , *[major].[minor].[build]* , of *[major].[minor].[build].[revision]* . Omdat sommige eindgebruikers mogelijk niet de voorkeur geven aan een geforceerde update van apps, kan de optie 'Waarschuwen' ideaal zijn bij het configureren van deze instelling. De Google Play Store is zo slim om alleen de verschilgegevens voor app-updates te verzenden. Dit kan echter nog steeds een grote hoeveelheid gegevens zijn die gebruikers mogelijk niet willen aannemen, bijvoorbeeld als ze op het moment van de update via mobiele gegevens werken. Het afdwingen van een update en het downloaden van een bijgewerkte app kan leiden tot onverwachte gegevenskosten op het moment van de update. Indien de instelling **Minimale versie bedrijfsportal** is geconfigureerd, beïnvloedt deze elke eindgebruiker die versie 5.0.4560.0 en toekomstige versies van de bedrijfsportal ontvangt. Deze instelling heeft geen invloed op gebruikers die gebruikmaken van een versie van bedrijfsportal die ouder is dan de versie waarop deze functie wordt uitgebracht. Eindgebruikers die automatische app-updates op hun apparaat gebruiken, krijgen waarschijnlijk geen dialoogvensters van deze functie te zien, aangezien ze waarschijnlijk de nieuwste versie van de bedrijfsportal hebben. Deze instelling is alleen voor Android met app-beveiliging voor ingeschreven en niet-ingeschreven apparaten.

Als u de instelling **Apparaatfabrikant(en)** wilt gebruiken, voert u een lijst met door puntkomma's gescheiden waarden in van Android-producenten. U vindt de Android-fabrikant van een apparaat in de apparaatinstellingen.<br>
Voorbeeldinvoer: *Fabrikant A;Fabrikant B* 

>[!NOTE]
> Dit is een lijst met algemene fabrikanten die apparaten met Intune hebben die als invoer kunnen worden gebruikt: Asus;Blackberry;Bq;Gionee;Google;Hmd global;Htc;Huawei;Infinix;Kyocera;Lemobile;Lenovo;Lge;Motorola;Oneplus;Oppo;Samsung;Sharp;Sony;Tecno;Vivo;Vodafone;Xiaomi;Zte;Zuk

Op apparaten van eindgebruikers moet de Intune-client actie ondernemen op basis van tekenreeksen van het apparaatmodel die zijn opgegeven in Intune-beleid voor toepassingsbeveiliging. Het afstemmen is volledig afhankelijk van wat het apparaat rapporteert. U (de IT-beheerder) wordt aangeraden om ervoor te zorgen dat het beoogde gedrag optreedt door deze instelling in een kleine gebruikersgroep te testen op basis van verschillende apparaatfabrikanten en -modellen. De standaardwaarde is **Niet geconfigureerd**.<br>
Stel een van de volgende acties in: 
- Opgegeven toestaan (blokkeren indien niet opgegeven)
- Opgegeven toestaan (wissen indien niet opgegeven)

**Wat gebeurt er als de IT-beheerder een andere lijst met Android-fabrikanten opgeeft terwijl er al beleid van kracht is voor dezelfde apps en dezelfde Intune-gebruiker?**<br>
Als er zich conflicten voordoen tussen het ene app-beschermingsbeleid voor geconfigureerde waarden en het andere, gaat Intune doorgaans uit van de meest beperkende aanpak. Het resulterende beleid voor de betreffende app die door de betreffende Intune-gebruiker wordt geopend, bestaat dan uit de overlap van de vermelde Android-fabrikanten in *Beleid A* en *Beleid B* voor dezelfde app-/gebruikercombinatie. *Beleid A* specificeert bijvoorbeeld 'Google;Samsung' en *Beleid B* 'Google'. Het resulterende beleid voor een Intune-gebruiker op wie zowel *Beleid A* als *Beleid B* is gericht, is dan 'Google'. 

### <a name="additional-settings-and-actions"></a>Extra instellingen en acties 

Standaard worden de rijen in de tabel gevuld als instellingen die zijn geconfigureerd voor **Offline respijtperiode** en **Maximum aantal pincodepogingen** als de instelling **Pincode is vereist voor toegang** is ingesteld op **Ja**.
 
Als u een instelling wilt configureren, selecteert u een instelling in de vervolgkeuzelijst onder de kolom **Instelling**. Nadat een instelling is geselecteerd, wordt het bewerkbare tekstvak ingeschakeld onder de kolom **Waarde** in dezelfde rij als is vereist dat de waarde wordt ingesteld. Ook de vervolgkeuzelijst onder de kolom **Actie** wordt ingeschakeld met de reeks voorwaardelijke startacties die van toepassing zijn op de instelling. 

De volgende lijst bevat de algemene lijst met acties:
- **Toegang blokkeren**: de toegang tot de bedrijfsapp wordt geblokkeerd voor de eindgebruiker.
- **Gegevens wissen**: de bedrijfsgegevens worden van het apparaat van de eindgebruiker gewist.
- **Waarschuwen**: de eindgebruiker ziet een dialoogvenster als een waarschuwingsbericht.

In sommige gevallen, zoals voor de instelling **Minimale versie van het besturingssysteem**, kunt u de instelling zo configureren dat alle toepasselijke acties worden uitgevoerd op basis van verschillende versienummers. 

![Schermafbeelding van de toegangsacties voor app-beveiliging - Minimale versie van het besturingssysteem](./media/app-protection-policies-access-actions/apps-selective-wipe-access-actions05.png)

Wanneer een instelling volledig is geconfigureerd, wordt de rij weergegeven in de alleen-lezenweergave en kan de rij op elk moment worden bewerkt. Bovendien is er voor de rij een vervolgkeuzelijst beschikbaar in de kolom **Instelling**. Instellingen die al zijn geconfigureerd en waarvoor meerdere acties niet zijn toegestaan, kunnen niet worden geselecteerd in de vervolgkeuzelijst.

## <a name="next-steps"></a>Volgende stappen

Ga voor meer informatie over het app-beveiligingsbeleid in Intune naar:
- [App-beveiligingsbeleid maken en toewijzen](app-protection-policies.md)
- [Beveiligingsbeleidsinstellingen voor iOS-apps](app-protection-policy-settings-ios.md)
- [Instellingen voor beveiligingsbeleid voor apps voor Android in Microsoft Intune](app-protection-policy-settings-android.md) 
