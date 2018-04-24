---
title: Bedrijfsportal-berichten die gebruikers mogelijk te zien krijgen op apparaten
titlesuffix: Microsoft Intune
description: Kom meer te weten over de verschillende berichten die eindgebruikers te zien kunnen krijgen in de bedrijfsportal.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 03/09/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 3df993aa-48c5-4799-b68d-c85fe4f7b02c
ms.reviewer: aanavath
ms.suite: ems
ms.openlocfilehash: 3ed729e437fcdbc4352bf5fa8ceada4ddf336708
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2018
---
# <a name="help-end-users-understand-company-portal-app-messages"></a>Eindgebruikers helpen bij het begrijpen van berichten van de bedrijfsportal-app

[!INCLUDE [both-portals](./includes/note-for-both-portals.md)]

> [!NOTE]
> De volgende informatie is alleen van toepassing op apparaten met Android 6.0 en hoger.

Kom meer te weten over de verschillende app-berichten die eindgebruikers te zien kunnen krijgen in de bedrijfsportal. Deze app-berichten worden meestal op verschillende momenten in het inschrijvingsproces weergegeven. Ontdek waar de berichten worden weergegeven, wat de berichten betekenen en wat er gebeurt als gebruikers toegang weigeren. Kom daarnaast te weten hoe u de berichten het beste kunt uitleggen aan gebruikers.

- __De bedrijfsportal toestaan telefoongesprekken uit te voeren en te beheren?__
- __De bedrijfsportal toegang verlenen tot foto's, media en bestanden op uw apparaat?__

## <a name="allow-company-portal-to-make-and-manage-phone-calls"></a>De bedrijfsportal toestaan telefoongesprekken uit te voeren en beheren?

### <a name="where-it-appears"></a>Waar deze wordt weergegeven
Het bericht **De bedrijfsportal toestaan om telefoongesprekken uit te voeren en te beheren?** wordt weergegeven wanneer gebruikers in de bedrijfsportal-app op **Inschrijven** tikken wanneer ze hun apparaat inschrijven.

### <a name="what-it-means"></a>Wat het betekent
Wanneer gebruikers hiermee akkoord gaan, geven ze toestemming om het telefoonnummer en het IMEI-nummer van hun apparaat naar de Intune-service te verzenden. Deze worden weergegeven in de beheerconsole op de pagina __Hardware__.

> [!NOTE]
> **De bedrijfsportal-app voert nooit telefoongesprekken uit en beheert deze niet.** De berichttekst wordt beheerd door Google en kan niet worden gewijzigd.

Als u de pagina **Hardware** wilt weergeven, gaat u naar **Groepen** > **Alle mobiele apparaten** > **Apparaten**. Selecteer het apparaat van de gebruiker en ga naar **Eigenschappen weergeven** > **Hardware**.

### <a name="what-happens-if-users-deny-access"></a>Wat er gebeurt als gebruikers toegang weigeren
Als gebruikers de toegang weigeren, kunnen ze de bedrijfsportal-app wel nog gebruiken en hun apparaat inschrijven. Het telefoonnummer en het IMEI-nummer worden echter leeg weergegeven op de pagina __Hardware__ in de beheerconsole. De tweede keer dat gebruikers zich aanmelden bij de bedrijfsportal-app nadat ze toegang hebben geweigerd, wordt in het bericht een selectievakje bij **Niet opnieuw vragen** weergegeven dat gebruikers kunnen inschakelen zodat het bericht nooit meer wordt weergegeven.

Als gebruikers toegang verlenen en deze later weer intrekken, wordt het bericht de volgende keer dat gebruikers zich bij de bedrijfsportal-app aanmelden, weergegeven na de inschrijving.

Als gebruikers later alsnog besluiten om toegang te verlenen, kunnen ze naar **Instellingen** > **Apps** > **Bedrijfsportal** > **Machtigingen** > **Telefoon** gaan en de optie inschakelen.

### <a name="how-to-explain-this-to-your-users"></a>Dit uitleggen aan uw gebruikers
Stuur uw gebruikers naar [Uw Android-apparaat inschrijven bij Intune](/intune-user-help/enroll-your-device-in-intune-android) voor meer informatie.

## <a name="allow-company-portal-to-access-your-contacts"></a>Bedrijfsportal toegang tot uw contactpersonen toestaan?

### <a name="where-it-appears"></a>Waar deze wordt weergegeven
Het bericht **Bedrijfsportal toegang tot uw contactpersonen toestaan?** wordt weergegeven wanneer gebruikers in de bedrijfsportal-app op **Inschrijven** tikken wanneer ze hun apparaat inschrijven.

### <a name="what-it-means"></a>Wat het betekent
Wanneer gebruikers hiermee akkoord gaan, stemmen ze ermee in dat hun werkaccount met Intune wordt gemaakt en dat de Azure Active Directory-identiteit die voor de gebruiker van dat apparaat is geregistreerd daarmee wordt beheerd.

> [!NOTE]
> **Microsoft heeft nooit toegang tot contactpersonen.** De berichttekst wordt beheerd door Google en kan niet worden gewijzigd.

### <a name="what-happens-if-users-deny-access"></a>Wat er gebeurt als gebruikers toegang weigeren
Als een gebruiker geen toestemming geeft, wordt het apparaat niet bij Intune ingeschreven en kan het niet worden beheerd. De tweede keer dat gebruikers zich aanmelden bij de bedrijfsportal-app nadat ze toegang hebben geweigerd, wordt in het bericht een selectievakje bij **Niet opnieuw vragen** weergegeven dat gebruikers kunnen inschakelen zodat het bericht nooit meer wordt weergegeven.

Als gebruikers toegang verlenen en deze later weer intrekken, wordt het bericht de volgende keer dat gebruikers zich bij de bedrijfsportal-app aanmelden, weergegeven na de registratie.

Als gebruikers later alsnog besluiten om toegang te verlenen, kunnen ze naar **Instellingen** > **Apps** > **Bedrijfsportal** > **Machtigingen** > **Telefoon** gaan en de optie inschakelen.

### <a name="how-to-explain-this-to-your-users"></a>Dit uitleggen aan uw gebruikers
Stuur uw gebruikers naar [Uw Android-apparaat inschrijven bij Intune](/intune-user-help/enroll-your-device-in-intune-android) voor meer informatie.

## <a name="allow-company-portal-to-access-photos-media-and-files-on-your-device"></a>De bedrijfsportal toegang verlenen tot foto's, media en bestanden op uw apparaat?

### <a name="where-it-appears"></a>Waar deze wordt weergegeven
Het bericht **De bedrijfsportal toegang verlenen tot foto's, media en bestanden op uw apparaat?** wordt weergegeven wanneer gebruikers op **Gegevens verzenden** tikken om hun logboeken te verzenden naar hun IT-beheerder.

### <a name="what-it-means"></a>Wat het betekent
Door hiermee akkoord te gaan, staan gebruikers toe dat gegevenslogboeken worden geschreven naar de SD-geheugenkaart van het apparaat. Hierdoor kunnen deze logboeken ook worden verzonden via een USB-kabel.   

> [!NOTE]
> **De bedrijfsportal-app gebruikt nooit foto's, media en bestanden van gebruikers.** De berichttekst wordt beheerd door Google en kan niet worden gewijzigd.

### <a name="what-happens-if-users-deny-access"></a>Wat er gebeurt als gebruikers toegang weigeren
Als gebruikers toegang weigeren, kunnen ze nog steeds gegevenslogboeken via e-mail verzenden, maar de logboeken worden niet gekopieerd naar de SD-kaart van het apparaat.

De tweede keer dat gebruikers zich aanmelden bij de bedrijfsportal-app nadat ze toegang hebben geweigerd, wordt in het bericht een selectievakje bij **Niet opnieuw vragen** weergegeven dat gebruikers kunnen inschakelen zodat het bericht nooit meer wordt weergegeven. Als gebruikers toegang verlenen en deze later weer intrekken, wordt het bericht de volgende keer dat ze logboeken verzenden, weergegeven. Als gebruikers later echter alsnog besluiten om toegang te verlenen, kunnen ze naar **Instellingen** > **Apps** > **Bedrijfsportal** > **Machtigingen** > **Opslag** gaan en de machtiging instellen.


### <a name="how-to-explain-this-to-your-users"></a>Dit uitleggen aan uw gebruikers
Stuur uw gebruikers naar [Logboeken via e-mail naar de IT-beheerder verzenden](/intune-user-help/send-logs-to-your-it-admin-by-email-android). 

## <a name="your-company-support-needs-to-give-you-access-to-company-resources"></a>De ondersteuningsafdeling van uw bedrijf moet u toegang geven tot de bedrijfsbronnen

### <a name="where-it-appears"></a>Waar deze wordt weergegeven
Als u de bedrijfsportal-app niet hebt toegevoegd aan de lijst **Toegestane apps** of **Vrijgestelde apps**, zullen aanmeldpogingen van gebruikers mislukken. Het volgende bericht wordt weergegeven:

> **De ondersteuningsafdeling van uw bedrijf moet u toegang geven tot de bedrijfsbronnen**  
> Uw bedrijf gebruikt Windows Information Protection-beleid om uw apparaat te beveiligen. De ondersteuningsafdeling van uw bedrijf moet ervoor zorgen dat de bedrijfsportal toegang heeft tot de resources.

### <a name="what-it-means"></a>Wat het betekent

Voeg de bedrijfsportal toe aan de lijst **Toegestane apps** of **Vrijgestelde apps** in het Windows Information Protection (WIP)-beveiligingsbeleid voor apps. Zie [Beveiligingsinstelling voor de beveiliging van apps voor Windows Information Protection (WIP) maken en implementeren met Intune](/intune-classic/deploy-use/create-windows-information-protection-policy-with-intune).

### <a name="see-also"></a>Zie ook
[Wat u uw eindgebruikers vertelt over het gebruik van Intune](end-user-educate.md)
