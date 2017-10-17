---
title: De app Lookout for Work implementeren
description: Lookout for Work-apps voor Android configureren en implementeren.
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/21/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 524c4209-ad57-4d35-955e-a00d796bf858
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: sandera
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: fd0ad36f40463ab56f1a5ab0a11fa9eeb0c35db4
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/10/2017
---
# <a name="configure-and-deploy-lookout-for-work-app"></a>De Lookout for Work-app configureren en implementeren

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

In dit artikel wordt uitgelegd hoe u de Lookout for Work-app configureert en implementeert voor Android- en iOS-apparaten.

## <a name="android-google-play-store-app"></a>Android (Google Play Store-app)

1.  Ga in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com) naar **Apps** en kies **Apps toevoegen**.
2.  Kies op de pagina **Setup van software** van de uitgever de optie **Externe koppeling** en geef de volgende URL op: https://play.google.com/store/apps/details?id=com.lookout.enterprise
  >[!NOTE]
  >Klik niet op het vak voor het vereisen van een beheerde browser.

3.  Vul op de pagina **Beschrijving van software** de volgende informatie in:
  * **Uitgever:** Lookout Mobile Security
  * **Naam:** Lookout for Work
  * **Beschrijving:** Lookout biedt de beste beveiliging tegen mobiele bedreigingen om uw apparaat te beschermen. Wanneer de Lookout-app op het apparaat is geïnstalleerd, wordt uw apparaat met de app beschermd tegen bedreigingen en worden u en uw bedrijfsbeheerder gewaarschuwd als een bedreiging wordt aangetroffen.
  * **Categorie:** computerbeheer

4. Na voltooiing wordt het bericht **Het uploaden van gegevens naar Microsoft Intune is voltooid** weergegeven.

  Wanneer u nu in de Intune-console op **Apps** klikt, wordt de **Lookout for Work**-app weergegeven in de lijst. ![schermopname van de pagina Apps van de Intune-beheerconsole waarop de Lookout for Work-app wordt weergegeven](../media/mtp/lookout-app-listed-intune-console.png)

5. Implementeer de app voor gebruikers door de Lookout for Work-app te selecteren en **Implementatie beheren** te kiezen.

  U moet dezelfde gebruikers selecteren als die zijn toegevoegd aan de optie Registratiebeheer in de Lookout MTP-console.  Zie stap 3 in de sectie [Uw abonnement configureren met Lookout MTP](configure-deploy-lookout-for-work-app.md) voor informatie over het toevoegen van gebruikersgroepen aan Lookout MTP.

  >[!IMPORTANT]
  > De Intune-wizard voor implementatie van apps is onbekend met de Azure AD-gebruikersgroepen en in plaats daarvan worden de Intune-gebruikersgroepen gebruikt. U moet daarom een Intune-gebruikersgroep maken op basis van de Azure AD-gebruikersgroep die in de Lookout MTP-console is geregistreerd, zoals beschreven in [dit](plan-your-user-and-device-groups.md) onderwerp.

6. Kies de optie **Vereiste installatie** om te vereisen dat de Lookout-app op het apparaat van de gebruiker wordt geïnstalleerd.

## <a name="ios-enterprise-signed-version-of-lookout-app"></a>iOS (door bedrijf ondertekende versie van Lookout-app)

1. Zorg ervoor dat **iOS-beheer** is ingesteld op het apparaat. Zie [iOS- en Mac-apparaatbeheer instellen](set-up-ios-and-mac-management-with-microsoft-intune.md) voor instructies voor het instellen van uw apparaat voor iOS-beheer.

2. **Onderteken opnieuw** de Lookout for Work-app voor iOS. De Lookout for Work-app voor iOS wordt gedistribueerd buiten de iOS App Store. **Voordat u de app distribueert**, moet u de app opnieuw ondertekenen met het iOS Enterprise Developer-certificaat. Zie het [proces voor het opnieuw ondertekenen van Lookout for Work-apps voor iOS](https://personal.support.lookout.com/hc/articles/114094038714) (Engelstalig) op de website van Lookout voor gedetailleerde instructies voor het opnieuw ondertekenen van Lookout for Work-apps voor iOS.

3. Schakel Azure Active Directory-verificatie voor de iOS-gebruikers als volgt in:
  1.  Meld u aan bij de [Azure Active Directory-beheerportal](https://manage.windowsazure.com) en navigeer naar de pagina met toepassingen.
  2.  Voeg de **Lookout for Work-app voor iOS** toe als een **native clienttoepassing**.
  ![schermopname van het dialoogvenster Apps toevoegen met de optie voor een native clientapp](../media/mtp/aad-add-app.png)
  3. Vervang **com.lookout.enterprise.yourcompanyname** door de klantbundel-id die u hebt geselecteerd bij het ondertekenen van de IPA.
  4.  Voeg de aanvullende omleidings-URI **&lt;companyportal://code/>** toe, gevolgd door een versie met URL-codering van uw oorspronkelijke omleidings-URI.
  5.  Voeg **overgedragen machtigingen** toe aan uw app.

  Zie [Een native clienttoepassing configureren](https://azure.microsoft.com/documentation/articles/app-service-mobile-how-to-configure-active-directory-authentication/#optional-configure-a-native-client-application) (Engelstalig) voor meer informatie.

4. Upload het opnieuw ondertekende IPA-bestand, zoals beschreven in het onderwerp [Apps voor mobiele apparaten toevoegen in Microsoft Intune](/intune-classic/deploy-use/add-apps-for-mobile-devices-in-microsoft-intune). Stel de minimale versie van het besturingssysteem in op iOS 8.0 of hoger.

  ![schermafbeelding van de pagina 'Apps' in de Intune-beheerdersconsole, waarbij de Lookout for Work-app is weergegeven in de lijst met apps](../media/mtp/ios-app-uploaded-intune.png)

5. Maak het configuratiebeleid voor de beheerde app, zoals beschreven in het onderwerp [iOS-apps met configuratiebeleid voor mobiele apps in Microsoft Intune configureren](/intune-classic/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune).

  ![schermafdruk van de wizard voor een nieuw beleid met de configuratiebeleid voor apps met iOS 8.0 of hoger gemarkeerd](../media/mtp/ios-app-config.png)

6. **De app voor gebruikers implementeren**: selecteer de Lookout for Work-app en kies **Implementatie beheren**.

  U moet dezelfde gebruikers selecteren die zijn toegevoegd aan de optie Registratiebeheer in de Lookout-console.  Zie stap 3 in de sectie [Uw Lookout-abonnement configureren](https://docs.microsoft.com/sccm/protect/deploy-use/configure-and-deploy-lookout-for-work-apps) voor informatie over het toevoegen van gebruikersgroepen aan Lookout MTP.

  >[!IMPORTANT]
  > De implementatiewizard van Intune app is niet op de hoogte van de Azure AD-gebruikersgroepen en maakt in plaats daarvan gebruik van de Intune-gebruikersgroepen. Daarom moet u een Intune-gebruikersgroep maken op basis van de Azure AD-gebruikersgroep die is geregistreerd in de Lookout-console, zoals beschreven in [dit](plan-your-user-and-device-groups.md) onderwerp.

  Kies de optie **Vereiste installatie** om te vereisen dat de Lookout-app op het apparaat van de gebruiker wordt geïnstalleerd.

## <a name="what-happens-when-the-deployed-app-is-opened-on-the-device"></a>Wat gebeurt er wanneer de geïmplementeerde app op het apparaat wordt geopend
https://github.com/Microsoft/Docs/blob/master/ContributorGuide/index.md Wanneer de gebruiker de Lookout for Work-app opent op het apparaat, wordt de gebruiker gevraagd de app te activeren en de optie Aanmelden bij Azure Active Directory te kiezen. Een gedetailleerd overzicht van de eindgebruikersstroom vindt u in de volgende onderwerpen:

* [U wordt gevraagd Lookout for Work te installeren op uw Android-apparaat](https://docs.microsoft.com/intune-user-help/you-are-prompted-to-install-lookout-for-work-android)

* [U moet een bedreiging oplossen die met Lookout for Work op een Android-apparaat is gevonden](https://docs.microsoft.com/intune-user-help/you-need-to-resolve-a-threat-found-by-lookout-for-work-android)

## <a name="next-steps"></a>Volgende stappen
* [Het nalevingsbeleid voor Lookout-apparaten maken in Intune](https://docs.microsoft.com/sccm/protect/deploy-use/enable-device-threat-protection-rule-compliance-policy)
