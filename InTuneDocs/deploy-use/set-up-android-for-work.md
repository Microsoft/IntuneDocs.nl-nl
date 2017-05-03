---
title: Android for Work instellen | Microsoft Docs
description: Schakel het beheer van mobiele apparaten (MDM) in voor Android for Work-apparaten met Microsoft Intune.
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/29/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b2fdcea9-9ad7-4d73-88e2-854b7a774bb2
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 8b2bd3ecba0b597bc742ea08872ffe8fc58155cf
ms.openlocfilehash: 660d0c69fc09c6ec8b82185b3808269ef4bb6852
ms.lasthandoff: 04/24/2017


---

# <a name="enable-enrollment-of-android-for-work-devices"></a>Registratie van Android for Work-apparaten inschakelen

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Om Android for Work-apparaten te kunnen beheren, moet u een Android for Work-binding toevoegen aan Intune. Om apparaten te registreren die ondersteuning bieden voor Android for Work, maar die eerder zijn geregistreerd als gewone Android-apparaten, moet u de registratie van de apparaten eerst ongedaan maken en ze vervolgens opnieuw registreren.

## <a name="add-android-for-work-binding-for-intune"></a>Android for Work-binding toevoegen voor Intune

1. **Intune instellen**<br>
Als u dit nog niet hebt gedaan, moet u het beheer van mobiele apparaten voorbereiden door de [beheerautoriteit voor mobiele apparaten in te stellen](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-8#enable-device-enrollment) op **Microsoft Intune** en MDM in te stellen.

2. **Android for Work-binding configureren**<br>
    Open de [Microsoft Intune-beheerconsole](https://manage.microsoft.com) als Intune-beheerder, ga naar **Beheer** &gt; **Mobile Device Management** &gt; **Android for Work** en klik op **Configureren** om de Android for Work-website van Google Play te openen. Deze wordt geopend in een nieuw tabblad in de browser.

3. **Aanmelden bij Google**<br>
   Meld u aan op de aanmeldingspagina van Google met het Google-account dat wordt gekoppeld aan alle Android for Work-beheertaken voor deze tenant. Dit is het Google-account dat door de IT-beheerders in uw organisatie wordt gebruikt voor het beheren en publiceren van apps in de Play for Work-console.

4. **Organisatiegegevens opgeven**<br>
   Geef bij **Organization name** (Organisatienaam) de naam van uw bedrijf op. Bij **Enterprise mobility management (EMM) provider** moet *Microsoft Intune* worden weergegeven. Ga akkoord met de overeenkomst voor Android for Work, en klik op **Confirm** (Bevestigen). Uw aanvraag wordt verwerkt.

## <a name="specify-android-for-work-enrollment-settings"></a>Registratie-instellingen voor Android for Work opgeven
   Android for Work wordt alleen ondersteund op bepaalde Android-apparaten. Zie de [vereisten voor Android for Work](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012 style="target=new_window") van Google voor meer informatie.  Elk apparaat dat ondersteuning biedt voor Android for Work, biedt ook ondersteuning voor conventioneel Android-beheer.  In Intune kunt u opgeven hoe apparaten met ondersteuning voor Android for Work moeten worden beheerd:

   - **Alle apparaten beheren als Android-apparaten**: alle Android-apparaten, ook de apparaten met ondersteuning voor Android for Work, worden geregistreerd als conventionele Android-apparaten.
   - **Ondersteunde apparaten beheren als Android for Work-apparaten**: alle apparaten met ondersteuning voor Android for Work worden geregistreerd als Android for Work-apparaten. Alle Android-apparaten die geen ondersteuning bieden voor Android for Work, worden geregistreerd als conventionele Android-apparaten.
   - **Ondersteunde apparaten alleen beheren als Android for Work-apparaten voor gebruikers in deze gebruikersgroepen**: hiermee kunt u Android for Work-beheer beperken tot bepaalde gebruikers. Alleen voor leden van de geselecteerde groepen worden apparaten met ondersteuning voor Android for Work geregistreerd als Android for Work-apparaten. Alle overige apparaten worden geregistreerd als Android-apparaten. Dit is nuttig tijdens een Android for Work-testfase.

## <a name="next-steps-for-android-for-work"></a>Volgende stappen voor Android for Work
Nadat u de Android for Work-binding en -instellingen hebt geconfigureerd, kunt u het volgende doen:
- [Android for Work-apps implementeren](android-for-work-apps.md)
- [Android for Work-configuratiebeleid toevoegen](android-for-work-policy-settings-in-microsoft-intune.md)

## <a name="unbinding-your-android-for-work-administrative-account"></a>Binding van uw Android for Work-beheerdersaccount ongedaan maken

U kunt Android for Work-registratie en -beheer uitschakelen. Door in de Intune-beheerconsole op **Binding ongedaan maken** te klikken, worden alle geregistreerde Android for Work-apparaten en de relatie tussen het Android for Work-account en Intune verwijderd.

### <a name="how-to-unbind-an-android-for-work-account"></a>Binding van een Android for Work-account ongedaan maken

1. **Android for Work-binding ongedaan maken**<br>
    Open de [Microsoft Intune-beheerconsole](https://manage.microsoft.com) als gebruiker met administratorbevoegdheden, ga naar **Beheer** &gt; **Mobile Device Management** &gt; **Android for Work** en klik op **Binding ongedaan maken**.

2. **Verwijderen van Android for Work-binding bevestigen**<br>
  Klik op **Ja** om de binding te verwijderen en de registratie van alle Android for Work-apparaten in Intune ongedaan te maken.

