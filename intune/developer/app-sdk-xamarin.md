---
title: Microsoft Intune App SDK Xamarin Bindings
description: Met Intune App SDK Xamarin Bindings kunt u het app-beveiligingsbeleid voor Intune inschakelen in iOS- en Android-apps die zijn gebouwd met Xamarin.
keywords: SDK, Xamarin, intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 02/28/2020
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: developer
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 275d574b-3560-4992-877c-c6aa480717f4
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune
ms.collection: M365-identity-device-management
ms.openlocfilehash: 183cc5ed233de4a3285cf5cfd3290aead9c1de72
ms.sourcegitcommit: 9ee2401a2f01373a962749b0728c22385dbcba6d
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/29/2020
ms.locfileid: "78181905"
---
# <a name="microsoft-intune-app-sdk-xamarin-bindings"></a>Microsoft Intune App SDK Xamarin Bindings

> [!NOTE]
> U kunt desgewenst eerst het artikel [Aan de slag met Intune App SDK](app-sdk-get-started.md) lezen, waarin wordt uitgelegd hoe u de integratie voor elk ondersteund platform kunt voorbereiden.

## <a name="overview"></a>Overzicht
Met [Intune App SDK Xamarin Bindings](https://github.com/msintuneappsdk/intune-app-sdk-xamarin) kunt u het [app-beveiligingsbeleid voor Intune](../apps/app-protection-policy.md) inschakelen in iOS- en Android-apps die zijn gebouwd met Xamarin. Met bindingen kunnen ontwikkelaars eenvoudig beschermingsfuncties van Intune inbouwen in hun Xamarin-apps.

Met de Microsoft Intune App SDK Xamarin Bindings kunt u Intune-beveiligingsbeleid voor apps (ook wel APP- of MAM-beleid genoemd) opnemen in de apps die u met Xamarin hebt ontwikkeld. Een MAM-app is geïntegreerd met de Intune App SDK. IT-beheerders kunnen app-beveiligingsbeleid implementeren in uw mobiele app wanneer die actief door Intune wordt beheerd.

## <a name="whats-supported"></a>Wat wordt ondersteund

### <a name="developer-machines"></a>Machines van ontwikkelaars
* Windows (Visual Studio versie 15.7+)
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

Controleer de [licentievoorwaarden](https://github.com/msintuneappsdk/intune-app-sdk-xamarin/blob/master/Microsoft%20License%20Terms%20Intune%20App%20SDK%20Xamarin%20Component.pdf). Een exemplaar van de licentievoorwaarden voor uw administratie afdrukken en bewaren. Door de Intune App SDK Xamarin Bindings te downloaden en gebruiken, gaat u akkoord met deze licentievoorwaarden. Als u deze niet accepteert, mag u de software niet gebruiken.

De Intune SDK is afhankelijk van [Active Directory Authentication Library (ADAL)](https://azure.microsoft.com/documentation/articles/active-directory-authentication-libraries/) voor de [verificatie](https://azure.microsoft.com/documentation/articles/active-directory-authentication-scenarios/) en voorwaardelijke startscenario's, die vereisen dat apps worden geconfigureerd met [Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-whatis/). 

Als uw toepassing al is geconfigureerd voor het gebruik van ADAL of MSAL en een eigen aangepaste client-id heeft waarmee u met Azure Active Directory kunt verifiëren, zorgt u ervoor dat u de stappen volgt voor het geven van uw Xamarin-app-machtigingen aan de Intune MAM-service (Mobile Application Management). Gebruik de instructies in de sectie [Uw app toegang geven tot de Intune-app-beveiligingsservice](app-sdk-get-started.md#give-your-app-access-to-the-intune-app-protection-service-optional) van de handleiding [Aan de slag met de Intune-SDK](app-sdk-get-started.md).

## <a name="security-considerations"></a>Beveiligingsoverwegingen

Potentiële adresvervalsing (spoofing), vrijgeven van informatie en uitbreiding van bevoegdheden voorkomen:

* Zorg ervoor dat de ontwikkeling van Xamarin-apps wordt uitgevoerd op een beveiligd werkstation.
* Zorg ervoor dat de bindingen afkomstig zijn van een geldige Microsoft-bron:
  * [MS Intune App SDK NuGet-profiel](https://www.nuget.org/profiles/msintuneappsdk)
  * [Intune App SDK Xamarin GitHub-opslagplaats](https://github.com/msintuneappsdk/intune-app-sdk-xamarin)
* Configureer uw NuGet-configuratie voor uw project om ondertekende, ongewijzigde NuGet-pakketten te vertrouwen.
Zie [Ondertekende pakketten installeren](https://docs.microsoft.com/nuget/consume-packages/installing-signed-packages) voor meer informatie.
* Beveilig de uitvoermap die de Xamarin-app bevat. Overweeg het gebruik van een map op gebruikersniveau voor de uitvoer.


## <a name="enabling-intune-app-protection-polices-in-your-ios-mobile-app"></a>App-beveiligingsbeleid voor Intune inschakelen in uw mobiele iOS-app
1. Voeg het [Microsoft.Intune.MAM.Xamarin.iOS NuGet-pakket](https://www.nuget.org/packages/Microsoft.Intune.MAM.Xamarin.iOS) toe aan uw Xamarin.iOS-project.
2. Volg de algemene stappen voor het integreren van de Intune App SDK in een mobiele iOS-app. U kunt beginnen met stap 3 van de integratie-instructies uit de [Ontwikkelaarshandleiding voor Microsoft Intune App SDK voor iOS](app-sdk-ios.md#build-the-sdk-into-your-mobile-app). U kunt de laatste stap in deze sectie voor het uitvoeren van de IntuneMAMConfigurator overslaan, omdat dit hulpprogramma is opgenomen in het pakket Microsoft.Intune.MAM.Xamarin.iOS en automatisch wordt uitgevoerd tijdens de compilatie.
    **Belangrijk**: delen van sleutelketens inschakelen voor een app wijkt in Visual Studio enigszins af van de procedure in Xcode. Open de plist Entitlements van de app en zorg ervoor dat de optie 'Enable Keychain' is ingeschakeld en dat de juiste groepen voor het delen van de sleutelketen in die sectie zijn toegevoegd. Controleer vervolgens of de plist Entitlements is opgegeven in het veld 'Custom Entitlements' van de opties voor 'iOS Bundle Signing' van het project voor alle betrokken configuratie-/platformcombinaties.
3. Nadat de bindingen zijn toegevoegd en de app correct is geconfigureerd, kan uw app gebruikmaken van de Intune SDK API's. Daarvoor moet u de volgende naamruimte opnemen:

      ```csharp
      using Microsoft.Intune.MAM;
      ```

4. Om het app-beveiligingsbeleid te kunnen ontvangen, moet uw app worden geregistreerd in de Intune MAM-service. Als uw app de [Azure Active Directory Authentication Library](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory) (ADAL) of de [Microsoft Authentication Library](https://www.nuget.org/packages/Microsoft.Identity.Client) (MSAL) niet gebruikt om gebruikers te verifiëren en u de verificatie wilt laten verwerken door de Intune-SDK, moet uw app de UPN van de gebruiker doorgeven aan de LoginAndEnrollAccount-methode van IntuneMAMEnrollmentManager:

      ```csharp
       IntuneMAMEnrollmentManager.Instance.LoginAndEnrollAccount([NullAllowed] string identity);
      ```

      Apps worden mogelijk als null doorgegeven als het UPN van de gebruiker niet bekend is op het moment van de aanroep. In dit geval wordt gebruikers gevraagd zowel hun e-mailadres als hun wachtwoord in te voeren.
      
      Als uw app al ADAL of MSAL gebruikt om gebruikers te verifiëren, kunt u een SSO-ervaring (Single-sign-on) tussen uw app en de Intune-SDK configureren. Eerst moet u de AAD-instellingen die door de Intune-SDK worden gebruikt, overschrijven door de AAD-instellingen van uw app. U kunt dit doen via de IntuneMAMSettings-woordenlijst in de Info.plist van de app, zoals vermeld in de [Ontwikkelaarshandleiding voor Microsoft Intune App SDK voor iOS](app-sdk-ios.md#configure-settings-for-the-intune-app-sdk). U kunt ook gebruikmaken van code via de eigenschappen voor het overschrijven van AAD van de IntuneMAMSettings-klasse. De methode Info.plist wordt aanbevolen voor toepassingen waarvan de ADAL-instellingen statisch zijn, terwijl de eigenschappen voor overschrijven worden aanbevolen voor toepassingen die deze waarden tijdens runtime bepalen. Zodra alle SSO-instellingen zijn geconfigureerd, moet uw app de UPN van de gebruiker aan de RegisterAndEnrollAccount-methode van IntuneMAMEnrollmentManager doorgeven zodra deze is geverifieerd:

      ```csharp
      IntuneMAMEnrollmentManager.Instance.RegisterAndEnrollAccount(string identity);
      ```

      Apps kunnen het resultaat van een registratiepoging bepalen door de EnrollmentRequestWithStatus-methode te implementeren in een subklasse van IntuneMAMEnrollmentDelegate en de eigenschap Delegeren van IntuneMAMEnrollmentManager Delegate in te stellen op een exemplaar van die klasse. 

      Na een geslaagde registratie kunnen apps de UPN van het geregistreerde account bepalen (als deze nog niet bekend was) door een query uit te voeren op de volgende eigenschap: 

      ```csharp
       string enrolledAccount = IntuneMAMEnrollmentManager.Instance.EnrolledAccount;
      ```      
### <a name="sample-applications"></a>Voorbeeldtoepassingen
Voorbeeldtoepassingen waarin MAM-functionaliteit in Xamarin.iOS-apps wordt belicht, zijn beschikbaar in [GitHub](https://github.com/msintuneappsdk/sample-intune-xamarin-ios).

> [!NOTE] 
> Er is geen remapper voor iOS/iPadOS. De integratie in een Xamarin.Forms-app zou hetzelfde moeten zijn als voor een gewoon Xamarin.iOS-project. 

## <a name="enabling-intune-app-protection-policies-in-your-android-mobile-app"></a>Intune App-beveiligingsbeleid inschakelen in uw mobiele Android-app
1. Voeg het [Microsoft.Intune.MAM.Xamarin.Android NuGet-pakket](https://www.nuget.org/packages/Microsoft.Intune.MAM.Xamarin.Android) toe aan uw Xamarin.Android-project.
    1. Voeg voor een Xamarin.Forms-app ook het [Microsoft.Intune.MAM.Remapper.Tasks NuGet-pakket](https://www.nuget.org/packages/Microsoft.Intune.MAM.Remapper.Tasks) toe aan uw Xamarin.Android-project. 
2. Volg de algemene stappen die nodig zijn om [de Intune App SDK te integreren](app-sdk-android.md) in een mobiele Android-app en raadpleeg dit document voor aanvullende informatie.

### <a name="xamarinandroid-integration"></a>Xamarin.Android-integratie

Een volledig overzicht voor het integreren van de Intune App SDK kunt u vinden in de [Ontwikkelaarshandleiding voor Microsoft Intune App SDK voor Android](app-sdk-android.md). Als u de handleiding leest en de Intune App SDK integreert in uw Xamarin-app, zijn de volgende secties bedoeld om de verschillen te belichten tussen de implementatie voor een systeemeigen Android-app die is ontwikkeld in Java en een Xamarin-app die is ontwikkeld in C#. Deze secties moeten worden beschouwd als aanvullend en zijn geen vervanging voor het lezen van de handleiding als geheel.

#### <a name="remapper"></a>Remapper
Vanaf release 1.4428.1 kan het pakket `Microsoft.Intune.MAM.Remapper` worden toegevoegd aan een Xamarin.Android-toepassing als [buildhulpprogramma](app-sdk-android.md#build-tooling) om de MAM-klasse, -methode en -vervanging van de systeemservices uit te voeren. Als de remapper is opgenomen, worden de MAM-equivalente vervangingsgedeelten van de methoden waarvan de naam is gewijzigd en de MAM-toepassingssecties automatisch uitgevoerd wanneer de toepassing wordt gebouwd.

Als u een klasse wilt uitsluiten van MAM'ificatie door de remapper kunt u de volgende eigenschap toevoegen aan het `.csproj`-bestand van uw projecten.

```xml
  <PropertyGroup>
    <ExcludeClasses>Semicolon separated list of relative class paths to exclude from MAM-ification</ExcludeClasses>
  </PropertyGroup>
```

> [!NOTE]
> Met de remapper is foutopsporing in Xamarin.Android-apps momenteel niet mogelijk. Voor het opsporen van fouten in uw toepassing wordt handmatige integratie aanbevolen.

#### <a name="renamed-methods"></a>[Methoden waarvan de naam is gewijzigd](app-sdk-android.md#renamed-methods)
In veel gevallen is een methode die in de Android-klasse beschikbaar is, in de vervangende MAM-klasse als definitief gemarkeerd. De vervangende MAM-klasse biedt in dit geval een gelijknamige methode (voorafgegaan door `MAM`) die in plaats daarvan moet worden overschreven. Wanneer een activiteit wordt afgeleid van `MAMActivity`, moet niet `OnCreate()` worden overschreven en niet `base.OnCreate()` worden aangeroepen, maar moet `Activity``OnMAMCreate()` overschrijven en `base.OnMAMCreate()` aanroepen.

#### <a name="mam-application"></a>[MAM-toepassing](app-sdk-android.md#mamapplication)
Uw app moet een definitie van een `Android.App.Application`-klasse bevatten. Bij handmatige integratie van MAM moet MAM overnemen van `MAMApplication`. Controleer of uw subklasse op de juiste manier is voorzien van het `[Application]`-kenmerk en de `(IntPtr, JniHandleOwnership)`-constructor overschrijdt.

```csharp
    [Application]
    class TaskrApp : MAMApplication
    {
    public TaskrApp(IntPtr handle, JniHandleOwnership transfer)
        : base(handle, transfer) { }
```

> [!NOTE]
> Een probleem met de MAM Xamarin-bindingen kan ertoe leiden dat de toepassing crasht indien deze is geïmplementeerd in de foutopsporingsmodus. Als tijdelijke oplossing moet het kenmerk `Debuggable=false` worden toegevoegd aan de `Application`-klasse en moet de markering `android:debuggable="true"` worden verwijderd uit het manifest als deze handmatig was ingesteld.

#### <a name="enable-features-that-require-app-participation"></a>[Functies inschakelen waarvoor app-deelname is vereist](app-sdk-android.md#enable-features-that-require-app-participation)
Voorbeeld: Bepalen of er een pincode is vereist voor de app

```csharp
MAMPolicyManager.GetPolicy(currentActivity).IsPinRequired;
```

Voorbeeld: De primaire Intune-gebruiker bepalen

```csharp
IMAMUserInfo info = MAMComponents.Get<IMAMUserInfo>();
return info?.PrimaryUser;
```

Voorbeeld: Bepalen of opslaan naar apparaat of in de cloud is toegestaan

```csharp
MAMPolicyManager.GetPolicy(currentActivity).GetIsSaveToLocationAllowed(SaveLocation service, String username);
```

#### <a name="register-for-notifications-from-the-sdk"></a>[Registreren voor meldingen van de SDK](app-sdk-android.md#register-for-notifications-from-the-sdk)
Uw app moet worden geregistreerd voor meldingen van de SDK door een `MAMNotificationReceiver` te maken en deze te registreren met `MAMNotificationReceiverRegistry`. Dit wordt gedaan door de ontvanger en het gewenste type melding op te geven in `App.OnMAMCreate`, zoals in het volgende voorbeeld te zien is:

```csharp
public override void OnMAMCreate()
{
    // Register the notification receivers
    IMAMNotificationReceiverRegistry registry = MAMComponents.Get<IMAMNotificationReceiverRegistry>();
    foreach (MAMNotificationType notification in MAMNotificationType.Values())
    {
        registry.RegisterReceiver(new ToastNotificationReceiver(this), notification);
    }
    ...
```

#### <a name="mam-enrollment-manager"></a>[MAM-inschrijvingsmanager](app-sdk-android.md#mamenrollmentmanager)

```csharp
IMAMEnrollmentManager mgr = MAMComponents.Get<IMAMEnrollmentManager>();
```

### <a name="xamarinforms-integration"></a>Xamarin.Forms-integratie

Voor `Xamarin.Forms`-toepassingen voert het pakket `Microsoft.Intune.MAM.Remapper` automatisch MAM-klassevervanging uit door `MAM`-klassen te injecteren in de klassehiërarchie van veelgebruikte `Xamarin.Forms`-klassen. 

> [!NOTE]
> De Xamarin.Forms-integratie moet worden uitgevoerd naast de Xamarin.Android-integratie die hierboven is beschreven. De remapper werkt anders voor Xamarin.Forms-apps, zodat de handmatige MAM-vervanging toch moet worden uitgevoerd.

Zodra de remapper is toegevoegd aan uw project moet u de vervangingen door MAM-equivalenten uitvoeren. U kunt bijvoorbeeld `FormsAppCompatActivity` en `FormsApplicationActivity` in uw toepassing blijven gebruiken mits overschrijvingen van `OnCreate` en `OnResume` zijn vervangen door respectievelijk de MAM-equivalenten `OnMAMCreate` en `OnMAMResume`.

```csharp
    public class MainActivity : global::Xamarin.Forms.Platform.Android.FormsAppCompatActivity
    {
        protected override void OnMAMCreate(Bundle savedInstanceState)
        {
            base.OnMAMCreate(savedInstanceState);
            global::Xamarin.Forms.Forms.Init(this, savedInstanceState);
            LoadApplication(new App());
        }
```

Zolang u de vervangingen niet doorvoert, kunnen de volgende compilatiefouten optreden:
* [Compilatiefout CS0239](https://docs.microsoft.com/dotnet/csharp/misc/cs0239). Deze fout wordt veelal gezien in deze vorm ``'MainActivity.OnCreate(Bundle)': cannot override inherited member 'MAMAppCompatActivityBase.OnCreate(Bundle)' because it is sealed``.
Dit is verwacht want wanneer de remapper de overname van Xamarin-klassen wijzigt, worden sommige functies `sealed` en wordt een nieuwe MAM-variant toegevoegd aan de overschrijving.
* [Compilatiefout CS0507](https://docs.microsoft.com/dotnet/csharp/language-reference/compiler-messages/cs0507): Deze fout wordt veelal gezien in deze vorm ``'MyActivity.OnRequestPermissionsResult()' cannot change access modifiers when overriding 'public' inherited member ...``. Wanneer de remapper de overname van sommige Xamarin-klassen wijzigt, worden sommige lidfuncties gewijzigd in `public`. Als u een van deze functies overschrijft, moet u de toegangsmodificator voor deze overschrijvingen ook wijzigen in `public`.

> [!NOTE]
> Met de remapper wordt een afhankelijkheid herschreven die in Visual Studio wordt gebruikt voor automatische aanvulling via IntelliSense. Wanneer de remapper is toegevoegd, moet u het project daarom mogelijk opnieuw laden en bouwen zodat de wijzigingen juist worden herkend in IntelliSense.

#### <a name="troubleshooting"></a>Probleemoplossing
* Als u tijdens het starten een leeg, wit scherm in uw toepassing tegenkomt, moet u mogelijk afdwingen dat de navigatieaanroepen worden uitgevoerd in de hoofdthreat.
* De Intune SDK Xamarin-bindingen bieden geen ondersteuning voor apps die gebruikmaken van een framework voor meerdere platformen, zoals MvvmCross, als gevolg van conflicten tussen MvvmCross- en Intune MAM-klassen. Hoewel de integratie bij sommige klanten gelukt kan zijn na het verplaatsen van hun apps naar Xamarin.Forms zonder opmaak, bieden we geen expliciete richtlijnen of invoegtoepassingen voor app-ontwikkelaars die MvvmCross gebruiken.

### <a name="company-portal-app"></a>Bedrijfsportal-app
De Intune SDK Xamarin-bindingen zijn afhankelijk van de aanwezigheid van de Android-app [Bedrijfsportal](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) op het apparaat voor het inschakelen van app-beveiligingsbeleid. De bedrijfsportal haalt het app-beveiligingsbeleid op van de Intune-service. Tijdens de initialisatie van de app worden het beleid en de code geladen om het betreffende beleid af te dwingen bij de bedrijfsportal. De gebruiker hoeft niet te zijn aangemeld.

> [!NOTE]
> Wanneer de bedrijfsportal-app zich niet op het **Android**-apparaat bevindt, gedraagt een door Intune beheerde app zich hetzelfde als een normale app die geen ondersteuning biedt voor Intune-beleid voor de beveiliging van apps.

Voor app-beveiliging zonder apparaatregistratie hoeft de gebruiker het apparaat _**niet**_ te registreren via de bedrijfsportal-app.

### <a name="sample-applications"></a>Voorbeeldtoepassingen
Voorbeeldtoepassingen waarin MAM-functionaliteit in Xamarin.Android- en Xamarin.Forms-apps wordt belicht, zijn beschikbaar in [GitHub](https://github.com/msintuneappsdk/Taskr-Sample-Intune-Xamarin-Android-Apps).

## <a name="support"></a>Support
Als uw organisatie een bestaande Intune-klant is, kunt u contact opnemen met uw ondersteuningsmedewerker van Microsoft om een ondersteuningsticket te openen en een probleem te melden op de [GitHub-problemenpagina](https://github.com/msintuneappsdk/intune-app-sdk-xamarin/issues). We zullen u zo snel mogelijk helpen. 
