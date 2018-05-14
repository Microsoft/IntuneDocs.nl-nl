---
title: Microsoft Intune App SDK Xamarin Bindings
description: Met Intune App SDK Xamarin Bindings kunt u het app-beveiligingsbeleid voor Intune inschakelen in iOS- en Android-apps die zijn gebouwd met Xamarin.
keywords: SDK, Xamarin, intune
author: Erikre
manager: dougeby
ms.author: erikre
ms.date: 03/19/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 275d574b-3560-4992-877c-c6aa480717f4
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 5c9f81761e7e24393471f44da4cf619f017e9bbd
ms.sourcegitcommit: 4c06fa8e9932575e546ef2e880d96e96a0618673
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/03/2018
---
# <a name="microsoft-intune-app-sdk-xamarin-bindings"></a>Microsoft Intune App SDK Xamarin Bindings

> [!NOTE]
> U kunt desgewenst eerst het artikel [Aan de slag met Intune App SDK](app-sdk-get-started.md) lezen, waarin wordt uitgelegd hoe u de integratie voor elk ondersteund platform kunt voorbereiden.

## <a name="overview"></a>Overzicht
Met [Intune App SDK Xamarin Bindings](https://github.com/msintuneappsdk/intune-app-sdk-xamarin) kunt u het [app-beveiligingsbeleid voor Intune](/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) inschakelen in iOS- en Android-apps die zijn gebouwd met Xamarin. Met bindingen kunnen ontwikkelaars eenvoudig beschermingsfuncties van Intune inbouwen in hun Xamarin-apps.

Met de Microsoft Intune App SDK Xamarin Bindings kunt u Intune-beveiligingsbeleid voor apps (ook wel APP- of MAM-beleid genoemd) opnemen in de apps die u met Xamarin hebt ontwikkeld. Een MAM-app is geïntegreerd met de Intune App SDK. IT-beheerders kunnen app-beveiligingsbeleid implementeren in uw mobiele app wanneer die actief door Intune wordt beheerd.

## <a name="whats-supported"></a>Wat wordt ondersteund

### <a name="developer-machines"></a>Machines van ontwikkelaars
* Windows
* macOS


### <a name="mobile-app-platforms"></a>Mobiele app-platformen
* Android
* iOS


### <a name="intune-mobile-application-management-scenarios"></a>Scenario’s voor Intune Mobile Application Management

* Intyne APP-WE (zonder apparaatinschrijving)
* Apparaten die zijn ingeschreven bij Intune MDM
* Apparaten die zijn ingeschreven bij EMM van derden

Xamarin-apps die zijn gemaakt met de Intune App SDK Xamarin Bindings, kunnen nu app-beveiligingsbeleid van Intune ontvangen op apparaten die wel en apparaten die niet zijn ingeschreven in MDM (Mobile Device Management) van Intune.

## <a name="prerequisites"></a>Vereisten

Controleer de [licentievoorwaarden](https://github.com/msintuneappsdk/intune-app-sdk-xamarin/blob/master/Microsoft%20License%20Terms%20Intune%20App%20SDK%20Xamarin%20Component.pdf). Een exemplaar van de licentievoorwaarden voor uw administratie afdrukken en bewaren. Door de Intune App SDK Xamarin Bindings te downloaden en gebruiken, gaat u akkoord met deze licentievoorwaarden. Als u deze niet accepteert, moet u de software niet gebruiken.

## <a name="enabling-intune-app-protection-polices-in-your-ios-mobile-app"></a>App-beveiligingsbeleid voor Intune inschakelen in uw mobiele iOS-app
1. Voeg het [Microsoft.Intune.MAM.Xamarin.iOS NuGet-pakket](https://www.nuget.org/packages/Microsoft.Intune.MAM.Xamarin.iOS) toe aan uw Xamarin.iOS-project.
2.  Volg de algemene stappen voor het integreren van de Intune App SDK in een mobiele iOS-app. U kunt beginnen met stap 3 van de integratie-instructies uit de [Ontwikkelaarshandleiding voor Microsoft Intune App SDK voor iOS](app-sdk-ios.md#build-the-sdk-into-your-mobile-app). U kunt de laatste stap in deze sectie voor het uitvoeren van de IntuneMAMConfigurator overslaan, omdat dit hulpprogramma is opgenomen in het pakket Microsoft.Intune.MAM.Xamarin.iOS en automatisch wordt uitgevoerd tijdens de compilatie.
    **Belangrijk**: delen van sleutelketens inschakelen voor een app wijkt in Visual Studio enigszins af van de procedure in Xcode. Open de plist Entitlements van de app en zorg ervoor dat de optie 'Enable Keychain' is ingeschakeld en dat de juiste groepen voor het delen van de sleutelketen in die sectie zijn toegevoegd. Controleer vervolgens of de plist Entitlements is opgegeven in het veld 'Custom Entitlements' van de opties voor 'iOS Bundle Signing' van het project voor alle betrokken configuratie-/platformcombinaties.
3.  Nadat de bindingen zijn toegevoegd en de app correct is geconfigureerd, kan uw app gebruikmaken van de Intune SDK API's. Daarvoor moet u de volgende naamruimte opnemen:

      ```csharp
      using Microsoft.Intune.MAM;
      ```
4. Om het app-beveiligingsbeleid te kunnen ontvangen, moet uw app worden geregistreerd in de Intune MAM-service. Als uw app al de Azure Active Directory Authentication Library (ADAL) gebruikt om gebruikers te verifiëren, moet uw app de UPN van de gebruiker doorgeven aan de registerAndEnrollAccount-methode van IntuneMAMEnrollmentManager nadat deze is geverifieerd:
      ```csharp
      IntuneMAMEnrollmentManager.Instance.RegisterAndEnrollAccount(string identity);
      ```
      **Belangrijk**: zorg ervoor dat u de standaard ADAL-instellingen van de Intune App SDK overschrijft met die van uw app. U kunt dit doen via de IntuneMAMSettings-woordenlijst in de Info.plist van de app, zoals vermeld in de [Ontwikkelaarshandleiding voor Microsoft Intune App SDK voor iOS](app-sdk-ios.md#configure-settings-for-the-intune-app-sdk), maar u kunt ook gebruikmaken van de eigenschappen voor het overschrijven van AAD van de IntuneMAMPolicyManager-instantie. De methode Info.plist wordt aanbevolen voor toepassingen waarvan de ADAL-instellingen statisch zijn, terwijl de eigenschappen voor overschrijven worden aanbevolen voor toepassingen die deze waarden tijdens runtime bepalen. 
      
      Als uw app geen gebruikmaakt van ADAL en u verificatie wilt uitvoeren met de SDK Intune, moet uw app de loginAndEnrollAccoun-methode van IntuneMAMEnrollmentManager aanroepen:
      ```csharp
       IntuneMAMEnrollmentManager.Instance.LoginAndEnrollAccount([NullAllowed] string identity);
      ```

## <a name="enabling-intune-app-protection-policies-in-your-android-mobile-app"></a>Intune App-beveiligingsbeleid inschakelen in uw mobiele Android-app

### <a name="xamarinandroid-integration"></a>Xamarin.Android-integratie

1. Voeg de nieuwste versie van het [Microsoft.Intune.MAM.Xamarin.Android NuGet-pakket](https://www.nuget.org/packages/Microsoft.Intune.MAM.Xamarin.Android) toe aan uw Xamarin.Android-project. Hierdoor krijgt u de benodigde referenties waarmee Intune uw toepassing kan inschakelen.

2. Lees en volg de [Intune App SDK for Android Developers Guide](app-sdk-android.md) volledig en let daarbij vooral op het volgende:
    1. De [sectie voor gehele klasse- en methodevervangingen](app-sdk-android.md#replace-classes-methods-and-activities-with-their-mam-equivalent). 
    2. De [MAMApplication-sectie](app-sdk-android.md#mamapplication). Controleer of uw subklasse op de juiste manier is voorzien van het `[Application]`-kenmerk en de `(IntPtr, JniHandleOwnership)`-constructor overschrijdt.
    3. De [sectie ADAL-integratie](app-sdk-android.md#configure-azure-active-directory-authentication-library-adal) als uw app verificatie op basis van AAD uitvoert.
    4. De [sectie MAM-WE-registratie](app-sdk-android.md#app-protection-policy-without-device-enrollment) als u van plan bent om beleid te verkrijgen via de MAM-service in uw toepassing.

> [!NOTE]
> Wanneer u probeert vergelijkbare API’s te vinden in de [Intune App SDK voor Android-ontwikkelaarshandleiding](app-sdk-android.md) in de `Microsoft.Intune.MAM.Xamarin.Android`-bindingen of codefragmenten uit de handleiding omzet, moet u zich ervan bewust zijn dat de bindingengenerator van Xamarin de Android-API’s op de volgende manieren aanpast:
> * Alle id’s worden geconverteerd naar Pascal-hoofdlettergebruik (com.foo.bar -> Com.Foo.Bar)
> * Alle get/set-bewerkingen worden omgezet naar eigenschapsbewerkingen (bijvoorbeeld Foo.getBar() -> Foo.Bar, Foo.setBar("zap") -> Foo.Bar = "zap")
> * Alle interfaces hebben het teken I als voorvoegsel bij de naam (FooInterface -> IFooInterface)

### <a name="xamarinforms-integration"></a>Xamarin.Forms-integratie

**Naast het uitvoeren van alle bovenstaande stappen** hebben we voor `Xamarin.Forms`-toepassingen het `Microsoft.Intune.MAM.Remapper`-pakket beschikbaar gesteld. This pakket voert klassevervanging voor u uit door `MAM`-klassen in te voeren in de klassehiërarchie van veel gebruikte `Xamarin.Forms`-klassen zoals `FormsAppCompatActivity` en `FormsApplicationActivity`, zodat u die klassen kunt blijven gebruiken door overschrijvingen op te geven voor de equivalente MAM-functies zoals `OnMAMCreate` en `OnMAMResume`. Ga als volgt te werk als u dit wilt gebruiken:

1.  Voeg het [Microsoft.Intune.MAM.Remapper.Tasks](https://www.nuget.org/packages/Microsoft.Intune.MAM.Remapper.Tasks) NuGet-pakket toe aan uw project. Hierdoor worden de Intune APP SDK Xamarin-bindingen automatisch toegevoegd als deze niet al hebt ingevoegd.

2.  Voeg een aanroep toe tot `Xamarin.Forms.Forms.Init(Context, Bundle)` in de functie `OnMAMCreate` van de `MAMApplication`-klasse die u hebt gemaakt in de bovenstaande stap 2.2. Dit is benodigd omdat uw toepassing met Intune-beheer op de achtergrond kan worden gestart.

> [!NOTE]
> Omdat er met deze bewerking een afhankelijkheid wordt herschreven die Visual Studio gebruikt voor automatische aanvulling met behulp van Intellisense, moet u Visual Studio mogelijk opnieuw opstarten nadat de remapper voor de eerste keer wordt uitgevoerd, om ervoor te zorgen dat Intellisense de wijzigingen herkent. 

## <a name="support"></a>Support

Als uw organisatie een bestaande Intune-klant is, kunt u contact opnemen met uw ondersteuningsmedewerker van Microsoft om een ondersteuningsticket te openen en een probleem te melden op de [Github-problemenpagina](https://github.com/msintuneappsdk/intune-app-sdk-xamarin/issues). U wordt zo snel mogelijk geholpen. 