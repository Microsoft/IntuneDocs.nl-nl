---
title: Problemen met Android Enterprise-apparaten in Microsoft Intune oplossen
description: Suggesties voor het oplossen van een aantal van de meestvoorkomende problemen bij het inschrijven van Android-apparaten in Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/25/2020
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.subservice: enrollment
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: ''
ms.reviewer: mghadial
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 04c726c1dc6af7e92b75335d105de605ef00e712
ms.sourcegitcommit: 8b716db3c0fdbb7dff62497ec283902a5069a343
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/27/2020
ms.locfileid: "77652365"
---
# <a name="troubleshoot-android-enterprise-device-problems-in-microsoft-intune"></a>Problemen met Android Enterprise-apparaten in Microsoft Intune oplossen

Dit artikel helpt Intune-beheerders om problemen bij het inschrijven van Android Enterprise-apparaten in Intune te begrijpen en op te lossen.

## <a name="apps-on-android-enterprise-devices"></a>Apps op Android Enterprise-apparaten

### <a name="managed-google-play-apps-that-arent-deployed-through-intune-are-displayed-in-the-work-profile"></a>Beheerde Google Play-apps die niet via Intune zijn geïmplementeerd, worden weergegeven in het werkprofiel
Systeemapps kunnen worden ingeschakeld in het werkprofiel door de OEM van het apparaat op het moment dat het werkprofiel wordt gemaakt. Dit wordt niet beheerd door de MDM-provider.

Volg deze stappen voor het oplossen van problemen:

  1. Logboeken van de bedrijfsportal verzamelen.
  2. Apps noteren die onverwacht in het werkprofiel verschijnen.
  3. De registratie van uw apparaat bij Intune ongedaan maken en de bedrijfsportal verwijderen.
  4. Installeer de [Test DPC](https://play.google.com/store/apps/details?id=com.afwsamples.testdpc)-app, die u in staat stelt een werkprofiel te maken om mee te testen zonder een EMM.
  5. Volg de instructies in [Test DPC](https://play.google.com/store/apps/details?id=com.afwsamples.testdpc) om een werkprofiel op het apparaat te maken.
  6. Beoordeel apps die in het werkprofiel verschijnen. 
  7. Als dezelfde apps in de Test DPC-app worden weergegeven, worden deze apps verwacht door de OEM voor dat apparaat.

### <a name="unapproved-managed-google-play-for-work-store-apps-arent-being-removed-from-the-client-apps-page-in-intune"></a>Niet-goedgekeurde, beheerde zakelijke apps uit de Google Play Store worden niet verwijderd uit de pagina Client-apps in Intune
Dit is normaal.

### <a name="managed-google-play-apps-arent-being-reported-under-the-discovered-apps-blade-in-the-intune-portal"></a>Beheerde Google Play-apps worden niet gerapporteerd onder de blade Gedetecteerde apps in de Intune-portal
Dit is normaal. Alleen systeem-apps die zijn geïnstalleerd in het werkprofiel worden geïnventariseerd in de blade Apps. Gebruik de blade **Beheerde apps** om geïnstalleerde, beheerde Google Play-apps te bekijken.

### <a name="are-web-applications-supported-for-work-profile-enrolled-devices"></a>Worden webtoepassingen ondersteund voor apparaten die op werkprofielen zijn ingeschreven?
Ja. Zie [Beheerde Google Play-webkoppelingen](../apps/apps-add-android-for-work.md#managed-google-play-web-links) voor meer informatie

## <a name="device-management"></a>Apparaatbeheer

### <a name="file-path-internal-storageandroiddatacommicrosoftwindowsintunecompanyportalfiles-missing-on-work-profile-enrolled-devices"></a>Bestandspad Internal storage/Android/Data.com.microsoft.windowsintune.companyportal/files missing on work profile enrolled devices

  **Antwoord**: Dit is normaal. Dit pad is alleen gemaakt voor het apparaatbeheerderscenario (verouderde Android-inschrijving).

  Volg de volgende stappen om logboeken voor de bedrijfsportal te verzamelen:

  1. Tik in de bedrijfsportal-app met de badge op **Menu** > **Help** > **E-mailondersteuning** en klik vervolgens op **E-mail en uploadlogboeken verzenden**. 
  2. Selecteer een van de e-mailapps als u de vraag **hulpaanvraag verzenden met** krijgt.
  3. Er wordt een e-mail naar uw IT-beheerder gegenereerd met een incident-id die kan worden opgegeven aan de Microsoft-productondersteuning.

### <a name="managed-google-play-last-sync-time--hasnt-been-updated-in-days"></a>Laatste synchronisatietijd van Google Play is al dagen niet bijgewerkt
Dit is normaal. De synchronisatie kan alleen handmatig worden geactiveerd.

### <a name="encryption-is-required-when-a-device-is-enrolled-can-it-be-turned-off"></a>Versleuteling is vereist bij het inschrijven van een apparaat. Kan dit worden uitgeschakeld?
Nee, Google vereist dat het apparaat wordt versleuteld voor het maken van een werkprofiel. 

### <a name="samsung-devices-are-blocking-the-use-of-third-party-keyboards-like-swiftkey"></a>Op Samsung-apparaten wordt het gebruik van toetsenborden van derden, bijvoorbeeld SwiftKey, geblokkeerd
Samsung heeft deze beperking ingevoerd op apparaten met Android 8.0 of hoger. Microsoft werkt samen met Samsung aan dit probleem en zal nieuwe informatie posten zodra deze beschikbaar is.

## <a name="remote-actions"></a>Externe acties

### <a name="wipe-factory-reset-option-isnt-available-for-work-profile-enrolled-device"></a>De optie Wissen (fabrieksinstellingen herstellen) is niet beschikbaar voor een apparaat dat op een werkprofiel is ingeschreven
Dit is normaal. In het werkprofielscenario heeft de MDM-provider geen volledige controle over het apparaat. De enige beschikbare optie is Buiten gebruik stellen (bedrijfsgegevens verwijderen), welke het volledige werkprofiel en alle inhoud daarvan verwijdert.

### <a name="is-device-passcode-reset-supported"></a>Wordt wachtwoordcode van het apparaat opnieuw instellen ondersteund?
Voor apparaten die op een werkprofiel zijn ingeschreven, kunt u alleen op apparaten met Android 8.0 of hoger de wachtwoordcode herstellen als:
- de wachtwoordcode van het werkprofiel beheerd is,
- de eindgebruiker u gemachtigd heeft deze te herstellen.

Wachtwoordcode voor apparaat herstellen wordt ondersteund voor toegewezen apparaten (COSU) en volledig beheerde apparaten.


## <a name="next-steps"></a>Volgende stappen

- [Problemen bij de apparaatinschrijving oplossen](../troubleshoot-device-enrollment-in-intune.md)
- [Stel een vraag op het Intune-forum](https://social.technet.microsoft.com/Forums/%7Blang-locale%7D/home?category=microsoftintune&filter=alltypes&sort=lastpostdesc)
- [Lees de blog van het Microsoft Intune Support Team](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/bg-p/IntuneCustomerSuccess)
- [Lees de blog Microsoft Enterprise Mobility and Security](https://techcommunity.microsoft.com/t5/Azure-Active-Directory-Identity/Announcing-the-public-preview-of-Azure-AD-group-based-license/ba-p/245210)