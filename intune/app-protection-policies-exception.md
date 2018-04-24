---
title: Beleidsuitzonderingen voor gegevensoverdracht voor apps
titleSuffix: Microsoft Intune
description: Maak uitzonderingen voor het gegevensoverdrachtbeleid van Intune MAM (Mobile Application Management).
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/26/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f9015e3a-c22c-42eb-90e6-ba48dee3a41d
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1910334093a416933912c9cdeedac85e36d66e92
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-create-exceptions-to-the-intune-mobile-application-management-mam-data-transfer-policy"></a>Uitzonderingen maken voor het gegevensoverdrachtbeleid van Intune MAM (Mobile Application Management)

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Als beheerder kunt u uitzonderingen maken voor het gegevensoverdrachtbeleid van Intune MAM (Mobile Application Management). Met een uitzondering kunt u aangeven welke onbeheerde apps gegevens van en naar beheerde apps mogen overdragen. De onbeheerde apps die u op de uitzonderingenlijst plaatst, moeten door de IT-afdeling worden vertrouwd. 

>[!WARNING] 
> U bent zelf verantwoordelijk voor het aanbrengen van wijzigingen aan het uitzonderingsbeleid voor gegevensoverdracht. Door toevoegingen aan dit beleid kunnen onbeheerde apps (apps die niet door Intune worden beheerd) toegang verkrijgen door de gegevens die door beheerde apps worden beschermd. Als u toegang biedt tot beschermde gegevens kan dit leiden tot beveiligingslekken. Voeg alleen gegevensoverdrachtuitzonderingen toe voor apps die uw organisatie moet gebruiken, maar die geen ondersteuning bieden voor Intune APP (beleid voor toepassingsbeveiliging). Daarnaast dient u alleen uitzonderingen toe te voegen voor apps waarvan u niet denkt dat ze zullen leiden tot een gegevenslek.

Deze functie is van toepassing wanneer u een Intune-beveiligingsbeleid voor toepassingen maakt, met gegevensoverdracht ingesteld op **Alleen beheerde apps**. Afgezien van de uitzonderingen die u maakt, wordt de gegevensoverdracht nog steeds beperkt tot de toepassingen die door Intune worden beheerd als uw beleid voor gegevensoverdracht is ingesteld op **Uitsluitend beheerde apps**. U kunt de beperkingen maken met behulp van protocollen (iOS) of pakketten (Android).

U kunt deze functie zodanig configureren dat uitzonderingen op het Intune MAM-app-beveiligingsbeleid met **beperkte gegevensoverdracht** worden toegestaan. Dit beleid is alleen vereist als u wilt toestaan dat gegevens worden overgedragen naar een app die geen ondersteuning biedt voor Intune APP. Met dit beleid kunnen toepassingen die worden beheerd door Intune en waarvoor de gegevensoverdracht is ingesteld op **Uitsluitend beheerde apps** onbeheerde toepassingen aanroepen op basis van een URL-protocol (iOS) of een pakketnaam (Android). Er worden in Intune belangrijke, systeemeigen toepassingen toegevoegd aan de lijst standaarduitzonderingen. 

## <a name="ios-data-transfer-exceptions"></a>iOS-uitzonderingen voor gegevensoverdracht
Bij beleid voor iOS kunt u uitzonderingen voor gegevensoverdracht configureren op basis van URL-protocollen. Als u een uitzondering wilt toevoegen, bekijkt u de documentatie van de ontwikkelaar van de app om te achterhalen of er informatie in staat over ondersteunde URL-protocollen. Zie [Beveiligingsbeleidsinstellingen voor iOS-apps - Uitzonderingen voor gegevensoverdracht](app-protection-policy-settings-ios.md#data-transfer-exemptions) voor meer informatie over uitzonderingen voor gegevensoverdracht in iOS.

## <a name="android-data-transfer-exceptions"></a>Android-uitzonderingen voor gegevensoverdracht
Bij beleid voor Android kunt u uitzonderingen voor gegevensoverdracht configureren op basis van app-pakketnamen. Kijk op de **Google Play** Store-pagina van de app die u als uitzondering wilt toevoegen om de app-pakketnaam te achterhalen. Zie [Beveiligingsbeleidsinstellingen voor Android-apps - Uitzonderingen voor gegevensoverdracht](app-protection-policy-settings-android.md#data-transfer-exemptions) voor aanvullende informatie over uitzonderingen voor gegevensoverdracht in Android.


>[!TIP]
> U kunt de pakket-id van een app vinden door te bladeren naar de app in de Google Play-store. De pakket-id is opgenomen in de URL van de pagina van de app. De pakket-id van de Microsoft Word-app is bijvoorbeeld **com.microsoft.office.word**.

### <a name="example"></a>Voorbeeld
Als u het **Webex**-pakket als uitzondering toevoegt aan het MAM-gegevensoverdrachtbeleid, mogen Webex-links in een beheerd Outlook-e-mailbericht rechtstreeks worden geopend in de Webex-toepassing. De gegevensoverdracht wordt nog steeds beperkt in andere onbeheerde apps.

- iOS **Webex**-voorbeeld: als u de **Webex**-app wilt uitsluiten zodat deze mag worden aangeroepen door in Intune beheerde apps, moet u een uitzondering voor gegevensoverdracht toevoegen voor de volgende tekenreeks: <code>wbx</code>.

- Android **Webex**-voorbeeld: als u de **Webex**-app wilt uitsluiten zodat deze mag worden aangeroepen door in Intune beheerde apps, moet u een uitzondering voor gegevensoverdracht toevoegen voor de volgende tekenreeks: <code>com.cisco.webex.meetings</code>. 

## <a name="next-steps"></a>Volgende stappen

- [Beveiligingsbeleid voor apps maken en implementeren](app-protection-policies.md)
- [Beveiligingsbeleidsinstellingen voor iOS-apps - Uitzonderingen voor gegevensoverdracht](app-protection-policy-settings-ios.md#data-transfer-exemptions)
- [Beveiligingsbeleidsinstellingen voor Android-apps - Uitzonderingen voor gegevensoverdracht](app-protection-policy-settings-android.md#data-transfer-exemptions)
