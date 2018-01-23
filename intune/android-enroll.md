---
title: Android-apparaten inschrijven bij Intune | Microsoft Docs
titlesuffix: Azure portal
description: Meer informatie over het inschrijven van Android-apparaten in Intune.
keywords: 
author: ErikjeMS
ms.author: erikje
manager: angrobe
ms.date: 01/10/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f276d98c-b077-452a-8835-41919d674db5
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 7877d0bb6ba7a9c9d51cd261a7f1fbf555f88961
ms.sourcegitcommit: 0795870bfe941612259ebec0fe313a783a44d9b9
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/11/2018
---
# <a name="enroll-android-devices"></a>Android-apparaten inschrijven

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Als Intune-beheerder kunt u Android-apparaten beheren, waaronder Samsung Knox Standard-apparaten. U kunt ook het werkprofiel [Android for Work-apparaten](#enable-enrollment-of-android-for-work-devices) beheren.

Apparaten waarop Samsung Knox Standard wordt uitgevoerd, bieden ondersteuning voor beheer van meerdere gebruikers in Intune. Eindgebruikers kunnen hun Azure AD-referenties gebruiken om zich aan en af te melden bij het apparaat. Het apparaat wordt centraal beheerd, ongeacht of het in gebruik is of niet. Wanneer gebruikers zich aanmelden, hebben ze toegang tot apps en wordt er een eventueel beleid toegepast. Wanneer ze zich afmelden, worden alle app-gegevens gewist.

## <a name="prerequisite"></a>Vereiste

U moet de MDM-instantie instellen op **Microsoft Intune** als voorbereiding op het beheer van mobiele apparaten. Zie [Set the MDM authority](mdm-authority-set.md) (De MDM-instantie instellen) voor instructies. U stelt de instantie slechts één keer in, wanneer u Intune voor het eerst instelt voor het beheer van mobiele apparaten.

## <a name="set-up-android-enrollment"></a>Android-inschrijving instellen

Standaard staat Intune de registratie van Android- en Samsung Knox Standard-apparaten toe.

Zie [Beperkingen voor apparaattypen instellen](enrollment-restrictions-set.md) als u de inschrijving wilt blokkeren van Android-apparaten of alleen Android-apparaten die het eigendom van de gebruiker zijn.

Als u apparaatbeheer wilt inschakelen, moeten uw gebruikers hun apparaat inschrijven door de app Intune-bedrijfsportal te downloaden (beschikbaar via Google Play) en vervolgens de app te openen en de prompts te volgen. Zodra Android-apparaten worden beheerd, kunt u [nalevingsbeleid toewijzen](compliance-policy-create-android.md), [apps beheren](app-management.md) en meer.

## <a name="enable-enrollment-of-android-for-work-devices"></a>Registratie van Android for Work-apparaten inschakelen

Als u het werkprofiel op apparaten met [ondersteuning voor Android for Work](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012) wilt beheren, moet u een Android for Work-binding toevoegen aan Intune. Om apparaten te registreren die ondersteuning bieden voor Android for Work, maar die eerder zijn geregistreerd als gewone Android-apparaten, moet u de inschrijving van de apparaten ongedaan maken en ze vervolgens opnieuw inschrijven.

Als u Android for Work-apparaten inschrijft met een [Device Enrollment Manager](device-enrollment-manager-enroll.md)-account, kunt u per account 10 apparaten inschrijven.

## <a name="add-android-for-work-binding-for-intune"></a>Android for Work-binding toevoegen voor Intune

1. **Intune MDM instellen**<br>
Als u dit nog niet hebt gedaan, moet u het beheer van mobiele apparaten voorbereiden door [de instantie voor het beheer van mobiele apparaten in te stellen](mdm-authority-set.md) als **Microsoft Intune**.
2. **Android for Work-binding configureren**<br>
    Meld u als Intune-beheerder aan bij Azure Portal en kies **Meer services** > **Bewaking en beheer** > **Intune**.

   a. Kies op de blade **Intune** de optie **Apparaatinschrijving** > **Inschrijving van Android for Work** en klik op **Configureren** om de Android for Work-website van Google Play te openen. De website wordt op een nieuw tabblad in de browser geopend.
   ![Schermopname met een koppeling om de Android for Work-binding te configureren](./media/android-work-bind.png)

   b. **Aanmelden bij Google**<br>
   Meld u aan op de aanmeldingspagina van Google met het Google-account dat wordt gekoppeld aan alle Android for Work-beheertaken voor deze tenant. Dit is het Google-account dat de IT-beheerders van uw bedrijf gebruiken voor het beheren en publiceren van apps in de Play for Work-console.

   c. **Organisatiegegevens opgeven**<br>
   Geef bij **Organization name** (Organisatienaam) de naam van uw bedrijf op. Bij **Enterprise mobility management (EMM) provider** moet **Microsoft Intune** worden weergegeven. Ga akkoord met de overeenkomst voor Android for Work en kies **Confirm** (Bevestigen). Uw aanvraag wordt verwerkt.

## <a name="specify-android-for-work-enrollment-settings"></a>Inschrijvingsinstellingen voor Android for Work opgeven
   Android for Work wordt alleen ondersteund op bepaalde Android-apparaten. Zie de [vereisten voor Android for Work](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012 style="target=new_window") van Google voor meer informatie. Elk apparaat dat ondersteuning biedt voor Android for Work biedt ook ondersteuning voor conventioneel Android-beheer. In Intune kunt u opgeven hoe apparaten met ondersteuning voor Android for Work moeten worden beheerd:

   - **Alle apparaten beheren als Android-apparaten**. Alle Android-apparaten, ook de apparaten met ondersteuning voor Android for Work, worden ingeschreven als conventionele Android-apparaten.
   - **Ondersteunde apparaten beheren als Android for Work-apparaten**. Alle apparaten met ondersteuning voor Android for Work worden ingeschreven als Android for Work-apparaten. Alle Android-apparaten die geen ondersteuning bieden voor Android for Work, worden geregistreerd als conventionele Android-apparaten.
   - **Alleen ondersteunde apparaten voor de gebruikers in deze gebruikersgroepen beheren als Android for Work**. U kunt Android for Work-beheer richten op een beperkte set gebruikers. Alleen voor leden van de geselecteerde groepen worden apparaten met ondersteuning voor Android for Work geregistreerd als Android for Work-apparaten. Alle overige apparaten worden geregistreerd als Android-apparaten. Dit is nuttig tijdens een Android for Work-testfase.

## <a name="approve-the-company-portal-app-in-the-managed-google-play-store"></a>De bedrijfsportal-app in de beheerde Google Play Store goedkeuren
U moet de bedrijfsportal-app voor Android in de beheerde Google Play Store goedkeuren om ervoor te zorgen dat deze automatische app-updates ontvangt. Als u deze niet goedkeurt, wordt de bedrijfsportal uiteindelijk verouderd en worden er geen nieuwe belangrijke oplossingen voor problemen of nieuwe functies ontvangen wanneer deze door Microsoft worden uitgegeven.

Volg deze stappen voor het goedkeuren van de Intune bedrijfsportal:

1.  Ga naar de bedrijfsportal-app in de [beheerde Google Play Store](https://play.google.com/work/apps/details?id=com.microsoft.windowsintune.companyportal).
2.  Meld u aan bij de beheerde Google Play Store met hetzelfde Google-account dat u hebt gebruikt om de binding voor Android for Work te configureren.
3.  Klik op **Goedkeuren.**  Hiermee wordt een nieuw dialoogvenster geopend.
4.  Controleer de machtigingen in dit dialoogvenster en klik vervolgens op **Goedkeuren**. U moet deze machtigingen toestaan om de bedrijfsportal-app het werkprofiel op het apparaat te laten beheren.
5.  Selecteer **Goedgekeurd houden wanneer de app nieuwe machtigingen aanvraagt** en klik vervolgens op **Opslaan.**

<!--  ## Next steps for Android for Work
After configuring the Android for Work binding and settings, you can do the following:
- [Deploy Android for Work apps](android-for-work-apps.md)
- [Add Android for Work configuration policies](android-for-work-policy-settings-in-microsoft-intune.md)  -->

## <a name="tell-your-users-how-to-enroll-their-devices-to-access-company-resources"></a>Uw gebruikers vertellen hoe ze hun apparaten moeten inschrijven om toegang te krijgen tot bedrijfsresources

Vertel uw gebruikers dat ze naar Google Play moeten gaan om de app Intune-bedrijfsportal te downloaden en vervolgens de app moeten openen en de prompts voor inschrijving van hun apparaat moeten volgen. De app leidt gebruikers door het inschrijvingsproces en legt uit wat gebruikers kunnen verwachten en wat IT-beheerders wel en niet kunnen zien op hun apparaten.

U kunt hen ook een link naar online inschrijvingsstappen sturen: [Uw Android-apparaat inschrijven bij Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android).

Zie de volgende artikelen voor meer informatie over andere taken voor gebruikers:

- [Bronnen over de eindgebruikerservaring in Microsoft Intune](end-user-educate.md)
- [Uw Android-apparaat gebruiken met Intune](https://docs.microsoft.com/intune-user-help/using-your-android-device-with-intune)

## <a name="unbind-your-android-for-work-administrative-account"></a>Binding van uw Android for Work-beheerdersaccount ongedaan maken

U kunt Android for Work-registratie en -beheer uitschakelen. Als u **Binding verwijderen** in de Intune-beheerconsole kiest, verwijdert u alle ingeschreven Android for Work-apparaten voor inschrijving. U verwijdert ook de relatie tussen het Android for Work-account en Intune.

### <a name="to-unbind-an-android-for-work-account"></a>Binding van een Android for Work-account ongedaan maken

1. **Android for Work-binding ongedaan maken**<br>
    Meld u als Intune-beheerder aan bij Azure Portal en kies **Meer services** > **Bewaking en beheer** > **Intune**.  Kies op de blade **Intune** **Apparaatinschrijving** > **Inschrijving van Android for Work** en kies **Binding verwijderen**.

2. **Verwijderen van Android for Work-binding bevestigen**<br>
  Kies **Ja** om de binding te verwijderen en de inschrijving van alle Android for Work-apparaten in Intune ongedaan te maken.
