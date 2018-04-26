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
ms.openlocfilehash: 9f9cc117925f59c9fb7c55d0ff10aedf09d26f93
ms.sourcegitcommit: b727b6bd6f138c5def7ac7bf1658068db30a0ec3
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/06/2018
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

## <a name="enabling-app-protection-policies-in-your-android-mobile-app"></a>App-beveiligingsbeleid inschakelen in uw mobiele Android-app
Voeg het [Microsoft.Intune.MAM.Xamarin.Android NuGet-pakket](https://www.nuget.org/packages/Microsoft.Intune.MAM.Xamarin.Android) toe aan uw Xamarin.Android-project.

Voor Xamarin.Android-apps moet u de [Intune App SDK voor Android-ontwikkelaarshandleiding](app-sdk-android.md) volledig lezen en volgen, inclusief het vervangen van klasse, methoden en activiteiten door hun MAM-equivalent op basis van de [tabel](app-sdk-android.md#replace-classes-methods-and-activities-with-their-mam-equivalent) in de handleiding. 

> [!NOTE]
> Als uw app geen definitie van een `android.app.Application`-klasse bevat, moet u een klasse maken en zorgen voor overname van `MAMApplication`.

> [!NOTE]
> Wanneer u probeert vergelijkbare API’s te vinden in de [Intune App SDK voor Android-ontwikkelaarshandleiding](app-sdk-android.md) in de `Microsoft.Intune.MAM.Xamarin.Android`-bindingen of codefragmenten uit de handleiding omzet, moet u zich ervan bewust zijn dat de bindingengenerator van Xamarin de Android-API’s op de volgende manieren aanpast:
> * Alle id's worden omgezet naar Pascale case (com.microsoft.foo -> Com.Microsoft.Foo)
> * Alle get/set-bewerkingen worden omgezet naar eigenschapsbewerkingen (bijvoorbeeld Foo.getBar() -> Foo.Bar, Foo.setBar("zap") -> Foo.Bar = "zap")
> * Alle interfaces hebben het teken I als voorvoegsel bij de naam (FooInterface -> IFooInterface)

Voor apps die gebruikmaken van Xamarin Forms of andere UI-frameworks is het hulpprogramma `Microsoft.Intune.MAM.Remapper` meegeleverd. Dit hulpprogramma voert de klassevervanging voor u uit. Ga als volgt te werk als u dit wilt gebruiken:

1.  Voeg het [Microsoft.Intune.MAM.Remapper.Tasks](https://www.nuget.org/packages/Microsoft.Intune.MAM.Remapper.Tasks) NuGet-pakket toe aan uw project.

2.  Stel de compileeractie van het `remapping-config.json`-bestand dat is opgenomen in het Nuget-pakket in op **RemappingConfigFile**. Het meegeleverde `remapping-config.json` werkt alleen met Xamarin.Forms. Raadpleeg het Leesmij-bestand in het Remapper NuGet-pakket voor andere UI-frameworks.

3.  Voeg een aanroep naar Xamarin.Forms.Forms.Init (Context, bundel) toe aan de OnMAMCreate-functie van uw MAMApplication, omdat uw toepassing met behulp van Intune-beheer op de achtergrond kan worden gestart.

4.  Voer de rest van de stappen in [Intune App SDK voor Android-ontwikkelaarshandleiding](app-sdk-android.md) uit die van toepassing zijn op uw app.

> [!NOTE]
> De compileerbewerking van remapping-config.json kan in sommige gevallen worden hersteld tijdens het bijwerken van het Microsoft.Intune.MAM.Remapper.Tasks-pakket, waardoor uw compilaties mislukken.

## <a name="next-steps"></a>Volgende stappen

U hebt de basisstappen voor het instellen van uw app voor Intune-beheer voltooid. Nu kunt u de stappen in de integratiehandleidingen voor elk van de hierboven vermelde platforms uitvoeren.

Als uw organisatie een bestaande Intune-klant is, kunt u contact opnemen met uw ondersteuningsmedewerker van Microsoft om een ondersteuningsticket te openen en een probleem te melden op de [Github-problemenpagina](https://github.com/msintuneappsdk/intune-app-sdk-xamarin/issues). U wordt zo snel mogelijk geholpen. 