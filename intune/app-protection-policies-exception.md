---
title: Beleidsuitzonderingen voor gegevensoverdracht voor apps
titleSuffix: Microsoft Intune
description: Maak uitzonderingen voor het gegevensoverdrachtbeleid van Intune MAM (Mobile Application Management).
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/01/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f9015e3a-c22c-42eb-90e6-ba48dee3a41d
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: c9f6ee3d1672c375071b061b4a551f609792deb9
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/02/2019
ms.locfileid: "57238248"
---
# <a name="how-to-create-exceptions-to-the-intune-mobile-application-management-mam-data-transfer-policy"></a>Uitzonderingen maken voor het gegevensoverdrachtbeleid van Intune MAM (Mobile Application Management)

Als beheerder kunt u uitzonderingen maken voor het gegevensoverdrachtbeleid van Intune MAM (Mobile Application Management). Met een uitzondering kunt u aangeven welke onbeheerde apps gegevens van en naar beheerde apps mogen overdragen. De onbeheerde apps die u op de uitzonderingenlijst plaatst, moeten door de IT-afdeling worden vertrouwd. 

>[!WARNING] 
> U bent zelf verantwoordelijk voor het aanbrengen van wijzigingen aan het uitzonderingsbeleid voor gegevensoverdracht. Door toevoegingen aan dit beleid kunnen onbeheerde apps (apps die niet door Intune worden beheerd) toegang verkrijgen door de gegevens die door beheerde apps worden beschermd. Als u toegang biedt tot beschermde gegevens kan dit leiden tot beveiligingslekken. Voeg alleen gegevensoverdrachtuitzonderingen toe voor apps die uw organisatie moet gebruiken, maar die geen ondersteuning bieden voor Intune APP (beleid voor toepassingsbeveiliging). Daarnaast dient u alleen uitzonderingen toe te voegen voor apps waarvan u niet denkt dat ze zullen leiden tot een gegevenslek.

In een Intune Application Protection Policy betekent de instelling **App mag gegevens overdragen naar andere apps** voor **door beleid beheerde apps** dat de app alleen gegevens kan overdragen naar apps die worden beheerd door Intune. Als u gegevensoverdracht moet toestaan naar specifieke apps die de Intune-app niet ondersteunen, kunt u uitzonderingen op dit beleid maken met behulp van de optie **Vrijgestelde apps selecteren**. Met uitzonderingen kunnen toepassingen die worden beheerd door Intune niet-beheerde toepassingen aanroepen op basis van URL-protocol (iOS) of pakketnaam (Android). Standaard bevat deze lijst met uitzonderingen in Intune belangrijke, systeemeigen toepassingen. 

> [!NOTE]
> Het aanpassen van of toevoegen aan de uitzonderingen voor gegevensoverdracht heeft geen invloed op ander appbeveiligingsbeleid, zoals beperkingen voor knippen, kopiëren en plakken. 

## <a name="ios-data-transfer-exceptions"></a>iOS-uitzonderingen voor gegevensoverdracht
Bij beleid voor iOS kunt u uitzonderingen voor gegevensoverdracht configureren op basis van URL-protocollen. Als u een uitzondering wilt toevoegen, bekijkt u de documentatie van de ontwikkelaar van de app om te achterhalen of er informatie in staat over ondersteunde URL-protocollen. Zie [Beveiligingsbeleidsinstellingen voor iOS-apps - Uitzonderingen voor gegevensoverdracht](app-protection-policy-settings-ios.md#data-transfer-exemptions) voor meer informatie over uitzonderingen voor gegevensoverdracht in iOS.

> [!NOTE]
> Microsoft heeft geen methode om handmatig te zoeken naar het URL-protocol voor het maken van app-uitzonderingen voor toepassingen van derden. 

## <a name="android-data-transfer-exceptions"></a>Android-uitzonderingen voor gegevensoverdracht
Bij beleid voor Android kunt u uitzonderingen voor gegevensoverdracht configureren op basis van app-pakketnamen. Kijk op de **Google Play** Store-pagina van de app die u als uitzondering wilt toevoegen om de app-pakketnaam te achterhalen. Zie [Beveiligingsbeleidsinstellingen voor Android-apps - Uitzonderingen voor gegevensoverdracht](app-protection-policy-settings-android.md#data-transfer-exemptions) voor meer informatie over uitzonderingen voor gegevensoverdracht in Android.


>[!TIP]
> U kunt de pakket-id van een app vinden door te bladeren naar de app in de Google Play-store. De pakket-id is opgenomen in de URL van de pagina van de app. De pakket-id van de Microsoft Word-app is bijvoorbeeld **com.microsoft.office.word**.

### <a name="example"></a>Voorbeeld
Als u het **Webex**-pakket als uitzondering toevoegt aan het MAM-gegevensoverdrachtbeleid, mogen Webex-links in een beheerd Outlook-e-mailbericht rechtstreeks worden geopend in de Webex-toepassing. De gegevensoverdracht wordt nog steeds beperkt in andere onbeheerde apps.

- iOS-**Webex**-voorbeeld:   Als u de **Webex**-app wilt uitsluiten zodat deze mag worden aangeroepen door in Intune beheerde apps, moet u een uitzondering voor gegevensoverdracht toevoegen voor de volgende tekenreeks: <code>wbx</code>
    
 - iOS-**Maps**-voorbeeld:  Als u de systeemeigen **Maps**-app wilt uitsluiten zodat deze mag worden aangeroepen door in Intune beheerde apps, moet u een uitzondering voor gegevensoverdracht toevoegen voor de volgende tekenreeks: <code>maps</code>

- Android-**Webex**-voorbeeld:   Als u de **Webex**-app wilt uitsluiten zodat deze mag worden aangeroepen door in Intune beheerde apps, moet u een uitzondering voor gegevensoverdracht toevoegen voor de volgende tekenreeks: <code>com.cisco.webex.meetings</code>
    
- Android-**SMS**-voorbeeld:   Als u de systeemeigen **SMS**-app wilt uitsluiten zodat deze mag worden aangeroepen door in Intune beheerde apps via verschillende berichten-apps en Android-apparaten, moet u uitzonderingen voor gegevensoverdracht toevoegen voor de volgende tekenreeksen: 
    <code>com.google.android.apps.messaging</code>
    
    <code>com.android.mms</code>
    
    <code>com.samsung.android.messaging</code>

## <a name="next-steps"></a>Volgende stappen

- [Beveiligingsbeleid voor apps maken en implementeren](app-protection-policies.md)
- [Beveiligingsbeleidsinstellingen voor iOS-apps - Uitzonderingen voor gegevensoverdracht](app-protection-policy-settings-ios.md#data-transfer-exemptions)
- [Beveiligingsbeleidsinstellingen voor Android-apps - Uitzonderingen voor gegevensoverdracht](app-protection-policy-settings-android.md#data-transfer-exemptions)
