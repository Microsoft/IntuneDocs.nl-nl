---
title: Lookout for Work-app implementeren | Microsoft Intune
description: Lookout for Work-apps voor Android configureren en implementeren.
author: karthikaraman
manager: angrobe
ms.date: 10/12/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 524c4209-ad57-4d35-955e-a00d796bf858
ms.reviewer: sandera
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 99005e15268a60cd801ef1c717088dff2f82927b
ms.openlocfilehash: 8dce0689d5c4a0672b227eedf3ae738217eb17cf


---

# Lookout for Work-apps configureren en implementeren
In dit artikel wordt uitgelegd hoe u de Lookout for Work-app configureert en implementeert voor Android- en iOS-apparaten.

## Android (Google Play Store-app)

* **Stap 1:** upload de Lookout for Work-app voor Android in de [Microsoft Intune-beheerdersconsole](https://manage.microsoft.com) zoals beschreven in het onderwerp [Apps voor mobiele apparaten toevoegen in Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/add-apps-for-mobile-devices-in-microsoft-intune).
>[!NOTE]
> Klik niet op het vak voor het vereisen van een beheerde browser.

![schermafdruk van de lijst met Lookout for Work-apps in de Intune-beheerdersconsole](../media/mtp/lookout-app-listed-intune-console.png)

* **Stap 2:** implementeer de app voor gebruikers. Selecteer de Lookout for Work-app in het scherm dat hierboven wordt weergegeven en selecteer vervolgens **Implementatie beheren**.

  U moet dezelfde gebruikers selecteren die zijn toegevoegd aan de optie Registratiebeheer in de Lookout-console.  Zie stap 3 in de sectie [Uw abonnement configureren met Lookout Device Threat Protection](set-up-your-subscription-with-lookout-mtp#configure-your-subscription-with-lookout-mtp) voor informatie over het toevoegen van gebruikersgroepen aan Lookout MTP.
>[!IMPORTANT]
> De implementatiewizard van Intune app is niet op de hoogte van de Azure AD-gebruikersgroepen en maakt in plaats daarvan gebruik van de Intune-gebruikersgroepen. Daarom moet u een Intune-gebruikersgroep maken op basis van de Azure AD-gebruikersgroep die is geregistreerd in de Lookout-console, zoals beschreven in [dit](plan-your-user-and-device-groups.md) onderwerp.

Kies de optie **Vereiste installatie** om te vereisen dat de Lookout-app op het apparaat van de gebruiker wordt geïnstalleerd.


## iOS (door bedrijf ondertekende versie van Lookout-app)

* **Stap 1:** zorg ervoor dat **iOS-beheer** is ingesteld op het apparaat. Zie [iOS- en Mac-apparaatbeheer instellen](Set up iOS and Mac device management.md) voor instructies voor het instellen van uw apparaat voor iOS-beheer.

* **Stap 2:** **onderteken** de Lookout for Work-app voor iOS opnieuw. De Lookout for Work-app voor iOS wordt gedistribueerd buiten de iOS App Store. **Voordat u de app distribueert**, moet u de app opnieuw ondertekenen met het iOS Enterprise Developer-certificaat. Zie het [proces voor het opnieuw ondertekenen van Lookout for Work-apps voor iOS](https://personal.support.lookout.com/hc/en-us/articles/114094038714) (Engelstalig) op de website van Lookout voor gedetailleerde instructies voor het opnieuw ondertekenen van Lookout for Work-apps voor iOS.


* **Stap 3:** schakel Azure Active Directory-verificatie voor de iOS-gebruikers als volgt in:
  1.  Meld u aan bij de [Azure Active Directory-beheerportal](https://manage.windowsazure.com) en navigeer naar de pagina met toepassingen.
  2.  Voeg de **Lookout for Work-app voor iOS** toe als een **native clienttoepassing**.
  ![schermafdruk van het dialoogvenster 'Apps toevoegen' met de optie voor een native clientapp](../media/mtp/aad-add-app.png)
  
  3. Vervang **com.lookout.enterprise.yourcompanyname** door de klantbundel-id die u hebt geselecteerd bij het ondertekenen van de IPA.
  4.  Voeg de aanvullende omleidings-URI **&lt;companyportal://code/>** toe, gevolgd door een versie met URL-codering van uw oorspronkelijke omleidings-URI.
  5.  Voeg **overgedragen machtigingen** toe aan uw app.

  Zie [Een native clienttoepassing configureren](https://azure.microsoft.com/en-us/documentation/articles/app-service-mobile-how-to-configure-active-directory-authentication/#optional-configure-a-native-client-application) (Engelstalig) voor meer informatie.


* **Stap 4:** upload het opnieuw ondertekende IPA-bestand, zoals beschreven in het onderwerp [Apps voor mobiele apparaten toevoegen in Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/add-apps-for-mobile-devices-in-microsoft-intune). Stel de minimale versie van het besturingssysteem in op iOS 8.0 of hoger.

  ![schermafbeelding van de pagina 'Apps' in de Intune-beheerdersconsole, waarbij de Lookout for Work-app is weergegeven in de lijst met apps](../media/mtp/ios-app-uploaded-intune.png)

* **Stap 5:** maak het configuratiebeleid voor de beheerde app, zoals beschreven in het onderwerp [iOS-apps met configuratiebeleid voor mobiele apps in Microsoft Intune configureren](https://docs.microsoft.com/en-us/intune/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune).

  ![schermafdruk van de wizard voor een nieuw beleid met de configuratiebeleid voor apps met iOS 8.0 of hoger gemarkeerd](../media/mtp/ios-app-config.png)

* **Stap 6:** **implementeer de app voor gebruikers**. Selecteer de Lookout for Work-app en kies **Implementatie beheren**.

  U moet dezelfde gebruikers selecteren die zijn toegevoegd aan de optie Registratiebeheer in de Lookout-console.  Zie stap 3 in de sectie [Uw abonnement configureren met Lookout Device Threat Protection](set-up-your-subscription-with-lookout-mtp#configure-your-subscription-with-lookout-mtp) voor informatie over het toevoegen van gebruikersgroepen aan Lookout MTP.
>[!IMPORTANT]
> De implementatiewizard van Intune app is niet op de hoogte van de Azure AD-gebruikersgroepen en maakt in plaats daarvan gebruik van de Intune-gebruikersgroepen. Daarom moet u een Intune-gebruikersgroep maken op basis van de Azure AD-gebruikersgroep die is geregistreerd in de Lookout-console, zoals beschreven in [dit](plan-your-user-and-device-groups.md) onderwerp.

Kies de optie **Vereiste installatie** om te vereisen dat de Lookout-app op het apparaat van de gebruiker wordt geïnstalleerd.

## Wat gebeurt er wanneer de geïmplementeerde app op het apparaat wordt geopend




Wanneer de gebruiker de Lookout for Work-app opent op het apparaat, wordt de gebruiker gevraagd de app te activeren en de optie Aanmelden bij Azure Active Directory te kiezen. Een gedetailleerd overzicht van de eindgebruikersstroom vindt u in de volgende onderwerpen:

* [U wordt gevraagd Lookout for Work te installeren op uw Android-apparaat](http://docs.microsoft.com/intune/enduser/you-are-prompted-to-install-lookout-for-work-android)

* [U moet een bedreiging oplossen die met Lookout for Work op een Android-apparaat is gevonden](http://docs.microsoft.com/intune/enduser/you-need-to-resolve-a-threat-found-by-lookout-for-work-android)

## Volgende stappen
* [De regel Device Threat Protection inschakelen in het nalevingsbeleid](enable-device-threat-protection-rule-in-compliance-policy.md)



<!--HONumber=Oct16_HO2-->


