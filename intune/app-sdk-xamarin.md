---
title: Intune App SDK Xamarin-onderdeel
description: Met het Intune App SDK Xamarin-onderdeel kunt u het app-beveiligingsbeleid voor Intune inschakelen in iOS- en Android-apps die zijn gebouwd met Xamarin.
keywords: SDK, Xamarin, intune
author: Erikre
manager: dougeby
ms.author: erikre
ms.date: 03/19/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 275d574b-3560-4992-877c-c6aa480717f4
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: b69cccca8c8be859de94ca8bdb50d6030439233a
ms.sourcegitcommit: 54fc806036f84a8667cf8f74086358bccd30aa7d
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/20/2018
---
# <a name="microsoft-intune-app-sdk-xamarin-component"></a>Intune App SDK Xamarin-onderdeel

> [!NOTE]
> U kunt desgewenst eerst het artikel [Aan de slag met Intune App SDK](app-sdk-get-started.md) lezen, waarin wordt uitgelegd hoe u de integratie voor elk ondersteund platform kunt voorbereiden.

## <a name="overview"></a>Overzicht
Met het [Intune App SDK Xamarin-onderdeel](https://github.com/msintuneappsdk/intune-app-sdk-xamarin) kunt u het [appbeveleigingsbeleid voor Intune](/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) inschakelen in iOS- en Android-apps die zijn gebouwd met Xamarin. Met dit onderdeel kunnen ontwikkelaars eenvoudig beschermingsfuncties van Intune inbouwen in hun Xamarin-apps.

> [!NOTE]
> Ondersteuning voor de Intune SDK voor Xamarin is momenteel beschikbaar in de preview-versie. 

Met de Microsoft Intune App SDK Xamarin Component kunt u Intune-beveiligingsbeleid voor apps (ook wel APP- of MAM-beleid genoemd) opnemen in de apps die u met Xamarin hebt ontwikkeld. Een MAM-app is geïntegreerd met de Intune App SDK. IT-beheerders kunnen app-beveiligingsbeleid implementeren in uw mobiele app wanneer die actief door Intune wordt beheerd.

## <a name="whats-supported"></a>Wat wordt ondersteund

### <a name="developer-machines"></a>Machines van ontwikkelaars
* macOS


### <a name="mobile-app-platforms"></a>Mobiele app-platformen
* Android
* iOS


### <a name="intune-mobile-application-management-scenarios"></a>Scenario’s voor Intune Mobile Application Management

* Apparaten die zijn ingeschreven bij Intune MDM
* Apparaten die zijn ingeschreven bij EMM van derden
* Onbeheerde apparaten (niet ingeschreven bij een MDM)

Xamarin-apps die zijn gemaakt met de Intune App SDK Xamarin Component, kunnen nu app-beveiligingsbeleid van Intune ontvangen op apparaten die wel en apparaten die niet zijn ingeschreven in Mobile Device Management (MDM) van Intune.

## <a name="prerequisites"></a>Vereisten

* **[Alleen android]** Op het apparaat moet de meest recente Microsoft Intune-bedrijfsportal-app zijn geïnstalleerd.

## <a name="get-started"></a>Aan de slag

1. Lees de [licentievoorwaarden](https://github.com/msintuneappsdk/intune-app-sdk-xamarin/blob/master/Microsoft%20License%20Terms%20Intune%20App%20SDK%20Xamarin%20Component.pdf) voor het Microsoft Intune MAM Xamarin-onderdeel.

2.  Download de NuGet-pakketten van het Intune App SDK Xamarin-onderdeel van [GitHub](https://github.com/msintuneappsdk/intune-app-sdk-xamarin). Deze pakketten zijn binnenkort beschikbaar op Nuget.org.  

## <a name="enabling-intune-app-protection-polices-in-your-ios-mobile-app"></a>App-beveiligingsbeleid voor Intune inschakelen in uw mobiele iOS-app
1. Voeg het `Microsoft.Intune.MAM.Xamarin.iOS` NuGet-pakket aan uw Xamarin.iOS-project toe.
2.  Volg de algemene stappen voor het integreren van de Intune App SDK in een mobiele iOS-app. U kunt beginnen met stap 3 van de integratie-instructies uit de [Ontwikkelaarshandleiding voor Microsoft Intune App SDK voor iOS](app-sdk-ios.md#build-the-sdk-into-your-mobile-app). U kunt de laatste stap in deze sectie voor het uitvoeren van de IntuneMAMConfigurator overslaan, omdat dit hulpprogramma is opgenomen in het pakket Microsoft.Intune.MAM.Xamarin.iOS en automatisch wordt uitgevoerd tijdens de compilatie.
    **Belangrijk**: delen van sleutelketens inschakelen voor een app wijkt in Visual Studio enigszins af van de procedure in Xcode. Open de plist Entitlements van de app en zorg ervoor dat de optie 'Enable Keychain' is ingeschakeld en dat de juiste groepen voor het delen van de sleutelketen in die sectie zijn toegevoegd. Controleer vervolgens of de plist Entitlements is opgegeven in het veld 'Custom Entitlements' van de opties voor 'iOS Bundle Signing' van het project voor alle betrokken configuratie-/platformcombinaties.
3.  Nadat het onderdeel is toegevoegd en de app correct is geconfigureerd, kan uw app gebruikmaken van de Intune SDK API's. Daarvoor moet u de volgende naamruimte opnemen:

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
Voeg het `Microsoft.Intune.MAM.Xamarin.Android` NuGet-pakket aan uw Xamarin.Android-project toe.

Voor Android-apps op basis van Xamarin die geen gebruik maken van een UI-framework, leest en volgt u de [Ontwikkelaarshandleiding voor de Intune App SDK voor Android](app-sdk-android.md). Voor uw Android-app op basis van Xamarin moet u klasse, methoden en activiteiten vervangen door hun MAM-equivalent op basis van de [tabel](app-sdk-android.md#replace-classes-methods-and-activities-with-their-mam-equivalent) in de handleiding. Als uw app geen definitie van een `android.app.Application`-klasse bevat, moet u een klasse maken en zorgen voor overname van `MAMApplication`.

Voor Xamarin Forms en andere UI-frameworks hebben we het hulpprogramma `MAM.Remapper` meegeleverd. Dit hulpprogramma voert de klassevervanging voor u uit. U moet echter wel de volgende stappen uitvoeren:

1.  Voeg het `Microsoft.Intune.MAM.Remapper.Tasks` NuGet-pakket toe.

2.  Voeg de volgende regel toe aan uw Android-csproj (vervang x.x.x.x door de werkelijke pakketversie):
  ```xml
 <Import Project="$(NugetPack)\\Microsoft.Intune.MAM.Remapper.Tasks.x.x.x.x\\build\\MonoAndroid10\\Microsoft.Intune.MAM.Remapper.targets" />
  ```

3.  Stel de build-bewerking van het toegevoegde bestand `remapping-config.json` in op **RemappingConfigFile**. Het meegeleverde `remapping-config.json` werkt alleen met Xamarin.Forms. Raadpleeg het Leesmij-bestand in het Remapper NuGet-pakket voor andere UI-frameworks.

## <a name="next-steps"></a>Volgende stappen

U hebt de basisstappen voor het inbouwen van het onderdeel in uw app voltooid. U kunt nu de stappen in de Xamarin Android-voorbeeldapp volgen. We bieden twee voorbeelden, één voor Xamarin.Forms en het andere voor Android.
