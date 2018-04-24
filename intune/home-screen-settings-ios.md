---
title: Indelingsinstellingen voor de Microsoft Intune-startpagina voor iOS-apparaten
titleSuffix: ''
description: Informatie over de instellingen in Microsoft Intune waarmee u het beginscherm kunt aanpassen en dokken op iOS-apparaten.
keywords: ''
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 03/02/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ab5ee886cbc324b0fe3383e7e585e8d0b6482326
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2018
---
# <a name="microsoft-intune-home-screen-layout-settings-for-devices-running-ios"></a>Indelingsinstellingen voor de Microsoft Intune-startpagina voor iOS-apparaten

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Gebruik deze instellingen voor het configureren van de indeling van apps en mappen in de dock en het startscherm van iOS-apparaten.

Op iOS-apparaten met een toegewezen profiel, moet de supervisiemodus zijn geactiveerd. Op het apparaat moet iOS 9.3 of hoger worden uitgevoerd.

1. Navigeer vanaf [Intune in Azure Portal](https://portal.azure.com) naar [ **Apparaatfuncties** in het apparaatconfiguratiegebied](device-features-configure.md).
2. Kies in het deelvenster **Apparaatfuncties** de optie **Indeling voor het beginscherm (alleen onder toezicht)**.
3. Kies in het deelvenster **Indeling voor het beginscherm (alleen onder toezicht)** of u indelingen van de **dock** of **pagina's** wilt configureren.

## <a name="add-items-to-the-dock"></a>Items toevoegen aan de dock

In het deelvenster **Dock** kunt u maximaal zes items of mappen toevoegen aan de dock onderaan in het iOS-scherm. Veel apparaten ondersteunen echter minder items. iPhones ondersteunen bijvoorbeeld maar 4 items. In dit geval worden alleen de eerste vier items die u hebt geconfigureerd op het apparaat weergegeven.

1. Kies **Toevoegen** om een item toe te voegen aan de dock.
2. Kies in het deelvenster **Rij toevoegen** of u een **app** of **map** wilt toevoegen.
3. Gebruik de informatie in dit onderwerp om de apps en mappen te configureren die u wilt weergeven in de dock.
4. Ga door naar het toevoegen van items. Als u klaar bent, klikt u in elk deelvenster op **OK** totdat u bent teruggekeerd naar het deelvenster **Profiel maken**. Kies **Maken**.

>[!TIP]
> U kunt items slepen en neerzetten in elk startscherm en alle paginalijsten om deze te rangschikken.

### <a name="example"></a>Voorbeeld

In dit voorbeeld hebt u het dockscherm zodanig geconfigureerd dat alleen de apps Safari, Mail en Aandelen worden weergegeven. In de volgende afbeelding is de app Mail geselecteerd om de eigenschappen te illustreren:

![Voorbeeld van iOS-dockinstellingen](./media/FfFiUcP.png)

Wanneer u het beleid aan een iPhone toewijst, is het resultaat een dock die er ongeveer als volgt uitziet:

![Voorbeeld van iOS-dockindeling op iPhone](./media/bAgCe8F.png)

## <a name="add-home-screen-pages"></a>Pagina's toevoegen aan startscherm

Voeg de pagina's toe die u wilt weergeven op het startscherm en voeg de apps toe die moeten worden weergegeven op elke pagina. Apps die u aan een pagina toevoegt, worden gerangschikt van links naar rechts, in de volgorde waarin deze zijn opgegeven in de lijst. Als u meer apps toevoegt dan er op een pagina passen, worden de apps naar een volgende pagina verplaatst.

1. Kies in het deelvenster **Pagina's** de optie **Toevoegen**.
2. Voer in het deelvenster **Rij toevoegen** een **paginanaam** in. Deze naam wordt ter referentie gegeven in de Azure-portal en *wordt niet weergegeven* op het iOS-apparaat.
3. Kies **Toevoegen** en kies of u een **App** of **Map** wilt toevoegen aan de pagina.
4. Gebruik de informatie in dit onderwerp om de apps en mappen te configureren die u wilt weergeven op de pagina.

### <a name="example"></a>Voorbeeld

In dit voorbeeld hebt u een nieuwe pagina met de naam **Contoso** geconfigureerd. Op de pagina staan alleen de apps Zoek vrienden en Instellingen. In de volgende afbeelding is de app Instellingen geselecteerd om de eigenschappen te illustreren:

![Voorbeeld van instellingen voor iOS-startscherm](./media/Jc2OxyX.png)

Wanneer u het beleid aan een iPhone toewijst, is het resultaat een pagina die er ongeveer als volgt uitziet:

![iOS-apparaat met gewijzigd startscherm](./media/Bd37PHa.png)

## <a name="how-to-add-an-app-to-the-list"></a>Een app aan de lijst toevoegen

1. Voer de **App-naam** in. Deze naam wordt ter referentie gegeven in de Azure-portal en *wordt niet weergegeven* op het iOS-apparaat.
2. Voer de **App-bundel-id** in van de app die u wilt weergeven. Zie voor hulp **Lijst van bundel-id's voor ingebouwde iOS-apps** verderop in dit onderwerp.
3. Klik op **OK**, ga door naar het toevoegen van items, tot een maximum van **6** voor de apparaatdock en **60** voor een apparaatpagina.
4. Klik op **OK**als u klaar bent.

## <a name="how-to-add-a-folder-to-the-list"></a>Een map aan de lijst toevoegen

Apps die u aan een pagina in een map toevoegt, worden gerangschikt van links naar rechts, in de volgorde waarin deze zijn opgegeven in de lijst. Als u meer apps toevoegt dan er op een pagina passen, worden de apps naar een volgende pagina verplaatst.

1. Voer de **Mapnaam** in. Deze naam zien gebruikers op hun apparaat.
2. Kies **Toevoegen** om een pagina in de map te maken. U kunt maximaal 20 pagina's toevoegen.
3. Voer in het deelvenster **Rij toevoegen** een naam in voor de pagina. Deze naam wordt ter referentie gegeven in de Azure-portal en *wordt niet weergegeven* op het iOS-apparaat.
3. Voer de **App-naam** in. Deze naam wordt ter referentie gegeven in de Azure-portal en *wordt niet weergegeven* op het iOS-apparaat.
2. Voer de **App-bundel-id** in van de app die u wilt weergeven. Zie **Een app aan de lijst toevoegen** voor meer informatie.
3. Kies **Toevoegen**. U kunt maximaal 60 items toevoegen.
4. Klik op **OK**als u klaar bent.


## <a name="bundle-id-reference-for-built-in-ios-apps"></a>Lijst van bundel-id's voor ingebouwde iOS-apps

Deze lijst bevat de bundel-id's van een aantal algemene ingebouwde iOS-apps. Als u de bundel-ID van andere apps wilt weten, neemt u contact op met de softwareleverancier.

|||
|-|-|
|App-naam|Bundel-id|
|App Store|com.apple.AppStore|
|Rekenmachine|com.apple.calculator|
|Kalender|com.apple.mobilecal|
|Camera|com.apple.camera|
|Klok|com.apple.mobiletimer|
|Kompas|com.apple.compass|
|Contactpersonen|com.apple.MobileAddressBook|
|FaceTime|com.apple.facetime|
|Zoek vrienden|com.apple.mobileme.fmf1|
|Zoek mijn iPhone|com.apple.mobileme.fmip1|
|Game Center|com.apple.gamecenter|
|GarageBand|com.apple.mobilegarageband|
|Status|com.apple.Health|
|iBooks|com.apple.iBooks|
|iTunes Store|com.apple.MobileStore|
|iTunes U|com.Apple.itunesu|
|Keynote|com.apple.Keynote|
|Mail|com.Apple.mobilemail|
|Kaarten|com.apple.Maps|
|Berichten|com.apple.MobileSMS|
|Music|com.apple.Music|
|Nieuws|com.apple.news|
|Opmerkingen|com.apple.mobilenotes|
|Getallen|com.apple.Numbers|
|Pages|com.apple.Pages|
|Photo Booth|com.apple.Photo-Booth|
|Foto's|com.apple.mobileslideshow|
|Podcasts|com.apple.podcasts|
|Herinneringen|com.apple.reminders|
|Safari|com.apple.mobilesafari|
|Instellingen|com.apple.Preferences|
|Aandelen|com.apple.stocks|
|Tips|com.apple.tips|
|Video 's|com.apple.videos|
|Dictafoon|com.apple.VoiceMemos|
|Wallet|com.apple.Passbook|
|Watch|com.apple.Bridge|
|Weer|com.apple.weather|


## <a name="next-steps"></a>Volgende stappen

U kunt het apparaatprofiel nu toewijzen aan de gewenste groepen. Zie [Apparaatprofielen toewijzen](device-profile-assign.md) voor meer informatie.
